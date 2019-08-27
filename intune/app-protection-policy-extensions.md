---
title: App-beveiligingsbeleid voor extensies
titleSuffix: Microsoft Intune
description: In dit onderwerp wordt het app-beveiligingsbeleid voor extensies beschreven.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f38f22d7aaf03f278fad86061aa8198c8e37f31f
ms.sourcegitcommit: b1ddc7f4a3d520b7d6755c7a423a46d1e2548592
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2019
ms.locfileid: "69655190"
---
# <a name="protecting-application-extensions"></a>Toepassingsextensies beveiligen

In dit artikel wordt het app-beveiligingsbeleid voor extensies in Microsoft Intune beschreven.

## <a name="add-ins-for-outlook-app"></a>Invoegtoepassingen voor Outlook-app

Met Outlook-invoegtoepassingen kunt u populaire apps integreren met de e-mailclient. Invoegtoepassingen voor Outlook zijn beschikbaar op het web en in Windows, Mac, en Outlook voor Android en iOS. De Intune SDK voor app-beveiligingsbeleid en het Intune-app-beveiligingsbeleid omvatten geen ondersteuning voor het beheren van invoegtoepassingen voor Outlook, maar er zijn andere manieren om het gebruik ervan te beperken. Aangezien invoegtoepassingen worden beheerd via Microsoft Exchange, kunnen gebruikers gegevens en berichten delen tussen Outlook en niet-beheerde invoegtoepassingen, tenzij invoegtoepassingen in Exchange zijn uitgeschakeld voor de gebruiker.

Als u wilt dat uw eindgebruikers geen Outlook-invoegtoepassingen meer kunnen benaderen en installeren (dit geldt dan voor alle Outlook-clients), moet u de volgende wijzigingen aanbrengen in rollen in het Exchange-beheercentrum:

- Als u wilt voorkomen dat gebruikers Office Store-invoegtoepassingen installeren, verwijdert u de My Marketplace-rol.
- Als u wilt voorkomen dat gebruikers sideloading uitvoeren voor invoegtoepassingen, verwijdert u de My Custom Apps-rol.
- Als u wilt voorkomen dat gebruikers sowieso een invoegtoepassing kunnen installeren, verwijdert u zowel de My Custom Apps-rol als de My Marketplace-rol.

Deze instructies zijn van toepassing op Office 365, Exchange 2016, Exchange 2013 via Outlook op het web, Windows, Mac en mobiele apparaten.

- Meer informatie over [invoegtoepassingen voor Outlook](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx).
- Meer informatie over [het opgeven van de beheerders en gebruikers die invoegtoepassingen voor de Outlook-app kunnen installeren en beheren](https://technet.microsoft.com/library/jj943754(v=exchg.150).aspx).

## <a name="linkedin-account-connections-for-microsoft-apps"></a>LinkedIn-accountverbindingen voor Microsoft-apps

Met LinkedIn-accountverbindingen kunnen gebruikers in bepaalde Microsoft-apps openbare LinkedIn-profielgegevens zien. Uw gebruikers kunnen er standaard voor kiezen om hun school- of werkaccount van LinkedIn of Microsoft te koppelen om aanvullende LinkedIn-profielgegevens te zien. 

> [!NOTE]
> LinkedIn-integratie is momenteel niet beschikbaar voor klanten van de Amerikaanse overheid en voor organisaties met Exchange Online-postvakken die worden gehost in Australië, Canada, China, Frankrijk, Duitsland, India, Zuid-Korea, het Verenigd Koninkrijk, Japan en Zuid-Afrika.

Het beleid voor Intune SDK en voor Intune-app-beveiliging omvat geen ondersteuning voor het beheren van LinkedIn-accountverbindingen, maar er zijn andere manieren om deze te beheren. U kunt LinkedIn-accountverbindingen voor uw hele organisatie uitschakelen of LinkedIn-accountverbindingen voor bepaalde gebruikersgroepen in uw organisatie inschakelen. Deze instellingen hebben invloed op LinkedIn-verbindingen in Office 365-apps op alle platforms (web, mobiel en desktop). U kunt het volgende doen:

- Schakel LinkedIn-accountverbindingen voor uw tenant in de Azure Portal in of uit. 
- Schakel LinkedIn-accountverbindingen voor de Office 2016-apps van uw organisatie in of uit met behulp van groepsbeleid.

Als LinkedIn-integratie voor uw tenant is ingeschakeld en gebruikers in uw organisatie verbinding maken met hun school- of werkaccounts van LinkedIn of Microsoft, dan hebben ze twee mogelijkheden: 

- Ze kunnen een machtiging geven om gegevens tussen beide accounts te delen. Dit betekent dat ze toestemming geven om via hun LinkedIn-account gegevens te delen met hun school- of werkaccount van Microsoft en dat hun school- of werkaccount van Microsoft gegevens kan delen met hun LinkedIn-account. Gegevens die met LinkedIn worden gedeeld, verlaten de onlineservices. 
- Ze kunnen een machtiging geven om gegevens alleen vanaf hun LinkedIn-account te delen met hun school- of werkaccount van Microsoft

Als een gebruiker toestaat dat gegevens tussen accounts worden gedeeld, zoals met Office-invoegtoepassingen, maakt de LinkedIn-integratie gebruik van bestaande Microsoft Graph API’s. LinkedIn-integratie gebruikt alleen een subset van de API’s die beschikbaar zijn voor Office-invoegtoepassingen en ondersteunt verschillende uitzonderingen.


|Machtigingen voor Microsoft Graph  |Beschrijving  |
|---------|---------|
|Leesmachtigingen voor [Personen](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#people-permissions)     |Hiermee geeft u de app toestemming om een beoordeelde lijst met relevante personen voor de aangemelde gebruiker te lezen. De lijst kan lokale contactpersonen, contactpersonen uit sociale netwerken of de directory van uw organisatie en personen uit recente communicaties (zoals e-mail en Skype) bevatten.         |
|Leesmachtigingen voor [Agenda's](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#calendars-permissions)     |Hiermee geeft u de app toestemming om gebeurtenissen in agenda's van gebruikers te lezen. Bevat de vergaderingen in de agenda's van gebruikers en de tijden, locaties en deelnemers daarvan.         |
|Leesmachtigingen voor [Gebruikersprofiel](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#user-permissions)     |Hiermee geeft u gebruikers toestemming om zich aan te melden bij de app en geeft u de app toestemming om het profiel van de aangemelde gebruikers te lezen. Het geeft de app ook toestemming om basale bedrijfsinformatie te lezen voor aangemelde gebruikers.         |
|Subscriptions     |Dit bereik is niet beschikbaar en nog niet in gebruik. Het bevat abonnementen die door de organisatie van de gebruiker zijn gegeven voor apps en services van Microsoft, zoals Office 365.         |
|Insights     |Dit bereik is niet beschikbaar en nog niet in gebruik. Het bevat de interessegebieden die zijn gekoppeld aan het account van de aangemelde gebruiker op basis van het gebruik van de Microsoft-services.         |

### <a name="learn-more"></a>Meer informatie

- Lees meer over [LinkedIn-informatie en -functies in uw Microsoft-apps](https://go.microsoft.com/fwlink/?linkid=850740).
- Lees meer over de versie met LinkedIn-accountverbindingen op de [pagina met de Office 365-roadmap](https://products.office.com/en-US/business/office-365-roadmap?filters=%26freeformsearch=linkedin#abc). 
- Lees meer over [Het configureren van LinkedIn-accountverbindingen](https://docs.microsoft.com/azure/active-directory/linkedin-integration).
- Voor meer informatie over gegevens die worden gedeeld tussen de LinkedIn-accounts, of de werk- of schoolaccounts van Microsoft van de gebruikers, raadpleegt u [LinkedIn in Microsoft-toepassingen op het werk of op school](https://www.linkedin.com/help/linkedin/answer/84077).

