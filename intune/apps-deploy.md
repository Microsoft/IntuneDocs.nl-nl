---
title: Apps toewijzen aan groepen in Microsoft Intune
titlesuffix: ''
description: Hier leest u meer informatie over het toewijzen van een Intune-app aan groepen gebruikers of apparaten met behulp van Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/24/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8ff89d1776d71dc24ea675de167f3fd22d6bdf04
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55838764"
---
# <a name="assign-apps-to-groups-with-microsoft-intune"></a>Apps toewijzen aan groepen met Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

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

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer in het menu **Intune** de optie **Client-apps**.
4. Selecteer **Apps** in de sectie **Beheren** van het menu.
5. Selecteer in het deelvenster **Apps** de app die u wilt toewijzen.
6. Selecteer **Toewijzingen** in de sectie **Beheren** van het menu.
7. Selecteer **Groep toevoegen** om het deelvenster **Groep toevoegen** te openen dat is gerelateerd aan de app.
8. Selecteer een **toewijzingstype** voor de specifieke app:
   - **Beschikbaar voor ingeschreven apparaten**: wijs de app toe aan groepen gebruikers die de app vanuit de bedrijfsportal-app of -website installeren.
   - **Beschikbaar met of zonder inschrijving**: deze app wordt toegewezen aan groepen gebruikers van wie de apparaten niet zijn ingeschreven bij Intune. Gebruikers moeten een Intune-licentie toegewezen krijgen, zie [Intune-licenties](licenses.md).
   - **Vereist**: de app wordt geïnstalleerd op apparaten in de geselecteerde groepen. Sommige platformen hebben mogelijk aanvullende prompts voor de eindgebruiker ter bevestiging voordat de installatie van de app begint.
   - **Verwijderen**: de app wordt verwijderd van apparaten in de geselecteerde groepen als Intune de toepassing eerder op het apparaat heeft geïnstalleerd via de toewijzingen 'Beschikbaar voor ingeschreven apparaten' of 'Vereist' met behulp van dezelfde implementatie. Webkoppelingen kunnen niet worden verwijderd na implementatie.

     > [!NOTE]
     > **Alleen voor iOS-apps**: als u een iOS VPN-profiel hebt gemaakt met VPN-instellingen per app, kunt u het VPN-profiel selecteren onder **VPN**. Als de app wordt uitgevoerd, wordt de VPN-verbinding geopend. Zie [VPN=instellingen voor iOS-apparaten](vpn-settings-ios.md) voor meer informatie.
     >
     > **Alleen bij Android apps**: als u een Android-app als **Beschikbaar met of zonder inschrijving** implementeert, is de rapportagestatus alleen beschikbaar op ingeschreven apparaten.

9. Selecteer **Opgenomen groepen** om de gebruikersgroepen te selecteren die worden beïnvloed door deze app-toewijzing.
10. Kies **Selecteren** wanneer u één of meer groepen hebt geselecteerd om op te nemen.
11. Selecteer **OK** op het deelvenster **Toewijzen** de selectie te voltooien van de groepen die moeten worden opgenomen.
12. Selecteer **Groepen uitsluiten** als u gebruikersgroepen wilt uitsluiten zodat ze niet worden beïnvloed door deze app-toewijzing.
13. Kies **Selecteren** in **Groepen selecteren** als u hebt besloten dat u groepen wilt uitsluiten.
14. Selecteer **OK** in het deelvenster **Groep toevoegen**.
15. Selecteer **Opslaan** in het deelvenster **Toewijzingen**.

De app wordt nu toegewezen aan de groepen die u hebt geselecteerd. Zie [App-toewijzingen opnemen en uitsluiten](apps-inc-exl-assignments.md) voor meer informatie over het opnemen en uitsluiten van app-toewijzingen.

## <a name="how-conflicts-between-app-intents-are-resolved"></a>Hoe conflicten tussen app-intents worden opgelost

Soms wordt dezelfde app aan meerdere groepen toegewezen, maar met verschillende intenties. De informatie in de volgende tabel kan u helpen de resulterende intentie te begrijpen wanneer dit plaatsvindt:

| Intent van groep 1 | Intent van groep 2 | Resulterende intent |
|-----------------------------------|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Gebruiker vereist|Gebruiker beschikbaar|Vereist en beschikbaar|
|Gebruiker vereist|Gebruiker niet beschikbaar|Vereist|
|Gebruiker vereist|Gebruiker verwijderen|Vereist|
|Gebruiker beschikbaar|Gebruiker niet beschikbaar|Niet beschikbaar|
|Gebruiker beschikbaar|Gebruiker verwijderen|Verwijderen|
|Gebruiker niet beschikbaar|Gebruiker verwijderen|Verwijderen
|Gebruiker vereist|Apparaat vereist|Beide bestaan, Intune verwerkt Vereist
|Gebruiker vereist|Apparaat verwijderen|Beide bestaan, Intune zet Vereist om
|Gebruiker beschikbaar|Apparaat vereist|Beide bestaan, Intune zet Vereist om (Vereist en Beschikbaar)
|Gebruiker beschikbaar|Apparaat verwijderen|Beide bestaan, Intune zet Beschikbaar om.<br><br>App wordt weergegeven in de bedrijfsportal.<br><br>Als de app al is geïnstalleerd (als een vereiste app bij de vorige intentie), wordt de app verwijderd.<br><br>Als de gebruiker **Installeren vanuit de bedrijfsportal** selecteert, wordt de app geïnstalleerd en wordt de intentie om te verwijderen niet gehonoreerd.|
|Gebruiker niet beschikbaar|Apparaat vereist|Vereist|
|Gebruiker niet beschikbaar|Apparaat verwijderen|Verwijderen|
|Gebruiker verwijderen|Apparaat vereist|Beide bestaan, Intune zet Vereist om|
|Gebruiker verwijderen|Apparaat verwijderen|Beide bestaan, Intune zet Verwijderen om|
|Apparaat vereist|Apparaat verwijderen|Vereist|
|Gebruiker vereist en beschikbaar|Gebruiker beschikbaar|Vereist en beschikbaar|
|Gebruiker vereist en beschikbaar|Gebruiker verwijderen|Vereist en beschikbaar|
|Gebruiker vereist en beschikbaar|Gebruiker niet beschikbaar|Vereist en beschikbaar|
|Gebruiker vereist en beschikbaar|Apparaat vereist|Beide bestaan, Vereist en Beschikbaar
|Gebruiker vereist en beschikbaar|Apparaat niet beschikbaar|Vereist en beschikbaar|
|Gebruiker vereist en beschikbaar|Apparaat verwijderen|Beide bestaan, Intune zet Vereist om (Vereist en Beschikbaar)
|Gebruiker niet beschikbaar|Apparaat niet beschikbaar|Niet beschikbaar|
|Gebruiker beschikbaar|Apparaat niet beschikbaar|Beschikbaar|
|Gebruiker vereist|Apparaat niet beschikbaar|Vereist|
|Gebruiker beschikbaar zonder registratie|Gebruiker vereist en beschikbaar|Vereist en beschikbaar
|Gebruiker beschikbaar zonder registratie|Gebruiker vereist|Vereist
|Gebruiker beschikbaar zonder registratie|Gebruiker niet beschikbaar|Niet beschikbaar
|Gebruiker beschikbaar zonder registratie|Gebruiker beschikbaar|Beschikbaar|
|Gebruiker beschikbaar zonder registratie|Apparaat vereist|Vereist en beschikbaar zonder registratie|
|Gebruiker beschikbaar zonder registratie|Apparaat niet beschikbaar|Beschikbaar zonder registratie|
|Gebruiker beschikbaar zonder registratie|Apparaat verwijderen|Verwijderen en beschikbaar zonder registratie<br><br>Als de gebruiker de app niet heeft geïnstalleerd vanuit de bedrijfsportal, wordt de intentie om te verwijderen gehonoreerd.<br><br>Als de gebruiker de app vanuit de bedrijfsportal installeert, krijgt de installatie prioriteit boven het verwijderen van de app.|

> [!NOTE]
> Alleen voor beheerde iOS Store-apps: wanneer u deze apps toevoegt in Microsoft Intune en toewijst als **Vereist**, worden de apps automatisch gemaakt met zowel de intentie **Vereist** als **Beschikbaar**.<br><br>
> iOS Store-apps (geen iOS VPP-apps) die met de vereiste intentie worden benaderd, worden afgedwongen op het apparaat op het moment dat het apparaat incheckt en worden ook weergegeven in de bedrijfsportal-app.

## <a name="android-enterprise-app-we-app-deployment"></a>Android Enterprise APP WE-app-implementatie
Voor Android-apparaten in een niet-geregistreerd APP-WE-implementatiescenario (App Protection Policy Without Enrollment), gebruikt u de beheerde Google Play Store om store-apps en LOB-apps te implementeren bij gebruikers. In het bijzonder kunt u eindgebruikers voorzien van een app-catalogus en een installatie waarbij het niet langer nodig is dat eindgebruikers de beveiligingsstatus van hun apparaten versoepelen door installaties uit onbekende bronnen toe te staan. Bovendien biedt dit implementatiescenario een verbeterde eindgebruikerservaring. Zie [Een app toewijzen](apps-deploy.md#assign-an-app) voor de stappen om een app toe te wijzen.

## <a name="next-steps"></a>Volgende stappen

Zie [Apps controleren](apps-monitor.md) voor meer informatie over het controleren van app-toewijzingen.
