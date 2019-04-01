---
title: In ontwikkeling - Microsoft Intune
titlesuffix: ''
description: Microsoft Intune-functies in ontwikkeling
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/04/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9c377a8558b1f318b4ddad735b6368a291e34516
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57756816"
---
# <a name="in-development-for-microsoft-intune---march-2019"></a>In de ontwikkeling voor Microsoft Intune - maart 2019

Om te helpen bij uw gereedheid en planning, deze pagina is een lijst met Intune UI-updates en functies die zijn in ontwikkeling, maar nog niet is vrijgegeven. Daarnaast:

- Als we verwachten, moet u maatregelen nemen voordat u een wijziging, publiceren we een gratis Office Message Center-bericht.
- Als een functie als een Preview-versie in productie, wordt gestart of algemeen beschikbaar is, de beschrijving van de functie worden verplaatst uit deze pagina en naar de [wat is er nieuw-pagina](whats-new.md).
- Deze pagina en de [wat is er nieuw-pagina](whats-new.md) worden regelmatig bijgewerkt. Controleer op andere updates.
- Raadpleeg de [M365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) voor strategische producten en tijdlijnen.

> [!Note]
> Deze items zijn de huidige verwachtingen van Microsoft over de mogelijkheden van Intune die afkomstig zijn in een toekomstige release. Datums en functies afzonderlijk kunnen worden gewijzigd. Niet alle items in de ontwikkeling hebben een omschrijving op deze pagina.

**RSS feed**: ontvang een melding wanneer deze pagina wordt bijgewerkt door de volgende URL in uw feedlezer te kopiëren en plakken: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`


<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune in Azure Portal


<!-- 1903 start-->

### <a name="encryption-report-----2351538---"></a>Rapport van versleuteling  <!-- 2351538 -->
U zult kunnen een nieuw rapport voor de versleuteling gebruiken om meer informatie over de versleutelingsstatus van uw apparaten weer te geven. Beschikbare details bevat een TPM-versie van apparaten, de gereedheid van de versleuteling en status, foutrapportage, en meer.  

### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-----2351547----"></a>Toegangssleutels BitLocker-herstel van de Intune-portal  <!-- 2351547  -->
We voegen een nieuw toegangspunt toe op apparaten, waar u de details van Azure Active Directory (AAD) over BitLocker-sleutel-ID en de BitLocker-sleutels voor herstel kunt bekijken.

### <a name="scope-tags-for-app-configuration-policies---2371891---"></a>Bereiktags voor app-configuratiebeleid <!--2371891 -->
U moet mogelijk een bereiktag toevoegen aan een configuratiebeleid voor apps, zodat alleen de personen met de rol is ook toegewezen die de bereiktag toegang tot de app-configuratiebeleid hebben. Het configuratiebeleid voor apps kan alleen worden gericht op of die zijn gekoppeld aan hetzelfde bereik label toegewezen apps.

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522---"></a>Autopilot-profielen toewijzen aan de virtuele groep Alle apparaten <!--2715522 -->
U kunt Autopilot-profielen toewijzen aan de virtuele groep Alle apparaten. Kies hiervoor **Inschrijving apparaat** > **Inschrijving Windows** > **Implementatieprofielen** > kies een profiel >  **Toewijzingen** > onder  **Toewijzen aan** kies **Alle apparaten**. Zie [Windows-apparaten inschrijven met Windows AutoPilot](enrollment-autopilot.md) voor meer informatie over Autopilot-profielen.

### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment----2751523----"></a>Beschikbare apps met behulp van de bedrijfsportal-app nadat de bulkinschrijving van Windows installeren <!-- 2751523  -->
Windows-apparaten die geregistreerd bij Intune via [bulkinschrijving voor Windows](windows-bulk-enroll.md) (inrichtingspakketten) is mogelijk de bedrijfsportal-app gebruiken voor het installeren van beschikbare apps. Zie voor meer informatie over de bedrijfsportal-app, [handmatig toevoegen van de Windows 10-bedrijfsportal](store-apps-company-portal-app.md) en [de Microsoft Intune-bedrijfsportal-app configureren](company-portal-app.md).

### <a name="scope-tags-for-ios-app-provisioning-profiles---2934430---"></a>Bereiktags voor profielen voor het inrichten van iOS-app <!--2934430 -->
U moet mogelijk een bereiktag toevoegen aan een inrichtingsprofiel voor iOS-app, zodat alleen de personen met de rol is ook toegewezen die de bereiktag hebben toegang tot de iOS-app het inrichtingsprofiel. 

### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment----3192477----"></a>Office Deployment Tool (ODT) XML voor de implementatie van Office ProPlus <!-- 3192477  -->
U zult kunnen Office Deployment Tool (ODT) XML bieden bij het maken van een exemplaar van Office Professional Plus in de Intune-beheerconsole. Hierdoor kunnen meer aanpassingsmogelijkheden als de bestaande Intune UI-opties niet voldoen aan uw behoeften. 

###  <a name="block-users-from-scanning-for-windows-updates-------3316758------"></a>Blokkeren dat gebruikers kunnen het zoeken naar updates voor Windows    <!-- 3316758    -->
We voegen een nieuwe Windows update-ring instellen die u kunt gebruiken die wordt blokkeren dat gebruikers kunnen scannen op Windows-updates toe. Deze instelling niet beschikbaar zijn vanuit de portal, maar kan worden geconfigureerd met behulp van de Intune Graph API.

### <a name="windows-update-notifications-----3316782---"></a>Windows Update-meldingen  <!-- 3316782 -->
We er ondersteuning toegevoegd voor de Windows Update-ring-configuraties, zodat u kunt het configureren van de Windows Update-meldingen die uw gebruikers te zien. Deze instelling niet beschikbaar zijn vanuit de portal, maar kan worden geconfigureerd met behulp van de Intune Graph API.

### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Wijzigingen in de bedrijfsportal-App-registratie voor gebruikers van iOS-12-apparaten <!--3448635 -->  
Bedrijfsportal-App voor iOS wordt een update van de app inschrijving schermen en stappen voor het uitlijnen met de MDM-inschrijving wijzigingen die zijn uitgebracht in Apple iOS 12.2. De bijgewerkte werkstroom wordt nu gevraagd voor gebruikers:

- Safari op de website bedrijfsportal (via Safari) openen en downloaden van het beheerprofiel voordat u terugkeert naar de bedrijfsportal-app toestaan. 
- Open de app instellingen voor het installeren van het beheerprofiel op hun apparaat.
- Ga terug naar de bedrijfsportal-app-registratie moet voltooien.  

Zie voor meer informatie over hoe u deze wijzigingen kunt voorbereiden, de [Microsoft Tech-Community post](https://techcommunity.microsoft.com/). In de tussentijd ter ondersteuning van nieuwe iOS-inschrijvingen in bedrijfsportal-App, hebben we de stappen in bijgewerkt [iOS-apparaat inschrijven bij Intune](https://docs.microsoft.com/en-us/intune/ios-enroll). Deze wijzigingen docs worden live nadat Apple iOS-versie 12.2 worden vrijgegeven. 

### <a name="support-for-additional-connectors-on-the-tenant-status-page----3617202-------"></a>Ondersteuning voor extra connectors op de pagina Status van de Tenant <!-- 3617202     -->
De Status van de Tenant-pagina statusinformatie voor aanvullende connectors, zoals wordt weergegeven *Windows Defender Advanced Threat Protection* (ATP) en andere Mobile Threat Defense-connectors.

### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles----3637917---"></a>Verlenen van Intune alleen-lezentoegang tot sommige Azure Active Directory-rollen <!-- 3637917 -->
We wordt verleend op basis van dat intune alleen-lezentoegang tot de volgende Azure AD-rollen. Machtigingen met Azure AD-rollen hebben voorrang boven machtigingen verleend via de Intune-rollen gebaseerd toegangsbeheer (RBAC).

Alleen toegang tot de Intune-controlegegevens lezen:

- Beheerder voor naleving
- Beheerder voor naleving-gegevens

Alleen-lezentoegang tot alle gegevens van Intune:

- Beveiligingsbeheer
- Beveiliging-Operator
- Beveiligingslezer
- Globale lezer

### <a name="easier-access-to-diagnostic-settings------3804627-----"></a>Eenvoudiger toegang tot diagnostische instellingen   <!-- 3804627   -->
We bij het toevoegen van een nieuwe optie om de **auditlogboeken** -blade in elke in elke werkbelasting auditlogboek in de Intune-console die u kunt rechtstreeks openen de *diagnostische instellingen* pagina.

### <a name="create-and-use-device-configuration-profiles-on-android-zebra-devices-in-intune----3895244----"></a>Maken en gebruiken van apparaat-configuratieprofielen van Android Zebra.bmp-apparaten in Intune <!-- 3895244  -->
Intune biedt ondersteuning voor Android Zebra.bmp configureren van apparaten. Specifiek, zult u kunnen: 

- Een apparaatconfiguratieprofiel maken en instellingen van toepassing op Android Zebra.bmp apparaten met behulp van de Mobility-extensies (MX) profielen die worden gegenereerd door StageNow (**apparaatconfiguratie** > **profielen**  >  **-Profiel maken** > **Android** voor platform).

Van toepassing op:  
- Android

<!-- 1901 start -->

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Implementatie van online gelicentieerde Microsoft Store voor Bedrijven-apps <!-- 1672660  -->
U kunt vereiste online gelicentieerde Microsoft Store voor Bedrijven-apps in de apparaatcontext toewijzen. Wanneer u op deze manier een Microsoft Store voor bedrijven-app implementeert, kan de app worden geïnstalleerd voor alle gebruikers op het apparaat. Dit is alleen van toepassing op Windows 10 RS4+ Desktop-apparaten. De optie om de app in de apparaatcontext te installeren, is beschikbaar op de toewijzingspagina voor client-apps voor gelicentieerde MSFB Online-apps.

## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.
