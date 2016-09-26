---
title: Toegang beperken met beveiliging tegen mobiele bedreigingen | Microsoft Intune
description: De toegang tot bedrijfsbronnen beperken op basis van apparaat, netwerk en toepassingsrisico.
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 61480eb11cc8f4b6b336e48a50c2fe1b5fcd3fac
ms.openlocfilehash: c05dfc8154cd13b74f42b4f63262613be8956d87


---

# De toegang tot bedrijfsbronnen beperken op basis van apparaat, netwerk en toepassingsrisico
U kunt de toegang van mobiele apparaten tot bedrijfsbronnen met Lookout regelen op basis van risicoanalyse. Dit is een Mobile Threat Protection-oplossing (MTP) die met Microsoft Intune is geïntegreerd. Het risico wordt gebaseerd op telemetriegegevens voor beveiligingsproblemen van besturingssystemen, geïnstalleerde apps die schadelijk zijn en netwerkprofielen. Deze gegevens worden met de Lookout MTP-service van apparaten verzameld. Op basis van de risicoanalyse kunt u vervolgens in Intune een beleid voor voorwaardelijke toegang configureren. Ook kunt u apparaten toestaan of weigeren die als niet-compatibel zijn beoordeeld vanwege bedreigingen die op deze apparaten zijn gedetecteerd.  Dit wordt momenteel alleen ondersteund voor **Android**-apparaten met **4.1 en hoger** die bij Microsoft Intune zijn geregistreerd.  
## Welk probleem wordt hiermee opgelost?
Bedrijven en organisaties moeten gevoelige gegevens tegen nieuwe bedreigingen beschermen. Denk daarbij aan fysieke bedreigingen, apps die een bedreiging vormen, bedreigingen in het netwerk en beveiligingsproblemen van besturingssystemen.

Bedrijven en organisaties hebben pc’s altijd al actief beschermd tegen aanvallen. Mobiele apparaten vormen een opkomend terrein dat vaak niet wordt beveiligd. Hoewel het besturingssysteem van mobiele platformen wordt beschermd met behulp van een geïntegreerde beveiliging, zoals de isolatie van apps en gescreende app-stores, blijven deze platformen kwetsbaar voor geavanceerde aanvallen. Werknemers gebruiken mobiele apparaten steeds vaker om te werken en informatie die gevoelig en waardevol kan zijn te openen. Deze apparaten moeten dan ook worden beveiligd tegen allerlei geavanceerde aanvallen.

Met Intune kunt u de toegang tot bedrijfsbronnen en -gegevens beheren op basis van risicoanalyse met MTP-oplossingen zoals Lookout.

## Hoe kunnen bedrijfsbronnen met Intune en Lookout Mobile Threat Protection worden beveiligd?
Met de mobiele app Lookout (Lookout for Work) die op mobiele apparaten wordt uitgevoerd, worden telemetriegegevens van bestandssystemen, netwerkstacks, apparaten en toepassingen vastgelegd (indien beschikbaar) en naar de cloudservice Lookout Mobile Threat Protection (MTP) verzonden. Vervolgens wordt het totale risico van mobiele bedreigingen voor apparaten berekend. U kunt ook de indeling van het risiconiveau voor de bedreigingen in de MTP-console wijzigen volgens uw vereisten.  
Het nalevingsbeleid van Intune bevat nu een nieuwe regel voor Lookout Mobile Threat Protection. Deze regel is op de risicoanalyse van Lookout MTP gebaseerd. Als deze regel is ingeschakeld, wordt in Microsoft Intune gecontroleerd of het apparaat voldoet aan het beleid dat u hebt ingeschakeld.

Als blijkt dat het apparaat niet aan het nalevingsbeleid voldoet, kan de toegang tot bronnen, zoals Exchange Online en SharePoint Online, worden geblokkeerd met behulp van beleid voor voorwaardelijke toegang. Wanneer de toegang is geblokkeerd, ontvangen de eindgebruikers een walkthrough waarmee ze het probleem kunnen oplossen en toegang krijgen tot bedrijfsbronnen. Deze walkthrough wordt geopend in de Lookout for Work-app.

## Voorbeeldscenario’s
Hieronder volgen enkele algemene scenario's:
### Bedreiging door schadelijke apps:
Wanneer schadelijke apps, zoals malware, op het apparaat worden gedetecteerd, kunt u voorkomen dat met deze apparaten:
* De bedrijfs-e-mail wordt geopend voordat de bedreiging is opgelost.
* Zakelijke bestanden worden gesynchroniseerd met de app OneDrive voor werk.
* Bedrijfskritische apps worden geopend.

**Toegang geblokkeerd als schadelijke apps worden gedetecteerd:**
![diagram dat laat zien hoe de toegang wordt geblokkeerd met het beleid voor voorwaardelijke toegang wanneer blijkt dat het apparaat niet-compatibel is vanwege schadelijke apps op het apparaat.](../media/mtp/malicious-apps-blocked.png)

**Apparaat gedeblokkeerd en bedrijfsbronnen kunnen worden geopend wanneer de bedreiging is verwijderd:**

![Diagram dat laat zien hoe toegang wordt verkregen met het beleid voor voorwaardelijke toegang wanneer blijkt dat het apparaat compatibel is na herstel.](../media/mtp/malicious-apps-unblocked.png)
### Bedreiging voor netwerk:
Bedreigingen voor uw netwerk worden gedetecteerd, zoals man-in-the-middle-aanvallen, en de toegang tot wifi-netwerken wordt beperkt op basis van apparaatrisico.

**Toegang tot het netwerk via wifi geblokkeerd:**
![diagram dat laat zien hoe de toegang via wifi wordt geblokkeerd met voorwaardelijke toegang op basis van netwerkbedreigingen.](../media/mtp/network-wifi-blocked.png)

**Toegang na herstel:**

![Diagram dat laat zien hoe de toegang na verwijdering van de bedreiging met voorwaardelijke toegang wordt toegestaan.](../media/mtp/network-wifi-unblocked.png)
### Bedreiging voor netwerk (geen toegang tot SharePoint Online):

Bedreigingen voor uw netwerk worden gedetecteerd, zoals man-in-the-middle-aanvallen, en synchronisatie van bedrijfsbestanden wordt voorkomen op basis van het apparaatrisico.

**Toegang tot SharePoint Online geblokkeerd op basis van een netwerkbedreiging op het apparaat:**

![Diagram dat laat zien hoe de toegang met het apparaat tot SharePoint Online op basis van bedreigingsdetectie met voorwaardelijke toegang wordt geblokkeerd.](../media/mtp/network-spo-blocked.png)


**Toegang na herstel:**

![Diagram dat laat zien hoe de toegang na verwijdering van de netwerkbedreiging wordt toegestaan met voorwaardelijke toegang.](../media/mtp/network-spo-unblocked.png)

## Volgende stappen
Hier volgen de belangrijkste stappen voor het implementeren van deze oplossing:
1.  [Uw abonnement instellen met Lookout Mobile Threat Protection](set-up-your-subscription-with-lookout-mtp.md)
2.  [Lookout MTP-verbinding in Intune inschakelen](enable-lookout-mtp-connection-in-intune.md)
3.  [De Lookout for Work-toepassing configureren en implementeren](configure-and-deploy-lookout-for-work-apps.md)
4.  [Nalevingsbeleid configureren](enable-device-threat-protection-rule-in-compliance-policy.md)
5.  [Problemen met de integratie van Lookout oplossen](http://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration.md)



<!--HONumber=Sep16_HO2-->


