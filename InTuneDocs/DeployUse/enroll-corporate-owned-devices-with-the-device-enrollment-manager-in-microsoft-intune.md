---
title: Inschrijven met de apparaatinschrijvingsmanager | Microsoft Intune
description: "De apparaatinschrijvingsmanager (DEM) kan een groot aantal mobiele apparaten in bedrijfseigendom beheren via één gebruikersaccount."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 656c93771776fd317f2b8d91bc59125fba1eb0b9
ms.openlocfilehash: 83b89d06793f6f3934537408fb600b3b89afd35b


---


# <a name="enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune"></a>Apparaten in bedrijfseigendom inschrijven met de apparaatinschrijvingsmanager in Microsoft Intune
Organisaties kunnen Intune gebruiken voor het beheren van een groot aantal mobiele apparaten met één gebruikersaccount. Het account voor de *apparaatinschrijvingsmanager* (DEM-account) is een speciaal Intune-account waarmee maximaal duizend apparaten kunnen worden geregistreerd. Voor elk geregistreerd apparaat is een licentie nodig. Gebruik apparaten die zijn geregistreerd met dit account als gedeelde apparaten in plaats van persoonlijke (BYOD)-apparaten. Gebruikers kunnen bijvoorbeeld geen 'systeemeigen' e-mail-apps gebruiken. Licenties voor DEM worden verleend per apparaat, niet per gebruiker.

U kunt bijvoorbeeld een DEM-gebruikersaccount voor een winkelmanager of supervisor toewijzen zodat zij het volgende kunnen doen:

-   Apparaten registreren in Intune.

-   Aanmelden bij de bedrijfsportal om bedrijfsapps op te halen.

-   Software installeren en verwijderen.

-   Toegang tot bedrijfsgegevens configureren.


**Een scenario voor apparaatinschrijvingsmanagers:** een restaurant wil tablets voor de verkooppunten van het bedieningspersoneel en bestellingsmonitoren voor het keukenpersoneel. De werknemers hebben geen toegang tot bedrijfsgegevens nodig of moeten zich aanmelden als gebruikers. De Intune-beheerder maakt een account voor apparaatinschrijvingsmanagers en schrijft de bedrijfsapparaten in met behulp van dat account. De beheerder kan de referenties voor de apparaatinschrijvingsmanager ook aan een restaurantmanager geven, zodat de manager de apparaten kan inschrijven en beheren.

De beheerder of de manager kan rolspecifieke apps op de restaurantapparaten implementeren. Een beheerder kan het apparaat ook selecteren in de Intune-console en het apparaat onttrekken aan het beheer van mobiele apparaten met behulp van de beheerconsole.

Apparaten die zijn geregistreerd met een account voor apparaatinschrijvingsmanagers, hebben de volgende beperkingen:
  - Er is geen specifieke gebruiker voor het apparaat. Er is daarom geen e-mailadres of toegang tot bedrijfsgegevens. VPN kan echter nog wel apps op apparaten leveren met toegang tot gegevens.
  - Er is geen voorwaardelijke toegang mogelijk omdat dit per gebruiker moet worden opgegeven.
  - U kunt geen apparaten opnieuw instellen vanuit de bedrijfsportal.
  - Alleen het lokale apparaat wordt weergegeven in de bedrijfsportal-app of op de website.
  - De apparaten kunnen geen Apple VPP-apps (Volume Purchase Program) gebruiken vanwege de Apple-ID-vereisten per gebruiker voor het beheer van apps.
  - (iOS) De apparaten kunnen niet ook worden geregistreerd met Apple Configurator of het Apple Device Enrollment Program (DEP), maar DEP- of Apple Configurator-beheerde apparaten kunnen worden geregistreerd zonder gebruikersaffiniteit.

> [!NOTE]
> Om bedrijfsapps te implementeren op apparaten die worden beheerd met de apparaatinschrijvingsmanager, moet u de bedrijfsportal-app als een **Vereiste installatie** implementeren naar het gebruikersaccount voor de apparaatinschrijvingsmanager.
> Om prestaties te verbeteren wordt bij het weergeven van de bedrijfsportal-app op een DEM-apparaat DEM alleen het lokale apparaat weergegeven. Extern beheer van andere DEM-apparaten is alleen mogelijk via de Intune-beheerconsole.

## <a name="create-device-enrollment-manager-accounts"></a>Apparaatinschrijvingsbeheerder-accounts maken
Apparaatinschrijvingsbeheerder-accounts zijn gebruikersaccounts met een machtiging voor het inschrijven van grote aantallen apparaten in bedrijfseigendom. Alleen gebruikers in de Intune-console kunnen apparaatinschrijvingsbeheerders zijn.

#### <a name="add-a-device-enrollment-manager-to-intune"></a>Een apparaatinschrijvingsbeheerder toevoegen aan Intune

1.  Ga naar de [Microsoft Intune-accountportal](http://go.microsoft.com/fwlink/?LinkId=698854) en meld u aan bij uw beheerdersaccount.

2.  Kies **Gebruiker toevoegen**.

3.  Controleer of het gebruikersaccount dat een apparaatinschrijvingsbeheerder moet worden, wordt vermeld. Als dat niet het geval is, voegt u de gebruiker toe door **Nieuw** te kiezen en de procedure voor het **toevoegen van de gebruiker** te voltooien. Er is een abonnementslicentie vereist voor elke gebruiker die de service gebruikt. De apparaatinschrijvingsmanager mag geen Intune-beheerder zijn. Controleer of u meer licenties moet toevoegen voordat u deze functie gebruikt.

4.  Meld u aan bij de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) met uw beheerdersreferenties.

5.  Kies in het navigatievenster **Beheer**, ga naar **Beheerdersbeheer** en selecteer **Apparaatinschrijvingsmanager**. De pagina **Apparaatinschrijvingsmanagers** wordt geopend.

6.  Kies **Toevoegen**. Het dialoogvenster **Apparaatinschrijvingsbeheerder toevoegen** wordt geopend.

7.  Voer de **gebruikers-id** van het Intune-account in en kies **OK**. De gebruiker van het account voor apparaatinschrijvingsmanagers mag geen Intune-beheerder zijn.

8.  De apparaatinschrijvingsmanager kan nu mobiele apparaten inschrijven met behulp van dezelfde procedure die een eindgebruiker gebruikt voor een BYOD-scenario in de bedrijfsportal. De eindgebruiker van het manageraccount kan de bedrijfsportal-app installeren en het apparaat inschrijven met zijn of haar DEM-referenties, op maximaal 1000 apparaten.

## <a name="delete-a-device-enrollment-manager-from-intune"></a>Een apparaatinschrijvingsbeheerder uit Intune verwijderen

1.  Meld u aan bij de [Microsoft Intune-accountportal](http://manage.microsoft.com) met uw beheerdersreferenties.

2.  Kies in het navigatievenster **Beheer**, ga naar **Beheerdersbeheer** en selecteer **Apparaatinschrijvingsmanager**. De pagina **Apparaatinschrijvingsmanagers** wordt geopend.

3.  Selecteer de apparaatregistratiemanager **Gebruiker** die u wilt verwijderen, en kies vervolgens **Verwijderen**. Deze gebruiker wordt niet uit Intune verwijderd en de apparaten die deze gebruiker beheert, blijven ingeschreven in Intune. Het verwijderen van een apparaatinschrijvingsbeheerder verhindert dat de betreffende gebruiker meer apparaten in Intune inschrijft.

4.  Kies **Ja** om te bevestigen dat u de apparaatinschrijvingsmanager wilt verwijderen.

Het verwijderen van een apparaatinschrijvingsbeheerder heeft geen invloed op ingeschreven apparaten. Wanneer een apparaatinschrijvingsbeheerder wordt verwijderd:

-   Heeft dat geen invloed op ingeschreven apparaten.

-   Blijven ingeschreven apparaten volledig beheerd.

-   Blijven de accountreferenties van de verwijderde apparaatinschrijvingsmanager geldig voor aanmelding bij de bedrijfsportal om toegang tot apps te krijgen.

-   Kunnen apparaten nog steeds niet worden gewist of buiten gebruik worden gesteld met de accountreferenties van de verwijderde apparaatinschrijvingsmanager.

-   Blijft het account van de verwijderde apparaatinschrijvingsmanager gerelateerd aan ingeschreven apparaten, maar kunnen er geen extra apparaten worden ingeschreven.



<!--HONumber=Nov16_HO3-->


