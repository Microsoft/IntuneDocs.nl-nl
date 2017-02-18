---
title: Use-casescenariovereisten voor Intune bepalen | Microsoft Docs
description: Dit artikel helpt bij het identificeren van vereisten voor use-case- en sub-use-casescenario&quot;s voor een cloudimplementatie van Microsoft Intune.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f807d6e4b20b98ecf622d1ebdd9db33b132a2e6a
ms.openlocfilehash: 91b25fe35c6a1f8a554d543ca005cc3b482f22d7


---

# <a name="determine-intune-use-case-scenario-requirements"></a>Use-casescenariovereisten voor Intune bepalen

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

In deze sectie bepaalt u de vereisten voor elke organisatiegroep binnen elk use-casescenario. Door dit proces te doorlopen kunt u zich beter voorbereiden op de andere gebieden van Intune-implementatieplanning zoals architectuur en ontwerp, onboarding en rollout. Het kan ook helpen om mogelijke hiaten en uitdagingen met betrekking tot uw implementatieproject voor Intune vast te stellen.

Wellicht hebt u verschillende sets van vereisten voor elk van uw use-case-/sub-use-casescenario's en de bijbehorende organisatiegroepen en platformen voor mobiele apparaten. Een voorbeeld. Voor de use-casescenariovereisten van uw organisatie moeten apparaten worden geregistreerd bij Intune met een reeks apparaatinstellingen (bijvoorbeeld een pincode van 6 tekens, uitschakelen van back-up in de cloud), die meer beperkingen heeft dan het BYOD-use-casescenario (Bring Your Own Device), waarvoor minder beperkte instellingen nodig zijn (zoals een pincode van 4 tekens, back-up in de cloud toegestaan).

Mogelijk zijn er ook organisatiegroepen voor een use-casescenario met verschillende sets aan vereisten (bijvoorbeeld pincode-instellingen, Wi-Fi- of VPN-profiel, apps die worden geïmplementeerd). Bovendien kunnen de vereisten afhankelijk zijn van de mogelijkheden van het platform voor mobiele apparaten (zoals vingerafdruklezer, e-mailprofiel).

Hier ziet u enkele voorbeelden van de use-casevereisten van een organisatie met verschillende sets aan vereisten voor elk use-case-/sub-use-casescenario, elke organisatiegroep en elk platform voor mobiele apparaten. U kunt ook de volgende tabel gebruiken om de use-casevereisten van uw organisatie in te voeren:

| **Use cases** | **Sub-use-cases** | **Groepen** | **Besturingssysteem apparaatplatformen** | **Requirements** |
|:---:|:---:|:---:|:---:|:---:|
| Zakelijk | Informatiemedewerker | HR, Financiën | iOS | Beveiligde e-mail, apparaatinstellingen, profielen, apps |                                                          
| Zakelijk | Leidinggevenden | HR, Financiën | iOS | Beveiligde e-mail, apparaatinstellingen, profielen, apps |                                                         
| Zakelijk | Kiosk | Retail | Android | Apparaatinstellingen, profielen, apps |
| BYOD | Informatiemedewerker | Marketing, Verkoop | iOS | Beveiligde e-mail, apparaatinstellingen, profielen, apps |                                                         
| BYOD | Leidinggevenden | Marketing, Verkoop | iOS | Beveiligde e-mail, apparaatinstellingen, profielen, apps |

## <a name="examples-of-requirements"></a>Voorbeelden van vereisten

Hier zijn enkele voorbeelden die kunnen worden gebruikt in de kolom 'Vereisten' waarnaar wordt verwezen in de bovenstaande tabel:

- **Beveiligde e-mail**
    - Voorwaardelijke toegang voor Exchange Online/On-Premises
    - Beveiligingsbeleid voor de Outlook-app
<br></br>
- **Apparaatinstellingen**
    - Pincode-instelling met vier, zes tekens
    - Cloudback-up beperken
<br></br>
- **Profielen**
    - Wi-Fi
    - VPN
    - E-mail (Windows 10 Mobile)
<br></br>
- **Apps**
    - Office 365 met beleid voor app-beveiliging
    - Line-of-business (LOB) met beleid voor app-beveiliging

## <a name="next-section"></a>Volgende sectie

De volgende sectie bevat richtlijnen over het [ontwikkelen van een Intune-rolloutplan](section-4-develop-a-rollout-plan.md).



<!--HONumber=Dec16_HO5-->


