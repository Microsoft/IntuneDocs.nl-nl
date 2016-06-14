---
# required metadata

title: Beleidsinstellingen in Microsoft Intune voor upgrades van de Windows-editie | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Beleidsinstellingen in Microsoft Intune voor upgrades van de Windows-editie
Met het **Beleid voor editie-upgrades** kunt u apparaten waarop een van de volgende edities van Windows 10 wordt uitgevoerd, automatisch een upgrade naar een nieuwere editie laten uitvoeren:
* Windows 10 Desktop
* Windows 10 Holographic

## Voordat u begint
Voordat u begint met het upgraden van apparaten naar de nieuwste versie, hebt u een van de volgende items nodig:
* Een productcode die geldig is voor het installeren van de nieuwe versie van Windows op alle apparaten waarop het beleid is gericht (voor edities van Windows 10 Desktop)
* Een licentiebestand van Microsoft met de licentiegegevens voor het installeren van de nieuwe versie van Windows op alle apparaten waarop het beleid is gericht (voor edities van Windows 10 Mobile en Windows 10 Holographic).
* De Windows 10-apparaten waarop u zich richt, moeten zijn ingeschreven bij Microsoft Intune.

## Beleidsinstellingen voor editie-upgrades

|Naam van de instelling|Details|
|-|-|
|**Naam**|Geef een naam op voor het beleid voor editie-upgrades.|
|**Beschrijving**|Geef eventueel een beschrijving op voor het beleid, zodat u dit kunt herkennen in de Intune-console.
|**Editie bijwerken naar**|Selecteer in de vervolgkeuzelijst de versie van Windows 10 Desktop, Windows 10 Holographic of Windows 10 Mobile waarnaar u de apparaten uit de doelgroep wilt bijwerken.
|**Productcode**|Geef de productcode op die u van Microsoft hebt ontvangen en die kan worden gebruikt om van alle beoogde Windows 10 Desktop-apparaten een upgrade uit te voeren.<br>Nadat u een beleid met een productcode hebt gemaakt, kunt u de productcode later niet meer bewerken. Dit komt doordat de code uit veiligheidsoverwegingen wordt verborgen. Als u de productcode wilt wijzigen, moet u de volledige code opnieuw invoeren.
|**Licentiebestand**|Klik op **Bladeren** om het licentiebestand te selecteren dat u hebt ontvangen van Microsoft, met daarin licentie-informatie voor de Windows Holographic-editie waarnaar u de beoogde apparaten wilt upgraden.

### Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

<!--HONumber=May16_HO1-->


