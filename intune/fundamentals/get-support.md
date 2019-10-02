---
title: Ondersteuning voor Microsoft Intune krijgen
titleSuffix: Microsoft Intune
description: Online- en telefonische ondersteuning verkrijgen voor betaalde Microsoft Intune-abonnementen en proefabonnementen.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/01/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7fc95d17-098e-4da5-8a09-a96476569dd9
ms.reviewer: cacamp
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8c4d40d3f15fe23511f3f15f7c13181a0fa72f6b
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71726515"
---
# <a name="how-to-get-support-for-microsoft-intune"></a>Ondersteuning voor Microsoft Intune krijgen  

[!INCLUDE [azure_portal](../../intune-classic/includes/note-for-both-portals.md)]  
  
Microsoft biedt wereldwijde technische, voorverkoop-, facturerings- en abonnementsondersteuning voor Microsoft Intune. Ondersteuning is online en telefonisch beschikbaar voor betaalde abonnementen en proefabonnementen. Online technische ondersteuning is beschikbaar in het Engels en Japans. Telefonische ondersteuning en online-ondersteuning bij factureren zijn in meer talen beschikbaar.

Als Intune-beheerder kunt u de optie **Help en ondersteuning** gebruiken om vanuit de Azure-portal een onlineondersteuningsticket voor Intune in te dienen. Als u een ondersteuningsincident wilt maken en beheren, moet uw account een Azure AD-rol (Azure Active Directory) hebben met de *actie* **microsoft.office365.supportTickets/tickets/manage**. Zie [beheerdersrollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) voor informatie over rollen en machtigingen in Azure AD die zijn vereist voor het maken van een ondersteuningsticket.  

>[!IMPORTANT]  
> Neem voor technische ondersteuning voor externe producten die met Intune werken (zoals SaaSwedo, Cisco of Lookout), contact op met de leverancier van dat product. Open pas een ondersteuningsaanvraag voor Intune als u zeker weet dat het andere product juist is geconfigureerd.
>
> Raadpleeg de sectie [Probleemoplossing](help-desk-operators.md) in de Intune-documentatie voor informatie over het oplossen van problemen met betrekking tot Microsoft Intune.

## <a name="known-issues-for-creating-support-incidents"></a>Bekende problemen bij het maken van ondersteuningsincidenten  

Als uw account wel beschikt over de vereiste machtigingen, maar geen toegang kan krijgen tot Help en ondersteuning, of er geen ondersteuningsincident kan worden gemaakt of beheerd, bekijkt u de volgende bekende problemen en oplossingen:  
- Verouderd gebruikerstoken voor uw account. Om dit probleem op te lossen meldt u zich af bij alle actieve consolesessies, meld u zich opnieuw aan, en probeert u vervolgens een ondersteuningsincident te maken of beheren. 
- Meerdere actieve sessies. Als u als meerdere gebruikers of bij meerdere sessies bent aangemeld, meldt u alle extra consoles af totdat u er één overhoudt. Vervolgens probeert u met één actieve sessie een ondersteuningsincident te maken of beheren.

Er kunnen aanvullende acties nodig zijn om toegangsproblemen op te lossen:
- Wis alle cookies voor uw actieve browsersessie, en probeer vervolgens opnieuw om een ondersteuningsincident te maken of beheren.
- Gebruik een InPrivate-browsingsessie om u aan te melden bij Intune, en probeer een ondersteuningsincident te maken of beheren.  

Ga naar het [Microsoft 365-beheercentrum](https://admin.microsoft.com) en maak van hieruit een ondersteuningsticket als de voorgaande tijdelijke oplossingen niet hebben geholpen. We werken momenteel aan een oplossing. Deze zal eind van de zomer beschikbaar zijn.  

## <a name="help-and-support-experience"></a>Help en ondersteuning-ervaring  

De Help en ondersteuning-ervaring voor Intune is beschikbaar via de [Microsoft 365 Device Management-portal](https://devicemanagement.microsoft.com) en via alle blades (of pagina's) onder Intune in Azure Portal. 

![Intune-blades](./media/get-support/intune-blades.png)


De *Help en ondersteuning*-ervaring is vergelijkbaar met de ervaring in het [Microsoft 365-beheercentrum](https://admin.microsoft.com/) en vervangt de vorige *Help en ondersteuning*, die beschikbaar blijft voor andere services in Azure. 

Gebruik de volgende opties voor toegang tot Help en ondersteuning:  
- **Dashboard Apparaatbeheer:**
  - Nadat u een functiegebied voor Intune hebt geselecteerd, selecteert u de optie voor **Help en ondersteuning**.
  - Selecteer op een willekeurig knooppunt in de Apparaatbeheer-portal het pictogram **?** in de rechterbovenhoek van de portal en gebruik vervolgens de vervolgkeuzelijst om de service te selecteren waarvoor u hulp wilt. Het pictogram **?** in de Apparaatbeheer-portal ondersteunt meerdere services en u moet de specifieke service selecteren waarvoor u hulp nodig hebt.  

    ![Uw service selecteren](./media/get-support/select-a-service.png)

    Nadat u een service hebt geselecteerd, ziet u de pagina *Help en ondersteuning* voor die service. Vervolgens kunt u [details opgeven](#specify-details-about-an-issue) over het specifieke probleem waarbij u hulp nodig hebt.  

    Als de resultaten van uw zoekopdracht niet overeenkomen met de verwachtingen voor uw service, controleert u of de juiste service is geselecteerd. De geselecteerde service wordt net na *Help en ondersteuning* weergegeven.  Als de juiste service niet is geselecteerd, klikt u op *Een service selecteren* om terug te gaan naar de vervolgkeuzelijst voor het selecteren van de service.   

    ![Uw service bevestigen](./media/get-support/confirm-your-service-selection.png) 


- **In de Azure-portal:**
  - **Help en ondersteuning** op een Intune-blade of -pagina selecteren

  Als u in de Azure-portal het pictogram **?** selecteert in de rechterbovenhoek of **Help en ondersteuning** in het navigatiedeelvenster aan de linkerkant selecteert, wordt *Help en ondersteuning* voor Azure geopend. Vanuit *Help en ondersteuning* voor Azure kunt u niet rechtstreeks een Intune-ondersteuningsincident openen, maar u kunt wel naar de pagina *Help en ondersteuning* voor Intune gaan door de volgende acties uit te voeren: 
  1. Selecteer Nieuwe ondersteuningsaanvraag.
  2. Geef bij Type probleem de waarde Technisch op.
  3. Geef bij Service de waarde Microsoft Intune op.
  4. Selecteer de koppeling naar de pagina Help en ondersteuning voor Intune.

> [!NOTE]  
> Als uw exemplaar van Intune wordt gehost op de Government Compute Cloud (GCC), ook wel een soevereine cloud zoals Azure Government genoemd, raadpleegt u Intune-ondersteuning voor Government Compute Cloud, verderop in dit artikel. De *Help en ondersteuning*-ervaring voor Intune is pas later dit jaar beschikbaar voor de GCC. 


Wanneer u *Help en ondersteuning* opent, is de weergave in de portal afhankelijk van of u actieve ondersteuningsincidenten hebt. Als u Premier Support hebt, bevat de weergave ook enkele extra elementen en opties:
- **Geen actieve ondersteuningsincidenten**: U ziet de pagina **Hebt u hulp nodig?** , zoals u kunt zien in de volgende afbeelding van het dashboard Apparaatbeheer.  
- **Actieve ondersteuningsincidenten**: U ziet de pagina [Ondersteuningstickets](#view-support-cases), waarop de lijst met uw actieve incidenten wordt weergegeven.  
- **Premier Support-contract**: Uw ervaring is hetzelfde als de eerste twee opties, maar de pagina Hebt u hulp nodig? bevat de volgende extra elementen: 
  - Na de paginatitel **Hebt u hulp nodig?** ziet u de Premier Support-banner:  
    ![Premier Support-banner](./media/get-support/premier-banner.png)
  - In de sectie **Ondersteuning vragen** van de pagina kunt u het initiële **ernst**niveau instellen wanneer u telefonisch een serviceaanvraag maakt.


![Het dashboard Apparaatbeheer en de pagina Hebt u hulp nodig?](./media/get-support/help-support-dashboard.png)

In deze weergave kunt u de volgende acties uitvoeren:

1. [Details opgeven](#specify-details-about-an-issue) over het probleem waarbij u hulp nodig hebt  
2. [Contextgevoelige Help](#view-context-sensitive-help) en gerelateerde oplossingen weergeven die zijn gebaseerd op de details die u hebt opgegeven  
3. [Ondersteuning krijgen](#get-support) met behulp van een e-mailadres of telefoonnummer  
4. [Ondersteuningscases weergeven](#view-support-cases) die u eerder hebt geopend met deze nieuwe werkstroom  

### <a name="specify-details-about-an-issue"></a>Details opgeven over een probleem 

Wanneer u Help en ondersteuning opent vanaf een locatie die wordt ondersteund in de nieuwe versie, wordt de pagina **Hebt u hulp nodig?** geopend. Op deze pagina kunt u informatie opgeven over een probleem. Terwijl u gegevens invoert, biedt de console algemene query's op basis van de trefwoorden die u gebruikt. Selecteer een aangeboden keuze of voltooi uw eigen beschrijving van het probleem. Als u uw eigen beschrijving invoert, selecteert u **Hulp vragen** om deze te verzenden. Nadat u een query hebt ingediend, keert de console terug naar de contextgevoelige informatie waarmee het probleem mogelijk kan worden opgelost.

Hier volgen enkele voorbeelden van query's die u kunt verzenden:
  
- *Ik kan het iOS-apparaat niet herstellen*  
- *Ik kan geen beleid voor voorwaardelijke toegang maken*  

![Geef op de pagina Hebt u hulp nodig? het probleem op](./media/get-support/describe-the-issue.png)

### <a name="view-context-sensitive-help"></a>Contextgevoelige Help weergeven 

Nadat u een voorgestelde query hebt geaccepteerd of uw eigen query hebt verzonden, worden contextafhankelijke resultaten weergegeven onder **Oplossingen weergeven**. Deze resultaten omvatten zowel Intune-specifieke ondersteuning bij zelfhulp als extra resultaten die zijn geretourneerd na een webzoekopdracht op basis van de querycriteria.  
![Resultaten weergeven](./media/get-support/view-results.png)

### <a name="get-support"></a>Ondersteuning krijgen 

Als u het probleem niet kunt oplossen met de zelfhulp of de webgebaseerde ondersteuning, gebruikt u de console om een ondersteuningsaanvraag per e-mail of telefoon te openen.  
Selecteer op de pagina **Hebt u hulp nodig?** de optie die u wilt gebruiken.  

  > [!NOTE] 
  > E-mailaanvragen voor ondersteuning zijn niet beschikbaar voor alle tenants.  

- Geef uw e-mailadres op voor een e-mailaanvraag. Indien gewenst kunt u bijlagen toevoegen aan uw inzending. Selecteer **Verzenden** om de aanvraag te openen. 

  ![E-mailaanvraag](./media/get-support/email-support.png)
  
- Geef uw telefoonnummer op voor een aanvraag voor telefonische ondersteuning. Indien gewenst kunt u tevens uw e-mailadres invoeren en bijlagen toevoegen aan uw inzending. Selecteer Bel mij om de aanvraag te verzenden.  



   ![Telefonische aanvraag](./media/get-support/phone-support.png)

**Premier Support**:  
Als u een Premier Support-contract hebt, hebt u dezelfde opties voor het maken van een incident voor telefonische ondersteuning. U kunt ook de **Ernst** voor de ondersteuningsaanvraag via de terugbelfunctie opgeven en ervoor kiezen om het ondersteuningsticket te maken op basis van uw Mission Critical-contract.  

![Premier Support-opties](./media/get-support/premier-phone-support-options.png)


### <a name="view-support-cases"></a>Ondersteuningscases weergeven  

Selecteer de knop Geschiedenis om de ondersteuningsincidenten weer te geven die u hebt gemaakt.  

![Ondersteuningscases weergeven](./media/get-support/view-support-tickets.png)

- Alleen de ondersteuningscases die u met de nieuwe werkstroom opent, zijn binnen deze werkstroom zichtbaar. Als u deze wilt weergeven, gebruikt u een Help en ondersteuning-weergave in de console voor apparaatbeheer of op de Intune-blade in Azure Portal. Deze cases hebben een nummer van acht cijfers. U kunt deze cases ook weergeven vanuit het Microsoft 365-beheercentrum.  

- Cases die u hebt geopend zonder gebruik van de Help en ondersteuning-ervaring van Intune, blijven ongewijzigd. Als u deze wilt weergeven, moet u een Help en ondersteuning-weergave gebruiken die geen deel uitmaakt van de Intune-ervaring of het dashboard Apparaatbeheer. Deze cases hebben een nummer dat begint met **117** of **118** en 15 cijfers lang is. Als u deze wilt weergeven:

    1. Meld u aan bij Azure (<https://portal.azure.com>) met uw Intune-beheerdersreferenties en selecteer de *?* in de rechterbovenhoek van de portal en selecteer vervolgens *Help + ondersteuning* om naar de gelijknamige[Azure Help + ondersteuning](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview)pagina te gaan.

    2. Op de pagina **Help + ondersteuning** kunt u de lijst met **Recente ondersteuningsaanvragen** weergeven en deze selecteren om meer details te zien.
 

## <a name="azure-help--support-experience"></a>Azure Help en ondersteuning-ervaring 

Wanneer u het navigatiedeelvenster **Help en ondersteuning** aan de linkerkant gebruikt of de optie **?** rechtsboven in de Azure-portal gebruikt, opent u de Azure Help en ondersteuning-ervaring. Deze is anders dan de Intune Help en ondersteuning-ervaring.  

Sinds april 2019 hebt u geen toegang tot de Azure *Help en ondersteuning*-ervaring om hulp te krijgen met Intune, tenzij u een abonnement op de Government Compute Cloud (GCC) hebt.  

Als uw exemplaar van Intune niet op GCC wordt uitgevoerd, wordt u bij navigatie in Azure *Help en ondersteuning* omgeleid naar de Intune *Help en ondersteuning*-ervaring voor het maken en beheren van ondersteuningsincidenten.  


## <a name="intune-support-for-government-compute-cloud"></a>Intune-ondersteuning voor Government Compute Cloud  

Als uw Intune-abonnement wordt gehost op de Government Compute Cloud (GCC), ook wel een soevereine cloud zoals Azure Government genoemd, hebt u nog geen toegang tot de nieuwere Intune Help en ondersteuning-ervaring.  Gebruik in plaats daarvan de volgende informatie om ondersteuning te vragen voor Intune. 


### <a name="create-an-online-support-ticket"></a>Een onlineondersteuningsticket maken 

>[!IMPORTANT]    
> Als *Help en ondersteuning* wordt overgezet naar een nieuw systeem dat nog niet beschikbaar is voor de GCC en u een ondersteuningsincident maakt, wordt in de portal een ondersteuningscase voorzien van een identificatienummer van 15 cijfers. Wanneer het 15-cijferige geval wordt gemaakt, wordt die case gespiegeld voor gebruik door Microsoft Ondersteuning. Deze gespiegelde case wordt gemaakt in een nieuw ondersteuningssysteem, maakt gebruik van een 8-cijferige case-id en wordt gebruikt door ondersteuningsservices voor het bijhouden van alle activiteit en communicatie voor uw ondersteuningsincident. Kort nadat uw 15-cijferige case is gemaakt, ontvangt u een e-mailbericht met het 8-cijferige nummer van de gespiegelde ondersteuningscase die wordt gebruikt door de ondersteuningsservices.  
> 
> Ondersteun persoonlijk werk en communiceer op basis van de 8-cijferige ondersteuningscase. Gebruik de 8-cijferige ondersteuningscase alleen om de communicatie te registreren en de voortgang van het incident bij te houden. U ontvangt updates per e-mail op basis van die 8-cijferige ondersteuningscase die fungeert als de record voor het bijhouden van het werk aan uw case. Er worden geen details gelogd in het 15-cijferige ondersteuningsincident. Wanneer de ondersteuning is voltooid en de 8-cijferige ondersteuningscase wordt gesloten, wordt deze status ook weergegeven in de 15-cijferige ondersteuningscase die u kunt bekijken in de Azure-portal.  Er mogen geen andere updates of statuswijzigingen worden verwacht voor de ondersteuningscase van 15 cijfers.  
> 
> Als de overgangen tussen ondersteuningsprogramma's later dit jaar worden voltooid, lijkt de ondersteuningservaring die door Intune op de cloud voor de overheid wordt gehost, op de standaard *Help en ondersteuning*-ervaring die op dit moment beschikbaar is voor Intune-abonnementen die worden gehost op de openbare cloud.  


1. Meld u aan bij Azure Portal (<https://portal.azure.com>) met de referenties van een Intune-beheerder. Kies de **?** in de rechterbovenhoek van de portal en selecteer vervolgens **Help + ondersteuning** om naar de gelijknamige[Azure Help + ondersteuning](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview)pagina te gaan.

   ![Afbeelding van de vraagtekenkoppeling, waarbij de koppeling Help en ondersteuning is gemarkeerd](./media/get-support/azure-get-support.png)

2. Selecteer **Nieuwe ondersteuningsaanvraag** op de pagina **Help en ondersteuning** van Azure.

   ![Afbeelding van de pagina Help en ondersteuning met de koppeling Nieuwe ondersteuningsaanvraag gemarkeerd](./media/get-support/azure-support-ticket-link.png)

3. Op het tabblad **Basis** moet u voor de meeste technische problemen met Intune de volgende opties kiezen:
   - **Type probleem**: **Technisch**
   - **Abonnement**: <*uw abonnement*>
   - **Service**: **Microsoft Intune**
   - **Type probleem**: Kies het probleemtype in de vervolgkeuzelijst.
   - **Subtype van het probleem**: Kies het subprobleemtype in de vervolgkeuzelijst.
   - **Onderwerp**: Beschrijf kort het probleem waarbij u hulp nodig hebt.

   ![Afbeelding van het tabblad Basis op de pagina Help en ondersteuning - Nieuwe ondersteuningsaanvraag](./media/get-support/help-new-support-case-basics.png)

   Kies **Volgende: Oplossingen** om door te gaan.
4. Bekijk op het tabblad **Oplossing** de aanbevolen stappen die u mogelijk helpen uw probleem op te lossen zonder een ticket in te dienen. Als u nog steeds een ondersteuningsaanvraag wilt maken nadat u de stappen hebt bekeken, klikt u op **Volgende: Details**.

   ![Afbeelding van het tabblad Oplossing op de pagina Help en ondersteuning - Nieuwe ondersteuningsaanvraag](./media/get-support/help-new-support-case-solutions.png)
5. Vul in het tabblad **Details** de details van uw probleem, de ondersteuningsmethode en uw contactgegevens in en klik op **Volgende: Beoordelen en maken**.

   ![Afbeelding van het tabblad Details op de pagina Help en ondersteuning - Nieuwe ondersteuningsaanvraag](./media/get-support/help-new-support-case-details.png)
6. Bekijk de informatie, controleer of deze klopt, en kies vervolgens **Maken** om uw ondersteuningsaanvraag in te dienen.

   ![Afbeelding van het tabblad Beoordelen en maken op de pagina Nieuwe ondersteuningsaanvraag](./media/get-support/help-new-support-case-create.png)

>[!IMPORTANT]
>Als u een vraag over facturering of abonnementen hebt, kunt u een aanvraag voor ondersteuning openen in het [Microsoft 365-beheercentrum](https://admin.microsoft.com/Support/SupportEntry.aspx).

### <a name="view-support-requests"></a>Ondersteuningsaanvragen weergeven  

U kunt uw ondersteuningsaanvragen weergeven in de Azure-portal. De beschikbare informatie is echter beperkt.  Ga als volgt te werk om uw incidenten weer te geven: 

1. Meld u aan bij Azure (<https://portal.azure.com>) met uw Intune-beheerdersreferenties en selecteer de **?** in de rechterbovenhoek van de portal en selecteer vervolgens **Help + ondersteuning** om naar de gelijknamige[Azure Help + ondersteuning](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview)pagina te gaan.

2. Op de pagina **Help en ondersteuning** kunt u de lijst met **recente ondersteuningsaanvragen** weergeven.

   > [!IMPORTANT]  
   > Government Compute Cloud-klanten kunnen alleen het ondersteuningscasenummer van 15 cijfers en de incidentstatus weergeven. Alle communicatie over de case en bijgehouden werk of waarschuwingen worden per e-mail verzonden en verwijzen naar het ondersteuningscasenummer van 8 cijfers dat is gemaakt als gespiegelde ondersteuningscase van de aanvraag die in de Intune-console is geopend.   

## <a name="additional-resources"></a>Extra resources  

- [Ondersteuning voor facturerings- en abonnementsbeheer](https://support.office.com/article/Contact-Office-365-for-business-support-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
- [Volumelicenties](https://go.microsoft.com/fwlink/p/?LinkID=282015)
- [Problemen met Intune oplossen](help-desk-operators.md)
