---
title: Gegevens ophalen uit de datawarehouse-API met een REST-client
description: Haal gegevens uit het Intune-datawarehouse op met een RESTful-API.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D6D15039-4036-446C-A58F-A5E18175720A
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1bbb0e8ba84e221df3a434da79c513939267648b
ms.sourcegitcommit: b8ef9d8387b4d9b2ea4e6ce937635304771e6532
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/11/2017
---
# <a name="get-data-from-the-intune-data-warehouse-api-with-a-rest-client"></a>Gegevens ophalen uit de Intune-datawarehouse-API met een REST-client

U kunt het Intune-datawarehousegegevensmodel openen via RESTful-eindpunten. Om toegang tot uw gegevens te krijgen, moet uw client zich door middel van OAuth 2.0 autoriseren met Microsoft Azure Active Directory (Azure AD). Om toegang toe te staan, moet u eerst een systeemeigen app in Azure instellen en machtigingen verlenen voor de Microsoft Intune-API. Uw lokale client wordt geautoriseerd, waarna de client met de datawarehouse-eindpunten kan communiceren via de systeemeigen app.

De stappen voor het instellen van een client zodat deze gegevens uit de datawarehouse-API kan ophalen, vereisen dat u:

1. Een client-app als systeemeigen app in Azure maakt
3. De client-app toegang geeft tot de Microsoft Intune-API
3. Een lokale REST-client maakt om de gegevens op te halen

Gebruik de volgende stappen om te leren hoe u Postman als client kunt autoriseren en gebruiken. Postman is een veelgebruikt hulpprogramma voor het oplossen van problemen en het ontwikkelen van REST-clients die met API’s werken. Raadpleeg de [Postman](https://www.getpostman.com)-site voor meer informatie over Postman. Dit onderwerp bevat ook een voorbeeld van C#-code. Dit is een voorbeeld voor het autoriseren van een client en het ophalen van gegevens uit de API.

## <a name="create-a-native-app-in-azure"></a>Een systeemeigen app maken in Azure

Maak een systeemeigen app in Azure. Deze systeemeigen app is de client-app. De client die op uw lokale apparaat draait, verwijst naar de Intune-datawarehouse-API als de lokale client om referenties vraagt. 

1. Meld u aan bij de Azure-portal voor uw tenant. Kies **Azure Active Directory** > **App-registraties** om de blade **App-registraties** te openen.
2. Klik op **Nieuwe app-registratie**.
3. Typ de app-gegevens.
    1.  Typ een beschrijvende naam, zoals Intune-datawarehouseclient voor de **Naam**.
    2.  Selecteer **Systeemeigen** als het **Toepassingstype**.
    3.  Typ een URL voor de **Aanmeldings-URL**. De aanmeldings-URL is afhankelijk van het specifieke scenario. Typ echter `https://www.getpostman.com/oauth2/callback` als u Postman wilt gebruiken. U gebruikt tijdens het verifiëren via de Azure AD de aanroep voor clientverificatie.
4.  Klik op **Maken**.

     ![Intune-datawarehouse-API](media\reports-get_rest_data_client_overview.png)

5. Noteer de **toepassings-id** van deze app. U gebruikt de id in de volgende sectie.
6. Voeg een sleutel toe als u van plan bent om Postman te gebruiken. De sleutel wordt gebruikt als het clientgeheim wanneer u verifieert met Azure AD. Een sleutel toevoegen:
    1.  Klik op **Sleutels** onder **API-toegang** op de blade Instellingen voor de app.
    2.  Typ bij **Beschrijving** een naam voor uw sleutel, zoals Clientgeheim.
    3.  Selecteer als Duur **1 jaar**.
    4.  Klik op **Opslaan**. 
    5.  Kopieer de waarde van uw sleutel. U kunt de sleutel niet ophalen nadat u de blade **Instellingen** voor de sleutels hebt gesloten.

## <a name="grant-the-native-app-access-to-the-microsoft-intune-api"></a>De systeemeigen app toegang verlenen tot de Microsoft Intune-API

U hebt nu een app gedefinieerd in Azure. Verleen via de systeemeigen app toegang tot de Microsoft Intune-API.

1.  Klik op de systeemeigen app. U hebt de app een naam gegeven, zoals Intune-datawarehouseclient.
2.  Selecteer op de blade **Instellingen** de optie **Vereiste machtigingen**
3.  Klik op de blade **Vereiste machtigingen** op **Toevoegen**.
4.  Klik op **Een API selecteren**.
5.  Zoek de naam van de webtoepassing. Deze heet **Microsoft Intune API**.
6.  Klik op de app in de lijst.
7.  Klik op **Selecteren**.
8.  Schakel het selectievakje **Gedelegeerde machtigingen** in om **Datawarehouse-gegevens ophalen uit Microsoft Intune** toe te voegen.

    ![Toegang inschakelen](media\reports-get_rest_data_client_access.png)

9.  Klik op **Selecteren**.
10.  Klik op **Gereed**.
11.  Klik eventueel op **Machtigingen verlenen** op de blade Vereiste machtigingen. Er wordt nu toegang verleend aan alle accounts in de huidige map. Zo wordt voorkomen dat het dialoogvenster voor toestemming wordt weergegeven voor elke gebruiker in de tenant. Raadpleeg [Toepassingen integreren met Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications) voor meer informatie.
12.  Klik op **Ja**.

## <a name="get-data-from-the-microsoft-intune-api-with-postman"></a>Gegevens van de Microsoft Intune-API ophalen met Postman

U kunt de Intune-datawarehouse-API gebruiken met een generieke REST-client, zoals Postman. Postman kan inzicht bieden in de functies van de API en het onderliggende OData-gegevensmodel en uw verbindingsproblemen met de API-resources oplossen. In deze sectie vindt u informatie over het genereren van een Auth 2.0-token voor uw lokale client. De client heeft het token nodig voor verificatie met Azure AD en om de API-resources te openen.

### <a name="information-you-will-need-to-make-the-call"></a>Informatie die u nodig hebt voor de aanroep

U hebt de volgende informatie nodig om een REST-aanroep te doen met Postman:

| Kenmerk        | Beschrijving                                                                                                                                                                          | Voorbeeld                                                                                       |
|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| Callback-URL     | Stel deze in als de callback-URL op de pagina met app-instellingen.                                                                                                                              | https://www.getpostman.com/oauth2/callback                                                    |
| Tokennaam       | Een tekenreeks die wordt gebruikt om de referenties door te geven aan de Azure-app. Het proces genereert uw token, zodat u de aanroep naar de datawarehouse-API kunt maken.                          | Drager                                                                                        |
| Auth.-URL         | Dit is de URL die wordt gebruikt voor verificatie. | https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com |
| URL van toegangstoken | Dit is de URL die wordt gebruikt om het token te verlenen.                                                                                                                                              | https://login.microsoftonline.com/common/oauth2/token |
| Client-id        | U hebt deze gemaakt en genoteerd toen u de systeemeigen app in Azure maakte.                                                                                               | 4184c61a-e324-4f51-83d7-022b6a81b991                                                          |
| Clientgeheim    | U hebt deze gemaakt en genoteerd toen u een sleutel aan de client-app toevoegde in Azure.                                                                                              | JZoRZGPmN9xwsUnfX9UW877dkV5Fn/qQClhr7SuyMUQ=                                                  |
| Scope (optioneel) | Leeg                                                                                                                                                                               | U kunt het veld leeg laten.                                                                     |
| Toekenningstype       | Het token is een autorisatiecode.                                                                                                                                                  | Autorisatiecode                                                                            |

U hebt het eindpunt nodig. In dit voorbeeld halen we gegevens op uit de entiteit **datums**. De entiteit **datums** heeft de volgende indeling: `https://fef.{aus}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`. U gebruikt de URL van uw tenantbeheer. U hebt de URL van uw tenantbeheer gebruikt toen u uw webtoepassing maakte.

### <a name="make-the-rest-call"></a>De REST-aanroep maken

Om een nieuw toegangstoken voor Postman te verkrijgen, moet u de autorisatie-URL voor Azure AD, uw client-id en uw clientgeheim toevoegen. Postman zal de autorisatiepagina openen, waar u uw referenties moet invoeren.

#### <a name="add-the-information-used-to-request-the-token"></a>Voeg de informatie toe die werd gebruikt om het token aan te vragen.

1.  Download Postman als u deze nog niet hebt geïnstalleerd. U kunt Postman downloaden via [www.getpostman](https://www.getpostman.com).
2.  Open Postman. Kies de HTTP-bewerking **GET**.
3.  Plak de URL van het eindpunt in het adres. Het resultaat ziet er ongeveer als volgt uit:  

    `https://fef.msua06.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`
4.  Kies het tabblad **Autorisatie** en selecteer **OAuth 2.0** in de lijst **Type**.
5.  Klik op **Nieuw toegangstoken ophalen**.
6.  Controleer of u de callback-URL al aan uw app hebt toegevoegd in Azure. De callback-URL is `https://www.getpostman.com/oauth2/callback`.
7.  Typ Drager als **Tokennaam**.
8.  Voeg de **Auth.-URL** toe. Het resultaat ziet er ongeveer als volgt uit:  

    `https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com`
9.  Voeg de **URL van toegangstoken** toe. Het resultaat ziet er ongeveer als volgt uit:  

     `https://login.microsoftonline.com/common/oauth2/token`

10. Voeg de **Client-id** toe van de systeemeigen app die u in Azure hebt gemaakt en die u `Intune Data Warehouse Client` hebt genoemd. Het resultaat ziet er ongeveer als volgt uit:  

     `4184c61a-e324-4f51-83d7-022b6a81b991`

11. Voeg het **Clientgeheim** toe dat u als sleutel hebt gedefinieerd toen u uw systeemeigen app in Azure maakte. Het resultaat ziet er ongeveer als volgt uit: 

     `F360R69M0MS72OB6YAqTyXO9MsXZx/OJTgAE2HB4k2k=`

12. Selecteer **Autorisatiecode** en vraag het toegangstoken lokaal aan.

13. Klik op **Token aanvragen**.

    ![Informatie voor het token](media\reports-postman_getnewtoken.png)

14. Typ uw referenties op de autorisatiepagina voor Active AD. De lijst met bestaande tokens in Postman bevat nu het token met de naam `Bearer`.
16. Kies het token. Selecteer **Header** bij Token toevoegen aan.
17. Klik op **Token gebruiken**. De lijst met headers bevat de nieuwe sleutelwaarde voor Autorisatie en de waarde `Bearer <your-authorization-token>`.

#### <a name="send-the-call-to-the-endpoint-using-postman"></a>De aanroep naar het eindpunt verzenden met Postman

1.  Klik op **Verzenden**.
2.  De geretourneerde gegevens worden in de hoofdtekst van het antwoord van Postman weergegeven.

    ![Postman 200OK](media\reports-postman_200OK.png)

## <a name="create-a-rest-client-c-to-get-data-from-the-intune-data-warehouse"></a>Een REST-client (C#) maken om gegevens uit het Intune-datawarehouse op te halen

Het volgende voorbeeld bevat een eenvoudige REST-client. De code gebruikt de klasse **httpClient** van de .Net-bibliotheek. Nadat de client referenties voor Azure AD heeft verkregen, bouwt de client een GET REST-aanroep op om de gegevensentiteit van de datawarehouse-API te ontvangen.

> [!Note]  
> U kunt het volgende codevoorbeeld openen [op GitHub](https://github.com/Microsoft/Intune-Data-Warehouse/blob/master/Samples/CSharp/Program.cs). Raadpleeg de GitHub-repo voor de meest recente wijzigingen en updates van het voorbeeld.

1.  Open **Microsoft Visual Studio**.
2.  Kies **Bestand** > **Nieuw project**. Vouw **Visual C#** uit en kies **Console-app (.Net Framework)**. 
3.  Noem het project ` IntuneDataWarehouseSamples`, blader naar de locatie waar u het project wilt opslaan en klik vervolgens op **OK**.
3.  Klik met de rechtermuisknop op de naam van de oplossing in Solution Explorer en selecteer vervolgens **NuGet-pakketten beheren voor oplossing**. Klik op **Bladeren** en typ vervolgens 'Microsoft.IdentityModel.Clients.ActiveDirectory' in het zoekvak.
4. Kies het pakket, selecteer het project **IntuneDataWarehouseSamples** onder Pakketten beheren voor uw oplossing en klik vervolgens op **Installeren**. 
5. Klik op **Ik ga akkoord** om de licentie van het NuGet-pakket te accepteren.
6. Open `Program.cs` in de Solution Explorer.

    ![Project in Visual Studio](media\reports-get_rest_data_in.png)

7.  Vervang de code in Program.cs door de volgende code:  
    ```csharp
namespace IntuneDataWarehouseSamples
{
    using System;
    using System.Net.Http;
    using System.Net.Http.Headers;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;

    class Program
    {
     static void Main(string[] args)
  {
   /**
    * TODO: Replace the below values with your own.
    * emailAddress - The email address of the user that you will authenticate as.
    *
    * password  - The password for the above email address.
    *    This is inline only for simplicity in this sample. We do not 
    *    recommend storing passwords in plaintext.
    *
    * applicationId - The application ID of the native app that was created in AAD.
    *
    * warehouseUrl   - The data warehouse URL for your tenant. This can be found in 
    *      the Azure portal.
    * 
    * collectionName - The name of the warehouse entity collection you would like to 
    *      access.
    */
   var emailAddress = "intuneadmin@yourcompany.com";
   var password = "password_of(intuneadmin@yourcompany.com)";
   var applicationId = "<Application ID>";
   var warehouseUrl = "https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta";
   var collectionName = "dates";

   var adalContext = new AuthenticationContext("https://login.windows.net/common/oauth2/token");
   AuthenticationResult authResult = adalContext.AcquireTokenAsync(
    resource: "https://api.manage.microsoft.com/",
    clientId: applicationId,
    userCredential: new UserPasswordCredential(emailAddress, password)).Result;

   var httpClient = new HttpClient();
   httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue("Bearer", authResult.AccessToken);

   var uriBuilder = new UriBuilder(warehouseUrl);
   uriBuilder.Path += "/" + collectionName;

   HttpResponseMessage response = httpClient.GetAsync(uriBuilder.Uri).Result;

   Console.Write(response.Content.ReadAsStringAsync().Result);
   Console.ReadKey();
  }
    }
    ```

8.  Werk de `TODO`'s in de voorbeeldcode bij.
9.  Druk op **Ctrl + F5** om de Intune.DataWarehouseAPIClient-client te bouwen en in de foutopsporingsmodus uit te voeren.

    ![Datumentiteit verkregen in JSON-indeling.](media\reports-get_rest_data_output.png)

10.  Bekijk de uitvoer van de console. De uitvoer bevat gegevens in een JSON-indeling, afkomstig uit de entiteit **datums** in uw Intune-tenant.

## <a name="next-steps"></a>Volgende stappen

U kunt informatie over autorisatie, de structuur van de API-URL en OData-eindpunten vinden in [Use the Intune Data Warehouse API](reports-api-url.md) (De Intune-datawarehouse-API gebruiken). 

U kunt ook het gegevensmodel voor het Intune-datawarehouse raadplegen voor informatie over de gegevensentiteiten die in de API zijn opgenomen. Zie [Intune Data Warehouse API Data Model](reports-ref-data-model.md) (Gegevensmodel van Intune-datawarehouse-API) voor meer informatie