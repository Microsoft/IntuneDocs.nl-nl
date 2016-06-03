---
# required metadata

title: Procedure: verificatie toevoegen aan uw app | Azure RMS
description: Beschrijft de beginselen van gebruikersverificatie voor uw app met RMS-functionaliteit.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 200D9B23-F35D-4165-9AC4-C482A5CE1D28
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Procedure: verificatie toevoegen aan uw app

Dit onderwerp beschrijft de beginselen van gebruikersverificatie voor uw app met RMS-functionaliteit.

## Wat is gebruikersverificatie?
Gebruikersverificatie is een essentiële stap voor de communicatie tussen de app op uw apparaat en de RMS-infrastructuur. Het verificatieproces maakt gebruik van het OAuth 2.0-standaardprotocol dat de volgende informatie vereist over de huidige gebruiker en zijn/haar verificatieaanvraag: **instantie**, **resource** en **gebruikers-id**.

**Opmerking**: ‘bereik’ wordt momenteel niet gebruikt, maar mogelijk later wel en is daarom gereserveerd voor toekomstig gebruik.

 

**Callback voor gebruikersverificatie**: de Microsoft Rights Management SDK 4.2 maakt gebruik van uw implementatie van een verificatiecallback als u geen toegangstoken biedt, wanneer uw toegangstoken moet worden vernieuwd of wanneer het toegangstoken is verlopen.

Elk van de RMS API's van het platform heeft een callback die moet worden geïmplementeerd om gebruikersverificatie te kunnen inschakelen.

-   De Android-API maakt gebruikt van de [**AuthenticationRequestCallback**](/rights-management/sdk/4.2/api/android/com.microsoft.rightsmanagement#msipcthin2_authenticationrequestcallback_interface_java)- en de [**AuthenticationCompletionCallback**](/rights-management/sdk/4.2/api/android/authenticationcompletioncallback#msipcthin2_authenticationcompletioncallback_interface_java)-interface.
-   De IOS-/OS X-API maakt gebruikt van het [**MSAuthenticationCallback**](/rights-management/sdk/4.2/api/iOS/iOS#msipcthin2_msauthenticationcallback_protocol_objc)-protocol.
-   De WinPhone-API maakt gebruikt van de [**IAuthenticationCallback**](/rights-management/sdk/4.2/api/winrt/Microsoft.RightsManagement#msipcthin2_iauthenticationcallback)-interface.
-   De Linux API-maakt gebruikt van de [IAuthenticationCallback](http://azuread.github.io/rms-sdk-for-cpp/classrmscore_1_1modernapi_1_1IAuthenticationCallback.html)-interface.

## Welke bibliotheek u voor verificatie moet gebruiken

Om uw verificatiecallback te implementeren, moet u de juiste bibliotheek downloaden en uw ontwikkelomgeving configureren voor het gebruik hiervan. U vindt de ADAL-bibliotheken voor deze platforms op GitHub. De volgende bronnen bevatten richtlijnen voor het instellen van uw omgeving en het gebruik van de bibliotheek.

-   [Windows Azure Active Directory Authentication Library (ADAL) voor iOS](https://github.com/MSOpenTech/azure-activedirectory-library-for-ios/)
-   [Windows Azure Active Directory Authentication Library (ADAL) voor Mac](https://github.com/MSOpenTech/azure-activedirectory-library-for-ios/)
-   [Windows Azure Active Directory Authentication Library (ADAL) voor Android](https://github.com/MSOpenTech/azure-activedirectory-library-for-android)
-   [Windows Azure Active Directory Authentication Library (ADAL) voor dotnet](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet)
-   Voor de Linux SDK wordt de ADAL-bibliotheek geleverd met de SDK-bron via [Github](https://github.com/AzureAD/rms-sdk-for-cpp).

**Opmerking** Wij raden u aan een van bovengenoemde Active Directory Authentication Libraries (ADAL) te gebruiken. Het is echter ook mogelijk een andere verificatiebibliotheek toe te passen.

## Invoer voor verificatie met Azure Active directeur Authentication Library (ADAL)

De ADAL vereist verschillende parameters om een gebruiker van Azure RMS (of AD RMS) met succes te verifiëren. Dit zijn de standaard OAuth 2.0-parameters die in het algemeen vereist zijn voor elke Azure AD-app, net als voor apps met RMS-functionaliteit. U kunt de huidige richtlijnen voor ADAL-gebruik vinden in de Leesmij-bestanden van de betreffende, hierboven genoemde Github-opslagplaatsen.

Deze parameters en richtlijnen zijn vereist voor RMS-werkstromen:

-   **Instantie**: de URL voor het verificatie-eindpunt, meestal AAD of ADFS. Deze parameter wordt aan uw app verstrekt door de RMS SDK-verificatiecallback.
-   **Resource**: de URL/URI van de servicetoepassing die u probeert te openen, meestal Azure RMS of AD RMS. Deze parameter wordt aan uw app verstrekt door de RMS SDK-verificatiecallback.
-   **Gebruikers-id**: de UPN, meestal het e-mailadres van de gebruiker die toegang wil tot de app. Deze parameter kan leeg zijn als de gebruiker nog niet bekend is en wordt ook gebruikt voor het cachen van het gebruikerstoken of het aanvragen van een token uit de cache. De parameter wordt in het algemeen ook gebruikt als 'hint' om een gebruiker naar iets te vragen.
-   **Client-id**: de id van uw client-app. Dit moet een geldige Azure AD-toepassings-id zijn. Zie Procedure: een Azure-toepassings-id ophalen voor meer informatie.
-   **Omleidings-Uri**: voorziet de verificatiebibliotheek van een URI-doel voor de verificatiecode. Houd er rekening mee dat er specifieke indelingen vereist zijn voor iOS en Android. Deze worden uitgelegd in de Leesmij-bestanden van de betreffende ADAL-opslagplaatsen in GitHub.

    Android: `msauth://packagename/Base64UrlencodedSignature`

    iOS: `<app-scheme>://<bundle-id>`

**Opmerking** Als uw app niet aan deze richtlijnen voldoet, mislukken Azure RMS- en Azure AD-werkstromen waarschijnlijk en worden ze niet ondersteund door Microsoft.com. Bovendien wordt de Rights Management License Agreement (RMLA) mogelijk overtreden als er in een productie-app een ongeldige client-id wordt gebruikt.

## Hoe moet de implementatie van een verificatiecallback eruitzien?

**Voorbeelden van verificatiecode**: deze SDK bevat voorbeeldcode die het gebruik van verificatiecallbacks laat zien. Voor uw gemak worden deze codevoorbeelden hier weergegeven, evenals in elk van de volgende gekoppelde onderwerpen.

**Android-gebruikersverificatie**: zie [Voorbeelden van Android-code](android-code.md), **stap 2** van het eerste scenario 'Een bestand met RMS-beveiliging gebruiken' voor meer informatie.


    class MsipcAuthenticationCallback implements AuthenticationRequestCallback
    {
    ...

    @Override
    public void getToken(Map<String, String> authenticationParametersMap,
                         final AuthenticationCompletionCallback authenticationCompletionCallbackToMsipc)
    {
        String authority = authenticationParametersMap.get("oauth2.authority");
        String resource = authenticationParametersMap.get("oauth2.resource");
        String userId = authenticationParametersMap.get("userId");
        mClientId = “12345678-ABCD-ABCD-ABCD-ABCDEFGHIJ”; // get your registered Azure AD application ID here
        mRedirectUri = “urn:ietf:wg:oauth:2.0:oob”;
        final String userHint = (userId == null)? "" : userId;
        AuthenticationContext authenticationContext = App.getInstance().getAuthenticationContext();
        if (authenticationContext == null || !authenticationContext.getAuthority().equalsIgnoreCase(authority))
        {
            try
            {
                authenticationContext = new AuthenticationContext(App.getInstance().getApplicationContext(), authority, …);
                App.getInstance().setAuthenticationContext(authenticationContext);
            }
            catch (NoSuchAlgorithmException e)
            {
                …
                authenticationCompletionCallbackToMsipc.onFailure();
            }
            catch (NoSuchPaddingException e)
            {
                …
                authenticationCompletionCallbackToMsipc.onFailure();
            }
       }
        App.getInstance().getAuthenticationContext().acquireToken(mParentActivity, resource, mClientId, mRedirectURI, userId, mPromptBehavior,
                       "&USERNAME=" + userHint, new AuthenticationCallback<AuthenticationResult>()
                        {
                            @Override
                            public void onError(Exception exc)
                            {
                                …
                                if (exc instanceof AuthenticationCancelError)
                                {
                                     …
                                    authenticationCompletionCallbackToMsipc.onCancel();
                                }
                                else
                                {
                                     …
                                    authenticationCompletionCallbackToMsipc.onFailure();
                                }
                            }

                            @Override
                            public void onSuccess(AuthenticationResult result)
                            {
                                …
                                if (result == null || result.getAccessToken() == null
                                        || result.getAccessToken().isEmpty())
                                {
                                     …
                                }
                                else
                                {
                                    // request is successful
                                    …
                                    authenticationCompletionCallbackToMsipc.onSuccess(result.getAccessToken());
                                }
                            }
                        });
                         }


**iOS-en OS X-gebruikersverificatie**: zie [Voorbeelden van iOS-en OS X-code](ios-os-x-code-examples.md) voor meer informatie.

**Stap 2** van het eerste scenario 'Een bestand met RMS-beveiliging gebruiken'.


    // AuthenticationCallback holds the necessary information to retrieve an access token.
    @interface MsipcAuthenticationCallback : NSObject<MSAuthenticationCallback>

    @end

    @implementation MsipcAuthenticationCallback

    - (void)accessTokenWithAuthenticationParameters:
         (MSAuthenticationParameters *)authenticationParameters
                                completionBlock:
         (void(^)(NSString *accessToken, NSError *error))completionBlock
    {
    ADAuthenticationError *error;
    ADAuthenticationContext* context = [ADAuthenticationContext authenticationContextWithAuthority:authenticationParameters.authority error:&error];

    NSString *appClientId = @”12345678-ABCD-ABCD-ABCD-ABCDEFGHIJ”;

    // get your registered Azure AD application ID here

    NSURL *redirectURI = [NSURL URLWithString:@”ms-sample://com.microsoft.sampleapp”];

    // get your <app-scheme>://<bundle-id> here
    // Retrieve token using ADAL
    [context acquireTokenWithResource:authenticationParameters.resource
                             clientId:appClientId
                          redirectUri:redirectURI
                               userId:authenticationParameters.userId
                      completionBlock:^(ADAuthenticationResult *result)
                      {
                          if (result.status != AD_SUCCEEDED)
                          {
                              NSLog(@"Auth Failed");
                              completionBlock(nil, result.error);
                          }
                          else
                          {
                              completionBlock(result.accessToken, result.error);
                          }
                      }

        ];
    }



**Linux-/C++-gebruikersverificatie**: zie [Voorbeelden van Linux-code](linux-c-code-examples.md) voor meer informatie.



    // Class Header
    class AuthCallback : public IAuthenticationCallback {
    private:

      std::shared_ptr<rmsauth::FileCache> FileCachePtr;
      std::string clientId_;
      std::string redirectUrl_;

      public:

      AuthCallback(const std::string& clientId,
               const std::string& redirectUrl);
      virtual std::string GetToken(shared_ptr<AuthenticationParameters>& ap) override;
    };

    class ConsentCallback : public IConsentCallback {
      public:

      virtual ConsentList Consents(ConsentList& consents) override;
    };

    // Class Implementation
    AuthCallback::AuthCallback(const string& clientId, const string& redirectUrl)
    : clientId_(clientId), redirectUrl_(redirectUrl) {
      FileCachePtr = std::make_shared<FileCache>();
    }

    string AuthCallback::GetToken(shared_ptr<AuthenticationParameters>& ap)
    {
      string redirect =
      ap->Scope().empty() ? redirectUrl_ : ap->Scope();

      try
      {
        if (redirect.empty()) {
        throw rmscore::exceptions::RMSInvalidArgumentException(
              "redirect Url is empty");
      }

      if (clientId_.empty()) {
      throw rmscore::exceptions::RMSInvalidArgumentException("client Id is empty");
      }

      AuthenticationContext authContext(
        ap->Authority(), AuthorityValidationType::False, FileCachePtr);

      auto result = authContext.acquireToken(ap->Resource(),
                                           clientId_, redirect,
                                           PromptBehavior::Auto,
                                           ap->UserId());
      return result->accessToken();
      }

      catch (const rmsauth::Exception& ex)
      {
        // out logs
        throw;
      }
    }



 

 


<!--HONumber=Apr16_HO4-->


