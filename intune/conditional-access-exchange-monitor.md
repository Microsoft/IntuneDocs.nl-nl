---
title: De naleving van voorwaardelijke toegang bewaken voor On-Premises Exchange en Exchange Online
titleSuffix: Intune on Azure
description: De naleving van voorwaardelijke toegang bewaken voor On-Premises Exchange en Exchange Online via de Intune Azure Portal
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2ec9bcc605486258203f49f9f7631bd2a04cdf22
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune"></a>De naleving van voorwaardelijke toegang in Intune controleren voor Exchange On-Premises en Exchange Online

Vanaf versie Intune 1704 kunnen beheerders informatie weergeven met betrekking tot Exchange ActiveSync-apparaatrecords die zijn gesynchroniseerd met Intune via de on-premises Exchange-connector of de Intune Service to Service Connector (Exchange Online-connector). De nalevingsrapporten van voorwaardelijke toegang biedt een overzicht van apparaten met verschillende synchronisatiestatussen:

-   **Toestaan**

-   **Blokkeren**

-   **Quarantaine**

## <a name="to-monitor-conditional-access-compliance"></a>Naleving van voorwaardelijke toegang bewaken

1.  Ga naar [Azure Portal](https://portal.azure.com/) en meld u aan met uw Intune-referenties.

2.  Nadat u zich hebt aangemeld, ziet u het **Azure-dashboard**.

3.  Kies **Meer services** in het linkermenu en typ dan **Intune** in het vak tekstfilter.

4.  Kies **Intune**. Vervolgens ziet u het **Intune-Dashboard**.

5.  Kies **Voorwaardelijke toegang** en kies vervolgens **Overzicht**.

6.  Kies een van de drie gebieden (**Geblokkeerd**, **Quarantaine** of **Toegestaan**) op de grafiek om uw rapport van de naleving van het voorwaardelijke toegangsbeleid weer te geven.

    ![Dashboard voor voorwaardelijke toegang](./media/CA-reporting-intune-1.png)

Als u een van de drie gebieden hebt gekozen, kunt u meer details weergeven over apparaten die worden toegestaan, geblokkeerd of in quarantaine worden geplaatst.

U kunt ook inzoomen op bepaalde apparaten voor meer informatie. Het apparaat in de onderstaande afbeelding is geblokkeerd. Intune biedt de mogelijkheid om bedrijfsgegevens uit de blade voor het rapport van de naleving van voorwaardelijke toegang te verwijderen.

![Rapport van de naleving van voorwaardelijke toegang door een apparaat](./media/CA-reporting-intune-3.png)

Op de blade Apparaatdetails ziet u meer informatie:

-   **Overzicht:** hier kunt u apparaateigenschappen bekijken, zoals de OS-versie, het apparaatmodel, het eigendom, het serienummer, de fabrikant, het telefoonnummer en de laatste keer dat het apparaat is ingecheckt.

-   **Eigenschappen:** hier kunt u het apparaateigendom instellen (persoonlijk of bedrijfseigendom).

-   **Hardware:** biedt de informatie die u in het overzicht ziet en ook opslagdetails (totale ruimte en vrije schijfruimte), systeembehuizing, netwerkdetails, netwerkservice en meer blokkeringsdetails van voorwaardelijke toegang.

-   **Gedetecteerde apps:** hier ziet u alle toepassingen die op uw apparaat zijn geïnstalleerd. U kunt de lijst met geïnstalleerde apps ook exporteren naar een CSV-indeling.

-   **Compatibiliteit:** hier worden alle details van het nalevingsbeleid van het apparaat weergegeven.

-   **Apparaatconfiguratie:** hier ziet u alle configuratiedetails van het apparaat.

-   **Toegang tot Exchange:** hier vindt u meer informatie over de apparaatstatus na het toepassen van beleid voor voorwaardelijke toegang.
