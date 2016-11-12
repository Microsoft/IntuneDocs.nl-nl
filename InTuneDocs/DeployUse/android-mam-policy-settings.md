---
title: MAM-beleidsinstellingen voor Android | Microsoft Intune
description: In dit onderwerp worden de beleidsinstellingen voor het beheren van mobiele apps voor Adroid-apparaten beschreven.
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5dbb702a-1df5-4637-95c9-77a5f0b1a0e3
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e5e41cbbf3bac3ed78ee3a6929e364f829fa1d4b
ms.openlocfilehash: f8a25815662333fd48d7ea9df24f5f228cee8217


---

# Mobile App Management-beleidsinstellingen voor Android in Microsoft Intune
De in dit onderwerp beschreven beleidsinstellingen kunnen worden [geconfigureerd](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) voor een Mobile App Management-beleid (MAM) op het tabblad **Instellingen** in de Azure-portal.
Er zijn twee soorten beleidsinstellingen, namelijk instellingen voor herlocatie van gegevens en instellingen voor toegang. In dit onderwerp verwijst de term *Door beleid beheerde apps* naar apps die zijn geconfigureerd met MAM-beleid.

##  Instellingen voor herlocatie van gegevens

- **Back-ups van Android verhinderen**: kies **Ja** om dit uit te schakelen, of **Nee** om toe te staan dat er back-ups worden gemaakt van bedrijfsgegevens uit door beleid beheerde apps.

  Standaardwaarde = **Ja**.
- **Toestaan dat app gegevens overdraagt naar andere apps**: kies een van de opties om aan te geven welke apps bedrijfsgegevens uit door beleid beheerde apps mogen ontvangen:
  -   **Door beleid beheerde apps**: alleen overdracht toestaan naar apps met MAM-beleid.
  -   **Alle apps**: overdracht naar alle apps toestaan.
  -   **Geen**: geen gegevensoverdracht naar apps toestaan.

  Standaardwaarde = **Door beleid beheerde apps**.
- **Toestaan dat app gegevens van andere apps ontvangt**: geef op via welke apps er gegevens mogen worden overgedragen naar de door beleid beheerde apps:
  -   **Door beleid beheerde apps**: overdracht alleen toestaan vanuit andere door beleid beheerde apps.
  -   **Alle apps**: gegevensoverdracht vanuit alle apps toestaan.
  -   **Geen**: gegevensoverdracht vanuit geen enkele app toestaan.

  Standaardwaarde = **Alle apps**.

-   **Opslaan als voorkomen**: kies **Ja** als u het gebruik van de optie Opslaan als wilt uitschakelen in alle apps die dit beleid gebruiken. Selecteer **Nee** als u het gebruik van de optie Opslaan als wilt toestaan.

  Standaardwaarde = **Ja**.
- **Knippen, kopiëren en plakken met andere apps beperken**: geef op wanneer knip-, kopieer- en plakbewerkingen moeten worden beperkt. U kunt kiezen uit:
  -   **Geblokkeerd**: geen knip-, kopieer- en plakbewerkingen toestaan tussen door beleid beheerde apps.
  -   **Door beleid beheerde apps**: knip-, kopieer- en plakbewerkingen alleen toestaan tussen door beleid beheerde apps.
  -   **Door beleid beheerde apps met Plakken in**: knippen en kopiëren toestaan tussen door beleid beheerde apps. Gegevens die uit alle apps zijn geknipt of gekopieerd, mogen in deze app worden geplakt.
  -   **Elke app**: er zijn geen beperkingen voor knip-, kopieer- en plakbewerkingen tussen apps.

  Standaardwaarde = **Door beleid beheerde apps met Plakken in**.
-   **Webinhoud beperken voor weergave in de Managed Browser**: als deze instelling is ingeschakeld, worden koppelingen in de app geopend in de Managed Browser-app.

  Voor apparaten die niet zijn ingeschreven bij Intune, worden webkoppelingen in door beleid beheerde apps alleen geopend in de Managed Browser-app met behulp van het MAM-beleid.

  Als u Intune gebruikt voor het beheer van uw apparaten, raadpleegt u [Internettoegang beheren met beheerde-browserbeleid met Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

  Standaardwaarde = **Ja**.
- **App-gegevens versleutelen**: selecteer **Ja** om versleuteling in te schakelen. Als deze instelling is ingeschakeld, wordt de versleuteling van apps die aan een MAM-beleid zijn gekoppeld, geleverd door Microsoft. Gegevens worden synchroon versleuteld tijdens I/O-taken voor bestanden. Inhoud van de apparaatopslag wordt altijd versleuteld.
  >[!NOTE]
  >De versleutelingsmethode is niet gecertificeerd volgens FIPS 140-2.

  Standaardwaarde = **Ja**.

- **Synchronisatie van contactpersonen uitschakelen:** kies **Ja** om te voorkomen dat contactgegevens worden gesynchroniseerd met de systeemeigen adresboek-app op het apparaat. Als u **Nee** selecteert, slaat de app de contactgegevens op in de systeemeigen adresboek-app op het apparaat.

  Wanneer u selectief wist om bedrijfsgegevens te verwijderen, worden de contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, ook verwijderd. Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. Dit is momenteel alleen van toepassing op de Microsoft Outlook-app.

  Standaardwaarde = **Ja**.
- **Afdrukken uitschakelen:** kies **Ja** als u wilt voorkomen dat bedrijfsgegevens worden afgedrukt met apps waarop het MAM-beleid van toepassing is.

  Standaardwaarde = **Ja**.

##  Toegangsinstellingen

- **Pincode vereisen voor toegang:** kies **Ja** om een pincode te vereisen voor het gebruik van apps die door beleid worden beheerd. De eerste keer dat de gebruiker de app uitvoert, wordt gevraagd om dit in te stellen.

 Standaardwaarde = **Ja**.

 -  **Eenvoudige pincode toestaan:** hier kunt u opgeven of gebruikers eenvoudige pincodes mogen gebruiken, zoals 1234 of 1111. Standaardwaarde = **Ja**.
 - **Lengte van de pincode:** geef het minimale aantal cijfers op waaruit een pincode moet bestaan. Standaardwaarde = **4**.
 - **Aantal pogingen voordat pincode opnieuw wordt ingesteld**: geef het aantal toegestane invoerpogingen voor de pincode op voordat de gebruiker de pincode opnieuw moet instellen. Er is geen standaardwaarde voor deze instelling.
- **Bedrijfsreferenties vereisen voor toegang**: selecteer **Ja** als u de bedrijfsreferenties in plaats van een pincode wilt vereisen voor toegang tot apps. Als u deze waarde op **Ja** instelt, overschrijft dit de vereisten voor de pincode of Touch-ID. De gebruiker wordt gevraagd om zijn zakelijke referenties te verstrekken.

  Standaardwaarde = **Nee**.
- **De uitvoering blokkeren van beheerde apps die op gekraakte of geroote apparaten worden uitgevoerd**: selecteer **Ja** om te voorkomen dat apps worden uitgevoerd op gekraakte of geroote apparaten. De gebruiker kan de apps nog steeds gebruiken voor privétaken maar moet voor zijn werk een ander apparaat gebruiken.

  Standaardwaarde = **Ja**.
- **Toegangsvereisten opnieuw controleren na (minuten)**
  -   **Time-out**: geef de periode (in minuten) op waarna de toegangsvereisten voor de app opnieuw worden gecontroleerd.
  -   **Offline respijtperiode**: als het apparaat offline is, geeft u de periode (in minuten) op waarna de toegangsvereisten voor de app opnieuw worden gecontroleerd.

  Standaardwaarden = time-outperiode van **30** minuten en offline respijtperiode van **720** minuten.

-   **Offline interval (in dagen) voordat app-gegevens worden gewist**: u kunt ervoor kiezen de bedrijfsgegevens te wissen wanneer een apparaat gedurende een bepaalde periode offline is geweest.  Geef het aantal dagen op dat een apparaat offline mag zijn voordat de bedrijfsgegevens van het apparaat worden verwijderd.

    >[!TIP]
    >Voer een waarde van **0** in om deze instelling uit te schakelen.

  Standaardwaarde = **90** dagen.
- **Schermopname en Android-assistent blokkeren (Android 6 Marshmallow of hoger**: selecteer **Ja** om schermopnamen en functies van de **Android-assistent** op het apparaat te blokkeren wanneer deze app wordt gebruikt.



<!--HONumber=Oct16_HO3-->


