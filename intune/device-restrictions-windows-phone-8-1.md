---
title: Intune-apparaatbeperkingsinstellingen voor Windows Phone 8.1
titleSuffix: Intune on Azure
description: Meer informatie over de Intune-instellingen die u kunt gebruiken voor het beheren van apparaatinstellingen en functionaliteit op Windows Phone 8.1-apparaten.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d42714-49ca-43b3-b080-2e67a4268198
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e425b8a3c93c2f5dc73fbe9c75aa9adf49c5cdc8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="windows-phone-81-device-restriction-settings-in-microsoft-intune"></a>Windows Phone 8.1-apparaatbeperkingsinstellingen in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>Algemeen
-   **Alle instellingen alleen op Windows Phone 8.1 toepassen**: dit is een instelling die u in de klassieke Intune-portal kunt configureren. In Azure Portal kan deze instelling niet worden gewijzigd. Als de instelling is ingesteld op **Geconfigureerd**, zijn de instellingen alleen van toepassing op Windows Phone 8.1-apparaten. Als de instelling is ingesteld op **Niet geconfigureerd**, gelden deze instellingen ook voor Windows 10 Mobile-apparaten.
-   **Camera**: hiermee kunt u het gebruik van de camera van het apparaat inschakelen of blokkeren.
-   **Kopiëren en plakken**: hiermee kunt u de functie voor kopiëren en plakken op apparaten inschakelen of blokkeren.
-   **Verwisselbare opslag**: hiermee stelt u het apparaat in staat verwisselbare opslag te gebruiken, zoals SD-kaarten.
-   **Geolocatie**: hiermee stelt u het apparaat in staat locatiegegevens te gebruiken.
-   **Microsoft-account**: hiermee kunt u toestaan of voorkomen dat de gebruiker een Microsoft-account aan het apparaat kan koppelen.
-   **Schermafbeelding**: hiermee staat u de gebruiker toe de inhoud van het scherm vast te leggen als afbeelding.
-   **Verzending van diagnostische gegevens**: hiermee stelt u het apparaat in staat diagnostische gegevens naar Microsoft te verzenden.
-   **Aangepaste e-mailaccounts synchroniseren**: hiermee stelt u het apparaat in staat verbinding te maken met niet-Microsoft-e-mailaccounts.

## <a name="password"></a>Wachtwoord
-   **Alle instellingen alleen op Windows Phone 8.1 toepassen**: dit is een instelling die u in de klassieke Intune-portal kunt configureren. In Azure Portal kan deze instelling niet worden gewijzigd. Als de instelling is ingesteld op **Geconfigureerd**, zijn de instellingen alleen van toepassing op Windows Phone 8.1-apparaten. Als de instelling is ingesteld op **Niet geconfigureerd**, gelden deze instellingen ook voor Windows 10 Mobile-apparaten.
-   **Wachtwoord vereist**: hiermee geeft u aan dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat.
    -   **Vereist wachtwoordtype**: hiermee geeft u het wachtwoordtype op dat is vereist, zoals alfanumeriek of alleen numeriek.
    -   **Minimale wachtwoordlengte**: hiermee geeft u het minimum aantal tekens op waaruit het wachtwoord moet bestaan.
    -   **Eenvoudige wachtwoorden**: hiermee geeft u op dat eenvoudige wachtwoorden, zoals 0000 en 1234, kunnen worden gebruikt.
    -   **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: hiermee geeft u op hoe vaak een onjuist wachtwoord kan worden ingevoerd voordat het apparaat wordt gewist.
    -   **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: hiermee geeft u op hoeveelheid tijd een apparaat inactief moet zijn voordat het scherm wordt vergrendeld.
    -   **Wachtwoord verloopt (dagen)**: hiermee geeft u het aantal dagen op voordat het wachtwoord voor het apparaat moet worden gewijzigd.
    -   **Wachtwoorden niet opnieuw gebruiken**: hiermee geeft u op hoeveel eerder gebruikte wachtwoorden worden onthouden.
-   **Versleuteling**: hiermee vereist u dat de gegevens op ondersteunde mobiele apparaten worden versleuteld.

## <a name="app-store"></a>App Store
-   **Alle instellingen alleen op Windows Phone 8.1 toepassen**: dit is een instelling die u in de klassieke Intune-portal kunt configureren. In Azure Portal kan deze instelling niet worden gewijzigd. Als de instelling is ingesteld op **Geconfigureerd**, zijn de instellingen alleen van toepassing op Windows Phone 8.1-apparaten. Als de instelling is ingesteld op **Niet geconfigureerd**, gelden deze instellingen ook voor Windows 10 Mobile-apparaten.
-   **App Store**: hiermee stelt u gebruikers in staat verbinding te maken met de App Store van het apparaat.

## <a name="restricted-apps"></a>Beperkte apps

-   **Alle instellingen alleen op Windows Phone 8.1 toepassen**: dit is een instelling die u in de klassieke Intune-portal kunt configureren. In Azure Portal kan deze instelling niet worden gewijzigd. Als de instelling is ingesteld op **Geconfigureerd**, zijn de instellingen alleen van toepassing op Windows Phone 8.1-apparaten. Als de instelling is ingesteld op **Niet geconfigureerd**, gelden deze instellingen ook voor Windows 10 Mobile-apparaten.

Configureer een van de volgende lijsten in de lijst met beperkte apps:

Lijst met **geblokkeerde apps**: hiermee maakt u een lijst met apps die niet worden beheerd door Intune en die gebruikers niet mogen installeren en uitvoeren.
Lijst met **toegestane apps**: hiermee maakt u een lijst met apps die gebruikers mogen installeren. Apps die worden beheerd door Intune, zijn automatisch toegestaan.

Als u de lijst wilt configureren, klikt u op **Toevoegen** en geeft u een naam van uw keuze op, eventueel de uitgever van de app, en de URL van de app in de App Store.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>De URL naar een app in de Store opgeven

Als u een app-URL wilt opgeven in de lijst met toegestane en geblokkeerde apps, gebruikt u de volgende notatie:

Zoek op de pagina [Windows Phone Store](https://www.microsoft.com/store/apps/windows-phone) naar de app die u wilt gebruiken.

Open de pagina van de app en kopieer de URL naar het klembord. U kunt deze URL nu gebruiken in de lijst met toegestane apps of de lijst met geblokkeerde apps.

Voorbeeld: zoek in de Store naar de Skype-app. De URL die u gebruikt, is **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.



### <a name="additional-options"></a>Extra opties

U kunt ook op **Importeren** klikken om de lijst te vullen met waarden uit een CSV-bestand in de indeling <*app-URL*>, <*app-naam*>, <*app-uitgever*>. Of klik op **Exporteren** om een CSV-bestand (met dezelfde indeling) te maken met de inhoud van de lijst met beperkte apps.


## <a name="browser"></a>Browser
-   **Alle instellingen alleen op Windows Phone 8.1 toepassen**: dit is een instelling die u in de klassieke Intune-portal kunt configureren. In Azure Portal kan deze instelling niet worden gewijzigd. Als de instelling is ingesteld op **Geconfigureerd**, zijn de instellingen alleen van toepassing op Windows Phone 8.1-apparaten. Als de instelling is ingesteld op **Niet geconfigureerd**, gelden deze instellingen ook voor Windows 10 Mobile-apparaten.
-   **Webbrowser**: hiermee kunt u het gebruik van de ingebouwde webbrowser op apparaten toestaan of blokkeren.

## <a name="cellular-and-connectivity"></a>Mobiel en connectiviteit
-   **Alle instellingen alleen op Windows Phone 8.1 toepassen**: dit is een instelling die u in de klassieke Intune-portal kunt configureren. In Azure Portal kan deze instelling niet worden gewijzigd. Als de instelling is ingesteld op **Geconfigureerd**, zijn de instellingen alleen van toepassing op Windows Phone 8.1-apparaten. Als de instelling is ingesteld op **Niet geconfigureerd**, gelden deze instellingen ook voor Windows 10 Mobile-apparaten.
-   **Wi-Fi**: hiermee schakelt u de Wi-Fi-functionaliteit van het apparaat in of uit.
-   **Wi-Fi-tethering**: hiermee schakelt u het gebruik van Wi-Fi-tethering op het apparaat in.
-   **Automatisch verbinding maken met Wi-Fi-hotspots**: hiermee stelt u het apparaat in staat automatisch verbinding te maken met gratis Wi-Fi-hotspots en automatisch alle gebruiksvoorwaarden te accepteren.
-   **Wi-Fi-hotspots melden**: hiermee wordt informatie over Wi-Fi-verbindingen verzonden om de gebruiker te helpen verbindingen in de buurt te detecteren.
-   **NFC**: hiermee schakelt u de bewerkingen in of uit waarvoor Near Field Communication wordt gebruikt op apparaten die deze ondersteunen.
-   **Bluetooth**: hiermee schakelt u de Bluetooth-functionaliteit van het apparaat in of uit.
