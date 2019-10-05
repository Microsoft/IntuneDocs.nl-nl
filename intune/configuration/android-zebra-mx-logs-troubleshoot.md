---
title: StageNow-Logboeken gebruiken op Android Zebra-apparaten in Microsoft Intune-Azure | Microsoft Docs
description: Zie veelvoorkomende problemen en oplossingen wanneer u StageNow op Android-apparaten gebruikt met Microsoft Intune. Meer informatie over het ophalen van Logboeken en voor beelden van het lezen van Logboeken voor succes of fouten.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 324550836cd8e7c8ea2786d15618d5f5010a043f
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71735243"
---
# <a name="troubleshoot-and-see-potential-issues-on-android-zebra-devices-in-microsoft-intune"></a>Problemen oplossen en potentiële problemen op Android Zebra-apparaten in Microsoft Intune weer geven

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

In Microsoft Intune kunt u [Zebra Mobility Extensions (MX) gebruiken voor het beheren van Android Zebra-apparaten](android-zebra-mx-overview.md). Wanneer u Zebra-apparaten gebruikt, maakt u profielen in StageNow om instellingen te beheren en uploadt u deze naar intune. InTune maakt gebruik van de StageNow-app om de instellingen op de apparaten toe te passen. De StageNow-app maakt ook een gedetailleerd logboek bestand op het apparaat dat wordt gebruikt voor het oplossen van problemen.

Deze functie is van toepassing op:

- Android

U maakt bijvoorbeeld een profiel in StageNow om een apparaat te configureren. Wanneer u het profiel StageNow maakt, genereert de laatste stap een bestand voor het testen van het profiel. U gebruikt dit bestand met de StageNow-app op het apparaat.

In een ander voor beeld maakt u een profiel in StageNow en test u het. In intune voegt u het StageNow-profiel toe en wijst u dit toe aan uw Zebra-apparaten. Bij het controleren van de status van het toegewezen profiel wordt in het profiel een status op hoog niveau weer gegeven.

In beide gevallen kunt u meer Details ophalen uit het StageNow-logboek bestand dat wordt opgeslagen op het apparaat wanneer een StageNow-Profiel van toepassing is.

Sommige problemen zijn niet gerelateerd aan de inhoud van het StageNow-profiel en worden niet weer gegeven in de logboeken.

Dit artikel laat u zien hoe u de StageNow-Logboeken kunt lezen en een aantal andere potentiële problemen met Zebra-apparaten kunt weer geven die mogelijk niet in de logboeken worden weer gegeven.

Het [gebruik en beheer van Zebra-apparaten met Zebra Mobility Extensions](android-zebra-mx-overview.md) bevat meer informatie over deze functie.

## <a name="get-the-logs"></a>De logboeken ophalen

### <a name="use-the-stagenow-app-on-the-device"></a>De StageNow-app op het apparaat gebruiken
Wanneer u een profiel direct met StageNow op uw computer test in, in plaats van [intune te gebruiken om het profiel te implementeren](android-zebra-mx-overview.md#step-4-create-a-device-management-profile-in-stagenow), slaat de StageNow-app op het apparaat de logboeken op uit de test. Als u het logboek bestand wilt ophalen, gebruikt u de **meer (...)** optie in de StageNow-app op het apparaat.

### <a name="get-logs-using-android-debug-bridge"></a>Logboeken ophalen met Android debug Bridge
Als u logboeken wilt ophalen nadat het profiel al is geïmplementeerd met intune, verbindt u het apparaat met een computer met [Android debug Bridge (ADB)](https://developer.android.com/studio/command-line/adb) (opent de website van Android).

Op het apparaat worden Logboeken opgeslagen in `/sdcard/Android/data/com.microsoft.windowsintune.companyportal/files`

### <a name="get-logs-from-email"></a>Logboeken ophalen van e-mail
Als u logboeken wilt ophalen nadat het profiel al is geïmplementeerd met intune, kunnen eind gebruikers de logboeken via een e-mail-app op het apparaat verzenden. Open de Bedrijfsportal-app op het Zebra-apparaat en [Verzend de logboeken](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android). Met de functie Logboeken verzenden wordt ook een PowerLift-incident-ID gemaakt, waarnaar u kunt verwijzen als u contact opneemt met micro soft ondersteuning.

## <a name="read-the-logs"></a>De logboeken lezen

Wanneer u de logboeken bekijkt, wordt er een fout bericht weer geven wanneer u de tag `<characteristic-error>` ziet. Fout Details worden geschreven naar de tag `<parm-error>` > eigenschap `desc`.

## <a name="error-types"></a>Fouttypen

Zebra-apparaten bevatten verschillende fout rapportage niveaus:

- De CSP wordt niet ondersteund op het apparaat. Het apparaat is bijvoorbeeld geen mobiel apparaat en heeft geen mobiele manager.
- De MX-of OSX-versie komt niet overeen. Elke CSP heeft een versie nummer. Zie [de documentatie van Zebra](http://techdocs.zebra.com/mx/) (opent de website van Zebra) voor een volledige ondersteunings matrix.
- Het apparaat rapporteert nog een probleem of fout.

## <a name="examples"></a>Voorbeelden

U hebt bijvoorbeeld het volgende invoer profiel:

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

In het logboek is de XML identiek aan de invoer. Deze overeenkomende uitvoer betekent dat het profiel zonder fouten is toegepast op het apparaat:

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

In een ander voor beeld hebt u de volgende invoer:

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

In het logboek wordt een fout weer gegeven, aangezien het een `<characteristic-error>`-tag bevat. In dit scenario heeft het profiel geprobeerd een Android-pakket (APK) te installeren dat niet voor komt in het opgegeven pad:

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

## <a name="other-potential-issues-with-zebra-devices"></a>Andere potentiële problemen met Zebra-apparaten

In deze sectie vindt u andere mogelijke problemen die kunnen optreden wanneer u Zebra-apparaten met een Apparaatbeheer gebruikt. Deze problemen worden niet gerapporteerd in de StageNow-Logboeken.

### <a name="android-system-webview-is-out-of-date"></a>Android System WebView is verouderd

Wanneer oudere apparaten zich aanmelden met behulp van de app Bedrijfsportal, zien gebruikers mogelijk een bericht dat het onderdeel van de systeem weergave is verouderd en moet er een upgrade van worden uitgevoerd. Als Google Play is geïnstalleerd op het apparaat, kunt u het verbinden met internet en controleren op updates. Als Google Play niet is geïnstalleerd op het apparaat, kunt u de bijgewerkte versie van het onderdeel ophalen en op de apparaten Toep assen. U kunt ook bijwerken naar het meest recente besturings systeem van het apparaat dat is uitgegeven door Zebra.

### <a name="management-actions-take-a-long-time"></a>Beheer acties nemen veel tijd in beslag

Als Google Play Services niet beschikbaar zijn, duurt het Maxi maal acht uur voordat sommige taken zijn voltooid. De [beperkingen van intune-bedrijfsportal app voor Android](https://support.microsoft.com/help/3211588/limitations-of-intune-company-portal-app-for-android-in-china) (Open een andere micro soft-website) kunnen een goede resource zijn.

### <a name="device-spoofing-suspected-shows-in-intune"></a>Program ma's die worden verdacht van spoofing, worden weer gegeven in intune

Deze fout betekent dat intune vermoedt dat een niet-Zebra Android-apparaat het model en de fabrikant rapporteert als een Zebra-apparaat.

### <a name="company-portal-app-is-older-than-minimum-required-version"></a>Bedrijfsportal-app is ouder dan de mini maal vereiste versie

InTune kan de mini maal vereiste versie van de app Bedrijfsportal bijwerken. Als Google Play niet op het apparaat is geïnstalleerd, wordt de app Bedrijfsportal niet automatisch bijgewerkt. Als de mini maal vereiste versie nieuwer is dan de geïnstalleerde versie, werkt de Bedrijfsportal-app niet meer. Update naar de nieuwste Bedrijfsportal-app met behulp [van extern laden op Zebra-apparaten](android-zebra-mx-overview.md#sideload-the-company-portal-app).

## <a name="next-steps"></a>Volgende stappen

[Zebra-discussie forums](https://developer.zebra.com/community/home/discussions) (opent de website van Zebra)

[Zebra-apparaten gebruiken en beheren met Zebra Mobility Extensions in Intune](android-zebra-mx-overview.md)
