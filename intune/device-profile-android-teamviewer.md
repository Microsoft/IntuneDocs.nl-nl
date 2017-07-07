---
title: Android-apparaten extern beheren met TeamViewer
titleSuffix: Intune on Azure
description: Meer informatie over hoe u Android-apparaten extern beheert met TeamViewer.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 15a005ae2b84c7bd4f913f892089965c10f3b23e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="provide-remote-assistance-for-intune-managed-android-devices"></a>Hulp op afstand verlenen voor Android-apparaten die worden beheerd met Intune

Intune kan de afzonderlijk verkrijgbare [TeamViewer](https://www.teamviewer.com)-software gebruiken, zodat u uw gebruikers met Android-apparaten hulp op afstand kunt bieden. Gebruik de informatie in dit onderwerp om enkele instellingen te configureren en aan de slag te gaan.

## <a name="before-you-start"></a>Voordat u begint

### <a name="required-permissions"></a>Vereiste machtigingen

Zorg ervoor dat de volgende machtigingen als [Intune-rol](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control) zijn toegewezen aan de gebruiker van Azure Portal:
- Als u de beheerder de mogelijkheid wilt bieden om de instellingen voor de TeamViewer-connector te wijzigen, verleent u de beheerder de machtiging **Hulp op afstand bijwerken**.
- Als u de beheerder de mogelijkheid wilt bieden om nieuwe instellingen voor hulp of afstand te configureren, verleent u de beheerder de machtiging **Hulp op afstand aanvragen**. Gebruikers met machtigingen kunnen voor iedere gebruiker een aanvraag indien om een sessie te starten. Deze mogelijkheid wordt niet beperkt door het toewijzingsbereik voor een Intune-rol. De toewijzingsbereiken van Intune-rollen beperken niet het aantal apparaten of gebruikers waarvoor verzoeken om hulp op afstand kunnen worden geïnitieerd.

>[!NOTE]
>Door TeamViewer in te schakelen, kunt u met de TeamViewer voor Intune-connector TeamViewer-sessies maken, Active Directory-gegevens lezen en het toegangstoken voor het TeamViewer-account opslaan.

### <a name="configure-the-intune-teamviewer-connector"></a>De Intune TeamViewer-connector configureren

Voordat u hulp op afstand via Android-apparaten kunt bieden, moet u eerst de Intune TeamViewer-connector configureren door de volgende stappen uit te voeren:


1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies op de blad **Apparaten en groepen** achtereenvolgens**Setup** > **TeamViewer-connector**.
5. Klik op de blade **TeamViewer-connector** op **Inschakelen** en accepteer vervolgens de licentieovereenkomst voor de TeamViewer-service.
6. Kies **Aanmelden bij TeamViewer voor goedkeuring**.
7. Er wordt een webpagina van de TeamViewer-site geopend. Voer de referenties van uw TeamViewer-licentie in en klik vervolgens op **Aanmelden**.


## <a name="how-to-remotely-administer-an-android-device"></a>Een Android-apparaat op afstand beheren

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies op de blade **Apparaten** achtereenvolgens **Beheren** > **Alle apparaten**.
5. Selecteer het apparaat dat u extern wilt beheren en kies op de blade met de apparaateigenschappen vervolgens **Meer** > **Nieuwe Hulp op afstand-sessie**.
6. Nadat er een verbinding tussen Intune en de TeamViewer-service tot stand is gebracht, worden er enkele gegevens over het Android-apparaat weergegeven. Kies **Verbinden** om de externe sessie te starten.

![Android TeamViewer-vensters](./media/android-teamviewer.png)

U kunt in het TeamViewer-venster verschillende externe acties op het Android-apparaat uitvoeren, waaronder het op afstand beheren van het apparaat. Zie de [TeamViewer-documentatie](https://www.teamviewer.com/support/documents/) voor gedetailleerde informatie over de acties die u kunt uitvoeren.

Wanneer u klaar bent, sluit u het TeamViewer-venster.

## <a name="end-user-notifications"></a>Meldingen voor eindgebruikers

Er wordt een vlag voor meldingen op het pictogram van de bedrijfsportal-app op het apparaat van de eindgebruiker weergegeven. Daarnaast wordt er een melding weergegeven wanneer de app wordt geopend. Ze kunnen het verzoek om hulp op afstand accepteren.

