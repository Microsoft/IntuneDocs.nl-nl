---
title: Nalevingsbeleid voor apparaten | Microsoft Intune
description: In dit onderwerp wordt uitgelegd wat het nalevingsbeleid voor apparaten is en hoe dit beleid werkt.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: b41307f620284315e4c71b0d0292b229753876ad


---

# <a name="device-compliance-policies-in-microsoft-intune"></a>Nalevingsbeleid voor apparaten in Microsoft Intune
## <a name="what-is-a-compliance-policy"></a>Wat is nalevingsbeleid?
U moet er voor de beveiliging van bedrijfsgegevens voor zorgen dat de apparaten die worden gebruikt voor toegang tot bedrijfs-apps en- gegevens, voldoen aan bepaalde regels. Deze regels kunnen bijvoorbeeld zijn dat voor toegang tot apparaten een pincode moet worden opgegeven en dat gegevens op apparaten moeten zijn versleuteld. Een verzameling van dergelijke regels wordt een nalevingsbeleid genoemd.

## <a name="how-should-i-use-compliance-policies"></a>Hoe gebruikt u nalevingsbeleid?
U kunt nalevingsbeleid gebruiken met beleid voor voorwaardelijke toegang om alleen toegang te verlenen aan apparaten die voldoen aan de regels van het nalevingsbeleid voor de toegang tot e-mail en andere services. Lees het artikel [De toegang tot e-mail en O365-services beperken](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) om te begrijpen hoe de twee soorten beleid samen kunnen worden gebruikt.

U kunt nalevingsbeleid ook onafhankelijk van voorwaardelijke toegang gebruiken. Bij onafhankelijk gebruik van nalevingsbeleid worden de betreffende apparaten geëvalueerd en samen met hun nalevingsstatus gerapporteerd. U kunt bijvoorbeeld rapporteren over het aantal apparaten dat niet is versleuteld of over welke apparaten zijn opengebroken of geroot. Bij onafhankelijk gebruik van nalevingsbeleid zijn er echter geen toegangsbeperkingen tot bedrijfsbronnen aanwezig.

U implementeert nalevingsbeleid voor gebruikers. Wanneer er nalevingsbeleid wordt geïmplementeerd voor een gebruiker, worden de apparaten van de gebruiker gecontroleerd op naleving.
Raadpleeg voor meer informatie over hoe lang het duurt voordat mobiele apparaten een beleid krijgen nadat het beleid is geïmplementeerd [Instellingen en functies op uw apparaten beheren](https://docs.microsoft.com/en-us/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#frequently-asked-questions-about-intune-policies).

De volgende tabel bevat de typen apparaten die ondersteuning bieden voor nalevingsbeleid. In de tabel wordt ook beschreven hoe niet-compatibele instellingen worden beheerd wanneer een nalevingsbeleid wordt gebruikt in combinatie met beleid voor voorwaardelijke toegang.

-----------------------------

|Beleidsinstelling| Windows 8.1 en hoger| Windows Phone 8.1 en hoger| iOS 8.0 en hoger|Android 4.0 en hoger<br/>Samsung Knox Standard 4.0 en hoger|
|-----|----|----|----|----|
|**Configuratie van pincode of wachtwoord** |Hersteld|Hersteld|Hersteld|In quarantaine|
|**Apparaatversleuteling**|Niet van toepassing|Hersteld|Hersteld (door een pincode in te stellen)|In quarantaine|
|**Opengebroken of geroot apparaat**|Niet van toepassing|Niet van toepassing|In quarantaine (geen instelling)|In quarantaine (geen instelling)|
|**E-mailprofiel**|Niet van toepassing|Niet van toepassing|In quarantaine|Niet van toepassing|
|**Minimale versie van het besturingssysteem**|In quarantaine|In quarantaine|In quarantaine|In quarantaine|
|**Maximale versie van het besturingssysteem**|In quarantaine|In quarantaine|In quarantaine|In quarantaine|
|**Windows Health Attestation**|In quarantaine: Windows 10 en Windows 10 Mobile<br /><br />Niet van toepassing: Windows 8.1|Niet van toepassing|Niet van toepassing|Niet van toepassing|

------------------------------

**Hersteld** = het besturingssysteem van het apparaat dwingt naleving af. (De gebruiker wordt bijvoorbeeld gedwongen een pincode in te stellen.)

**In quarantaine** = het besturingssysteem van het apparaat dwingt geen naleving af. (Bij Android-apparaten bijvoorbeeld wordt de gebruiker niet gedwongen het apparaat te versleutelen.) Als het apparaat niet compatibel is, worden de volgende acties uitgevoerd:

-   Het apparaat wordt geblokkeerd als een beleid voor voorwaardelijke toegang van toepassing is voor de gebruiker.

-   De bedrijfsportal stelt de gebruiker op de hoogte van eventuele nalevingsproblemen.

## <a name="next-steps"></a>Volgende stappen
[Een nalevingsbeleid voor apparaten maken](create-a-device-compliance-policy-in-microsoft-intune.md)

[Een nalevingsbeleid voor apparaten implementeren en bewaken](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### <a name="see-also"></a>Zie tevens
[De toegang tot e-mail en O365-services beperken](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


