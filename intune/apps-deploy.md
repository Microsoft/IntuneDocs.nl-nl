---
title: Apps aan groepen toewijzen in Microsoft Intune
titlesuffix: 
description: Als u een app aan Microsoft Intune hebt toegevoegd, wilt u deze wellicht toewijzen aan groepen met gebruikers of apparaten.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: eba329be463fbf0593638bd4cf41c404a17f9cc0
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Apps aan groepen toewijzen met Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Wanneer u een app aan Microsoft Intune hebt toegevoegd, kunt u deze toewijzen aan gebruikers en apparaten.

Apps kunnen worden toegewezen aan apparaten, ongeacht of ze worden beheerd door Intune. In de volgende tabel ziet u de verschillende opties voor het toewijzen van apps aan gebruikers en apparaten.

||||
|-|-|-|-|
|&nbsp;|Apparaten die zijn ingeschreven met Intune|Apparaten die niet zijn ingeschreven met Intune|
|Toewijzen aan gebruikers|Ja|Ja|
|Toewijzen aan apparaten|Ja|Nee|
|Ingepakte apps of apps waarin Intune SDK is opgenomen (voor app-beveiligingsbeleid) toewijzen|Ja|Ja|
|Apps toewijzen als beschikbaar|Ja|Ja|
|Apps toewijzen als vereist|Ja|Nee|
|Apps verwijderen|Ja|Nee|
|App-updates ontvangen van Intune|Ja|Nee|
|Eindgebruikers installeren beschikbare apps vanuit de bedrijfsportal-app|Ja|Nee|
|Eindgebruikers installeren beschikbare apps vanuit de bedrijfsportal-app op internet|Ja|Ja|

> [!NOTE]
> Op dit moment kunt u iOS- en Android-apps (beide Line-Of-Business-apps en apps die in de Store zijn gekocht) toewijzen aan apparaten die niet met Intune zijn ingeschreven.<br></br><br></br>
> Voor het ontvangen van app-updates op apparaten die niet zijn ingeschreven bij Intune moeten gebruikers de bedrijfsportal openen en de app-updates handmatig installeren.

## <a name="how-to-assign-an-app"></a>Een app toewijzen

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies **Mobiele apps** op de blade **Intune**.
1. Kies in de workload **Mobiele apps** de optie **Apps** in de sectie **Beheren**.
2. Kies de app die u wilt toewijzen op de blade met de lijst met apps.
3. Kies op de app-specifieke blade **Overzicht** de optie **Toewijzingen** in de sectie **Beheren**.
4. Kies **Groep toevoegen** om de blade **Groep toevoegen** weer te geven die bij de app hoort.
5. Voor de specifieke app moet u een **toewijzingstype** selecteren. U hebt de volgende mogelijkheden:
    - **Beschikbaar voor ingeschreven apparaten**: gebruikers installeren de app vanuit de bedrijfsportal-app of vanaf de website.
    - **Beschikbaar met of zonder inschrijving**: deze app wordt toegewezen aan groepen met gebruikers van wie de apparaten niet zijn ingeschreven met Intune. Houd er rekening mee dat het app-type **Android for Work** geen ondersteuning biedt voor deze optie. 
    - **Vereist**: de app wordt geïnstalleerd op apparaten in de geselecteerde groepen.
    - **Verwijderen**: de app wordt verwijderd van apparaten in de geselecteerde groepen.

    > [!NOTE]
    > **Alleen voor iOS-apps**: als u een iOS VPN-profiel hebt gemaakt met VPN-instellingen per app, kunt u het selecteren onder **VPN**. Als de app wordt uitgevoerd, wordt de VPN-verbinding geopend. Zie [VPN=instellingen voor iOS-apparaten](vpn-settings-ios.md) voor meer informatie.

6. Selecteer **Opgenomen groepen** om de gebruikersgroepen te selecteren die worden beïnvloed door deze app-toewijzing.
7. Klik op **Selecteren** wanneer u één of meer groepen hebt geselecteerd om op te nemen.
8. Klik op **OK** op de blade **Toewijzen** om het selecteren van de op te nemen groepen te voltooien.
9. Klik op **Groepen uitsluiten** als u gebruikersgroepen wilt uitsluiten zodat ze niet worden beïnvloed door deze app-toewijzing.
10. Als u hebt besloten dat u groepen wilt uitsluiten, klikt u op **Selecteren** op de blade **Groepen selecteren**.
11. Klik op **OK** op de blade **Groep toevoegen**.
12. Klik op **Opslaan** op de blade **Toewijzingen** om uw toewijzingen op te slaan.

De app wordt nu toegewezen aan de groepen die u hebt geselecteerd. Zie [App-toewijzingen opnemen en uitsluiten](apps-inc-exl-assignments.md) voor meer informatie over het opnemen en uitsluiten van app-toewijzingen.

## <a name="how-conflicts-between-app-intents-are-resolved"></a>Hoe conflicten tussen app-intents worden opgelost

Soms wordt dezelfde app aan meerdere groepen toegewezen, maar met verschillende intents. In dergelijke gevallen raadpleegt u deze tabel om te begrijpen waarom de resulterende intent is gekozen.

||||
|-|-|-|
|Intent van groep 1|Intent van groep 2|Resulterende intent|
|Gebruiker vereist|Gebruiker beschikbaar|Vereist en beschikbaar|
|Gebruiker vereist|Gebruiker niet beschikbaar|Vereist|
|Gebruiker vereist|Gebruiker verwijderen|Vereist|
|Gebruiker beschikbaar|Gebruiker niet beschikbaar|Niet beschikbaar|
|Gebruiker beschikbaar|Gebruiker verwijderen|Verwijderen|
|Gebruiker niet beschikbaar|Gebruiker verwijderen|Verwijderen
|Gebruiker vereist|Apparaat vereist|Beide bestaan, gateway verwerkt vereist
|Gebruiker vereist|Apparaat verwijderen|Beide bestaan, gateway verwerkt vereist
|Gebruiker beschikbaar|Apparaat vereist|Beide bestaan, gateway zet vereist om (Vereist en Beschikbaar)
|Gebruiker beschikbaar|Apparaat verwijderen|Beide bestaan, gateway zet Beschikbaar om<br>App wordt weergegeven in bedrijfsportal.<br>Als de app al is geïnstalleerd (als een vereiste app met vorige intent),wordt de app verwijderd.<br>Maar als de gebruiker in de bedrijfsportal op Installeren klikt, wordt de app geïnstalleerd en wordt de intent om te verwijderen niet gehonoreerd.|
|Gebruiker niet beschikbaar|Apparaat vereist|Vereist|
|Gebruiker niet beschikbaar|Apparaat verwijderen|Verwijderen|
|Gebruiker verwijderen|Apparaat vereist|Beide bestaan, gateway zet Vereist om|
|Gebruiker verwijderen|Apparaat verwijderen|Beide bestaan, gateway zet Verwijderen om|
|Apparaat vereist|Apparaat verwijderen|Vereist|
|Gebruiker vereist en beschikbaar|Gebruiker beschikbaar|Vereist en beschikbaar|
|Gebruiker vereist en beschikbaar|Gebruiker verwijderen|Vereist en beschikbaar|
|Gebruiker vereist en beschikbaar|Gebruiker niet beschikbaar|Vereist en beschikbaar|
|Gebruiker vereist en beschikbaar|Apparaat vereist|Beide bestaan Vereist en Beschikbaar
|Gebruiker vereist en beschikbaar|Apparaat niet beschikbaar|Vereist en beschikbaar|
|Gebruiker vereist en beschikbaar|Apparaat verwijderen|Beide bestaan, gateway zet Vereist om Vereist en Beschikbaar
|Gebruiker niet beschikbaar|Apparaat niet beschikbaar|Niet beschikbaar|
|Gebruiker beschikbaar|Apparaat niet beschikbaar|Beschikbaar|
|Gebruiker vereist|Apparaat niet beschikbaar|Vereist|
|Gebruiker beschikbaar zonder registratie|Gebruiker vereist en beschikbaar|Vereist en beschikbaar
|Gebruiker beschikbaar zonder registratie|Gebruiker vereist|Vereist
|Gebruiker beschikbaar zonder registratie|Gebruiker niet beschikbaar|Niet beschikbaar
|Gebruiker beschikbaar zonder registratie|Gebruiker beschikbaar|Beschikbaar|
|Gebruiker beschikbaar zonder registratie|Apparaat vereist|Vereist en beschikbaar zonder registratie|
|Gebruiker beschikbaar zonder registratie|Apparaat niet beschikbaar|Beschikbaar zonder registratie|
|Gebruiker beschikbaar zonder registratie|Apparaat verwijderen|Verwijderen en beschikbaar zonder registratie<br>Als de gebruiker de app niet heeft geïnstalleerd vanuit de bedrijfsportal, wordt het verzoek om verwijdering gehonoreerd.<br>Als de gebruiker de app vanuit de bedrijfsportal installeert, krijgt de installatie prioriteit boven het verwijderen van de app.|

>[!NOTE]
>Alleen voor beheerde iOS Store-apps: wanneer u deze apps toevoegt aan Microsoft Intune en toewijst als **Vereist**, worden ze automatisch gemaakt met zowel de intentie **Vereist** als **Beschikbaar**.

## <a name="next-steps"></a>Volgende stappen

Zie [How to monitor apps](apps-monitor.md) (Apps controleren) voor meer informatie over het controleren van app-toewijzingen.
