---
title: De regel Device Threat Protection inschakelen in het nalevingsbeleid | Microsoft Intune
description: De regel Mobile Threat Protection inschakelen in het nalevingsbeleid van het apparaat.
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9c2ffb5fe497d56d8250fe3dec7db606c2067a1c
ms.openlocfilehash: 761372b2c8b81699bc2584ab1ef8d0f9d523abe9


---

# De regel Device Threat Protection inschakelen in het nalevingsbeleid
Met Intune en Lookout Mobile Threat Protection kunt u mobiele bedreigingen detecteren en een risicoanalyse maken op het apparaat.  
Met een nalevingsbeleidsregel kunt u deze risicoanalyse gebruiken om te bepalen of het apparaat aan uw beleid voldoet. Vervolgens kunt u het beleid voor voorwaardelijke toegang gebruiken om Exchange, SharePoint en andere services toe te staan of te blokkeren op basis van de apparaatcompatibiliteit.

Als de bedreigingsdetectie van Lookout MTP van invloed moet zijn op het nalevingsbeleid voor het apparaat:

1.  De regel **Device Threat Protection** moet zijn ingeschakeld in het nalevingsbeleid.

2.  De status op de pagina **Lookout-status** in de Intune-beheerconsole moet **Actief** zijn. Zie het onderwerp [Lookout MTP-verbinding in Intune inschakelen](enable-lookout-mtp-connection-in-intune.md) voor meer informatie en instructies over het activeren van de Lookout-integratie.


## De regel Device Threat Protection configureren

Voordat u de regel Device Threat Protection maakt in het nalevingsbeleid, raden we u aan uw [abonnement in te stellen met Lookout MTP](set-up-your-subscription-with-lookout-mtp.md), de [Lookout-verbinding in Intune in te schakelen](enable-lookout-mtp-connection-in-intune.md) en de [Lookout for Work-app te configureren](configure-and-deploy-lookout-for-work-apps.md). De nalevingsregel wordt alleen afgedwongen als de installatie is voltooid.

Als u de Device Threat Protection-regel wilt inschakelen, kunt u een bestaand nalevingsbeleid gebruiken of een nieuw beleid maken.

Als onderdeel van de configuratie van Lookout MTP in de [Lookout MTP-console](https://aad.lookout.com) hebt u een beleid gemaakt waarmee verschillende bedreigingen in de categorieën Hoog, Gemiddeld en Laag worden ingedeeld. In het nalevingsbeleid van Intune stelt u met het bedreigingsniveau het maximaal toegestane bedreigingsniveau in.

Ga in de Intune-beheerconsole op de pagina voor nalevingsbeleid naar **Apparaatstatus** en schakel de regel **Device Threat Protection** in met de wisselknop. Selecteer vervolgens het maximaal toegestane bedreigingsniveau. U kunt daarbij kiezen uit:
* **Geen (beveiligd)**: dit is het meest veilige niveau.  Dit betekent dat er op het apparaat geen bedreigingen mogen staan.  Als een van de bedreigingsniveaus voor het apparaat wordt gedetecteerd, wordt het apparaat geëvalueerd als niet-compatibel.  
* **Laag**: het apparaat wordt als compatibel geëvalueerd als er bedreigingen van een laag niveau op staan. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
* **Gemiddeld**: het apparaat wordt als compatibel geëvalueerd als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als bedreigingen met hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-compatibel beoordeeld.
* **Hoog**: dit is de minst veilige optie. Het komt erop neer dat alle bedreigingniveaus worden toegestaan. Dit is mogelijk alleen nuttig als u deze oplossing slechts voor rapportagedoeleinden gebruikt.

![schermopname met de instelling voor de regel Device Threat Protection ](../media/mtp/mtp-compliance-policy-rule.png)

![schermopname met de optie voor het bedreigingsniveau voor de instelling voor de regel Device Threat Protection](../media/mtp/mtp-compliance-policy-setting.png)

Als u beleid voor voorwaardelijke toegang voor O365 en andere services maakt, wordt bovenstaande compatibiliteitsevaluatie in acht genomen en wordt niet-compatibele apparaten de toegang geweigerd tot de bedreiging is opgelost.

U kunt de compatibiliteitsstatus van een apparaat bekijken op de pagina Apparaten van de Intune-beheerconsole.

![schermopname van de pagina Apparaten in de Intune-beheerconsole waarop de compatibiliteitsstatus van een apparaat is weergeven](../media/mtp/mtp-device-status-intune-console.png)

## Volgende stappen
* Beleid voor voorwaardelijke toegang maken
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange On-premises](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype voor Bedrijven Online](restrict-access-to-skype-for-business-online-with-microsoft-intune,md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Sep16_HO2-->


