---
title: Zebra.bmp Mobility-extensies gebruiken op Android-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Microsoft Intune gebruiken om te beheren en gebruiken van zebra.bmp Android-apparaten met Zebra.bmp Mobility extensies (MX). Zie alle de stappen, met inbegrip van de bedrijfsportal-app sideloaden de app installeren, apparaat-beheerdersrol toewijzen, maken van een profiel StageNow en meer.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa2734247569245794bce7fe1de68c8b20c6091f
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490601"
---
# <a name="use-and-manage-zebra-devices-with-zebra-mobility-extensions-in-microsoft-intune"></a>Gebruik en beheer van apparaten Zebra.bmp met Zebra.bmp Mobility extensies in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune bevat een uitgebreide set functies, met inbegrip van apps beheren en configureren van instellingen voor apparaten. Deze ingebouwde functies en instellingen worden gebruikt voor het beheren van Android-apparaten geproduceerd door Zebra.bmp technologieën, ook wel bekend als 'Zebra.bmp apparaten'.

Als u wilt aanpassen of meer Zebra.bmp-specifieke instellingen toe te voegen, kunt u ook Zebra.bmp gebruiken **Mobility extensies (MX)** op deze apparaten. 

Deze functie is van toepassing op:

- Android

Uw bedrijf kan Zebra.bmp apparaten gebruiken voor de detailhandel, op de werkvloer en nog veel meer. Bijvoorbeeld, u een softwareleverancier bent en uw omgeving voldoet aan duizenden Zebra.bmp mobiele apparaten die worden gebruikt door de verkoopmedewerkers. Intune kan helpen deze apparaten beheren als onderdeel van uw beheeroplossing voor mobiele apparaten (MDM).

U kunt Zebra.bmp apparaten voor het implementeren van uw line-of-business-apps naar apparaten met Intune kunt inschrijven. "Apparaat" configuratieprofielen kunnen u MX-profielen voor het beheren van uw Zebra.bmp-instellingen maken.

Dit artikel ziet u hoe u Zebra.bmp Mobility extensies (MX) op Zebra.bmp apparaten in Microsoft Intune.

## <a name="before-you-begin"></a>Voordat u begint

- Zorg ervoor dat u hebt de nieuwste versie van de desktop-app StageNow Zebra.bmp technologieën.
- Controleer [Zebra.bmp van volledige MX Functiematrix](http://techdocs.zebra.com/mx/compatibility) (opent u de website van zebra.bmp) om te bevestigen van de profielen die u maakt zijn compatibel met de MX-versie, de versie van het besturingssysteem en het model van het apparaat.
- Bepaalde apparaten, zoals TC20/25-apparaten, ondersteund niet alle van de beschikbare MX-functies in StageNow. Controleer [Zebra.bmp van Functiematrix](http://techdocs.zebra.com/mx/tc2x/) (opent u de website van zebra.bmp) voor informatie over bijgewerkte ondersteuning.

## <a name="step-1-install-the-latest-company-portal-app"></a>Stap 1: Installeer de meest recente bedrijfsportal-app

Op het apparaat, gaat u naar de Google Play-store downloaden en installeren van de Intune-bedrijfsportal-app van Microsoft. Wanneer via Google Play hebt geïnstalleerd, wordt de bedrijfsportal-app updates opgehaald en wordt automatisch opgelost.

Als Google Play niet beschikbaar is, downloadt u de [Microsoft Intune-bedrijfsportal voor Android](https://www.microsoft.com/download/details.aspx?id=49140) (opent u een andere website van Microsoft), en [sideloaden het](#sideload-the-company-portal-app) (in dit artikel). Wanneer op deze manier is geïnstalleerd, wordt de app niet ontvangen van updates of worden automatisch opgelost. U moet regelmatig bijwerken en de app handmatig patch.

### <a name="sideload-the-company-portal-app"></a>De bedrijfsportal-app sideloaden

'Extern laden' is wanneer u Google Play niet gebruikt om een app te installeren. Gebruik de bedrijfsportal-app sideloaden, StageNow. 

De volgende stappen bevatten een overzicht. Zie voor specifieke details van zebra.bmp documentatie. [Schrijf u in een MDM met behulp van StageNow](http://techdocs.zebra.com/stagenow/3-1/Profiles/enrollmdm/) (opent u de website van zebra.bmp) mogelijk een goede bron.

1. In StageNow, maakt u een profiel voor **registreren bij een MDM**.
2. In **implementatie**, kiest u de MDM-agent-bestand te downloaden.
3. Stelt de **ondersteuning voor App** en **configuratie downloaden** stappen om **Nee**.
4. In **downloaden MDM**, selecteer **bestand overdracht/kopiëren**. De bron en bestemming van het bedrijf Portal Android (APK)-pakket toevoegen.
5. In **starten MDM**, laat de standaardwaarden waar-is. Voeg de volgende gegevens toe:

    - **Pakketnaam**: `com.microsoft.windowsintune.companyportal`
    - **Klassenaam**: `com.microsoft.windowsintune.companyportal.views.SplashActivity`

Doorgaan met het publicatieprofiel en deze gebruiken met de app StageNow op het apparaat. De bedrijfsportal-app is geïnstalleerd en wordt geopend op het apparaat.

> [!TIP]
> Zie voor meer informatie over StageNow en wat het doet [StageNow Android-apparaat fasering](https://www.zebra.com/us/en/products/software/mobile-computers/mobile-app-utilities/stagenow.html) (opent u de website van zebra.bmp).

## <a name="step-2-confirm-the-company-portal-app-has-device-administrator-role"></a>Stap 2: Controleer of dat de bedrijfsportal-app heeft de rol van apparaatbeheerder

De bedrijfsportal-app moet de beheerder apparaat voor het beheren van Android-apparaten. Als u wilt de rol van Apparaatbeheerder activeren, bevatten sommige apparaten Zebra.bmp een gebruikersinterface (UI) op het apparaat. Als het apparaat een gebruikersinterface bevat, de bedrijfsportal-app wordt de eindgebruiker gevraagd om te verlenen Apparaatbeheerder tijdens [inschrijving](#step-3-enroll-the-device-in-to-intune) (in dit artikel).

Als een gebruikersinterface niet beschikbaar is, gebruikt u de **DevAdmin Manager** in StageNow om een profiel waarin Apparaatbeheerder handmatig wordt toegekend aan de bedrijfsportal-app te maken.

De volgende stappen bevatten een overzicht. Zie voor specifieke details van zebra.bmp documentatie. 
[Accu wisselen modus als apparaatbeheerder](https://zebratechnologies.force.com/s/article/Set-Battery-Swap-Mode-as-Device-Administrator-using-StageNow-Tool) (Zebra.bmp van website opent) mogelijk een goede bron.

1. Maak een profiel in StageNow, en selecteer **Xpert modus**.
2. Voeg **DevAdmin Manager** aan het profiel.
3. Stel **actie voor het beheer van apparaten** naar **inschakelen als Apparaatbeheerder**.
4. Stel **apparaat Admin pakketnaam** te `com.microsoft.windowsintune.companyportal`.
5. Stel **Admin klasse apparaatnaam** naar `com.microsoft.omadm.client.PolicyManagerReceiver`.

Doorgaan met het publicatieprofiel en deze gebruiken met de app StageNow op het apparaat. De bedrijfsportal-app wordt de rol van Apparaatbeheerder verleend.

## <a name="step-3-enroll-the-device-in-to-intune"></a>Stap 3: Het apparaat in Intune inschrijven

Na het voltooien van de eerste twee stappen, is de bedrijfsportal-app op het apparaat geïnstalleerd. Het apparaat is klaar om te worden ingeschreven in intune.

[Android-apparaten inschrijven](android-enroll.md) vermeldt de stappen. Als u veel Zebra.bmp apparaten hebt, kunt u gebruik van een [apparaatinschrijvingsmanageraccount](device-enrollment-manager-enroll.md).

## <a name="step-4-create-a-device-management-profile-in-stagenow"></a>Stap 4: Een apparaatprofiel voor beheer in StageNow maken

Gebruik StageNow te maken van een profiel dat u configureert de instellingen die u wilt beheren op het apparaat. Zie voor specifieke details van zebra.bmp documentatie. [Profielen](http://techdocs.zebra.com/stagenow/3-2/stagingprofiles/) (Zebra.bmp van website opent) mogelijk een goede bron.

Wanneer u het profiel in StageNow, op de laatste stap maakt, selecteert u **exporteren naar MDM**. Hiermee wordt een XML-bestand gegenereerd. Sla dit bestand. U hebt deze nodig in een latere stap.

> [!TIP]
> Het is raadzaam om te testen van het profiel voordat u deze op apparaten in uw organisatie implementeren. Als u wilt testen, in de laatste stap bij het maken van profielen met StageNow op uw computer, gebruikt u de **testen** opties. Het bestand StageNow gegenereerd met de app StageNow op het apparaat vervolgens gebruiken. 
> 
> De app StageNow op het apparaat wordt logboeken die worden gegenereerd wanneer u het testen van het profiel. [Gebruik StageNow Zebra.bmp Android-apparaten in Intune aanmeldt](android-zebra-mx-logs-troubleshoot.md) bevat informatie over het gebruik van StageNow logboeken voor meer inzicht in fouten.

> [!NOTE]
> Als u verwijzen naar apps, updatepakketten of andere in uw profiel StageNow updatebestanden, wilt u dat het apparaat om deze updates te downloaden. U kunt de updates, moet het apparaat verbinding met de server van de implementatie StageNow wanneer het profiel wordt toegepast. 
> 
> Of u kunt ingebouwde functies gebruiken in Intune om op te halen van deze wijzigingen, met inbegrip van: 
> - App-beheerfuncties op [toevoegen](apps-add.md), [implementeren](apps-deploy.md), bijwerken, en [monitor](apps-monitor.md) apps.
> - Beheren [systeem- en app-updates](device-restrictions-android-for-work.md#device-owner-only) op apparaten waarop Android Enterprise

Nadat u het bestand hebt getest, wordt de volgende stap is het implementeren van het profiel op apparaten met Intune.

> [!NOTE]
> Implementeer een profiel voor elk apparaat. Als er meerdere StageNow profielen die u wilt implementeren op de apparaten, de profielen StageNow exporteren en de instellingen in één XML-bestand te combineren, voordat u deze aan Intune toevoegen. 
> 
> U wilt niet dat twee instellingen die de dezelfde eigenschap in de dezelfde XML-bestand configureren. Het doel is om te voorkomen van conflicten tussen de instellingen op het apparaat.

## <a name="step-5-create-a-profile-in-intune"></a>Stap 5: Een profiel maken in Intune

Maak in Intune een apparaatconfiguratieprofiel:

1. Selecteer in [Azure Portal](https://portal.azure.com) de optie **Alle services** > filter op **Intune** > selecteer **Intune**.
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

    - **Naam**: voer een beschrijvende naam in voor het nieuwe profiel.
    - **Beschrijving:** voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: selecteer **Android**.
    - **Profieltype**: Selecteer **MX-profiel (alleen Zebra.bmp)**.

4. In **MX-profiel in XML-indeling**, toevoegen van het XML-profielbestand [u hebt geëxporteerd uit StageNow](#step-4-create-a-device-management-profile-in-stagenow) (in dit artikel).
5. Selecteer **OK** > **Maken** om uw wijzigingen op te slaan. Het beleid is gemaakt en weergegeven in de lijst.

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens kunt u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

De volgende keer dat het apparaat controleert op configuratie-updates, wordt de MX-profiel geïmplementeerd op het apparaat. Apparaten synchroniseren met Intune wanneer apparaten registreert, en vervolgens ongeveer elke 8 uur. U kunt ook [synchronisatie in Intune afgedwongen](device-sync.md). Of open op het apparaat de **bedrijfsportal-app** > **instellingen** > **synchronisatie**. 

> [!TIP]
> - Uit veiligheidsoverwegingen, niet het XML-tekst-profiel niet worden weergegeven nadat u deze hebt opgeslagen. De tekst is versleuteld en u ziet alleen sterretjes (`****`). Ter referentie, is het raadzaam om op te slaan kopieën van de profielen MX voordat u ze aan Intune toevoegen.
> 
> - Voor het bijwerken van een profiel nadat deze toegewezen aan apparaten Zebra.bmp, maakt u een bijgewerkte StageNow XML-bestand, de bestaande Intune-profiel bewerken en de nieuwe StageNow XML-bestand toevoegen. Dit nieuwe bestand overschreven door het vorige StageNow-beleid in het profiel.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

[StageNow Logboeken gebruiken om op te lossen Zebra.bmp apparaten](android-zebra-mx-logs-troubleshoot.md).
