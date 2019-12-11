---
title: Klassieke Intune-groepen in Azure Portal
titleSuffix: Microsoft Intune
description: Maak kennis met de nieuwe functies voor groepen in Microsoft Intune Azure Portal.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/31/2019
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 323f384d-8a76-4adc-999b-e508d641bfa1
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0cf8e136b3ef5c3d4329e075af4c180423d74a15
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72502840"
---
# <a name="microsoft-intune-classic-groups-in-the-azure-portal"></a>Klassieke Microsoft Intune-groepen in Azure Portal

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

We hebben op basis van uw feedback wijzigingen doorgevoerd in de wijze waarop u werkt met groepen in Microsoft Intune.
Als u Intune via Azure Portal gebruikt, zijn uw Intune-groepen naar de Azure Active Directory-beveiligingsgroepen gemigreerd.

Het voordeel voor u is dat u nu in al uw Enterprise Mobility + Security- en Azure AD-apps op dezelfde manier met groepen kunt werken. Bovendien kunt u PowerShell en Graph API gebruiken om deze nieuwe functionaliteit uit te breiden en aan te passen.

Azure AD-beveiligingsgroepen ondersteunen alle typen Intune-implementaties voor zowel gebruikers als apparaten. Daarnaast kunt u gebruikmaken van dynamische Azure AD-groepen die automatisch worden bijgewerkt op basis van de kenmerken die u verstrekt. U kunt bijvoorbeeld een groep apparaten maken die werken met iOS 9. Wanneer een apparaat met iOS 9 wordt ingeschreven, verschijnt het apparaat automatisch in de dynamische groep.

## <a name="what-is-not-available"></a>Welke functies zijn niet beschikbaar?

Sommige functies voor Intune-groepen die u mogelijk eerder hebt gebruikt, zijn niet beschikbaar in Azure AD:

- De Intune-groepen **Niet-gegroepeerde gebruikers** en **Niet-gegroepeerde apparaten** zijn niet meer beschikbaar.
- De optie **Specifieke leden uitsluiten** van een groep bestaat niet in Azure Portal. U kunt echter een Azure AD-beveiligingsgroep met geavanceerde regels gebruiken om dit gedrag te repliceren. U kunt bijvoorbeeld een geavanceerde regel maken waarmee u alle personen van de afdeling Verkoop opneemt in een beveiligingsgroep, behalve degenen waarbij het woord 'assistent' in hun titel voorkomt. Deze geavanceerde regel ziet er als volgt uit:

  `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- De groep **Alle door Exchange ActiveSync beheerde apparaten** in de klassieke Intune-console is niet gemigreerd naar Azure AD. U hebt echter nog altijd toegang tot informatie over met EAS beheerde apparaten via Azure Portal.

## <a name="how-to-get-started"></a>Aan de slag

- Lees de volgende onderwerpen voor informatie over Azure AD-beveiligingsgroepen en hoe deze werken:
  - [Toegang tot resources beheren met Azure Active Directory-groepen](https://azure.microsoft.com/documentation/articles/active-directory-manage-groups/).
  - [Groepen beheren in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/).
  - [Geavanceerde regels maken met kenmerken](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
- Zorg ervoor dat beheerders die groepen moeten maken, worden toegevoegd aan de Azure AD-rol **Intune-servicebeheerder**. De rol Servicebeheerder van Azure AD heeft geen **Groep beheren**-machtigingen.
- Als uw Intune-groepen de optie **Specifieke leden uitsluiten** hebben gebruikt, beslist u of u deze groepen opnieuw kunt vormgeven zonder uitsluitingen of dat u geavanceerde regels nodig hebt om aan bedrijfsbehoeften te voldoen.


## <a name="what-happened-to-intune-groups"></a>Wat is er gebeurd met Intune-groepen?
Wanneer groepen worden gemigreerd van de Azure-portal naar Intune in Azure Portal, worden de volgende regels toegepast:

| Groepen in Intune|Groepen in Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Statische gebruikersgroep|Statische Azure AD-beveiligingsgroep|
|Dynamische gebruikersgroep|Statische Azure AD-beveiligingsgroepen met een Azure AD-beveiligingsgroepshiërarchie|
|Statische apparaatgroep|Statische Azure AD-beveiligingsgroep|
|Dynamische apparaatgroep|Dynamische Azure AD-beveiligingsgroep|
|Een groep met een voorwaarde voor opneming|Statische Azure AD-beveiligingsgroep met statische of dynamische leden op basis van de insluitingsvoorwaarde in Intune|
|Een groep met een uitsluitingsvoorwaarde|Niet gemigreerd|
|De ingebouwde groepen:<br>- **Alle gebruikers**<br>- **Niet-gegroepeerde gebruikers**<br>- **Alle apparaten**<br>- **Niet-gegroepeerde apparaten**<br>- **Alle computers**<br>- **Alle mobiele apparaten**<br>- **Alle door MDM beheerde apparaten**<br>- **Alle door EAS beheerde apparaten**|Azure AD-beveiligingsgroepen|

## <a name="group-hierarchy"></a>Groepshiërarchie

In de Intune-console hadden alle groepen een bovenliggende groep. Groepen konden alleen leden van de bovenliggende groep bevatten. Onderliggende groepen in Azure AD kunnen leden bevatten die niet in de bovenliggende groep zijn opgenomen.

## <a name="group-attributes"></a>Groepskenmerken
Kenmerken zijn eigenschappen van apparaten die kunnen worden gebruikt om groepen te definiëren. Deze tabel bevat een beschrijving van hoe deze criteria worden gemigreerd naar Azure AD-beveiligingsgroepen.

| Kenmerk in Intune|Kenmerk in Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|OE-kenmerk (organisatie-eenheid) voor apparaatgroepen|OE-kenmerk voor dynamische groepen.|
|Domeinnaamkenmerk voor apparaatgroepen|Domeinnaamkenmerk voor dynamische groepen.|
|Beveiligingsgroep als een kenmerk voor gebruikersgroepen|Groepen kunnen geen kenmerken zijn van dynamische query's in Azure AD. Dynamische groepen kunnen alleen kenmerken bevatten die specifiek zijn voor een gebruiker of apparaat.|
|Kenmerk manager voor gebruikersgroepen|Geavanceerde regel voor kenmerk *manager* in dynamische groepen|
|Alle gebruikers van de bovenliggende gebruikersgroep|Statische groep met die groep als een lid|
|Alle mobiele apparaten uit de bovenliggende apparaatgroep|Statische groep met die groep als een lid|
|Alle mobiele apparaten die worden beheerd met Intune|Kenmerk beheertype met 'MDM' als waarde voor dynamische groep|
|Geneste groepen binnen statische groepen |Geneste groepen binnen statische groepen|
|Geneste groepen binnen dynamische groepen|Dynamische groep met één genest niveau|

## <a name="what-happens-to-policies-and-apps-you-previously-deployed"></a>Wat gebeurt er met beleidsregels en apps die u eerder hebt geïmplementeerd?

Beleid en apps blijven gewoon geïmplementeerd voor groepen, net als voorheen. U beheert deze groepen nu echter via Azure Portal en niet meer via de Intune-console.
