---
title: Een macOS-apparaat wissen
titleSuffix: Microsoft Intune
description: Lees hoe u alle gegevens van een macOS-apparaat kunt wissen, inclusief het besturingssysteem.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/31/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ab396092-907a-44b7-a157-aabee62176a9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 64f8b31c4fab5b247ae466df52a0b965f1be813b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179963"
---
# <a name="erase-all-data-from-a-macos-device"></a>Alle gegevens van een macOS-apparaat wissen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

U kunt alle gegevens van een macOS-apparaat wissen, inclusief het besturingssysteem. Het apparaat wordt ook uit Intune-beheer verwijderd. De eindgebruiker wordt hier niet over gewaarschuwd.

1. Ga in [Intune in de Azure-portal](https://aka.ms/intuneportal) naar **Apparaten** > **Alle apparaten** en kies het apparaat dat u wilt wissen.
![Schermopname](./media/device-erase/choosedevice.png)
2. Klik op **Meer** > **Wissen** en geef een zescijferig nummer op voor de **Herstelpincode**. Dit is de pincode die u aan de gebruiker moet geven zodat ze het besturingssysteem weer op hun apparaat kunnen installeren. Noteer deze pincode; de pincode is niet meer zichtbaar nadat de wisactie is voltooid.
![Schermopname](./media/device-erase/providepin.png)
3. Klik op **OK** om het apparaat te wissen.
