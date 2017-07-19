---
title: Intune-apparaatbeperkingsinstellingen voor macOS
titleSuffix: Intune on Azure
description: Meer informatie over de Intune-instellingen die u kunt gebruiken voor het beheren van apparaatinstellingen en functionaliteit op macOS-apparaten.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3129cbaf-96c2-4837-8907-ca87a605a496
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 716ca0a2041bdd2ecfadd180999a09f80373cb2a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="macos-device-restriction-settings-in-microsoft-intune"></a>macOS-apparaatbeperkingsinstellingen in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gebruik deze instellingen voor het beheren van macOS-apparaten met behulp van een profiel voor apparaatbeperking.

## <a name="password"></a>Wachtwoord
-   **Wachtwoord vereist**: hiermee geeft u aan dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat.
    -   **Vereist wachtwoordtype**: hiermee geeft u op of het wachtwoord alleen numerieke tekens mag bevatten of dat het wachtwoord alfanumeriek moet zijn (en dus letters en cijfers moet bevatten). Deze instelling wordt alleen ondersteund op Mac OS X-versie 10.10.3 en hoger.
    -   **Het minimumaantal niet-alfanumerieke tekens in een wachtwoord**: hiermee geeft u het aantal complexe tekens (tussen **0** en **4** tekens) op dat het wachtwoord moet bevatten.<br>Een complex teken is een symbool zoals **?**
    -   **Minimale wachtwoordlengte**: voer de minimale lengte van het wachtwoord in dat een gebruiker moet configureren (tussen **4** en **16** tekens).
    -   **Eenvoudige wachtwoorden**: hiermee stelt u in dat eenvoudige wachtwoorden mogen worden gebruikt, zoals **0000** en **1234**.
    -   **Maximum aantal minuten waarna een wachtwoord voor het vergrendelde scherm is vereist**: hiermee geeft u op hoe lang de computer inactief moet zijn voordat een wachtwoord is vereist om te ontgrendelen.
    -   **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: hiermee geeft u de hoeveelheid tijd op die de computer inactief moet zijn voordat het scherm wordt vergrendeld.
    -   **Wachtwoord verloopt (dagen)**: hiermee geeft u op na hoeveel dagen de gebruiker het wachtwoord moet wijzigen (tussen **1** en **255** dagen).
    -   **Wachtwoorden niet opnieuw gebruiken**: hiermee geeft u op hoeveel eerder gebruikte wachtwoorden niet opnieuw mogen worden gebruikt (tussen **1** en **24**).

## <a name="restricted-apps"></a>Beperkte apps

Configureer een van de volgende lijsten in de lijst met beperkte apps:

Lijst met **niet-toegestane apps**: hiermee maakt u een lijst met apps die niet worden beheerd door Intune en die gebruikers niet mogen installeren en uitvoeren.
Lijst met **goedgekeurde apps**: hiermee maakt u een lijst met apps die gebruikers mogen installeren. Om te blijven voldoen aan het beleid, mogen gebruikers apps die niet worden vermeld, niet installeren. Apps die worden beheerd door Intune, zijn automatisch toegestaan.

Als u de lijst wilt configureren, klikt u op **Toevoegen** en geeft u een naam van uw keuze op, eventueel de uitgever van de app, en de bundel-ID van de app (bijvoorbeeld *com.apple.calculator*).

## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Niet-gemarkeerde e-maildomeinen

Voeg in het veld **E-maildomein-URL** een of meer URL's toe aan de lijst. Wanneer eindgebruikers een e-mail ontvangen dat afkomstig is van een ander domein dan het domein dat u hebt geconfigureerd, wordt de e-mail in de map iOS Mail gemarkeerd als niet-vertrouwd.

