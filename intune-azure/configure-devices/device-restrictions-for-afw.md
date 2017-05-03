---
title: Intune-apparaatbeperkingsinstellingen voor Android for Work
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp vindt u meer informatie over de Intune-instellingen die u kunt gebruiken voor het beheren van apparaatinstellingen en functionaliteit op apparaten met Android for Work.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1830720b-16cb-4f2f-a71a-62967f882563
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 03fec9d22e705ccb27f4eb1f8f82c7ace95e841e
ms.openlocfilehash: c5cff131e7bcedadbad42fe6ab8bf00017f933ff
ms.lasthandoff: 04/26/2017


---

# <a name="android-for-work-device-restriction-settings-in-microsoft-intune"></a>Android for Work-apparaatbeperkingsinstellingen in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="work-profile-settings"></a>Werkprofielinstellingen
-     **Gegevens delen tussen werkprofiel en persoonlijk profiel**: gebruik deze instelling om te bepalen of apps in het werkprofiel gegevens mogen delen met apps in het persoonlijke profiel. U kunt kiezen uit:
    - **Delen buiten grenzen toestaan**: dit is de standaardinstelling voor het delen van gegevens van het apparaat en deze is afhankelijk van de versie van Android die wordt uitgevoerd. Delen van het persoonlijke profiel naar het werkprofiel is standaard toegestaan. Delen tussen van het werkprofiel naar het persoonlijke profiel is standaard geblokkeerd. Zo voorkomt u het lekken van gegevens van het werkprofiel naar het persoonlijke profiel. Google biedt geen een manier om gegevens te blokkeren van het persoonlijke profiel naar het werkprofiel op apparaten met eerdere versies dan 6.0.  
    - **Met de apps in het werkprofiel kunnen aanvragen voor het delen van het persoonlijke profiel worden verwerkt**: gebruik deze optie om de ingebouwde Android-functie in te schakelen waarmee het delen van gegevens vanuit het persoonlijke profiel naar het werkprofiel is toegestaan. Wanneer dit is ingeschakeld, kan een deelverzoek dat is ingediend vanuit een app in het persoonlijke profiel worden gedeeld met apps in het werkprofiel. Dit is de standaardinstelling voor Android-apparaten met een eerdere versie dan 6.0.
    - **Met de apps in het persoonlijke profiel kunnen aanvragen voor het delen van het werkprofiel worden verwerkt**: hiermee kunt u gegevens delen buiten de grenzen van het werkprofiel, in beide richtingen. Wanneer u deze instelling selecteert, kunnen apps met het werkprofiel gegevens delen met onbeheerde apps in het persoonlijke profiel.  Gebruik deze instelling zorgvuldig omdat hiermee beheerde gegevens in het werkprofiel kunnen worden verstuurd naar de onbeheerde zijde van het apparaat.


-     **Werkprofielmeldingen terwijl het apparaat is vergrendeld**: hiermee kunt u bepalen of de apps in het werkprofiel meldingen op het scherm kunnen weergeven wanneer het apparaat is vergrendeld.
-     **Standaardapp-machtigingen**: hiermee stelt u het standaardmachtigingsbeleid in voor alle apps in het werkprofiel. Vanaf Android 6 wordt voor sommige machtigingen voor apps tijdens runtime om goedkeuring gevraagd aan eindgebruikers. Met deze beleidsinstelling kunt u in het werkprofiel bepalen hoe en of gebruikers om machtiging wordt gevraagd voor apps.
U kunt bijvoorbeeld een app naar het werkprofiel pushen waarvoor toegang tot de locatie is vereist. Normaal gesproken wordt dan een pop-up in de app getoond met de vraag of de gebruiker de app toegang tot de locatie wilt geven. De gebruiker kan dit dan toestaan of weigeren. Met dit beleid kunt u beslissen of alle machtigingen automatisch moeten worden toegekend zonder ernaar te vragen, automatisch moeten worden geweigerd zonder ernaar te vragen of dat de eindgebruiker dit mag beslissen. U kunt kiezen uit:
    -     **Standaardwaarde apparaat**
    -     **Vragen**
    -     **Automatisch verlenen**
    -     **Automatisch weigeren**

## <a name="password"></a>Wachtwoord

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
- **Smart Lock en andere trustagenten**: hiermee kunt u de functie Smart Lock beheren op compatibele apparaten. Met deze telefoonfunctie, soms ook wel vertrouwensagent genoemd, kunt u het wachtwoord voor het vergrendelingsscherm op het apparaat uitschakelen of overslaan als het apparaat zich op een vertrouwde locatie bevindt (bijvoorbeeld wanneer het is verbonden met een bepaald Bluetooth-apparaat of wanneer het zich in de buurt van een NFC-tag bevindt.) Met deze instelling kunt u voorkomen dat gebruikers Smart Lock configureren.

## <a name="custom-policy-settings"></a>Aangepaste beleidsinstellingen
Gebruik het **aangepaste Android for Work-configuratiebeleid** van Microsoft Intune om OMA-URI-instellingen te implementeren die kunnen worden gebruikt om de functies op Android for Work-apparaten te beheren. Dit zijn standaardinstellingen die door veel fabrikanten van mobiele apparaten worden gebruikt voor het beheren van apparaatfuncties.

Op deze manier kunt u Android-instellingen implementeren die niet met Intune-beleid kunnen worden geconfigureerd.
Intune biedt momenteel ondersteuning voor een beperkt aantal aangepaste Android-beleidsregels. Zie de voorbeelden in dit onderwerp om na te gaan welk beleid u kunt configureren.

### <a name="general-settings"></a>Algemene instellingen

|Naam van de instelling|Details|
    |----------------|--------------------|
    |**Naam** |Voer een unieke naam in voor het aangepaste Android-beleid, zodat dit gemakkelijk is te herkennen in de Intune-console.|
    |**Beschrijving** |Geef een beschrijving op die een overzicht biedt van het aangepaste Android-beleid, evenals andere relevante informatie die u helpt om het beleid weer te vinden.|

### <a name="oma-uri-settings"></a>OMA-URI-instellingen

  |Naam van de instelling|Details|
  |--------|--------------------|
  |**Naam** |Voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.|
  |**Beschrijving** |Geef een beschrijving op die een overzicht geeft van de instelling en overige relevante informatie die u helpt om de instelling terug te vinden.|
    |**OMA-URI (hoofdlettergevoelig)** |Geef aan voor welke OMA-URI u een instelling wilt opgeven.|
  |**Gegevenstype** |Selecteer het gegevenstype waarin u deze OMA-URI-instelling opgeeft. Kies uit: **tekenreeks, tekenreeks (XML), datum en tijd, geheel getal, drijvende komma** en **booleaanse waarde**.|
  |**Waarde** |Geef de waarde op die moet worden gekoppeld aan de OMA-URI die u eerder hebt opgegeven.|

