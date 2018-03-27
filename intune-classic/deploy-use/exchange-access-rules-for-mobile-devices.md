---
title: Exchange-toegangsregels voor mobiele apparaten
description: Exchange ActiveSync-toegangsregels voor het toestaan of blokkeren van apparaatverbindingen met EAS
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/19/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 208b9f45-02d9-413a-b86a-8bad9b5008fa
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9c3da7d517bd26bf694ea7bfa658ec1a4688d8f8
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="exchange-access-rules-for-mobile-devices"></a>Exchange-toegangsregels voor mobiele apparaten

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Exchange-toegangsregels voor mobiele apparaten bepalen het niveau van toegang dat de betreffende apparaten hebben tot Exchange ActiveSync. Deze instellingen beïnvloeden alle mobiele apparaten, met inbegrip van apparaten die niet zijn ingeschreven in Microsoft Intune. U kunt beginnen met het definiëren van een **Standaardregel** die wordt toegepast op mobiele apparaten waarop geen aangepaste regel van toepassing is.

De volgende tabel bevat de toegangsniveaus die worden beheerd door Exchange ActiveSync:

|Toegangsniveau|Description|
|----------------|---------------|
|**Apparaten toegang bieden tot Exchange**|In het geval van *toegestane toegang* kan een mobiel apparaat synchroniseren via Exchange ActiveSync en verbinding maken met de Exchange-server voor het ophalen van e-mail en het beheren van de agenda, contactpersonen, taken en notities. Dit geldt zolang het apparaat voldoet aan het Exchange ActiveSync-beleid voor postvakken dat u in Exchange hebt geconfigureerd, tenzij de gebruiker of het specifieke mobiele apparaat is geblokkeerd door de Exchange-beheerder.|
|**Toegang tot Exchange voor apparaten blokkeren**|In het geval van *geblokkeerde toegang* zijn mobiele apparaten geblokkeerd en kunnen ze geen verbinding maken met de Exchange-server. Apparaten ontvangen de HTTP-fout 403 - Verboden. De gebruiker ontvangt een e-mailbericht van de Exchange-server om aan te geven dat het mobiele apparaat geen toegang krijgt tot het postvak van de gebruiker. Dit bericht kan niet op het geblokkeerde mobiele apparaat worden weergegeven. Met behulp van de taak **Gebruikersmelding instellen** kunt u aangepaste tekst aan dit bericht toevoegen met instructies voor gebruikers van wie de apparaten zijn geblokkeerd. |
|**Plaats de apparaten in quarantaine zodat u ze later kunt toestaan of blokkeren**|Wanneer een mobiel apparaat in quarantaine is geplaatst, kan het mobiele apparaat verbinding maken met de Exchange-server. Het krijgt echter slechts beperkte toegang tot gegevens. De gebruikers kunnen inhoud toevoegen aan hun eigen mappen Agenda, Contactpersonen, Taken en Notities, maar de server staat niet toe dat het apparaat inhoud ophaalt uit het postvak van de gebruiker. De gebruiker ontvangt één e-mailbericht dat aangeeft dat het mobiele apparaat in quarantaine is geplaatst. Dit bericht wordt verzonden naar het apparaat en het postvak van de gebruiker. Met behulp van de taak **Gebruikersmelding instellen** kunt u aangepaste tekst aan dit bericht toevoegen met instructies voor gebruikers van wie de apparaten in quarantaine zijn geplaatst.|

Een toegangsstrategie is een combinatie van een **standaardregel** en **platformuitzonderingen** die van toepassing is op alle mobiele apparaten die verbonden zijn met Exchange. In de volgende tabel wordt een aantal voorbeelden van toegangsstrategieën vermeld.

|Toegangsstrategie|Description|
|-------------------|---------------|
|Acceptatielijst|U kunt een *acceptatielijst* gebruiken om een lijst met bekende apparaten toegang te verlenen en om toegang te beperken voor alle andere apparaten. Hiertoe moet u aangepaste regels maken voor apparaatplatformen, zodat ze toegang hebben tot het postvak van gebruikers. Wanneer u een dergelijke regel maakt, moet u de standaardtoegangsregel instellen voor het blokkeren of in quarantaine plaatsen van alle andere apparaten. Als u een nieuw apparaat aan de acceptatielijst wilt toevoegen, maakt u een nieuwe aangepaste regel.|
|Blokkeringslijst|U kunt een *blokkeringslijst* gebruiken om alle apparaten standaard toegang te verlenen, met uitzondering van een verzameling apparaten die geen toegang tot uw organisatie mogen hebben. U maakt een blokkeringslijst door aangepaste regels in te stellen voor het blokkeren van apparaatplatformen die niet met de postvakken van de organisatie mogen synchroniseren. De standaardregel moet zo worden ingesteld dat alle apparaten die niet uitdrukkelijk zijn geblokkeerd door bestaande regels, toegang mogen hebben. Als u een nieuw apparaat of een verzameling apparaten aan de blokkeringslijst wilt toevoegen, maakt u een nieuwe aangepaste regel.|
|Gemengde acceptatie en blokkering|Naast het maken van acceptatie- en blokkeringslijsten kunt u nieuwe mobiele apparaten in quarantaine plaatsen wanneer ze binnenkomen in de organisatie zodat u ze kunt evalueren. Als u bijvoorbeeld een blokkeringslijst hebt voor mobiele apparaten die niet zijn toegestaan binnen uw organisatie, en een acceptatielijst voor mobiele apparaten die wel zijn toegestaan binnen de organisatie, kunt u de standaardregel instellen op quarantaine. Alle overige apparaten worden automatisch in quarantaine geplaatst. Zo kunt u nieuwe apparaten detecteren zodra ze de organisatie binnenkomen en beslissen of u ze aan de acceptatie- of de blokkeringslijst toevoegt.|
De volgende procedure beschrijft hoe u een aangepaste regel maakt.

## <a name="create-a-default-access-rule"></a>Een standaardtoegangsregel maken

1.  Kies in [Microsoft Intune-beheerconsole](https://manage.microsoft.com)  **Beleid** &gt; **Exchange ActiveSync**.

2.  Selecteer in de lijst **Standaardregel** de toegangsregel die u wilt toepassen op alle mobiele apparaten die niet onder een regel of een persoonlijke uitzondering vallen. Kies **Opslaan**.

De volgende procedure beschrijft hoe u een aangepaste regel maakt:

## <a name="create-a-custom-access-rule"></a>Een aangepaste toegangsregel maken

1. Kies in [Microsoft Intune-beheerconsole](https://manage.microsoft.com)  **Beleid** &gt; **Exchange ActiveSync**.

2.  Selecteer in de lijst **Platformuitzonderingen** de optie **Regel toevoegen** en maak een aangepaste regel. Kies **Opslaan**.
