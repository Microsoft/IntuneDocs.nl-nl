---
title: Migreren naar Azure Active Directory-groepen
description: Hoe uw groepen worden gemigreerd van Intune naar Azure AD
keywords: 
author: arob98
ms.author: angrobe
manager: angerobe
ms.date: 12/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 03b69afa-3548-4033-9039-191528f3fd99
ms.custom: intune-classic
ms.openlocfilehash: 3a71f2dc4507d59ea3c11fa034340b5e8535c3c4
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/15/2017
---
# <a name="a-new-way-of-using-groups-in-intune"></a>Een nieuwe manier om groepen in Intune te gebruiken

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

We hebben op basis van uw feedback enkele wijzigingen doorgevoerd in de wijze waarop u werkt met groepen in Microsoft Intune.
We zijn bezig met het migreren van de Intune-groepen van al onze klanten naar Azure Active Directory-beveiligingsgroepen.

Het voordeel voor u is dat u nu in al uw Enterprise Mobility + Security- en Azure AD-apps op dezelfde manier met groepen kunt werken. Bovendien kunt u gebruikmaken van PowerShell en Graph API om deze nieuwe functionaliteit uit te breiden en aan te passen.

Azure AD-beveiligingsgroepen ondersteunen alle typen Intune-implementaties voor zowel gebruikers als apparaten. Daarnaast kunt u gebruikmaken van dynamische Azure AD-groepen die automatisch worden bijgewerkt op basis van de kenmerken die u verstrekt. U kunt bijvoorbeeld een groep apparaten maken die werken met iOS 9. Wanneer een nieuw apparaat met iOS 9 wordt geregistreerd, wordt dat automatisch aan de dynamische groep toegevoegd.

## <a name="when-is-this-happening"></a>Wanneer vindt dat plaats?

Het migratieproces is al in gang gezet. U krijgt een bericht voordat we u gaan migreren.
Als u al bent gemigreerd, ziet u een bericht dat lijkt op dit wanneer u toegang probeert te krijgen tot groepen vanuit de klassieke Intune-console:

![Bericht dat laat zien dat er groepen zijn gemigreerd.](http://i.imgur.com/72KRaXj.png)

## <a name="what-wont-be-available"></a>Wat is er niet beschikbaar?

Sommige bestaande mogelijkheden van Intune-groepen zijn niet beschikbaar in Azure AD:

- De Intune-groepen **Niet-gegroepeerde gebruikers** en **Niet-gegroepeerde apparaten** worden niet gemigreerd.
- De optie **Specifieke leden uitsluiten** die wordt toegepast op een groep die al in de Intune-console aanwezig is, bestaat niet in de Azure-portal. U kunt echter een Azure AD-beveiligingsgroep met geavanceerde regels gebruiken om dit gedrag te repliceren. U kunt bijvoorbeeld een geavanceerde regel maken waarmee u alle personen op de afdeling Verkoop opneemt in een beveiligingsgroep, behalve degenen waarbij het woord 'assistent' in hun titel voorkomt. Die geavanceerde regel ziet er als volgt uit: `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- De groep **Alle door Exchange ActiveSync beheerde apparaten** die is ingebouwd in de Intune-console, wordt niet gemigreerd naar Azure AD. U hebt echter nog altijd toegang tot informatie over met EAS beheerde apparaten via de Azure-portal.
- Het is niet mogelijk om rapporten te filteren op groepen in de klassieke Intune-console.
<!--- - Custom group targeting of notification rules will not be available. ROB I took this out as I couldn't replicate the behavior. --->

## <a name="how-to-get-ready"></a>Hoe bereidt u zich voor

- Lees de volgende Azure AD-onderwerpen voor informatie over Azure AD-beveiligingsgroepen en hoe deze werken:
    -  [Toegang tot resources beheren met Azure Active Directory-groepen](https://azure.microsoft.com/documentation/articles/active-directory-manage-groups/).
    -  [Groepen beheren in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/).
    -  [Geavanceerde regels maken met kenmerken](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
- Overweeg het verwijderen van Intune-groepen die u niet meer gebruikt voordat u migreert.
-  Zorg ervoor dat alle beheerders die groepen moeten maken, worden toegevoegd aan de Azure AD-rol **Intune-servicebeheerder**. Houd er rekening mee dat de rol Servicebeheerder van Azure AD geen **Groep beheren**-machtigingen heeft.
-  Als u gebruikmaakt van groepen met de optie **Specifieke leden uitsluiten**, overweeg dan om deze groepen zodanig in te stellen dat ze geen gebruikmaken van uitsluitingen of om geavanceerde regels in uw Azure AD-query toe te passen om hetzelfde resultaat te verkrijgen.


## <a name="what-happens-to-intune-groups"></a>Wat gebeurt er met Intune-groepen?

| Groepen in Intune|Groep in Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Statische gebruikersgroep|Statische Azure AD-beveiligingsgroep|
|Dynamische gebruikersgroep|Statische Azure AD-beveiligingsgroepen met een Azure AD-beveiligingsgroepshiërarchie|
|Statische apparaatgroep|Statische Azure AD-beveiligingsgroep|
|Dynamische apparaatgroep|Dynamische Azure AD-beveiligingsgroep|
|Een groep met een voorwaarde voor opneming|Statische Azure AD-beveiligingsgroep met statische of dynamische leden op basis van de insluitingsvoorwaarde in Intune.|
|Een groep met een uitsluitingsvoorwaarde|Niet gemigreerd|
|De ingebouwde groepen **Alle gebruikers**, **Niet-gegroepeerde gebruikers**, **Alle apparaten**, **Niet-gegroepeerde apparaten**, **Alle computers**, **Alle mobiele apparaten**, **Alle met MDM-beheerde apparaten** en **Alle met EAS beheerde apparaten**|Azure AD-beveiligingsgroepen.|

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

## <a name="what-happens-to-policies-and-apps-youve-already-deployed"></a>Wat gebeurt er met beleidsregels en apps die u al hebt geïmplementeerd?

Beleid en apps blijven gewoon geïmplementeerd voor groepen, net als voorheen. U beheert deze groepen nu echter via de Azure-portal en niet meer via de klassieke Intune-console.
 
