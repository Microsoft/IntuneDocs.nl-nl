---
# required metadata

title: Migreren van AD RMS naar Azure Rights Management - Stap 4 | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: d51e7bdd-2e5c-4304-98cc-cf2e7858557d


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Migratiestap 4: taken na migratie

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management*


Gebruik de volgende informatie voor stap 4 van de migratie van AD RMS naar Azure Rights Management (Azure RMS). Deze procedures beslaan stap 8 en 9 van [Migreren van AD RMS naar Azure Rights Management](migrate-from-ad-rms-to-azure-rms.md).


## Stap 8. AD RMS uit bedrijf nemen

Optioneel: verwijder het SCP (Service Connection Point) uit Active Directory om te voorkomen dat computers uw lokale Rights Management-infrastructuur detecteren. Dit is optioneel vanwege de omleiding die u in het register hebt geconfigureerd (bijvoorbeeld door het migratiescript uit te voeren). Als u het serviceaansluitpunt wilt verwijderen, doet u dat met het hulpprogramma AD SCP Register van de [Rights Management Services Administration Toolkit](http://www.microsoft.com/download/details.aspx?id=1479).

Monitor uw AD RMS-servers op activiteit, bijvoorbeeld door de [aanvragen in het systeemstatusrapport](https://technet.microsoft.com/library/ee221012%28v=ws.10%29.aspx) te controleren, de [tabel ServiceRequest](http://technet.microsoft.com/library/dd772686%28v=ws.10%29.aspx) te bekijken of [de gebruikerstoegang tot beveiligde inhoud te controleren](http://social.technet.microsoft.com/wiki/contents/articles/3440.ad-rms-frequently-asked-questions-faq.aspx). Nadat u hebt bevestigd dat er geen RMS-clients meer communiceren met deze servers en de clients Azure RMS zonder fouten gebruiken, kunt u de AD RMS-serverrol van deze servers verwijderen. Als u specifieke servers gebruikt, kunt u ook eerst de servers gedurende een bepaalde tijd uitschakelen om te controleren of er geen gemelde problemen zijn waarvoor deze servers opnieuw moeten worden gestart om de continuïteit van de service te waarborgen, terwijl u onderzoekt waarom de clients geen gebruik maken van Azure RMS.

Nadat u uw AD RMS-servers buiten gebruik hebt gesteld, is het wellicht een goed idee om uw sjablonen in de klassieke Azure-portal te controleren, te consolideren (zodat gebruikers er minder hebben om uit te kiezen) of te herconfigureren. U kunt zelfs nieuwe sjablonen toevoegen. Dit is ook een aangewezen moment om de standaardsjablonen te publiceren. Zie [Aangepaste sjablonen configureren voor Azure Rights Management](../deploy-use/configure-custom-templates.md) voor meer informatie.

## Stap 9. Uw Azure RMS-tenantsleutel opnieuw versleutelen
Deze stap is vereist wanneer de migratie is voltooid en voor uw AD RMS-implementatie de RMS cryptografische modus 1 is gebruikt, omdat bij opnieuw versleutelen een nieuwe tenantsleutel wordt gemaakt die de RMS cryptografische modus 2 gebruikt. Het gebruik van Azure RMS met cryptografische modus 1 wordt alleen ondersteund tijdens het migratieproces.

Deze stap is optioneel, maar wordt aanbevolen wanneer de migratie is voltooid, zelfs als u de RMS cryptografische modus 2 hebt gebruikt, omdat de service helpt bij de beveiliging van uw Azure RMS-tenantsleutel tegen potentiële beveiligingsrisico's voor uw AD RMS-sleutel. Wanneer u uw Azure RMS-tenantsleutel opnieuw versleutelt, wordt er een nieuwe sleutel gemaakt en de oorspronkelijke sleutel gearchiveerd. Omdat de overstap van de ene sleutel op de andere niet onmiddellijk plaatsvindt, maar in de loop van een paar weken, moet u niet wachten totdat u een inbreuk op de oorspronkelijke sleutel vermoedt, maar versleutelt u uw RMS-tenantsleutel opnieuw zodra de migratie is voltooid.

Ga als volgt te werk om uw Azure RMS-tenantsleutel opnieuw te versleutelen:

-   Als uw RMS-tenantsleutel wordt beheerd door Microsoft: bel de Microsoft-klantondersteuning (CSS) en bewijs dat u de RMS-tenantbeheerder bent.

-   Als uw RMS-tenantsleutel wordt beheerd door uzelf (BYOK): herhaal de BYOK-procedure om een nieuwe sleutel te genereren en te maken (via internet of persoonlijk).

Zie [Bewerkingen voor uw Azure Rights Management-tenantsleutel](../deploy-use/operations-tenant-key.md) voor meer informatie over het beheren van uw RMS-tenantsleutel.

## Volgende stappen

Nu u de migratie hebt voltooid, controleert u het [implementatieschema](deployment-roadmap.md) om te bekijken of er nog andere implementatietaken zijn die u moet uitvoeren.



<!--HONumber=Apr16_HO4-->


