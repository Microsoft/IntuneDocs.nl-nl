---
title: IPCHelloWorld - een voorbeeldtoepassing | Azure RMS
description: Dit onderwerp bevat instructies voor het maken van een voorbeeldtoepassing met rechten.
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 581451A2-9558-4D0D-9D01-BEAB282C5A83
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ac6afddc2b39d6209ef1b89d8d84011942cdba5a
ms.openlocfilehash: e75ec6c04afd171552697f79deb33ad2cfe2c4e1


---
** Deze SDK-inhoud is niet actueel. U kunt tijdelijk de [huidige versie](https://msdn.microsoft.com/library/windows/desktop/hh535290(v=vs.85).aspx) van de documentatie op MSDN vinden. **
# IPCHelloWorld - een voorbeeldtoepassing

Dit onderwerp bevat instructies voor het maken van een voorbeeldtoepassing met rechten.

Met deze eenvoudige toepassing, IPCHelloWorld, kunt u zich richten op de bassiconcepten en code van een toepassing met rechten.

U kunt de voorbeeldtoepassing, [Webinar\_Collateral.zip](https://connect.microsoft.com/site1170/Downloads/DownloadDetails.aspx?DownloadID=42440), downloaden via Microsoft Connect. De overige downloadbare items op de site zijn voor aanvullend gemak hier geïntegreerd.

**Opmerking** Het IPCHelloWorld-project is al geconfigureerd voor de Rights Management Services SDK 2.1. Voor meer informatie over het configureren van een nieuw project met gebruik van de RMS SDK 2.1 raadpleegt u [Visual Studio configureren](how-to-configure-a-visual-studio-project-to-use-the-ad-rms-sdk-2-0.md).

 
In de volgende gedeelten staat informatie over de belangrijkste toepassingsstappen en kennis die u moet hebben.

## MSIPC.dll laden

Voordat u RMS SDK 2.1-functies kunt aanroepen, moet u de functie [**IpcInitialize**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcinitialize) aanroepen om MSIPC.dll te laden.



    hr = IpcInitialize();

    if (FAILED(hr))
    {
      wprintf(L"Failed to initialize MSIPC. Are you sure the runtime is installed?\n");
      goto exit;
    }



## Sjablonen inventariseren

In een RMS-sjabloon wordt het beleid gedefinieerd dat wordt gebruikt om gegevens te beveiligen: hierin worden gebruikers opgegeven die toegang hebben tot de gegevens en welke rechten deze gebruikers hebben. RMS-sjablonen worden op de RMS-server geïnstalleerd.

In het volgende codefragment worden de beschikbare RMS-sjablonen van de standaard-RMS-server geïnventariseerd.



    hr = IpcGetTemplateList(NULL, 0, 0, NULL, NULL, &pcTil);

    if (FAILED(hr))
    {
      DisplayError(L"IpcGetTemplateList failed", hr);
      goto exit;
    }



Met deze aanroep worden de RMS-sjablonen opgehaald die zijn geïnstalleerd op de standaardserver. Daarna worden de resultaten geladen in de [**IPC\_TIL**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcinitialize)-structuur waarnaar wordt verwezen door de *pcTil*-variabele. Vervolgens worden de sjablonen weergeven.



    if (0 == pcTil->cTi)
    {
      wprintf(L"* No templates configured for your RMS server * \n\n");
      wprintf(L"\\------------------------------------------------------\n\n");
      goto exit;
    }

    for (DWORD dw = 0; dw < pcTil->cTi; dw++)
    {
      wprintf(L"Template #%d:\n", dw);
      wprintf(L"    Name:         %s\n", pcTil->aTi[dw].wszName);
      wprintf(L"    Issued by:    %s\n", pcTil->aTi[dw].wszIssuerDisplayName);
      wprintf(L"    Description:  %s\n", pcTil->aTi[dw].wszDescription);
      wprintf(L"\n");
    }



## Een licentie serialiseren

Voordat u gegevens kunt beveiligen, moet u een licentie serialiseren en een inhoudssleutel ophalen. De inhoudssleutel wordt gebruikt om de gevoelige gegevens te versleutelen. De geserialiseerde licentie wordt meestal gekoppeld aan de versleutelde gegevens. De licentie wordt door de gebruiker van de beveiligde gegevens gebruikt. De consument moet de functie [**IpcGetKey**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgetkey) aanroepen met de geserialiseerde licentie om de inhoudssleutel op te halen voor het ontsleutelen van de inhoud en voor het ophalen van het beleid dat is gekoppeld aan de inhoud.

Om het eenvoudig te houden, gebruikt u voor het serialiseren van een licentie de eerste RMS-sjabloon die is geretourneerd door [**IpcGetTemplateList**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgettemplatelist).

Normaal gesproken gebruikt u een gebruikersdialoogvenster om gebruikers toe te staan de gewenste sjabloon te selecteren.



    hr = IpcSerializeLicense((LPCVOID)pcTil->aTi[0].wszID, IPC_SL_TEMPLATE_ID,
    0, NULL, &hContentKey, &pSerializedLicense);

    if (FAILED(hr))
    {
      DisplayError(L"IpcSerializeLicense failed", hr);
      goto exit;
    }



Hierna beschikt u over de inhoudssleutel (*hContentKey*) en de geserialiseerde licentie (*pSerializedLicense*) die u moet koppelen aan de beveiligde gegevens.

## Gegevens beveiligen

U bent er nu klaar voor om de gevoelige gegevens te versleutelen met de functie [**IpcEncrypt**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcencrypt). Eerst bekijkt u in de functie **IpcEncrypt** hoe groot de versleutelde gegevens zullen worden.



    cbText = (DWORD)(sizeof(WCHAR)*(wcslen(wszText)+1));
    hr = IpcEncrypt(hContentKey, 0, TRUE, (PBYTE)wszText, cbText,
    NULL, 0, &cbEncrypted);

    if (FAILED(hr)) {
      DisplayError(L"IpcEncrypt failed", hr);
      goto exit;
    }



*wszText* bevat de tekst zonder opmaak die u wilt beveiligen. De functie [**IpcEncrypt**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcencrypt) retourneert de grootte van de versleutelde gegevens in de parameter *cbEncrypted*.

Wijs nu geheugen toe voor de versleutelde gegevens.



    pbEncrypted = (PBYTE)LocalAlloc(LPTR, cbEncrypted);

    if (NULL == pbEncrypted) {
      wprintf(L"Out of memory\n");
      goto exit;
    }


Als laatste voert u de daadwerkelijke versleuteling uit.



    hr = IpcEncrypt(hContentKey, 0, TRUE, (PBYTE)wszText, cbText,
    pbEncrypted, cbEncrypted, &cbEncrypted);

    if (FAILED(hr)) {
      DisplayError(L"IpcEncrypt failed", hr);
      goto exit;
    }


Na deze stap beschikt u over de versleutelde gegevens (*pbEncrypted*) en de geserialiseerde licentie (*pSerializedLicense*) die wordt gebruikt door consumenten om de gegevens te ontsleutelen.

## Foutafhandeling

In dit voorbeeld wordt de functie **DisplayError** gebruikt voor het afhandelen van fouten.



    void DisplayError(LPCWSTR wszErrorInfo, HRESULT hrError)
    {
        LPCWSTR wszErrorMessageText = NULL;

        if (SUCCEEDED(IpcGetErrorMessageText(hrError, 0, &wszErrorMessageText))) {
          wprintf(L"%s: 0x%08X (%s)\n", wszErrorInfo, hrError, wszErrorMessageText);
        }
        else {
          wprintf(L"%s: 0x%08X\n", wszErrorInfo, hrError);
        }
    }   


De functie **DisplayError** maakt gebruik van de functie [**IpcGetErrorMessageText**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgeterrormessagetext) om het foutbericht op te halen uit de bijbehorende foutcode en verwerkt deze in de standaarduitvoer.

## Opschonen

U moet alle toegewezen resources vrijgeven om het proces te voltooien.



    if (NULL != pbEncrypted) {
      LocalFree((HLOCAL)pbEncrypted);
    }

    if (NULL != pSerializedLicense) {
      IpcFreeMemory((LPVOID)pSerializedLicense);
    }

    if (NULL != hContentKey) {
      IpcCloseHandle((IPC_HANDLE)hContentKey);
    }

    if (NULL != pcTil) {
      IpcFreeMemory((LPVOID)pcTil);
    }


## Verwante onderwerpen

* [Opmerkingen voor ontwikkelaars](developer-notes.md)
* [Visual Studio configureren](how-to-configure-a-visual-studio-project-to-use-the-ad-rms-sdk-2-0.md)
* [**IpcEncrypt**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcencrypt)
* [**IpcGetErrorMessageText**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgeterrormessagetext)
* [**IpcGetKey**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgetkey)
* [**IpcGetTemplateList**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgettemplatelist)
* [**IpcInitialize**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcinitialize)
* [**IPC\_TIL**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcinitialize)
* [Webinar\_Collateral.zip](https://connect.microsoft.com/site1170/Downloads/DownloadDetails.aspx?DownloadID=42440)
 

 



<!--HONumber=Jun16_HO4-->


