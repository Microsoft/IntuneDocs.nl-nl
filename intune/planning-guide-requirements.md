---
title: Vereisten voor gebruiksscenario's bepalen
description: U kunt aan de hand van dit artikel vereisten bepalen voor gebruiksscenario's en subgebruiksscenario's voor een Microsoft Intune-cloudimplementatie.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 65a1fb8fb41fa8d9f3e707c73bf752a997a8a1a1
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/01/2017
---
# <a name="determine-use-case-scenario-requirements"></a>Vereisten voor gebruiksscenario's bepalen

In deze sectie bepaalt u de vereisten voor elke organisatiegroep in elk gebruiksscenario. Met het doorlopen van deze procedure bereidt u zich gelijk voor op de andere gebieden van de Intune-implementatieplanning, zoals de architectuur en het ontwerp, de onboarding en implementatie. U kunt aan de hand hiervan ook mogelijke hiaten en uitdagingen met betrekking tot uw Intune-implementatieproject vaststellen.

Mogelijk zijn er verschillende vereisten voor elk van uw gebruiksscenario's en subgebruiksscenario's en de daaraan gekoppelde organisatiegroepen en platformen voor mobiele apparaten. Mogelijk moeten volgens de vereisten van uw bedrijfsgebruiksscenario bijvoorbeeld de apparaten bij Intune worden ingeschreven met meer beperkingen in de apparaatinstellingen, zoals een pincode van zes tekens of een uitgeschakelde cloudback-up. Voor uw BYOD-gebruiksscenario (Bring Your Own Device) kunnen minder beperkende instellingen gelden en kan een pincode van vier tekens en een cloudback-up zijn toegestaan.

Er zijn mogelijk ook organisatiegroepen voor uw bedrijfsgebruiksscenario waarvoor verschillende vereisten gelden (bijvoorbeeld pincode-instellingen, Wi-Fi- of VPN-profiel, apps die worden geïmplementeerd). De vereisten kunnen ook worden bepaald door de mogelijkheden van het platform voor mobiele apparaten (zoals vingerafdruklezer, e-mailprofiel).

Hier volgen enkele voorbeelden van gebruikssituatievereisten van een organisatie met verschillende vereisten voor elk gebruiksscenario en subgebruiksscenario, elke organisatiegroep en elk platform voor mobiele apparaten. U kunt ook de volgende tabel gebruiken om de gebruikssituatievereisten van uw organisatie in te voeren:

| **Use cases** | **Subgebruikssituaties** | **Groepen** | **Apparaatplatformen** | **Requirements** |
|:---:|:---:|:---:|:---:|:---:|
| Zakelijk | Informatiemedewerker | HR, Financiën | iOS | Beveiligde e-mail, apparaatinstellingen, profielen, apps |                                                          
| Zakelijk | Leidinggevenden | HR, Financiën | iOS | Beveiligde e-mail, apparaatinstellingen, profielen, apps |                                                         
| Zakelijk | Kiosk | Retail | Android | Apparaatinstellingen, profielen, apps |
| BYOD | Informatiemedewerker | Marketing, Verkoop | iOS | Beveiligde e-mail, apparaatinstellingen, profielen, apps |                                                         
| BYOD | Leidinggevenden | Marketing, Verkoop | iOS | Beveiligde e-mail, apparaatinstellingen, profielen, apps |

U kunt [een sjabloon van de bovenstaande tabel downloaden](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) om de gebruikssituatievereisten en subgebruikssituatievereisten van uw organisatie in te voeren.


## <a name="examples-of-requirements"></a>Voorbeelden van vereisten

Hier zijn nog enkele voorbeelden die kunnen worden gebruikt in de kolom Vereisten:

- **Beveiligde e-mail**
    - Voorwaardelijke toegang voor Exchange Online/On-Premises
    - Beveiligingsbeleid voor de Outlook-app

- **Apparaatinstellingen**
    - Pincode-instelling met vier, zes tekens
    - Cloudback-up beperken

- **Profielen**
    - Wi-Fi
    - VPN
    - E-mail (Windows 10 Mobile)

- **Apps**
    - Office 365 met beleid voor app-beveiliging
    - Line-of-business (LOB) met beleid voor app-beveiliging

## <a name="next-steps"></a>Volgende stappen

De volgende sectie bevat richtlijnen over het [ontwikkelen van een Intune-rolloutplan](planning-guide-rollout-plan.md).
