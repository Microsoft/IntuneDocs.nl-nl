---
# required metadata

title: MAM-beleidsinstellingen voor Android | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 5dbb702a-1df5-4637-95c9-77a5f0b1a0e3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Mobile App Management-beleidsinstellingen voor Android in Microsoft Intune
De hieronder beschreven beleidsinstellingen kunnen worden [geconfigureerd](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) voor een MAM-beleid op het tabblad **Instellingen** in de Azure-portal.
Er zijn twee soorten beleidsinstellingen: Herlocatie van gegevens en Toegang:

##  Instellingen voor herlocatie van gegevens
De term **Door beleid beheerde apps** wordt gebruikt om te verwijzen naar apps die zijn geconfigureerd met MAM-beleid.
- **Back-ups van Android verhinderen**: kies **Ja** om dit uit te schakelen, of **Nee** om toe te staan dat er back-ups worden gemaakt van bedrijfsgegevens uit door beleid beheerde apps.

  **Standaardwaarde = Ja**
- **Toestaan dat app gegevens overdraagt naar andere apps**: selecteer één van de opties om aan te geven welke apps bedrijfsgegevens uit door beleid beheerde apps mogen ontvangen:
  -   **Door beleid beheerde apps**: overdracht alleen toestaan naar apps met MAM-beleid
  -   **Alle apps**: overdracht naar alle apps toestaan
  -   **Geen**: geen gegevensoverdracht naar apps toestaan

  **Standaardwaarde = Door beleid beheerde apps**
- **Toestaan dat app gegevens van andere apps ontvangt**: geef op via welke apps gegevens mogen worden overgedragen naar de door beleid beheerde apps:
  -   **Door beleid beheerde apps**: overdracht alleen toestaan vanuit andere door beleid beheerde apps
  -   **Alle apps**: gegevensoverdracht vanuit alle apps toestaan
  -   **Geen**: gegevensoverdracht vanuit geen enkele app toestaan

      **Standaardwaarde = Alle apps**

-   **Opslaan als voorkomen**: selecteer **Ja** als u het gebruik van de optie Opslaan als wilt uitschakelen in alle apps die dit beleid gebruiken. Selecteer **Nee** als u het gebruik van de optie Opslaan als wilt toestaan.

  **Standaardwaarde = Ja**
- **Knippen, kopiëren en plakken met andere apps beperken**: geef op wanneer knip-, kopieer- en plakbewerkingen moeten worden beperkt. U kunt kiezen uit:
  -   **Geblokkeerd**: geen knip-, kopieer- en plakbewerkingen toestaan tussen door beleid beheerde apps.
  -   **Door beleid beheerde apps**: knip-, kopieer- en plakbewerkingen alleen toestaan tussen door beleid beheerde apps.
  -   **Door beleid beheerde apps met Plakken in**: knippen en kopiëren toestaan tussen door beleid beheerde apps. Gegevens die uit alle apps zijn geknipt of gekopieerd, mogen in deze app worden geplakt.
  -   **Elke app**: geen beperkingen voor knip-, kopieer- en plakbewerkingen tussen apps.

    **Standaardwaarde = Door beleid beheerde apps met Plakken in**
-   **Webinhoud beperken voor weergave in de Managed Browser**: als deze instelling is ingeschakeld, worden koppelingen in de app geopend in de Managed Browser.

  Voor apparaten die niet zijn ingeschreven bij Intune, worden webkoppelingen in door beleid beheerde apps alleen geopend in de Managed Browser-app, op basis van het MAM-beleid.

  Als u Intune gebruikt voor het beheer van uw apparaten, raadpleegt u [Internettoegang beheren met beheerde-browserbeleid met Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

    **Standaardwaarde = Ja**
- **App-gegevens versleutelen**: selecteer **Ja** om versleuteling in te schakelen. Als deze instelling is ingeschakeld, wordt de versleuteling van apps die zijn gekoppeld aan een Mobile Application Management-beleid, geleverd door Microsoft. Gegevens worden synchroon versleuteld tijdens de I/O-bewerkingen voor bestanden. Inhoud van de apparaatopslag wordt altijd versleuteld.

  **Standaardwaarde = Ja**

- **ContactSyncDisabled**: selecteer **Ja** om te voorkomen dat contactgegevens worden gesynchroniseerd met de systeemeigen adresboek-app op het apparaat. Als u **Nee** selecteert, slaat de app de contactgegevens op in de systeemeigen adresboek-app op het apparaat.<br/>Wanneer u selectief wist om bedrijfsgegevens te verwijderen, worden de contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, ook verwijderd. Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron kunnen niet worden gewist. Dit is momenteel alleen van toepassing op de **Microsoft Outlook**-app.

  **Standaardwaarde = Ja**

##  Beleidsinstellingen voor Android-toegang
De term **Door beleid beheerde apps** wordt gebruikt om te verwijzen naar apps die zijn geconfigureerd met MAM-beleid

- **Eenvoudige pincode vereisen voor toegang**: selecteer **Ja** om een pincode te vereisen voor het gebruik van door beleid beheerde apps. De eerste keer dat de gebruiker de app uitvoert, wordt gevraagd om dit in te stellen.

 **Standaardwaarde = Ja**
- **Aantal pogingen voordat pincode opnieuw wordt ingesteld**: geef het aantal toegestane invoerpogingen voor de pincode op voordat de gebruiker de pincode opnieuw moet instellen.

 **Er is geen standaardwaarde voor deze instelling.**
- **Bedrijfsreferenties vereisen voor toegang**: selecteer **Ja** als u de bedrijfsreferenties in plaats van een pincode wilt vereisen voor toegang tot apps.  Als u deze waarde op **Ja** instelt, overschrijft dit de vereisten voor de pincode of Touch-ID.  De gebruiker wordt gevraagd om zijn zakelijke referenties te verstrekken.

  **Standaardwaarde = Nee**
- **De uitvoering blokkeren van beheerde apps die op gekraakte of geroote apparaten worden uitgevoerd**: selecteer **Ja** om te voorkomen dat apps worden uitgevoerd op gekraakte of geroote apparaten. De gebruiker kan de apps nog steeds gebruiken voor privétaken maar moet voor zijn werk een ander apparaat gebruiken.

  **Standaardwaarde = Ja**
- **Toegangsvereisten opnieuw controleren na (minuten)**-   **Time-out:** periode (in minuten) waarna de toegangsvereisten voor de app opnieuw worden gecontroleerd.
  -   **Offline respijtperiode**: als het apparaat offline is, geeft u de periode (in minuten) op waarna de toegangsvereisten voor de app opnieuw worden gecontroleerd.

    **Standaardwaarden = time-outperiode van 30 minuten en offline respijtperiode van 720 minuten**

-   **Offline interval (in dagen) voordat app-gegevens worden gewist**: u kunt ervoor kiezen de bedrijfsgegevens te wissen wanneer een apparaat gedurende een bepaalde periode offline is geweest.  Geef het aantal dagen op dat een apparaat offline mag zijn voordat de bedrijfsgegevens van het apparaat worden verwijderd. **Tip**: als u een waarde van 0 invoert, wordt deze instelling uitgeschakeld.

  **Standaardwaarde = 90 dagen**
- **Schermopname en Android-assistent blokkeren (Android 6 Marshmallow of hoger**: selecteer **Ja** om schermopnamen en functies van de **Android-assistent** op het apparaat te blokkeren wanneer deze app wordt gebruikt.


<!--HONumber=May16_HO1-->


