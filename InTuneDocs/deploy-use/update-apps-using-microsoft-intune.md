---
title: Apps bijwerken | Microsoft Intune
description: Gebruik de informatie in dit onderwerp om na te gaan hoe u apps kunt bijwerken wanneer een nieuwe versie vereist is.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: e78642494356038d4dff259ca54030122fd90819


---

# Apps bijwerken met Microsoft Intune
Microsoft Intune kan u helpen app-updates te beheren. Gebruik de informatie in dit onderwerp om na te gaan hoe u apps kunt bijwerken wanneer een nieuwe versie vereist is.

## Apps bijwerken
Wanneer er een nieuwe versie wordt uitgebracht van een app die u hebt geïmplementeerd, kunt u met Intune de app bijwerken en de nieuwere versie implementeren. U kunt een implementatie alleen vervangen door een nieuwere versie van dezelfde app (die dezelfde id heeft). U kunt app-updates niet gebruiken om een implementatie bij te werken met een ander app-pakket.

### App-id 's
De app-id is een eigenschap waarmee een unieke app wordt aangeduid. U kunt niet meerdere exemplaren van een app installeren met dezelfde id. Hier volgen enkele voorbeelden van app-id’s:

- **iOS** - bundel-id (bijvoorbeeld: com.microsoft.excel)
- **Android** - pakket-id (bijvoorbeeld: com.microsoft.excel)
- **Windows Phone** - (xap-installatieprogramma) gebruik product-id (GUID)
- **Windows** - (appx/appxbundle), gebruik de volledige naam van het pakket



> [!IMPORTANT]
> Wanneer u een app implementeert met de implementatieactie **Vereiste installatie** en u de implementatieactie later wijzigt in **Beschikbare installatie**, worden updates voor de app niet automatisch geïnstalleerd op apparaten waarop de app was geïnstalleerd voordat de implementatie werd gewijzigd. Als u dit probleem wilt oplossen, kunt u het volgende doen:
>
> -   Laat de gebruiker van het apparaat naar de bedrijfsportal gaan, de geïnstalleerde app selecteren en vervolgens **Installeren** kiezen.
> -   Wijzig de implementatieactie in **Verwijderen**en nadat de app is verwijderd, implementeert u de app opnieuw met de implementatieactie **Beschikbare installatie**.

### Een app bijwerken

1.  Kies **Apps** &gt; **Apps** in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com).

2.  In de lijst **Apps** selecteert u de app die u wilt bijwerken, en vervolgens kiest u **Bewerken**.

3.  In de wizard **Software bewerken** geeft u nieuwe details voor het app-pakket op.

4.  Als u klaar bent, kiest u **Bijwerken**.

Wanneer een apparaat de volgende keer op beschikbare apps controleert, wordt de app automatisch bijgewerkt naar de nieuwste versie.
Apps die zijn geïnstalleerd met een app-pakket (Line-Of-Business-apps), worden automatisch bijgewerkt voor zowel vereiste als beschikbare implementaties, zolang de app dezelfde id heeft.

Voor apps die worden geïmplementeerd als een koppeling naar een winkel, wordt de update beheerd door de winkel waaruit de app afkomstig is.



<!--HONumber=Oct16_HO4-->


