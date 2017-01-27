---
title: De regel voor apparaatbeveiliging inschakelen | Microsoft Docs
description: De regel Mobile Threat Protection inschakelen in het nalevingsbeleid van het apparaat.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9f05e516723976dcf6862475dbb78f9dce2913be
ms.openlocfilehash: 08edca426901eda3017bf17dda3b330dd186ce58


---

# <a name="enable-device-threat-protection-rule-in-the-compliance-policy"></a>De regel Device Threat Protection inschakelen in het nalevingsbeleid

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Met Intune met Lookout Mobile Threat Protection kunt u bedreigingen op mobiele apparaten detecteren en de risico's op die apparaten beoordelen. U kunt een nalevingsbeleidsregel maken voor risicoanalyse om te bepalen of het apparaat compatibel is. Vervolgens kunt u beleid voor voorwaardelijke toegang gebruiken om toegang tot services te blokkeren op basis van de apparaatcompatibiliteit.

Vereisten voor nalevingsbeleid met Lookout Device Threat Protection:

- [Abonnement op Lookout Device Threat Protection](set-up-your-subscription-with-lookout-mtp.md)
- [De Lookout-verbinding in Intune inschakelen](enable-lookout-mtp-connection-in-intune.md)
- [De Lookout for Work-app configureren](configure-and-deploy-lookout-for-work-apps.md)

Als onderdeel van de configuratie van Lookout Device Threat Protection in de [Lookout-console](https://aad.lookout.com) hebt u een beleid gemaakt waarmee verschillende bedreigingen in de categorieën Hoog, Gemiddeld en Laag worden ingedeeld. In het nalevingsbeleid van Intune stelt u het maximaal toegestane bedreigingsniveau in.

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



<!--HONumber=Jan17_HO4-->


