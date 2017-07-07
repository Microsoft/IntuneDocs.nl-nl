---
title: Een nalevingsbeleid voor apparaten maken
description: Een nalevingsbeleid maken voor het beveiligen van mobiele apparaten en pc's die worden gebruikt voor toegang tot uw bedrijfsgegevens.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5336dac0-a2cc-4cd4-8511-67e4f95bd700
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3dcafbd3cfdbccdfa851e8d21572d834d629564b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="create-a-device-compliance-policy-in-microsoft-intune"></a>Een nalevingsbeleid voor apparaten maken in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In dit onderwerp worden de stappen beschreven die u kunt volgen om nalevingsbeleid te maken waaraan een apparaat zich moet houden om aan dat beleid te voldoen.

##  <a name="step-1-add-a-new-policy"></a>Stap 1: Een nieuw beleid toevoegen
  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Beleid** &gt; **Nalevingsbeleid** &gt; **Toevoegen**.

  ![Schermafbeelding van de pagina met nalevingsbeleid in de Intune-beheerconsole, waarop de optie Toevoegen in het menu boven aan de pagina wordt weergegeven](./media/intune-sa-3a-add-compliance-policy.png)

##  <a name="step-2--configure-settings"></a>Stap 2: Instellingen configureren
Op de pagina **Beleid maken** configureert u de instellingen die u nodig hebt:
  -   De systeembeveiligingsinstellingen, zoals wachtwoorden en versleuteling.
  -   De apparaatstatusinstellingen, zoals of een apparaat is gekraakt of door de Windows-apparaatstatusservice Health Attestation als in orde wordt gerapporteerd.
  -   Instellingen voor apparaateigenschappen, zoals de minimaal vereiste versie van het besturingssysteem of de maximale versie van het besturingssysteem die is toegestaan.
![Het tabblad Algemeen van de pagina Beleid maken](./media/intune-sa-3b-create-policy.png)


##  <a name="step-3-save-the-policy"></a>Stap 3: Het beleid opslaan
Als u klaar bent, kiest u **Beleid opslaan**.

U hebt de optie om het beleid direct na het opslaan te implementeren, maar u kunt het beleid ook later implementeren. Het nieuwe beleid wordt weergegeven in het knooppunt **Nalevingsbeleid** van de werkruimte **Beleid**.

##  <a name="step-4-set-the-compliance-status-validity-period"></a>Stap 4: de geldigheidsperiode voor de nalevingsstatus instellen
Als u de tijd wilt opgeven die het apparaat heeft om in te checken voordat een apparaat als niet compatibel wordt gezien, gaat u naar de instellingen voor het nalevingsbeleid en werkt u de tijd bij. De standaardwaarde is ingesteld op 30 dagen.

![Instellingen voor nalevingsbeleid in de beleidsmenubalk](../media/mdm-compliance-policy-settings.png)

![Dialoogvenster voor nalevingsbeleid](../media/mdm-ca-compliance-status-validity-period.png)

## <a name="supported-policy-settings"></a>Ondersteunde beleidsinstellingen
In de volgende tabel staan de instellingen voor nalevingsbeleid en de platformen waarop deze worden ondersteund.

-------------
|Instelling|iOS|Android|Windows|
|-----|----|-----|-----|
|Wachtwoord vereist voor het ontgrendelen van mobiele apparaten|iOS 6 en hoger|Android 4.0 en hoger <br>Samsung KNOX Standard 4.0 of hoger|Windows Phone 8.1 en hoger|
|Eenvoudige wachtwoorden toestaan|iOS 6 en hoger|Niet ondersteund|Windows Phone 8.1 en hoger|
|Minimale wachtwoordlengte|iOS 6 en hoger| Android 4.0 en hoger<br>Samsung KNOX Standard 4.0 of hoger| Windows Phone 8.1 en hoger<br>Windows 8.1|
|Vereist wachtwoordtype|iOS 6 en hoger|Niet beschikbaar|Windows Phone 8.1 en hoger <br>Windows RT<br> Windows RT 8.1 <br>Windows 8.1|
|Minimum aantal tekensets|iOS 6 en hoger|Niet beschikbaar|Windows Phone 8.1 en hoger <br>Windows RT<br> Windows RT 8.1 <br>Windows 8.1|
|Wachtwoordkwaliteit|Niet beschikbaar|Android 4.0 en hoger <br>Samsung KNOX Standard 4.0 of hoger|Niet beschikbaar|
|Minuten inactief voordat wachtwoord is vereist|iOS 6 en hoger|Android 4.0 en hoger<br>Samsung KNOX Standard 4.0 of hoger|Windows Phone 8.1 en hoger<br>Windows RT en Windows RT 8.1<br>Windows 8.1|
|Wachtwoordverlooptijd (dagen)|iOS 6 en hoger|Android 4.0 en hoger<br>Samsung KNOX Standard 4.0 of hoger|Windows Phone 8.1 en hoger<br>Windows RT en Windows RT 8.1<br>Windows 8.1|
|Wachtwoordgeschiedenis onthouden|iOS 6 en hoger|Android 4.0 en hoger<br>Samsung KNOX Standard 4.0 of hoger|Windows Phone 8.1 en hoger<br>Windows RT en Windows RT 8.1<br>Windows 8.1|
|Wachtwoorden niet opnieuw gebruiken|iOS 6 en hoger|Android 4.0 en hoger<br>Samsung KNOX Standard 4.0 of hoger|Windows Phone 8.1 en hoger<br>Windows RT en Windows RT 8.1<br>Windows 8.1|
|Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status| Niet beschikbaar| Niet beschikbaar|Windows 10 Mobile|
|Versleuteling vereisen voor mobiel apparaat|Niet van toepassing|Android 4.0 en hoger<br>Samsung KNOX Standard 4.0 of hoger|Windows Phone 8.1 en hoger<br> Windows 8.1|
|Vereist dat apparaten als in orde worden gerapporteerd| Niet beschikbaar| Niet beschikbaar|Windows <br>Windows 10 Mobile|
|Het apparaat mag niet zijn gekraakt of geroot|iOS 6 en hoger|Android 4.0 en hoger<br>Samsung KNOX Standard 4.0 of hoger|Niet beschikbaar|
|E-mailaccounts moeten worden beheerd door Intune|iOS 6 en hoger|Niet beschikbaar| Niet beschikbaar|
|Het e-mailprofiel selecteren dat moet worden beheerd door Intune|iOS 6 en hoger|Niet beschikbaar| Niet beschikbaar|
|Minimale versie van het besturingssysteem dat is vereist|iOS 6 en hoger|Android 4.0 en hoger<br>Samsung KNOX Standard 4.0 of hoger| Windows Phone 8.1 en hoger<br>Windows 8.1|
|Maximale versie van het besturingssysteem dat is toegestaan|iOS 6 en hoger|Android 4.0 en hoger<br>Samsung KNOX Standard 4.0 of hoger|Windows Phone 8.1 en hoger<br>Windows 8.1|

Selecteer een van de volgende mogelijkheden voor meer informatie over instellingen voor naleving die op elk platform worden ondersteund:
> [!div class="op_single_selector"]
- [Instellingen voor nalevingsbeleid voor iOS-apparaten](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Instellingen voor nalevingsbeleid voor Android-apparaten](android-compliance-policy-settings-in-microsoft-intune.md)
- [Instellingen voor nalevingsbeleid voor Windows en Windows Phones ](windows-compliance-policy-settings-in-microsoft-intune.md)


## <a name="next-steps"></a>Volgende stappen
[Nalevingsbeleid implementeren en bewaken](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### <a name="see-also"></a>Zie tevens
[Inleiding in nalevingsbeleid voor apparaten](introduction-to-device-compliance-policies-in-microsoft-intune.md)
