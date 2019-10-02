---
title: Beveiligingsbeleid configureren voor apps in Windows 10
titleSuffix: Microsoft Intune
description: In dit onderwerp wordt beschreven hoe u app-beveiligingsbeleid (APP) kunt configureren voor Windows 10-apparaten.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: bbb4326f044429dfc633bf7f39787bc18a81fd84
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71725631"
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Aan de slag met de configuratie van beveiligingsbeleid voor apps in Windows 10 

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Mobile Application Management (MAM) inschakelen voor Windows 10 door de MAM-provider in te stellen in Azure AD. Door een MAM-provider in te stellen in Azure AD, kunt u de status van de inschrijving definiëren bij het maken van een nieuw WIP-beleid (Windows Information Protection) met Intune. De status van inschrijving mag MAM of MDM (Mobile Device Management) zijn.

## <a name="to-configure-the-mam-provider"></a>De MAM-provider configureren

1. Meld u aan bij Azure Portal en selecteer **Azure Active Directory**.

2. Kies **Mobility (MDM en MAM)** in de groep **Beheren**.

3. Klik op **Microsoft Intune**.

4. Configureer de instellingen in de groep **Standaard MAM-URL's herstellen** op de blade **Configureren**.

   **MAM-gebruikersbereik**  
   Automatische inschrijving voor MAM gebruiken voor het beheren van bedrijfsgegevens op Windows-apparaten van uw werknemers. De automatische inschrijving voor MAM wordt geconfigureerd voor Bring-Your-Own-Device-scenario's.<ul><li>**Geen**<br>Selecteer als geen gebruikers kunnen worden ingeschreven bij MAM.</li><li>**Sommige**<br>Selecteer de Azure AD-groepen met gebruikers die worden ingeschreven bij MAM.</li><li>**Alle**<br>Selecteer of alle gebruikers kunnen worden ingeschreven bij MAM.</li></ul>

   **URL voor MAM-gebruiksvoorwaarden**  
   De URL voor de MAM-gebruiksvoorwaarden wordt niet ondersteund voor Microsoft Intune. Dit invoervak moet leeg zijn om beveiligingsbeleid te kunnen toepassen.

   **Detectie-URL voor MAM**  
   De URL van het eindpunt van inschrijving van de MAM-service. Het eindpunt van de inschrijving wordt gebruikt om apparaten in te schrijven voor beheer met de MAM-service.

   **URL van MAM-naleving**  
   De URL voor MAM-naleving wordt niet ondersteund voor Microsoft Intune. Dit invoervak moet leeg zijn om beveiligingsbeleid te kunnen toepassen. 

5. Klik op **Opslaan**.

## <a name="next-steps"></a>Volgende stappen

[WIP-beveiligingsbeleid voor apps maken](windows-information-protection-policy-create.md)
