---
title: Apps implementeren | Microsoft Intune
description: Gebruik de informatie in dit onderwerp om apps met Microsoft Intune te implementeren.
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ef1d2d69acfeea9670324f580d33b191001ffa9
ms.openlocfilehash: 8ab2517a11ecb6ae5395814472dfbb3e83da132b

---
# Apps in Microsoft Intune implementeren

Gebruik de informatie in dit onderwerp om apps met Microsoft Intune te implementeren.


## Een app implementeren
In deze procedure implementeert u de app op geselecteerde apparaat- of gebruikersgroepen.

### Een app implementeren

1. Klik in de [Microsoft Intune-beheerdersconsole](https://manage.microsoft.com) op **Apps** &gt; **Apps** om de lijst weer te geven van de apps die u beheert.

2.  Selecteer de app die u wilt implementeren en klik vervolgens op **Implementatie beheren**.

3.  Selecteer de gebruikers- of apparaatgroepen waarvoor u de app wilt implementeren, in het dialoogvenster *&lt;<app-naam>&gt;* op de pagina **Groepen selecteren**.

4.  Configureer de volgende instellingen op de pagina **Implementatieactie**:

    - **Goedkeuring**: maak voor de implementatie een keuze uit de volgende mogelijkheden:
        - **Vereist** (verplichte installatie)
        - **Beschikbaar** (gebruikers installeren op verzoek vanuit de bedrijfsportal)
        - **Niet van toepassing** (de app wordt niet geïnstalleerd en niet weergegeven in de bedrijfsportal)
        - **Verwijderen** (de app wordt verwijderd van de betreffende apparaten)
    - **Deadline**: kies bij vereiste installaties hoe snel de app wordt geïmplementeerd. U kunt kiezen uit vooraf gedefinieerde waarden, maar u kunt ook **Aangepast** selecteren om uw eigen deadline te configureren.

5. Als de app die u wilt implementeren, kan worden geconfigureerd door Mobile Application Management-beleid, wordt de pagina **Mobile App Management** weergegeven. Op deze pagina kiest u het Mobile Application Management-beleid dat u wilt koppelen aan deze app.

    [Kijk welke Microsoft-apps compatibel zijn met de beleidsregels van Mobile Application Management.](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)

6. Als de app die u wilt implementeren, compatibel is met Intune VPN-profielen, wordt de pagina **VPN-profiel** weergegeven. Op deze pagina kunt u iOS-apps koppelen aan een VPN-profiel dat u hebt geïmplementeerd. De VPN-verbinding wordt automatisch geopend wanneer de app wordt gestart. Als u een VPN-profiel beschikbaar wilt stellen, moet voor dit profiel de instelling **VPN per app** zijn ingeschakeld.
 Zie [Gebruikers helpen om via VPN-profielen met Microsoft Intune verbinding met hun werk te laten maken](vpn-connections-in-microsoft-intune.md) voor meer informatie over het configureren van VPN-profielen, waaronder ondersteuning voor het koppelen van profielen aan apps.

## Voorbeeld

In dit voorbeeld hebt u de app als **Beschikbaar** geïmplementeerd voor een iOS-apparaat.
De app wordt op de apparaten van gebruikers weergegeven in de bedrijfsportal. Hier kan de app worden geïnstalleerd. In deze schermafbeelding is de app Bing voor iOS geïmplementeerd met behulp van het installatietype **Externe koppeling**, met een aangepast pictogram, en de optie **Geef deze app weer als aanbevolen app en markeer deze in de bedrijfsportal** ingeschakeld.  
![Voor iOS beschikbare app](./media/available-install-on-iOS.png)

Als u de app hebt geïmplementeerd als **Vereist**, krijgt de gebruiker een melding dat er een app gereed is om te worden geïnstalleerd. In deze schermafbeelding is de app Werkmappen voor iOS geïmplementeerd met behulp van het installatietype **Beheerde iOS-app uit de App Store**.  
![Voor iOS vereiste app](./media/iOS-Required-install.PNG)

## Volgende stappen

Nadat u een app hebt geïmplementeerd, is het een goed idee om de voortgang ervan te controleren. Zie [Apps in Microsoft Intune controleren](monitor-apps-in-microsoft-intune.md) voor meer informatie.



<!--HONumber=Jul16_HO3-->


