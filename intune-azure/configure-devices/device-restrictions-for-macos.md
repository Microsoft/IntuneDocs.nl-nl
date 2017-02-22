---
title: Intune-apparaatbeperkingsinstellingen voor macOS | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp vindt u meer informatie over de Intune-instellingen die u kunt gebruiken voor het beheren van apparaatinstellingen en functionaliteit op macOS-apparaten.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3129cbaf-96c2-4837-8907-ca87a605a496
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1e9c97d66e80de635ad43a1339d092b7987f738b
ms.openlocfilehash: 6856303581f5275c88d5d4efe07088de8f7ab713


---

# <a name="macos-device-restriction-settings-in-intune-azure-preview"></a>macOS-apparaatbeperkingsinstellingen in Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="password"></a>Wachtwoord
-   **Wachtwoord vereist**: hiermee geeft u aan dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat.
    -   **Vereist wachtwoordtype**: hiermee geeft u op of het wachtwoord alleen numerieke tekens mag bevatten of dat het wachtwoord alfanumeriek moet zijn (en dus letters en cijfers moet bevatten). Deze instelling wordt alleen ondersteund op Mac OS X-versie 10.10.3 en hoger.
    -   **Het minimumaantal niet-alfanumerieke tekens in een wachtwoord**: hiermee geeft u het aantal complexe tekens (tussen **0** en **4** tekens) op dat het wachtwoord moet bevatten.<br>Een complex teken is een symbool, zoals **?**.
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





<!--HONumber=Feb17_HO1-->


