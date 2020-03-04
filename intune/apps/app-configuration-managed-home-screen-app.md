---
title: De app Microsoft Managed Home Screen configureren
titleSuffix: Microsoft Intune
description: Ontdek hoe u de app Microsoft Managed Home Screen kunt configureren.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/27/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 865c7f03-f525-4dfa-b3a8-d088a9106502
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4a9372a67dc0f45e256c3eba9b816db866e23998
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77781805"
---
# <a name="configure-the-microsoft-managed-home-screen-app-for-android-enterprise"></a>De app Microsoft Managed Home Screen voor Android Enterprise configureren

Managed Home Screen is de toepassing die wordt gebruikt voor aan Android Enterprise toegewezen apparaten in bedrijfseigendom die via Intune zijn geregistreerd en worden uitgevoerd in de kioskmodus voor meerdere apps. Voor deze apparaten fungeert Managed Home Screen als startprogramma voor andere goedgekeurde apps die erop worden uitgevoerd. Managed Home Screen biedt IT-beheerders de mogelijkheid om hun apparaten aan te passen en de functionaliteit te beperken waartoe de eindgebruiker toegang heeft. 

## <a name="when-to-configure-the-microsoft-managed-home-screen-app"></a>Wanneer u het beste de app Microsoft Managed Home Screen kunt configureren

Normaal gesproken kunt u, als de instellingen beschikbaar zijn via de apparaatconfiguratie, daar de instellingen configureren. Hiermee bespaart u tijd, worden fouten geminimaliseerd en krijgt u een betere Intune- ondersteuningservaring. Echter enkele van de instellingen van het beheerde beginscherm zijn momenteel alleen beschikbaar via het deelvenster **App-configuratiebeleid** in de Intune-console. Ontdek met behulp van dit document hoe u de verschillende instellingen kunt configureren met Configuration Designer of een JSON-script. 

> [!NOTE]
> Het is momenteel mogelijk, en dit wordt ook aangeraden, om in de whitelist opgenomen toepassingen en vastgemaakte webkoppelingen in te stellen via **Apps** en **Apparaatconfiguratie**. Zie voor een volledige lijst van instellingen die in **Apparaatconfiguratie** beschikbaar zijn en van invloed zijn op Managed Home Screen [Toegewezen apparaatinstellingen](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings).  

Navigeer eerst naar het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) en selecteer **Apps** > **Configuratiebeleid voor apps**. Voeg een configuratiebeleid toe voor **Beheerde apparaten** met **Android** en kies **Managed Home Screen** als bijbehorende app. Klik op **Configuratie-instellingen** om de verschillende beschikbare instellingen voor Managed Home Screen te configureren. 

## <a name="choosing-a-configuration-settings-format"></a>Een indeling voor de configuratie-instellingen kiezen

Er zijn twee methoden waarmee u configuratie-instellingen kunt definiëren voor Managed Home Screen:

- Met **Configuration Designer** kunt u instellingen configureren met een gebruiksvriendelijke gebruikersinterface waarmee u functies in of uit kunt schakelen en waarden kunt instellen. In deze methode zijn er enkele uitgeschakelde configuratiesleutels met waardetype `BundleArray`. Deze configuratiesleutels kunnen alleen worden geconfigureerd door JSON-gegevens in te voeren. 
- Met **JSON-gegevens** kunt u alle mogelijke configuratiesleutels definiëren met een JSON-script. 

Als u eigenschappen toevoegt met de Configuration Designer, kunt u deze eigenschappen automatisch omzetten in JSON door **JSON-gegevens invoeren** te selecteren in de vervolgkeuzelijst **Indeling configuratie-instellingen**.

![Schermopname van de indelingsopties voor configuratie-instellingen](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_01.png)

## <a name="using-configuration-designer"></a>Configuration Designer gebruiken

Met Configuration Designer kunt u vooraf gevulde instellingen en de bijbehorende waarden selecteren. 

![Schermopname van toegevoegde configuratie-instellingen](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_02.png)

De volgende tabel bevat de beschikbare configuratiesleutels, waardetypen, standaardwaarden en beschrijvingen van Managed Home Screen. De beschrijving voorziet in het verwachte apparaatgedrag op basis van de geselecteerde waarden. Configuratiesleutels die zijn uitgeschakeld in Configuration Designer worden niet in de tabel weergegeven.

| Configuratiesleutel | Waardetype | Standaardwaarde | Beschrijving |
|---------------------------------------------------------------------------------------------------------------------------|-------------|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| De rastergrootte instellen | string | Automatisch | Hiermee kunt u de rastergrootte instellen voor apps die op het beheerde startscherm moeten worden geplaatst. U kunt het aantal rijen en kolommen van de app instellen om de rastergrootte in de volgende indeling `columns;rows` te definiëren. Als u de rastergrootte definieert, zou het maximum aantal apps dat wordt weergegeven in een rij op het startscherm het aantal rijen zijn dat u instelt en zou het maximale aantal apps dat wordt weergegeven in een kolom in het startscherm het aantal kolommen zijn dat u instelt. |
| Meldingsbadge inschakelen | Booleaanse waarde | FALSE | Hiermee kunt de meldingsbadge voor app-pictogrammen inschakelen die het aantal nieuwe meldingen in de app aangeeft. Als u deze instelling inschakelt, zullen eindgebruikers meldingsbadges zien in apps met ongelezen meldingen. Als u deze configuratiesleutel uitgeschakeld houdt, zal de gebruiker geen meldingsbadge zien voor apps die mogelijk ongelezen meldingen hebben. |
| Startscherm vergrendelen | Booleaanse waarde | TRUE | Hiermee ontneemt u de gebruiker de mogelijkheid om app-pictogrammen op het startscherm te verplaatsen. Als u deze configuratiesleutel inschakelt, worden de app-pictogrammen op het startscherm vergrendeld en zal de eindgebruiker deze niet kunnen slepen en neerzetten naar verschillende rasterposities van het startscherm. Als deze op `false` is gezet, zullen eindgebruikers toepassings- en weblinkpictogrammen op Managed Home Screen kunnen verplaatsen.  |
| Achtergrond apparaat instellen | string | Standaard | Hiermee kunt u een achtergrond van uw keuze instellen door de URL van de installatiekopie in te voeren die u als achtergrond wilt instellen. |
| De grootte van het app-pictogram instellen | integer | 2 | Hiermee kunt u de pictogramgrootte instellen voor apps die worden weergegeven op het startscherm. U kunt de volgende waarden in deze configuratie kiezen voor de verschillende grootten - 0 (minimale grootte), 1 (klein), 2 (normaal), 3 (groot) en 4 (maximale grootte). |
| Pictogram app-map instellen | integer | 0 | Hiermee kunt u het uiterlijk van app-mappen definiëren op het startscherm. U kunt voor het uiterlijk de volgende waarden kiezen: Donker vierkant(0);   Donker cirkel(1); Licht vierkant(2); Licht cirkel(3). |
| Schermstand instellen | integer | 1 | Hiermee kunt u de stand van het startscherm instellen op de modus Staand, Liggend of Automatisch draaien. U kunt de stand instellen door de waarden 1 (voor de staande modus), 2 (voor de liggende modus), 3 (voor Automatisch draaien) in te voeren. |
| Telemetrie van het apparaat inschakelen | Booleaanse waarde | FALSE | Hiermee kunt u de telemetrie inschakelen die wordt vastgelegd voor het beheerde startscherm. Als u dit inschakelt, kan Microsoft telemetrie over het apparaatgebruik vastleggen, zoals het aantal keren dat een bepaalde app op dit apparaat wordt gestart. |
| De in de whitelist opgenomen toepassingen instellen | bundleArray | FALSE | Hiermee kunt u de apps definiëren die op het startscherm worden weergegeven. U kunt kiezen uit alle apps die op het apparaat zijn geïnstalleerd. U definieert de apps door de naam van het app-pakket in te voeren van de apps die u graag zichtbaar wilt maken. Met com.microsoft.emmx voegt u bijvoorbeeld Instellingen toe aan het startscherm. De apps die u in dit gedeelte op de whitelist plaatst, moeten al op het apparaat zijn geïnstalleerd om te worden weergegeven op het startscherm. |
| Vastgemaakte webkoppelingen instellen | bundleArray | FALSE | Hiermee kunt u websites vastmaken als pictogrammen voor snel starten op het startscherm. Met deze configuratie kunt u de URL definiëren en toevoegen aan het startscherm waar de eindgebruiker deze met één keer tikken kan starten in de browser. |
| De schermbeveiliging inschakelen | Booleaanse waarde | FALSE | De schermbeveiligingsmodus wel of niet inschakelen. Indien deze is ingesteld op true, kunt u **screen_saver_image**, **screen_saver_show_time**, **inactive_time_to_show_screen_saver**, en **media_detect_ screen_saver** configureren. |
| Installatiekopie van schermbeveiliging | string |   | Hiermee stelt u de URL van de installatiekopie van de schermbeveiliging in. Als er geen URL is ingesteld, geven apparaten de standaard ingestelde schermbeveiligingsafbeelding weer wanneer de schermbeveiliging wordt geactiveerd. De standaardafbeelding geeft het pictogram van de Managed Home Screen-app weer.  |
| Tijd weergeven bij schermbeveiliging | integer | 0 | Hiermee wordt de optie geboden om de hoeveelheid tijd in seconden in te stellen die op het apparaat wordt weergegeven tijdens de schermbeveiligingsmodus. Als deze is ingesteld op 0, wordt de schermbeveiliging voor onbepaalde tijd weergegeven in de schermbeveiligingsmodus totdat het apparaat wordt geactiveerd.  |
| Duur van inactiviteit voor het inschakelen van de schermbeveiliging | integer | 30 | Het aantal seconden dat het apparaat niet actief is voordat de schermbeveiliging wordt geactiveerd. Als deze op 0 ia ingesteld, schakelt het apparaat nooit in de modus voor schermbeveiliging. |
| Media wordt gedetecteerd voordat schermbeveiliging wordt weergegeven | Booleaanse waarde | TRUE | Kies of schermbeveiliging op het scherm van het apparaat moet worden weergegeven als audio/video wordt afgespeeld op apparaat. Als deze optie is ingesteld op waar, wordt op het apparaat geen audio/video afgespeeld, ongeacht de waarde in **inactive_time_to_show_scree_saver**. Als deze optie is ingesteld op onwaar, wordt schermbeveiliging weergegeven op het apparaatscherm op basis van de waarde die in **inactive_time_to_show_screen_saver** is ingesteld.   |
| Virtuele startknop inschakelen | Booleaanse waarde | FALSE | Schakel deze instelling op `True` waardoor de eindgebruiker toegang heeft tot een startknop voor Managed Home Screen waardoor de gebruiker naar Managed Home Screen terugkeert vanuit de huidige taak waarin hij/zij zich bevindt.  |
| Type virtuele startknop | string | swipe_up | Gebruik **swipe_up** om toegang te krijgen tot de startknop met een gebaar Omhoog vegen. Gebruik **float** om toegang te krijgen tot een sticky, permanente startknop die de gebruiker over het scherm kan verplaatsen. |
| Indicatiebalk van accu- en signaalsterkte | Booleaanse waarde | True  | Wanneer u deze instelling op `True` zet, wordt de indicatiebalk voor de batterij- en signaalsterkte weergegeven. |
| Wachtwoord voor afsluiten taakvergrendelingsmodus | string |   | Voer een 4-6-cijferige code in waarmee u tijdelijk de taakvergrendelingsmodus kunt opheffen voor het oplossen van problemen. |
| Wi-Fi-instellingen tonen | Booleaanse waarde | FALSE | Wanneer u deze instelling op `True` zet, kan de eindgebruiker Wi-Fi in- of uitschakelen of verbinding maken met verschillende Wi-Fi-netwerken.  |
| Bluetooth-instelling tonen | Booleaanse waarde | FALSE | Wanneer u deze instelling op `True` zet, kan de eindgebruiker Bluetooth in- of uitschakelen of verbinding maken met verschillende voor Bluetooth geschikte netwerken.   |
| Toepassingen in een map worden geordend op naam | Booleaanse waarde | TRUE | Als u deze instelling op `False` instelt, verschijnen items in een map in de volgorde waarin ze zijn opgegeven. Anders worden ze op alfabetische volgorde in de map weergegeven.   |
| Alfabetische volgorde ingeschakeld | Booleaanse waarde | FALSE | Als u deze instellingen op `True` instelt, is het mogelijk om de volgorde van toepassingen, weblinks en mappen in de Managed Home Screen in te stellen. Als dit is ingeschakeld, stelt u de volgorde in met **app_order**. Dan kan de eindgebruiker Bluetooth in- of uitschakelen of verbinding maken met verschillende voor Bluetooth geschikte netwerken.   |
| Toepassingsvolgorde | bundleArray | FALSE | Hiermee geeft u de volgorde van toepassingen, weblinks en mappen op in Managed Home Screen. Als u deze instelling wilt gebruiken, moet **Startscherm vergrendelen** zijn ingeschakeld, moet **Rastergrootte instellen** zijn gedefinieerd en moet **Toepassingsvolgorde ingeschakeld** zijn ingesteld op `True`.   |

## <a name="enter-json-data"></a>JSON-gegevens invoeren

Voer JSON-gegevens in voor het configureren van alle beschikbare instellingen voor Managed Home Screen, evenals de instellingen die zijn uitgeschakeld in **Configuration Designer**.

![Schermopname van de toegevoegde JSON-gegevens](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_03.png)

Naast de lijst met configureerbare instellingen die worden vermeld in de tabel **Configuration Designer** (hierboven) biedt de volgende tabel de configuratiesleutels die u alleen via JSON-gegevens kunt configureren.

|    Configuratiesleutel    |    Waardetype    |    Standaardwaarde    |    Beschrijving    |
|-------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    De in de whitelist opgenomen toepassingen instellen    |    bundleArray    | <img alt="JSON - Example 1" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson01.png" width="300"> |    Hiermee kunt u de serie apps definiëren die op het startscherm zijn weergegeven bij de apps die op het apparaat zijn geïnstalleerd. U kunt de apps definiëren door de naam van het app-pakket in te voeren van de apps die u graag zichtbaar wilt maken. Met com.android.settings voegt u bijvoorbeeld Instellingen toe aan het startscherm. De apps die u in dit gedeelte op de whitelist plaatst, moeten al op het apparaat zijn geïnstalleerd om te worden weergegeven op het startscherm.    |
|    Vastgemaakte webkoppelingen instellen    |    bundleArray    | <img alt="JSON - Example 2" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson02.png" width="300"> |    Hiermee kunt u websites vastmaken als pictogrammen voor snel starten op het startscherm. Met deze configuratie kunt u de URL definiëren en toevoegen aan het startscherm waar de eindgebruiker deze met één keer tikken kan starten in de browser.    |
|    Een beheerde map maken voor het groeperen van apps    |    bundleArray    | <img alt="JSON - Example 3" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson03.png" width="300"> |    Hiermee kunt u mappen maken en benoemen en apps groeperen binnen deze mappen. Eindgebruikers kunnen geen mappen verplaatsen, de naam van de mappen wijzigen of de apps binnen de mappen verplaatsen.   Mappen worden weergegeven in de volgorde waarin deze zijn gemaakt en apps in de mappen worden op alfabetische volgorde weergegeven.         Opmerking: alle apps die u wilt groeperen in mappen moeten naar behoren zijn toegewezen aan het apparaat en moet zijn toegevoegd aan de beheerde startscherm.     |

Hier volgt een voorbeeld-JSON-script met alle beschikbare configuratiesleutels die erin zijn opgenomen:

```json
{
    "kind": "androidenterprise#managedConfiguration",
    "productId": "com.microsoft.launcher.enterprise",
    "managedProperty": [
        {
            "key": "lock_home_screen",
            "valueBool": true
        },
        {
            "key": "wallpaper",
            "valueString": "default"
        },
        {
            "key": "icon_size",
            "valueInteger": 2
        },
        {
            "key": "app_folder_icon",
            "valueInteger": 0
        },
        {
            "key": "screen_orientation",
            "valueInteger": 1
        },
        {
            "key": "enable_telemetry",
            "valueBool": false
        },
        {
            "key": "applications",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "package",
                            "valueString": “app package name here”
                        }
                    ]
                }
            ]
        },
        {
            "key": "weblinks",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "link",
                            "valueString": “link here”
                        },
                        {
                            "key": "label",
                            "valueString": “weblink label here”
                        }
                    ]
                }
            ]
        },
        {
            "key": "show_virtual_home",
            "valueBool": false
        },
        {
            "key": "virtual_home_type",
            "valueString": "swipe_up"
        },
        {
            "key": "show_virtual_status_bar",
            "valueBool": true
        },
        {
            "key": "exit_lock_task_mode_code",
            "valueString": ""
        },
        {
            "key": "show_wifi_setting",
            "valueBool": false
        },
        {
            "key": "show_bluetooth_setting",
            "valueBool": false
        },
        {
            "key": "grid_size",
            "valueString": "4;5"
        },
        {
            "key": "app_order_enabled",
            "valueBool": true
        },
        {
            "key": "apps_in_folder_ordered_by_name",
            "valueBool": true
        },
        {
            "key": "app_orders",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "package",
                            "valueString": "com.Microsoft.emmx"
                        },
                        {
                            "key": "type",
                            "valueString": "application"
                        },
                        {
                            "key": "container",
                            "valueInteger": 1
                        },
                        {
                            "key": "position",
                            "valueInteger": 1
                        }
                    ]
                },
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Work"
                        },
                        {
                            "key": "type",
                            "valueString": "managed_folder"
                        },
                        {
                            "key": "container",
                            "valueInteger": 1
                        },
                        {
                            "key": "position",
                            "valueInteger": 2
                        }
                    ]
                },
                {
                    "managedProperty": [
                        {
                            "key": "package",
                            "valueString": "com.microsoft.launcher.enterprise"
                        },
                        {
                            "key": "type",
                            "valueString": "application"
                        },
                        {
                            "key": "class",
                            "valueString": "com.microsoft.launcher.launcher"
                        },
                        {
                            "key": "container",
                            "valueInteger": 1
                        },
                        {
                            "key": "position",
                            "valueInteger": 3
                        }
                    ]
                }
            ]
        },
        {
            "key": "managed_folders",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Folder name here"
                        },
                        {
                            "key": "applications",
                            "valueBundleArray": [
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.emmx"
                                        }
                                    ]
                                },
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.bing"
                                        }
                                    ]
                                },
                                {
                                    "managedProperty": [
                                        {
                                            "key": "link",
                                            "valueString": "https://microsoft.com/"
                                        }
                                    ]
                                }
                            ]
                        }
                    ]
                },
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Example folder name 2"
                        },
                        {
                            "key": "applications",
                            "valueBundleArray": [
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.office.word"
                                        }
                                    ]
                                }
                            ]
                        }
                    ]
                }
            ]
        }
    ]
}
```

## <a name="googles-android-device-policy-app"></a>De app Android Device Policy van Google
De app Managed Home Screen biedt nu toegang tot de app Android Device Policy van Google. De app Managed Home Screen is een aangepast startprogramma dat wordt gebruikt voor apparaten die bij Intune zijn ingeschreven als toegewezen Android Enterprise-apparaat (AE) op basis van de kioskmodus voor meerdere apps. U kunt de app Android Device Policy openen of gebruikers naar de app leiden voor ondersteuning en foutopsporing. De opstartmogelijkheid is beschikbaar op het moment dat het apparaat wordt ingeschreven en wordt gekoppeld aan Managed Home Screen. Er zijn geen extra installaties nodig voor het gebruik van deze functionaliteit.

## <a name="managed-home-screen-debug-screen"></a>Scherm voor probleemopsporing voor Managed Home Screen
U kunt het scherm voor probleemopsporing voor Managed Home Screen openen door op de knop **Terug** te klikken tot het scherm voor foutopsporing wordt weergegeven (klik vijftien keer of vaker op de knop **Terug**). Vanuit dit scherm voor foutopsporing kunt u de toepassing Android Device Policy starten, logboeken weergeven en uploaden of de kioskmodus tijdelijk onderbreken om het apparaat bij te werken. Voor meer informatie over het onderbreken van de kioskmodus raadpleegt u het item **Kioskmodus verlaten** in de [toegewezen apparaatinstellingen](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings) voor Android Enterprise.

## <a name="next-steps"></a>Volgende stappen

- Zie voor meer informatie over aan Android Enterprise toegewezen apparaten [Intune-inschrijving van aan Android Enterprise toegewezen apparaten instellen](../enrollment/android-kiosk-enroll.md).
