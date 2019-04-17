---
title: Beheerde Google Play-apps toewijzen aan Android-bedrijfsapparaten
titleSuffix: Microsoft Intune
description: Ontdek hoe u apps synchroniseert en toewijst aan Android-bedrijfsapparaten vanuit de beheerde Google Play Store.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/15/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1ad07252ccf10fefdd1c753ab103eb91a2789c39
ms.sourcegitcommit: 8c795b041cd39e3896595f64f53ace48be0ec84c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2019
ms.locfileid: "59587345"
---
# <a name="add-managed-google-play-apps-to-android-enterprise-devices-with-intune"></a>Beheerde Google Play-apps toevoegen aan Android-bedrijfsapparaten met Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android Enterprise is een programma voor apparaten met Android-werkprofiel, toegewezen apparaten/kioskapparaten en volledig beheerde apparaten. Bij apparaten met een Android-werkprofiel vormt Android Enterprise een reeks functies en services waarmee persoonlijke apps en gegevens worden gescheiden van zakelijke apps en gegevens. Android Enterprise biedt aanvullende beheeropties en privacy wanneer mensen hun Android-apparaten voor hun werk gebruiken. Intune helpt u om apps en instellingen te implementeren op apparaten met een Android-werkprofiel om ervoor te zorgen dat werk- en privégegevens gescheiden zijn. Alle apps die u installeert op apparaten met een Android-werkprofiel zijn afkomstig uit de beheerde Google Play Store. Hoe u apps toewijst aan apparaten met een Android-werkprofiel verschilt van hoe u deze apps toewijst aan standaard Android-apparaten. U meldt zich aan bij de store, bladert naar de gewenste apps en keurt deze goed. De app verschijnt vervolgens op het knooppunt **Gelicentieerde apps** in Azure Portal, waarna u de toewijzing van apps kunt beheren zoals u bij elke app zou doen.

Als u uw eigen LOB-apps (line-of-business) hebt gemaakt, kunt u deze als volgt toewijzen:
- Meld u aan voor een Google-ontwikkelaarsaccount, zodat u apps kunt publiceren naar een privégebied in de Google Play-store.
- Synchroniseer de apps met Intune.

## <a name="before-you-start"></a>Voordat u begint

Zorg ervoor dat u Intune en Android-werkprofielen hebt geconfigureerd voor samenwerking in de workload **Apparaatinschrijving** van de Azure-portal. Zie [Enroll Android devices](android-work-profile-enroll.md) (Android-apparaten registreren) voor meer informatie.

>[!NOTE]
>Als u met Microsoft Intune werkt, kunt u beter de Microsoft Edge- of Google Chrome-browser gebruiken.

## <a name="managed-google-play-app-type"></a>Type beheerde Google Play-app
Met het type **beheerde Google Play-app** hebt u toestemming om specifiek [beheerde Google Play-apps](https://play.google.com/work/search?q=microsoft&c=apps) aan Intune toe te voegen. Als Intune-beheerder kunt u nu door goedgekeurde beheerde Google Play-apps bladeren en goedgekeurde beheerde Google Play-apps zoeken, goedkeuren, synchroniseren en toewijzen in Intune.  U hoeft niet langer afzonderlijk naar de beheerde Google Play-console te bladeren en u hoeft niet opnieuw een verificatie uit te voeren.

> [!NOTE]
> Als u liever een beheerde Google Play-app synchroniseert met Intune, raadpleegt u [Een beheerde Google Play-app met Intune synchroniseren](apps-add-android-for-work.md#synchronize-a-managed-google-play-app-with-intune-alternative)

## <a name="add-a-managed-google-play-app-using-intune"></a>Een beheerde Google Play-app toevoegen met behulp van Intune

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services** > **Intune**.  
    Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer in het deelvenster **Intune** de optie **Client-apps** > **Apps**.
5. Selecteer **Toevoegen** in het deelvenster **Apps**.
6. In de vervolgkeuzelijst **App-type** selecteert u **Beheerd Google Play**.
7. Selecteer **Beheerd Google Play - Goedkeuren** om de beheerde Google Play-catalogus te openen.
8. Gebruik het zoekvak om te zoeken naar apps die u wilt opnemen.
9. Klik op **Goedkeuren** om de app goed te keuren in Beheerd Google Play en klik op **Goedkeuren** om de app-machtigingen te accepteren.
10. Selecteer **Goedgekeurd houden wanneer de app nieuwe machtigingen aanvraagt** in het venster Instellingen voor goedkeuring en klik vervolgens op **Opslaan**. Als u deze optie niet kiest, moet u handmatig alle nieuwe machtigingen goedkeuren als de app-ontwikkelaar een update publiceert.  Hierdoor worden installaties en updates van de app gestopt totdat de machtigingen zijn goedgekeurd. Daarom wordt het aanbevolen de optie voor het automatisch goedkeuren van nieuwe machtigingen te selecteren. 
11. Klik op **OK** om de app(s) op te nemen die u hebt goedgekeurd.
12. Klik op **Synchroniseren** in het deelvenster **App-app** om te synchroniseren met de Beheerd Google Play-service.

## <a name="synchronize-a-managed-google-play-app-with-intune-alternative"></a>Een beheerde Google Play-app synchroniseren met Intune (alternatief)
Als u liever een beheerde Google Play-app met Intune synchroniseert in plaats deze rechtstreeks met behulp van Intune toe te voegen, gebruikt u de volgende stappen.

> [!IMPORTANT]
> De onderstaande informatie biedt een alternatieve methode voor het toevoegen van een beheerde Google Play-app met behulp van Intune, zoals hierboven beschreven.

### <a name="synchronize-an-app-from-the-managed-google-play-store"></a>Een app uit de beheerde Google Play Store synchroniseren

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

    De app is goedgekeurd en wordt weergegeven in uw IT-beheerconsole. U kunt vervolgens de [Android-werkprofiel-app synchroniseren met Intune](apps-add-android-for-work.md#sync-a-managed-google-play-app-with-intune).

### <a name="sync-a-managed-google-play-app-with-intune"></a>Een beheerde Google Play Store-app met Intune synchroniseren

Als u een app uit de store hebt goedgekeurd maar deze nog niet wordt weergegeven in het knooppunt **Apps met licentie** van de workload **Client-apps**, dwingt u als volgt een onmiddellijke synchronisatie af:

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer in het deelvenster **Intune** de optie **Client-apps**.
4. Selecteer in het workloadvenster **Client-apps**, onder **Installatie** de optie **Beheerde Google Play Store**.
5. Kies in het deelvenster **Beheerde Google Play Store** **Vernieuwen**.  
    De pagina werkt de tijd en de status van de laatste synchronisatie bij.
6. Selecteer in het workloadvenster **Client-apps** de optie **Apps**.  
    De zojuist beschikbaar geworden beheerde Google Play Store-app wordt weergegeven.

## <a name="assigning-the-managed-google-play-app"></a>De beheerde Google Play-app toewijzen

Als de app wordt weergegeven in het knooppunt **App-licenties** van het workloadvenster **Client-apps**, kunt u de app [net als alle andere apps toewijzen](/intune-azure/manage-apps/deploy-apps) door de app aan groepen gebruikers toe te voegen.

Nadat u de app hebt toegewezen, wordt deze geïnstalleerd op de apparaten die u hebt aangewezen. De gebruiker van het apparaat wordt geen toestemming voor de installatie gevraagd.

## <a name="manage-android-enterprise-app-permissions"></a>Machtigingen voor Android Enterprise-apps beheren
Android Enterprise vereist dat u apps goedkeurt in de beheerde Google Play Store-webconsole voordat u de apps met Intune synchroniseert en aan uw gebruikers toewijst. Met Android Enterprise kunt u de apps op de achtergrond en automatisch naar de apparaten van gebruikers pushen. U moet daarom de machtigingen voor de app namens al uw gebruikers accepteren. Gebruikers krijgen geen app-machtigingen te zien wanneer ze de apps installeren. Het is dus belangrijk dat u de informatie over de machtigingen begrijpt.

Wanneer een app-ontwikkelaar machtigingen bijwerkt met een nieuwe versie van de app, worden de machtigingen niet automatisch geaccepteerd, zelfs niet wanneer u de vorige machtigingen ook al had goedgekeurd. Apparaten met de oude versie van de app kunnen deze nog steeds gebruiken. De app is echter niet bijgewerkt tot de nieuwe machtigingen zijn goedgekeurd. Op apparaten waar de app niet op is geïnstalleerd, worden deze pas geïnstalleerd wanneer de nieuwe machtigingen voor de app zijn goedgekeurd.

### <a name="update-app-permissions"></a>App-machtigingen bijwerken

Bezoek met enige regelmaat de beheerde Google Play-console om te controleren op nieuwe machtigingen. U kunt de Google Play zodanig configureren dat u of anderen een e-mailbericht ontvangen wanneer nieuwe machtigingen voor een goedgekeurde app zijn vereist. Als u een app toewijst en u ziet dat deze niet is geïnstalleerd op apparaten, controleert u aan de hand van de volgende stappen op nieuwe machtigingen:

1. Ga naar [Google Play](https://play.google.com/work).
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

## <a name="delete-managed-google-play-apps"></a>Beheerde Google Play-apps verwijderen
Indien noodzakelijk, kunt u beheerde Google Play-apps verwijderen uit Microsoft Intune. Als u een beheerde Google Play-app wilt verwijderen, opent u Microsoft Intune in de Azure-portal en selecteert u **Client-apps** > **Apps**. In de lijst met apps selecteert u het beletselteken (...) rechts naast de beheerde Google Play-app en vervolgens **Verwijderen** in de weergegeven lijst. Wanneer u een beheerde Google Play-app uit de lijst met apps verwijdert, wordt de goedkeuring voor de beheerde Google Play-app automatisch verwijderd.

## <a name="next-steps"></a>Volgende stappen

- [Apps aan groepen toewijzen](apps-deploy.md)
