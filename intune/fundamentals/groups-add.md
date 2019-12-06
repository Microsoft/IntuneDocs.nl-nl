---
title: Groepen toevoegen om gebruikers en apparaten in te delen
titleSuffix: Microsoft Intune
description: Voeg groepen toe om gebruikers en apparaten in te delen op basis van geografie, afdeling of hardwarespecificaties.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: altsou
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6e3219e32ef9bea838f0c19258d0b22a99083a12
ms.sourcegitcommit: 1a22b8b31424847d3c86590f00f56c5bc3de2eb5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/21/2019
ms.locfileid: "74261580"
---
# <a name="add-groups-to-organize-users-and-devices"></a>Groepen toevoegen om gebruikers en apparaten in te delen

Intune maakt gebruik van Azure AD-groepen (Azure Active Directory) voor het beheren van apparaten en gebruikers. Als beheerder van Intune kunt u groepen instellen die aansluiten bij de behoeften van uw organisatie. Maak groepen om gebruikers of apparaten in te delen op geografische locatie, afdeling of hardwarekenmerken. Gebruik groepen voor het beheren van taken op schaal. U kunt zo bijvoorbeeld beleidsregels instellen voor een groot aantal gebruikers tegelijk of apps implementeren op een reeks apparaten.

U kunt de volgende typen groepen toevoegen:

- **Toegewezen groepen**: voeg handmatig gebruikers of apparaten toe aan een statische groep. 
- **Dynamische groepen** (vereist Azure AD Premium): voeg automatisch gebruikers of apparaten toe aan gebruikersgroepen of apparaatgroepen op basis van een expressie die u maakt.

  Wanneer een gebruiker bijvoorbeeld wordt toegevoegd met de titel van manager, wordt die gebruiker automatisch toegevoegd aan een gebruikersgroep **Alle managers**. Of, wanneer een apparaat het besturingssysteemtype iOS-apparaat heeft, wordt het apparaat automatisch toegevoegd aan een apparaatgroep **Alle iOS-apparaten**.

## <a name="add-a-new-group"></a>Een nieuwe groep toevoegen

Volg de onderstaande stappen om een nieuwe groep te maken.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Groepen** > **Nieuwe groep**:

   ![Schermopname van de Azure-portal met de optie Nieuwe groep geselecteerd](./media/groups-add/groups-add-new.png)

3. Kies bij **Groepstype** een van de volgende opties:

    - **Beveiliging**: met beveiligingsgroepen kunt u bepalen wie toegang heeft tot resources. Deze optie wordt aanbevolen voor uw groepen in Intune. U kunt bijvoorbeeld groepen maken voor gebruikers, zoals **Alle gebruikers in Zaandam** of **Alle vrouwen bij Contoso**. U kunt ook groepen maken voor apparaten, zoals **Alle iOS-apparaten** of **Alle apparaten van studenten met Windows 10**.

        > [!TIP]
        > De gebruikers en groepen die zijn gemaakt, kunnen ook worden weergegeven in het [Microsoft 365-beheercentrum](https://admin.microsoft.com), het Azure Active Directory-beheercentrum en in [Microsoft Intune in de Azure-portal](https://go.microsoft.com/fwlink/?linkid=2090973). In de tenant van uw organisatie kunt u in al deze gebieden groepen maken en beheren.
        >
        > Als uw primaire rol apparaatbeheer is, raden we u aan het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) te gebruiken.

    - **Office 365**: deze groepen zijn ontworpen om de toegang tot Office 365-resources te beheren en te delen. U kunt bijvoorbeeld een Office 365-groep maken om een Postvak IN of agenda in Outlook-te delen. Zie [Over Office 365-groepen](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) voor meer informatie.

4. Voer een **naam** en **beschrijving** in voor de nieuwe groep. Wees specifiek en voeg informatie toe, zodat anderen weten waar de groep voor dient.

    Geef bijvoorbeeld **Alle apparaten van studenten met Windows 10** in als groepsnaam en **Alle apparaten met Windows 10 van scholieren op de middelbare scholen in Zaandam in de klassen 4-6** in als groepsbeschrijving.

5. Voer het **lidmaatschapstype** in. Uw opties zijn:

    - **Toegewezen**: beheerders wijzen gebruikers of apparaten handmatig toe aan deze groep en verwijderen handmatig gebruikers of apparaten.
    - **Dynamische gebruiker**: beheerders maken lidmaatschapsregels om leden automatisch toe te voegen en te verwijderen.
    - **Dynamisch apparaat**: beheerders maken dynamische groepsregels om apparaten automatisch toe te voegen en te verwijderen.

        ![Schermafbeelding van Intune-groepseigenschappen](./media/groups-add/groups-add-properties.png)

    Voor meer informatie over deze lidmaatschapstypen en het maken van dynamische expressies raadpleegt u:

    - [Een basisgroep maken en leden toevoegen met Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    - [Dynamische lidmaatschapsregels voor groepen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)

    > [!NOTE]
    > Wanneer u in dit beheercentrum gebruikers of groepen maakt, krijgt u mogelijk niet de **Azure Active Directory**-huisstijl te zien. Maar dat is wel wat er wordt gebruikt.

6. Kies **Maken** om de nieuwe groep toe te voegen. U groep wordt in de lijst weergegeven.

> [!TIP]
> Overweeg ook om een van de andere dynamische gebruikers- en apparaatgroepen te gebruiken die u kunt maken, zoals:
>
> - Alle scholieren op de middelbare scholen in Zaandam
> - Alle Android Enterprise-apparaten
> - Alle iOS 11- en oudere apparaten
> - Marketing
> - Human Resources
> - Alle medewerkers in Zaandam
> - Alle medewerkers in NH

## <a name="groups-and-policies"></a>Groepen en beleidsregels

Toegang tot de resources van uw organisatie wordt beheerd door gebruikers en groepen die u maakt.

Als u groepen maakt, kunt u overwegen om [nalevingsbeleid](../protect/device-compliance-get-started.md) en [configuratieprofielen](../configuration/device-profiles.md) te gebruiken. U kunt bijvoorbeeld het volgende hebben:

- Beleidsregels die specifiek zijn voor een besturingssysteem van een apparaat.
- Beleidsregels die specifiek zijn voor verschillende rollen in uw organisatie.
- Beleidsregels die specifiek zijn voor organisatie-eenheden die u hebt gedefinieerd in Active Directory.

U kunt een standaardbeleid maken dat van toepassing is op alle groepen en apparaten, als u de basisvereisten voor naleving binnen uw organisatie wilt maken. Maak vervolgens een specifieker beleid voor de meest uiteenlopende categorieën gebruikers en apparaten. U kunt bijvoorbeeld een e-mailbeleid maken voor elk apparaatbesturingssysteem.

Zie [Beleid toewijzen aan gebruikersgroepen of apparaatgroepen](../configuration/device-profile-assign.md#user-groups-vs-device-groups) en [profielaanbevelingen](../configuration/device-profile-create.md#recommendations) voor aanbevelingen en richtlijnen voor configuratieprofielen.

## <a name="see-also"></a>Zie tevens

- [Op rollen gebaseerd toegangsbeheer (RBAC) met Microsoft Intune](role-based-access-control.md)
- [Toegang tot resources beheren met Azure AD-groepen](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
