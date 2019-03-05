---
title: Apparaten categoriseren in groepen in Intune
titleSuffix: Microsoft Intune
description: Ontdek hoe u apparaten categoriseert in groepen voor eenvoudiger beheer.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f8c1273a4c458096aef7a16b13c3c76d647ec517
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57232757"
---
# <a name="categorize-devices-into-groups"></a>Apparaten categoriseren in groepen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met apparaatcategorieën van Microsoft Intune kunnen apparaten automatisch worden toegevoegd aan groepen op basis van categorieën die u definieert, zodat het voor u eenvoudiger wordt om die apparaten te beheren.

Voor apparaatcategorieën wordt de volgende werkstroom gebruikt:
1. Maak categorieën die gebruikers kunnen kiezen bij het registreren van hun apparaat.
2. Wanneer gebruikers van iOS- en Android-apparaten een apparaat registreren, moeten ze een categorie kiezen uit de lijst met categorieën die u hebt geconfigureerd. Als u een categorie wilt toewijzen aan een Windows-apparaat, moeten gebruikers de bedrijfsportal-website gebruiken.
3. Vervolgens kunt u beleidsregels en apps implementeren naar deze groepen.

U kunt alle apparaatcategorieën maken die u maar wilt. Bijvoorbeeld:
- Verkooppuntapparaat
- Demonstratieapparaat
- Sales
- Boekhouding
- Manager

## <a name="how-to-configure-device-categories"></a>Apparaatcategorieën configureren

### <a name="step-1-create-device-categories-on-the-intune-blade-of-the-azure-portal"></a>Stap 1: Apparaatcategorieën maken op de blade Intune in Azure Portal
1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving**.
2. Kies **Apparaatcategorieën** op de blade **Apparaatinschrijving**.
3. Kies **Maken** op de pagina **Apparaatcategorieën** om een nieuwe categorie toe te voegen.
4. Voer op de blade **Apparaatcategorie maken** een **Naam** in voor de nieuwe categorie en een optionele **Beschrijving**.
5. Selecteer **Maken** wanneer u klaar bent. De nieuwe categorie wordt weergegeven in de lijst met categorieën.

Als u Azure Active Directory-beveiligingsgroepen (Azure AD) maakt in stap 2, gebruikt u de naam van de apparaatcategorie.

### <a name="step-2-create-azure-active-directory-security-groups"></a>Stap 2: Azure Active Directory-beveiligingsgroepen maken
In deze stap maakt u dynamische groepen in Azure Portal op basis van de apparaatcategorie en de naam van de apparaatcategorie.

Zie [Geavanceerde regels maken met kenmerken](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) in de documentatie van Azure AD om door te gaan.

Gebruik de informatie in deze sectie om een apparaatgroep met een geavanceerde regel te maken op basis van het kenmerk **deviceCategory**. Bijvoorbeeld: (**device.deviceCategory -eq** *de naam van de apparaatcategorie in Azure Portal*.

Wanneer u apparaatgroepen hebt geconfigureerd en gebruikers hun apparaat registreren, krijgen ze een lijst te zien met de categorieën die u hebt geconfigureerd. Wanneer ze een categorie hebben gekozen en de inschrijving voltooien, wordt hun apparaat toegevoegd aan de Active Directory-beveiligingsgroep die overeenkomt met de gekozen categorie.

### <a name="view-the-categories-of-devices-that-you-manage"></a>De apparaatcategorieën weergeven die u beheert

1.  Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaten**.

2.  Klik onder **Beheren** op **Alle apparaten**.

3.  Bekijk de kolom **Apparaatcategorie** in de lijst met apparaten.

Als de kolom **Apparaatcategorie** niet wordt weergegeven, selecteert u **Kolommen**. Kies **Apparaatcategorie** uit de lijst en selecteer vervolgens **Toepassen**.

### <a name="change-the-category-of-a-device"></a>De categorie van een apparaat wijzigen

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaten**.
2. Op de blade **Apparaten** onder de sectie **Beheren** kiest u **Alle apparaten**.
3. Kies het gewenste apparaat in de lijst met apparaten. Kies op de blade met apparaateigenschappen onder de sectie **Beheren** de optie **Eigenschappen**.
4. Op de volgende blade kunt u de **apparaatcategorie** van het geselecteerde apparaat wijzigen in een van de categorienamen die u eerder hebt geconfigureerd.

## <a name="after-you-configure-device-groups"></a>Na het configureren van apparaatgroepen

Wanneer gebruikers van iOS- en Android-apparaten hun apparaat registreren, moeten ze een categorie kiezen uit de lijst met categorieën die u hebt geconfigureerd. Wanneer ze een categorie hebben gekozen en de registratie voltooien, wordt hun apparaat toegevoegd aan de Intune-apparaatgroep of Active Directory-beveiligingsgroep die overeenkomt met de gekozen categorie.

Windows-gebruikers moeten de website van de bedrijfsportal gebruiken om een categorie te selecteren.

Uw gebruikers kunnen bij elk platform altijd naar portal.manage.microsoft.com gaan nadat het apparaat is geregistreerd. Laat de gebruiker naar de bedrijfsportalwebsite en vervolgens **Mijn apparaten** gaan. De gebruiker kan een geregistreerd apparaat op de pagina kiezen en vervolgens een categorie kiezen.

Nadat de categorie is gekozen, wordt het apparaat automatisch toegevoegd aan de bijbehorende groep die u hebt gemaakt. Als een apparaat al is geregistreerd voordat u categorieën configureert, ziet de gebruiker een melding over het apparaat op de bedrijfsportal-website. Hierdoor weten gebruikers dat ze de volgende keer dat ze de bedrijfsportal-app in iOS of Android openen, een categorie moeten selecteren.

## <a name="further-information"></a>Meer informatie
- U kunt een apparaatcategorie bewerken in Azure Portal. U moet de Azure AD-beveiligingsgroepen die naar deze categorie verwijzen dan echter handmatig bijwerken.

- Als u een categorie verwijdert, wordt voor apparaten die aan de categorie zijn toegewezen de categorienaam **Niet-toegewezen** weergegeven.
