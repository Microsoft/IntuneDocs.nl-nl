---
title: Nalevingsbeleid voor apparaten | Microsoft Intune
description: In dit onderwerp wordt uitgelegd wat het nalevingsbeleid voor apparaten is en hoe deze beleidsregels werken.
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 44443db664753b202cc3fa07f8b76894320dc55d
ms.openlocfilehash: f3bb686dda7bdf1e9557be2b5f5e0da2fb4d27e4


---

# Nalevingsbeleid voor apparaten in Microsoft Intune
## Wat is nalevingsbeleid?
Om bedrijfsgegevens te beveiligen, moet u ervoor zorgen dat de apparaten die worden gebruikt voor toegang tot bedrijfs-apps en -gegevens, voldoen aan bepaalde regels, zoals het gebruik van een pincode voor toegang tot het apparaat en versleuteling van gegevens die op het apparaat zijn opgeslagen. Een verzameling van dergelijke regels wordt nalevingsbeleid genoemd.

## Hoe gebruikt u nalevingsbeleid?
U kunt nalevingsbeleid gebruiken met beleid voor voorwaardelijke toegang om alleen toegang te verlenen aan apparaten die voldoen aan de regels van het nalevingsbeleid voor de toegang tot e-mail en andere services. Lees het artikel [De toegang tot e-mail en O365-services beperken](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) om te begrijpen hoe de twee soorten beleid samen kunnen worden gebruikt.

U kunt nalevingsbeleid ook onafhankelijk van voorwaardelijke toegang gebruiken. Bij onafhankelijk gebruik worden de betreffende apparaten geëvalueerd en samen met de nalevingsstatus gerapporteerd. U kunt bijvoorbeeld rapporteren over het aantal apparaten dat niet is versleuteld of over welke apparaten zijn opengebroken of geroot. Bij onafhankelijk gebruik zijn er echter geen toegangsbeperkingen tot bedrijfsbronnen aanwezig.

U implementeert nalevingsbeleid voor gebruikers. Wanneer er nalevingsbeleid wordt geïmplementeerd voor een gebruiker, worden de apparaten van de gebruiker gecontroleerd op naleving.

De volgende tabel bevat de apparaattypen die worden ondersteund door nalevingsbeleid en informatie over hoe niet-compatibele instellingen worden beheerd als het beleid wordt gebruikt met beleid voor voorwaardelijke toegang.

--------------

|Beleidsinstelling| Windows 8.1 en hoger| Windows Phone 8.1 en hoger| iOS 6.0 en hoger|Android 4.0 en hoger<br/>Samsung KNOX Standard 4.0 of hoger|
|-----|----|----|----|----|
|**Configuratie van pincode of wachtwoord** |Hersteld|Hersteld|Hersteld|In quarantaine|
|**Apparaatversleuteling**|N.v.t.|Hersteld|Hersteld (door een pincode in te stellen)|In quarantaine|
|**Opengebroken of geroot apparaat**|N.v.t.|N.v.t.|In quarantaine (geen instelling)|In quarantaine (geen instelling)|
|**E-mailprofiel**|N.v.t.|N.v.t.|In quarantaine|N.v.t.|
|**Minimale versie van het besturingssysteem**|In quarantaine|In quarantaine|In quarantaine|In quarantaine|
|**Maximale versie van het besturingssysteem**|In quarantaine| In quarantaine| In quarantaine| In quarantaine|
|**Windows-statusverklaring**|Windows 10 en Windows 10 Mobile zijn in quarantaine geplaatst.<br /><br />Deze instelling is niet van toepassing op Windows 8.1.|N.v.t.|N.v.t.|N.v.t.|
--------------
**Hersteld**: naleving wordt afgedwongen door het besturingssysteem van het apparaat (de gebruiker moet bijvoorbeeld een pincode instellen).  Het komt dan nooit voor dat de instelling niet aan de voorwaarden voldoet.

**In quarantaine**: het besturingssysteem van het apparaat dwingt geen naleving af (gebruikers hoeven hun Android-apparaat bijvoorbeeld niet per se te versleutelen). Als het apparaat niet compatibel is, worden de volgende acties uitgevoerd:

-   Het apparaat wordt geblokkeerd als de gebruiker niet in naleving handelt van een beleid voor voorwaardelijke toegang.

-   De bedrijfsportal stelt de gebruiker op de hoogte van nalevingsproblemen.

## Volgende stappen
[Een nalevingsbeleid voor apparaten maken](create-a-device-compliance-policy-in-microsoft-intune.md)

[Een nalevingsbeleid voor apparaten implementeren en bewaken](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### Zie tevens
[De toegang tot e-mail en O365-services beperken](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)



<!--HONumber=Sep16_HO1-->


