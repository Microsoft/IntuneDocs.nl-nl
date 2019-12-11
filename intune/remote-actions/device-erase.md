---
title: Een macOS-apparaat wissen
titleSuffix: Microsoft Intune
description: Lees hoe u alle gegevens van een macOS-apparaat kunt wissen, inclusief het besturingssysteem.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/31/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ab396092-907a-44b7-a157-aabee62176a9
ms.reviewer: coferro
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6bc2ba86ddb36355bca8328b9c205047abf1b4ff
ms.sourcegitcommit: ec69e7ccc6e6183862a48c1b03ca6a3bf573f354
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/07/2019
ms.locfileid: "74907267"
---
# <a name="erase-all-data-from-a-macos-device"></a>Alle gegevens van een macOS-apparaat wissen

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

U kunt alle gegevens van een macOS-apparaat wissen, inclusief het besturingssysteem. Het apparaat wordt ook uit Intune-beheer verwijderd. De eindgebruiker wordt hier niet over gewaarschuwd.

1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **Alle apparaten** > kies het apparaat dat u wilt wissen.
2. Klik op **Meer** > **Wissen** en geef een zescijferig nummer op voor de **Herstelpincode**. Dit is de pincode die u aan de gebruiker moet geven zodat ze het besturingssysteem weer op hun apparaat kunnen installeren. Noteer deze pincode; de pincode is niet meer zichtbaar nadat de wisactie is voltooid.
![Schermopname](./media/device-erase/providepin.png)
3. Klik op **OK** om het apparaat te wissen.
