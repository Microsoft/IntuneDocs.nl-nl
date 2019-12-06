---
title: Een MTD-nalevingsbeleid voor apparaten maken met Microsoft Intune
titleSuffix: Microsoft Intune
description: Maak een Intune-nalevingsbeleid voor apparaten waarbij gebruik wordt gemaakt van de bedreigingsniveaus van uw MTD-partner om te bepalen of een mobiel apparaat toegang mag hebben tot bedrijfsresources.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 504c77fb56918cf97312e70f50b38356f9f7efef
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/22/2019
ms.locfileid: "74409701"
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>MTD-nalevingsbeleid (Mobile Threat Defense) voor apparaten maken met Intune

Intune met MTD helpt u bij het detecteren van bedreigingen en het beoordelen van risico op mobiele apparaten. U kunt een Intune-nalevingsbeleidsregel maken voor een risicoanalyse waarmee wordt bepaald of het apparaat compatibel is. Vervolgens kunt u [beleid voor voorwaardelijke toegang](create-conditional-access-intune.md) gebruiken om toegang tot services te blokkeren op basis van de apparaatnaleving.

> [!NOTE]
> Deze informatie is van toepassing op alle Mobile Threat Defense-partners.

## <a name="before-you-begin"></a>Voordat u begint

Als onderdeel van de configuratie van MTD in de MTD-partnerconsole, hebt u een beleid gemaakt waarmee verschillende bedreigingen in de categorieën Hoog, Gemiddeld en Laag worden ingedeeld. U moet nu het MTD-niveau instellen in het nalevingsbeleid van Intune voor apparaten.

Vereisten voor apparaatnalevingsbeleid met MTD:

- De integratie van MTD met Intune instellen

## <a name="to-create-an-mtd-device-compliance-policy"></a>Nalevingsbeleid voor MTD-apparaten maken

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Apparaat** > **Nalevingsbeleid** > **Beleid maken**.

3. Geef een **Naam**, **Beschrijving** op voor het nalevingsbeleid van het apparaat, selecteer het **Platform** en selecteer vervolgens **Configureren** onder de sectie **Instellingen**.

4. Kies in het deelvenster **Nalevingsbeleid** de optie **Apparaatstatus**.

5. Kies in het deelvenster **Apparaatstatus** het Mobile Threat-niveau uit de vervolgkeuzelijst bij **Vereisen dat het apparaat het apparaatdreigingsniveau niet overschrijdt**.

   - **Beveiligd**: Dit is het veiligste niveau. Het apparaat kan geen enkele bedreiging hebben en heeft nog altijd toegang tot bedrijfsbronnen. Als er bedreigingen worden gevonden, wordt het apparaat geëvalueerd als niet-compatibel.

   - **Laag**: het apparaat is conform als er alleen bedreigingen van een laag niveau aanwezig zijn. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.

   - **Gemiddeld**: het apparaat is conform als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als er bedreigingen van hoog niveau worden aangetroffen, wordt het apparaat als niet-compatibel beoordeeld.

   - **Hoog**: dit is het minst veilige niveau. Hiermee worden alle bedreigingsniveaus toegestaan en wordt Mobile Threat Defense uitsluitend gebruikt voor rapportagedoeleinden. Op apparaten moet de MTD-app met deze instelling zijn geactiveerd.

6. Selecteer tweemaal **OK** en vervolgens **Maken** om het beleid te maken.

> [!IMPORTANT]
> Als u beleid voor voorwaardelijke toegang voor Office 365 of andere services maakt, wordt de compatibiliteitsevaluatie van het apparaat bekeken en wordt niet-compatibele apparaten de toegang tot bedrijfsresources geweigerd tot de bedreiging op het apparaat is opgelost.

## <a name="to-assign-an-mtd-device-compliance-policy"></a>Nalevingsbeleid voor MTD-apparaten toewijzen

Een nalevingsbeleid voor apparaten aan gebruikers toewijzen:

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Apparaat** > **Nalevingsbeleid**.

3. Selecteer het beleid dat u aan gebruikers wilt toewijzen en kies vervolgens **Toewijzingen**. Gebruik de beschikbare opties *Opnemen* en *Uitsluiten* als u wilt dat groepen dit beleid al dan niet ontvangen.  

4. Selecteer Opslaan om de toewijzing te voltooien. Wanneer u de toewijzing opslaat, wordt het beleid naar de geselecteerde gebruikers geïmplementeerd en worden hun apparaten geëvalueerd op naleving.

## <a name="next-steps"></a>Volgende stappen

[MTD met Intune inschakelen](mtd-connector-enable.md)
