---
title: Line-Of-Business-apps beveiligen op apparaten die niet zijn geregistreerd | Microsoft Intune
description: In dit onderwerp wordt beschreven hoe u uw aangepaste reeks business-apps kunt voorbereiden, zodat u beleidsregels voor het beheren van mobiele apps kunt toepassen die kunnen helpen gegevensverlies te voorkomen.
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 00219467-a62e-43b6-954b-3084f54c45ba
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ce0bc5d1256e96e04e5d59420baed2117cb4854d
ms.openlocfilehash: 1df9d98f45eaf93163116e4f6a4c9d32125043c8


---

# Line-Of-Business-apps en -gegevens beveiligen op apparaten die niet zijn geregistreerd bij Microsoft Intune

Met MAM-beleid (Mobile App Management) kunt u uw bedrijfsgegevens beveiligen door gegevensverplaatsingen, zoals kopiëren en plakken, te beperken of door te voorkomen dat gebruikers bedrijfsdocumenten kunnen opslaan naar een persoonlijke locatie.   Als u MAM-beleid wilt toepassen op iOS en/of Android Line-Of-Business-apps, moet u de app eerst inpakken met de Microsoft Intune App Wrapping Tool.  App-wrapping is het proces waarbij een beheerlaag wordt toegepast op een mobiele app zonder dat de onderliggende toepassing hoeft te worden gewijzigd.  Zodra de app is ingepakt, kunt u MAM-beleid op de app toepassen en deze distribueren naar uw eindgebruikers.  

In dit onderwerp wordt uitgelegd wat de vereiste stappen zijn om MAM-beleid toe te passen voor apps die worden geopend op **apparaten in eigendom van de werknemer die niet worden beheerd** en op apparaten die worden beheerd met een **MDM-oplossing (Mobile Device Management) van derden**.  Zie [Bepalen hoe u apps voorbereidt op Mobile Application Management met Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) om uw Line-Of-Business-apps voor te bereiden die worden uitgevoerd op **apparaten die zijn geregistreerd bij Intune**.
##  Stap 1: De app voorbereiden
Voordat u MAM-beleid op een app kunt toepassen, moet u de app eerst inpakken met de Microsoft Intune App Wrapping Tool.  De instructies voor de installatie en het gebruik van het hulpprogramma zijn opgenomen in de download.  
>[!IMPORTANT]  
>Deze versie van de App Wrapping Tool, die apparaten ondersteunt die niet zijn geregistreerd bij Intune, is de komende weken beschikbaar als private preview. Als u wilt deelnemen, stuurt u een e-mail naar msintuneappsdk@microsoft.com voor meer informatie.

## Stap 2: De app toevoegen

Als u de Line-Of-Business-app wilt koppelen aan MAM-beleid, voert u de volgende stappen uit om de app-gegevens toe te voegen aan uw Intune-abonnement/tenant:

1. Ga in [Azure Portal](https://portal.azure.com/) naar **Intune Mobile Application Management > Instellingen** en kies **Line-Of-Business-apps**.

  ![Schermafbeelding van de instellingenblade met de optie Line-Of-Business](../media/mam-azure-portal-lob-on-settings.png)

2. Kies op de blade **Line-Of-Business-apps** de optie **Een aangepaste app toevoegen**.

  ![Schermafbeelding van de blade Line-Of-Business-apps met bovenaan de knop Aangepaste app toevoegen](../media/mam-azure-portal-add-lob-app-action.png)
3.  Geef een naam voor de app op, geef in het veld App-id de bundel-id op en geef het platform (iOS of Android) op.

  ![Schermafbeelding van de blade Een aangepaste app toevoegen](../media/mam-azure-portal-add-app-details.png) Met deze stap maakt u een unieke vermelding voor uw app.  De app wordt ook weergegeven in de lijst met doel-apps voor een MAM-beleid voor uw tenant, zoals staat beschreven in de volgende stap.

## Stap 3: MAM-beleid toepassen
Nadat de metagegevens van de app zijn geüpload naar de service, wordt de app weergegeven in de lijst met apps.  U kunt nu [een nieuw beleid of een bestaand beleid maken](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) en dit toepassen op de Line-Of-Business-app die u hebt toegevoegd in stap 2.

>[!IMPORTANT]
>U moet het MAM-beleid toepassen op de gebruikers die de ingepakte app gaan gebruiken.  Gebruikers waarvoor dit beleid niet wordt geïmplementeerd, kunnen deze app niet gebruiken.


  ![Schermafbeelding van de blade Doellijst met apps, waarin de nieuwe Line-Of-Business-app wordt weergegeven](../media/mam-azure-portal-lob-on-targeted-app-list.png)
## Stap 4: De app distribueren
U kunt apps op de volgende manieren implementeren voor uw eindgebruikers:
* Voor apparaten die zijn geregistreerd bij een MDM-oplossing van derden, kunt u de apps distribueren via uw MDM-oplossing.
* Voor apparaten die niet worden beheerd door een MDM-oplossing, hebt u een aangepaste oplossing nodig. Eindgebruikers moeten de app downloaden en installeren op hun apparaat.

## De metagegevens wijzigen
Als u de app-gegevens, zoals de naam van de app of de bundel-id, moet wijzigen, moet u [de app verwijderen](#remove-apps) en [toevoegen](#step-2-add-the-app) met de nieuwe metagegevens.

##  Apps verwijderen
U kunt een Line-Of-Business-app verwijderen uit de lijst met apps.  Hiermee wordt de app verwijderd uit de lijst en wordt de koppeling met het MAM-beleid verbroken. De app wordt echter niet van het apparaat van de eindgebruiker verwijderd.  

1.  Ga in [Azure Portal](https://portal.azure.com/) naar **Intune Mobile App Management > Instellingen**.  Kies op de blade **Instellingen** de optie **Line-Of-Business** om de lijst met bestaande apps te openen.  
2.  Selecteer de app die u wilt verwijderen en kies het **(…) contextmenu**.

  ![Schermafbeelding van de blade Line-Of-Business-apps met het weglatingsteken](../media/mam-azure-portal-lob-context-menu.png)
3.  Kies **Toepassing verwijderen** om de app te verwijderen.

  ![Schermafbeelding van de Line-Of-Business-blade met de optie voor het verwijderen van de app](../media/mam-azure-portal-delete-app.png)

  Hiermee worden alle apps uit de lijst met Line-Of-Business-apps en de doellijst met apps in het MAM-beleid verwijderd.



<!--HONumber=Jul16_HO3-->


