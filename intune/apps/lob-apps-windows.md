---
title: Een Windows Line-Of-Business-app toevoegen aan Microsoft Intune
titleSuffix: ''
description: Hier vindt u meer informatie over het toevoegen van Windows Line-Of-Business-apps (LOB) met Microsoft Intune.
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
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6f4c7b5e3cca06a3ec10ea1b3dfc5e45546c841f
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563909"
---
# <a name="add-a-windows-line-of-business-app-to-microsoft-intune"></a>Een Windows Line-Of-Business-app toevoegen aan Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Een LOB-app is een app die u vanaf een app-installatiebestand toevoegt. Dit type app wordt doorgaans intern geschreven. De volgende stappen bevatten instructies waarmee u een Windows LOB-app kunt toevoegen aan Microsoft Intune.

> [!IMPORTANT]
> Wanneer u Win32-apps implementeert met behulp van een installatiebestand met de extensie *.msi*, kunt u overwegen om de [Intune-beheerextensie](../apps/intune-management-extension.md) te gebruiken. Als u de installatie van Win32-apps en Line-Of-Business-apps tijdens de Autopilot-registratie combineert, is het mogelijk dat de installatie van de app mislukt.  

## <a name="step-1-specify-the-software-setup-file"></a>Stap 1: locatie van het software-installatiebestand opgeven

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. Selecteer in het deelvenster **App toevoegen** de optie **Line-Of-Business-app** als het **app-type**.

## <a name="step-2-configure-the-app-package-file"></a>Stap 2: app-pakketbestand configureren

1. Selecteer in het deelvenster **App toevoegen** de optie **App-pakketbestand**.
2. Selecteer in het deelvenster **App-pakketbestand** de bladerknop. Selecteer vervolgens een Windows-installatiebestand met de extensie **.msi**, **.appx** of **.appxbundle**.

    > [!NOTE]
    > De bestandsextensies voor Windows-apps zijn **.msi**, **.appx**, **.appxbundle**, **.msix** en **.msixbundle**.  

1. Klik op **OK** wanneer u klaar bent.


## <a name="step-3-configure-app-information"></a>Stap 3: App-gegevens configureren

1. Selecteer **App-gegevens** in het deelvenster **App toevoegen**.
2. Configureer de volgende gegevens in het deelvenster **App-gegevens**. Sommige van de waarden in dit deelvenster worden mogelijk automatisch ingevuld.
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal wordt weergegeven. Zorg ervoor dat alle app-namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving**: Voer een beschrijving in voor de app. De beschrijving wordt weergegeven in de bedrijfsportal.
    - **Uitgever**: Voer de naam van de uitgever van de app in.
    - **App-versie negeren**: stel deze optie in op **Ja** als de app-ontwikkelaar de app automatisch bijwerkt. Deze optie is alleen van toepassing op mobiele .msi-apps.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Met categorieën kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: Geef de app prominent weer op de hoofdpagina van de bedrijfsportal wanneer gebruikers door apps bladeren.
    - **Informatie-URL**: voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven in de bedrijfsportal.
    - **Privacy-URL**: voer de URL in van een website die privacyinformatie over deze app bevat (optioneel). De URL wordt weergegeven in de bedrijfsportal.
    - **Opdrachtregelargumenten**: voer eventueel opdrachtregelargumenten in die u wilt toepassen op het MSI-bestand wanneer dit wordt uitgevoerd.  Bijvoorbeeld **/q**. Neem niet de msiexec-opdracht of -argumenten op, zoals **/i** of **/x**, omdat ze automatisch worden gebruikt. Zie [Opdrachtregelopties](https://docs.microsoft.com/windows/desktop/Msi/command-line-options) voor meer informatie. Als voor het MSI-bestand extra opdrachtregelopties vereist zijn, kunt u [Win32-app-beheer](app-management.md) gebruiken.
    - **Ontwikkelaar**: Voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app (optioneel). Bijvoorbeeld **HR-afdeling**.
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Logo**: upload een pictogram dat u aan de app wilt koppelen. Het pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
3. Klik op **OK** wanneer u klaar bent.

## <a name="step-4-finish-up"></a>Stap 4: Voltooien

1. Controleer in het deelvenster **App toevoegen** of de app-gegevens die u hebt geconfigureerd correct zijn.
2. Selecteer **Toevoegen** om de app te uploaden naar Intune.

## <a name="step-5-update-a-line-of-business-app"></a>Stap 5: een Line-Of-Business-app bijwerken

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

   > [!NOTE]
   > De Intune-service kan alleen een nieuw APPX-bestand op het apparaat implementeren als u de tekenreeks `Version` in het bestand AppxManifest.xml in uw APPX-pakket verhoogt.

## <a name="configure-a-self-updating-mobile-msi-app-to-ignore-the-version-check-process"></a>Een mobiele MSI-app die automatisch wordt bijgewerkt configureren om de versiecontrole te negeren

U kunt een bekende mobiele MSI-app die automatisch wordt bijgewerkt configureren om de versiecontrole te negeren.

Sommige op het MSI-installatieprogramma gebaseerde apps worden automatisch bijgewerkt door de app-ontwikkelaar of via een andere bijwerkmethode. Voor deze automatisch bijgewerkte MSI-apps kunt u de instelling **App-versie negeren** in het deelvenster **App-gegevens** configureren. Wanneer u deze instelling op **Ja** instelt, dwingt Microsoft Intune de app-versie die is geïnstalleerd op de Windows-client niet af.

Met deze functie kunt u voorkomen dat er een racevoorwaarde optreedt. Een racevoorwaarde kan bijvoorbeeld optreden wanneer de app automatisch wordt bijgewerkt door de ontwikkelaar van de app en door Intune wordt bijgewerkt. Er kan door beide partijen worden geprobeerd om een versie van de app op een Windows-client af te dwingen, waardoor een conflict kan ontstaan.

## <a name="next-steps"></a>Volgende stappen

- De app die u hebt gemaakt, wordt weergegeven in de lijst met apps. U kunt deze nu toewijzen aan de gewenste groepen. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

- Meer informatie over de manieren waarop u de eigenschappen en de toewijzing van uw app kunt controleren. Zie [App-gegevens en -toewijzingen controleren](apps-monitor.md).

- Meer informatie over de context van uw app in Intune. Zie [Overzicht van de app-levenscyclus in Microsoft Intune](app-lifecycle.md).
