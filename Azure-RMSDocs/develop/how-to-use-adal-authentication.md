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

# Instructies: ADAL-verificatie gebruiken

Verificatie met Azure RMS voor uw app met Azure Active Directory Authentication Library (ADAL).

Als u uw toepassing bijwerkt zodat dit ADAL-verificatie gebruikt in plaats van de Microsoft Online-aanmeldhulp, kunnen u en uw klanten het volgende:

- Multi-Factor Authentication gebruiken
- De RMS 2.1-client installeren zonder dat hiervoor beheerdersrechten voor de computer vereist zijn
- Uw toepassing certificeren voor Windows 10

## Twee verificatiemethoden

Dit onderwerp bevat twee verificatiemethoden met bijbehorende codevoorbeelden.

- **Interne verificatie** - OAuth-verificatie beheerd door de RMS SDK.

  Gebruik deze methode als u wilt dat de RMS-client een ADAL-verificatieprompt weergeeft als verificatie vereist is. Zie de sectie 'Interne verificatie' voor meer informatie over het configureren van uw toepassing.

  > [!Note] Als u in uw toepassing momenteel AD RMS SDK 2.1 met de aanmeldhulp gebruikt, wordt aanbevolen de interne verificatiemethode te gebruiken als pad voor uw toepassingsmigratie.

- **Externe verificatie** - OAuth-verificatie beheerd door uw toepassing.

  Gebruik deze methode als u wilt dat uw toepassing zijn eigen OAuth-verificatie gebruikt. Met deze methode oefent de RMS-client een door de toepassing gedefinieerde callback uit wanneer verificatie vereist is. Zie 'Externe verificatie' aan het eind van dit onderwerp voor een gedetailleerd voorbeeld.

  > [!Note] Met externe verificatie wordt niet de mogelijkheid geïmpliceerd om de gebruiker te wijzigen. De RMS-client gebruikt altijd de standaardgebruiker voor een bepaalde RMS-tenant.

## Interne verificatie

1. Volg de stappen voor de Azure-configuratie in [Azure RMS configureren voor ADAL verificatie](adal-auth.md). Ga vervolgens terug naar de volgende stap van de app-initialisatie.
2. U kunt nu uw toepassing configureren voor het gebruik van de interne ADAL-verificatie die wordt geleverd door RMS SDK 2.1.

Als u de RMS-client wilt configureren, voegt u een aanroep toe aan het recht [IpcSetGlobalProperty](/rights-management/sdk/2.1/api/win/functions#msipc_ipcsetglobalproperty) na het aanroepen van [IpcInitialize](/rights-management/sdk/2.1/api/win/functions#msipc_ipcinitialize) om de RMS-client te configureren. Gebruik het volgende codefragment als voorbeeld.

      C++
      IpcInitialize();

      IPC_AAD_APPLICATION_ID applicationId = { 0 };
      applicationId.cbSize = sizeof(IPC_AAD_APPLICATION_ID);
      applicationId.wszClientId = L"GUID-provided-by-AAD-for-your-app-(no-brackets)";
      applicationId.wszRedirectUri = L"RedirectionUriWeProvidedAADForOurApp://authorize";
      HRESULT hr = IpcSetGlobalProperty(IPC_EI_APPLICATION_ID, &applicationId);
      if (FAILED(hr)) {
        //Handle the error
      }

## Externe verificatie

Gebruik deze code als voorbeeld voor het beheren van uw eigen verificatietokens.
C++ extern HRESULT GetADALToken(LPVOID pContext, const IPC_NAME_VALUE_LIST& Parameters, __out wstring wstrToken) throw();

      HRESULT GetLicenseKey(PCIPC_BUFFER pvLicense, __in LPVOID pContextForAdal, __out IPC_KEY_HANDLE &hKey)
      {
          IPC_OAUTH2_CALLBACK pfGetADALToken =
          [](LPVOID pvContext, PIPC_NAME_VALUE_LIST pParameters, IPC_AUTH_TOKEN_HANDLE* phAuthToken) -> HRESULT
          {
              wstring wstrToken;
              HRESULT hr = GetADALToken(pvContext, *pParameters, wstrToken);
              return SUCCEEDED(hr) ? IpcCreateOAuth2Token(wstrToken.c_str(), OUT phAuthToken) : hr;
          };

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
          credentialContext.pcOAuth2 = &callbackCredentialContext;

          IPC_PROMPT_CTX promptContext =
          {
              sizeof(IPC_PROMPT_CTX),
              NULL,
              IPC_PROMPT_FLAG_SILENT | IPC_PROMPT_FLAG_HAS_USER_CONSENT,
              NULL,
              &credentialContext
          };

          hKey = 0L;
          return IpcGetKey(pvLicense, 0, &promptContext, NULL, &hKey);
      }

## Verwante onderwerpen

* [Gegevenstypen](/rights-management/sdk/2.1/api/win/datatypes)
* [Omgevingseigenschappen](/rights-management/sdk/2.1/api/win/environmentproperties)
* [IpcCreateOAuth2Token](/rights-management/sdk/2.1/api/win/functions#msipc_ipccreateoauth2token)
* [IpcGetKey](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgetkey)
* [IpcInitialize](/rights-management/sdk/2.1/api/win/functions#msipc_ipcinitialize)
* [IPC_CREDENTIAL](/rights-management/sdk/2.1/api/win/IPC_CREDENTIAL)
* [IPC_NAME_VALUE_LIST](/rights-management/sdk/2.1/api/win/IPC_NAME_VALUE_LIST)
* [IPC_OAUTH2_CALLBACK_INFO](/rights-management/sdk/2.1/api/win/IIPC_OAUTH2_CALLBACK_INFO)
* [IPC_PROMPT_CTX](/rights-management/sdk/2.1/api/win/IPC_PROMPT_CTX)
* [IPC_AAD_APPLICATION_ID](/rights-management/sdk/2.1/api/win/IIPC_AAD_APPLICATION_ID)


<!--HONumber=Jun16_HO2-->


