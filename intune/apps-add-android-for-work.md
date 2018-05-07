---
title: Apps aan Android for Work-apparaten toewijzen
titlesuffix: Microsoft Intune
description: Ontdek hoe u apps synchroniseert en toewijst aan Android for Work-apparaten uit de Google Play for Work-store.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1742c33642667a9e7b8ca2f780094345959cd86c
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="assign-apps-to-android-for-work-devices-with-intune"></a>Apps aan Android for Work-apparaten toewijzen met Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android for Work is een programma voor Android-apparaten. Alle apps die u installeert op Android for Work-apparaten, zijn afkomstig uit de Google Play for Work-store. Hoe u apps toewijst aan Android for Work-apparaten verschilt van hoe u deze apps toewijst aan standaard Android-apparaten. U meldt zich aan bij de store, bladert naar de gewenste apps en keurt deze goed. De app verschijnt vervolgens op het knooppunt **Gelicentieerde apps** in Azure Portal, waarna u de toewijzing van apps kunt beheren zoals u bij elke app zou doen.

Als u uw eigen LOB-apps (line-of-business) hebt gemaakt, kunt u deze als volgt toewijzen:
- Meld u aan voor een Google-ontwikkelaarsaccount, zodat u apps kunt publiceren naar een privégebied in de Google Play-store.
- Synchroniseer de apps met Intune.

## <a name="before-you-start"></a>Voordat u begint

Zorg ervoor dat u Intune en Android for Work hebt geconfigureerd voor samenwerking in de workload **Apparaatinschrijving** van de Azure-portal.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Een app uit de Google Play for Work-store synchroniseren

1. Ga naar de [Google Play for Work-store](https://play.google.com/work). Meld u aan met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android for Work te configureren.
2. Zoek in de store naar de app die u wilt toewijzen met behulp van Intune en selecteer deze.
3. Op de pagina waarop de app wordt weergegeven, selecteert u **Goedkeuren**.  
    In het volgende voorbeeld is de app van Microsoft Excel gekozen.

    ![De knop Goedkeuring in de Google Play for Work-store](media/approve.png)
    
   Er wordt een venster voor de app geopend, waarin u om toestemming wordt gevraagd voor het uitvoeren van verschillende bewerkingen door de app. 

4. Selecteer **Goedkeuren** om de app-machtigingen te accepteren en door te gaan.

    ![De knop Goedkeuren voor app-machtigingen](media/approve-app-permissions.png)

5. Selecteer een optie om de nieuwe machtigingsaanvragen voor de app te verwerken en selecteer vervolgens **Opslaan**.

    ![Opties om nieuwe machtigingsaanvragen voor de app te verwerken](media/approve-app-settings.png)

    De app is goedgekeurd en wordt weergegeven in uw IT-beheerconsole. U kunt vervolgens de [Android for Work-app synchroniseren met Intune](apps-add-android-for-work.md#sync-an-android-for-work-app-with-intune). 

## <a name="sync-an-android-for-work-app-with-intune"></a>Een Android for Work-app synchroniseren met Intune

Als u een app uit de store hebt goedgekeurd maar deze nog niet wordt weergegeven in het knooppunt **Apps met licentie** van de workload **Mobiele apps**, dwingt u als volgt een onmiddellijke synchronisatie af:

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer **Mobiele apps** in het deelvenster **Intune**.
4. In het werkbelastingvenster **Mobiele apps**, onder **Installatie**, selecteert u **Android for Work**.
5. Selecteer in het deelvenster **Android for Work** de optie **Synchroniseren**.  
    De pagina werkt de tijd en de status van de laatste synchronisatie bij.
6. In het werkbelastingvenster **Mobiele apps** selecteert u **Apps**.  
    De nieuw beschikbare Android for Work-app wordt weergegeven.

Als de app wordt weergegeven in het knooppunt **App-licenties** van het werkbelastingvenster **Mobiele apps**, kunt u de app [toewijzen als alle andere apps](/intune-azure/manage-apps/deploy-apps). U kunt de app alleen toewijzen aan groepen gebruikers.

Nadat u de app hebt toegewezen, wordt deze geïnstalleerd op de apparaten die u hebt aangewezen. De gebruiker van het apparaat wordt geen toestemming voor de installatie gevraagd.

## <a name="manage-android-for-work-app-permissions"></a>App-machtigingen voor Android voor Work beheren
Android for Work vereist dat u apps goedkeurt in de beheerde Google Play-webconsole voordat u de apps met Intune synchroniseert en aan uw gebruikers toewijst. Met Android for Work kunt u de apps op de achtergrond en automatisch naar de apparaten van gebruikers pushen en daarom moet u de machtigingen voor de app namens al uw gebruikers accepteren. Gebruikers krijgen geen app-machtigingen te zien wanneer ze de apps installeren. Het is dus belangrijk dat u de informatie over de machtigingen leest en begrijpt.

Wanneer een app-ontwikkelaar een nieuwe versie van de app publiceert met bijgewerkte machtigingen, worden de machtigingen niet automatisch geaccepteerd, zelfs niet wanneer u de vorige machtigingen ook al had goedgekeurd. Apparaten met de oude versie van de app kunnen deze nog steeds gebruiken. De app is echter niet bijgewerkt tot de nieuwe machtigingen zijn goedgekeurd. Op apparaten waar de app niet op is geïnstalleerd, worden deze pas geïnstalleerd wanneer de nieuwe machtigingen voor de app zijn goedgekeurd.

### <a name="update-app-permissions"></a>App-machtigingen bijwerken

Bezoek met enige regelmaat de beheerde Google Play-console om te controleren op nieuwe machtigingen. U kunt de Google Play zodanig configureren dat u of anderen een e-mailbericht ontvangen wanneer nieuwe machtigingen voor een goedgekeurde app zijn vereist. Als u een app toewijst en u ziet dat deze niet is geïnstalleerd op apparaten, controleert u aan de hand van de volgende stappen op nieuwe machtigingen:

1. Ga naar [Google Play](http://play.google.com/work).
2. Meld u aan met het Google-account dat u gebruikt om apps te publiceren en goed te keuren.
3. Selecteer het tabblad **Updates** en controleer of er apps kunnen worden bijgewerkt.  
    Voor alle vermelde apps zijn nieuwe machtigingen vereist. De apps worden pas toegewezen wanneer de machtigingen zijn toegepast.

U kunt Google Play eventueel ook zodanig configureren dat de app-machtigingen per app automatisch opnieuw worden goedgekeurd. 

## <a name="working-with-a-line-of-business-app-from-the-google-play-for-work-store"></a>Werken met een Line-Of-Business-app uit de Google Play for Work Store

1. Meld u aan bij de [Google Play-ontwikkelaarsconsole](https://play.google.com/apps/publish) met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android for Work te configureren.  
    Als u zich voor het eerst aanmeldt, moet u zich registreren en betalen om lid te worden van het Google-ontwikkelaarsprogramma.
2. Selecteer in de console **Nieuwe toepassing toevoegen**.
3. U uploadt en verstrekt informatie over uw app op dezelfde manier als bij het publiceren van een app naar de Google Play store. U moet echter wel **Deze toepassing alleen beschikbaar maken voor mijn organisatie (<*organisatienaam*>)** selecteren.

    ![De app alleen voor uw organisatie beschikbaar maken](media/restrict.png)

    Deze bewerking zorgt ervoor dat de app alleen beschikbaar is voor uw organisatie en niet in de openbare Google Play-store.

    Raadpleeg voor meer informatie over Android-apps uploaden en publiceren [Help bij Google-ontwikkelaarsconsole](https://support.google.com/googleplay/android-developer/answer/113469).
4. Nadat u uw app hebt gepubliceerd, meldt u zich aan bij de [Google Play for Work-store](https://play.google.com/work) met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android for Work te configureren.
5. Controleer in het knooppunt **Apps** van de store of de door u gepubliceerde app wordt weergegeven.  
    De app is automatisch goedgekeurd om te worden gesynchroniseerd met Intune.

## <a name="next-steps"></a>Volgende stappen

- [Apps aan groepen toewijzen](apps-deploy.md) 

