---
title: Persoonlijke gegevens controleren, exporteren of verwijderen
titleSuffix: Microsoft Intune
description: Informatie over het controleren, exporteren of verwijderen van persoonlijke gegevens.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 96990be0-eb1e-43a4-a0e4-09c7dbdc2bf4
ms.reviewer: kerimh
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 74428abf8141c648b5b81bba3177cc89a3cb01d2
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306811"
---
# <a name="audit-export-or-delete-personal-data-in-intune"></a>Persoonlijke gegevens controleren, exporteren of verwijderen in Intune

Intune-beheerders kunnen auditlogboeken gebruiken om activiteiten omtrent persoonlijke gegevens bij te houden. Beheerders kunnen persoonlijke gegevens ook exporteren en verwijderen.

[!INCLUDE [GDPR-related guidance](../includes/gdpr-intro-sentence.md)]

## <a name="audit-personal-data"></a>Persoonlijke gegevens controleren

Auditlogboeken bieden tenantbeheerders een lijst met activiteiten die een wijziging in Microsoft Intune genereren. Auditlogboeken zijn beschikbaar voor veel beheeractiviteiten. Hiermee worden acties doorgaans gemaakt, bijgewerkt (bewerkt), verwijderd en toegewezen. Externe taken die controlegebeurtenissen genereren, kunnen ook worden bekeken. Deze auditlogboeken bevatten mogelijk persoonlijke gegevens van gebruikers wiens apparaten zijn ingeschreven bij Intune.  

Om veiligheidsredenen kunnen auditlogboeken voor acties van gebruikers en apparaten gedurende een periode van één jaar in Intune worden bewaard. Deze logboeken worden na de bewaarperiode van één jaar automatisch verwijderd.

Zie [Auditlogboeken voor Intune-activiteiten](../fundamentals/monitor-audit-logs.md) om auditlogboeken te bekijken. 

Beheerders kunnen auditlogboeken niet verwijderen.

Deze auditgebeurtenissen worden één jaar bewaard. Tenantbeheerders kunnen auditlogboeken aanvragen met [dit formulier voor een ondersteuningsaanvraag](https://privacy.microsoft.com/en-US/privacy-questions?).

## <a name="export-personal-data"></a>Persoonlijke gegevens exporteren

Beheerders kunnen de persoonlijke gegevens van eindgebruikers exporteren, inclusief accounts, servicegegevens en bijbehorende logboeken, om te voldoen aan AVG-aanvragen. Het is aan u en uw organisatie om te bepalen of u de betrokkene een kopie verstrekt van de persoonlijke gegevens of dat u een legitieme reden hebt om dit te weigeren. Als u de aanvraag goedkeurt, kunt u een kopie verstrekken van het feitelijke document, een op de juiste wijze geredigeerde versie of een schermopname van de gedeelten die u geschikt acht om te delen.

Voor het exporteren van de persoonlijke gegevens van een gebruiker kunt u het volgende gebruiken: 
- De blade Intune MDM-apparaat voor het exporteren van een lijst met apparaten. U kunt ook rechtstreeks apparaatgegevens kopiëren.
- het [Export-IntuneData.ps1 script](https://aka.ms/intunedataexport).

## <a name="delete-end-user-personal-data"></a>Persoonlijke gegevens van eindgebruikers verwijderen

Er zijn drie manieren om persoonlijke gegevens te verwijderen uit Intune-beheer:
- De gebruiker verwijderen uit Azure Active Directory
- De fabrieksinstellingen van het apparaat terugzetten
- De gebruiker verwijdert zichzelf

### <a name="delete-a-user-from-intune"></a>Een gebruiker uit Intune verwijderen

Als u de persoonlijke gegevens van een eindgebruiker uit Intune wilt verwijderen, moet een beheerder [de gebruiker verwijderen uit Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user). Wanneer de gebruiker wordt verwijderd uit AAD (permanent verwijderd), ontvangt Intune het verwijdersignaal van AAD. Vervolgens worden alle persoonlijke gegevens van de gebruiker verwijderd uit de Intune-service. De gegevens van de gebruiker worden binnen 30 dagen na de verwijderingsactie verwijderd uit de Intune-service.

### <a name="reset-device-to-factory-settings"></a>De fabrieksinstellingen van het apparaat terugzetten
Wanneer u de fabrieksinstellingen van het apparaat terugzet, worden alle bedrijfsgegevens en persoonlijke gegevens teruggezet naar de oorspronkelijke fabrieksinstellingen. Dit is bijvoorbeeld handig als u het apparaat aan een volgende werknemer wilt geven. Gebruikersbestanden, door de gebruiker geïnstalleerde toepassingen en niet-standaardinstellingen worden verwijderd. Deze gegevens worden binnen 30 dagen na de verwijderingsactie verwijderd uit de Intune-service.

### <a name="user-self-removal-from-intune-management"></a>De gebruiker verwijdert zichzelf uit Intune-beheer
Gebruikers kunnen hun persoonlijke [Android-, Apple- of Windows-](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-android)apparaat uit Intune-beheer verwijderen zonder hulp van de beheerder.   

### <a name="retire"></a>Buiten gebruik stellen
Via de actie **Buiten gebruik stellen** worden door Intune ingerichte gegevens verwijderd, zoals bedrijfstoepassingen, gegevens over apps die door Intune worden beheerd, beleidsinstellingen en e-mailprofielen die via Intune worden ingericht. Bij deze actie blijven de persoonlijke gegevens van de gebruiker op het apparaat behouden.

### <a name="delete-a-tenant-from-microsoft-intune"></a>Een tenant uit Microsoft Intune verwijderen

Als een Intune-tenantklant zijn Intune-account annuleert, worden alle tenantgegevens binnen 180 dagen nadat de klant het Intune-account heeft gesloten, verwijderd. Als de AAD-tenant is gekoppeld aan andere Microsoft Enterprise-abonnementen (Azure, Office 365), worden alleen de Intune-klantgegevens verwijderd. De AAD-tenantresource blijft behouden voor gebruik met de andere abonnementen. Als het Intune-account het enige abonnement is dat is gekoppeld aan de AAD-tenant, worden de tenant en alle resources en klantgegevens verwijderd.

### <a name="delete-a-user-in-a-hybrid-mobile-device-management-mdm-environment"></a>Een gebruiker in een hybride MDM-omgeving (Mobile Device Management) verwijderen
Wanneer u een hybride MDM-omgeving hebt (hierin is Intune geïntegreerd met Configuration Manager), moet u de volgende acties (in deze volgorde) voltooien om een gebruiker volledig te verwijderen uit de lokale Active Directory, Configuration Manager en Intune.

1. Verwijder de gebruiker uit uw lokale Active Directory (AD). Hierdoor wordt de gebruiker niet meer gesynchroniseerd naar Azure AD en ook niet meer gedetecteerd via Configuration Manager-detectie. 
2. Verwijder de gebruiker uit de Configuration Manager-console om de gebruiker en gekoppelde gegevens uit Configuration Manager te verwijderen. Ga in de console naar **Asset en naleving** > **Gebruikers**, klik met de rechtermuisknop op de gebruiker om deze te verwijderen en klik vervolgens op **Verwijderen**.
3. [Gebruiker uit AAD verwijderen](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory#delete-a-user). Hierdoor worden de gebruiker en gekoppelde gegevens zowel uit Azure Active Directory als Intune verwijderd. Wanneer de gebruiker wordt verwijderd uit AAD (permanent verwijderd), ontvangt Intune het verwijdersignaal van AAD. Vervolgens worden alle persoonlijke gegevens van de gebruiker verwijderd uit de Intune-service. De gegevens van de gebruiker worden binnen 30 dagen na de verwijderingsactie verwijderd uit de Intune-service.

> [!Important]
>De onboarding van nieuwe hybride MDM-klanten is afgeschaft. Zie de blogpost [Overstappen van hybride Mobile Device Management naar Intune op Azure](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Move-from-Hybrid-Mobile-Device-Management-to-Intune-on-Azure/ba-p/280150) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

Ontdek hoe u persoonlijke gegevens in Intune kunt [controleren, exporteren of verwijderen](privacy-data-audit-export-delete.md).
