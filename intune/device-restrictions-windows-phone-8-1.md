---
title: Microsoft Intune-apparaatbeperkingsinstellingen voor Windows Phone 8.1
titleSuffix: ''
description: Meer informatie over de Intune-instellingen die u kunt gebruiken voor het beheren van apparaatinstellingen en functionaliteit op apparaten met Windows Phone 8.1.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 343b15e13a944cb519451a14c299d66444b17569
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57230360"
---
# <a name="microsoft-intune-windows-phone-81-device-restriction-settings"></a>Microsoft Intune Windows Phone 8.1-apparaatbeperkingsinstellingen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel komt u meer te weten over de Microsoft Intune-apparaatbeperkingsinstellingen die u kunt configureren voor apparaten met Windows Phone 8.1.


## <a name="general"></a>Algemeen

-   **Camera**: hiermee kunt u het gebruik van de camera van het apparaat inschakelen of blokkeren.
-   **Kopiëren en plakken**: hiermee kunt u de functie voor kopiëren en plakken op apparaten inschakelen of blokkeren.
-   **Verwisselbare opslag**: hiermee stelt u het apparaat in staat verwisselbare opslag te gebruiken, zoals SD-kaarten.
-   **Geolocatie**: hiermee stelt u het apparaat in staat locatiegegevens te gebruiken.
-   **Microsoft-account**: hiermee kunt u toestaan of voorkomen dat de gebruiker een Microsoft-account aan het apparaat kan koppelen.
-   **Schermafbeelding**: hiermee staat u de gebruiker toe de inhoud van het scherm vast te leggen als afbeelding.
-   **Verzending van diagnostische gegevens**: hiermee stelt u het apparaat in staat diagnostische gegevens naar Microsoft te verzenden.
-   **Aangepaste e-mailaccounts synchroniseren**: hiermee stelt u het apparaat in staat verbinding te maken met niet-Microsoft-e-mailaccounts.

## <a name="password"></a>Wachtwoord

-   **Wachtwoord**: hiermee geeft u aan dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat.
    -   **Vereist wachtwoordtype**: hiermee geeft u het wachtwoordtype op dat is vereist, zoals alfanumeriek of alleen numeriek.
    -   **Minimale wachtwoordlengte**: hiermee geeft u het minimum aantal tekens op waaruit het wachtwoord moet bestaan.
    -   **Eenvoudige wachtwoorden**: hiermee geeft u op dat eenvoudige wachtwoorden, zoals 0000 en 1234, kunnen worden gebruikt.
    -   **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: hiermee geeft u op hoe vaak een onjuist wachtwoord kan worden ingevoerd voordat het apparaat wordt gewist.
    -   **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: hiermee geeft u op hoeveelheid tijd een apparaat inactief moet zijn voordat het scherm wordt vergrendeld.
    -   **Wachtwoord verloopt (dagen)**: hiermee geeft u het aantal dagen op voordat het wachtwoord voor het apparaat moet worden gewijzigd.
    -   **Wachtwoorden niet opnieuw gebruiken**: hiermee geeft u op hoeveel eerder gebruikte wachtwoorden worden onthouden.
-   **Versleuteling**: hiermee vereist u dat de gegevens op ondersteunde mobiele apparaten worden versleuteld.

## <a name="app-store"></a>App Store

-   **App Store**: hiermee stelt u gebruikers in staat verbinding te maken met de App Store van het apparaat.

## <a name="restricted-apps"></a>Beperkte apps

Configureer een van de volgende lijsten in de lijst met beperkte apps:

Lijst met **geblokkeerde apps**: hiermee maakt u een lijst met apps die niet worden beheerd door Intune en die gebruikers niet mogen installeren en uitvoeren.
Lijst met **toegestane apps**: hiermee maakt u een lijst met apps die gebruikers mogen installeren. Apps die worden beheerd door Intune, zijn automatisch toegestaan.

Als u de lijst wilt configureren, klikt u op **Toevoegen** en geeft u een naam van uw keuze op, eventueel de uitgever van de app, en de URL van de app in de App Store.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>De URL naar een app in de Store opgeven

Als u een app-URL wilt opgeven in de lijst met toegestane en geblokkeerde apps, gebruikt u de volgende notatie:

Zoek op de pagina [Windows Phone Store](https://www.microsoft.com/store/apps/windows-phone) naar de app die u wilt gebruiken.

Open de pagina van de app en kopieer de URL naar het klembord. U kunt deze URL nu gebruiken in de lijst met toegestane apps of de lijst met geblokkeerde apps.

Voorbeeld: Zoek in de store naar de Skype-app. De URL die u gebruikt, is `http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51`.



### <a name="additional-options"></a>Extra opties

U kunt ook op **Importeren** klikken om de lijst te vullen met waarden uit een CSV-bestand in de indeling <*app-URL*>, <*app-naam*>, <app publisher>, of klik op **Exporteren** om een CSV-bestand (met dezelfde indeling) te maken met de inhoud van de lijst met beperkte apps.


## <a name="browser"></a>Browser

-   **Webbrowser**: hiermee kunt u het gebruik van de ingebouwde webbrowser op apparaten toestaan of blokkeren.

## <a name="cellular-and-connectivity"></a>Mobiel en connectiviteit

-   **Wi-Fi**: hiermee schakelt u de Wi-Fi-functionaliteit van het apparaat in of uit.
-   **Wi-Fi-tethering**: hiermee schakelt u het gebruik van Wi-Fi-tethering op het apparaat in.
-   **Automatisch verbinding maken met Wi-Fi-hotspots**: hiermee stelt u het apparaat in staat automatisch verbinding te maken met gratis Wi-Fi-hotspots en automatisch alle gebruiksvoorwaarden te accepteren.
-   **Wi-Fi-hotspots melden**: hiermee wordt informatie over Wi-Fi-verbindingen verzonden om de gebruiker te helpen verbindingen in de buurt te detecteren.
-   **NFC**: hiermee schakelt u de bewerkingen in of uit waarvoor Near Field Communication wordt gebruikt op apparaten die deze ondersteunen.
-   **Bluetooth**: hiermee schakelt u de Bluetooth-functionaliteit van het apparaat in of uit.
