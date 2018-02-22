---
title: Regel voor apparaatbeveiliging inschakelen
description: De regel Mobile Threat Protection inschakelen in het nalevingsbeleid van het apparaat.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f649227c6ad49cd9c788e75097bc4a5eeb71f350
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/30/2018
---
# <a name="create-lookout-device-compliance-policy-in-intune"></a>Het nalevingsbeleid voor Lookout-apparaten maken in Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Met Intune met Lookout Mobile Threat Defense kunt u bedreigingen op mobiele apparaten detecteren en de risico's op die apparaten beoordelen. U kunt een nalevingsbeleidsregel maken voor risicoanalyse om te bepalen of het apparaat compatibel is. Vervolgens kunt u beleid voor voorwaardelijke toegang gebruiken om toegang tot services te blokkeren op basis van de apparaatcompatibiliteit.

Vereisten voor het nalevingsbeleid bij Lookout Mobile Threat Defense:

- [Het Lookout Mobile Threat Defense-abonnement instellen](setup-your-lookout-mtd-subscription.md)
- [De Lookout-verbinding in Intune inschakelen](enable-lookout-mtd-connection.md)
- [De Lookout for Work-app configureren en implementeren](configure-deploy-lookout-for-work-app.md)

Als onderdeel van de configuratie van Lookout Mobile Threat Defense in de [Lookout-console](https://aad.lookout.com) hebt u een beleid gemaakt waarmee verschillende bedreigingen in de categorieën Hoog, Gemiddeld en Laag worden ingedeeld. In het nalevingsbeleid van Intune stelt u het maximaal toegestane bedreigingsniveau in.

1. In de [Intune-beheerconsole](https://manage.microsoft.com) gaat u naar de pagina **Nalevingsbeleid**. U kunt een bestaand nalevingsbeleid gebruiken of een nieuw beleid maken. Ga naar **Apparaatstatus** en schakel **Device Threat Protection** in.
  ![schermopname met de instelling voor de regel Device Threat Protection](../media/mtp/mtp-compliance-policy-rule.png)

2. Selecteer **Maximaal toegestaan bedreigingsniveau**:
  * **Geen (beveiligd)**: dit is het meest veilige niveau.  Het apparaat kan geen enkele bedreiging hebben en heeft nog altijd toegang tot bedrijfsbronnen.  Als er bedreigingen worden gevonden, wordt het apparaat geëvalueerd als niet-compatibel.  
  * **Laag**: het apparaat is compatibel als er alleen bedreigingen van een laag niveau aanwezig zijn. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  * **Gemiddeld**: het apparaat is compatibel als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als er bedreigingen van hoog niveau worden aangetroffen, wordt het apparaat als niet-compatibel beoordeeld.
  * **Hoog**: dit is de minst veilige optie. Hiermee worden alle bedreigingsniveaus toegestaan en Lookout Mobile Threat Protection wordt alleen voor rapportagedoeleinden gebruikt.

![schermopname met de optie voor het bedreigingsniveau voor de instelling voor de regel Device Threat Protection](../media/mtp/mtp-compliance-policy-setting.png)

Als u beleid voor voorwaardelijke toegang voor Office 365 of andere services maakt, wordt deze compatibiliteitsevaluatie bekeken en wordt niet-compatibele apparaten de toegang tot die services geweigerd tot de bedreiging is opgelost.

## <a name="monitor-device-threats"></a>Apparaatbedreigingen bewaken
Ga naar [Alle apparaten](https://manage.microsoft.com) in de **Intune-beheerconsole** om de compatibiliteitsstatus van een apparaat te bekijken.

![schermopname van de pagina Apparaten in de Intune-beheerconsole waarop de compatibiliteitsstatus van een apparaat is weergeven](../media/mtp/mtp-device-status-intune-console.png)

## <a name="next-steps"></a>Volgende stappen
* Beleid voor voorwaardelijke toegang maken
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange On-premises](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype voor Bedrijven Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)
