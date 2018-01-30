---
title: Wat is beveiligingsbeleid voor apps
titleSuffix: Azure portal
description: Gebruik dit onderwerp voor meer informatie om de gegevens van uw bedrijf te beveiligen met het beveiligingsbeleid voor apps van Microsoft Intune.
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 01/19/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a6645261e2a90ea3890dc22b42fe65d6af4af6e5
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="what-are-app-protection-policies"></a>Wat is beveiligingsbeleid voor apps?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met het beveiligingsbeleid voor apps van Microsoft Intune kunt u uw bedrijfsgegevens beveiligen en voorkomen dat gegevens verloren gaan.

## <a name="how-you-can-protect-app-data"></a>Hoe u app-gegevens kunt beveiligen
Uw werknemers gebruiken mobiele apparaten voor zowel privé- als werktaken.  U wilt er niet alleen voor zorgen dat uw werknemers productief kunnen zijn, maar u wilt ook bedoeld of onbedoeld gegevensverlies voorkomen.  Bovendien wilt u de mogelijkheid hebben om bedrijfsgegevens te beschermen die toegankelijk zijn via apparaten, zelfs als deze apparaten niet door u worden beheerd.

U kunt het beveiligingsbeleid voor apps van Intune gebruiken om de gegevens van uw bedrijf te beveiligen. Omdat het beveiligingsbeleid voor apps van Intune **onafhankelijk van een beheeroplossing voor mobiele apparaten (MDM)** werkt, kunt u het gebruiken om de gegevens van uw bedrijf te beveiligen met of zonder inschrijving van apparaten in een oplossing voor apparaatbeheer. Door **beleid op app-niveau** te implementeren, kunt u de toegang tot bedrijfsbronnen beperken en gegevens binnen de controlesfeer van uw IT-afdeling houden.

Het beveiligingsbeleid voor apps kan worden geconfigureerd voor apps die worden uitgevoerd op apparaten die:

- **Zijn ingeschreven bij Microsoft Intune:** bij de apparaten in deze categorie gaat het meestal om apparaten die in het bezit zijn van het bedrijf.

-   **Zijn ingeschreven bij een MDM-oplossing van derden:** bij de apparaten in deze categorie gaat het meestal om apparaten die in het bezit zijn van het bedrijf.

  > [!NOTE]
  > MAM-beleid mag niet worden gebruikt met MAM-oplossingen van derden of beveiligde container-oplossingen.

-   **Niet zijn ingeschreven bij een MDM-oplossing:** bij de apparaten in deze categorie gaat het meestal om apparaten die in het bezit zijn van werknemers, of om apparaten die niet worden beheerd door of zijn ingeschreven bij Intune of een andere MDM-oplossing.

> [!IMPORTANT]
> U kunt MAM-beleid maken voor mobiele Office-apps die verbinding maken met Office 365-services. Beveiligingsbeleid voor apps wordt niet ondersteund voor apps die verbinding maken met on-premises Exchange- of SharePoint-services.

**De belangrijke voordelen van het gebruik van het beveiligingsbeleid voor apps zijn**

-   Uw bedrijfsgegevens worden beschermd op het niveau van de app.  Omdat het beheer van mobiele apps geen apparaatbeheer vereist, kunt u bedrijfsgegevens beveiligen op zowel beheerde als onbeheerde apparaten. Het beheer wordt gecentreerd rond de identiteit van de gebruiker, waardoor er geen apparaatbeheer is vereist.

-   De productiviteit van eindgebruikers wordt niet negatief beïnvloed en het beleid wordt niet toegepast wanneer de app in een persoonlijke context wordt gebruikt.  Het beleid wordt alleen in een werkcontext toegepast, waardoor u de mogelijkheid hebt om bedrijfsgegevens te beschermen zonder aan persoonlijke gegevens te komen.

Het gebruik van MDM met het beveiligingsbeleid voor apps biedt extra voordelen en bedrijven kunnen het beveiligingsbeleid voor apps met en zonder MDM gelijktijdig gebruiken. Een medewerker kan bijvoorbeeld een telefoon gebruiken die door het bedrijf is verstrekt en daarnaast een privétablet gebruiken.  In dit geval is de bedrijfstelefoon ingeschreven in MDM en beveiligd door het beveiligingsbeleid voor apps, terwijl het privéapparaat alleen door beveiligingsbeleid voor apps wordt beveiligd.

- **MDM zorgt ervoor dat het apparaat wordt beveiligd**.  U kunt bijvoorbeeld een pincode vereisen voor toegang tot het apparaat, of u kunt beheerde apps op het apparaat implementeren. U kunt ook apps implementeren op apparaten via uw MDM-oplossing, zodat u meer controle over het beheer van apps hebt.

- **Het beveiligingsbeleid voor apps zorgt ervoor dat de app-laag goed wordt beveiligd**. U kunt bijvoorbeeld een pincode vereisen voor het openen van een werkgerelateerde app, of voor het uitwisselen van gegevens tussen apps, of u kunt voorkomen dat gegevens van bedrijfsapps naar een persoonlijke opslaglocatie worden opgeslagen.


### <a name="supported-platforms-for-app-protection-polices"></a>Ondersteunde platformen voor het beveiligingsbeleid voor apps
-   iOS 9 of hoger
-   Android 4.4 of hoger

Windows-apparaten worden momenteel niet ondersteund. Wanneer u Windows 10-apparaten registreert bij Intune, kunt u Windows Information Protection gebruiken, dat vergelijkbare functionaliteit biedt. Zie [Uw ondernemingsgegevens beveiligen met Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip) voor meer informatie.
##  <a name="how-app-protection-policies-protect-app-data"></a>Hoe het beveiligingsbeleid voor apps app-gegevens beveiligen

####  <a name="apps-without-app-protection-policies"></a>Apps zonder het beveiligingsbeleid voor apps

![Afbeelding die laat zien dat gegevens vrij kunnen bewegen tussen apps wanneer er geen beveiligingsbeleid voor apps is](./media/apps-without-protection-policies.png)

Bedrijfsgegevens en persoonlijke gegevens kunnen met elkaar worden vermengd als er apps zonder beperkingen worden gebruikt.  Bedrijfsgegevens kunnen terechtkomen op locaties zoals persoonlijke opslag of kunnen worden overgebracht naar apps die buiten uw controlesfeer liggen, wat leidt tot gegevensverlies. De pijlen in het diagram geven onbeperkte verplaatsingen van gegevens tussen apps (bedrijfs-apps en persoonlijke app) en naar opslaglocaties aan.

### <a name="data-protection-with-app-protection-policies"></a>Gegevensbeveiliging met het beveiligingsbeleid voor apps

![Afbeelding die laat zien hoe bedrijfsgegevens worden beveiligd wanneer het beveiligingsbeleid voor apps wordt toegepast ](./media/apps-with-protection-policies.png)


U kunt het beveiligingsbeleid voor apps gebruiken om te voorkomen dat bedrijfsgegevens worden opgeslagen in de lokale opslag van het apparaat en de verplaatsing van gegevens naar andere apps die niet zijn beveiligd door het beveiligingsbeleid voor apps beperken. Beveiligingsbeleidsinstellingen voor apps bevatten:
- Beleid voor gegevensverplaatsing zoals **Geen Opslaan als**, **Knippen, kopiëren en plakken beperken**.
- Instellingen voor toegangsbeleid zoals **Eenvoudige pincode vereisen voor toegang**, **De uitvoering blokkeren van beheerde apps die worden uitgevoerd op apparaten waarop jailbreaking is uitgevoerd of die worden uitgevoerd als rootgebruiker**.

### <a name="data-protection-with-app-protection-policies-on-devices-managed-by-a-mdm-solution"></a>Gegevensbeveiliging met het beveiligingsbeleid voor apps op apparaten die worden beheerd door een MDM-oplossing

![Afbeelding die laat zien hoe het beveiligingsbeleid voor apps werkt op BYOD-apparaten](./media/app-protection-policies-with-mdm.png)

**Voor apparaten die zijn ingeschreven in een MDM-oplossing**-

Bovenstaande afbeelding toont de beveiligingslagen die worden geboden door het MDM- en beveiligingsbeleid voor apps samen.

De MDM-oplossing:

-   Schrijft het apparaat in

-   Implementeert de apps op het apparaat

-   Zorgt voor continue apparaatcompatibiliteit en -beheer

**Het beveiligingsbeleid voor apps biedt op de volgende manieren extra waarde:**

-   Het helpt u bedrijfsgegevens te beveiligen tegen het lekken van gegevens naar consumenten-apps en -services

-   Het past beperkingen toe (opslaan als, klembord, pincode, enzovoort) op mobiele apps

-   Het wist bedrijfsgegevens van apps zonder die apps van het apparaat te verwijderen


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a>Het biedt gegevensbeveiliging met het beveiligingsbeleid voor apps voor apparaten die niet zijn ingeschreven

![Afbeelding die laat zien hoe het beveiligingsbeleid voor apps werkt op beheerde apparaten](./media/app-protection-policies-without-mdm.png)

Het bovenstaande diagram laat zien hoe beleid voor gegevensbeveiliging op app-niveau werkt zonder MDM

Voor BYOD-apparaten die niet zijn ingeschreven in een MDM-oplossing, kan het beveiligingsbeleid voor apps helpen bij het beschermen van bedrijfsgegevens op app-niveau.
Er zijn echter enkele beperkingen waar u rekening mee moet houden, zoals:

-   U kunt geen apps implementeren op het apparaat.  De eindgebruiker moet de apps downloaden uit de Store.

-   U kunt geen certificaatprofielen op deze apparaten inrichten.

-   U kunt geen Wi-Fi- en VPN-instellingen van het bedrijf op deze apparaten inrichten.


## <a name="multi-identity"></a>Meerdere identiteiten

Met apps die ondersteuning bieden voor meerdere identiteiten, kunt u verschillende accounts (zakelijk en persoonlijk) gebruiken voor toegang tot dezelfde apps, terwijl beveiligingsbeleid voor apps wordt toegepast wanneer de apps worden gebruikt in zakelijke context.

Wanneer een gebruiker de OneDrive-app start vanaf een werkaccount, kan hij de bestanden niet verplaatsen naar een persoonlijke opslaglocatie. Wanneer OneDrive wordt gebruikt voor een persoonlijk account, kunnen de gegevens op de persoonlijke OneDrive-locatie zonder beperkingen worden gekopieerd en verplaatst.

- Meer informatie over de apps die ondersteuning bieden voor [MAM en meerdere identiteiten](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) met Intune.

##  <a name="next-steps"></a>Volgende stappen

[Beveiligingsbeleid voor apps maken en implementeren met Microsoft Intune](app-protection-policies.md)
