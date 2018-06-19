---
title: Uw Windows-apparaat handmatig synchroniseren | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: aa556b2939986759aa92e63750fd161c05afbc38
ms.sourcegitcommit: 6a9830de768dd97a0e95b366fd5d2f93980cee05
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2018
ms.locfileid: "34048016"
---
# <a name="sync-your-windows-device-manually"></a>Uw Windows-apparaat handmatig synchroniseren

Voer een handmatige synchronisatie van uw apparaat uit als een app erg langzaam wordt geïnstalleerd. Bij een handmatige synchronisatie maakt uw apparaat verbinding met Intune en worden de nieuwste updates en communicatie opgehaald. De installatiesnelheid kan verbeteren nadat de apparaatsynchronisatie is voltooid.

Intune ondersteunt handmatige synchronisatie vanuit de bedrijfsportal-app en vanuit de app Instellingen van het apparaat. 

De functionaliteit van de bedrijfsportal-app wordt ondersteund op Windows 10-apparaten waarop de makersupdate (1703) of hoger wordt uitgevoerd. 
* [Synchroniseren vanuit de bedrijfsportal-app](#Sync-from-Company-Portal-app-for-Windows)  

Alle Windows-apparaten kunnen worden gesynchroniseerd vanuit de app Instellingen van het apparaat, met inbegrip van:

* [Windows 10 Desktop](#windows-10-desktop)  
* [Microsoft HoloLens](#microsoft-hololens)   
* [Windows 10 Mobile](#windows-10-mobile)  
* [Windows Phone 8.1](#windows-phone-81)    

## <a name="sync-from-company-portal-app-for-windows"></a>Synchroniseren vanuit de bedrijfsportal-app voor Windows
Voer deze stappen uit als u een Windows 10-apparaat wilt synchroniseren waarop makersupdate (versie 1703) of hoger wordt uitgevoerd.

1.  Open de bedrijfsportal-app op uw apparaat.

2.  Selecteer **Instellingen** > **Synchroniseren**.

    ![Schermafbeelding van de startpagina van de bedrijfsportal-app waarin Instellingen is gemarkeerd](./media/RS1_homePage_settings_04.png)  
    
    ![Schermafbeelding van de instellingenpagina van de bedrijfsportal-app waarin de knop Synchroniseren is gemarkeerd](./media/RS1_settingspage_sync05.png)    

## <a name="sync-from-settings-app"></a>Synchroniseren vanuit de app Instellingen 
Voltooi deze stappen als u uw Microsoft HoloLens-, Windows 10 desktop-, Windows 10 Mobile- of Windows Phone 8.1-apparaat handmatig wilt synchroniseren vanuit de app Instellingen.

### <a name="windows-10-desktop"></a>Windows 10 Desktop
1. Selecteer op het apparaat **Start** > **Instellingen**.

2. Selecteer **Accounts**.

    ![Accounts kiezen op de pagina Instellingen](./media/win10pc-sync-2-settings-accounts.png)  

3. Er bestaan meerdere versies van Windows 10 voor pc's. Vergelijk uw scherm met onderstaande schermafbeeldingen om te bepalen welke reeks stappen u moet volgen. 

    * Als in het scherm **Toegang tot werk of school** wordt weergegeven, gaat u verder met de stappen in [Toegang tot werk of school](#access-work-or-school).

    ![Optie Toegang tot werk of school in app Instellingen](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

    * Als in het scherm **Toegang via het werknetwerk** wordt weergegeven, gaat u verder met de stappen onder [Toegang via het werknetwerk](#work-access).  

    ![Toegang via het werknetwerk kiezen als het accounttype](./media/win10pc-sync-3-work-access.png)

#### <a name="access-work-or-school-steps"></a>Stappen voor toegang tot werk of school

1. Klik op **Toegang tot werk of school**.

    ![Schermafbeelding van de optie Toegang tot werk of school](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

2. Selecteer het account waarnaast het pictogram van een werkmap wordt weergegeven. Als u dit account helemaal niet ziet, heeft uw bedrijf uw instellingen mogelijk op een andere manier geconfigureerd. Klik in dat geval op het account waarnaast een Microsoft-logo wordt weergegeven.

     ![Kies de naam van het account naast de aktetas of het Microsoft-logo](./media/win10pc-rs1-sync-info-button.png)

3. Klik op **Info**. 

4. Klik op **Synchroniseren**. 

#### <a name="work-access-steps"></a>Stappen voor toegang via het werknetwerk

1.  Klik op **Toegang via het werknetwerk**.

    ![Toegang via het werknetwerk kiezen als het accounttype](./media/win10pc-sync-3-work-access.png)

2. Selecteer onder **Registreren voor apparaatbeheer** de naam van uw bedrijf.

    ![De naam van het bedrijf kiezen voor apparaatbeheer](./media/win10pc-sync-4-tap-com-name.png)

3. Klik op **Synchroniseren**. De knop blijft uitgeschakeld totdat de synchronisatie is voltooid.

    ![De knop Synchroniseren kiezen](./media/win10pc-sync-5-tap-sync.png)  


### <a name="windows-10-mobile"></a>Windows 10 Mobile

   1. Ga op uw apparaat naar **Alle apps** > **Instellingen** > **Accounts**.

       ![Accounts kiezen op het scherm Instellingen](./media/win10m-sync-1-settings-accounts.png)

   2. Selecteer **Toegang via werknetwerk**.

       ![Toegang via het werknetwerk kiezen als het accounttype](./media/win10m-sync-2-work-access.png)

   3. Selecteer onder **Registreren voor apparaatbeheer** de naam van uw bedrijf.

       ![De naam van het bedrijf kiezen voor apparaatbeheer](./media/win10m-sync-3-tap-comp-name.png)

   4. Selecteer het pictogram **Synchroniseren**. De knop blijft uitgeschakeld totdat de synchronisatie is voltooid.

       ![Het pictogram Synchroniseren kiezen](./media/win10m-sync-4-tap-sync.png)  
### <a name="microsoft-hololens"></a>Microsoft HoloLens  
Deze instructies zijn van toepassing op HoloLens-apparaten waarop de Windows 10 Jubileumupdate (ook wel RS1 genoemd) wordt uitgevoerd. 
1.  Open de app Instellingen op uw apparaat.  

2.  Selecteer **Accounts** > **Toegang via werknetwerk**.  
    ![Schermafbeelding van de app Instellingen in HoloLens waarin de koppeling Accounts is gemarkeerd](./media/RS1_holoLens_SettingsRS1_Accounts_06.png)  

3.  Selecteer uw verbonden account > **Synchroniseren**. ![Schermafbeelding van de app Instellingen in HoloLens waarin de knop Synchroniseren is gemarkeerd](./media/RS1_holoLens_SyncRS1_Sync_08.png)  

### <a name="windows-phone-81"></a>Windows Phone 8.1

1. Ga naar **Alle apps** > **Instellingen** > **Werkplek**.

    ![Lijst met instellingen](./media/wp81-1-sync-settings-workplace.png)

2. Selecteer de naam van uw bedrijf.

    ![De naam van het bedrijf kiezen voor het werkplekaccount](./media/wp81-2-sync-tap-compname.png)

3. Selecteer het pictogram **Synchroniseren**.

    ![Het pictogram Synchroniseren kiezen](./media/wp81-3-sync-tap-sync-button.png)

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Controleer of de contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](https://portal.manage.microsoft.com#HelpDeskDialog).
