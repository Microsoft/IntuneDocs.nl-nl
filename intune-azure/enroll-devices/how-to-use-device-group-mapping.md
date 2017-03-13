---
title: "Apparaatcategorieën in Intune gebruiken"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: in dit onderwerp vindt u informatie over het gebruik van apparaatcategorieën die gebruikers kunnen kiezen wanneer ze hun apparaten registreren bij Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: c635ced382074f7f45254fb219b58f54b56abb8e
ms.lasthandoff: 02/18/2017


---

# <a name="map-device-groups"></a>Apparaatgroepen toewijzen


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Gebruik apparaatcategorieën van Microsoft Intune om apparaten automatisch aan groepen toe te voegen op basis van categorieën die u definieert, zodat het voor u eenvoudiger wordt om die apparaten te beheren.

Voor apparaatcategorieën wordt de volgende werkstroom gebruikt:
1.    Categorieën maken die gebruikers kunnen kiezen bij het registreren van hun apparaat
4.    Wanneer eindgebruikers hun apparaat registreren, moeten ze een categorie kiezen uit de lijst met categorieën die u hebt geconfigureerd. Als een apparaat al is geregistreerd, wordt de eindgebruiker gevraagd een categorie te selecteren wanneer hij of zij de bedrijfsportal-app opnieuw opent.


U kunt alle apparaatcategorieën maken die u maar wilt, bijvoorbeeld:
- Verkooppuntapparaat
- Demonstratieapparaat
- Sales
- Boekhouding
- Manager

## <a name="how-to-configure-device-categories"></a>Apparaatcategorieën configureren

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>Stap 1: apparaatcategorieën maken op de blade Intune in Azure Portal
1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Apparaten inschrijven** op de blade **Intune**.
3. Kies **Apparaatcategorieën** op de blade **Inschrijving**.
4. Kies **Maken** op de pagina **Apparaatcategorieën** om een nieuwe categorie toe te voegen.
5. Voer op de volgende blade een **naam** in voor de nieuwe categorie en voer desgewenst een **beschrijving** in.
6. Wanneer u klaar bent, klikt u op **Maken**. In de lijst met categorieën ziet u de categorie die u zojuist hebt gemaakt.

Als u Azure Active Directory-beveiligingsgroepen maakt in stap 2, gebruikt u de naam van de apparaatcategorie.

### <a name="step-2---create-azure-active-directory-security-groups"></a>Stap 2: Active Directory-beveiligingsgroepen maken
In deze stap maakt u dynamische groepen in Azure Portal op basis van de apparaatcategorie en de naam van de apparaatcategorie.

Zie het onderwerp [Geavanceerde regels maken met kenmerken](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) in de documentatie van Azure Active Directory om door te gaan. 

Gebruik de informatie in deze sectie om een apparaatgroep met een geavanceerde regel te maken op basis van het kenmerk **deviceCategory** (apparaatcategorie). Bijvoorbeeld: (**device.deviceCategory -eq** "*<the device category name you got from the Intune portal>*")

Wanneer u apparaatgroepen hebt geconfigureerd en gebruikers hun apparaat registreren, krijgen ze een lijst te zien met de categorieën die u hebt geconfigureerd. Wanneer ze een categorie hebben gekozen en de inschrijving voltooien, wordt hun apparaat toegevoegd aan de Active Directory-beveiligingsgroep die overeenkomt met de gekozen categorie.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>De apparaatcategorieën weergeven die u beheert

1.    Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies op de blade Intune van Azure Portal **Apparaten en groepen**.

3.    Klik onder **Beheren** op **Alle apparaten**.

4.    Bekijk de kolom **Categorie** in de lijst met apparaten.

Als de kolom **Categorie** niet wordt weergegeven, klikt u op **Kolommen**, kiest u **Categorie** in de lijst en klikt u vervolgens op **Toepassen**.

### <a name="to-change-the-category-of-a-device"></a>De categorie van een apparaat wijzigen

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Apparaten en groepen** op de blade **Intune**.
4. Kies **Beheren** > **Alle apparaten** op de blade **Apparaten en groepen**.
5. Kies het gewenste apparaat in de lijst met apparaten en kies **Beheren** > **Eigenschappen** op de blade Apparaateigenschappen.
6. Op de volgende blade kunt u de **apparaatcategorie** van het geselecteerde apparaat wijzigen in een van de categorienamen die u eerder hebt geconfigureerd.



## <a name="further-information"></a>Meer informatie
- U kunt een apparaatcategorie bewerken in Azure Portal. Als u dit doet, moet u de Azure Active Directory-beveiligingsgroepen die naar deze categorie verwijzen, handmatig bijwerken.

- Als u een categorie verwijdert, wordt voor de apparaten die aan de categorie zijn toegewezen de categorienaam **Niet-toegewezen** weergegeven.



