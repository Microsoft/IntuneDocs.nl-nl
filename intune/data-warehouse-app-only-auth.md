---
title: Intune Datawarehouse-verificatie enkel voor toepassing
titleSuffix: Microsoft Intune
description: In dit onderwerp wordt Datawarehouse-verificatie enkel voor toepassing beschreven.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d7166563-6bb5-4624-b8c8-6b300a997c3a
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b72a0bf1a5f5c996ad299bd84ff6f927ef780059
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52185199"
---
# <a name="intune-data-warehouse-application-only-authentication"></a>Intune Datawarehouse-verificatie enkel voor toepassing

U kunt een toepassing instellen met behulp van Azure Active Directory (Azure AD) en verifiëren bij Intune Datawarehouse. Dit proces is handig voor websites, apps en achtergrondprocessen waarbij de toepassing geen toegang mag hebben tot de referenties van de gebruiker. Met behulp van de volgende stappen geeft u uw toepassing met Azure AD toestemming met behulp van OAuth 2.0.

## <a name="authorization"></a>Autorisatie

Azure Active Directory (Azure AD) maakt gebruik van OAuth 2.0 om het mogelijk te maken dat u toegang tot webtoepassingen en web-API's in uw Azure AD-tenant kunt autoriseren. In deze handleiding wordt beschreven hoe u uw toepassing verifieert met C#. De OAuth 2.0-autorisatiecodestroom wordt beschreven in sectie 4.1 van de OAuth 2.0-specificatie. Zie [Toegang tot webtoepassingen die gebruikmaken van OAuth 2.0 en Azure Active Directory autoriseren](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code) voor meer informatie.


## <a name="azure-keyvault"></a>Azure KeyVault

Het volgende proces maakt gebruik van een persoonlijke methode om een app-sleutel te verwerken en te converteren. Deze persoonlijke methode heet SecureString. U kunt Azure KeyVault als alternatief gebruiken om de app-sleutel op te slaan. Bekijk [Key Vault](https://azure.microsoft.com/services/key-vault/) voor meer informatie.

## <a name="create-a-web-app"></a>Een web-app maken

In deze sectie geeft u informatie over de web-app waarnaar u in Intune wilt verwijzen. Een web-app is een client-/servertoepassing. De server levert de web-app, waaronder de gebruikersinterface, inhoud en functionaliteit. Dit type app wordt afzonderlijk onderhouden op internet. U gebruikt Intune om de web-app toegang te geven tot Intune. De gegevensstroom wordt geïnitieerd door de web-app. 

1.  Meld u aan bij [Azure Portal](https://portal.azure.com).
2.  Zoek met behulp van het veld **Resources, services en documenten zoeken**, boven in Azure Portal, naar **Azure Active Directory**.
3.  Selecteer **Azure Active Directory** in het vervolgkeuzemenu **Services**.
4.  Selecteer **App-registraties**.
5.  Klik op **Nieuwe toepassing registreren** om de blade **Maken** weer te geven.
6.  Voeg op de blade **Maken** de app-details toe:

    - Een app-naam, bijvoorbeeld *Intune App-Only Auth*.
    - Het **Toepassingstype**. Kies **Web-app/API** om een app toe te voegen die een webtoepassing, een web-API of beide is.
    - De **Aanmeldings-URL** van de toepassing. Dit is de locatie waar gebruikers tijdens het verificatieproces automatisch naartoe navigeren. Ze moeten bewijzen dat ze zijn wie ze beweren te zijn. Bekijk [What is application access and single sign-on with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis) (wat is toepassingstoegang en eenmalige aanmelding met Azure Active Directory?) voor meer informatie.

7.  Klik onderaan de blade **Maken** op **Maken**.

    >[!NOTE] 
    > Kopieer de **Toepassings-id** uit de blade **Geregistreerde app** voor later gebruik.

## <a name="create-a-key"></a>Een sleutel maken

In deze sectie genereert Azure AD een sleutelwaarde voor uw app.

1.  Selecteer op de blade **App-registraties** de nieuwe app om de app-blade weer te geven.
2.  Selecteer **Instellingen** bovenaan de blade om de blade **Instellingen** weer te geven.
3.  Selecteer **Sleutels** op de blade **Instellingen**.
4.  Voeg de **Beschrijving** van de sleutel toe, evenals een periode in **Geldig tot** en een **Waarde** voor de sleutel.
5.  Klik op **Opslaan** om de sleutels van de toepassing op te slaan en bij te werken.
6.  U moet de gegenereerde sleutelwaarde (base64-gecodeerd) kopiëren.

    >[!NOTE] 
    > De sleutelwaarde verdwijnt nadat u de blade **Sleutels** verlaat. U kunt de sleutel niet later ophalen uit deze blade. Kopieer de sleutel voor later gebruik.

## <a name="grant-application-permissions"></a>Toepassingsmachtigingen verlenen

In deze sectie verleent u machtigingen aan de toepassingen.

1.  Selecteer **Vereiste machtigingen** op de blade **Instellingen**.
2.  Klik op **Toevoegen**.
3.  Selecteer **Een API toevoegen** om de blade **Een API selecteren** weer te geven.
4.  Selecteer **Microsoft Intune API (MicrosoftIntuneAPI)** en klik vervolgens op **Selecteren** op de blade **Een API selecteren**. De stap **Machtigingen selecteren** wordt geselecteerd en de blade **Toegang inschakelen** wordt weergegeven.
5.  Kies de optie **Datawarehouse-gegevens ophalen uit Microsoft Intune** in de sectie **Toepassingsmachtigingen**.
6.  Klik op **Selecteer** op de blade **Toegang inschakelen**.
7.  Klik op **Gereed** op de blade **API-toegang toevoegen**.
8.  Klik op **Machtigingen verlenen** op de blade **Vereiste machtigingen** en klik op **Ja** wanneer u wordt gevraagd om de bestaande machtigingen die deze toepassing al heeft, bij te werken.

## <a name="generate-token"></a>Token genereren

Maak in Visual Studio een Console-app-project (.NET Framework) dat het .NET Framework ondersteunt en C# als codetaal gebruikt.

1.  Selecteer **Bestand** > **Nieuw** > **Project** om het dialoogvenster **Nieuw project** weer te geven.
2.  Selecteer aan de linkerkant **Visual C#** om alle .NET Framework-projecten weer te geven.
3.  Selecteer **Console-app (.NET Framework)**, voeg een naam voor de app toe en klik vervolgens op **OK** om de app te maken.
4.  Selecteer **Program.cs** in **Solution Explorer** om de code weer te geven.
5.  Selecteer in het pop-upmenu **Toevoegen** > **Nieuw item**. Het dialoogvenster **Nieuw item toevoegen** wordt weergegeven.
6.  Selecteer aan de linkerkant **Code** onder **Visual C#**.
7.  Selecteer **Klasse**, wijzig de naam van de klasse in *IntuneDataWarehouseClass.cs* en klik op **Toevoegen**.
8.  Voeg de volgende code in in de methode <code>Main</code>:

    ``` csharp
         var applicationId = ConfigurationManager.AppSettings["appId"].ToString();
         SecureString applicationSecret = ConvertToSecureStr(ConfigurationManager.AppSettings["appKey"].ToString()); // Load as SecureString from configuration file or secret store (i.e. Azure KeyVault)
         var tenantDomain = ConfigurationManager.AppSettings["tenantDomain"].ToString();
         var adalContext = new AuthenticationContext($"https://login.windows.net/" + tenantDomain + "/oauth2/token");
    
         AuthenticationResult authResult = adalContext.AcquireTokenAsync(
             resource: "https://api.manage.microsoft.com/",
             clientCredential: new ClientCredential(
                 applicationId,
                 new SecureClientSecret(applicationSecret))).Result;
    ``` 

9. Voeg aanvullende naamruimtes toe door de volgende code bovenaan het codebestand in te voegen:

    ``` csharp
     using System.Security;
     using Microsoft.IdentityModel.Clients.ActiveDirectory;
     using System.Configuration;
    ``` 

10. Voeg na de methode <code>Main</code> de volgende persoonlijke methode toe om de app-sleutel te verwerken en te converteren:

    ``` csharp
    private static SecureString ConvertToSecureStr(string appkey)
    {
        if (appkey == null)
            throw new ArgumentNullException("AppKey must not be null.");
    
        var secureAppKey = new SecureString();
    
        foreach (char c in appkey)
            secureAppKey.AppendChar(c);
    
        secureAppKey.MakeReadOnly();
        return secureAppKey;
    }
    ```

11. Klik in **Solution Explorer** met de rechtermuisknop op **Referenties** en selecteer vervolgens **NuGet-pakketten beheren**.
12. Zoek naar *Microsoft.IdentityModel.Clients.ActiveDirectory* en installeer het bijbehorende Microsoft NuGet-pakket.
13. Selecteer en open in **Solution Explorer** het bestand *App.config*.
14. Voeg de sectie <code>appSettings</code> toe, zodat de XML er als volgt uitziet:

    ``` xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup> 
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <appSettings>
          <add key="appId" value="App ID created from 'Create a Web App' procedure"/>
          <add key="appKey" value="Key created from 'Create a key' procedure" />
          <add key="tenantDomain" value="contoso.onmicrosoft.com"/>
        </appSettings>
    </configuration>
    ``` 

15. Werk de waarden <code>appId</code>, <code>appKey</code> en <code>tenantDomain</code> bij, zodat deze overeenkomen met uw unieke app-gerelateerde waarden.
16. Bouw uw app.

    >[!NOTE] 
    > Bekijk het [Intune Datawarehouse-codevoorbeeld](https://github.com/Microsoft/Intune-Data-Warehouse/tree/master/Samples/CSharp ) voor aanvullende implementatiecode.

## <a name="next-steps"></a>Volgende stappen
Lees meer informatie over Azure Key Vault in [Wat is Azure Key Vault?](https://docs.microsoft.com/azure/key-vault/key-vault-whatis)

