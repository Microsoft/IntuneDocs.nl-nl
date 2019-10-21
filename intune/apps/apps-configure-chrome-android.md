---
title: Google Chrome configureren voor Android-apparaten met behulp van Intune
titleSuffix: Microsoft Intune
description: Gebruik Intune-configuratiebeleid met Google Chrome voor Android-apparaten.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 35f52e80f83426c076ac7925d308daacf4595f88
ms.sourcegitcommit: b1e97211db7cb949eb39be6776b3a11d434fdab0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2019
ms.locfileid: "72251498"
---
# <a name="configure-google-chrome-for-android-devices-using-intune"></a>Google Chrome configureren voor Android-apparaten met behulp van Intune 

U kunt Intune-configuratiebeleid voor apps gebruiken om Google Chrome te configureren voor Android-apparaten. De instellingen voor de app kunnen automatisch worden toegepast. U kunt bijvoorbeeld specifieke bladwijzers en URL's instellen die u wilt blokkeren of toestaan.

## <a name="prerequisites"></a>Vereisten

- Het Android Enterprise-apparaat van de gebruiker moet zijn ingeschreven bij Intune. Zie [Inschrijving van Android Enterprise-apparaten met een werkprofiel instellen](~/enrollment/android-work-profile-enroll.md) voor meer informatie.
- Google Chrome moet zijn toegevoegd als een beheerde Google Play-app. Zie [Uw Intune-account verbinden met uw beheerde Google Play-account](~/enrollment/connect-intune-android-enterprise.md) voor meer informatie over beheerde Google Play.

## <a name="add-the-google-chrome-app-to-intune"></a>De Google Chrome-app toevoegen aan Intune

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer in het deelvenster **Intune** achtereenvolgens **Client-apps** > **Apps** > **Toevoegen**, en voeg vervolgens de **Beheerde Google Play**-app toe.
3. Ga naar beheerde Google Play, zoek met **Google Chrome** en keur goed.

    ![Google Chrome zoeken en goedkeuren](~/apps/media/apps-configure-chrome-android/search.png)

4. Wijs Google Chrome als vereist app-type toe aan een gebruikersgroep. Google Chrome wordt automatisch geïmplementeerd wanneer het apparaat is ingeschreven bij Intune.

Zie [Beheerde Google Play Store-apps](~/apps/apps-add-android-for-work.md#managed-google-play-store-apps) voor aanvullende details over het toevoegen van een beheerde Google Play-app in Intune.

## <a name="add-an-app-configuration-policy-for-managed-android-enterprise-devices"></a>App-configuratiebeleid toevoegen voor beheerde Android Enterprise-apparaten

1. Selecteer in het deelvenster [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) de opties **App-configuratiebeleid** > **Toevoegen**.
2. Voeg uw beleidsnaam toe, kies onder Type apparaatinschrijving de optie **Beheerde apparaten**, en kies onder Platform de optie **Android**.

    ![Google Chrome-configuratiebeleid toevoegen](~/apps/media/apps-configure-chrome-android/add-policy.png)

3. Klik op **Gekoppelde app** en selecteer **Google Chrome**.

    ![Selecteer onder Gekoppelde app de optie Google Chrome](~/apps/media/apps-configure-chrome-android/associated-app.png)

4. Klik op **Configuratie-instellingen**, selecteer **Configuration Designer gebruiken**, en klik vervolgens op **Toevoegen** om de configuratiesleutels te selecteren.

    ![Configuration Designer gebruiken toevoegen](~/apps/media/apps-configure-chrome-android/configuration.png)

    Hieronder ziet u het voorbeeld van de algemene instellingen:
    - **Toegang tot een lijst met URL's blokkeren**: `["*"]`
    - **Toegang tot een lijst met URL's toestaan**: `["baidu.com", "yahoo.com", "chrome://*"]`
    - **Beheerde bladwijzers**: `[{"toplevel_name": "My managed bookmarks folder"  },  {"url": "baidu.com",   "name": "Baidu"},  {"url": "youtube.com", "name": "Youtube"},  {"name": "Chrome links",  "children": [{"url": "chromium.org", "name": "Chromium"},    {"url": "dev.chromium.org", "name": "Chromium Developers"}]}]`
    - **Beschikbaarheid van Incognito-modus**: `Incognito mode disabled`

    Zodra de configuratie-instellingen zijn toegevoegd met behulp van Configuration Designer, worden ze weergegeven in een tabel. 

    ![Algemene instellingen](~/apps/media/apps-configure-chrome-android/common-settings.png)

    Met de bovenstaande instellingen maakt u bladwijzers en kunt u toegang tot alle websites toestaan, behalve `baidu.com`, `yahoo.com` en `chrome://`.

5. Klik op **OK** en **Toevoegen** om uw configuratiebeleid toe te voegen aan Intune.
6. Wijs dit configuratiebeleid toe aan een gebruikersgroep. Zie [Apps aan groepen toewijzen met Microsoft Intune](~/apps/apps-deploy.md) voor meer informatie. 

## <a name="verify-the-device-settings"></a>De apparaatinstellingen controleren

Zodra het Android-apparaat is ingeschreven bij Android Enterprise, wordt de beheerde Google Chrome-app met het portfoliopictogram automatisch geïmplementeerd.
 
   <img alt="Managed Google Chrome with the portfolio icon" src="~/apps/media/apps-configure-chrome-android/chrome-icon.png" width="350">

Als u Google Chrome start, ziet u dat de instellingen zijn toegepast.

   Bladwijzers:<br>
   <img alt="Bookmarks" src="~/apps/media/apps-configure-chrome-android/bookmarks.png" width="350">

   Geblokkeerde URL:<br>
   <img alt="Blocked URL" src="~/apps/media/apps-configure-chrome-android/blocked-url.png" width="350">

   Toegestane URL:<br>
   <img alt="Allow URL" src="~/apps/media/apps-configure-chrome-android/allowed-url.png" width="350">

   Incognito-tabblad:<br>
   <img alt="Incognito tab" src="~/apps/media/apps-configure-chrome-android/incognito-tab.png" width="350">

## <a name="troubleshooting"></a>Probleemoplossing

1. Ga naar de Intune-portal om de implementatiestatus van het beleid te controleren.

    ![De implementatiestatus van het beleid controleren](~/apps/media/apps-configure-chrome-android/monitor-status.png)

2. Start Google Chrome en ga naar **chrome://policy** . We kunnen bevestigen dat de instellingen juist zijn toegepast.

    ![Bevestigen dat de instellingen juist zijn toegepast](~/apps/media/apps-configure-chrome-android/confirm.png)

## <a name="additional-information"></a>Aanvullende informatie

- [App-configuratiebeleid toevoegen voor beheerde Android Enterprise-apparaten](~/app-configuration-policies-use-android.md)
- [Lijst met Chrome Enterprise-beleid](https://cloud.google.com/docs/chrome-enterprise/policies/)

## <a name="next-steps"></a>Volgende stappen

- Zie [Intune-inschrijving van volledig beheerde Android Enterprise-apparaten instellen](~/enrollment/android-fully-managed-enroll.md) voor meer informatie over volledig beheerde Android Enterprise-apparaten.
