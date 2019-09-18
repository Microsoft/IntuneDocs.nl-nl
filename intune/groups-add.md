---
title: Groepen toevoegen om gebruikers en apparaten in te delen
titleSuffix: Microsoft Intune
description: Voeg groepen toe om gebruikers en apparaten in te delen op basis van geografie, afdeling of hardwarespecificaties.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/13/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: altsou
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bab0a33eee5f4d4856fb9d01d822236d1927a4e3
ms.sourcegitcommit: 74911a263944f2dbd9b754415ccda6c68dae0759
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2019
ms.locfileid: "71071731"
---
# <a name="add-groups-to-organize-users-and-devices"></a>Groepen toevoegen om gebruikers en apparaten in te delen
Intune maakt gebruik van Azure AD-groepen (Active Directory) voor het beheren van apparaten en gebruikers. Als beheerder van Intune kunt u groepen instellen die aansluiten bij de behoeften van uw organisatie. Maak groepen om gebruikers of apparaten in te delen op geografische locatie, afdeling of hardwarekenmerken. Gebruik groepen voor het beheren van taken op schaal. U kunt zo bijvoorbeeld beleidsregels instellen voor een groot aantal gebruikers tegelijk of apps implementeren op een reeks apparaten.

U kunt de volgende typen groepen toevoegen:
- **Toegewezen groepen**: voeg handmatig gebruikers of apparaten toe aan een statische groep
- **Dynamische groepen**: (met Azure Active Directory Premium) hiermee kunt u dynamisch gebruikers- of apparaatgroepen maken aan de hand van eenvoudige of geavanceerde regels

## <a name="add-a-new-group"></a>Een nieuwe groep toevoegen

Volg de onderstaande stappen om een nieuwe groep te maken.
1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. In het deelvenster **Intune** kiest u **Groepen**. Kies vervolgens **Nieuwe groep** in het deelvenster **Alle groepen**.
   ![Schermafbeelding van de Azure-portal met de optie Nieuwe groep geselecteerd](./media/groups-add-new.png)
4. Kies voor **Groepstype** een van de volgende opties:
    - **Beveiliging**: Beveiligingsgroepen zijn een goede bron voor het vullen van gebruikersgroepen. Aangezien in beveiligingsgroepen is gedefinieerd wie toegang heeft tot bronnen, kunnen beveiligingsgroepen goed worden gebruikt als basis voor Intune-gebruikersgroepen. U kunt beveiligingsgroepen die vanuit Active Directory worden gesynchroniseerd met Azure Active Directory of die u rechtstreeks in Azure Active Directory maakt via het Microsoft 365-beheercentrum of Azure Portal, gebruiken wanneer u gebruikersgroepen in Intune maakt.
    - **Office 365**

5. Voer een **naam** en **beschrijving** in voor de nieuwe groep. Deze eigenschappen worden alleen weergegeven in de beheerportal en zijn niet zichtbaar voor gebruikers.

6. Kies een waarde voor **Type lidmaatschap**:
   - **Toegewezen**: om een groep te maken met handmatig toegewezen leden. Lees hier meer over [toegewezen groepen van Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
   - **Dynamische gebruiker**: om een gebruikersgroep te maken op basis van een **dynamische query**.
   - **Dynamisch apparaat**: om een apparaatgroep te maken op basis van een **dynamische query**.

   ![Schermafbeelding van Intune-groepseigenschappen](./media/groups-add-properties.png)

   In Azure AD kunt u dynamische groepen maken op basis van regels die het lidmaatschap definiëren. Lees hier meer over het [maken van dynamische groepen op basis van kenmerken](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

7. Selecteer **Office-functies inschakelen** om leden van de gebruikersgroep toegang te geven tot gedeelde Office 365-apps. Meer informatie over [Office 365 Groepen](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).
8. Kies **Maken** om de nieuwe groep toe te voegen.

## <a name="groups-and-policies"></a>Groepen en beleidsregels

Denk bij het maken van groepen goed na over hoe u [beleidsregels](device-compliance-get-started.md) toepast. U kunt bijvoorbeeld beleidsregels gebruiken die specifiek zijn voor besturingssystemen van apparaten en beleidsregels die specifiek zijn voor verschillende rollen in uw organisatie of voor organisatie-eenheden die u al hebt opgegeven in Active Directory. Het kan nuttig zijn om aparte apparaatgroepen voor iOS, Android en Windows en gebruikersgroepen voor elke organisatierol te hebben.

U wilt waarschijnlijk ook een standaardbeleid maken dat van toepassing is op alle groepen en apparaten, om de basisvereisten voor naleving binnen uw organisatie vast te leggen. Vervolgens kunt u een specifieker beleid maken voor de meest uiteenlopende categorieën gebruikers en apparaten. U kunt bijvoorbeeld een e-mailbeleid maken voor elk apparaatbesturingssysteem.



## <a name="see-also"></a>Zie tevens
- [Toegang tot resources beheren met Azure Active Directory-groepen](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Klassieke Intune-groepen in Azure Portal](groups-get-started.md)
