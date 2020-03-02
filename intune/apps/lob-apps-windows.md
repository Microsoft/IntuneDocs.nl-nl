---
title: Een Windows Line-Of-Business-app toevoegen aan Microsoft Intune
titleSuffix: ''
description: Hier vindt u meer informatie over het toevoegen van Windows Line-Of-Business-apps (LOB) met Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/21/2020
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
ms.openlocfilehash: ceb4d2354ca073cf05f526df7638aebf8f16d5b7
ms.sourcegitcommit: 5881979c45fc973cba382413eaa193d369b8dcf6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "77569486"
---
# <a name="add-a-windows-line-of-business-app-to-microsoft-intune"></a>Een Windows Line-Of-Business-app toevoegen aan Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Een LOB-app is een app die u vanaf een app-installatiebestand toevoegt. Dit type app wordt doorgaans intern geschreven. De volgende stappen bevatten instructies waarmee u een Windows LOB-app kunt toevoegen aan Microsoft Intune.

> [!IMPORTANT]
> Wanneer u Win32-apps implementeert met behulp van een installatiebestand met de extensie .msi (verpakt in een .intunewin-bestand met behulp van de Content Prep Tool), kunt u de [Intune-beheerextensie](../apps/intune-management-extension.md) gebruiken. Als u de installatie van Win32-apps en Line-Of-Business-apps tijdens de Autopilot-registratie combineert, is het mogelijk dat de installatie van de app mislukt.  

## <a name="select-the-app-type"></a>Het app-type selecteren

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. Selecteer in het deelvenster **Een app-type selecteren** onder het app-type **Overige** de optie **Line-Of-Business-app**.
4. Klik op **Selecteren**. De stappen **App toevoegen** worden weergegeven.

## <a name="step-1---app-information"></a>Stap 1: App-gegevens

### <a name="select-the-app-package-file"></a>Het app-pakketbestand selecteren

1. Klik in het deelvenster **App toevoegen** op **App-pakketbestand selecteren**. 
2. Selecteer in het deelvenster **App-pakketbestand** de bladerknop. Selecteer vervolgens een Windows-installatiebestand met de extensie **.msi**, **.appx** of **.appxbundle**.
   De details van de app worden weergegeven.

    > [!NOTE]
    > De bestandsextensies voor Windows-apps zijn **.msi**, **.appx**, **.appxbundle**, **.msix** en **.msixbundle**.  

3. Wanneer u klaar bent, selecteert u **OK** in het deelvenster **App-pakketbestand** om de app toe te voegen.

### <a name="set-app-information"></a>App-gegevens instellen

1. Voeg de details voor uw app toe op de pagina **App-gegevens**. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden in het deelvenster mogelijk automatisch ingevuld.
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal wordt weergegeven. Zorg ervoor dat alle app-namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving**: voer een beschrijving van de app in. De beschrijving wordt weergegeven in de bedrijfsportal.
    - **Uitgever**: Voer de naam van de uitgever van de app in.
    - **Minimumversie van het besturingssysteem**: selecteer in de lijst de minimumversie van het besturingssysteem waarin de app kan worden geïnstalleerd. Als u de app toewijst aan een apparaat met een lager besturingssysteem, wordt de app niet geïnstalleerd.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Met categorieën kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: Geef de app prominent weer op de hoofdpagina van de bedrijfsportal wanneer gebruikers door apps bladeren.
    - **Informatie-URL**: Voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven in de bedrijfsportal.
    - **Privacy-URL**: (optioneel) Voer de URL in van een website die privacyinformatie over deze app bevat. De URL wordt weergegeven in de bedrijfsportal.
    - **Ontwikkelaar**: Voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app (optioneel). Bijvoorbeeld **HR-afdeling**.
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Logo**: upload een pictogram dat u aan de app wilt koppelen. Het pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
2. Klik op **Volgende** om de pagina **Bereiktags** weer te geven.

## <a name="step-2---select-scope-tags-optional"></a>Stap 2: Bereiktags selecteren (optioneel)
U kunt bereiktags gebruiken om te bepalen wie er informatie over client-apps mag bekijken in Intune. Zie [Use role-based access control and scope tags for distributed IT](../fundamentals/scope-tags.md) (Op rollen gebaseerd toegangsbeheer en bereiktags gebruiken voor gedistribueerde IT) voor uitgebreide informatie over bereiktags.

1. Klik op **Bereiktags selecteren** om desgewenst bereiktags toe te voegen voor de app. 
2. Klik op **Volgende** om de pagina **Toewijzingen** weer te geven.

## <a name="step-3---assignments"></a>Stap 3: Toewijzingen

1. Selecteer de groepstoewijzingen **Vereist**, **Beschikbaar voor ingeschreven apparaten** of **Verwijderen** voor de app. Zie [Groepen toevoegen om gebruikers en apparaten in te delen](~/fundamentals/groups-add.md) en [Apps toewijzen aan groepen met Microsoft Intune](apps-deploy.md) voor meer informatie.
2. Klik op **Volgende** om naar de pagina **Controleren en maken** weer te geven. 

## <a name="step-4---review--create"></a>Stap 4: beoordelen en maken

1. Controleer de waarden en instellingen die u hebt ingevoerd voor de app.
2. Klik als u klaar bent op **Maken** om de app toe te voegen aan Intune.

    De blade **Overzicht** voor de Line-Of-Business-app wordt weergegeven.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps. In de lijst, kunt u de apps toewijzen aan groepen die u kiest. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

## <a name="update-a-line-of-business-app"></a>een Line-Of-Business-app bijwerken

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

- Meer informatie over Win32-apps. Zie [Win32-app-beheer](~/apps/apps-win32-app-management.md).
