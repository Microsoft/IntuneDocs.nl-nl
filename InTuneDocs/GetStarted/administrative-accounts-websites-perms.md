---
title: Beheerdersaccounts, websites en machtigingen | Microsoft Intune
description: beheerdersaccounts machtigingen websites
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db3075e7-38fd-4dfe-b266-26aed10ac8ea
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0c1e08cc49d75303f6793894e3c8a040f6e7a8b1
ms.openlocfilehash: 29d6f9cd31e6fbf287ae30fb2171bf752ff71157


---

# Beheerdersaccounts, websites en machtigingen in Microsoft Intune

Lees dit onderwerp en andere vereisten in [Wat u moet weten voordat u met Microsoft Intune aan de slag gaat](what-to-know-before-you-start-microsoft-intune.md) voordat u Microsoft Intune instelt.

Voor het beheer van Intune moet u het volgende gebruiken:
- Twee typen beheerdersaccounts
- Gebruikersaccounts met aanvullende machtigingen
- Twee webbeheerconsoles/portals om uw beheerders toegang te verlenen tot de zaken die moeten worden beheerd.

In de volgende gedeelten worden deze accounts en portals uitgelegd.

## Beheerdersaccounts en gebruikersaccounts met speciale machtigingen

Hieronder vindt u de accounts en machtigingen die u voor Intune gebruikt.

### Tenantbeheerder
|Machtigingsniveaus|Meer informatie|
|--------------------------|-------------------------|
|Aan tenantbeheerders is één beheerdersrol toegewezen waarmee het beheerbereik voor die gebruiker en de te beheren taken zijn gedefinieerd.<br /><br />De beheerdersrollen voor de verschillende Microsoft-cloudservices komen overeen, hoewel bepaalde rollen door sommige services mogelijk niet worden ondersteund.<br /><br /> In Microsoft Intune worden de volgende rollen gebruikt:<br /><br />- Algemeen beheerder<br />- Financieel medewerker<br />- Wachtwoordbeheerder<br />- Serviceondersteuningsbeheerder<br />- Gebruikerstoegangbeheerder|Het account dat u gebruikt om uw Microsoft Intune-abonnement te maken, is standaard een tenantbeheerder met de rol Algemeen beheerder.<br /></br>  Als tenantbeheerder gebruikt u de [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] om uw abonnement voor [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] te beheren en om tenantbeheerders toe te wijzen vanuit de [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Gebruik een tenantbeheerder met de rol voor algemeen beheer voor toegang tot de [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] om uw eerste servicebeheerder toe te wijzen. Gebruik een tenantbeheerder bij voorkeur niet voor dagelijkse beheertaken. Een tenantbeheerder heeft geen licentie voor [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] nodig om toegang tot de [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)] te krijgen.<br /><br />De tenantbeheerder is een algemeen concept in Microsoft-cloudservices. Wanneer u zich abonneert op [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], is uw service een tenant van Microsoft Azure AD. Zie het gedeelte Azure AD-tenant in [Wat is een Azure AD-adreslijst?](http://technet.microsoft.com/library/jj573650.aspx).|


### Servicebeheerder
|Machtigingsniveaus|Meer informatie|
|--------------------------|-------------------------|
|Aan een servicebeheerder wordt een van de volgende machtigingen toegewezen:<br /><br />**Volledige toegang[!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]: verleent toegang tot alle gebieden van de **, zonder beperkingen. Kan ook andere servicebeheerders toevoegen en beheren.<br /><br />**Alleen-lezentoegang**: verleent leestoegang tot alle gebieden van de [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. Een alleen-lezen servicebeheerder kan gegevens niet wijzigen, maar kan wel rapporten uitvoeren.<br /><br />**Helpdesk - knooppunt Groepen**: verleent machtigingen die de servicebeheerder in staat stellen om uitsluitend een aantal taken uit te voeren die betrekking hebben op helpdeskscenario's. Zie [Intune-consoleweergaven aanpassen voor beheerdersrollen](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console) voor informatie over deze machtigingenset.|Met [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] wordt standaard geen servicebeheerder toegewezen. In plaats daarvan moet u een tenantbeheerder met de rol van algemeen beheerder gebruiken om de eerste servicebeheerder voor uw abonnement toe te wijzen. </br></br> Als servicebeheerder kunt u de [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] gebruiken om dagelijkse taken te beheren voor [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].<br /><br />U wijst servicebeheerders vanuit de beheerconsole toe. Een servicebeheerder moet een licentie voor [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] hebben, voordat het account toegang heeft tot de beheerconsole.|



### Apparaatinschrijvingsmanagers
|Machtigingsniveaus|Meer informatie|
|--------------------------|-------------------------|
|Apparaatinschrijvingsmanagers zijn standaardgebruikersaccounts die een aanvullende machtiging voor het inschrijven van meer dan vijf apparaten hebben.|Elke [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]-gebruiker kan standaard maximaal vijf apparaten inschrijven. U kunt een gebruikersaccount echter de machtiging voor apparaatinschrijvingsmanager geven en vervolgens dat account gebruiken om grote groepen bedrijfsapparaten in te schrijven. Dit is handig als apparaten bijvoorbeeld tijdelijk aan gebruikers worden toegewezen of worden gebruikt in kioskmodus, waarbij geen gebruiker aan het apparaat gekoppeld hoeft te worden.|


## Beheerwebsites voor Intune
 Voor verschillende beheertaken gebruikt u een van de volgende beheerwebsites die u kunt openen met een [ondersteunde webbrowser](supported-web-browsers.md).

- [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune-beheerdersconsole](https://admin.manage.microsoft.com/)

### [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**Als tenantbeheerder gebruikt u deze portal om uw abonnement te beheren**, met inbegrip van de volgende taken wanneer dit wordt toegestaan door uw beheerdersrol:

- Gebruikersaccounts voor het abonnement beheren en directory-synchronisatie configureren vanuit uw lokale Active Directory.
- Groepen gebruikers, genaamd beveiligingsgroepen, beheren.
- Licenties voor het gebruik van [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] aan gebruikers toewijzen.
- De domeinnaam configureren die u bij uw abonnement wilt gebruiken. De domeinnaam bepaalt het account waarmee gebruikers zich aanmelden.
- Facturering en aankoopgegevens voor uw abonnement beheren, waaronder het aantal licenties dat u hebt, of de hoeveelheid opslagruimte in de cloud die u kunt gebruiken.
- Koppelingen zoeken om de status van de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-service weer te geven.
- Als tenantbeheerder kunt u zich zelfs bij de Office 365-portal aanmelden om het abonnement te beheren wanneer aan uw account geen licentie is toegewezen voor het gebruik van [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].
- Elke gebruiker die een licentie voor Intune heeft maar geen beheerder is, kan deze portal gebruiken om zijn/haar accountwachtwoord opnieuw in te stellen en zijn/haar profiel te bewerken.
- Voor toegang tot de Office 365-portal moet uw account de aanmeldingsstatus **Toegestaan** hebben. Deze status is niet hetzelfde als wanneer u een licentie voor het abonnement hebt. Standaard hebben alle gebruikersaccounts de status **Toegestaan**.


### [Microsoft Intune-beheerdersconsole](https://admin.manage.microsoft.com/)

**Als servicebeheerder gebruikt u deze portal om dagelijkse taken te beheren**, waaronder:

- Beleid voor computers en mobiele apparaten instellen.
- Software, zoals software-updates en apps, uploaden en implementeren.
- [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Endpoint Protection op computers beheren.
- Apparaatstatus weergeven en rapporten uitvoeren.
- Aanmelden bij deze portal. Als u zich wilt aanmelden bij deze portal, moet u beheerdersmachtigingen hebben voor de service of een tenantbeheerder zijn met de rol Algemene beheerder.


Alleen gebruikers met servicebeheerdersmachtigingen en tenantbeheerders met de rol Algemene beheerder kunnen zich bij deze portal aanmelden. Voor toegang tot de beheerconsole moet uw account een licentie voor het gebruik van [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] en de aanmeldingsstatus **Toegestaan** hebben.

Meer informatie over [gebruikers toevoegen voor uw abonnement](start-with-a-paid-subscription-to-microsoft-intune-step-3.md) en over [licenties toewijzen voor uw abonnement](start-with-a-paid-subscription-to-microsoft-intune-step-4.md).

 ### Zie tevens
 [Wat u moet weten voordat u met Microsoft Intune aan de slag gaat](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Aug16_HO5-->


