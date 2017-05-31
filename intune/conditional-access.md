---
title: Wat is voorwaardelijke toegang?
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: meer informatie over het definiëren van de voorwaarden waaraan gebruikers en apparaten moeten voldoen voor toegang tot bedrijfsresources in Microsoft Intune Azure Preview."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 8ab6d782460a857a0901abd9bd567365ee2e3f70
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="what-is-conditional-access"></a>Wat is voorwaardelijke toegang?


[!INCLUDE[azure_preview](./includes/azure_preview.md)]


In dit onderwerp wordt voorwaardelijke toegang beschreven omdat deze van toepassing op Enterprise Mobility + Security. Vervolgens worden de mogelijkheden voor voorwaardelijke toegang in Intune beschreven.

Voor voorwaardelijke toegang van Enterprise Mobility + Security (EMS) wordt gebruikgemaakt van de kracht van Azure Active Directory Premium en Microsoft Intune om uw bedrijfsgegevens veilig te houden, terwijl uw medewerkers kunnen werken vanaf elk apparaat.

Met voorwaardelijke toegang kunt u voorwaarden opgeven die de toegang tot uw bedrijfsgegevens beperken op basis van de locatie, de apparaat- en gebruikersstatus en de gevoeligheid van een toepassing.

Met betrekking tot het apparaat werken Intune en Azure Active Directory samen om ervoor te zorgen dat alleen beheerde en compatibele apparaten toegang kunnen krijgen tot e-mail en Office 365-services. U kunt bijvoorbeeld een beleid instellen in Azure Active Directory zodat alleen computers die zijn toegevoegd aan een domein of mobiele apparaten die zijn ingeschreven in een beheertoepassing voor mobiele apparaten, zoals Intune, toegang kunnen hebben tot Office 365-services. Met Intune kunt u een nalevingsprofiel voor een apparaat instellen waarmee de nalevingsstatus van het apparaat wordt vastgesteld. De nalevingsstatus wordt gerapporteerd aan Azure Active Directory voor afdwinging van het beleid in Azure Active Directory als de gebruiker toegang tot uw bedrijfsresources probeert te krijgen. Zie [Wat is apparaatcompatibiliteit?](device-compliance.md) voor meer informatie over apparaatcompatibiliteit in Intune.

Voorwaardelijke toegang voor cloud-apps, zoals Exchange Online, kan worden geconfigureerd via Azure Active Directory. Zie dit [artikel](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) voor meer informatie.

## <a name="on-premises-conditional-access-in-intune"></a>Voorwaardelijke on-premises toegang in Intune

Voorwaardelijke toegang in Intune kan worden gebruikt voor **toegang voor Exchange On-premises** op basis van het apparaatbeheer en de inschrijving.

Op basis van de instellingen voor nalevingsbeleid wordt beoordeeld in hoeverre het apparaat het geldende beleid naleeft. De beoordeling van voorwaardelijke toegang wordt gebruikt om toegang voor Exchange On-premises te blokkeren of toe te staan. Wanneer voorwaardelijke toegang wordt gebruikt in combinatie met een nalevingsbeleid voor apparaten, hebben alleen apparaten die voldoen aan het beleid toegang voor Exchange On-premises. U kunt geavanceerde instellingen configureren in voorwaardelijke toegang voor gedetailleerdere controle, zoals: toestaan of blokkeren van bepaalde platformen of apparaten die niet worden beheerd door Intune onmiddellijk te blokkeren.

Het nalevingsprofiel voor een apparaat en voorwaardelijke toegang worden toegewezen aan de gebruiker. Een apparaat dat de gebruiker gebruikt voor toegang voor Exchange On-premises wordt gecontroleerd op naleving van het beleid. Houd er rekening mee dat er nalevingsbeleid moet worden toegewezen aan de gebruiker van het apparaat, zodat de naleving door het apparaat kan worden beoordeeld. Als er geen nalevingsbeleid wordt geïmplementeerd voor de gebruiker, wordt het apparaat beschouwd als een apparaat dat voldoet aan het beleid en worden er geen toegangsbeperkingen toegepast.

Wanneer apparaten niet voldoen aan de gestelde voorwaarden, wordt de eindgebruiker geleid door de procedure voor het registreren van het apparaat en het verhelpen van het probleem dat verhindert dat het apparaat compatibel is.

## <a name="next-steps"></a>Volgende stappen

[Beleid maken voor voorwaardelijke toegang voor Exchange On-premises](conditional-access-exchange-create.md)

[Voorwaardelijke toegang in Azure Active Directory configureren](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

