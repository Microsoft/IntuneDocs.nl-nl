---
title: Gebruik StageNow aanmeldt Zebra.bmp Android-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Zie veelvoorkomende problemen en oplossingen bij het gebruik van StageNow op Android-apparaten met Microsoft Intune. U leert ook hoe u Logboeken ophalen en Bekijk voorbeelden van hoe u de logboeken voor het slagen of fouten worden gelezen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 36476820805c00cefafcd9f64dd2f08a014762c0
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490538"
---
# <a name="troubleshoot-and-see-potential-issues-on-android-zebra-devices-in-microsoft-intune"></a>Problemen oplossen en potentiële problemen zien op Zebra.bmp Android-apparaten in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In Microsoft Intune, kunt u [Zebra.bmp Mobility extensies (MX) voor het beheren van apparaten met Android Zebra.bmp](android-zebra-mx-overview.md). Als u Zebra.bmp apparaten, moet u profielen maken in StageNow om instellingen te beheren en te uploaden naar Intune. Intune maakt gebruik van de app StageNow om toe te passen van de instellingen op de apparaten. De app StageNow maakt ook een gedetailleerd logboekbestand op het apparaat dat wordt gebruikt om op te lossen.

Deze functie is van toepassing op:

- Android

U kunt bijvoorbeeld een profiel maken in StageNow om een apparaat te configureren. Wanneer u de StageNow-profiel maakt, genereert de laatste stap een bestand voor het testen van het profiel. U gebruikt dit bestand met de app StageNow op het apparaat.

In een ander voorbeeld kunt u een profiel maken in StageNow en testen. In Intune, kunt u de StageNow profiel toevoegen en deze vervolgens toewijzen aan uw apparaten Zebra.bmp. Tijdens het controleren van de status van het toegewezen profiel, ziet u het profiel een statuswaarde op hoog niveau.

In beide gevallen, kunt u meer informatie krijgen van het logboekbestand StageNow, telkens wanneer een profiel StageNow van toepassing is op het apparaat is opgeslagen.

Sommige problemen worden niet met betrekking tot de inhoud van het profiel StageNow en niet worden doorgevoerd in de logboeken.

Dit artikel ziet u hoe u de logboeken StageNow lezen en een lijst met enkele andere potentiële problemen met Zebra.bmp-apparaten die niet kunnen worden doorgevoerd in de logboeken.

[Gebruik en beheer van apparaten met Zebra.bmp Mobility extensies Zebra.bmp](android-zebra-mx-overview.md) bevat meer informatie over deze functie.

## <a name="get-the-logs"></a>De logboeken ophalen

### <a name="use-the-stagenow-app-on-the-device"></a>De app StageNow op het apparaat gebruiken
Wanneer u een profiel rechtstreeks op uw computer, in plaats van met StageNow testen [Intune het profiel kan implementeren](android-zebra-mx-overview.md#step-4-create-a-device-management-profile-in-stagenow), de StageNow-app op het apparaat Hiermee slaat u de logboeken van de test. Als u het logboekbestand, gebruikt de **meer (...)**  optie in de app StageNow op het apparaat.

### <a name="get-logs-using-android-debug-bridge"></a>Met behulp van Android foutopsporing Bridge-logboeken ophalen
Als u zich aanmeldt nadat het profiel al is geïmplementeerd met Intune, kunt u het apparaat aansluit op een computer met [Android foutopsporing Bridge (adb)](https://developer.android.com/studio/command-line/adb) (opent u de Android-website).

Op het apparaat, worden logboeken opgeslagen in `/sdcard/Android/data/com.microsoft.windowsintune.companyportal/files`

### <a name="get-logs-from-email"></a>Logboeken ophalen uit de e-mailadres
Als u zich aanmeldt nadat het profiel al is geïmplementeerd met Intune, krijgen eindgebruikers kunt u een e-mail de logboeken met behulp van een e-mail-app op het apparaat. Open de bedrijfsportal-app op het apparaat Zebra.bmp en [de logboeken te zenden](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). Met de functie van de logboeken verzenden maakt ook een PowerLift incident-ID, die u kunt verwijzen naar als contact opneemt met Microsoft ondersteuning.

## <a name="read-the-logs"></a>De logboeken te lezen

Bij het zoeken naar de logboeken, er is een fout als u ziet de `<characteristic-error>` tag. Details van fouten worden geschreven naar de `<parm-error>` tag > `desc` eigenschap.

## <a name="error-types"></a>Fouttypen

Zebra.bmp apparaten zijn verschillende niveaus voor foutrapportage:

- De CSP wordt niet ondersteund op het apparaat. Bijvoorbeeld, het apparaat is niet van een mobiel apparaat en beschikt niet over een mobiel manager.
- De MX- of OS x-versie komt niet overeen. Elke CSP is samengesteld. Zie voor een volledige ondersteuningsmatrix [Zebra.bmp van documentatie](http://techdocs.zebra.com/mx/) (opent u de website van zebra.bmp).
- Het apparaat rapporteert een ander probleem of een fout.

## <a name="examples"></a>Voorbeelden

U hebt bijvoorbeeld de volgende invoer profiel:

```xml
<wap-provisioningdoc>
    <characteristic type="Clock">
        <parm name="AutoTime" value="false"/>
        <parm name="TimeZone" value="GMT-5"/>
        <parm name="Date" value="2014-12-03"/>
        <parm name="Time" value="11:11:11"/>
    </characteristic>
</wap-provisioningdoc>
```

Het XML-bestand is in het logboek identiek aan de invoer. Deze overeenkomende uitvoer betekent dat het profiel is toegepast op het apparaat zonder fouten:

```xml
<wap-provisioningdoc>
    <characteristic type="Clock" version="6.0">
        <parm name="AutoTime" value="false"/>
        <parm name="TimeZone" value="GMT-5"/>
        <parm name="Date" value="2014-12-03"/>
        <parm name="Time" value="11:11:11"/>
    </characteristic>
</wap-provisioningdoc>
```

In een ander voorbeeld hebt u de volgende invoer:

```xml
<wap-provisioningdoc>
    <characteristic type="XmlMgr" version="4.2" >
        <parm name="ProcessingMode" value="1"/>
    </characteristic>
    <characteristic type="AppMgr" version="4.2" >
        <parm name="Action" value="Install"/>
        <parm name="APK" value="/sdcard/test.apk"/>
    </characteristic>
</wap-provisioningdoc>
```

Het logboek krijgt de foutstatus, omdat deze bevat een `<characteristic-error>` tag. In dit scenario wordt geprobeerd het profiel voor het installeren van een pakket Android (APK) die niet bestaat in het opgegeven pad:

```xml
<wap-provisioningdoc>
    <characteristic type="XmlMgr" version="4.2">
        <parm name="ProcessingMode" value="1"/>
    </characteristic>
    <characteristic-error type="AppMgr" version="5.1" desc="missing">
        <parm-error name="Action" value="Install" desc="apk doesnot exist in the path"/>
        <parm name="APK" value="/sdcard/test.apk"/>
    </characteristic-error>
</wap-provisioningdoc>
```

## <a name="other-potential-issues-with-zebra-devices"></a>Andere potentiële problemen met apparaten Zebra.bmp

Deze sectie vindt u andere mogelijke problemen u ziet bij het gebruik van zebra.bmp apparaten met apparaat-beheerder. Deze problemen worden niet in de logboeken StageNow gerapporteerd.

### <a name="android-system-webview-is-out-of-date"></a>Android System WebView is verouderd

Wanneer oudere apparaten zich aanmelden met behulp van de bedrijfsportal-app, kunnen gebruikers zien een bericht dat het onderdeel System WebView verouderd is en moet worden bijgewerkt. Als het apparaat heeft Google Play is geïnstalleerd, is het verbinden met het internet en controleren op updates. Als het apparaat geen Google Play geïnstalleerd, de bijgewerkte versie van het onderdeel en pas deze toe op de apparaten. Of update naar de meest recente besturingssysteem dat is uitgegeven door Zebra.bmp van het apparaat.

### <a name="management-actions-take-a-long-time"></a>Acties voor duren lange tijd

Als Google Play-services niet beschikbaar zijn, worden sommige taken tot acht uur te voltooien. [Beperkingen van de Intune-bedrijfsportal-app voor Android](https://support.microsoft.com/help/3211588/limitations-of-intune-company-portal-app-for-android-in-china) (opent u een andere Microsoft-website) mogelijk een goede bron.

### <a name="device-spoofing-suspected-shows-in-intune"></a>'Apparaat verdacht spoofing' ziet u in Intune

Deze fout betekent dat Intune vermoedt dat een niet - Zebra.bmp Android-apparaat rapporteert de fabrikant als een apparaat Zebra.bmp en het model.

### <a name="company-portal-app-is-older-than-minimum-required-version"></a>Bedrijfsportal-app is ouder dan de minimaal vereiste versie

Intune kan de minimaal vereiste versie van de bedrijfsportal-app bijwerken. Als Google Play niet is geïnstalleerd op het apparaat, wordt de bedrijfsportal-app niet automatisch bijgewerkt. Als de minimaal versie is nieuwer dan de versie is geïnstalleerd vereiste, betekent dit dat de bedrijfsportal-app werkt niet. Update van de meest recente bedrijfsportal-app via [sideloading op apparaten Zebra.bmp](android-zebra-mx-overview.md#sideload-the-company-portal-app).

## <a name="next-steps"></a>Volgende stappen

[Zebra.bmp discussieborden](https://developer.zebra.com/community/home/discussions) (opent u de website van zebra.bmp)

[Gebruik en beheer van apparaten Zebra.bmp met Zebra.bmp Mobility extensies in Intune](android-zebra-mx-overview.md)
