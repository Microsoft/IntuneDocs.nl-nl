---
title: Apps bijwerken
description: Gebruik de informatie in dit onderwerp om na te gaan hoe u apps kunt bijwerken wanneer een nieuwe versie vereist is.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4ee48f751c181cd12c8e549c5aa4aab0c6252add
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="update-apps-using-microsoft-intune"></a>Apps bijwerken met Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Intune kan u helpen app-updates te beheren. Gebruik de informatie in dit onderwerp om na te gaan hoe u apps kunt bijwerken wanneer een nieuwe versie vereist is.

## <a name="how-to-update-apps"></a>Apps bijwerken
Wanneer er een nieuwe versie wordt uitgebracht van een app die u hebt geïmplementeerd, kunt u met Intune de app bijwerken en de nieuwere versie implementeren. U kunt een implementatie alleen vervangen door een nieuwere versie van dezelfde app (die dezelfde id heeft). U kunt app-updates niet gebruiken om een implementatie bij te werken met een ander app-pakket.

### <a name="app-identifiers"></a>App-id 's
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

### <a name="to-update-an-app"></a>Een app bijwerken

1.  Kies **Apps** &gt; **Apps** in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com).

2.  In de lijst **Apps** selecteert u de app die u wilt bijwerken, en vervolgens kiest u **Bewerken**.

3.  In de wizard **Software bewerken** geeft u nieuwe details voor het app-pakket op.

4.  Als u klaar bent, kiest u **Bijwerken**.

Wanneer een apparaat de volgende keer op beschikbare apps controleert, wordt de app automatisch bijgewerkt naar de nieuwste versie.
Apps die zijn geïnstalleerd met een app-pakket (Line-Of-Business-apps), worden automatisch bijgewerkt voor zowel vereiste als beschikbare implementaties, zolang de app dezelfde id heeft.

Voor apps die worden geïmplementeerd als een koppeling naar een winkel, wordt de update beheerd door de winkel waaruit de app afkomstig is.
