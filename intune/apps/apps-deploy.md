---
title: Apps toewijzen aan groepen in Microsoft Intune
titleSuffix: ''
description: Hier leest u meer informatie over het toewijzen van een Intune-app aan groepen gebruikers of apparaten met behulp van Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 15d6a67cb41455a1e3c0830e9ed242bfa52b0269
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912655"
---
# <a name="assign-apps-to-groups-with-microsoft-intune"></a>Apps toewijzen aan groepen met Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Nadat u [een app hebt toegevoegd](apps-add.md) aan Microsoft Intune, kunt u de app toewijzen aan gebruikers en apparaten. Het is belangrijk dat u weet dat u een app kunt toewijzen aan een apparaat, ongeacht of het apparaat wordt beheerd in Intune.

> [!NOTE]
> De Beschikbare implementatie-opzet wordt niet ondersteund voor apparaatgroepen. Alleen gebruikersgroepen worden ondersteund.

In de volgende tabellen worden de verschillende opties vermeld voor het toewijzen van apps aan gebruikers en apparaten:

|   | Apparaten die zijn ingeschreven met Intune | Apparaten die niet zijn ingeschreven met Intune |
|-------------------------------------------------------------------------------------------|------------------------------|----------------------------------|
| Toewijzen aan gebruikers | Ja | Ja |
| Toewijzen aan apparaten | Ja | Nee |
| Ingepakte apps of apps waarin Intune SDK is opgenomen (voor app-beveiligingsbeleid) toewijzen | Ja | Ja |
| Apps toewijzen als beschikbaar | Ja | Ja |
| Apps toewijzen als vereist | Ja | Nee |
| Apps verwijderen | Ja | Nee |
| App-updates ontvangen van Intune | Ja | Nee |
| Eindgebruikers installeren beschikbare apps vanuit de bedrijfsportal-app | Ja | Nee |
| Eindgebruikers installeren beschikbare apps vanaf de webversie van de bedrijfsportal-app | Ja | Ja |

> [!NOTE]
> Momenteel kunt u iOS- en Android-apps (Line-Of-Business-apps en apps die in de Store zijn gekocht) toewijzen aan apparaten die niet zijn ingeschreven bij Intune.
>
> Voor het ontvangen van app-updates op apparaten die niet zijn ingeschreven bij Intune, moeten gebruikers naar de bedrijfsportal van hun organisatie gaan en de app-updates handmatig installeren.

## <a name="assign-an-app"></a>Een app toewijzen

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps**.
3. Selecteer in het deelvenster **Apps** de app die u wilt toewijzen.
4. Selecteer **Toewijzingen** in de sectie **Beheren** van het menu.
5. Selecteer **Groep toevoegen** om het deelvenster **Groep toevoegen** te openen dat is gerelateerd aan de app.
6. Selecteer een **toewijzingstype** voor de specifieke app:
   - **Beschikbaar voor ingeschreven apparaten**: wijs de app toe aan groepen gebruikers die de app vanuit de bedrijfsportal-app of -website installeren.
   - **Beschikbaar met of zonder inschrijving**: deze app wordt toegewezen aan groepen gebruikers van wie de apparaten niet zijn ingeschreven bij Intune. Gebruikers moeten een Intune-licentie toegewezen krijgen, zie [Intune-licenties](../fundamentals/licenses.md).
   - **Vereist**: de app wordt geïnstalleerd op apparaten in de geselecteerde groepen. Sommige platformen hebben mogelijk aanvullende prompts voor de eindgebruiker ter bevestiging voordat de installatie van de app begint.
   - **Verwijderen**: de app wordt verwijderd van apparaten in de geselecteerde groepen als Intune de toepassing eerder op het apparaat heeft geïnstalleerd via de toewijzingen 'Beschikbaar voor ingeschreven apparaten' of 'Vereist' met behulp van dezelfde implementatie. Webkoppelingen kunnen niet worden verwijderd na implementatie.

     > [!NOTE]
     > **Alleen voor iOS-apps**:
     > - Als u wilt configureren wat er gebeurt met beheerde apps wanneer apparaten niet meer worden beheerd, kunt u de gewenste instelling selecteren onder **Verwijderen bij verwijdering van apparaat**. Zie [Instelling voor verwijderen van apps voor beheerde iOS-apps](apps-deploy.md#app-uninstall-setting-for-ios-managed-apps) voor meer informatie.
     > - als u een iOS VPN-profiel hebt gemaakt met VPN-instellingen per app, kunt u het VPN-profiel selecteren onder **VPN**. Als de app wordt uitgevoerd, wordt de VPN-verbinding geopend. Zie [VPN=instellingen voor iOS-apparaten](../vpn-settings-ios.md) voor meer informatie.
     >
     > **Alleen bij Android apps**: als u een Android-app als **Beschikbaar met of zonder inschrijving** implementeert, is de rapportagestatus alleen beschikbaar op ingeschreven apparaten.
     >
     > Voor **Beschikbaar voor ingeschreven apparaten**: De app wordt alleen als beschikbaar weergegeven als de gebruiker die is aangemeld bij de bedrijfsportal de primaire gebruiker is die het apparaat heeft geregistreerd en de app van toepassing is op het apparaat.

7. Selecteer **Opgenomen groepen** om de gebruikersgroepen te selecteren die worden beïnvloed door deze app-toewijzing.
8. Kies **Selecteren** wanneer u één of meer groepen hebt geselecteerd om op te nemen.
9. Selecteer **OK** op het deelvenster **Toewijzen** de selectie te voltooien van de groepen die moeten worden opgenomen.
10. Selecteer **Groepen uitsluiten** als u gebruikersgroepen wilt uitsluiten zodat ze niet worden beïnvloed door deze app-toewijzing.
11. Kies **Selecteren** in **Groepen selecteren** als u hebt besloten dat u groepen wilt uitsluiten.
12. Selecteer **OK** in het deelvenster **Groep toevoegen**.
13. Selecteer **Opslaan** in het deelvenster **Toewijzingen**.

De app wordt nu toegewezen aan de groepen die u hebt geselecteerd. Zie [App-toewijzingen opnemen en uitsluiten](apps-inc-exl-assignments.md) voor meer informatie over het opnemen en uitsluiten van app-toewijzingen.

## <a name="how-conflicts-between-app-intents-are-resolved"></a>Hoe conflicten tussen app-intents worden opgelost

Het is niet mogelijk om meerdere app-toewijzingsintenties in te stellen voor één groep, maar als een gebruiker of apparaat lid is van meerdere groepen waaraan verschillende intenties zijn toegewezen, resulteert dit in een conflict. Het is raadzaam om toewijzingsconflicten voor toepassingen te vermijden.
De informatie in de volgende tabel kan u helpen de resulterende intentie te begrijpen wanneer dit conflict plaatsvindt:

| Intent van groep 1 | Intent van groep 2 | Resulterende intent |
|-----------------------------------|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Gebruiker vereist|Gebruiker beschikbaar|Vereist en beschikbaar|
|Gebruiker vereist|Gebruiker verwijderen|Vereist|
|Gebruiker beschikbaar|Gebruiker verwijderen|Verwijderen|
|Gebruiker vereist|Apparaat vereist|Beide bestaan, Intune verwerkt Vereist
|Gebruiker vereist|Apparaat verwijderen|Beide bestaan, Intune zet Vereist om
|Gebruiker beschikbaar|Apparaat vereist|Beide bestaan, Intune zet Vereist om (Vereist en Beschikbaar)
|Gebruiker beschikbaar|Apparaat verwijderen|Beide bestaan, Intune zet Beschikbaar om.<br><br>App wordt weergegeven in de bedrijfsportal.<br><br>Als de app al is geïnstalleerd (als een vereiste app bij de vorige intentie), wordt de app verwijderd.<br><br>Als de gebruiker **Installeren vanuit de bedrijfsportal** selecteert, wordt de app geïnstalleerd en wordt de intentie om te verwijderen niet gehonoreerd.|
|Gebruiker verwijderen|Apparaat vereist|Beide bestaan, Intune zet Vereist om|
|Gebruiker verwijderen|Apparaat verwijderen|Beide bestaan, Intune zet Verwijderen om|
|Apparaat vereist|Apparaat verwijderen|Vereist|
|Gebruiker vereist en beschikbaar|Gebruiker beschikbaar|Vereist en beschikbaar|
|Gebruiker vereist en beschikbaar|Gebruiker verwijderen|Vereist en beschikbaar|
|Gebruiker vereist en beschikbaar|Apparaat vereist|Beide bestaan, Vereist en Beschikbaar
|Gebruiker vereist en beschikbaar|Apparaat verwijderen|Beide bestaan, Intune zet Vereist om (Vereist en Beschikbaar)
|Gebruiker beschikbaar zonder registratie|Gebruiker vereist en beschikbaar|Vereist en beschikbaar
|Gebruiker beschikbaar zonder registratie|Gebruiker vereist|Vereist
|Gebruiker beschikbaar zonder registratie|Gebruiker beschikbaar|Beschikbaar|
|Gebruiker beschikbaar zonder registratie|Apparaat vereist|Vereist en beschikbaar zonder registratie|
|Gebruiker beschikbaar zonder registratie|Apparaat verwijderen|Verwijderen en beschikbaar zonder registratie<br><br>Als de gebruiker de app niet heeft geïnstalleerd vanuit de bedrijfsportal, wordt de intentie om te verwijderen gehonoreerd.<br><br>Als de gebruiker de app vanuit de bedrijfsportal installeert, krijgt de installatie prioriteit boven het verwijderen van de app.|

> [!NOTE]
> Alleen voor beheerde iOS Store-apps: wanneer u deze apps toevoegt in Microsoft Intune en toewijst als **Vereist**, worden de apps automatisch gemaakt met zowel de intentie **Vereist** als **Beschikbaar**.<br><br>
> iOS Store-apps (geen iOS VPP-apps) die met de vereiste intentie worden benaderd, worden afgedwongen op het apparaat op het moment dat het apparaat incheckt en worden ook weergegeven in de bedrijfsportal-app.<br><br>
> Wanneer er conflicten optreden bij de instelling **Verwijderen bij verwijdering van apparaat**, wordt de app niet van het apparaat verwijderd als het apparaat niet meer wordt beheerd.

## <a name="managed-google-play-app-deployment-to-unmanaged-devices"></a>Implementatie van beheerde Google Play-apps op niet-beheerde apparaten
Voor Android-apparaten in een niet-ingeschreven APP-WE-implementatiescenario (App Protection Policy Without Enrollment), kunt u de beheerde Google Play Store gebruiken om store-apps en LOB-apps (line-of-business) te implementeren bij gebruikers. Beheerde Google Play-apps met de instelling **Beschikbaar met of zonder inschrijving** worden weergegeven in de Play Store-app op het apparaat van de eindgebruiker en niet in de bedrijfsportal-app. De eindgebruiker kan vanuit de Google Play-app in apps bladeren en apps installeren die op deze manier zijn geïmplementeerd. Omdat de apps worden geïnstalleerd vanuit de beheerde Google Play Store, hoeft de eindgebruiker diens apparaatinstellingen niet te wijzigen om de installatie van apps uit onbekende bronnen toe te staan. Dit zorgt ervoor dat de apparaten beter beveiligd zijn. Als de app-ontwikkelaar een nieuwe versie van een app die op het apparaat van een gebruiker was geïnstalleerd, publiceert in de Play Store, wordt de app automatisch bijgewerkt door Google Play. 

Stappen voor het toewijzen van beheerde Google Play-apps aan niet-beheerde apparaten:

1. Verbind uw Intune-tenant met de beheerde Google Play Store. Als u dit al hebt gedaan om het Android Enterprise-werkprofiel, of toegewezen of volledig beheerde Android Enterprise-apparaten te beheren, hoeft u dit niet opnieuw te doen.
2. Apps vanuit de beheerde Google Play Store toevoegen aan uw Intune-console.
3. Toon beheerde Google Play-apps aan de gewenste gebruikersgroep als **Beschikbaar met of zonder inschrijving**. De instellingen **Vereist** en **Verwijderen** voor app-targeting worden niet ondersteund voor niet-ingeschreven apparaten.
4. Een beveiligingsbeleid voor apps toewijzen aan de gebruikersgroep.
5. De volgende keer dat de eindgebruiker de bedrijfsportal-app opent, ziet deze een bericht dat aangeeft dat er apps beschikbaar zijn in de Play Store-app.  Als de gebruiker op de melding tikt, wordt hij of zij rechtstreeks naar de Play-app geleid, waar zakelijke apps worden weergegeven. Ook kan de gebruiker afzonderlijk naar de Play Store-app navigeren.
6. De eindgebruiker kan het contextmenu in de Play Store-app uitvouwen, en schakelen tussen diens persoonlijke Google-account (waar de persoonlijke apps te zien zijn) en werkaccount (waar store- en LOB-apps te zien zijn die op hem of haar zijn gericht). Eindgebruikers installeren de apps door in de Play Store-app op Installeren te tikken.

Als er opdracht wordt gegeven voor selectieve verwijdering op basis van APP in de Intune-console, wordt het werkaccount automatisch verwijderd uit de Play Store-app en kan de eindgebruiker vanaf dat moment geen zakelijke apps meer zien in de catalogus van de Play Store-app. Wanneer het werkaccount van een apparaat wordt verwijderd, blijven de apps die vanuit de Play Store zijn geïnstalleerd, op het apparaat staan. Deze apps worden niet verwijderd. 

## <a name="app-uninstall-setting-for-ios-managed-apps"></a>Instelling voor verwijderen van apps voor beheerde iOS-apps
Voor iOS-apparaten kunt u kiezen wat er gebeurt met beheerde apps bij het ongedaan maken van de registratie van het apparaat bij Intune of bij het verwijderen van het beheerprofiel. Hiertoe gebruikt u de instelling **Verwijderen bij verwijdering van apparaat**. Deze instelling is alleen van toepassing op apps nadat het apparaat is ingeschreven en apps zijn geïnstalleerd als beheerde apps. De instelling kan niet worden geconfigureerd voor web-apps of webkoppelingen. Alleen gegevens die worden beveiligd door Mobile Application Management (MAM) worden verwijderd na buitengebruikstelling door middel van selectief wissen van een app.

De standaardwaarden voor de instelling worden als volgt vooraf ingevuld voor nieuwe toewijzingen:

|iOS-apptype | Standaardinstelling voor Verwijderen bij verwijdering van apparaat |
|--------------------|----------------|
| Line-Of-Business-app | Ja |
| Store-app | Nee |
| VPP-app | Nee |
| Ingebouwde app | Nee |

>[!NOTE]
>**Beschikbaar-toewijzingstypen:** Als u deze instelling bijwerkt voor groepen van het type 'Beschikbaar voor ingeschreven apparaten' of 'Beschikbaar met of zonder inschrijving', krijgen gebruikers die de beheerde app al hebben, de bijgewerkte instelling pas nadat ze het apparaat met Intune hebben gesynchroniseerd en de app opnieuw hebben geïnstalleerd. 
>
>**Bestaande toewijzingen:** Toewijzingen die al bestonden vóór de introductie van deze instelling, blijven ongewijzigd en alle beheerde apps op het apparaat worden verwijderd uit het beheer.

## <a name="next-steps"></a>Volgende stappen

Zie [Apps controleren](apps-monitor.md) voor meer informatie over het controleren van app-toewijzingen.
