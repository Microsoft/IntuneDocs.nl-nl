---
title: Apparaten extern beheren met TeamViewer
titlesuffix: Azure portal
description: "Meer informatie over hoe u apparaten extern beheert met TeamViewer.”"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8bb3061baf42b011c98cf7b196e939448f91cff4
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/20/2017
---
# <a name="provide-remote-assistance-for-intune-managed-devices"></a>Hulp op afstand verlenen voor apparaten die worden beheerd met Intune

Intune kan de afzonderlijk verkrijgbare [TeamViewer](https://www.teamviewer.com)-software gebruiken, zodat u gebruikers met door u beheerde apparaten hulp op afstand kunt bieden. Gebruik de informatie in dit onderwerp om aan de slag te gaan.

## <a name="before-you-start"></a>Voordat u begint

### <a name="supported-devices"></a>Ondersteunde apparaten

De volgende door Intune beheerde apparaten ondersteunen extern beheer:

- Door Intune beheerde Android-apparaten
- Door Intune beheerde Windows-apparaten met Windows 10, Windows 10 Mobile en hoger.

>[!NOTE]
>Windows Holographic (HoloLens), Windows Team (Surface Hub) en Windows 10 S worden niet ondersteund door de TeamViewer-software



### <a name="required-permissions"></a>Vereiste machtigingen

Zorg ervoor dat de volgende machtigingen als [Intune-rol](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control) zijn toegewezen aan de gebruiker van Azure Portal:
- Als u de beheerder de mogelijkheid wilt bieden om de instellingen voor de TeamViewer-connector te wijzigen, verleent u de beheerder de machtiging **Hulp op afstand bijwerken**.
- Als u de beheerder een nieuwe aanvraag voor hulp of afstand wilt kunnen laten uitvoeren, verleent u de beheerder de machtiging **Hulp op afstand aanvragen**. Gebruikers met de machtiging **Hulp op afstand aanvragen** kunnen een aanvraag indienen om een sessie voor een willekeurige gebruiker te starten. Ze worden hiertoe niet door een toewijzingsbereik van een Intune-rol beperkt. De toewijzingsbereiken van Intune-rollen beperken niet het aantal apparaten of gebruikers waarvoor verzoeken om hulp op afstand kunnen worden geïnitieerd.

>[!NOTE]
>Door TeamViewer in te schakelen, kunt u met de TeamViewer voor Intune-connector TeamViewer-sessies maken, Active Directory-gegevens lezen en het toegangstoken voor het TeamViewer-account opslaan.

### <a name="configure-the-intune-teamviewer-connector"></a>De Intune TeamViewer-connector configureren

Voordat u hulp op afstand voor apparaten kunt bieden, moet u eerst de Intune TeamViewer-connector configureren door de volgende stappen uit te voeren:


1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies op de blad **Apparaten en groepen** achtereenvolgens**Setup** > **TeamViewer-connector**.
5. Klik op de blade **TeamViewer-connector** op **Inschakelen** en accepteer vervolgens de licentieovereenkomst voor de TeamViewer-service.
6. Kies **Aanmelden bij TeamViewer voor goedkeuring**.
7. Er wordt een webpagina van de TeamViewer-site geopend. Voer de referenties van uw TeamViewer-licentie in en klik vervolgens op **Aanmelden**.


## <a name="how-to-remotely-administer-a-device"></a>Een apparaat op afstand beheren

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies op de blade **Apparaten** achtereenvolgens **Beheren** > **Alle apparaten**.
5. Selecteer het apparaat dat u extern wilt beheren en kies op de blade met de apparaateigenschappen vervolgens **Meer** > **Nieuwe Hulp op afstand-sessie**.
6. Nadat er een verbinding tussen Intune en de TeamViewer-service tot stand is gebracht, worden er enkele gegevens over het apparaat weergegeven. Kies **Verbinden** om de externe sessie te starten.

![Voorbeeld van TeamViewer in Android](./media/android-teamviewer.png)

U kunt in het TeamViewer-venster verschillende externe acties op het apparaat uitvoeren, waaronder het op afstand beheren van het apparaat. Zie de [TeamViewer-documentatie](https://www.teamviewer.com/support/documents/) voor gedetailleerde informatie over de acties die u kunt uitvoeren.

Als u klaar bent, sluit u het TeamViewer-venster.

## <a name="next-steps"></a>Volgende stappen

Er wordt een vlag voor meldingen op het pictogram van de bedrijfsportal-app op het apparaat van de eindgebruiker weergegeven. Daarnaast wordt er een melding weergegeven wanneer de app wordt geopend. Ze kunnen het verzoek om hulp op afstand accepteren.

