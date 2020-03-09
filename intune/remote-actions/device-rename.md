---
title: Naam van een apparaat wijzigen met Microsoft Intune - Azure | Microsoft Docs
description: Wijzig de naam van een apparaat met behulp van Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/27/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b286e095613c56f2d6fdfa5a2cf2cd1398611f12
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77781832"
---
# <a name="rename-a-device-in-intune"></a>Naam van een apparaat wijzigen in Intune

Met de actie **Naam van apparaat wijzigen** kunt u de naam wijzigen van een apparaat dat is ingeschreven bij Intune. De naam van het apparaat wordt gewijzigd in Intune en op het apparaat.

U kunt de namen van de volgende typen apparaten wijzigen:
- Windows-apparaat in bedrijfseigendom 
- iOS/iPadOS onder supervisie
- MacOS 10-apparaat in bedrijfseigendom

Deze functie biedt momenteel geen ondersteuning voor de naamwijziging van hybride Azure AD Windows-apparaten.

## <a name="rename-a-device"></a>De naam van een apparaat wijzigen

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Kies **Apparaten** > **Alle apparaten** > kies een apparaat > **...**  > **Naam van apparaat wijzigen**.
4. Typ op de blade **Naam van apparaat wijzigen** de nieuwe naam in het tekstvak. U kunt letters, cijfers en afbreekstreepjes gebruiken. De naam moet minstens één letter of afbreekstreepje bevatten.
5. Als u het apparaat opnieuw wilt opstarten nadat u de naam ervan hebt gewijzigd, kiest u naast **Opnieuw opstarten na het wijzigen van de naam** de optie **Ja**.
6. Kies **Naam wijzigen**.

## <a name="windows-device-rename-rules"></a>Regels voor het wijzigen van de naam van Windows-apparaten
Bij het wijzigen van de naam van een Windows-apparaat moet de nieuwe naam aan de volgende regels voldoen:
- Maximaal 15 tekens (moet kleiner zijn dan of gelijk zijn aan 63 bytes, exclusief navolgende null-tekens)
- Niet null of een lege tekenreeks
- Toegestane ASCII: Letters (a-z, A-Z), cijfers (0-9) en afbreekstreepjes
- Toegestane Unicode: tekens > = 0x80, moet geldige UTF8 zijn, moet IDN-toewijsbaar zijn (dat wil zeggen dat RtlIdnToNameprepUnicode moet slagen, zie RFC 3492)
- Namen mogen niet alleen cijfers bevatten
- Namen mogen geen spaties bevatten
- Niet-toegestane tekens: { | } ~ [ \ ] ^ ' : ; < = > ? & @ ! " # $ % ` ( ) + / , . _ *)


## <a name="next-steps"></a>Volgende stappen

Ga naar de pagina **Overzicht** voor het apparaat om de status van de actie **Naam wijzigen** te zien.
