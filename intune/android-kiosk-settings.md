---
title: Kioskinstellingen voor Android in Microsoft Intune - Azure | Microsoft Docs
description: Configureer uw Android-kioskapparaten als kiosk voor één of meerdere apps.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cef98527ee2c281547f8046f3c6f08275d8f0807
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/31/2018
ms.locfileid: "43329380"
---
# <a name="kiosk-settings-for-android-devices-in-intune"></a>Kioskinstellingen voor Android-apparaten in Intune

U kunt een apparaat configureren in de kioskmodus voor één of meerdere apps met behulp van configuratie-instellingen voor apparaten. Wanneer een apparaat in de kioskmodus is, is het gebruik van het apparaat beperkt tot de app(s) of webkoppelingen die zijn gedefinieerd door het beperkingsprofiel. 

## <a name="restrict-an-android-kiosk-device-to-a-single-app"></a>Een Android-kioskapparaat beperken tot één app

Als het beperkingsprofiel van een kioskapparaat is ingesteld op **Kioskmodus** = **kiosk voor één app**, hebben gebruikers slechts toegang tot één app. Wanneer een apparaat in deze modus wordt gestart, wordt de specifieke app gestart. Gebruikers kunnen geen nieuwe apps openen of de actieve app wijzigen.

1. Zorg ervoor dat de app die moet worden gebruikt op het kioskapparaat is [geïmplementeerd op het apparaat](apps-deploy.md) en dat u de app hebt toegewezen aan de groep met apparaten die u voor uw kioskapparaten hebt gemaakt.
2. Ga naar de [Intune-portal](https://portal.azure.com) en kies **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Stel de volgende velden op de blade **Profiel maken** in:
     - **Naam**
     - **Platform**: Android Enterprise
     - **Profieltype**: Alleen eigenaar van apparaat > Apparaatbeperkingen
4. Kies **Instellingen** > **Kiosk**.
5. Kies voor **Kioskmodus** de optie **Kiosk voor één app**.
6. Kies **Een beheerde app selecteren** en selecteer vervolgens de beheerde Google Play-app die u wilt instellen als de enige app die beschikbaar is voor apparaten die gebruikmaken van dit profiel.
7. Kies **OK** > **OK** > **OK** > **Maken**.
8. Kies het profiel dat u zojuist hebt gemaakt > **Toewijzingen**.
9. Kies onder **Toewijzen aan** de optie **Geselecteerde groepen**.
10. Kies **Groepen selecteren om op te nemen** > kies de apparaatgroep die u hebt gemaakt voor uw kioskapparaten > **Selecteren**.

## <a name="restrict-a-kiosk-device-to-a-set-of-apps-or-web-links"></a>Een kioskapparaat beperken tot een aantal apps of webkoppelingen

Als het beperkingsprofiel van een kioskapparaat is ingesteld op **Kioskmodus** = **kiosk voor meerdere apps**, hebben gebruikers alleen toegang tot het aantal apps dat u configureert. U kunt ook een aantal webkoppelingen definiëren die gebruikers mogen bezoeken. Wanneer het beleid wordt toegepast, zien gebruikers pictogrammen voor de toegestane apps op het startscherm.

Als u een Android-kioskapparaat wilt instellen voor meerdere apps, volgt u deze stappen:

1. [De app voor het beheerde startscherm vanuit het beheerde Google Play importeren en implementeren](#import-and -deploy-the-managed-home-screen-app)
2. [Apps toevoegen en toewijzen die kunnen worden gebruikt in de kioskmodus](#add-and-assign-apps-that-can-be-used-in-kiosk-mode)
3. (Optioneel) [Webkoppelingen toevoegen die kunnen worden gebruikt in de kioskmodus](#add-web-links-that-can-be-used-in-kiosk-mode)

### <a name="import-and-deply-the-managed-home-screen-app"></a>De app voor het beheerde startscherm importeren en implementeren

1. Blader naar de [pagina van het beheerde startscherm op Google Play](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) en meld u aan met hetzelfde account dat u voor andere beheerde apps van Google Play gebruikt.
2. Kies **Goedkeuren**.
3. Ga naar de [Intune-portal](https://portal.azure.com) en kies **Client-apps** > **Beheerde Google Play** > **Synchroniseren**.
4. Kies **Apps** > **Beheerd startscherm** > **Toewijzingen** > **Groep toevoegen**.
5. Kies **Vereist** onder **Toewijzingstype**.
6. Kies **Opgenomen groepen** > **Groepen selecteren om op te nemen** > kies de apparaatgroep die u hebt gemaakt voor uw kioskapparaten > **Selecteren** > **OK** > **OK** > **Opslaan**.

### <a name="add-and-assign-apps-that-can-be-used-in-kiosk-mode"></a>Apps toevoegen en toewijzen die kunnen worden gebruikt in de kioskmodus

Voor elke app die u beschikbaar wilt stellen voor de kioskapparaten, voert u de volgende stappen uit:

1. [Voeg de app toe aan Intune](store-apps-android.md).
2. Kies **Client-apps** > **Apps** > kies de app > **Toewijzingen** > **Groep toevoegen**.
3. Kies **Vereist** onder **Toewijzingstype**.
4. Kies **Opgenomen groepen** > **Groepen selecteren om op te nemen** > kies de apparaatgroep die u hebt gemaakt voor uw kioskapparaten > **Selecteren** > **OK** > **OK** > **Opslaan**.

### <a name="add-web-links-that-can-be-used-in-kiosk-mode"></a>Webkoppelingen toevoegen die kunnen worden gebruikt in de kioskmodus

1. Ga naar de [Intune-portal](https://portal.azure.com) en kies **Client-apps** > **Apps** > **Toevoegen**.
2. Kies **Webkoppeling** onder **App-type**.
3. Kies **Configureren** en geef de vereiste informatie op. U hoeft geen logoafbeelding toe te voegen, omdat deze automatisch wordt opgehaald van de website favicon.ico.
4. Kies **OK** > **Toevoegen**.

Implementeer met [Mobile Apps](apps-add.md) een webbrowser-app op de kioskapparaten.

### <a name="create-a-multi-app-kiosk-profile"></a>Een kioskprofiel voor meerdere apps maken

1. Ga naar de [Intune-portal](https://portal.azure.com) en kies **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Stel de volgende velden op de blade **Profiel maken** in:
     - **Naam**: typ een intuïtieve naam
     - **Platform**: Android Enterprise
     - **Profieltype**: Alleen eigenaar van apparaat > Apparaatbeperkingen
4. Kies **Instellingen** > **Kiosk**.
5. Kies voor **Kioskmodus** de optie **Kiosk voor meerdere apps**.
6. Kies **Toevoegen** en selecteer de apps of webkoppelingen die u beschikbaar wilt stellen voor apparaten die dit profiel gebruiken.
7. Kies **OK** > **OK** > **OK** > **Maken**.
8. Kies het profiel dat u zojuist hebt gemaakt > **Toewijzingen**.
9. Kies onder **Toewijzen aan** de optie **Geselecteerde groepen**.
10. Kies **Groepen selecteren om op te nemen** > kies de apparaatgroep die u hebt gemaakt voor uw kioskapparaten > **Selecteren** > **Opslaan**.

## <a name="next-steps"></a>Volgende stappen
[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
