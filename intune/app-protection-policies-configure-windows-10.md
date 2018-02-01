---
title: Aan de slag met de configuratie van beveiligingsbeleid voor apps in Windows 10
titlesuffix: Azure portal
description: MAM-provider (mobile application management) instellen in Azure AD
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3254adc66c5fd5dc991364c3a33aabef8ac2030b
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Aan de slag met de configuratie van beveiligingsbeleid voor apps in Windows 10

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Mobile Application Management (MAM) inschakelen voor Windows 10 door de MAM-provider in te stellen in Azure AD. Door een MAM-provider in te stellen in Azure AD, kunt u de status van de inschrijving definiëren bij het maken van een nieuw WIP-beleid (Windows Information Protection) met Intune. De status van inschrijving mag MAM of MDM (Mobile Device Management) zijn.

> [!NOTE]
> Apparaten met een MAM-inschrijvingsstatus moeten aan Azure AD zijn toegevoegd.

## <a name="to-configure-the-mam-provider"></a>De MAM-provider configureren

1. Meld u aan bij Azure Portal en selecteer **Azure Active Directory**.

2. Kies **Mobility (MDM en MAM)** in de groep **Beheren**.

3. Klik op **Microsoft Intune**.

4. Configureer de instellingen in de groep **Standaard MAM-URL's herstellen** op de blade **Configureren**.

    **MAM-gebruikersbereik**  
      Automatische inschrijving voor MAM gebruiken voor het beheren van bedrijfsgegevens op Windows-apparaten van uw werknemers. De automatische inschrijving voor MAM wordt geconfigureerd voor Bring-Your-Own-Device-scenario's.<ul><li>**Geen**<br>Selecteer of alle gebruikers kunnen worden ingeschreven bij MAM.</li><li>**Sommige**<br>Selecteer de Azure AD-groepen met gebruikers die worden ingeschreven bij MAM.</li><li>**Alle**<br>Selecteer of alle gebruikers kunnen worden ingeschreven bij MAM.</li></ul>

    **URL voor MAM-gebruiksvoorwaarden**  
     De URL van het eindpunt van de gebruiksrechtovereenkomst van de MAM-service. Het eindpunt van de gebruiksrechtovereenkomst wordt gebruikt om de servicevoorwaarden voor eindgebruikers weer te geven voordat ze hun apparaten inschrijven voor beheer. De tekst van de gebruiksrechtovereenkomst informeert gebruikers over het beleid dat wordt afgedwongen op het mobiele apparaat.

    **Detectie-URL voor MAM**  
    De URL van het eindpunt van inschrijving van de MAM-service. Het eindpunt van de inschrijving wordt gebruikt om apparaten in te schrijven voor beheer met de MAM-service.

    **URL van MAM-naleving**  
      De URL van het eindpunt voor naleving van de MAM-service. Wanneer een gebruiker geen toegang krijgt tot een resource vanaf een niet-compatibel apparaat, wordt een koppeling naar de URL voor het nalevingsbeleid weergegeven aan de gebruiker. Gebruikers kunnen naar deze URL gaan, die wordt gehost door de MAM-service, om te begrijpen waarom het apparaat wordt beschouwd als niet-compatibel. Gebruikers kunnen ook herstel van self-service starten zodat hun apparaten compatibel worden en ze toegang kunnen krijgen tot resources.

5.  Klik op **Opslaan**.

## <a name="next-steps"></a>Volgende stappen

[WIP-beveiligingsbeleid voor apps maken](windows-information-protection-policy-create.md)
