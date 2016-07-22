---
title: Migreren van AD RMS naar Azure Rights Management - Stap 4 | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 06/29/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: d51e7bdd-2e5c-4304-98cc-cf2e7858557d
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ea4dd88ed749092fd02135d8ca25b621f74fe72f
ms.openlocfilehash: 7ed3569475362272ace055862fe8bb3ee072036a


---

# Migratiestap 4: taken na migratie

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management*


Gebruik de volgende informatie voor stap 4 van de migratie van AD RMS naar Azure Rights Management (Azure RMS). Deze procedures beslaan stap 8 en 9 van [Migreren van AD RMS naar Azure Rights Management](migrate-from-ad-rms-to-azure-rms.md).


## Stap 8. AD RMS uit bedrijf nemen

Optioneel: verwijder het SCP (Service Connection Point) uit Active Directory om te voorkomen dat computers uw lokale Rights Management-infrastructuur detecteren. Dit is optioneel vanwege de omleiding die u in het register hebt geconfigureerd (bijvoorbeeld door het migratiescript migratie uit te voeren). Als u het Service Connection Point wilt verwijderen, doet u dat met het hulpprogramma AD SCP Register van de [Rights Management Services Administration Toolkit](http://www.microsoft.com/download/details.aspx?id=1479).

Controleer uw AD RMS-servers op activiteit, bijvoorbeeld door het controleren van de [aanvragen in het systeemstatusrapport](https://technet.microsoft.com/library/ee221012%28v=ws.10%29.aspx), de [tabel ServiceRequest](http://technet.microsoft.com/library/dd772686%28v=ws.10%29.aspx) of [door de gebruikerstoegang tot beveiligde inhoud te controleren](http://social.technet.microsoft.com/wiki/contents/articles/3440.ad-rms-frequently-asked-questions-faq.aspx). Nadat u hebt bevestigd dat er geen RMS-clients meer communiceren met deze servers en de clients Azure RMS zonder fouten gebruiken, kunt u de AD RMS-serverrol van deze servers verwijderen. Als u specifieke servers gebruikt, kunt u ook eerst de servers gedurende een bepaalde tijd uitschakelen om te controleren of er geen gemelde problemen zijn waarvoor deze servers opnieuw moeten worden gestart om de continuïteit van de service te waarborgen, terwijl u onderzoekt waarom de clients geen gebruik maken van Azure RMS.

Nadat u uw AD RMS-servers buiten gebruik hebt gesteld, is het wellicht een goed idee om uw sjablonen in de klassieke Azure-portal te controleren, te consolideren (zodat gebruikers er minder hebben om uit te kiezen) of te herconfigureren. U kunt zelfs nieuwe sjablonen toevoegen. Dit is ook een aangewezen moment om de standaardsjablonen te publiceren. Zie [Configuring custom templates for Azure Rights Management](../deploy-use/configure-custom-templates.md) (Aangepaste sjablonen configureren voor Azure Rights Management)voor meer informatie.

## Stap 9. Uw Azure RMS-tenantsleutel opnieuw versleutelen
Deze stap is vereist wanneer de migratie is voltooid en voor uw AD RMS-implementatie de RMS cryptografische modus 1 is gebruikt, omdat bij opnieuw versleutelen een nieuwe tenantsleutel wordt gemaakt die de RMS cryptografische modus 2 gebruikt. Het gebruik van Azure RMS met cryptografische modus 1 wordt alleen ondersteund tijdens het migratieproces.

Deze stap is optioneel, maar wordt aanbevolen wanneer de migratie is voltooid, zelfs als u de RMS cryptografische modus 2 hebt gebruikt, omdat de service helpt bij de beveiliging van uw Azure RMS-tenantsleutel tegen potentiële beveiligingsrisico's voor uw AD RMS-sleutel. Wanneer u uw Azure RMS-tenantsleutel opnieuw versleutelt, wordt er een nieuwe sleutel gemaakt en de oorspronkelijke sleutel gearchiveerd. Omdat de overstap van de ene sleutel op de andere niet onmiddellijk plaatsvindt, maar een aantal weken duurt, moet u niet wachten totdat u een inbreuk op de oorspronkelijke sleutel vermoedt, maar versleutelt u uw Azure RMS-tenantsleutel opnieuw zodra de migratie is voltooid.

Ga als volgt te werk om uw Azure RMS-tenantsleutel opnieuw te versleutelen:

-   Als uw Azure RMS-sleutel wordt beheerd door Microsoft: Neem hiervoor [contact op met Microsoft Ondersteuning](../get-started/information-support.md#to-contact-microsoft-support) om een **Azure Rights Management-ondersteuningsaanvraag voor het opnieuw versleutelen van uw Azure RMS-tenantsleutel** te openen. U moet bewijzen dat u een beheerder bent voor uw Azure RMS-tenant. Het bevestigen van dit proces duurt enkele dagen. Er gelden standaardkosten voor de ondersteuning. Het opnieuw versleutelen van uw tenantsleutel is geen gratis ondersteuningsservice.

-   Als uw Azure RMS-tenantsleutel wordt beheerd door uzelf (BYOK): herhaal de BYOK-procedure om een nieuwe sleutel te genereren en te maken (via internet of persoonlijk).

Zie [Bewerkingen voor uw Azure Rights Management-tenantsleutel](../deploy-use/operations-tenant-key.md) voor meer informatie over het beheren van uw Azure RMS-tenantsleutel.

## Volgende stappen

Nu u de migratie hebt voltooid, controleert u het [implementatieschema](deployment-roadmap.md) om te bekijken of er nog andere implementatietaken zijn die u moet uitvoeren.




<!--HONumber=Jul16_HO3-->


