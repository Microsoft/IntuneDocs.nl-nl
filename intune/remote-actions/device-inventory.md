---
title: Apparaatdetails weergeven met Microsoft Intune - Azure | Microsoft Docs
description: Bekijk uw apparaatdetails, waaronder informatie over het besturingssysteem, de opslagruimte, de fabrikant en het model. Bekijk een lijst met geïnstalleerde apps, controleer de beleidsregels voor naleving en stel TeamViewer in met Microsoft Intune in Azure. Vergelijkbaar met het bekijken van de inventaris van de apparaten die u beheert.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: af4270587ab5894d52a7d12b1c2082b7b3298e51
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77413748"
---
# <a name="see-device-details-in-intune"></a>Apparaatdetails bekijken in Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

De functie **Apparaten** biedt meer informatie over de apparaten die u beheert, zoals over de hardware en welke apps zijn geïnstalleerd.

In dit artikel leest u hoe u al uw apparaten en hun eigenschappen kunt bekijken in Azure Portal.

## <a name="view-the-device-details"></a>Apparaatdetails weergeven

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Selecteer **Apparaten** > **Alle apparaten** en selecteer een van de apparaten in de lijst om de details ervan te openen:

   - **Overzicht** toont de apparaatnaam en een lijst met enkele belangrijke eigenschappen van het apparaat, inclusief of het een BYOD-apparaat (Bring Your Own Device) is, wanneer het apparaat is ingecheckt, en meer. U kunt de volgende acties uitvoeren op het apparaat:
      - [Buiten gebruik stellen](devices-wipe.md#retire)
      - [Wissen](devices-wipe.md#wipe)
      - [Vergrendelen op afstand](device-remote-lock.md)
      - [Apparaat synchroniseren](device-sync.md)
      - [Wachtwoordcode opnieuw instellen](device-passcode-reset.md)
      - [Opnieuw starten](device-restart.md) (alleen Windows)
      - [Nieuwe start](device-fresh-start.md) (alleen Windows)
      - Een externe hulpsessie starten
   - Gebruik **Eigenschappen** om een [apparaatcategorie die u maakt](../enrollment/device-group-mapping.md) toe te wijzen en wijzig de eigendom van het apparaat naar een persoonlijk apparaat of een bedrijfsapparaat.
   - **Hardware** bevat veel details over het apparaat, zoals de apparaat-id, het besturingssysteem en de versie, opslagruimte en meer informatie.
   - Bij **Gedetecteerde toepassingen** staan alle apps vermeld die volgens Intune op het apparaat zijn geïnstalleerd, en de appversies. Zie [Door Intune gedetecteerde apps](../apps/app-discovered-apps.md) voor meer informatie.
   - Bij **Apparaatnaleving** staan alle toegewezen nalevingsbeleidsregels en wordt vermeld of het apparaat compatibel of niet compatibel is.
   - Bij **Apparaatconfiguratie** ziet u het configuratiebeleid van alle apparaten die aan het apparaat zijn toegewezen en wordt vermeld of het beleid is geslaagd of mislukt.

## <a name="hardware-device-details"></a>Hardwareapparaatdetails
Afhankelijk van de provider die door de apparaten wordt gebruikt, worden mogelijk niet alle gegevens vermeld

> [!Note]  
> Hardware- en software-inventaris wordt om de 7 dagen vernieuwd in de Intune-service.

|Detail|Beschrijving|Platform| 
|--------------|----------------------|----|  
|Naam|De naam van het apparaat.|Windows, iOS|
|Naam van de beheerder|De apparaatnaam wordt alleen in de console gebruikt. Als u deze naam wijzigt, verandert de naam op het apparaat niet.|Windows, iOS|
|udid|De unieke apparaat-id van het apparaat.|Windows, iOS|
|Intune-apparaat-id|Een GUID waarmee het apparaat op unieke wijze wordt aangeduid.|Windows, iOS|
|Serienummer|Het serienummer van het apparaat, opgegeven door de fabrikant.|Windows, iOS|
|Gedeeld apparaat|Als de waarde hier **Ja** is, wordt het apparaat door meerdere gebruikers gedeeld.|Windows, iOS|
|Door de gebruiker goedgekeurde inschrijving|Als de waarde hier **Ja** is, is er door de gebruiker goedgekeurde inschrijving beschikbaar. Dit betekent dat beheerders bepaalde beveiligingsinstellingen op het apparaat kunnen beheren.|Windows, iOS|
|Besturingssysteem|Het besturingssysteem op het apparaat.|Windows, iOS|
|Versie van besturingssysteem|De versie van het besturingssysteem van het apparaat.|Windows, iOS|
|Taal van besturingssysteem|De taal die is ingesteld voor het besturingssysteem op het apparaat.|Windows, iOS|
|Buildnummer|Het buildnummer van het besturingssysteem.|Android|
|Beveiligingspatchniveau|Het niveau van de beveiligingspatch voor het apparaat.|Android|
|Totale opslagruimte|De totale opslagruimte op het apparaat (in gigabytes).|Windows, iOS|
|Beschikbare opslagruimte|De niet-gebruikte opslagruimte op het apparaat (in gigabytes).|Windows, iOS|
|IMEI|Het IMEI-nummer (International Mobile Equipment Identity) van het apparaat.|Windows, iOS/iPadOS, Android|
|MEID|Het MEID-nummer (Mobile Equipment Identifier) van het apparaat.|Windows, iOS/iPadOS, Android|
|Fabrikant|De fabrikant van het apparaat.|Windows, iOS/iPadOS, Android|
|Model|Het model van het apparaat.|Windows, iOS/iPadOS, Android|
|Telefoonnummer|Het telefoonnummer dat is toegewezen aan het apparaat.|Windows, iOS/iPadOS, Android*|
|Provider van abonnee|De mobiele provider die op het apparaat wordt gebruikt.|Windows, iOS/iPadOS, Android|
|Mobiele-telefoontechnologie|Het radiosysteem dat wordt gebruikt door het apparaat.|Windows, iOS/iPadOS, Android|
|MAC-adres Wi-Fi|Het Media Access Control-adres van het apparaat.|Windows, iOS/iPadOS, Android|
|ICCID|De Integrated Circuit Card Identifier, het unieke identificatienummer van een SIM-kaart.|Windows, iOS/iPadOS, Android|
|Inschrijvingsdatum|De datum en tijd waarop het apparaat is ingeschreven bij Intune.|Windows, iOS/iPadOS, Android|
|Laatste contact|De datum en tijd waarop het apparaat het laatst verbinding heeft gemaakt met Intune.|Windows, iOS/iPadOS, Android|
|Code voor het overslaan van het activeringsslot|De code die kan worden gebruikt om het activeringsslot uit te schakelen.|iOS|
|Azure AD-geregistreerd|Als de waarde **Ja** is, is het apparaat geregistreerd bij Azure Active Directory.|Windows, iOS/iPadOS, Android|
|Intune geregistreerd|Als de waarde **Ja** is, is het apparaat geregistreerd bij Intune|Windows, iOS/iPadOS, Android|
|Naleving|De nalevingsstatus van het apparaat.|Windows, iOS/iPadOS, Android|
|EAS geactiveerd|Als de waarde **Ja** is, wordt het apparaat gesynchroniseerd met een Exchange-postvak.|Windows, iOS/iPadOS, Android|
|Activerings-id voor EAS|De Exchange ActiveSync-id van het apparaat.|Windows, iOS/iPadOS, Android|
|Onder supervisie|Als de waarde **Ja** is, hebben de beheerders uitgebreide controle over het apparaat.|Windows, iOS/iPadOS, Android|
|Versleuteld|Als de waarde **Ja** is, worden de gegevens die zijn opgeslagen op het apparaat versleuteld.|Windows, iOS/iPadOS, Android|

> [!Note]  
> Op toegewezen of volledig beheerde Android-apparaten wordt het telefoonnummer niet geïnventariseerd.

## <a name="next-steps"></a>Volgende stappen
Bekijk wat u nog meer kunt doen om met Intune uw [apparaten te beheren](device-management.md).
