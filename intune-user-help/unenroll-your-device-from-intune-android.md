---
title: Uw Android-apparaat uit Intune verwijderen | Microsoft Docs
description: Uw Android-apparaat uit de Intune-bedrijfsportal verwijderen
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: f40aab26-7613-48cc-a74e-de83df9465a4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: bb1538d484590a19eb7525a1451b5082ebab245d
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506045"
---
# <a name="unenroll-your-android-device-from-management"></a>Uw Android-apparaat uitschrijven bij het beheer  

Verwijder een geregistreerd Android-apparaat zodat het niet meer wordt beheerd door uw organisatie. In dit artikel wordt beschreven hoe u het apparaat verwijdert uit de Bedrijfsportal-app. Na verwijdering van het apparaat zijn de volgende zaken van toepassing:  

* Het apparaat heeft geen toegang meer tot de beveiligde gegevens en resources van uw organisatie.
* Het apparaat wordt niet meer weergegeven in de Bedrijfsportal.
* U kunt geen apps meer installeren vanuit de Bedrijfsportal.
* Instellingen die op het apparaat zijn gewijzigd toen u dit hebt toegevoegd (bijvoorbeeld het uitschakelen van de camera of een vereiste wachtwoordlengte), zijn niet meer van toepassing.  

> [!NOTE]
> U kunt de registratie of het apparaat van het bedrijf niet verwijderen uit de Microsoft Intune-app. Het apparaat is geregistreerd tijdens de eerste installatie van het apparaat en moet worden geregistreerd om toegang te krijgen tot de resources van uw organisatie.  

1. Ga in de Bedrijfsportal naar de rechterbovenhoek en tik op de drie verticale puntjes. Het actiemenu wordt geopend.

   ![Een schermopname van de Android-bedrijfsportal-app met in de rechterbovenhoek het geopende actiemenu. De nieuwe optie Bedrijfsportal verwijderen is als derde optie beschikbaar, onder Mijn profiel en Instellingen, en boven Voorwaarden en bepalingen, Help en feedback en Over.](./media/android_remove_cp_menu_action_after_1705.png)

2. Tik op **Bedrijfsportal verwijderen**.  

3. Er wordt een bericht weergegeven met informatie over wat er gebeurt nadat u uw apparaat hebt uitgeschreven. Tik op **OK** om te bevestigen dat u het apparaat uit de Bedrijfsportal wilt verwijderen.

   ![Een schermopname van de bevestiging die beschikbaar is nadat u de nieuwe optie Bedrijfsportal verwijderen hebt geselecteerd in het actiemenu.](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="remove-data-collected-by-the-company-portal-app"></a>Gegevens verwijderen die door de bedrijfsportal-app zijn verzameld  

U kunt als volgt alle gegevens verwijderen die de bedrijfsportal-app voor Android op uw apparaat opslaat:

- Wis de appgegevens door op **Toepassingen** > **[*naam van de app*]**  > **Gegevens wissen** te tikken.
- Verwijder de volgende map: \storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal.

## <a name="uninstall-the-company-portal-app"></a>De Bedrijfsportal-app verwijderen

Bedrijfsportal is een app voor apparaatbeheer. Deze kan niet worden verwijderd voordat u uw apparaat bij het beheer hebt uitgeschreven. Nadat u dit hebt gedaan, tikt u op het pictogram van de Bedrijfsportal-app en houdt u dit ingedrukt totdat **Verwijderen** wordt weergegeven. Tik op **Verwijderen** om de app van uw apparaat te verwijderen.  

U kunt ook op **Instellingen** > **Apps** > **Bedrijfsportal** > **Verwijderen** tikken.  

### <a name="remove-the-company-portal-app-as-a-device-administrator"></a>De Bedrijfsportal-app verwijderen als apparaatbeheerder

Als laatste redmiddel kunt u de app als apparaatbeheerder van uw apparaat verwijderen.  

Als u een apparaat hebt waarvan het bedrijf de eigenaar is, kan uw organisatie mogelijk verplichten Bedrijfsportal te allen tijden op uw apparaat te houden. Als u deze app verwijdert, kan u de toegang tot beschermde bedrijfsresources worden ontzegd, zoals e-mail, apps, Wi-Fi of VPN, tot u de app opnieuw installeert. Zie [Apps toevoegen aan Microsoft Intune](/intune/apps/apps-add#apps-that-are-added-automatically-by-intune) voor meer informatie over het installeren, bijwerken of verwijderen van vereiste apps.

U kunt de Bedrijfsportal als apparaatbeheerder als volgt uitschakelen. De daadwerkelijke naam van elke instelling kan afwijken op uw Android-apparaat.  

**Optie 1**:  

1. Selecteer **Instellingen** > **Beveiliging** > **Aanvullende beveiligingsinstellingen** > **Apparaatbeheerders**.  
2. Wis de selectie **Bedrijfsportal**.  

**Optie 2**:

1. Selecteer **Instellingen** > **Schermvergrendeling en beveiliging** > **Andere beveiligingsinstellingen** > **Apps voor apparaatbeheer**.
2. Wis de selectie **Bedrijfsportal**.

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Controleer of de contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).
