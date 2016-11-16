---
title: Apps implementeren | Microsoft Intune
description: Gebruik de informatie in dit onderwerp om apps met Microsoft Intune te implementeren.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: 6ae7bd35157da261d0627f70933fe2a808f9e677

---
# Apps in Microsoft Intune implementeren

Gebruik de informatie in dit onderwerp om apps met Microsoft Intune te implementeren.


## Een app implementeren
In deze procedure implementeert u een app op geselecteerde apparaat- of gebruikersgroepen.

### Een app implementeren

1. Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Apps** &gt; **Apps** om de lijst weer te geven van de apps die u beheert.

2.  Selecteer de app die u wilt implementeren en klik vervolgens op **Implementatie beheren**.

3.  Selecteer in het dialoogvenster *&lt;app-naam&gt;* op de pagina **Groepen selecteren** de gebruikers- of apparaatgroepen waarvoor u de app wilt implementeren.

4.  Configureer de volgende instellingen op de pagina **Implementatieactie**:

    - **Goedkeuring**: maak voor de implementatie een keuze uit de volgende mogelijkheden:
        - **Vereist** (verplichte installatie)
        - **Beschikbaar** (gebruikers installeren op verzoek vanuit de bedrijfsportal)
        - **Niet van toepassing** (de app wordt niet geïnstalleerd en niet weergegeven in de bedrijfsportal)
        - **Verwijderen** (de app wordt verwijderd van de betreffende apparaten)
    - **Deadline**: kies bij vereiste installaties hoe snel de app wordt geïmplementeerd. U kunt kiezen uit vooraf gedefinieerde waarden, maar u kunt ook **Aangepast** selecteren om uw eigen deadline te configureren.

5. Als de app die u wilt implementeren, kan worden geconfigureerd door Mobile Application Management-beleid, wordt de pagina **Mobile App Management** weergegeven. Op deze pagina kiest u het Mobile Application Management-beleid dat u wilt koppelen aan deze app.

    [Kijk welke Microsoft-apps compatibel zijn met de beleidsregels van Mobile Application Management.](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)

6. Als de app die u wilt implementeren, compatibel is met Intune VPN-profielen, wordt de pagina **VPN-profiel** weergegeven. Op deze pagina kunt u iOS-apps koppelen aan een VPN-profiel dat u hebt geïmplementeerd. De VPN-verbinding wordt automatisch gemaakt wanneer de app wordt gestart. Als u een VPN-profiel beschikbaar wilt stellen, moet voor dit profiel de instelling **VPN per app** zijn ingeschakeld.
 Zie [VPN-verbindingen in Microsoft Intune](vpn-connections-in-microsoft-intune.md) voor meer informatie over het configureren van VPN-profielen, zoals informatie over het koppelen van profielen aan apps.

## Voorbeeld

In dit voorbeeld hebt u de app als **Beschikbaar** geïmplementeerd voor een iOS-apparaat.
De app wordt weergegeven op apparaten van gebruikers in de bedrijfsportal en gebruikers kunnen de app vanaf daar installeren.

In deze schermafbeelding is bijvoorbeeld de Bing voor iOS-app geïmplementeerd met behulp van het installatietype **Externe koppeling** met een aangepast pictogram. Daarbij is de optie **Geef deze app weer als een aanbevolen app en markeer deze in de bedrijfsportal** geselecteerd.  
![Voor iOS beschikbare app](./media/available-install-on-iOS.png)

Als u de app hebt geïmplementeerd als **Vereist**, krijgt de gebruiker een melding dat er een app gereed is om te worden geïnstalleerd. In deze schermafbeelding is bijvoorbeeld de app Werkmappen voor iOS geïmplementeerd met behulp van het installatietype **Beheerde iOS-app uit de App Store**.  
![Voor iOS vereiste app](./media/iOS-Required-install.PNG)

## Volgende stappen

Nadat u een app hebt geïmplementeerd, is het een goed idee om de voortgang ervan te controleren. Zie [Apps in Microsoft Intune controleren](monitor-apps-in-microsoft-intune.md) voor meer informatie.



<!--HONumber=Oct16_HO4-->


