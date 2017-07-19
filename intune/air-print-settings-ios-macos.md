---
title: Intune AirPrint-instellingen voor iOS- en macOS-apparaten
titleSuffix: Intune on Azure
description: Meer informatie over het gebruik van Intune om ervoor te zorgen dat iOS- en macOS-apparaten automatisch verbinding maken met AirPrint-printers.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 743eb9a71efe1a5ea18b15312fdd4fe684f0ff07
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/05/2017
---
# <a name="airprint-settings-for-ios-and-macos-devices"></a>AirPrint-instellingen voor iOS- en macOS-apparaten

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gebruik deze instellingen om iOS- of macOS-apparaten zodanig te configureren dat deze automatisch verbinding maken met printers in uw netwerk die compatibel zijn met AirPrint. U kunt alleen doorgaan als u beschikt over het IP-adres en het resourcepad van de printers.

## <a name="find-airprint-printer-information"></a>AirPrint-printergegevens zoeken

Gebruik deze procedure om AirPrint-gegevens toe te voegen aan de nettolading van AirPrint, zodat gebruikers van iOS-apparaten kunnen afdrukken met bekende AirPrint-printers.

1. Open op een Mac die verbonden is met hetzelfde lokale netwerk (subnet) als de Airprint-printers het opdrachtregelprogramma Terminal (via **/Programma's/Hulpprogramma's**)
2. Typ in de Terminal **ippfind** en druk op de Enter-toets.
3. Noteer de printergegevens die worden geretourneerd, bijvoorbeeld: **ipp://myprinter.local.:631/ipp/port1**. Het eerste deel van de informatie is de naam van de printer en het laatste deel is het resourcepad.
4. Typ in de Terminal **myprinter.local ping** en druk op de Enter-toets.
5. Noteer de IP-adresgegevens die worden geretourneerd, bijvoorbeeld **PING myprinter.local (10.50.25.21)**.
6. gebruik ten slotte het IP-adres en resourcepad in de instellingen van de nettolading van AirPrint. Een voorbeeld van een IP-adres is **10.50.25.21** en een voorbeeld van een resourcepad is **/ipp/port1**.

## <a name="configure-an-airprint-profile"></a>Een AirPrint-profiel configureren

1. Kies **AirPrint** op de blade **Apparaatfuncties**.
2. Als u een AirPrint-bestemming wilt toevoegen, voert u op de blade **AirPrint** het **IP-adres** en **resourcepad** in en klikt u vervolgens op **Toevoegen**.
3. Ga door naar het toevoegen met zo veel bestemmingen als u wilt. Als u klaar bent, kiest u **OK**.

U kunt ook een lijst met printers importeren uit een bestand met door komma's gescheiden waarden (.csv) of u kunt de lijst exporteren.


## <a name="next-steps"></a>Volgende stappen

U kunt het apparaatprofiel nu toewijzen aan de gewenste groepen. Zie [Apparaatprofielen toewijzen](device-profile-assign.md) voor meer informatie.