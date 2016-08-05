---
title: Inschrijven met apparaatregistratiebeheer | Microsoft Intune
description: "Het apparaatregistratiebeheer (DEM) kan een groot aantal mobiele apparaten in bedrijfseigendom beheren via één gebruikersaccount."
keywords: 
author: NathBarn
manager: arob98
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1f6f98d582ce9a686ca02682a9066d8b2162d6ab
ms.openlocfilehash: d126bbfc40cada71458b03c23e571490b4af4d44


---


# Apparaten in bedrijfseigendom inschrijven met de apparaatinschrijvingsbeheerder in Microsoft Intune
Organisaties kunnen Intune gebruiken voor het beheren van een groot aantal mobiele apparaten met één gebruikersaccount. Het *Manager voor apparaatregistratie*-account (DEM-account) is een speciaal Intune-account met machtigingen om meer dan 1000 apparaten te registreren. Gebruik apparaten die zijn geregistreerd met het Manager voor apparaatregistratie-account als gedeelde apparaten in plaats van persoonlijke (BYOD)-apparaten. Gebruikers kunnen bijvoorbeeld geen 'systeemeigen' e-mail-apps gebruiken. U kunt een gebruikersaccount voor een winkelmanager of supervisor, bijvoorbeeld een apparaatinschrijvingsbeheerder, toewijzen om het volgende te kunnen uitvoeren:

-   Apparaten in Intune inschrijven

-   Aanmelden bij de bedrijfsportal om bedrijfsapps op te halen

-   Software installeren en verwijderen

-   Toegang tot bedrijfsgegevens configureren


**Voorbeelden van een scenario voor apparaatregistratiemanagers:** een restaurant wil tablets voor de verkooppunten van het bedieningspersoneel en bestellingsmonitors voor het keukenpersoneel. De werknemers hebben geen toegang tot bedrijfsgegevens nodig en hoeven zich niet aan te melden als gebruiker. De Intune-beheerder maakt een apparaatinschrijvingsbeheerder-account en schrijft de bedrijfsapparaten in met behulp van dat account. De beheerder kan de referenties voor de apparaatinschrijvingsbeheerder ook aan een restaurantmanager geven, zodat hij of zij de apparaten kan inschrijven en beheren.

De beheerder of de manager kan rolspecifieke apps op de restaurantapparaten implementeren. Een beheerder het apparaat ook selecteren in de Intune-console en het apparaat onttrekken aan het beheer van mobiele apparaten met behulp van de beheerconsole.

Apparaten die zijn geregistreerd met een Manager voor apparaatregistratie-account hebben de volgende beperkingen:
  - Er zijn geen specifieke gebruikers zodat alle apparaten 'gebruikersloos' zijn. Er is daarom geen toegang tot e-mail- of bedrijfsgegevens, al kunnen apparaat-apps bijvoorbeeld met VPN nog steeds toegang tot gegevens krijgen
  - Er is geen voorwaardelijke toegang mogelijk omdat dit per gebruiker moet worden opgegeven
  - Dit kunnen geen apparaten zijn die opnieuw zijn ingesteld vanuit de bedrijfsportal
  - Alleen het lokale apparaat wordt weergegeven in de bedrijfsportal-app of website
  - Er zijn geen Apple VPP-apps (Volume Purchase Program) vanwege de Apple-ID-vereisten per gebruiker voor het beheer van apps
  - De apparaten kunnen niet ook worden geregistreerd met Apple Configurator of het Apple-apparaatregistratieprogramma (iOS-apparaten)

> [!NOTE]
> Om bedrijfs-apps te implementeren op apparaten die worden beheerd met de apparaatinschrijvingsbeheerder, moet u de bedrijfsportal-app als een **Vereiste installatie** implementeren naar het gebruikersaccount voor de apparaatinschrijvingsbeheerder.
> Om prestaties te verbeteren wordt bij het weergeven van de bedrijfsportal-app op een DEM-apparaat DEM alleen het lokale apparaat weergegeven. Extern beheer van andere DEM-apparaten is alleen mogelijk via de Intune-beheerconsole.

## Apparaatinschrijvingsbeheerder-accounts maken
Apparaatinschrijvingsbeheerder-accounts zijn gebruikersaccounts met een machtiging voor het inschrijven van grote aantallen apparaten in bedrijfseigendom. Alleen gebruikers in de Intune-console kunnen apparaatinschrijvingsbeheerders zijn.

#### Een apparaatinschrijvingsbeheerder toevoegen aan Intune

1.  Ga naar de [Microsoft Intune-accountportal](http://go.microsoft.com/fwlink/?LinkId=698854) en meld u aan bij uw beheerdersaccount.

2.  Kies **Gebruiker toevoegen**.

3.  Controleer of het gebruikersaccount dat een apparaatinschrijvingsbeheerder moet worden, wordt vermeld. Als dat niet het geval is, voegt u de gebruiker toe door **Nieuw** te kiezen en de procedure voor het toevoegen van de gebruiker te voltooien. Er is een abonnementslicentie vereist voor elke gebruiker die toegang de service heeft en de *apparaatinschrijvingsbeheerder* mag geen Intune-beheerder zijn. Bepaal of u meer licenties moet toevoegen voordat u deze functie gebruikt.

4.  Meld u aan bij de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) met uw beheerdersaanmelding.

5.  Kies in het navigatievenster **Beheer**, ga naar **Beheerdersbeheer** en selecteer **Manager voor apparaatregistratie**. De pagina Apparaatinschrijvingsbeheerders wordt geopend.

6.  Kies **Toevoegen**. Het dialoogvenster **Apparaatinschrijvingsbeheerder toevoegen** wordt geopend.

7.  Voer de **gebruikers-id** van het Intune-account in en kies **OK**. De apparaatinschrijvingsbeheerder-gebruiker mag geen Intune-beheerder zijn.

8.  De apparaatinschrijvingsbeheerder kan nu mobiele apparaten inschrijven met behulp van dezelfde procedure die een eindgebruiker gebruikt voor een BYOD-scenario in de bedrijfsportal.

## Een apparaatinschrijvingsbeheerder uit Intune verwijderen

1.  Meld u aan bij de [Microsoft Intune-accountportal](http://manage.microsoft.com) met uw beheerdersaanmelding.

2.  Kies in het navigatievenster **Beheer**, ga naar **Beheerdersbeheer** en selecteer **Manager voor apparaatregistratie**. De pagina Apparaatinschrijvingsbeheerders wordt geopend.

3.  Selecteer de apparaatregistratiemanager **Gebruiker** die u wilt verwijderen, en kies vervolgens **Verwijderen**. Deze gebruiker wordt niet uit Intune verwijderd en de apparaten die deze gebruiker beheert, blijven ingeschreven in Intune. Het verwijderen van een apparaatinschrijvingsbeheerder verhindert dat de betreffende gebruiker meer apparaten in Intune inschrijft.

4.  Klik op **Ja** om te bevestigen dat u de apparaatregistratiemanager wilt verwijderen.

Het verwijderen van een apparaatinschrijvingsbeheerder heeft geen invloed op ingeschreven apparaten. Wanneer een apparaatinschrijvingsbeheerder wordt verwijderd:

-   heeft dat geen invloed op ingeschreven apparaten;

-   blijven ingeschreven apparaten volledig beheerd;

-   blijven de accountreferenties van de verwijderde apparaatinschrijvingsbeheerder geldig voor aanmelding bij de bedrijfsportal om toegang tot apps te krijgen;

-   kunnen apparaten nog steeds niet worden gewist of buiten gebruik worden gesteld met de accountreferenties van de verwijderde apparaatinschrijvingsbeheerder;

-   blijft de account van de verwijderde apparaatinschrijvingsbeheerder gerelateerd aan ingeschreven apparaten, maar kunnen er geen extra apparaten worden ingeschreven.



<!--HONumber=Jul16_HO4-->


