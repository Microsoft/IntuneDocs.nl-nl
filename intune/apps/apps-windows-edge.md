---
title: Microsoft Edge voor Windows 10 toevoegen aan Microsoft Intune
titleSuffix: ''
description: Meer informatie over het toevoegen van Microsoft Edge voor Windows 10 aan Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: kellieei
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: af24b5fe33bc1e794529ef5a5ab6975eed4fb9cc
ms.sourcegitcommit: 556b7ea2049014c9027f0e44affd3f301fab55fc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/06/2019
ms.locfileid: "73709915"
---
# <a name="add-microsoft-edge-for-windows-10-to-microsoft-intune"></a>Microsoft Edge voor Windows 10 toevoegen aan Microsoft Intune

Voordat u apps kunt implementeren, configureren, bewaken of beveiligen, moet u deze aan Intune toevoegen. Een van de beschikbare [app-typen](~/apps/apps-add.md#app-types-in-microsoft-intune) is Microsoft Edge *versie 77 en later*. Door dit app-type in Intune te selecteren, kunt u Microsoft Edge *versie 77 en later* toewijzen aan en installeren op door u beheerde Windows 10-apparaten.

> [!IMPORTANT]
> Dit app-type is in **openbare preview** en biedt Dev- en Beta-kanalen voor Windows 10. De implementatie is alleen in het Engels (EN) beschikbaar, maar eindgebruikers kunnen de weergavetaal wijzigen in de browser via **Instellingen** > **Talen**. Microsoft Edge is een Win32-app die wordt geïnstalleerd in systeemcontext en in soortgelijke architecturen (x86-app in een x86-besturingssysteem en x64-app in een x64-besturingssysteem). Er worden bestaande Microsoft Edge-installaties door Intune gedetecteerd. Als de app in de gebruikerscontext is geïnstalleerd, wordt deze door een systeeminstallatie overschreven. Als de app in de systeemcontext is geïnstalleerd, wordt de installatie gerapporteerd. Automatische updates van Microsoft Edge is bovendien standaard **Ingeschakeld** en Microsoft Edge kan niet worden verwijderd.

> [!NOTE]
> Microsoft Edge *versie 77 en later* is ook beschikbaar voor macOS.
> 
> U kunt de ingebouwde toepassingsimplementatie van Microsoft Edge niet gebruiken voor aan de werkplek toegevoegde computers. Voor de ingebouwde toepassingsimplementatie is de Intune-beheerextensie vereist, die er alleen is voor aan AAD toegevoegde apparaten. U kunt Microsoft Edge *versie 77 en later* wel implementeren met behulp van een *MSI-bestand* dat is geüpload naar **Client-apps** . Zie [Een Windows Line-Of-Business-app toevoegen aan Microsoft Intune](~/apps/lob-apps-windows.md).

## <a name="prerequisites"></a>Vereisten
- Windows 10 RS2 en hoger is vereist.
- Alle vooraf geïnstalleerde versies van Microsoft Edge *versie 77 en later* voor de kanalen **Dev** en **Beta** in de gebruikerscontext worden overschreven met Edge, geïnstalleerd in de systeemcontext.

## <a name="configure-the-app-in-intune"></a>De app configureren in Intune
U kunt een Microsoft Edge versie 77 en later toevoegen aan Intune met behulp van de volgende stappen:

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer in het deelvenster **Intune** de optie **Client-apps** > **Apps** > **Toevoegen**.
3. Selecteer in de lijst **App-type** onder **Microsoft Edge, versie 77 en later** de optie **Windows 10**.

## <a name="configure-app-information"></a>App-gegevens configureren
In deze stap geeft u informatie op over deze app-implementatie. Aan de hand van deze informatie kunt u de app vinden in Intune en kunnen gebruikers de app vinden in de bedrijfsportal.

1. Selecteer de optie **App-gegevens** om de blade **App-gegevens** weer te geven.
2. Op de blade **App-gegevens** geeft u informatie op over deze app-implementatie. Aan de hand van deze informatie kunt u de app vinden in Intune en kunnen gebruikers de app vinden in de bedrijfsportal.
    - **Naam**: Voer de naam van de app in zoals deze in de bedrijfsportal zal worden weergegeven. Zorg ervoor dat alle namen uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving**: Voer een beschrijving in voor de app. U kunt bijvoorbeeld de beoogde gebruikers vermelden in de beschrijving.
    - **Uitgever**: Microsoft wordt weergegeven als de uitgever.
    - **Categorie**: selecteer een of meer ingebouwde app-categorieën of een categorie die u hebt gemaakt (optioneel). Met deze instellingen kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: Selecteer deze optie om de app prominent weer te geven op de hoofdpagina van de bedrijfsportal wanneer gebruikers zoeken naar apps.
    - **Informatie-URL**: Voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: (optioneel) Voer de URL in van een website die privacyinformatie over deze app bevat. De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: Microsoft wordt weergegeven als de ontwikkelaar.
    - **Eigenaar**: Microsoft wordt weergegeven als de eigenaar.
    - **Opmerkingen**: Voer de opmerkingen in die u aan deze app wilt koppelen (optioneel).
3. Selecteer **OK**.

## <a name="configure-app-settings"></a>App-instellingen configureren
In deze stap configureert u de installatieopties voor de app.

1. Selecteer op de blade **App toevoegen** de optie **App-instellingen**.
2. Selecteer op de blade **App-instellingen** de optie **Beta** of **Dev** in de lijst **Kanaal** om te bepalen vanuit welk Edge-kanaal u de app gaat implementeren.
    - Het kanaal **Beta** is de stabielste previewervaring van Microsoft Edge en de beste keuze voor een volledige pilot binnen uw organisatie. Met elke zes weken belangrijke updates bevat elke release de vergaarde kennis en verbeteringen van het Dev-kanaal.
    - Het kanaal **Dev** is gereed voor zakelijke feedback over Windows, Windows Server en macOS. Het wordt elke week bijgewerkt en bevat de nieuwste verbeteringen en oplossingen.

    > [!NOTE]
    > Het Microsoft Edge-browserlogo wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.

3.  Selecteer **OK**.

## <a name="select-scope-tags-optional"></a>Bereiktags selecteren (optioneel)
U kunt bereiktags gebruiken om te bepalen wie er informatie over client-apps mag bekijken in Intune. Zie Op rollen gebaseerd toegangsbeheer en bereiktags gebruiken voor gedistribueerde IT voor uitgebreide informatie over bereiktags.
1.  Selecteer **Bereik (tags)**  > **Toevoegen**.
2.  Gebruik het vak onder **Selecteren** om bereiktags te zoeken.
3.  Schakel het selectievakje in naast de bereiktags die u aan deze app wilt toewijzen.
4.  Klik op **Selecteren** > **OK**.

## <a name="add-the-app"></a>De app toevoegen
Wanneer u klaar bent met het configureren van de app, selecteert u **Toevoegen** op de blade **App-app**. 

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u selecteert. 

> [!NOTE]
> Momenteel blijft Microsoft Edge op het apparaat als u de toewijzing van de implementatie ervan ongedaan maakt.

## <a name="troubleshooting"></a>Probleemoplossing
**Microsoft Edge versie 77 en later voor Windows 10:**<br>
Intune maakt gebruik van de Intune-beheerextensie om het Microsoft Edge-installatieprogramma te downloaden en te implementeren op toegewezen Windows 10-apparaten. Vervolgens worden de implementatie-instellingen doorgegeven aan het Microsoft Edge-installatieprogramma, dat de Microsoft Edge-browser rechtstreeks vanuit het CDN downloadt en installeert. Raadpleeg de [vereisten voor de Intune-beheerextensie](~/apps/intune-management-extension.md#prerequisites) en de best practices die worden beschreven bij toegang tot Azure Update Service en het CDN om ervoor te zorgen dat het in uw netwerkconfiguratie is toegestaan dat Windows 10-apparaten toegang krijgen tot deze locaties. Als u toegang tot installatiebestanden vanaf een CDN wilt toestaan om de browser te installeren, moet u bovendien toegang tot Windows Update-eindpunten toestaan. Zie voor meer informatie [Verbindingseindpunten beheren voor Windows 10, versie 1809 – Windows Update](https://docs.microsoft.com/windows/privacy/manage-windows-1809-endpoints#windows-update) en [Netwerkeindpunten voor Microsoft Intune](~/fundamentals/intune-endpoints.md).

## <a name="next-steps"></a>Volgende stappen
- [Apps aan groepen toewijzen](~/apps/apps-deploy.md)
