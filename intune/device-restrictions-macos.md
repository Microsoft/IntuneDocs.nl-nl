---
title: Microsoft Intune-apparaatbeperkingsinstellingen voor macOS
titlesuffix: ''
description: Meer informatie over de Intune-instellingen die u kunt gebruiken voor het beheren van apparaatinstellingen en functionaliteit op macOS-apparaten.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 69ea07e8d0a5d4a54abe7d1e592b3930d4e82354
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="microsoft-intune-macos-device-restriction-settings"></a>Microsoft Intune macOS-apparaatbeperkingsinstellingen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel komt u meer te weten over de Microsoft Intune-apparaatbeperkingsinstellingen die u kunt configureren voor apparaten met macOS.

## <a name="password"></a>Wachtwoord
-   **Wachtwoord**: hiermee geeft u aan dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat.
    -   **Vereist wachtwoordtype**: hiermee geeft u op of het wachtwoord alleen numerieke tekens mag bevatten of dat het wachtwoord alfanumeriek moet zijn (en dus letters en cijfers moet bevatten). Deze instelling wordt alleen ondersteund op Mac OS X-versie 10.10.3 en hoger.
    -   **Het minimumaantal niet-alfanumerieke tekens in een wachtwoord**: hiermee geeft u het aantal complexe tekens (tussen **0** en **4** tekens) op dat het wachtwoord moet bevatten.<br>Een complex teken is een symbool zoals ‘**?**’.
    -   **Minimale wachtwoordlengte**: voer de minimale lengte van het wachtwoord in dat een gebruiker moet configureren (tussen **4** en **16** tekens).
    -   **Eenvoudige wachtwoorden**: hiermee stelt u in dat eenvoudige wachtwoorden mogen worden gebruikt, zoals **0000** en **1234**.
    -   **Maximum aantal minuten waarna een wachtwoord voor het vergrendelde scherm is vereist**: hiermee geeft u op hoe lang de computer inactief moet zijn voordat een wachtwoord is vereist om te ontgrendelen.
    -   **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: hiermee geeft u de hoeveelheid tijd op die de computer inactief moet zijn voordat het scherm wordt vergrendeld.
    -   **Wachtwoord verloopt (dagen)**: hiermee geeft u op na hoeveel dagen de gebruiker het wachtwoord moet wijzigen (tussen **1** en **255** dagen).
    -   **Wachtwoorden niet opnieuw gebruiken**: hiermee geeft u op hoeveel eerder gebruikte wachtwoorden niet opnieuw mogen worden gebruikt (tussen **1** en **24**).

## <a name="restricted-apps"></a>Beperkte apps

Configureer een van de volgende lijsten in de lijst met beperkte apps:

- Lijst met **niet-toegestane apps**: hiermee maakt u een lijst met apps die niet worden beheerd door Intune en die gebruikers niet mogen installeren en uitvoeren. Zo wordt niet voorkomen dat gebruikers een niet-toegestane app installeren, maar als zij dit doen, wordt het aan u gemeld.
- Lijst met **goedgekeurde apps**: hiermee maakt u een lijst met apps die gebruikers mogen installeren. Gebruikers mogen geen apps installeren die niet worden vermeld. Apps die worden beheerd door Intune, zijn automatisch toegestaan. Zo wordt niet voorkomen dat gebruikers een app installeren die niet op de lijst met goedgekeurde apps staat, maar als zij dit doen, wordt het aan u gemeld.

Als u de lijst wilt configureren, klikt u op **Toevoegen** en geeft u een naam van uw keuze op, eventueel de uitgever van de app, en de bundel-ID van de app (bijvoorbeeld *com.apple.calculator*).

## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Niet-gemarkeerde e-maildomeinen

Voeg in het veld **E-maildomein-URL** een of meer URL's toe aan de lijst. Wanneer gebruikers een e-mail ontvangen dat afkomstig is van een ander domein dan het domein dat u hebt geconfigureerd, wordt de e-mail in de map iOS Mail gemarkeerd als niet-vertrouwd.

