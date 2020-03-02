---
title: Beheerde Google Play-apps toewijzen aan Android Enterprise-apparaten
titleSuffix: Microsoft Intune
description: Ontdek hoe u apps synchroniseert en toewijst aan Android Enterprise-apparaten vanuit de beheerde Google Play Store.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/22/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: a4b3bd06bad6c31c2d0fb4c31a7ad605af96be86
ms.sourcegitcommit: 29f3ba071c9348686d3ad6f3b8864d8557e05b97
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/26/2020
ms.locfileid: "77609196"
---
# <a name="add-managed-google-play-apps-to-android-enterprise-devices-with-intune"></a>Beheerde Google Play-apps toevoegen aan Android Enterprise-apparaten met Intune

Beheerde Google Play is de zakelijke App Store van Google en tevens de enige bron van toepassingen voor Android Enterprise. U kunt Intune gebruiken om de implementatie van apps te organiseren via Beheerde Google Play voor elk Android Enterprise-scenario (inclusief werkprofiel, toegewezen en volledig beheerde inschrijvingen). Hoe u beheerde Google Play-apps toevoegt aan Intune, verschilt van de manier waarop Android-apps worden toegevoegd voor niet-Android Enterprise-apparaten. Store-apps, LOB-apps (Line-Of-Business) en web-apps worden goedgekeurd in of toegevoegd aan beheerde Google Play en vervolgens gesynchroniseerd met Intune, zodat ze worden weergegeven in de lijst met client-apps. Als ze in de lijst met client-apps worden weergegeven, kunt u de toewijzing van elke beheerde Google Play-app beheren zoals elke andere app.

In Intune worden automatisch vier veelgebruikte Android Enterprise-apps toegevoegd aan de Intune-beheerconsole, bij het verbinding maken tussen uw Intune-tenant en beheerde Google Play, om het u gemakkelijker te maken Android Enterprise-beheer te configureren en te gebruiken. Die vier apps zijn:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** : wordt gebruikt voor scenario's met volledig beheer door Android Enterprise. Deze app wordt automatisch geïnstalleerd op volledig beheerde apparaten tijdens het apparaatinschrijvingsproces.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** : om u aan te melden bij uw accounts als u verificatie in twee stappen gebruikt. Deze app wordt automatisch geïnstalleerd op volledig beheerde apparaten tijdens het apparaatinschrijvingsproces.
- **[Intune-bedrijfsportal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** : wordt gebruikt voor beleidsregels voor app-beveiliging (APP) en werkprofielscenario's van Android Enterprise.
- **[Managed Home Screen](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise)** : wordt gebruikt voor toegewezen kiosk-scenario's van Android Enterprise voor meerdere apps. IT-beheerders moeten een toewijzing maken om deze app te installeren op toegewezen apparaten die worden gebruikt in kiosk-scenario's voor meerdere apps.

>[!NOTE]
>Wanneer eindgebruikers hun volledig beheerde Android Enterprise-apparaat inschrijven, wordt de Intune-bedrijfsportal-app automatisch geïnstalleerd en is het pictogram van de toepassing mogelijk zichtbaar voor de eindgebruiker. Als de eindgebruiker probeert de Intune-bedrijfsportal-app te starten, wordt de eindgebruiker omgeleid naar de Microsoft Intune-app en wordt het pictogram van de bedrijfsportal-app vervolgens verborgen.

## <a name="before-you-start"></a>Voordat u begint
- Uw Intune-tenant moet verbonden zijn met de beheerde Google Play Store.  Zie [Uw Intune-account verbinden met uw Beheerde Google Play-account](../enrollment/connect-intune-android-enterprise.md) voor meer informatie.
- Zorg ervoor dat u Intune en Android-werkprofielen hebt geconfigureerd voor samenwerking in de workload **Apparaatinschrijving** van de Azure-portal als u van plan bent om apparaten met een werkprofiel in te schrijven. Zie [Enroll Android devices](../enrollment/android-work-profile-enroll.md) (Android-apparaten registreren) voor meer informatie.

>[!NOTE]
>Als u met Microsoft Intune werkt, kunt u beter de Microsoft Edge- of Google Chrome-browser gebruiken.

## <a name="managed-google-play-app-types"></a>Typen beheerde Google Play-apps
Er zijn drie typen apps met beheerde Google Play beschikbaar:

- **Beheerde Google Play Store-app**: openbare apps die algemeen beschikbaar zijn in de Play Store. U kunt deze apps in Intune beheren door te bladeren naar de apps die u wilt beheren, de apps goed te keuren en deze vervolgens te synchroniseren met Intune.
- **Privé-app uit beheerde Google Play Store**: dit zijn LOB-apps die zijn gepubliceerd in de beheerde Google Play Store door Intune-beheerders.  Deze apps zijn privé en zijn alleen beschikbaar voor uw Intune-tenant. Dit is hoe LOB-apps worden beheerd en geïmplementeerd met beheerde Google Play en Android Enterprise.
- **Webkoppeling voor beheerde Google Play**: webkoppelingen met door IT-beheerders gedefinieerde pictogrammen die kunnen worden geïmplementeerd op Android Enterprise-apparaten. Deze worden weergegeven op apparaten in de lijst met apps van het apparaat, net als bij gewone apps.

## <a name="managed-google-play-store-apps"></a>Beheerde Google Play Store-apps
Er zijn twee manieren om beheerde Google Play Store-apps te zoeken en goed te keuren met Intune:

1. Rechtstreeks in de Intune-console: zoek apps in de Store en keur ze goed in een weergave die wordt gehost binnen Intune. De weergave is direct beschikbaar in de Intune-console en u hoeft zich dus niet opnieuw te verifiëren met een ander account.
1. In de console van Beheerd Google Play: u kunt ook de console van Beheerd Google Play rechtstreeks openen en daar apps goedkeuren. Zie [Een beheerde Google Play-app met Intune synchroniseren](apps-add-android-for-work.md#sync-a-managed-google-play-app-with-intune) voor meer informatie.  Hiervoor is een afzonderlijke aanmelding vereist met het account dat u hebt gebruikt om uw Intune-tenant te verbinden met Beheerd Google Play.

### <a name="add-a-managed-google-play-store-app-directly-in-the-intune-console"></a>Een beheerde Google Play Store-app rechtstreeks toevoegen in de Intune-console

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. Selecteer in het deelvenster **Een app-type selecteren** onder de beschikbare typen **Store-app** de optie **Beheerde Google Play-app**.
4. Klik op **Selecteren**. De **Beheerde Google Play** App Store wordt weergegeven.

    > [!NOTE]
    > Uw Intune-tenantaccount moet zijn verbonden met uw Android Enterprise-account om door beheerde Google Play Store-apps te kunnen bladeren. Zie [Uw Intune-account verbinden met uw Beheerde Google Play-account](../enrollment/connect-intune-android-enterprise.md) voor meer informatie.

5. Selecteer een app om de details van de app weer te geven.
6. Op de pagina waarop de app wordt weergegeven, klikt u op **Goedkeuren**. Er wordt een venster voor de app geopend, waarin u om toestemming wordt gevraagd voor het uitvoeren van verschillende bewerkingen door de app.
7. Selecteer **Goedkeuren** om de app-machtigingen te accepteren en door te gaan.
8. Selecteer **Goedgekeurd houden wanneer de app nieuwe machtigingen aanvraagt** in het venster **Instellingen voor goedkeuring** en klik vervolgens op **Gereed**. 

    > [!IMPORTANT]
    > Als u deze optie niet kiest, moet u handmatig alle nieuwe machtigingen goedkeuren als de app-ontwikkelaar een update publiceert. Hierdoor worden installaties en updates van de app gestopt totdat de machtigingen zijn goedgekeurd. Daarom wordt het aanbevolen de optie voor het automatisch goedkeuren van nieuwe machtigingen te selecteren. 

9. Klik op **Selecteren** om de app te selecteren.
10. Klik boven aan de blade op **Synchroniseren** om de app te synchroniseren met de Beheerde Google Play-service.
11. Klik op **Vernieuwen** om de lijst met apps bij te werken en de zojuist toegevoegde app weer te geven.

### <a name="add-a-managed-google-play-store-app-in-the-managed-google-play-console-alternative"></a>Een beheerde Google Play Store-app toevoegen in de beheerde Google Play-console (alternatief)
Als u liever een beheerde Google Play-app met Intune synchroniseert in plaats deze rechtstreeks met behulp van Intune toe te voegen, gebruikt u de volgende stappen.

> [!IMPORTANT]
> De onderstaande informatie biedt een alternatieve methode voor het toevoegen van een beheerde Google Play-app met behulp van Intune, zoals hierboven beschreven.

1. Ga naar de [beheerde Google Play Store](https://play.google.com/work). Meld u aan met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android Enterprise te configureren.
2. Zoek in de store naar de app die u wilt toewijzen met behulp van Intune en selecteer deze.
3. Op de pagina waarop de app wordt weergegeven, klikt u op **Goedkeuren**.  
    In het volgende voorbeeld is de app van Microsoft Excel gekozen.

    ![De knop Goedkeuren in de beheerde Google Play Store](./media/apps-add-android-for-work/approve.png)

   Er wordt een venster voor de app geopend, waarin u om toestemming wordt gevraagd voor het uitvoeren van verschillende bewerkingen door de app.

4. Selecteer **Goedkeuren** om de app-machtigingen te accepteren en door te gaan.

    ![De knop Goedkeuren voor app-machtigingen](./media/apps-add-android-for-work/approve-app-permissions.png)

5. Selecteer een optie om de nieuwe machtigingsaanvragen voor de app te verwerken en selecteer vervolgens **Opslaan**.

    ![Opties om nieuwe machtigingsaanvragen voor de app te verwerken](./media/apps-add-android-for-work/approve-app-settings.png)

    De app is goedgekeurd en wordt weergegeven in uw IT-beheerconsole. U kunt vervolgens de [Android-werkprofiel-app synchroniseren met Intune](apps-add-android-for-work.md#sync-a-managed-google-play-app-with-intune).

## <a name="managed-google-play-private-lob-apps"></a>Privé-LOB-apps uit de beheerde Google Play Store

Er zijn twee manieren om LOB-apps toe te voegen aan Beheerd Google Play:

1. Rechtstreeks in de Intune-console: u kunt LOB-apps dan toevoegen door alleen de app-APK en een titel in te dienen, vanuit Intune. Voor deze methode is geen Google-ontwikkelaarsaccount nodig en u hoeft dus ook geen kosten te betalen om u bij Google te registreren als ontwikkelaar.  Deze methode is eenvoudiger en bestaat uit veel minder stappen, waardoor LOB-apps binnen slechts tien minuten beschikbaar zijn voor beheer.
1. In de Google Play-ontwikkelaarsconsole: als u een Google-ontwikkelaarsaccount hebt of geavanceerde distributiefuncties wilt configureren die alleen beschikbaar zijn in de Google Play-ontwikkelaarsconsole (zoals het toevoegen van extra schermafbeeldingen voor apps), kunt u de [Google Play-ontwikkelaarsconsole](https://play.google.com/apps/publish) gebruiken. 

### <a name="managed-google-play-private-lob-app-publishing-directly-in-the-intune-console"></a>Privé-LOB-apps uit de beheerde Google Play Store rechtstreeks publiceren in de Intune-console

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. Selecteer in het deelvenster **Een app-type selecteren** onder de beschikbare typen **Store-app** de optie **Beheerde Google Play-app**.
4. Klik op **Selecteren**. De **Beheerde Google Play** App Store wordt weergegeven in Intune.
5. Selecteer **Privé-apps** (naast het pictogram *Vergrendelen*) in het Google Play-venster. 
6. Klik op de knop **+** rechts onderaan om een nieuwe app toe te voegen.
7. Voeg een **Titel** toe voor de app en klik op **APK uploaden** om het app-pakket toe te voegen.
8. Klik op **Maken**.
9. Sluit het deelvenster Beheerde Google Play als u klaar bent met het toevoegen van apps.
10. Klik op **Synchroniseren** in het deelvenster **App-app** om te synchroniseren met de Beheerd Google Play-service. 

    > [!NOTE]
    > Het kan enkele minuten duren voordat privé-apps beschikbaar zijn voor synchronisatie. Als de app niet wordt weergegeven wanneer u de eerste keer een synchronisatie uitvoert, wacht u enkele minuten en start u een nieuwe synchronisatie.

Zie het volgende ondersteuningsartikel van Google voor meer informatie over beheerde Google Play-privé-apps, waaronder veelgestelde vragen: https://support.google.com/googleplay/work/answer/9146439

>[!IMPORTANT]
>Privé-apps die met deze methode worden toegevoegd, kunnen nooit openbaar worden gemaakt. Gebruik deze publicatiemethode daarom alleen als u zeker weet dat deze app altijd privé zal blijven voor uw organisatie.

### <a name="managed-google-play-private-lob-app-publishing-using-the-google-developer-console"></a>Privé-LOB-apps in de beheerde Google Play Store publiceren met de Google-console voor ontwikkelaars

1. Meld u aan bij de [Google Play Store-ontwikkelaarsconsole](https://play.google.com/apps/publish) met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android Enterprise te configureren.  
    Als u zich voor het eerst aanmeldt, moet u zich registreren en betalen om lid te worden van het Google-ontwikkelaarsprogramma.
2. Selecteer in de console **Nieuwe toepassing toevoegen**.
3. U uploadt en verstrekt informatie over uw app op dezelfde manier als bij het publiceren van een app naar de Google Play store. U moet echter wel **Deze toepassing alleen beschikbaar maken voor mijn organisatie (<*organisatienaam*>)** selecteren.

    ![De app alleen voor uw organisatie beschikbaar maken](./media/apps-add-android-for-work/restrict.png)

    Via deze bewerking komt de app alleen voor uw organisatie beschikbaar. Deze is dan niet beschikbaar in de openbare Google Play Store.

    Raadpleeg voor meer informatie over Android-apps uploaden en publiceren [Help bij Google-ontwikkelaarsconsole](https://support.google.com/googleplay/android-developer/answer/113469).
4. Nadat u uw app hebt gepubliceerd, meldt u zich aan bij de [beheerde Google Play Store](https://play.google.com/work) met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android Enterprise te configureren.
5. Controleer in het knooppunt **Apps** van de store of de door u gepubliceerde app wordt weergegeven.  
    De app is automatisch goedgekeurd om te worden gesynchroniseerd met Intune.

## <a name="managed-google-play-web-links"></a>Beheerde Google Play-webkoppelingen

Beheerde Google Play-webkoppelingen kunnen net als andere Android-apps worden geïnstalleerd en beheerd. Wanneer de koppeling is geïnstalleerd op een apparaat, wordt deze weergegeven in de lijst met apps van de gebruiker, samen met de andere apps die de gebruiker heeft geïnstalleerd. Wanneer u op de koppeling tikt, wordt deze geopend in de browser van het apparaat.

Webkoppelingen worden geopend met Microsoft Edge of een andere browser-app die u hebt geïmplementeerd. Zorg ervoor dat u ten minste één browser-app op apparaten implementeert, zodat webkoppelingen goed kunnen worden geopend. Alle **weergave-opties** die beschikbaar zijn voor webkoppelingen (volledig scherm, zelfstandig en minimale gebruikersinterface) werken echter alleen met Chrome. 

> [!IMPORTANT]
> Op het moment van publiceren van dit document is er een Google-fout bekend die voorkomt dat webkoppelingen worden geopend op apparaten met andere browsers dan Chrome. Google heeft aangegeven dit probleem te gaan verhelpen.  Deze mededeling wordt verwijderd wanneer Microsoft bevestiging heeft van Google dat het probleem is opgelost.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. Selecteer in het deelvenster **Een app-type selecteren** onder de beschikbare typen **Store-app** de optie **Beheerde Google Play-app**.
4. Klik op **Selecteren**. De **Beheerde Google Play** App Store wordt weergegeven in Intune.
5. Selecteer **Web-apps** (naast het *wereldbolpictogram*) in het Google Play-venster.
6. Klik op de knop **+** rechts onderaan om een nieuwe app toe te voegen.
7. Voeg een **titel** voor de app en de **URL** van de web-app toe, selecteer hoe de app moet worden weergegeven en selecteer een app-pictogram.
8. Klik op **Maken**.
9. Sluit het deelvenster Beheerde Google Play als u klaar bent met het toevoegen van apps.
10. Klik op **Synchroniseren** in het deelvenster **App-app** om te synchroniseren met de Beheerd Google Play-service. 

    > [!NOTE]
    > Het kan enkele minuten duren voordat web-apps beschikbaar zijn voor synchronisatie. Als de app niet wordt weergegeven wanneer u de eerste keer een synchronisatie uitvoert, wacht u enkele minuten en start u een nieuwe synchronisatie.

## <a name="sync-a-managed-google-play-app-with-intune"></a>Een beheerde Google Play Store-app met Intune synchroniseren

Als u een app uit de Store hebt goedgekeurd maar deze nog niet wordt weergegeven in het workloadvenster **Apps**, start u als volgt een onmiddellijke synchronisatie:

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Selecteer **Apps** > **Tenantbeheer** > **Connectors en tokens** > **Beheerde Google Play**.
5. Kies in het deelvenster **Beheerde Google Play Store** **Vernieuwen**.  
    De pagina werkt de tijd en de status van de laatste synchronisatie bij.
6. Selecteer in het Microsoft Endpoint Manager-beheercentrum de opties **Apps** > **Alle apps**.  
    De zojuist beschikbaar geworden beheerde Google Play Store-app wordt weergegeven.

## <a name="assigning-a-managed-google-play-app-to-android-enterprise-work-profile-devices"></a>Beheerde Google Play-app toewijzen aan apparaten met Android Enterprise-werkprofiel

Als de app wordt weergegeven in het knooppunt **App-licenties** van het workloadvenster **Apps**, kunt u de app [net als alle andere apps toewijzen](/intune-azure/manage-apps/deploy-apps) door de app aan groepen gebruikers toe te wijzen.

Nadat u de app hebt toegewezen, wordt deze geïnstalleerd (of is deze beschikbaar voor installatie) op de apparaten van de gebruikers die u hebt aangewezen. De gebruiker van het apparaat wordt geen toestemming voor de installatie gevraagd. Zie [Inschrijving van apparaten met Android Enterprise-werkprofielen instellen](../enrollment/android-work-profile-enroll.md) voor meer informatie over apparaten met Android Enterprise-werkprofielen. 

> [!NOTE] 
> Alleen apps die zijn toegewezen, worden weergegeven in de beheerde Google Play Store voor een eindgebruiker. Daarom is dit een belangrijke stap die de beheerder moet uitvoeren bij het instellen van apps met beheerde Google Play.

## <a name="assigning-a-managed-google-play-app-to-android-enterprise-fully-managed-devices"></a>Beheerde Google Play-app toewijzen aan volledig beheerde Android Enterprise-apparaten

[Volledig beheerde Android Enterprise-apparaten](../enrollment/android-fully-managed-enroll.md) zijn apparaten in bedrijfseigendom voor één gebruiker, die uitsluitend worden gebruikt voor werk, niet voor persoonlijk gebruik. Gebruikers van volledig beheerde apparaten kunnen hun beschikbare bedrijfs-apps ophalen uit de beheerde Google Play-app op hun apparaat.

De standaardinstelling is dat werknemers met een volledig beheerd Android Enterprise-apparaat niet de mogelijkheid hebben om apps te installeren die niet zijn goedgekeurd door de organisatie. Werknemers kunnen evenmin geïnstalleerde apps verwijderen als dit tegen het beleid is. Als u gebruikers toegang wilt geven tot de volledige Google Play Store voor het installeren van apps in plaats van alleen toegang te hebben tot de goedgekeurde apps in de beheerde Google Play Store, kunt u **Toegang tot alle apps in Google Play Store toestaan** **inschakelen**. Met deze instelling hebben gebruikers toegang tot alle apps in de Google Play Store met behulp van hun bedrijfsaccount, maar kunnen de aankoopmogelijkheden beperkt zijn. U kunt de beperking voor beperkte aankopen verwijderen door gebruikers toe te staan nieuwe accounts toe te voegen aan het apparaat. Als u dit doet, kunnen eindgebruikers apps kopen in de Google Play Store via hun persoonlijke accounts, en ze kunnen dan in-app-aankopen doen. Zie [Android Enterprise-apparaatinstellingen voor beheer van functies vanuit Intune](../configuration/device-restrictions-android-for-work.md) voor meer informatie. 

> [!NOTE]
> De Microsoft Intune-app en de Microsoft Authenticator-app worden tijdens het onboarden als vereiste apps geïnstalleerd op alle volledig beheerde apparaten. De voordelen hiervan zijn dat er ondersteuning wordt geboden voor voorwaardelijke toegang en dat gebruikers van Microsoft Intune-apps problemen met naleving kunnen zien en oplossen. 

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

## <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices"></a>Aanvullende rapportage van beheerde Google Play-apps voor apparaten met Android Enterprise-werkprofiel

Voor beheerde Google Play-apps die op apparaten met Android Enterprise-werkprofiel zijn geïmplementeerd, kunt u de status en het versienummer van de op een apparaat geïnstalleerde app weergeven met Intune. 

## <a name="delete-managed-google-play-apps"></a>Beheerde Google Play-apps verwijderen
Indien noodzakelijk, kunt u beheerde Google Play-apps verwijderen uit Microsoft Intune. Als u een beheerde Google Play-app wilt verwijderen, opent u Microsoft Intune in Azure Portal en selecteert u **Apps** > **Alle apps**. In de lijst met apps selecteert u het beletselteken (...) rechts naast de beheerde Google Play-app en vervolgens **Verwijderen** in de weergegeven lijst. Wanneer u een beheerde Google Play-app uit de lijst met apps verwijdert, wordt de goedkeuring voor de beheerde Google Play-app automatisch verwijderd.

> [!NOTE]
> Als een app niet wordt goedgekeurd of wordt verwijderd uit de beheerde Google Play Store, wordt deze niet verwijderd uit de lijst met client-apps van Intune. Hierdoor kunt u nog steeds een beleid voor verwijderen toepassen op gebruikers, zelfs als de app niet is goedgekeurd.

## <a name="android-enterprise-system-apps"></a>Android Enterprise-systeem-apps

U kunt een Android Enterprise-systeem-app inschakelen voor [toegewezen Android Enterprise-apparaten](../enrollment/android-kiosk-enroll.md) of [volledig beheerde apparaten](../enrollment/android-fully-managed-enroll.md). Zie [Android Enterprise-systeem-apps toevoegen aan Microsoft Intune](apps-ae-system.md) voor meer informatie over het toevoegen van een Android Enterprise-systeem-app.

## <a name="next-steps"></a>Volgende stappen

- [Apps aan groepen toewijzen](apps-deploy.md)
