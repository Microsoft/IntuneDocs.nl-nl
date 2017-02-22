---
title: Aan de slag met groepen in de preview-versie van Intune Azure Portal | Microsoft Docs
description: Nieuwe functies voor groepen in preview-versie van Intune Azure Portal
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 01/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 323f384d-8a76-4adc-999b-e508d641bfa1
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 27a9c9d8269b302fa9735972056d38e7919f42b5


---

# <a name="get-started-with-groups"></a>Aan de slag met groepen

[!INCLUDE[azure preview](../includes/azure_preview.md)]

We hebben op basis van uw feedback wijzigingen doorgevoerd in de wijze waarop u werkt met groepen in Microsoft Intune.
Als u Intune via Azure Portal gebruikt, zijn uw Intune-groepen naar de Azure Active Directory-beveiligingsgroepen gemigreerd.

Het voordeel voor u is dat u nu in al uw Enterprise Mobility + Security- en Azure AD-apps op dezelfde manier met groepen kunt werken. Bovendien kunt u gebruikmaken van PowerShell en Graph API om deze nieuwe functionaliteit uit te breiden en aan te passen.

Azure AD-beveiligingsgroepen ondersteunen alle typen Intune-implementaties voor zowel gebruikers als apparaten. Daarnaast kunt u gebruikmaken van dynamische Azure AD-groepen die automatisch worden bijgewerkt op basis van de kenmerken die u verstrekt. U kunt bijvoorbeeld een groep apparaten maken die werken met iOS 9. Wanneer een nieuw apparaat met iOS 9 wordt geregistreerd, wordt dat automatisch aan de dynamische groep toegevoegd.

## <a name="what-is-not-available"></a>Welke functies zijn niet beschikbaar?

Sommige functies voor Intune-groepen die u mogelijk eerder hebt gebruikt, zijn niet beschikbaar in Azure AD:

- De Intune-groepen **Niet-gegroepeerde gebruikers** en **Niet-gegroepeerde apparaten** zijn niet meer beschikbaar.
- De optie **Specifieke leden uitsluiten** van een groep bestaat niet in Azure Portal. U kunt echter een Azure AD-beveiligingsgroep met geavanceerde regels gebruiken om dit gedrag te repliceren. U kunt bijvoorbeeld een geavanceerde regel maken waarmee u alle personen op de afdeling Verkoop opneemt in een beveiligingsgroep, behalve degenen waarbij het woord 'assistent' in hun titel voorkomt. Die geavanceerde regel ziet er als volgt uit: `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- De groep **Alle door Exchange ActiveSync beheerde apparaten** die is ingebouwd in de Intune-console, is niet gemigreerd naar Azure AD. U hebt echter nog altijd toegang tot informatie over met EAS beheerde apparaten via de Azure-portal.


## <a name="how-to-get-started"></a>Aan de slag

- Lees de volgende Azure AD-onderwerpen voor informatie over Azure AD-beveiligingsgroepen en hoe deze werken:
    -  [Toegang tot resources beheren met Azure Active Directory-groepen](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
    -  [Groepen beheren in Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/).
    -  [Geavanceerde regels maken met kenmerken](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
-  Zorg ervoor dat alle beheerders die groepen moeten maken, worden toegevoegd aan de Azure AD-rol **Intune-servicebeheerder**. Houd er rekening mee dat de rol Servicebeheerder van Azure AD geen **Groep beheren**-machtigingen heeft.
-  Als u gebruikmaakte van groepen met de optie **Specifieke leden uitsluiten**, overweeg dan om deze groepen zodanig in te stellen dat ze geen gebruikmaken van uitsluitingen of om geavanceerde regels in uw Azure AD-query toe te passen om hetzelfde resultaat te verkrijgen.


## <a name="what-happened-to-intune-groups"></a>Wat is er gebeurd met Intune-groepen?

| Groepen in Intune|Groep in Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Statische gebruikersgroep|Statische Azure AD-beveiligingsgroep|
|Dynamische gebruikersgroep|Statische Azure AD-beveiligingsgroepen met een Azure AD-beveiligingsgroepshiërarchie|
|Statische apparaatgroep|Statische Azure AD-beveiligingsgroep|
|Dynamische apparaatgroep|Dynamische Azure AD-beveiligingsgroep|
|Een groep met een voorwaarde voor opneming|Statische Azure AD-beveiligingsgroep met statische of dynamische leden op basis van de insluitingsvoorwaarde in Intune|
|Een groep met een uitsluitingsvoorwaarde|Niet gemigreerd|
|De ingebouwde groepen **Alle gebruikers**, **Niet-gegroepeerde gebruikers**, **Alle apparaten**, **Niet-gegroepeerde apparaten**, **Alle computers**, **Alle mobiele apparaten**, **Alle met MDM-beheerde apparaten** en **Alle met EAS beheerde apparaten**|Azure AD-beveiligingsgroepen|

In Intune moeten alle groepen een bovenliggende groep hebben. Groepen kunnen alleen leden van de bovenliggende groep bevatten. Onderliggende groepen in Azure AD kunnen leden bevatten die niet in de bovenliggende groep zijn opgenomen.

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

Beleid en apps blijven gewoon geïmplementeerd voor groepen, net als voorheen. U beheert deze groepen nu echter via de Azure-portal en niet meer via de klassieke Intune-console.



<!--HONumber=Feb17_HO1-->


