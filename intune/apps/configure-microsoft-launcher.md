---
title: Microsoft Launcher voor Android Enterprise configureren met Intune
titleSuffix: ''
description: Gebruik Intune-configuratiebeleid met Microsoft Launcher.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/26/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 55f76b0c5c71f7828fed17233c2b81d6b066cc3b
ms.sourcegitcommit: fab685b22a010fe231b27a0c5eda34a6f22f4c8d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "78216111"
---
# <a name="configure-microsoft-launcher"></a>Microsoft Launcher configureren

Microsoft Launcher is een Android-toepassing waarmee gebruikers hun telefoon kunnen personaliseren, onderweg georganiseerd kunnen blijven, en kunnen overschakelen van werken op hun telefoon naar werken op de pc. 

In Launcher mogen IT-beheerders van bedrijven startschermen van volledig beheerde Android Enterprise-apparaten aanpassen, door de achtergrond, apps en posities van pictogrammen te selecteren. Hierdoor wordt het uiterlijk van alle beheerde Android-apparaten gestandaardiseerd op verschillende OEM-apparaten en systeemversies. 

## <a name="how-to-configure-the-microsoft-launcher-app"></a>De Microsoft Launcher-app configureren 

Navigeer naar het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) en selecteer **Apps** > **Configuratiebeleid voor apps**. Voeg een configuratiebeleid toe voor **Beheerde apparaten** met **Android**, en kies **Microsoft Launcher** als bijbehorende app. Klik op **Configuratie-instellingen** om de verschillende beschikbare instellingen voor Microsoft Launcher te configureren. 

## <a name="choosing-a-configuration-settings-format"></a>Een indeling voor de configuratie-instellingen kiezen 

Er zijn twee methoden waarmee u configuratie-instellingen kunt definiëren voor Microsoft Launcher: 

- Met **Configuration Designer** kunt u instellingen configureren met een gebruiksvriendelijke gebruikersinterface waarmee u functies in of uit kunt schakelen en waarden kunt instellen. In deze methode zijn er enkele uitgeschakelde configuratiesleutels met waardetype BundleArray. Deze configuratiesleutels kunnen alleen worden geconfigureerd door JSON-gegevens in te voeren. 

- Met **JSON-gegevens** kunt u alle mogelijke configuratiesleutels definiëren met een JSON-script. 

Als u eigenschappen toevoegt met **Configuration Designer**, kunt u deze eigenschappen automatisch omzetten in JSON door **JSON-gegevens invoeren** te selecteren in de vervolgkeuzelijst **Indeling voor configuratie-instellingen**.

   ![Indeling voor configuratie-instellingen - Configuration Designer gebruiken](./media/configure-microsoft-launcher/configure-microsoft-launcher-01.png)

## <a name="using-configuration-designer"></a>Configuration Designer gebruiken

Met Configuration Designer kunt u vooraf gevulde instellingen en de bijbehorende waarden selecteren.

   ![Indeling voor configuratie-instellingen - JSON-gegevens invoeren](./media/configure-microsoft-launcher/configure-microsoft-launcher-02.png)

De volgende tabel bevat de configuratiesleutels, waardetypen, standaardwaarden en beschrijvingen die beschikbare zijn in Microsoft Launcher. De beschrijving voorziet in het verwachte apparaatgedrag op basis van de geselecteerde waarden. Configuratiesleutels die zijn uitgeschakeld in Configuration Designer worden niet in de tabel weergegeven.

|    Configuratiesleutel    |    Waardetype    |    Standaardwaarde    |    Beschrijving     |
|---------------------------------------------------|------------------|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Inschrijvingstype    |    Tekenreeks     |    Standaard    |    Hiermee kunt u het inschrijvingstype instellen waarop u dit beleid wilt toepassen. Momenteel verwijst de waarde **Standaard** naar **CorporateOwnedBuisnessOnly**. Er zijn momenteel geen andere ondersteunde inschrijvingstypen.        JSON-sleutelnaam: management_mode_key        |
|    Gebruiker toestaan de Home Screen-app-volgorde te wijzigen    |    Boolean-waarde    |    True    |    Hiermee kunt u opgeven of de **Home Screen-app-volgorde** kan worden gewijzigd door de eindgebruiker.<ul><li>Als dit is ingesteld op **True**, wordt de app-volgorde die is gedefinieerd in het beleid, alleen afgedwongen bij de eerste implementatie. Vervolgens wordt het beleid niet afgedwongen om eventuele wijzigingen door te voeren die zijn aangebracht door de gebruiker.</li><li>Als dit is ingesteld op **False**, wordt de app-volgorde afgedwongen bij elke synchronisatie.</li></ul><br>**Opmerking:** De Home Screen-app-volgorde kan alleen worden geconfigureerd met de JSON-editor.<br><br>JSON-sleutelnaam:<br>`com.microsoft.launcher.HomeScreen.AppOrder.UserChangeAllowed`    |
|    De rastergrootte instellen    |    Tekenreeks    |    Automatisch    |    Hiermee kunt u de rastergrootte instellen voor apps die op het startscherm moeten worden geplaatst. U kunt het aantal rijen en kolommen van de app instellen om de rastergrootte te definiëren in de volgende indeling: `columns;rows`. Als u de rastergrootte definieert, is het maximale aantal apps dat wordt weergegeven in een rij op het startscherm, het aantal rijen dat u instelt. Het maximale aantal apps dat wordt weergegeven in een kolom in het startscherm, is het aantal kolommen dat u instelt.<br><br>        JSON-sleutelnaam:<br>`com.microsoft.launcher.HomeScreen.GridSize`    |
|    Achtergrond van apparaat instellen    |    Tekenreeks    |    Null    |    Hiermee kunt u een achtergrond van uw keuze instellen, door de URL van de afbeelding in te voeren die u wilt instellen als achtergrond.<br><br>JSON-sleutelnaam:<br>`com.microsoft.launcher.Wallpaper.URL`    |
|    Gebruiker toestaan de achtergrond te wijzigen    |    Booleaanse waarde    |    True    |    Hiermee kunt u opgeven of de instelling Achtergrond van apparaat instellen kan worden gewijzigd door de eindgebruiker.<ul><li>Als dit is ingesteld op **True**, wordt de achtergrond in het beleid alleen afgedwongen bij de eerste implementatie. Vervolgens wordt het beleid niet afgedwongen om eventuele wijzigingen door te voeren die zijn aangebracht door de gebruiker.</li><li>Als dit is ingesteld op **False**, wordt de achtergrond afgedwongen bij elke synchronisatie.</li></ul><br>JSON-sleutelnaam:<br>`com.microsoft.launcher.Wallpaper.URL.UserChangeAllowed`        |
|    Feed inschakelen    |    Boolean-waarde    |    True    |    Hiermee kunt u de startfeed inschakelen op het apparaat, wanneer de gebruiker naar rechts swipet op het startscherm.<ul><li>Als dit is ingesteld op **True**, wordt de feed ingeschakeld.</li><li>Als dit is ingesteld op **False**, wordt de feed uitgeschakeld.</li></ul><br>JSON-sleutelnaam:<br>`com.microsoft.launcher.Feed.Enabled`    |
|    Gebruiker toestaan het inschakelen van de feed te wijzigen    |    Boolean-waarde    |    True    |     Hiermee kunt u opgeven of de instelling **Feed inschakelen** kan worden gewijzigd door de eindgebruiker.<ul><li>Als dit is ingesteld op **True**, wordt de feed alleen afgedwongen bij de eerste implementatie. Vervolgens wordt het beleid niet afgedwongen om eventuele wijzigingen door te voeren die zijn aangebracht door de gebruiker.</li><li>Als dit is ingesteld op **False**, wordt de feed afgedwongen bij elke synchronisatie.</li></ul><br>JSON-sleutelnaam:`com.microsoft.launcher.Feed.Enabled.UserChangeAllowed`    |

## <a name="enter-json-data"></a>JSON-gegevens invoeren

Voer JSON-gegevens in voor het configureren van alle beschikbare instellingen voor Microsoft Launcher, evenals de instellingen die zijn uitgeschakeld in **Configuration Designer**, zoals hieronder weergegeven.

   ![Configuration Designer - JSON-gegevens](./media/configure-microsoft-launcher/configure-microsoft-launcher-03.png)

Naast de lijst met configureerbare instellingen in de tabel Configuration Designer (hierboven) biedt de volgende tabel de configuratiesleutels die u alleen kunt configureren via JSON-gegevens.

|    Configuratiesleutel    |    Waardetype    |    Standaardwaarde    |    Beschrijving     |
|----------------------------------------------------------------------------------------------------|-------------------|-------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    De in de whitelist opgenomen toepassingen instellen<br>JSON-sleutel:`com.microsoft.launcher.HomeScreen.Applications`    |    BundleArray    | Zie: [De in de whitelist opgenomen toepassingen instellen](configure-microsoft-launcher.md#set-allow-listed-applications)</sup>    |    Hiermee kunt u de apps definiëren die op het startscherm worden weergegeven. U kunt kiezen uit alle apps die zijn geïnstalleerd op het apparaat. U definieert de apps door de naam van het app-pakket in te voeren van de apps die u zichtbaar wilt maken. Met `com.android.settings` voegt u bijvoorbeeld instellingen toe aan het startscherm. De apps die u in deze sectie op de whitelist plaatst, moeten al op het apparaat zijn geïnstalleerd om te worden weergegeven op het startscherm.<p>Eigenschappen:<ul><li>**Pakket:** Naam van het toepassingspakket</li><li>**Klasse:** De toepassingsactiviteit die specifiek is voor een bepaalde app-pagina. Als deze waarde leeg is, wordt de standaardpagina van de app gebruikt.</li></ul>      |
|    Home Screen-app-volgorde<br>JSON-sleutel: `com.microsoft.launcher.HomeScreen.AppOrder`    |    BundleArray    |    Zie: [Home Screen-app-volgorde](configure-microsoft-launcher.md#home-screen-app-order)      |    Hiermee kunt u de app-volgorde op het startscherm opgeven.<p>Eigenschappen:<br><ul><li>**Type:** Het enige type dat wordt ondersteund, is `application`.</li><li>**Positie:** De sleuf voor het toepassingspictogram op het startscherm. Deze begint vanaf positie 1 linksboven en gaat van links naar rechts, en van boven naar beneden.</li><li>**Pakket:** Naam van het toepassingspakket.</li><li>**Klasse:** De toepassingsactiviteit die specifiek is voor een bepaalde app-pagina. Als deze waarde leeg is, wordt de standaardpagina van de app gebruikt.</li></ul>    |

### <a name="set-allow-listed-applications"></a>De in de whitelist opgenomen toepassingen instellen

```JSON
{
    "key": "com.microsoft.launcher.HomeScreen.Applications",
    "valueBundleArray": 
    [
        {
            "managedProperty": [
                {
                    "key": "package",
                    "valueString": ""
                },
                {
                    "key": "class",
                    "valueString": ""
                }
            ]
        }
    ]
}
```

### <a name="home-screen-app-order"></a>Home Screen-app-volgorde

```JSON
{
    "key": "com.microsoft.launcher.HomeScreen.AppOrder",
    "valueBundleArray": 
    [
        {
            "managedProperty": [
                {
                    "key": "type",
                    "valueString": "application"
                },
                {
                    "key": "position",
                    "valueInteger": 0
                },
                {
                    "key": "package",
                    "valueString": ""
                },
                {
                    "key": "class",
                    "valueString": ""
                }
            ]
        }
    ]
}
```

Hier volgt een voorbeeld-JSON-script met alle beschikbare configuratiesleutels die erin zijn opgenomen:

```JSON
{
    "kind": "androidenterprise#managedConfiguration", 
    "productId": "app:com.microsoft.launcher", 
    "managedProperty": [
        {
            "key": "management_mode_key", 
            "valueString": "Default"
        }, 
        {
            "key": "com.microsoft.launcher.Feed.Enable.UserChangeAllowed", 
            "valueBool": false
        }, 
        {
            "key": "com.microsoft.launcher.Feed.Enable", 
            "valueBool": true
        }, 
        {
            "key": "com.microsoft.launcher.Wallpaper.Url.UserChangeAllowed", 
            "valueBool": false
        }, 
        {
            "key": "com.microsoft.launcher.Wallpaper.Url", 
            "valueBool": "http://www.contoso.com/wallpaper.png"
        }, 
        {
            "key": "com.microsoft.launcher.HomeScreen.GridSize", 
            "valueString": "5;5"
        }, 
        {
            "key": "com.microsoft.launcher.HomeScreen.Applications", 
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "package", 
                            "valueString": "com.ups.mobile.android"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }, 
                {
                    "managedProperty": [
                        {
                            "key": "package", 
                            "valueString": "com.microsoft.teams"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }, 
                {
                    "managedProperty": [
                        {
                            "key": "package", 
                            "valueString": "com.microsoft.bing"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }
            ]
        }, 
        {
            "key": "com.microsoft.launcher.HomeScreen.AppOrder.UserChangeAllowed", 
            "valueBool": false
        }, 
        {
            "key": "com.microsoft.launcher.HomeScreen.AppOrder", 
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "type", 
                            "valueString": "application"
                        }, 
                        {
                            "key": "position", 
                            "valueInteger": 17
                        }, 
                        {
                            "key": "package", 
                            "valueString": "com.ups.mobile.android"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }, 
                {
                    "managedProperty": [
                        {
                            "key": "type", 
                            "valueString": "application"
                        }, 
                        {
                            "key": "position", 
                            "valueInteger": 18
                        }, 
                        {
                            "key": "package", 
                            "valueString": "com.microsoft.teams"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }, 
                {
                    "managedProperty": [
                        {
                            "key": "type", 
                            "valueString": "application"
                        }, 
                        {
                            "key": "position", 
                            "valueInteger": 19
                        }, 
                        {
                            "key": "package", 
                            "valueString": "com.microsoft.bing"
                        }, 
                        {
                            "key": "class", 
                            "valueString": ""
                        }
                    ]
                }
            ]
        }
    ]
}
```

## <a name="next-steps"></a>Volgende stappen

- Zie [Intune-inschrijving van volledig beheerde Android Enterprise-apparaten instellen](../enrollment/android-fully-managed-enroll.md) voor meer informatie over volledig beheerde Android Enterprise-apparaten.
