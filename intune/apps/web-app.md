---
title: Web-apps aan Microsoft Intune toevoegen
titleSuffix: ''
description: Meer informatie over het toevoegen van web-apps (client-/servertoepassingen) aan Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 204a19546e9466fdf7064e15b8cba7268ec1b757
ms.sourcegitcommit: b8127c7a62d9ac4d0f768980fa1424567bb58733
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2019
ms.locfileid: "72349980"
---
# <a name="add-web-apps-to-microsoft-intune"></a>Web-apps aan Microsoft Intune toevoegen

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune biedt ondersteuning voor diverse typen apps, waaronder web-apps. Een web-app is een client-/servertoepassing. De server levert de web-app, waaronder de gebruikersinterface, inhoud en functionaliteit. Bovendien bieden moderne webhostingplatformen meestal beveiliging, taakverdeling en andere voordelen. Een web-app wordt afzonderlijk onderhouden op internet. U gebruikt Microsoft Intune om naar dit type app te verwijzen. U wijst ook de groepen gebruikers toe die toegang krijgen tot deze app. 

Voordat u een app kunt beheren en aan uw gebruikers kunt toewijzen, voegt u de app toe aan Intune. 

Er wordt door Intune een snelkoppeling gemaakt naar de web-app op het apparaat van de gebruiker. Voor iOS-apparaten wordt een snelkoppeling naar de web-app toegevoegd aan het Startscherm. Voor Android-apparaten wordt een snelkoppeling naar de web-app toegevoegd aan het de widget Intune-bedrijfsportal, en moet de widget handmatig worden vastgemaakt door de gebruiker. Voor Windows-apparaten wordt een snelkoppeling naar de web-app geplaatst op het Startscherm.

> [!Note]
> Web-apps worden niet ondersteund op apparaten met een Android-werkprofiel. Op het apparaat van de gebruiker moet een browser zijn geïnstalleerd om web-apps te kunnen starten.

## <a name="add-a-web-app-to-intune"></a>Een web-app toevoegen aan Intune
Voer de volgende stappen uit om een app toe te voegen aan Intune als een snelkoppeling naar een app op internet:

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Selecteer in het deelvenster **Intune** de optie **Client-apps**.
4. Selecteer in het workloaddeelvenster **Client-apps** onder **Beheren** de optie **Apps**.
5. Selecteer **Toevoegen** in het deelvenster **Apps**.
6. Selecteer in het deelvenster **App toevoegen** het type **Weblink** in de vervolgkeuzelijst **App-type**.
7. Selecteer **Configureren**.
8. Voeg in het deelvenster **App-gegevens** de volgende gegevens toe:
    - **Naam**:  voer de naam van de app in zoals deze in de bedrijfsportal moet worden weergegeven. 

        > [!NOTE]
        > Als u de naam van de app wijzigt via Intune Azure Portal nadat u de app hebt geïnstalleerd en geïmplementeerd, kunt u geen beleid meer richten op de app met behulp van opdrachten.

    - **Beschrijving**: Voer een beschrijving in voor de app. Deze beschrijving wordt voor gebruikers weergegeven in de bedrijfsportal.
    - **Uitgever**: voer de naam van de uitgever van de app in.
    - **App-URL**: voer de URL in van de website waarop de app wordt gehost die u wilt toewijzen.
    - **Categorie**: Selecteer een of meer ingebouwde app-categorieën of een categorie die u hebt gemaakt (optioneel). Hiermee kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: selecteer deze optie om het app-pakket prominent weer te geven op de hoofdpagina van de bedrijfsportal wanneer gebruikers naar apps bladeren.
    - **Beheerde browser vereisen om deze koppeling te openen**: selecteer deze optie om aan uw gebruikers een koppeling naar een website of web-app toe te wijzen die ze in de door Intune beheerde browser kunnen openen. Deze browser moet op hun apparaat zijn geïnstalleerd.
    - **Logo**: Upload een pictogram dat aan de app wordt gekoppeld. Dit pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
9. Selecteer **OK**.
10. Selecteer **Toevoegen** in het deelvenster **App toevoegen**.

> [!Note]
> Gebruikers moeten de Intune-widget toevoegen aan hun beginscherm om web-apps weer te geven die zijn toegewezen aan Android-apparaten.
>
> Momenteel wordt de implementatie van Intune-web-apps op iOS-apparaten gekoppeld aan het beheerprofiel; dit kan niet handmatig worden verwijderd. U kunt het implementatietype in de Intune-portal wijzigen in **Verwijderen**. Daarna kunt u de web-app automatisch verwijderen. Als u de implementatie echter verwijdert voordat u de intentie van de app-toewijzing hebt gewijzigd in **Verwijderen**, bevindt de web-app zich permanent op het apparaat de registratie van het apparaat bij Intune ongedaan wordt gemaakt.

## <a name="next-steps"></a>Volgende stappen

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u selecteert. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp. 
