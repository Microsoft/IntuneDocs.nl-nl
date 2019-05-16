---
title: Ondersteuning voor Microsoft Intune krijgen
titleSuffix: Microsoft Intune
description: Online- en telefonische ondersteuning verkrijgen voor betaalde Microsoft Intune-abonnementen en proefabonnementen.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/05/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7fc95d17-098e-4da5-8a09-a96476569dd9
ms.reviewer: cacamp
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: cf1e87d40459d194f2c4aa0ff702a137e45504ab
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59569750"
---
# <a name="how-to-get-support-for-microsoft-intune"></a>Ondersteuning voor Microsoft Intune krijgen

[!INCLUDE [azure_portal](./includes/note-for-both-portals.md)]

Microsoft biedt wereldwijde technische, voorverkoop-, facturerings- en abonnementsondersteuning voor Microsoft Intune. Ondersteuning is online en telefonisch beschikbaar voor betaalde abonnementen en proefabonnementen. Online technische ondersteuning is beschikbaar in het Engels en Japans. Telefonische ondersteuning en online-ondersteuning bij factureren zijn in meer talen beschikbaar.

Als Intune-beheerder kunt u de optie **Help en ondersteuning** gebruiken om vanuit de Azure-portal een onlineondersteuningsticket voor Intune in te dienen. Als u een ondersteuningsincident wilt maken en beheren, moet aan uw account een Azure AD-rol (Azure Active Directory) zijn toegewezen die de *actie* **microsoft.office365.supportTickets/allEntities/allTasks** omvat. Zie [beheerdersrollen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) voor informatie over rollen en machtigingen in Azure AD die zijn vereist voor het maken van een ondersteuningsticket. 

**Bekende problemen bij het maken van ondersteuningsincidenten**

Als uw account wel beschikt over de vereiste machtigingen, maar geen toegang kan krijgen tot Help en ondersteuning, of er geen ondersteuningsincident kan worden gemaakt of beheerd, bekijkt u de volgende bekende problemen en oplossingen:  
- Verouderd gebruikerstoken voor uw account. Om dit probleem op te lossen meldt u zich af bij alle actieve consolesessies, meld u zich opnieuw aan, en probeert u vervolgens een ondersteuningsincident te maken of beheren. 
- Meerdere actieve sessies. Als u als meerdere gebruikers of bij meerdere sessies bent aangemeld, meldt u alle extra consoles af totdat u er één overhoudt. Vervolgens probeert u met één actieve sessie een ondersteuningsincident te maken of beheren.

Er kunnen aanvullende acties nodig zijn om toegangsproblemen op te lossen:
- Wis alle cookies voor uw actieve browsersessie, en probeer vervolgens opnieuw om een ondersteuningsincident te maken of beheren.
- Gebruik een InPrivate-browsingsessie om u aan te melden bij Intune, en probeer een ondersteuningsincident te maken of beheren.  

Ga naar het [Microsoft 365-beheercentrum](https://admin.microsoft.com) en maak van hieruit een ondersteuningsticket als de voorgaande tijdelijke oplossingen niet hebben geholpen. We werken momenteel aan een oplossing. Deze zal eind van de zomer beschikbaar zijn. 



>[!IMPORTANT]  
> Neem voor technische ondersteuning voor externe producten die met Intune werken (zoals SaaSwedo, Cisco of Lookout), contact op met de leverancier van dat product. Open pas een ondersteuningsaanvraag voor Intune als u zeker weet dat het andere product juist is geconfigureerd.
>
> Raadpleeg de sectie [Probleemoplossing](help-desk-operators.md) in de Intune-documentatie voor informatie over het oplossen van problemen met betrekking tot Microsoft Intune.




## <a name="help-and-support-experience"></a>Help en ondersteuning-ervaring
> [!TIP]   
> Een nieuwe Help- en ondersteuningservaring is beschikbaar voor alle tenants. Als u deze nieuwe ervaring niet in uw tenant ziet, wis dan de cache van uw browser en laad de pagina opnieuw.

De Help en ondersteuning-ervaring voor Intune is beschikbaar via de [Microsoft 365 Device Management-portal](http://devicemanagement.microsoft.com) en via alle blades (of pagina's) onder Intune in Azure Portal. 

![Intune-blades](./media/get-support/intune-blades.png)


Deze nieuwe ervaring is vergelijkbaar met de ervaring in het [Microsoft 365-beheercentrum](https://admin.microsoft.com/) en vervangt de vorige Help en ondersteuning-ervaring. 

Gebruik de volgende opties voor toegang tot Help en ondersteuning:  
- **Dashboard Apparaatbeheer:**
   - Een beschikbare optie voor **Help en ondersteuning** selecteren
   - Het pictogram **?** in de rechterbovenhoek van Azure Portal selecteren

- **In Azure Portal**:
   - **Help en ondersteuning** op een Intune-blade of -pagina selecteren

   U kunt vanaf elke locatie in Azure Portal het pictogram **?** in de rechterbovenhoek of **Help en ondersteuning** in het navigatiedeelvenster aan de linkerkant selecteren om de *Help en ondersteuning* voor Azure te openen. Gebruik voor de beste ervaring *Help en ondersteuning* op de Intune-blade.  

Met de nieuwe ervaring hebt u toegang tot de weergave **Hebt u hulp nodig?**, zoals u kunt zien in de volgende afbeelding van het dashboard Apparaatbeheer:  
![Het Apparaatbeheerdashboard en de pagina Hebt u hulp nodig?](./media/get-support/help-support-dashboard.png)

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

- Geef uw e-mailadres op voor een e-mailaanvraag. Indien gewenst kunt u bijlagen toevoegen aan uw inzending. Selecteer **Verzenden** om de aanvraag te openen.  

  ![E-mailaanvraag](./media/get-support/email-support.png)
  
- Geef uw telefoonnummer op voor een aanvraag voor telefonische ondersteuning. Indien gewenst kunt u tevens uw e-mailadres invoeren en bijlagen toevoegen aan uw inzending. Selecteer Bel mij om de aanvraag te verzenden.  

   ![Telefonische aanvraag](./media/get-support/phone-support.png)

### <a name="view-support-cases"></a>Ondersteuningscases weergeven
Selecteer de knop Geschiedenis om de ondersteuningsincidenten weer te geven die u hebt gemaakt.  

![Ondersteuningscases weergeven](./media/get-support/view-support-tickets.png)

- Alleen de ondersteuningscases die u met de nieuwe werkstroom opent, zijn binnen deze werkstroom zichtbaar. Als u deze wilt weergeven, gebruikt u een Help en ondersteuning-weergave in de console voor apparaatbeheer of op de Intune-blade in Azure Portal. Deze cases hebben een nummer van acht cijfers. U kunt deze cases ook weergeven vanuit het Microsoft 365-beheercentrum.  

- Cases die u hebt geopend zonder gebruik van de Help en ondersteuning-ervaring van Intune, blijven ongewijzigd. Als u deze wilt weergeven, moet u een Help en ondersteuning-weergave gebruiken die geen deel uitmaakt van de Intune-ervaring of het dashboard Apparaatbeheer. Deze cases hebben een nummer dat begint met **117** of **118** en 15 cijfers lang is. Als u deze wilt weergeven:

    1. Meld u aan bij Azure (<https://portal.azure.com>) met uw Intune-beheerdersreferenties en selecteer de *?* in de rechterbovenhoek van de portal en selecteer vervolgens *Help + ondersteuning* om naar de gelijknamige[Azure Help + ondersteuning](https://ms.portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview)pagina te gaan.

    2. Op de pagina **Help + ondersteuning** kunt u de lijst met **Recente ondersteuningsaanvragen** weergeven en deze selecteren om meer details te zien.


## <a name="azure-help--support-experience"></a>Azure Help en ondersteuning-ervaring
De volgende informatie beschrijft de Azure Help en ondersteuning-ervaring die toegankelijk blijft via Azure Portal wanneer u het linkernavigatievenster **Help en ondersteuning** of de optie **?** in de rechterbovenhoek van Azure Portal gebruikt. Vanaf januari 2019 is de Azure *Help en ondersteuning*-ervaring niet meer toegankelijk via *Help en ondersteuning* op de Intune-blades.  

### <a name="create-an-online-support-ticket"></a>Een onlineondersteuningsticket maken

1. Meld u aan bij Azure Portal (<https://portal.azure.com>) met de referenties van een Intune-beheerder. Kies de **?** in de rechterbovenhoek van de portal en selecteer vervolgens **Help + ondersteuning** om naar de gelijknamige[Azure Help + ondersteuning](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview)pagina te gaan.

   ![Afbeelding van de vraagtekenkoppeling, waarbij de koppeling Help en ondersteuning is gemarkeerd](./media/azure-get-support.png)

2. Selecteer **Nieuwe ondersteuningsaanvraag** op de pagina **Help en ondersteuning** van Azure.

   ![Afbeelding van de pagina Help en ondersteuning met de koppeling Nieuwe ondersteuningsaanvraag gemarkeerd](media/azure-support-ticket-link.png)

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

<!--
  - **Support plan**: **Technical support - included** (for Intune technical issues, support is complimentary) or **Premier**
     >[!IMPORTANT]
     >- If you are a **Premier customer** and don't see **Support plan: Premier**, contact your Technical Account Manager for help linking your contract and tenant.
     >- Support for Intune, and for Intune when used with Configuration Manager, is free of charge. To review details of the Premier Support offering, see the [Description of Services](https://enterprise.microsoft.com/en-us/services/services-list/) documentation, section 5.3.3 "Advisory Services."

4. On the **Problem** blade, to make sure your request is addressed by the right subject matter expert for your problem, select the following options:

   - **Severity**
   - **Problem type**
   - **Category**

     These details also let us provide **Related help** that might solve your problem without filing a ticket.

     ![Screenshot of Azure portal help and support page with Problem items filled out and displaying solutions based on your problem](./media/support-need-solutions.png)

     To help the support team research and resolve your problem, enter the following information:
    
   - **Details**
   - **Date**
   - **Time**
   - **Supplemental data**

   Choose **Next**.

5. Provide **Contact information** for this support request. Microsoft support uses this information to contact you.
6. Choose **Create** to submit your support request.
-->
>[!IMPORTANT]
>Als u een vraag over facturering of abonnementen hebt, kunt u een aanvraag voor ondersteuning openen in het [Microsoft 365-beheercentrum](https://admin.microsoft.com/Support/SupportEntry.aspx).

### <a name="view-support-requests"></a>Ondersteuningsaanvragen weergeven
U kunt een ondersteuningsaanvraag weergeven in Azure Portal. Hiervoor doet u het volgende:

1. Meld u aan bij Azure (<https://portal.azure.com>) met uw Intune-beheerdersreferenties en selecteer de **?** in de rechterbovenhoek van de portal en selecteer vervolgens **Help + ondersteuning** om naar de gelijknamige[Azure Help + ondersteuning](https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/overview)pagina te gaan.

2. Op de pagina **Help + ondersteuning** kunt u de lijst met **Recente ondersteuningsaanvragen** weergeven en deze selecteren om meer details te zien.

## <a name="additional-resources"></a>Extra resources
- [Ondersteuning voor facturerings- en abonnementsbeheer](https://support.office.com/article/Contact-Office-365-for-business-support-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
- [Volumelicenties](https://go.microsoft.com/fwlink/p/?LinkID=282015)
- [Problemen met Intune oplossen](help-desk-operators.md)
