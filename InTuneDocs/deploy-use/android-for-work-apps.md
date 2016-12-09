---
title: Apps implementeren op Android for Work-apparaten | Microsoft Intune
description: Dit onderwerp bevat procedures voor het synchroniseren en het vervolgens implementeren van apps op Android for Work-apparaten uit de Google Play for Work-store.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/6/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd0bbd90-d3fe-4efc-83fd-d1f3f86800d4
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 35ee89248e42c67f48d4607f5d415896e35b90e9


---

# <a name="how-to-deploy-apps-to-android-for-work-devices-with-intune"></a>Apps implementeren op Android for Work-apparaten met Intune

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

U implementeert apps op Android for Work-apparaten op een andere manier dan op standaard-Android-apparaten. Alle apps die u installeert voor Android for Work, zijn afkomstig uit de Google Play for Work-store. U meldt zich aan bij de store, bladert naar de gewenste apps en keurt deze goed.
De app wordt dan weergegeven in het knooppunt **Apps die zijn gekocht via het volume-aankoopprogramma** van de Intune-console. Hier kunt u de implementatie van de app beheren op dezelfde manier als implementaties van andere apps.
Als u uw eigen Line-Of-Business-apps (LOB) hebt gemaakt, kunt u deze ook implementeren. Hiertoe moet u zich aanmelden voor een Google-ontwikkelaarsaccount zodat u apps kunt publiceren naar een privégebied in de Google Play-store en deze vervolgens te synchroniseren met Intune.

## <a name="before-you-start"></a>Voordat u begint

1. Zorg ervoor dat u Intune en Android for Work hebt geconfigureerd voor samenwerking op het tabblad **Beheer** van de Intune-console.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Een app uit de Google Play for Work-store synchroniseren


1. Ga naar de [Google Play for Work-store](https://play.google.com/work). Meld u aan met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android for Work te configureren.
2. Zoek in de store naar de app die u wilt implementeren met Intune.
3. Kies **Goedkeuren** op de pagina voor de app die u hebt gekozen. In dit voorbeeld hebt u de app Microsoft Excel gekozen.<br>
  ![Voorbeeld van het goedkeuren van een app](/intune/deploy-use/media/approve.png)
4. Er wordt een venster voor de app geopend, waarin u om toestemming wordt gevraagd voor het uitvoeren van verschillende bewerkingen door de app. U moet **Goedkeuren** kiezen om door te gaan.<br>
  ![Voorbeeld van het goedkeuren van app-machtigingen](/intune/deploy-use/media/approve-app-permissions.png)
5. Kort daarna ziet u een bevestigingsbericht dat de app is goedgekeurd en beschikbaar is in uw IT-beheerconsole.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Een Line-Of-Business-app uit de Google Play for Work-store publiceren en synchroniseren

1. Ga naar de Google Play-ontwikkelaarsconsole, [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Meld u aan met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android for Work te configureren. Als u zich voor het eerst aanmeldt, moet u zich registreren en betalen om lid te worden van het Google-ontwikkelaarsprogramma.
3. Kies in de console **Nieuwe toepassing toevoegen**.
4. U uploadt en verstrekt informatie over uw app op dezelfde manier als bij het publiceren van een app naar de Google Play store. U moet echter wel de instelling **Deze toepassing alleen beschikbaar maken voor mijn organisatie (<*organisatienaam*>)** selecteren, zoals hieronder weergegeven.<br>
  ![Optie om de app alleen beschikbaar voor uw organisatie te maken](/intune/deploy-use/media/restrict.png)<br>
Dit zorgt ervoor dat de app alleen beschikbaar is voor uw organisatie en niet in de openbare Google Play-store.
Zie de [Help bij de Google-ontwikkelaarsconsole](https://support.google.com/googleplay/android-developer/answer/113469) voor meer informatie over het uploaden en publiceren van Android-apps.
5. Nadat u de app hebt gepubliceerd, gaat u naar de [Google Play for Work-store](https://play.google.com/work). Meld u aan met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android for Work te configureren.
6. Controleer in het knooppunt **Apps** van de store of u de door u gepubliceerde app ziet. Houd er rekening mee dat de app automatisch is goedgekeurd om te worden gesynchroniseerd met Intune.

## <a name="deploy-an-android-for-work-app"></a>Een Android for Work-app implementeren

Normaal gesproken wordt Intune twee keer per dag gesynchroniseerd met de Google Play for Work-store. Als u een app uit de store hebt goedgekeurd maar deze nog niet wordt weergegeven in het knooppunt **Apps die zijn gekocht via het volume-aankoopprogramma** van de werkruimte **Apps**, kunt u als volgt een onmiddellijke synchronisatie afdwingen:

1. Kies in de [Intune-beheerdersconsole](https://manage.microsoft.com) de optie **Beheer** > **Beheer van mobiele apparaten** > **Android for Work**.
2. Kies op de pagina **Instellingen voor beheer van mobiele apparaten voor Android for Work** de optie **Nu synchroniseren**.
3. Op de pagina ziet u ook de tijd en status van de laatste synchronisatie.

Wanneer de app wordt weergegeven in het knooppunt **Apps die zijn gekocht via het volume-aankoopprogramma** van de werkruimte **Apps**, kunt u [deze implementeren zoals elke andere app](deploy-apps-in-microsoft-intune.md). U kunt de app implementeren voor groepen of specifieke gebruikers. Op dit moment kunt u alleen de acties **Vereist** en **Verwijderen** selecteren. Vanaf oktober 2016 wordt ook de implementatieactie **Beschikbaar** toegevoegd voor nieuwe tenants.

Nadat u de app hebt geïmplementeerd, wordt deze geïnstalleerd op de opgegeven apparaten. De gebruiker van het apparaat wordt hiervoor niet om toestemming gevraagd.



<!--HONumber=Dec16_HO2-->


