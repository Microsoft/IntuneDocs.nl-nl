---
title: Active Directory synchroniseren en gebruikers toevoegen aan Intune | Microsoft Intune
description: On-premises gebruikers met Azure AD synchroniseren en beheerdersmachtigingen voor uw Intune-abonnement verlenen
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: 33534c685ad3a4ddfd4b605e088132f2b8ff2c36


---


# <a name="sync-active-directory-and-add-users-to-intune"></a>Active Directory synchroniseren en gebruikers toevoegen aan Intune
U kunt adreslijstsynchronisatie configureren voor het importeren van gebruikersaccounts uit de on-premises Active Directory in Microsoft Azure Active Directory (Azure AD). Het koppelen van uw on-premises Active Directory-service aan alle Azure Active Directory-services zorgt ervoor dat het beheer van gebruikersidentiteiten veel eenvoudiger wordt. U kunt ook eenmalige aanmelding configureren om de authenticatie vertrouwd en eenvoudig te maken voor uw gebruikers.

Het wordt u zelfs nog gemakkelijker gemaakt, want wanneer u meerdere services gebruikt met dezelfde [Azure AD-tenant](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/), zijn de gebruikersaccounts die u eerder hebt gesynchroniseerd, beschikbaar voor alle cloudservices met hetzelfde Azure AD-tenantabonnement.

## <a name="synchronize-on-premises-users-with-azure-ad"></a>On-premises gebruikers synchroniseren met Azure AD
Het enige hulpprogramma dat u nodig hebt om uw gebruikersaccounts te synchroniseren met Azure AD, is de [Azure AD Connect-wizard](https://www.microsoft.com/download/details.aspx?id=47594). De Azure AD Connect-wizard biedt een vereenvoudigde begeleiding voor het verbinden van de on-premises infrastructuur voor identiteiten aan de cloud.  Kies uw topologie en behoeften (een of meer mappen, wachtwoordsynchronisatie of federatie) om alle onderdelen door de wizard te laten implementeren en configureren die nodig zijn om de verbinding te laten werken. Inclusief: synchronisatieservices, Active Directory Federation Services (AD FS) en de Azure AD PowerShell-module.

> [!TIP]
> Azure AD Connect bevat functionaliteit die eerder is uitgebracht als Dirsync en Azure AD Sync. Lees meer over [adreslijstintegratie](http://technet.microsoft.com/library/jj573653.aspx). Zie [Overeenkomsten tussen Active Directory en Azure AD](http://technet.microsoft.com/library/dn518177.aspx) voor meer informatie over de voordelen van het synchroniseren van gebruikersaccounts vanuit de lokale directory naar Azure AD.

## <a name="grant-administrator-permissions"></a>Beheerdersbevoegdheden toekennen

Voor het beheer van Intune moet u het volgende gebruiken:
- Twee typen beheerdersaccounts
- Gebruikersaccounts met aanvullende machtigingen
- Twee webbeheerconsoles/portals om uw beheerders toegang te verlenen tot de zaken die moeten worden beheerd.

Nadat u gebruikers aan uw Intune-abonnement hebt toegevoegd, raden we u aan om aan een paar gebruikersaccounts beheerdersreferenties te verlenen. De console die u gebruikt om beheerdersreferenties toe te wijzen, is afhankelijk van het type beheerder dat u wilt toewijzen:

-   **Tenantbeheerder**: gebruik de **Microsoft Intune-accountportal** om dit type beheerder toe te wijzen voor het beheren van uw abonnement, met inbegrip van facturering, cloudopslag en het beheren van de gebruikers die Intune kunnen gebruiken.

-   **Servicebeheerder**: gebruik de **Microsoft Intune-beheerconsole** om dit type beheerder toe te wijzen voor dagelijkse taken, waaronder het beheer van mobiele apparaten of computers, het implementeren van beleid of software en het uitvoeren van rapporten.

In de volgende gedeelten worden deze accounts en portals uitgelegd.

## <a name="administrator-accounts-and-user-accounts-with-special-permissions"></a>Beheerdersaccounts en gebruikersaccounts met speciale machtigingen

Hieronder vindt u de accounts en machtigingen die u voor Intune gebruikt.

### <a name="tenant-administrator"></a>Tenantbeheerder
|Machtigingsniveaus|Meer informatie|
|--------------------------|-------------------------|
|Aan tenantbeheerders is één beheerdersrol toegewezen waarmee het beheerbereik voor die gebruiker en de te beheren taken zijn gedefinieerd.<br /><br />De beheerdersrollen voor de verschillende Microsoft-cloudservices komen overeen, hoewel bepaalde rollen door sommige services mogelijk niet worden ondersteund.<br /><br /> In Microsoft Intune worden de volgende rollen gebruikt:<br /><br />- Algemeen beheerder<br />- Financieel medewerker<br />- Wachtwoordbeheerder<br />- Serviceondersteuningsbeheerder<br />- Gebruikerstoegangbeheerder|Het account dat u gebruikt om uw Microsoft Intune-abonnement te maken, is standaard een tenantbeheerder met de rol Algemeen beheerder.<br /></br>  Als tenantbeheerder gebruikt u de [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] om uw abonnement voor Intune te beheren en om tenantbeheerders toe te wijzen vanuit de [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Gebruik een tenantbeheerder met de rol voor algemeen beheer voor toegang tot de [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] om uw eerste servicebeheerder toe te wijzen. Gebruik een tenantbeheerder bij voorkeur niet voor dagelijkse beheertaken. Een tenantbeheerder heeft geen licentie voor Intune nodig om toegang tot de [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)] te krijgen.<br /><br />De tenantbeheerder is een algemeen concept in Microsoft-cloudservices. Wanneer u zich abonneert op Intune, is uw service een tenant van Microsoft Azure AD. Zie het gedeelte Azure AD-tenant in [Wat is een Azure AD-adreslijst?](http://technet.microsoft.com/library/jj573650.aspx).|


### <a name="service-administrator"></a>Servicebeheerder
|Machtigingsniveaus|Meer informatie|
|--------------------------|-------------------------|
|Aan een servicebeheerder wordt een van de volgende machtigingen toegewezen:<br /><br />**Volledige toegang[!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]: verleent toegang tot alle gebieden van de **, zonder beperkingen. Kan ook andere servicebeheerders toevoegen en beheren.<br /><br />**Alleen-lezentoegang**: verleent leestoegang tot alle gebieden van de [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. Een alleen-lezen servicebeheerder kan gegevens niet wijzigen, maar kan wel rapporten uitvoeren.<br /><br />**Helpdesk - knooppunt Groepen**: verleent machtigingen die de servicebeheerder in staat stellen om uitsluitend een aantal taken uit te voeren die betrekking hebben op helpdeskscenario's. Zie [Intune-consoleweergaven aanpassen voor beheerdersrollen](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console) voor informatie over deze machtigingenset.|Met Intune wordt standaard geen servicebeheerder toegewezen. In plaats daarvan moet u een tenantbeheerder met de rol van algemeen beheerder gebruiken om de eerste servicebeheerder voor uw abonnement toe te wijzen. </br></br> Als servicebeheerder kunt u de [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] gebruiken om dagelijkse taken te beheren voor Intune.<br /><br />U wijst servicebeheerders vanuit de beheerconsole toe. Een servicebeheerder moet een licentie voor Intune hebben, voordat het account toegang heeft tot de beheerconsole.|



### <a name="device-enrollment-managers"></a>Apparaatinschrijvingsmanagers
|Machtigingsniveaus|Meer informatie|
|--------------------------|-------------------------|
|Apparaatinschrijvingsmanagers zijn standaardgebruikersaccounts die een aanvullende machtiging voor het inschrijven van meer dan vijf apparaten hebben.|Elke [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]-gebruiker kan standaard maximaal vijf apparaten inschrijven. U kunt een gebruikersaccount echter de machtiging voor apparaatinschrijvingsmanager geven en vervolgens dat account gebruiken om grote groepen bedrijfsapparaten in te schrijven. Dit is handig als apparaten bijvoorbeeld tijdelijk aan gebruikers worden toegewezen of worden gebruikt in kioskmodus, waarbij geen gebruiker aan het apparaat gekoppeld hoeft te worden.|




>[!div class="step-by-step"]

>[&larr; **Domeininstellingen**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Intune-licenties beheren** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Nov16_HO4-->


