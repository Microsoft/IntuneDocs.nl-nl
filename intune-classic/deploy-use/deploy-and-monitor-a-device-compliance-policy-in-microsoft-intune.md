---
title: Nalevingsbeleid implementeren en bewaken
description: Volg de stapsgewijze instructies in dit onderwerp om een nalevingsbeleid voor apparaten te implementeren en te bewaken.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 11/14/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d8f246d4-0d86-4c8b-a1bf-9977985506d8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e24c969206d3e1f34bfee0af46c4398c9d2739a8
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune"></a>Nalevingsbeleid voor apparaten implementeren en bewaken in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="deploy-a-compliance-policy"></a>Een nalevingsbeleid implementeren
Implementeer het nalevingsbeleid dat u hebt [gemaakt](create-a-device-compliance-policy-in-microsoft-intune.md) voor een of meer groepen gebruikers in uw organisatie. Wanneer er nalevingsbeleid wordt geïmplementeerd voor een gebruiker, worden de apparaten van de gebruiker gecontroleerd op naleving.

1.  Selecteer in de werkruimte **Beleid** het beleid dat u wilt implementeren en kies vervolgens **Implementatie beheren**.
![Schermafbeelding van de pagina voor het nalevingsbeleid waarin boven de menuoptie Implementatie beheren wordt weergegeven](./media/intune-sa-3c-deploy-compliance-policy2.png)

2.  Kies in het dialoogvenster **Implementatie beheren** een of meer groepen waarvoor u het beleid wilt implementeren, en kies vervolgens **Toevoegen** > **OK**.
![Schermafbeelding van het dialoogvenster Implementatie beheren](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png) Gebruik Active Directory-groepen die u al hebt gemaakt en met Intune hebt gesynchroniseerd, of maak deze groepen handmatig in de Intune-console. Zie [Een configuratiebeleid implementeren](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) voor meer informatie over het implementeren van beleid.

Gebruik het statusoverzicht en de waarschuwingen op de pagina **Overzicht** van de werkruimte **Beleid** om beleidsproblemen te identificeren die uw aandacht vereisen. Bovendien wordt er een statusoverzicht weergegeven in de werkruimte **Dashboard** .

> [!IMPORTANT]
> Als u geen nalevingsbeleid hebt geïmplementeerd en daarna een Exchange-beleid met voorwaardelijke toegang inschakelt, krijgen alle apparaten uit de doelgroep toegang.

## <a name="monitor-the-compliance-policy"></a>Het nalevingsbeleid bewaken

#### <a name="to-view-devices-that-do-not-conform-to-a-compliance-policy"></a>Apparaten weergeven die niet voldoen aan een nalevingsbeleid

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Groepen** > **Alle apparaten**.

2.  Dubbelklik op de naam van een apparaat in de lijst met apparaten.

3.  Kies het tabblad **Beleid** om een lijst met de beleidsregels voor dat apparaat weer te geven.

4.  Kies in de vervolgkeuzelijst **Filters** de optie **Voldoet niet aan het nalevingsbeleid**.
![Schermafbeelding van de lijst met opties in de lijst met filters](./media/intune-sa-3e-view-device-noncompliance.png)

#### <a name="to-view-the-health-attestation-reports"></a>Health Attestation-rapporten weergeven

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Rapporten**.

2.  Op de pagina **Health Attestation-rapporten - een nieuw rapport maken** kunt u een rapport bekijken met alle Health Attestation-gegevens van Windows 10 die door Intune zijn verzameld. Met de filters kunt u ook een rapport maken met een subset van de gegevens. De filters kunnen worden gebaseerd op het type apparaat, op het besturingssysteem of op een subset van gegevenspunten.

## <a name="how-intune-resolves-policy-conflicts"></a>Hoe Intune beleidsconflicten oplost
Conflicterende beleidsinstellingen kunnen zich voordoen wanneer er meerdere Intune-beleidsregels op een apparaat worden toegepast. Als de beleidsinstellingen elkaar overlappen, lost Intune de conflicten aan de hand van de volgende regels op:

-   Als de conflicterende instellingen uit een Intune-configuratiebeleid en een nalevingsbeleid voortkomen, hebben de instellingen in het nalevingsbeleid prioriteit boven de instellingen in het configuratiebeleid. Dit gebeurt zelfs als de instellingen in het configuratiebeleid veiliger zijn.

-   Als u meerdere nalevingsbeleidsregels hebt geïmplementeerd, wordt het veiligste beleid gebruikt.

## <a name="next-steps"></a>Volgende stappen
Zie [De toegang tot e-mail en O365-services beperken](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) voor informatie over u het nalevingsbeleid met beleidsregels voor voorwaardelijke toegang kunt gebruiken om de toegang tot services in uw organisatie te beheren.


### <a name="see-also"></a>Zie ook
[Inleiding in nalevingsbeleid voor apparaten in Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md)
