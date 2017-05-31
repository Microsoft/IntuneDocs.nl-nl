---
title: App-gegevens beveiligen met behulp van MAM-beleid | Microsoft Docs
description: "In dit onderwerp wordt uitgelegd hoe Mobile Application Management-beleid kan helpen bij het beveiligen van uw bedrijfsgegevens, het voorkomen van gegevensverlies, en het gescheiden houden van privégegevens en werkgegevens."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab6cd622-b738-4a63-9c91-56044aaafa6d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 9959e9f757e83c7aa4274b7e7b9df949fff022cc
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="protect-app-data-using-app-protection-policies-with-microsoft-intune"></a>Bescherm app-gegevens met beveiligingsbeleid voor apps met Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="how-you-can-protect-app-data"></a>Hoe u app-gegevens kunt beveiligen
Uw werknemers gebruiken mobiele apparaten voor zowel privé- als werktaken. U wilt er niet alleen voor zorgen dat uw werknemers productief kunnen zijn, maar u wilt ook bedoeld of onbedoeld gegevensverlies voorkomen.  Daarnaast wilt u de bedrijfsgegevens die werknemers gebruiken, kunnen beschermen door gebruik te maken van apparaten die u niet beheert.

U kunt het beveiligingsbeleid voor apps van Intune gebruiken om de gegevens van uw bedrijf te beveiligen. Omdat het beveiligingsbeleid voor apps van Intune **onafhankelijk van een beheeroplossing voor mobiele apparaten (MDM)** werkt, kunt u MAM gebruiken om uw bedrijfsgegevens te beveiligen met of zonder inschrijving van apparaten in een oplossing voor apparaatbeheer. Door **beleid op app-niveau** te implementeren, kunt u de toegang tot bedrijfsbronnen beperken en gegevens binnen de controlesfeer van uw IT-afdeling houden.

U kunt beveiligingsbeleid configureren voor apps die worden uitgevoerd op:

-   **Apparaten die zijn geregistreerd bij Microsoft Intune:** bij de apparaten in deze categorie gaat het meestal om apparaten die in het bezit zijn van het bedrijf.

-   **Apparaten die zijn geregistreerd bij een MDM-oplossing van derden:** bij de apparaten in deze categorie gaat het meestal om apparaten die in het bezit zijn van het bedrijf.

      > [!NOTE]
      > U kunt beter geen beveiligingsbeleid voor apps met mobiel applicatiebeheer of oplossingen voor beveiligde containers van derden gebruiken.

-   **Apparaten die niet zijn ingeschreven bij een MDM-oplossing:** bij de apparaten in deze categorie gaat het meestal om apparaten die in het bezit zijn van werknemers, of om apparaten die niet worden beheerd door of zijn ingeschreven bij Intune of een andere MDM-oplossing.

> [!IMPORTANT]
> U kunt beveiligingsbeleid voor apps maken voor mobiele Office-apps die verbinding maken met Office 365-services. Het beveiligingsbeleid voor apps wordt niet ondersteund voor apps die verbinding maken met on-premises Exchange-, Skype voor Bedrijven- of SharePoint-services.

## <a name="benefits-of-using-app-protection-policies"></a>Voordelen van het gebruik van het beveiligingsbeleid voor apps

-   **Uw bedrijfsgegevens worden beschermd op het niveau van de app.** Omdat Mobile Application Management geen apparaatbeheer vereist, kunt u bedrijfsgegevens beveiligen op zowel beheerde als onbeheerde apparaten. Het beheer wordt gecentreerd rond de identiteit van de gebruiker, waardoor er geen apparaatbeheer is vereist.

-   **De productiviteit van gebruikers wordt niet negatief beïnvloed en het beleid wordt niet toegepast wanneer u de app in een persoonlijke context gebruikt.** Het beleid wordt alleen in een werkcontext toegepast, waardoor u de mogelijkheid hebt om bedrijfsgegevens te beschermen zonder aan persoonlijke gegevens te komen.

Het gebruik van MDM met beveiligingsbeleid voor apps biedt extra voordelen en bedrijven kunnen tegelijkertijd MAM met en zonder MDM gebruiken. Een medewerker kan bijvoorbeeld een telefoon gebruiken die door het bedrijf is verstrekt en daarnaast een privétablet gebruiken. In dit geval is de bedrijfstelefoon ingeschreven in MDM en beveiligd door het beveiligingsbeleid voor apps, terwijl het privéapparaat alleen door beveiligingsbeleid voor apps wordt beveiligd.

- **MDM zorgt ervoor dat het apparaat wordt beveiligd.** U kunt bijvoorbeeld een pincode vereisen voor toegang tot het apparaat, of u kunt beheerde apps op het apparaat implementeren. U kunt ook apps implementeren op apparaten via uw MDM-oplossing, zodat u meer controle over het beheer van apps hebt.

- **Het beveiligingsbeleid voor apps zorgt ervoor dat de app-laag wordt beveiligd.** U kunt bijvoorbeeld beleid implementeren dat er een pincode is vereist om een werkgerelateerde app te openen, waarmee wordt voorkomen dat er gegevens tussen apps worden gedeeld en wordt voorkomen dat gegevens van bedrijfs-apps naar een persoonlijke opslaglocatie worden opgeslagen.

## <a name="devices-that-support-mam"></a>Apparaten die MAM ondersteunen
Beveiligingsbeleid voor apps wordt momenteel ondersteund op:
-   iOS 8.1 of hoger
-   Android 4 of hoger

>[!NOTE]
>Windows-apparaten worden niet ondersteund voor MAM zonder inschrijvingsscenario. Wanneer u Windows 10-apparaten registreert bij Intune, kunt u Windows Information Protection gebruiken, dat vergelijkbare functionaliteit biedt. Zie [Uw ondernemingsgegevens beveiligen met Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip) voor meer informatie.


##  <a name="how-app-protection-policies-protect-app-data"></a>Hoe het beveiligingsbeleid voor apps app-gegevens beveiligen

###  <a name="apps-without-app-protection-policies"></a>Apps zonder het beveiligingsbeleid voor apps

![Afbeelding die laat zien dat gegevens vrij kunnen bewegen tussen apps wanneer er geen beveiligingsbeleid voor apps is](../media/Apps_without_MAM_policies.png)

Wanneer u apps zonder beperkingen gebruikt, kunnen de bedrijfsgegevens en persoonlijke gegevens met elkaar worden vermengd. Bedrijfsgegevens kunnen terechtkomen op locaties zoals persoonlijke opslag of kunnen worden overgedragen naar apps die buiten uw controlesfeer liggen, wat kan leiden tot gegevensverlies. De pijlen in het diagram geven onbeperkte verplaatsingen van gegevens tussen apps (bedrijfs-apps en persoonlijke app) en naar opslaglocaties aan.

### <a name="data-protection-with-app-protection-policies"></a>Gegevensbeveiliging met het beveiligingsbeleid voor apps

![Afbeelding die laat zien hoe bedrijfsgegevens worden beveiligd wanneer het beveiligingsbeleid voor apps wordt toegepast](../media/Apps_with_mobile_app_policies.png)

U kunt het beveiligingsbeleid voor apps gebruiken om te voorkomen dat bedrijfsgegevens worden opgeslagen in de lokale opslag van het apparaat en de verplaatsing van gegevens naar andere apps die niet zijn beveiligd door het beveiligingsbeleid voor apps te beperken. Beveiligingsbeleidsinstellingen voor apps bevatten:
- Beleid voor gegevensverplaatsing zoals **Geen Opslaan als** en **Knippen, kopiëren en plakken beperken**.
- Instellingen voor toegangsbeleid zoals **Eenvoudige pincode vereisen voor toegang** en **Beheerde apps blokkeren op gekraakte of geroote apparaten**.

### <a name="data-protection-with-app-protection-on-devices-that-are-managed-by-a-mdm-solution"></a>Gegevensbeveiliging met beveiligingsbeleid voor apps op apparaten die worden beheerd door een MDM-oplossing

![Afbeelding die laat zien hoe beveiligingsbeleid voor apps werkt op BYOD-apparaten (Bring Your Own Devices)](../media/MAM_BYOD_November.png)

**Voor apparaten die zijn geregistreerd in een MDM-oplossing**: het vorige diagram toont u de beveiligingslagen die het MDM-beleid en het beveiligingsbeleid voor apps samen bieden.

De MDM-oplossing:

-   Registreert het apparaat.

-   Implementeert apps naar het apparaat.

-   Zorgt voor continue apparaatcompatibiliteit en -beheer.

**Het beveiligingsbeleid voor apps biedt op de volgende manieren extra waarde:**

-   De beleidsregels beveiligen uw bedrijfsgegevens tegen het lekken van gegevens naar consumenten-apps en -services.

-   De beleidsregels passen beperkingen (opslaan als, klembord, pincode enzovoort) op mobiele apps toe.

-   De beleidsregels wissen bedrijfsgegevens van apps zonder die apps van het apparaat te verwijderen.


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a>Het biedt gegevensbeveiliging met het beveiligingsbeleid voor apps voor apparaten die niet zijn ingeschreven

![Afbeelding die laat zien hoe het beveiligingsbeleid voor apps werkt op beheerde apparaten](../media/MAM_ManagedDevices_November.png)

Het voorgaande diagram laat zien hoe beleid voor gegevensbeveiliging op app-niveau werkt zonder MDM.

Voor BYOD-apparaten die niet zijn geregistreerd in een MDM-oplossing, kan het beveiligingsbeleid voor apps helpen bij het beschermen van bedrijfsgegevens op app-niveau.

Er zijn echter enkele beperkingen waarmee u rekening moet houden:

-   U kunt geen apps implementeren op het apparaat. De gebruiker moet de apps downloaden uit de Store.

-   U kunt geen certificaatprofielen op deze apparaten inrichten.

-   U kunt geen Wi-Fi- en VPN-instellingen van het bedrijf op deze apparaten configureren.


## <a name="multi-identity"></a>Meerdere identiteiten

Met apps die ondersteuning bieden voor meerdere identiteiten, kunt u verschillende accounts (zakelijk en persoonlijk) gebruiken voor toegang tot dezelfde apps, terwijl beveiligingsbeleid voor apps wordt toegepast wanneer de apps worden gebruikt in zakelijke context.  

Wanneer een gebruiker de OneDrive-app start vanaf een werkaccount, kan hij de bestanden niet verplaatsen naar een persoonlijke opslaglocatie. Wanneer OneDrive wordt gebruikt voor een persoonlijk account, kunnen de gegevens op de persoonlijke OneDrive-locatie zonder beperkingen worden gekopieerd en verplaatst.  

- Meer informatie over de apps die ondersteuning bieden voor [MAM en meerdere identiteiten](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) met Intune.

##  <a name="next-steps"></a>Volgende stappen
- [Aan de slag met configureren van beveiligingsbeleid voor apps](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

- [Beveiligingsbeleid voor apps maken en implementeren met Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)

