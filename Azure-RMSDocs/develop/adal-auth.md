---
# required metadata

title: ADAL-verificatie voor uw RMS-toepassing | Azure RMS
description: Biedt een overzicht van het verificatieproces met ADAL
keywords: authentication, RMS, ADAL
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: f89f59b7-33d1-4ab3-bb64-1e9bda269935

# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
** Deze SDK-inhoud is niet actueel. U kunt tijdelijk de [huidige versie](https://msdn.microsoft.com/library/windows/desktop/hh535290(v=vs.85).aspx) van de documentatie op MSDN vinden. **
# ADAL-verificatie voor uw RMS-toepassing

Verificatie met Azure RMS voor uw app met Azure ADAL maakt nu deel uit van de RMS-client 2.1.

Als u uw toepassing bijwerkt zodat dit ADAL-verificatie gebruikt in plaats van de Microsoft Online-aanmeldhulp, kunnen u en uw klanten het volgende:

- Multi-Factor Authentication gebruiken
- De RMS 2.1-client installeren zonder dat hiervoor beheerdersrechten voor de computer vereist zijn
- Uw toepassing certificeren voor Windows 10

## Twee verificatiemethoden

Dit onderwerp bevat twee verificatiemethoden met bijbehorende codevoorbeelden.

- **Interne verificatie** - OAuth-verificatie beheerd door de RMS SDK. Gebruik deze methode als u wilt dat de RMS-client een ADAL-verificatieprompt weergeeft als verificatie vereist is. Zie de sectie 'Interne verificatie' voor meer informatie over het configureren van uw toepassing.

> [!NOTE] Als u in uw toepassing momenteel AD RMS SDK 2.1 met de aanmeldhulp gebruikt, wordt aanbevolen de interne verificatiemethode te gebruiken als pad voor uw toepassingsmigratie.

- **Externe verificatie** - OAuth-verificatie beheerd door uw toepassing. Gebruik deze methode als u wilt dat uw toepassing zijn eigen OAuth-verificatie gebruikt. Met deze methode oefent de RMS-client een door de toepassing gedefinieerde callback uit wanneer verificatie vereist is. Zie 'Externe verificatie' aan het eind van dit onderwerp voor een gedetailleerd voorbeeld.

> [!NOTE] Met externe verificatie wordt niet de mogelijkheid geïmpliceerd om de gebruiker te wijzigen. De RMS-client gebruikt altijd de standaardgebruiker voor een bepaalde RMS-tenant.

### Interne verificatie

U hebt het volgende nodig:

- Een [abonnement voor Microsoft Azure](https://azure.microsoft.com/en-us/) (een gratis proefversie is voldoende):
- Een abonnement voor Microsoft Azure Rights Management (een gratis account voor [RMS voor personen](https://technet.microsoft.com/en-us/library/dn592127.aspx) is voldoende).

> [!NOTE] Vraag uw IT-beheerder of u beschikt over een abonnement voor Microsoft Azure Rights Management en laat uw IT-beheerder de volgende stappen uitvoeren. Als uw organisatie geen abonnement heeft, vraagt u uw IT-beheerder om er een te maken. Uw IT-beheerder moet zich bovendien abonneren met een werk- of schoolaccount, in plaats van een Microsoft-account (bijvoorbeeld Hotmail).

Na het aanmelden voor Microsoft Azure:

- Meld u met een account met beheerdersbevoegdheden aan bij de [Azure-beheerportal](https://manage.windowsazure.com) voor uw organisatie.

![Azure-aanmelding](../media/AzurePortalLogin.png)

- Blader omlaag naar de toepassing **Active Directory** aan de linkerkant van de portal.

![Selecteer Active Directory](../media/AzureADPick.png)

- Als u nog geen map hebt gemaakt, kiest u de knop **Nieuw** in de linkeronderhoek van de portal.

![Selecteer NIEUW](../media/AzureNewBtn.png)

- Selecteer het tabblad **Rights Management** en zorg ervoor dat de **Rights Management-status** **Actief**, **Onbekend** of **Niet geautoriseerd** is. Als de status **Inactief** is, kiest u de knop **Activeren** middenonder in de portal en bevestigt u uw selectie.

![Kies ACTIVEREN](../media/RMTab.png)

- Maak nu een nieuwe *Eigen toepassing* in uw directory door via Toepassingen uw directory te kiezen.

![Selecteer TOEPASSINGEN](../media/CreateNativeApp.png)

- Kies vervolgens de knop **Toevoegen** middenonder in de portal.

![Selecteer TOEVOEGEN](../media/AddAppBtn.png)

- Kies bij de prompt **Add an application my organization is developing** (Een toepassing toevoegen die door mijn organisatie wordt ontwikkeld).

![Add an application my organization is developing (Een toepassing toevoegen die door mijn organisatie wordt ontwikkeld) selecteren](../media/AddAnAppPick.png)

- Geef uw toepassing een naam door **EIGEN CLIENTTOEPASSING** te selecteren en de knop **Volgende** te kiezen.

![Uw app een naam geven](../media/TellUsInput.png)

- Voeg een omleidings-URI toe en klik op volgende. De omleidings-URI moet een geldige URI zijn en moet uniek zijn voor uw directory. U kunt bijvoorbeeld het volgende gebruiken: `com.mycompany.myapplication://authorize`.

![Omleidings-URI toevoegen](../media/RedirectURI.png)

- Selecteer uw toepassing in de map en kies **CONFIGUREREN**.

![Kies CONFIGUREREN](../media/ConfigYourApp.png)

>[!NOTE] Kopieer de **CLIENT-ID** en **OMLEIDINGS-URI** en sla deze op voor toekomstig gebruik tijdens het configureren van de RMS-client.

- Blader naar beneden in uw toepassing-instellingen en kies de knop **Toepassing toevoegen** onder **Machtigingen voor andere toepassingen**.

![Toepassing toevoegen selecteren](../media/PermissionsToOtherBtn.png)

- Voeg nu deze GUID `00000012-0000-0000-c000-000000000000` toe aan het invoervak **BEGINNEN MET** en klik op de knop Controleren.

![GUID toevoegen](../media/AddGUID.png)

- Kies de plusknop (+) naast **Microsoft Rights Management**.

![Selecteer de knop +.](../media/ChoosePlusBtn.png)

- Kies nu het vinkje in de linkeronderhoek van het dialoogvenster.

![Het vinkje kiezen](../media/ChooseCheck.png)

- U kunt nu een afhankelijkheid aan uw toepassing toevoegen voor Azure RMS. U kunt de afhankelijkheid als volgt toevoegen: selecteert het nieuwe item **Microsoft Rights Management Services** onder **Machtigingen voor andere toepassingen** en kies selectievakje **Beveiligde inhoud maken en openen voor gebruikers** onder de keuzelijst **Gedelegeerde machtigingen:**.

![Machtigingen instellen](../media/AddDependency.png)

- Sla uw toepassing op om de wijzigingen vast te leggen. Kies hiervoor het pictogram **OPSLAAN** middenonder in de portal.

![OPSLAAN selecteren](../media/SaveApplication.png)

- U kunt nu uw toepassing configureren voor het gebruik van de interne ADAL-verificatie die wordt geleverd door RMS SDK 2.1. Als u de RMS-client wilt configureren, voegt u een aanroep toe aan het recht [IpcSetGlobalProperty](/rights-management/sdk/2.1/api/win/IpcSetGlobalProperty) na het aanroepen van [IpcInitialize](/rights-management/sdk/2.1/api/win/IpcInitialize) om de RMS-client te configureren. Gebruik het volgende codefragment als voorbeeld.


    IpcInitialize();

    IPC_AAD_APPLICATION_ID applicationId = {0};   applicationId.cbSize = sizeof(IPC_AAD_APPLICATION_ID);   applicationId.wszClientId L"GUID-provided-by-AAD-for-your-app-(no-brackets) = ';   applicationId.wszRedirectUri = L "RedirectionUriWeProvidedAADForOurApp://authorize";

    HRESULT hr = IpcSetGlobalProperty(IPC_EI_APPLICATION_ID, &amp;applicationId);

    als (FAILED(hr)) {    //Behandel de fout   }

### Externe verificatie

- Gebruik deze code als voorbeeld voor het beheren van uw eigen verificatietokens.


    extern HRESULT GetADALToken(LPVOID pContext, const IPC_NAME_VALUE_LIST&amp; Parameters, __out wstring wstrToken) throw();

    HRESULT GetLicenseKey(PCIPC_BUFFER pvLicense, __in LPVOID pContextForAdal, __out IPC_KEY_HANDLE &amp;hKey) { IPC_OAUTH2_CALLBACK pfGetADALToken =         [](LPVOID pvContext, PIPC_NAME_VALUE_LIST pParameters, IPC_AUTH_TOKEN_HANDLE* phAuthToken) -&gt; HRESULT { wstring wstrToken; HRESULT hr = GetADALToken(pvContext, *pParameters, wstrToken); return SUCCEEDED(hr) ? IpcCreateOAuth2Token(wstrToken.c_str(), OUT phAuthToken) : hr; };

      IPC_OAUTH2_CALLBACK_INFO callbackCredentialContext =
      {
          sizeof(IPC_OAUTH2_CALLBACK_INFO),
          pfGetADALToken,
          pContextForAdal
      };

      IPC_CREDENTIAL credentialContext =
      {
          IPC_CREDENTIAL_TYPE_OAUTH2,
          NULL
      };
      credentialContext.pcOAuth2 = &amp;callbackCredentialContext;

      IPC_PROMPT_CTX promptContext =
      {
        sizeof(IPC_PROMPT_CTX),
        NULL,
        IPC_PROMPT_FLAG_SILENT | IPC_PROMPT_FLAG_HAS_USER_CONSENT,
        NULL,
        &amp;credentialContext
      };

      hKey = 0L;
      return IpcGetKey(pvLicense, 0, &amp;promptContext, NULL, &amp;hKey);
  }

### Verwante onderwerpen
- [Gegevenstypen](/rights-management/sdk/2.1/api/win/Data%20types)
- [Omgevingseigenschappen](/rights-management/sdk/2.1/api/win/Environment%20properties)
- [IpcCreateOAuth2Token](/rights-management/sdk/2.1/api/win/IpcCreateOAuth2Token)
- [IpcGetKey](/rights-management/sdk/2.1/api/win/IpcGetKey)
- [IpcInitialize](/rights-management/sdk/2.1/api/win/IpcInitialize)
- [IPC_CREDENTIAL](/rights-management/sdk/2.1/api/win/IPC\_CREDENTIAL)
- [IPC_NAME_VALUE_LIST](/rights-management/sdk/2.1/api/win/IPC\_NAME\_VALUE\_LIST)
- [IPC_OAUTH2_CALLBACK_INFO](/rights-management/sdk/2.1/api/win/IPC\_OAUTH2\_CALLBACK\_INFO)
- [IPC_PROMPT_CTX](/rights-management/sdk/2.1/api/win/IPC\_PROMPT\_CTX)
- [IPC_AAD_APPLICATION_ID](/rights-management/sdk/2.1/api/win/IPC\_AAD\_APPLICATION\_ID)


<!--HONumber=Jun16_HO1-->


