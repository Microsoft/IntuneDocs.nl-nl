---
title: MAM-beleidsinstellingen voor iOS | Microsoft Intune
description: Dit onderwerp beschrijft de beleidsinstellingen voor het beheren van mobiele apps voor iOS-apparaten.
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 673ff872-943c-4076-931c-0be90363aea9
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 913008568226621de4824c5bac287e8a65dc6533


---

#  <a name="ios-mobile-app-management-policy-settings"></a>Mobile Application Management-beleidsinstellingen voor iOS
De in dit onderwerp beschreven beleidsinstellingen kunnen worden [geconfigureerd](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) voor een Mobile App Management-beleid (MAM) op het tabblad **Instellingen** in de Azure-portal.

Er zijn twee soorten beleidsinstellingen, namelijk instellingen voor herlocatie van gegevens en instellingen voor toegang. In dit onderwerp verwijst de term *Door beleid beheerde apps* naar apps die zijn geconfigureerd met MAM-beleid.

##  <a name="data-relocation-settings"></a>Instellingen voor herlocatie van gegevens

- **Back-ups van iTunes en iCloud verhinderen**: kies **Ja** om dit uit te schakelen, of **Nee** om toe te staan dat er back-ups worden gemaakt van bedrijfsgegevens uit apps die door beleid worden beheerd.

  Standaardwaarde = **Ja**.

- **Toestaan dat de app gegevens overdraagt naar andere apps**: kies een van de opties om aan te geven welke apps gegevens uit door beleid beheerde apps mogen ontvangen:
  - **Door beleid beheerde apps**: alleen overdracht toestaan naar apps met MAM-beleid.
  - **Alle apps**: overdracht naar alle apps toestaan.
  - **Geen**: geen gegevensoverdracht naar apps toestaan, met inbegrip van andere door beleid beheerde apps.

  Als u deze optie daarnaast instelt op **Door beleid beheerde apps** of **Geen**, wordt de iOS 9-functie waarmee Spotlight Search naar gegevens in apps kan zoeken, geblokkeerd.

  >[!NOTE]
  >Deze instelling heeft geen controle over het gebruik van de functie Openen in op mobiele apparaten. Zie [Gegevensoverdracht beheren tussen iOS-apps met Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md) voor informatie over het beheer van de functie Open in.

  Standaardwaarde = **Door beleid beheerde apps**.

- **Toestaan dat app gegevens van andere apps ontvangt**: geef op via welke apps er gegevens mogen worden overgedragen naar de door beleid beheerde apps:
  -  **Door beleid beheerde apps**: overdracht alleen toestaan vanuit andere door beleid beheerde apps.
  -  **Alle apps**: gegevensoverdracht vanuit alle apps toestaan.
  -  **Geen**: gegevensoverdracht vanuit geen enkele app toestaan.

  Standaardwaarde = **Alle apps**.

- **Opslaan als voorkomen**: kies **Ja** als u het gebruik van de optie Opslaan als wilt uitschakelen in alle apps die dit beleid gebruiken. Selecteer **Nee** als u het gebruik van de optie Opslaan als wilt toestaan.

  Standaardwaarde = **Ja**.

- **Knippen, kopiëren en plakken met andere apps beperken**: geef op wanneer knip-, kopieer- en plakbewerkingen moeten worden beperkt. U kunt kiezen uit:
  -   **Geblokkeerd**: geen knip-, kopieer- en plakbewerkingen toestaan tussen door beleid beheerde apps.
  -   **Door beleid beheerde apps**: knip-, kopieer- en plakbewerkingen alleen toestaan tussen door beleid beheerde apps.
  -   **Door beleid beheerde apps met Plakken in**: knippen en kopiëren toestaan tussen door beleid beheerde apps. Gegevens die uit alle apps zijn geknipt of gekopieerd, mogen in deze app worden geplakt.
  - **Elke app**: er zijn geen beperkingen voor knip-, kopieer- en plakbewerkingen tussen apps.

  Standaardwaarde = **Door beleid beheerde apps met Plakken in**.

- **Webinhoud beperken voor weergave in de Managed Browser**: als deze instelling is ingeschakeld, worden koppelingen in de app geopend in de Managed Browser-app.

  Voor apparaten die niet zijn ingeschreven bij Intune, kunnen de webkoppelingen in door beleid beheerde apps alleen worden geopend in de Managed Browser-app.

  Als u Intune gebruikt voor het beheer van uw apparaten, raadpleegt u [Internettoegang beheren met beheerde-browserbeleid met Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

  Standaardwaarde = **Ja**.

- **App-gegevens versleutelen:** voor apps die zijn gekoppeld aan een Intune MAM-beleid, worden gegevens in rust versleuteld met behulp van versleuteling op apparaatniveau die wordt geleverd door het besturingssysteem. Als een pincode is vereist, worden de gegevens versleuteld volgens de instellingen in het MAM-beleid. Zoals vermeld in de Apple-documentatie [zijn de modules die worden gebruikt door iOS 7 gecertificeerd volgens FIPS 140-2](http://support.apple.com/en-us/HT202739).

  U kunt versleutelingswaarden voor pincodes opgeven in de beleidsinstellingen. Deze waarden bepalen wanneer de gegevens worden versleuteld. U kunt kiezen uit de volgende opties:
  -   **Wanneer apparaat is vergrendeld:** alle app-gegevens die aan dit beleid zijn gekoppeld, worden versleuteld terwijl het apparaat is vergrendeld.
  -   **Wanneer apparaat is vergrendeld (behalve voor open bestanden):** alle app-gegevens die aan dit beleid zijn gekoppeld, worden versleuteld wanneer het apparaat is vergrendeld, met uitzondering van gegevens in de bestanden die momenteel in de app zijn geopend.
  -   **Na opnieuw opstarten van apparaat:** alle app-gegevens die aan dit beleid zijn gekoppeld, worden versleuteld wanneer het apparaat opnieuw wordt opgestart, totdat het apparaat voor de eerste keer wordt ontgrendeld.
  -   **Apparaatinstellingen gebruiken:** app-gegevens worden versleuteld op basis van de standaardinstellingen op het apparaat.
  Wanneer u deze instelling inschakelt, moet de gebruiker een pincode instellen en gebruiken voor toegang tot het apparaat.  Als er geen pincode wordt ingesteld, worden de apps niet geopend en wordt de gebruiker gevraagd om een pincode in te stellen. Dit gebeurt met het bericht 'Uw bedrijf heeft ingesteld dat u eerst een pincode voor het apparaat moet inschakelen voor u toegang tot deze toepassing kunt krijgen.'.

  Standaardwaarde = Versleutelingsoptie is niet geselecteerd.
- **Synchronisatie van contactpersonen uitschakelen:** kies **Ja** om te voorkomen dat contactgegevens worden gesynchroniseerd met de systeemeigen adresboek-app op het apparaat. Als u **Nee** selecteert, slaat de app de contactgegevens op in de systeemeigen adresboek-app op het apparaat.

  Wanneer u selectief wist om bedrijfsgegevens te verwijderen, worden de contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, ook verwijderd. Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. Dit is momenteel alleen van toepassing op de Microsoft Outlook-app.

  Standaardwaarde = **Ja**.

- **Afdrukken uitschakelen:** kies **Ja** als u wilt voorkomen dat bedrijfsgegevens worden afgedrukt met apps waarop het MAM-beleid van toepassing is.

    Standaardwaarde = **Ja**.

##  <a name="access-settings"></a>Toegangsinstellingen

- **Pincode vereisen voor toegang:** kies **Ja** om een pincode te vereisen voor het gebruik van apps die door beleid worden beheerd. De eerste keer dat de gebruiker de app uitvoert, wordt gevraagd om dit in te stellen.

  Standaardwaarde = **Ja**.
    -  **Eenvoudige pincode toestaan:** hier kunt u opgeven of gebruikers eenvoudige pincodes mogen gebruiken, zoals 1234 of 1111. Standaardwaarde = **Ja**.
    - **Lengte van de pincode:** geef het minimale aantal cijfers op waaruit een pincode moet bestaan. Standaardwaarde = **4**.
    - **Aantal pogingen voordat pincode opnieuw wordt ingesteld**: geef het aantal toegestane invoerpogingen voor de pincode op voordat de gebruiker de pincode opnieuw moet instellen. Er is geen standaardwaarde voor deze instelling.

- **Vingerafdruk in plaats van pincode vereisen (iOS 8.0+)**: selecteer **Ja** als u een vingerafdruk-id in plaats van een pincode wilt vereisen voor toegang tot apps.
Op iOS-apparaten kunt u gebruikers zich laten identificeren met hun vingerafdruk in plaats van met een pincode. Wanneer gebruikers deze app proberen te openen via hun werkaccount, moeten ze hun vingerafdruk in plaats van een pincode gebruiken.

  Standaardwaarde = **Ja**.
- **Bedrijfsreferenties vereisen voor toegang**: selecteer **Ja** als u de bedrijfsreferenties in plaats van een pincode wilt vereisen voor toegang tot apps. Als u deze waarde op **Ja** instelt, overschrijft dit de vereisten voor de pincode of Touch-ID. De gebruiker wordt gevraagd om zijn zakelijke referenties te verstrekken.

  Standaardwaarde = **Nee**.
- **De uitvoering blokkeren van beheerde apps die op gekraakte of geroote apparaten worden uitgevoerd**: selecteer **Ja** om te voorkomen dat apps worden uitgevoerd op gekraakte of geroote apparaten. De gebruiker kan de apps nog steeds gebruiken voor privétaken maar moet voor zijn werk een ander apparaat gebruiken.

  Standaardwaarde = **Ja**.
- **Toegangsvereisten opnieuw controleren na (minuten)**
  -   **Time-out**: geef de periode (in minuten) op waarna de toegangsvereisten voor de app opnieuw worden gecontroleerd.
  -   **Offline respijtperiode**: als het apparaat offline is, geeft u de periode (in minuten) op waarna de toegangsvereisten voor de app opnieuw worden gecontroleerd.

  Standaardwaarden = time-outperiode van **30** minuten en offline respijtperiode van **720** minuten.
- **Offline interval (in dagen) voordat app-gegevens worden gewist**: u kunt ervoor kiezen de bedrijfsgegevens te wissen wanneer een apparaat gedurende een bepaalde periode offline is geweest. Geef het aantal dagen op dat een apparaat offline mag zijn voordat de bedrijfsgegevens van het apparaat worden verwijderd.

  >[!TIP]
  >Voer een waarde van **0** in om deze instelling uit te schakelen.

  Standaardwaarde = **90** dagen.



<!--HONumber=Oct16_HO5-->


