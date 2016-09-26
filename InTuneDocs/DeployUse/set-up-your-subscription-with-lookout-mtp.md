---
title: Abonnement instellen met Lookout MTP | Microsoft Intune
description: In dit onderwerp staat gedetailleerde informatie over het configureren van Lookout MTP.
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 61480eb11cc8f4b6b336e48a50c2fe1b5fcd3fac
ms.openlocfilehash: 8e2c71127801afc21d52e08d13dd9099b263e801


---

# Uw abonnement instellen voor Lookout Mobile Threat Protection
Als u uw abonnement wilt instellen voor de Lookout MTP-service, moet u de volgende informatie over uw Azure Active Directory (Azure AD) naar de Lookout-ondersteuning (enterprisesupport@lookout.com) sturen. 

* Azure AD-tenant-id
* Azure AD-groepsobject-id voor volledige toegang tot de Lookout MTP-console
* Azure AD-groepsobject-id voor beperkte toegang tot de Lookout MTP-console (optioneel)

Gebruik de informatie in de volgende sectie om de gegevens te verzamelen die u aan het Lookout-ondersteuningsteam moet geven.  

## Azure AD-gegevens ophalen
### Azure AD-tenant-id ophalen
Meld u aan bij de Azure AD-beheerportal (https://manage.windowsazure.com) en selecteer uw abonnement. 

![schermopname van de Azure AD-pagina met de naam van de tenant](../media/mtp/aad_tenant_name.png) Als u de naam van uw abonnement kiest, bevat de resulterende URL de abonnements-id.  Als u problemen heeft met het vinden van uw abonnements-id, kunt u in het [artikel van Microsoft Ondersteuning](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US) extra tips lezen.   
### Azure AD-groeps-id ophalen
De Lookout MTP-console ondersteunt twee toegangsniveaus:  
* **Volledige toegang:** de Azure AD-beheerder kan een groep maken met gebruikers die volledige toegang hebben en eventueel een groep maken met gebruikers met beperkte toegang.  Alleen gebruikers in deze groepen kunnen zich aanmelden bij de **Lookout MTP-console**.
* **Beperkte toegang:** geen toegang tot verschillende configuratie- en inschrijvingsgerelateerde modules van de Lookout MTP-console. Alleen-lezentoegang tot de module **Beveiligingsbeleid** van de Lookout MTP-console.  

Lees [dit artikel](https://personal.support.lookout.com/hc/en-us/articles/114094105653) op de Lookout-website voor meer informatie over de machtigingen.

U vindt de **groepsobject-id** op de eigenschappenpagina van de groep in de Azure AD-beheerconsole.

![schermopname van de eigenschappenpagina met het veld Groeps-id gemarkeerd](../media/mtp/aad_group_object_id.png)

Neem contact op met de Lookout-ondersteuning (email: enterprisesupport@lookout.com) wanneer u deze informatie hebt verzameld.

Met behulp van de gegevens die u hebt verzameld, zal de Lookout-ondersteuning in samenwerking met uw primaire contactpersoon zorgen voor onboarding van uw abonnement en uw Lookout MTP Enterprise-account maken.


## Uw abonnement configureren met Lookout MTP
### Stap 1: stel uw MTP in
Nadat de Lookout-ondersteuning uw Lookout MTP Enterprise-account heeft gemaakt, kunt u zich aanmelden bij de Lookout MTP-console.   De primaire contactpersoon van uw bedrijf ontvangt een e-mailbericht van Lookout met een koppeling naar de aanmeldings-URL: https://aad.lookout.com/les?action=consent

Wanneer u zich voor het eerst bij de Lookout MTP-console aanmeldt, moet u een gebruikersaccount met de Azure AD-rol van globale beheerder gebruiken. Voor Lookout MTP moet u namelijk uw Azure AD-tenant registreren.   Voor volgende aanmeldingen is dit niveau van Azure AD-bevoegdheden niet vereist.  Bij de eerste keer aanmelden wordt een instemmingspagina weergegeven. Kies **Accepteren** om de registratie te voltooien.

![schermopname van de pagina die bij de eerste keer aanmelden bij de Lookout MTP-console wordt weergegeven](../media/mtp/lookout_mtp_initial_login.png) Nadat u hebt ingestemd, wordt u omgeleid naar de Lookout MTP-console. Na de registratie kunt u zich aanmelden via de URL: https://aad.lookout.com

Zie het [probleemoplossingsartikel](https://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration) als u problemen ondervindt met aanmelden.

De volgende stappen beschrijven de taken die moeten worden uitgevoerd om de configuratie van Lookout MTP in de [Lookout MT-console](https://aad.lookout.com) te voltooien.

### Stap 2: de Intune-connector configureren

Ga in de Lookout MTP-console naar de module **Systeem**, kies het tabblad **Connectors** en selecteer **Intune**.

![schermopname van de Lookout MTP-console waarin het tabblad Connectors is geopend en de Intune-optie is gemarkeerd](../media/mtp/lookout_mtp_setup-intune-connector.png)

Configureer bij de optie Verbindingsinstellingen de heartbeatfrequentie in minuten.  Wanneer deze stap is voltooid, is de Intune-connector gereed.  

![schermopname van het tabblad Verbindingsinstellingen waarop de heartbeatfrequentie is geconfigureerd](../media/mtp/lookout-mtp-connection-settings.png)

### Stap 3: registratiegroepen configureren
Definieer bij de optie **Registratiebeheer** een set gebruikers van wie de apparaten moeten worden geregistreerd bij Lookout.   Aanbevolen wordt om als test te beginnen met een kleine groep gebruikers om meer vertrouwd te raken met de integratie.  Als u tevreden bent met de testresultaten, kunt u de registratie uitbreiden naar meer gebruikersgroepen.

Als u registratiegroepen wilt maken, moet u eerst een Azure AD-beveiligingsgroep definiëren die een goede eerste gebruikersset voor registratie bij Lookout MTP vormt. Zodra u de groep hebt gemaakt in Azure AD, gaat u in de Lookout MTP-console naar de optie **Registratiebeheer** en voegt u de Azure AD-beveiligingsgroep **Weergavenamen** toe voor registratie.

Wanneer een gebruiker in een registratiegroep zit, worden alle apparaten van die gebruiker geregistreerd die met Azure AD worden geïdentificeerd en ondersteund. Deze kunnen vervolgens in Lookout MTP worden geactiveerd.  De eerste keer dat de gebruiker de Lookout for Work-app op het ondersteunde apparaat opent, wordt het apparaat in Lookout MTP geactiveerd.
![schermopname van de registratiepagina van de Intune-connector](../media/mtp/lookout-mtp-enrollment.png)

U kunt het interval voor het controleren op nieuwe apparaten het best op de standaard 5 minuten laten staan.

>[!IMPORTANT]
> De weergavenaam is hoofdlettergevoelig.  Gebruik de **weergavenaam** zoals weergegeven op de pagina **Eigenschappen** van de beveiligingsgroep in de Azure-portal. In de afbeelding hieronder is de weergavenaam op de pagina **Eigenschappen** van de beveiligingsgroep in CamelCase weergegeven.  De titel wordt echter volledig in kleine letters weergegeven en mag niet in de Lookout MTP-console worden ingevoerd.
>![schermopname van de Azure-portal, Azure Active Directory-service, eigenschappenpagina](../media/mtp/aad-group-display-name.png)

De huidige versie heeft de volgende beperkingen:  
* Er is geen validatie voor de weergavenamen van de groep.  Zorg ervoor dat u voor de Azure AD-de beveiligingsgroep de waarde gebruikt in het veld **WEERGAVENAAM** in de Azure-portal.
* Het maken van groepen binnen groepen wordt momenteel niet ondersteund.  Opgegeven Azure AD-beveiligingsgroepen mogen alleen gebruikers bevatten en geen geneste groepen.


### Stap 4: statussynchronisatie configureren
Geef bij de optie **Statussynchronisatie** het type gegevens op dat naar Intune moet worden verzonden.  Nu moet u zowel de apparaatstatus als de bedreigingsstatus inschakelen voor een goede integratie van Lookout met Intune.  Deze worden standaard ingeschakeld.
### Stap 5: foutenrapport met informatie over geadresseerden configureren
Voer bij de optie **Foutbeheer** het e-mailadres in waarnaar het foutenrapport moet worden verzonden.

![schermopname van de foutenbeheerpagina van de Intune-connector](../media/mtp/lookout-mtp-connector-error-notifications.png)

### Stap 6: e-mailmeldingen configureren
Als u e-mailwaarschuwingen wilt ontvangen voor bedreigingen, meldt u zich aan bij de [Lookout MTP-console](https://aad.lookout.com) met het gebruikersaccount waarnaar de meldingen moeten worden verzonden.  Ga naar de module **Systeem** en klik op het tabblad **Voorkeuren**. Kies de gewenste meldingen en stel ze in op **AAN**. Sla de wijzigingen op.

![schermopname van de pagina Voorkeuren met het gebruikersaccount weergegeven](../media/mtp/lookout-mtp-email-notifications.png) Als u geen e-mailmeldingen meer wilt ontvangen, stelt u de meldingen in op **UIT** en slaat u de wijzigingen op.
### Stap 7: bedreigingsclassificatie configureren
Mobiele bedreigingen worden in Lookout MTP in verschillende typen ingedeeld. Aan de [bedreigingsclassificaties van Lookout MTP](http://personal.support.lookout.com/hc/en-us/articles/114094130693) zijn standaardrisiconiveaus gekoppeld. Deze kunnen op elk gewenst moment worden aangepast aan de vereisten van uw bedrijf.

![schermopname van de beleidspagina met bedreiging en classificaties](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> De risiconiveaus die hier zijn opgegeven, zijn een belangrijk aspect van MTP, omdat de apparaatcompatibiliteit voor Intune-integratie op basis van deze risiconiveaus in runtime wordt berekend. Dat wil zeggen dat de Intune-beheerder een regel in werking stelt om te bepalen of een apparaat niet-compatibel is als het een actieve bedreiging heeft met een minimumniveau van Hoog, Gemiddeld of Laag. De berekening van de apparaatcompatibiliteit in Intune wordt rechtstreeks door het bedreigingsclassificatiebeleid in MTP gestuurd.

## Registratie bewaken
Nadat de installatie is voltooid, wordt Azure AD met Lookout MTP gecontroleerd op apparaten die met de opgegeven registratiegroepen overeenkomen.  In de module Apparaten vindt u informatie over de apparaten die zijn geregistreerd.  De initiële status van apparaten wordt weergegeven als In behandeling.  De apparaatstatus wordt gewijzigd nadat de Lookout for Work-app op het apparaat is geïnstalleerd, geopend en geactiveerd.  Meer informatie over het pushen van de Lookout for Work-app naar het apparaat vindt u in het onderwerp [Configure and deploy Lookout for Work apps](configure-and-deploy-lookout-for-work-apps.md) (Lookout for Work-apps configureren en implementeren).
## Volgende stappen
[Lookout MTP-verbinding met Intune inschakelen](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Sep16_HO2-->


