---
title: Apps toewijzen aan apparaten met een Android-werkprofiel
titlesuffix: Microsoft Intune
description: Ontdek hoe u apps synchroniseert en toewijst aan apparaten met een Android-werkprofiel vanuit de beheerde Google Play Store.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: c7d5d29df0f91a4cff1060cd10a5d2355e196e39
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180134"
---
# <a name="assign-apps-to-android-work-profile-devices-with-intune"></a>Apps toewijzen aan apparaten met een Android-werkprofiel met Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android Enterprise is een programma voor apparaten met Android-werkprofiel en kioskapparaten. Bij apparaten met een Android-werkprofiel vormt Android Enterprise een reeks functies en services waarmee persoonlijke apps en gegevens worden gescheiden van zakelijke apps en gegevens. Android Enterprise biedt aanvullende beheeropties en privacy wanneer mensen hun Android-apparaten voor hun werk gebruiken. Intune helpt u om apps en instellingen te implementeren op apparaten met een Android-werkprofiel om ervoor te zorgen dat werk- en privégegevens gescheiden zijn. Alle apps die u installeert op apparaten met een Android-werkprofiel zijn afkomstig uit de beheerde Google Play Store. Hoe u apps toewijst aan apparaten met een Android-werkprofiel verschilt van hoe u deze apps toewijst aan standaard Android-apparaten. U meldt zich aan bij de store, bladert naar de gewenste apps en keurt deze goed. De app verschijnt vervolgens op het knooppunt **Gelicentieerde apps** in Azure Portal, waarna u de toewijzing van apps kunt beheren zoals u bij elke app zou doen.

Als u uw eigen LOB-apps (line-of-business) hebt gemaakt, kunt u deze als volgt toewijzen:
- Meld u aan voor een Google-ontwikkelaarsaccount, zodat u apps kunt publiceren naar een privégebied in de Google Play-store.
- Synchroniseer de apps met Intune.

## <a name="before-you-start"></a>Voordat u begint

Zorg ervoor dat u Intune en Android-werkprofielen hebt geconfigureerd voor samenwerking in de workload **Apparaatinschrijving** van de Azure-portal. Zie [Enroll Android devices](android-work-profile-enroll.md) (Android-apparaten registreren) voor meer informatie.

## <a name="synchronize-an-app-from-the-managed-google-play-store"></a>Een app uit de beheerde Google Play Store synchroniseren

1. Ga naar de [beheerde Google Play Store](https://play.google.com/work). Meld u aan met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android Enterprise te configureren.
2. Zoek in de store naar de app die u wilt toewijzen met behulp van Intune en selecteer deze.
3. Op de pagina waarop de app wordt weergegeven, selecteert u **Goedkeuren**.  
    In het volgende voorbeeld is de app van Microsoft Excel gekozen.

    ![De knop Goedkeuren in de beheerde Google Play Store](media/approve.png)
    
   Er wordt een venster voor de app geopend, waarin u om toestemming wordt gevraagd voor het uitvoeren van verschillende bewerkingen door de app. 

4. Selecteer **Goedkeuren** om de app-machtigingen te accepteren en door te gaan.

    ![De knop Goedkeuren voor app-machtigingen](media/approve-app-permissions.png)

5. Selecteer een optie om de nieuwe machtigingsaanvragen voor de app te verwerken en selecteer vervolgens **Opslaan**.

    ![Opties om nieuwe machtigingsaanvragen voor de app te verwerken](media/approve-app-settings.png)

    De app is goedgekeurd en wordt weergegeven in uw IT-beheerconsole. U kunt vervolgens de [Android-werkprofiel-app synchroniseren met Intune](apps-add-android-for-work.md#sync-an-android-for-work-app-with-intune). 

## <a name="sync-a-managed-google-play-app-with-intune"></a>Een beheerde Google Play Store-app met Intune synchroniseren

Als u een app uit de store hebt goedgekeurd maar deze nog niet wordt weergegeven in het knooppunt **Apps met licentie** van de workload **Client-apps**, dwingt u als volgt een onmiddellijke synchronisatie af:

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer in het deelvenster **Intune** de optie **Client-apps**.
4. Selecteer in het workloadvenster **Client-apps**, onder **Installatie** de optie **Beheerde Google Play Store**.
5. Kies in het deelvenster **Beheerde Google Play Store** **Vernieuwen**.  
    De pagina werkt de tijd en de status van de laatste synchronisatie bij.
6. Selecteer in het workloadvenster **Client-apps** de optie **Apps**.  
    De zojuist beschikbaar geworden beheerde Google Play Store-app wordt weergegeven.

Als de app wordt weergegeven in het knooppunt **App-licenties** van het workloadvenster **Client-apps**, kunt u de app [toewijzen als alle andere apps](/intune-azure/manage-apps/deploy-apps). U kunt de app alleen toewijzen aan groepen gebruikers.

Nadat u de app hebt toegewezen, wordt deze geïnstalleerd op de apparaten die u hebt aangewezen. De gebruiker van het apparaat wordt geen toestemming voor de installatie gevraagd.

## <a name="manage-android-enterprise-app-permissions"></a>Machtigingen voor Android Enterprise-apps beheren
Android Enterprise vereist dat u apps goedkeurt in de beheerde Google Play Store-webconsole voordat u de apps met Intune synchroniseert en aan uw gebruikers toewijst. Met Android Enterprise kunt u de apps op de achtergrond en automatisch naar de apparaten van gebruikers pushen. U moet daarom de machtigingen voor de app namens al uw gebruikers accepteren. Gebruikers krijgen geen app-machtigingen te zien wanneer ze de apps installeren. Het is dus belangrijk dat u de informatie over de machtigingen begrijpt.

Wanneer een app-ontwikkelaar machtigingen bijwerkt met een nieuwe versie van de app, worden de machtigingen niet automatisch geaccepteerd, zelfs niet wanneer u de vorige machtigingen ook al had goedgekeurd. Apparaten met de oude versie van de app kunnen deze nog steeds gebruiken. De app is echter niet bijgewerkt tot de nieuwe machtigingen zijn goedgekeurd. Op apparaten waar de app niet op is geïnstalleerd, worden deze pas geïnstalleerd wanneer de nieuwe machtigingen voor de app zijn goedgekeurd.

### <a name="update-app-permissions"></a>App-machtigingen bijwerken

Bezoek met enige regelmaat de beheerde Google Play-console om te controleren op nieuwe machtigingen. U kunt de Google Play zodanig configureren dat u of anderen een e-mailbericht ontvangen wanneer nieuwe machtigingen voor een goedgekeurde app zijn vereist. Als u een app toewijst en u ziet dat deze niet is geïnstalleerd op apparaten, controleert u aan de hand van de volgende stappen op nieuwe machtigingen:

1. Ga naar [Google Play](http://play.google.com/work).
2. Meld u aan met het Google-account dat u gebruikt om apps te publiceren en goed te keuren.
3. Selecteer het tabblad **Updates** en controleer of er apps kunnen worden bijgewerkt.  
    Voor alle vermelde apps zijn nieuwe machtigingen vereist. De apps worden pas toegewezen wanneer de machtigingen zijn toegepast.

U kunt Google Play eventueel ook zodanig configureren dat de app-machtigingen per app automatisch opnieuw worden goedgekeurd. 

## <a name="working-with-a-line-of-business-app-from-the-managed-google-play-store"></a>Werken met een Line-Of-Business-app uit de beheerde Google Play Store

1. Meld u aan bij de [Google Play Store-ontwikkelaarsconsole](https://play.google.com/apps/publish) met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android Enterprise te configureren.  
    Als u zich voor het eerst aanmeldt, moet u zich registreren en betalen om lid te worden van het Google-ontwikkelaarsprogramma.
2. Selecteer in de console **Nieuwe toepassing toevoegen**.
3. U uploadt en verstrekt informatie over uw app op dezelfde manier als bij het publiceren van een app naar de Google Play store. U moet echter wel **Deze toepassing alleen beschikbaar maken voor mijn organisatie (<*organisatienaam*>)** selecteren.

    ![De app alleen voor uw organisatie beschikbaar maken](media/restrict.png)

    Via deze bewerking komt de app alleen voor uw organisatie beschikbaar. Deze is dan niet beschikbaar in de openbare Google Play Store.

    Raadpleeg voor meer informatie over Android-apps uploaden en publiceren [Help bij Google-ontwikkelaarsconsole](https://support.google.com/googleplay/android-developer/answer/113469).
4. Nadat u uw app hebt gepubliceerd, meldt u zich aan bij de [beheerde Google Play Store](https://play.google.com/work) met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android Enterprise te configureren.
5. Controleer in het knooppunt **Apps** van de store of de door u gepubliceerde app wordt weergegeven.  
    De app is automatisch goedgekeurd om te worden gesynchroniseerd met Intune.

## <a name="next-steps"></a>Volgende stappen

- [Apps aan groepen toewijzen](apps-deploy.md) 

