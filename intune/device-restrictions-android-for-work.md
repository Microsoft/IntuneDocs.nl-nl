---
title: Intune-apparaatbeperkingsinstellingen voor Android for Work
titlesuffix: Azure portal
description: Meer informatie over de Intune-instellingen die u kunt gebruiken voor het beheren van apparaatinstellingen en functionaliteit op Android for Work-apparaten.
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1830720b-16cb-4f2f-a71a-62967f882563
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: beb8368aa2db33df84bb64985177b47beebc80ac
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/12/2017
---
# <a name="android-for-work-device-restriction-settings-in-microsoft-intune"></a>Android for Work-apparaatbeperkingsinstellingen in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>Werkprofielinstellingen
-   **Kopiëren en plakken tussen werkprofielen en persoonlijke profielen**: hiermee beheert u het kopiëren en plakken tussen zakelijke apps en persoonlijke apps. Kies **Blokkeren** om blokkeren in te schakelen. Kies **Niet geconfigureerd** om blokkeren uit te schakelen.
- **Gegevens delen tussen werkprofiel en persoonlijk profiel**: gebruik deze instelling om te bepalen of apps in het werkprofiel gegevens mogen delen met apps in het persoonlijke profiel. Met deze instelling worden de deelacties binnen toepassingen bepaald (bijvoorbeeld de optie **Delen…** in de Chrome-browser-app). De instelling is niet van toepassing voor het klembordgedrag voor kopiëren en plakken. In tegenstelling tot de [beleidsinstellingen voor de beveiliging van apps](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) worden de instellingen voor apparaatbeperkingen beheerd via de Intune-portal en wordt de Android for Work-profielpartitie gebruikt om beheerde apps te isoleren. U kunt kiezen uit:
    - **Delen buiten grenzen toestaan**: dit is de standaardinstelling voor het delen van gegevens van het apparaat en deze is afhankelijk van de versie van Android die wordt uitgevoerd. Delen van het persoonlijke profiel naar het werkprofiel is standaard toegestaan. Delen van het werkprofiel naar het persoonlijke profiel is standaard geblokkeerd. Met deze instelling wordt voorkomen dat er gegevens worden gedeeld van het werkprofiel met het persoonlijke profiel. Google biedt geen een manier om het delen van gegevens van het persoonlijke profiel naar het werkprofiel te blokkeren op apparaten met versie 6.0 of later.   
    - **Met de apps in het werkprofiel kunnen aanvragen voor het delen van het persoonlijke profiel worden verwerkt**: gebruik deze optie om de ingebouwde Android-functie in te schakelen waarmee het delen van gegevens vanuit het persoonlijke profiel naar het werkprofiel is toegestaan. Wanneer dit is ingeschakeld, kan een deelverzoek van een app in het persoonlijke profiel worden gedeeld met apps in het werkprofiel. Dit is de standaardinstelling voor Android-apparaten met een oudere versie dan 6.0.
    - **Standaardbeperkingen voor delen**: biedt de mogelijkheid om in beide richtingen buiten de grenzen van het werkprofiel delen. Wanneer u deze instelling selecteert, kunnen apps met het werkprofiel gegevens delen met apps in het persoonlijke profiel die geen badge hebben. Gebruik deze instelling zorgvuldig omdat hiermee beheerde apps in het werkprofiel gegevens kunnen delen met apps aan de onbeheerde zijde van het apparaat.

-   **Werkprofielmeldingen terwijl het apparaat is vergrendeld**: hiermee kunt u bepalen of de apps in het werkprofiel gegevens in meldingen kunnen weergeven wanneer het apparaat is vergrendeld.
-   **Standaardapp-machtigingen**: hiermee stelt u het standaardmachtigingsbeleid in voor alle apps in het werkprofiel. Vanaf Android 6 wordt de gebruiker gevraagd bepaalde vereiste machtigingen aan apps toe te kennen wanneer de app wordt gestart. Met deze beleidsinstelling kunt u in het werkprofiel bepalen of gebruikers wordt gevraagd om machtigingen toe te kennen voor alle apps in het werkprofiel. U kunt bijvoorbeeld een app aan het werkprofiel toewijzen waarvoor toegang tot de locatie is vereist. Normaal gesproken wordt de gebruiker gevraagd of hij de app toegang tot de locatie wil geven. Met dit beleid kunt u beslissen of alle machtigingen automatisch moeten worden toegekend zonder ernaar te vragen, automatisch moeten worden geweigerd zonder ernaar te vragen of dat de eindgebruiker dit mag beslissen. U kunt kiezen uit:
    -   **Standaardwaarde apparaat**
    -   **Vragen**
    -   **Automatisch verlenen**
    -   **Automatisch weigeren**

    De verleningsstatus voor machtigingen kan verder worden gedefinieerd voor specifieke apps door een app-configuratiebeleid voor een individuele app te definiëren (onder **Mobiele apps** > **App-configuratiebeleid**).

### <a name="work-profile-password"></a>Werkprofielwachtwoord
- **Werkprofielwachtwoord vereisen**: (Android 7.0 en later met het werkprofiel ingeschakeld) definieer een wachtwoordcodebeleid dat alleen van toepassin is op de apps in het werkprofiel. De eindgebruiker heeft standaard de mogelijkheid om de twee afzonderlijk gedefinieerde pincodes te gebruiken, maar kan er ook voor kiezen om ze te combineren in de sterkste van de twee.
- **Minimale wachtwoordlengte**: hiermee geeft u het minimale aantal tekens op waaruit het wachtwoord moet bestaan (van **4**-**16**)
- **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: selecteer de hoeveelheid tijd voordat het werkprofiel wordt vergrendeld. De gebruiker moet vervolgens zijn referenties invoeren om weer toegang te krijgen.
- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: voer in hoe vaak een onjuist wachtwoord kan worden ingevoerd voordat het werkprofiel wordt gewist van het apparaat.
- **Wachtwoord verloopt (dagen)**: hiermee geeft u het aantal dagen op totdat het wachtwoord van de eindgebruiker moet worden gewijzigd (van **1**-**255**).
- **Vereist wachtwoordtype**: selecteer het type wachtwoord dat moet worden ingesteld op het apparaat. U kunt kiezen uit:
    - **Standaardwaarde apparaat**
    - **Lage beveiligingsbiometrie**
    - **Vereist**
    - **Ten minste numeriek**
    - **Numeriek complex**: (herhalende of opeenvolgende nummers zoals 1111 of 1234 zijn niet toegestaan)
    - **Ten minste alfabetisch**
    - **Ten minste alfanumeriek**
    - **Minstens alfanumeriek met symbolen**
- **Wachtwoorden niet opnieuw gebruiken**: voer het aantal nieuwe wachtwoorden in dat moet zijn gebruikt voordat een oud wachtwoord opnieuw kan worden gebruikt (van **1**-**24**).
- **Ontgrendelen met vingerafdruk**: blokkeren dat een eindgebruiker de vingerafdrukscanner van het apparaat gebruikt om het apparaat te ontgrendelen.
- **Smart Lock en andere trustagenten**: hiermee kunt u de functie Smart Lock beheren op compatibele apparaten. Met deze telefoonfunctie, soms ook wel vertrouwensagent genoemd, kunt u het wachtwoord voor het werkprofiel op het apparaat uitschakelen of overslaan als het zich op een vertrouwde locatie bevindt (bijvoorbeeld wanneer het is verbonden met een bepaald Bluetooth-apparaat, of wanneer het zich in de buurt van een NFC-tag bevindt). U kunt deze instelling gebruiken om te voorkomen dat gebruikers Smart Lock configureren.

## <a name="device-password"></a>Wachtwoord van apparaat

- **Minimale wachtwoordlengte**: hiermee geeft u het minimale aantal tekens op waaruit het wachtwoord moet bestaan (van **4**-**14**)
- **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: selecteer de hoeveelheid tijd voordat een inactief apparaat automatisch wordt vergrendeld.
- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: voer in hoe vaak een onjuist wachtwoord kan worden ingevoerd voordat alle gegevens worden gewist van het apparaat.
- **Wachtwoord verloopt (dagen)**: hiermee geeft u het aantal dagen op totdat het wachtwoord van de eindgebruiker moet worden gewijzigd (van **1**-**255**).
- **Vereist wachtwoordtype**: selecteer het type wachtwoord dat moet worden ingesteld op het apparaat. U kunt kiezen uit:
    - **Standaardwaarde apparaat**
    - **Lage beveiligingsbiometrie**
    - **Vereist**
    - **Ten minste numeriek**
    - **Numeriek complex**: (herhalende of opeenvolgende nummers zoals 1111 of 1234 zijn niet toegestaan)
    - **Ten minste alfabetisch**
    - **Ten minste alfanumeriek**
    - **Minstens alfanumeriek met symbolen**
- **Wachtwoorden niet opnieuw gebruiken**: voer het aantal nieuwe wachtwoorden in dat moet zijn gebruikt voordat een oud wachtwoord opnieuw kan worden gebruikt (van **1**-**24**).
- **Ontgrendelen met vingerafdruk**: blokkeren dat een eindgebruiker de vingerafdrukscanner van het apparaat gebruikt om het apparaat te ontgrendelen.
- **Smart Lock en andere trustagenten**: hiermee kunt u de functie Smart Lock beheren op compatibele apparaten. Met deze telefoonmogelijkheid, soms ook wel vertrouwensagent genoemd, kunt u het wachtwoord voor het vergrendelingsscherm op het apparaat uitschakelen of overslaan als het zich op een vertrouwde locatie bevindt (bijvoorbeeld wanneer het is verbonden met een bepaald Bluetooth-apparaat, of wanneer het zich in de buurt van een NFC-tag bevindt). U kunt deze instelling gebruiken om te voorkomen dat gebruikers Smart Lock configureren.

## <a name="system-security"></a>Systeembeveiliging

 - **Bedreigingenscan voor apps**: hiermee kunt u afdwingen dat de instelling **Apps controleren** is ingeschakeld voor zakelijke en privéprofielen.

   > [!Note]  
   > Deze instelling werkt alleen voor apparaten met Android O en later. 

## <a name="next-steps"></a>Volgende stappen

Gebruik de informatie in het onderwerp [Intune- apparaatbeperkingsinstellingen configureren](device-restrictions-configure.md) om het profiel op te slaan en toe te wijzen aan gebruikers en apparaten.
