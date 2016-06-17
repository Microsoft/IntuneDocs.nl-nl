---
# required metadata

title: Apps bijwerken | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Apps bijwerken met Microsoft Intune
Microsoft Intune kan u helpen app-updates te beheren. Gebruik de informatie in dit onderwerp om te zien hoe u apps kunt bijwerken wanneer een nieuwe versie vereist is.

## Apps bijwerken
Wanneer er een nieuwe versie wordt uitgebracht van een app die u hebt geïmplementeerd, kunt u met Intune de app bijwerken en de nieuwere versie implementeren. U kunt een implementatie alleen vervangen door een nieuwere versie van dezelfde app (met dezelfde id). U kunt app-updates niet gebruiken om een implementatie bij te werken met een ander app-pakket.

> [!IMPORTANT]
> Wanneer u een app implementeert met de implementatieactie **Vereiste installatie** en u de implementatieactie later wijzigt in **Beschikbare installatie**, worden updates voor de app niet automatisch geïnstalleerd op apparaten waarop de app was geïnstalleerd voordat de implementatie werd gewijzigd. Als u dit probleem wilt oplossen, kunt u het volgende doen:
> 
> -   Laat de gebruiker van het apparaat naar de bedrijfsportal gaan, de geïnstalleerde app selecteren en op **Installeren**klikken.
> -   Wijzig de implementatieactie in **Verwijderen**en nadat de app is verwijderd, implementeert u de app opnieuw met de implementatieactie **Beschikbare installatie**.

### Een app bijwerken

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Apps** &gt; **Apps**.

2.  In de lijst **Apps** selecteert u de app die u wilt bijwerken, en klikt u vervolgens op **Bewerken**.

3.  In de wizard **Software bewerken** geeft u nieuwe details voor het app-pakket op.

4.  Wanneer u gereed bent, klikt u op **Bijwerken**.

Wanneer een apparaat de volgende keer op beschikbare apps controleert, wordt de app automatisch bijgewerkt naar de nieuwste versie.





<!--HONumber=May16_HO2-->


