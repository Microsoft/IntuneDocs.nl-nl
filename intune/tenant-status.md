---
title: Tenantstatuspagina in Microsoft Intune
titleSuffix: Microsoft Intune
description: Gebruik de tenantstatuspagina van Intune om belangrijke tenantgegevens te bekijken zonder daarvoor de Intune-portal te hoeven verlaten
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c744878c49dfa5adb1b4f64587abfe06151a69a0
ms.sourcegitcommit: 99b74d7849fbfc8f5cf99cba33e858eeb9f537aa
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/31/2019
ms.locfileid: "68670992"
---
# <a name="use-the-intune-tenant-status-page"></a>De tenantstatuspagina in Intune gebruiken
De pagina Tenantstatus is een gecentraliseerde hub met de huidige en belangrijke details over uw tenant. Dit zijn onder andere details over de beschikbaarheid en het gebruik van licenties, de status van de connector en belangrijke communicatie over de Intune-service.  

Als u het dashboard wilt bekijken, gaat u in Azure Portal naar **Intune > Tenantstatus**.  De tenantstatus wordt weergegeven in de **groep Help en ondersteuning**.  

De pagina is onderverdeeld in vier gedeelten:

## <a name="tenant-details"></a>Tenantgegevens
Tenantgegevens biedt overzichtelijke informatie over uw tenant. U ziet hier informatie zoals de naam van de tenant, de locatie ervan, uw MDM-instantie en het versienummer van de tenant. Het versienummer van de service is een koppeling waarmee u het artikel *Nieuwe functies in Intune* opent in de Microsoft-documentatie. In *Nieuwe functies* leest u meer over de nieuwste functies en updates voor de Intune-service.  

Dit gedeelte biedt ook basisinformatie over welke licenties beschikbaar zijn en hoeveel er zijn toegewezen aan gebruikers. De licenties voor apparaten worden niet weergegeven.

## <a name="connector-status"></a>Connectorstatus
In Connectorstatus kunt u de status van alle connectors bekijken die beschikbaar zijn voor Intune.  

Connectors zijn:
- **Door u geconfigureerde verbindingen met externe services**. Dit kan bijvoorbeeld de *Apple Volume Purchase Program*-service of de *Windows Autopilot*-service zijn.  De status van dit type connector wordt gebaseerd op het tijdstip van de laatste geslaagde synchronisatie.
- **Certificaten of referenties die nodig zijn voor het verbinden met een externe, niet-beheerde service**, zoals *Apple Push Notification Services*-certificaten (APNS). De status van dit type connector wordt gebaseerd op de verlooptijdstempel van het certificaat of de referentie.  

Standaard worden maximaal vijf connectoren weergegeven. U kunt **Alle connectors weergeven** selecteren om deze lijst uit te breiden zodat u alle beschikbare connectors ziet, inclusief de connectors die u nog niet voor gebruik hebt geconfigureerd.  

Connectors die niet in orde zijn, worden altijd bovenaan de lijst weergegeven. Daarna komen de connectors met waarschuwingen en daarna de connectors die in orde zijn. De connectors die nog niet zijn geconfigureerd, worden als laatste weergegeven.

Als er meer dan één connector van een bepaald type is, is de status een overzicht van alle connectors van hetzelfde type. De slechtste status van alle connectors in een groep wordt gebruikt als de status van de gehele groep.  

**Connectorstatus:**
- **Niet in orde:**
  - Het certificaat of de referentie is verlopen
  - De laatste synchronisatie is drie of meer dagen geleden
- **Waarschuwing:**
  - Het certificaat of de referentie verloopt binnen zeven dagen
  - De laatste synchronisatie is meer dan een dag geleden
- **In orde:**
  - Het certificaat of de referentie verloopt niet binnen zeven dagen
  - De laatste synchronisatie is minder dan een dag geleden  

Als u een connector uit de lijst selecteert, wordt in de portal de pagina weergegeven die relevant is voor het maken of configureren van die connector.  Als u bijvoorbeeld de connector **VVP Expiry Date** selecteert, wordt de pagina **iOS Volume-Purchased Program Tokens** geopend. Hier kunt u meer informatie over de connector bekijken. U kunt vervolgens een nieuwe configuratie maken, een bewerking doorvoeren of problemen met een bestaande configuratie oplossen.  

## <a name="intune-service-health"></a>Servicestatus van Intune  
U kunt gegevens over actieve incidenten en advies bekijken zonder dat u naar het Microsoft 365 Service Health-dashboard of het berichtencentrum hoeft te gaan. Beide zijn in het [Microsoft 365-beheercentrum](https://admin.microsoft.com) te vinden. Alleen incidenten waarbij er invloed is op uw tenant worden weergegeven.  

Wanneer u een incident selecteert, worden de incidentgegevens rechtstreeks op de tenantstatuspagina weergegeven. Als u advies en incidenten uit het verleden wilt bekijken, selecteert u **Incidenten/advies uit het verleden bekijken**. Het Microsoft 365-beheercentrum wordt geopend. U kunt dan voor uw tenant advies en incidenten uit de afgelopen 30 dagen bekijken.  

Als u informatie over *Intune Service Health* wilt bekijken, moet uw account beschikken over de rol **Globale beheerder** of **Servicebeheerder** in Azure Active Directory of het Microsoft 365-beheercentrum. Als u deze machtigingen wilt toewijzen, meldt u zich aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met globale-beheerdersmachtigingen. Selecteer **Gebruikers > Actieve gebruikers** en selecteer vervolgens het account waarvoor toegang is vereist. Selecteer **Bewerken** voor rollen, selecteer *Servicebeheerder* of *Globale beheerder* en selecteer vervolgens **Opslaan** voor uw bewerking om de machtigingen toe te wijzen.  

U kunt uw communicatievoorkeuren voor Intune Service Health alleen instellen via het Microsoft 365-beheercentrum.

## <a name="intune-news"></a>Intune-nieuws  
U kunt informatieve communicatie van het Intune-serviceteam bekijken zonder naar het Office-berichtencentrum te gaan. De communicatie omvat berichten over wijzigingen die recent zijn aangebracht aan de Intune-service en wijzigingen die binnenkort worden doorgevoerd voor uw tenant.  

Standaard worden de tien meest recente actieve berichten weergegeven. Als u oudere berichten wilt weergeven, klikt u op **Oudere berichten weergeven** om het *berichtencentrum* te openen in het Microsoft 365-beheercentrum.  

Als u informatie over Intune-nieuws wilt bekijken, moet uw account beschikken over de rol **Globale beheerder** of **Servicebeheerder** in Azure Active Directory, of de rol **Berichtencentrum-lezer** in het Microsoft 365-beheercentrum.  Als u deze machtiging wilt toewijzen, meldt u zich aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com) met beheerdersmachtigingen. Selecteer **Gebruikers > Actieve gebruikers** en selecteer vervolgens het account waarvoor toegang is vereist. Selecteer **Bewerken** voor *Rollen*, selecteer *Teams-communicatiebeheerder* en **sla vervolgens uw bewerking op** om de machtigingen toe te wijzen.  

U kunt uw communicatievoorkeuren voor Intune-nieuws alleen instellen via het Microsoft 365-beheercentrum.
