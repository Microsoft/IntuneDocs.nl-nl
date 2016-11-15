---
title: Uw abonnement instellen met Lookout | Microsoft Intune
description: Deze onderwerpen bevatten gedetailleerde informatie over het configureren van Lookout Device Threat Protection.
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8477a2f1-2e1d-4d42-8bcb-e1181cc900bb
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1187ad3fdd4a427333d610686698c1f806c6ee33
ms.openlocfilehash: 1d8cdaa36a852fba5912c250daa500e16bd3b661


---

# <a name="set-up-your-subscription-for-lookout-device-threat-protection"></a>Uw abonnement voor Lookout Device Threat Protection instellen
Als u uw abonnement wilt instellen voor de Lookout-service voor het beveiligen van uw apparaat tegen bedreigingen, moet u de volgende informatie over uw Azure Active Directory-abonnement (Azure AD) naar de Lookout-ondersteuning (enterprisesupport@lookout.com) sturen. Uw Lookout Mobility Endpoint Security-tenant wordt gekoppeld aan uw Azure AD-abonnement voor integratie van Lookout met Intune. 

* **Azure AD-tenant-id**
* **Azure AD-groepsobject-id** voor **volledige** toegang tot de Lookout-console
* **Azure AD-groepsobject-id** voor **beperkte** toegang tot de Lookout-console (optioneel)

> [!IMPORTANT]
> Het is niet mogelijk om een bestaande Lookout Mobile Endpoint Security-tenant die nog niet is gekoppeld aan uw Azure AD-tenant, te gebruiken voor de integratie met Azure AD en Intune. Neem contact op met de Lookout-ondersteuning om een nieuwe Lookout Mobile Endpoint Security-tenant te maken. Gebruik de nieuwe tenant voor de onboarding van Azure AD-gebruikers.

Gebruik de volgende sectie om de gegevens te verzamelen die u aan het Lookout-ondersteuningsteam moet geven.  

## <a name="get-your-azure-ad-information"></a>Uw Azure AD-gegevens ophalen
### <a name="azure-ad-tenant-id"></a>Azure AD-tenant-id
Meld u aan bij de [Azure AD-beheerportal](https://manage.windowsazure.com) en selecteer uw abonnement. 

![schermopname van de Azure AD-pagina met de naam van de tenant](../media/mtp/aad_tenant_name.png) Als u de naam van uw abonnement kiest, bevat de resulterende URL de abonnements-id.  Als u problemen hebt met het vinden van uw abonnements-id, kunt u dit [artikel van Microsoft Ondersteuning](https://support.office.com/en-us/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b?ui=en-US&rs=en-US&ad=US) tips lezen over het vinden van uw abonnements-id.   
### <a name="azure-ad-group-id"></a>Azure AD-groeps-id
De Lookout-console ondersteunt twee toegangsniveaus:  
* **Volledige toegang:** de Azure AD-beheerder kan een groep maken met gebruikers die volledige toegang hebben en eventueel een groep maken voor gebruikers met beperkte toegang.  Alleen gebruikers in deze groepen kunnen zich aanmelden bij de **Lookout-console**.
* **Beperkte toegang:** de gebruikers in deze groep hebben geen toegang tot verschillende configuratie- en inschrijvingsgerelateerde modules van de Lookout-console, en hebben alleen-lezentoegang tot de module **Beveiligingsbeleid** van de Lookout-console.  

Lees [dit artikel](https://personal.support.lookout.com/hc/en-us/articles/114094105653) op de Lookout-website voor meer informatie over de machtigingen.

De **groepsobject-id** bevindt zich op de pagina **Eigenschappen** van de groep in de **Azure AD-beheerconsole**.

![schermopname van de eigenschappenpagina met het veld Groeps-id gemarkeerd](../media/mtp/aad_group_object_id.png)

Neem contact op met de Lookout-ondersteuning (email: enterprisesupport@lookout.com) wanneer u deze informatie hebt verzameld.

Met behulp van de gegevens die u hebt verzameld, zal de Lookout-ondersteuning in samenwerking met uw primaire contactpersoon zorgen voor onboarding van uw abonnement en uw Lookout Enterprise-account maken.


## <a name="configure-your-subscription-with-lookout-device-threat-protection"></a>Uw abonnement configureren met Lookout Device Threat Protection
### <a name="step-1-set-up-your-device-threat-protection"></a>Stap 1: de bescherming van uw apparaat tegen bedreigingen instellen
Nadat de Lookout-ondersteuning uw Lookout Enterprise-account heeft gemaakt, kunt u zich aanmelden bij de Lookout-console.   De primaire contactpersoon van uw bedrijf ontvangt een e-mailbericht van Lookout met een koppeling naar de aanmeldings-URL: https://aad.lookout.com/les?action=consent

Wanneer u zich voor het eerst bij de Lookout-console aanmeldt, moet u een gebruikersaccount met de Azure AD-rol van globale beheerder gebruiken, omdat deze gegevens vereist zijn om uw Azure AD-tenant te registreren bij Lookout.   Voor volgende aanmeldingen is dit niveau van Azure AD-bevoegdheden niet vereist.  Bij de eerste keer aanmelden wordt een instemmingspagina weergegeven. Kies **Accepteren** om de registratie te voltooien.

![schermopname van de pagina die bij de eerste keer aanmelden bij de Lookout-console wordt weergegeven](../media/mtp/lookout_mtp_initial_login.png) Nadat u hebt ingestemd, wordt u doorgestuurd naar de Lookout-console. Na de registratie kunt u zich aanmelden via deze URL: https://aad.lookout.com

Zie het [probleemoplossingsartikel](https://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration) als u problemen ondervindt met aanmelden.

De volgende stappen beschrijven de taken die u moet uitvoeren om de configuratie van Lookout in de [Lookout-console](https://aad.lookout.com) te voltooien.

### <a name="step-2-configure-the-intune-connector"></a>Stap 2: de Intune-connector configureren

1.  Ga in de Lookout-console naar de module **Systeem**, kies het tabblad **Connectors** en selecteer **Intune**.

  ![schermopname van de Lookout-console waarin het tabblad Connectors is geopend en de Intune-optie is gemarkeerd](../media/mtp/lookout_mtp_setup-intune-connector.png)

2.  Configureer bij de optie Verbindingsinstellingen de heartbeatfrequentie in minuten.  Uw Intune-connector is nu gereed.  

  ![schermopname van het tabblad Verbindingsinstellingen waarop de heartbeatfrequentie is geconfigureerd](../media/mtp/lookout-mtp-connection-settings.png)

### <a name="step-3-configure-enrollment-groups"></a>Stap 3: registratiegroepen configureren
Definieer bij de optie **Registratiebeheer** een set gebruikers van wie de apparaten moeten worden geregistreerd bij Lookout. Het is het beste om te beginnen met een kleine groep gebruikers, om de integratie te testen en vertrouwd te raken met de manier waarop deze werkt.  Als u tevreden bent met de testresultaten, kunt u de registratie uitbreiden naar meer gebruikersgroepen.

Als u registratiegroepen wilt maken, moet u eerst een Azure AD-beveiligingsgroep definiëren die een goede eerste gebruikersset voor registratie bij Lookout Device Threat Protection vormt. Nadat u de groep hebt gemaakt in Azure AD, gaat u in de Lookout-console naar de optie **Registratiebeheer** en voegt u de Azure AD-beveiligingsgroep **Weergavenamen** toe voor registratie.

Wanneer een gebruiker in een registratiegroep zit, worden alle apparaten van die gebruiker geregistreerd die met Azure AD worden geïdentificeerd en ondersteund. Deze kunnen vervolgens in Lookout Device Threat Protection worden geactiveerd.  De eerste keer dat de gebruiker de Lookout for Work-app op het ondersteunde apparaat opent, wordt het apparaat in Lookout geactiveerd.

![schermopname van de registratiepagina van de Intune-connector](../media/mtp/lookout-mtp-enrollment.png)

U kunt het interval voor het controleren op nieuwe apparaten het best op de standaard 5 minuten laten staan.

>[!IMPORTANT]
> De weergavenaam is hoofdlettergevoelig.  Gebruik de **weergavenaam** zoals weergegeven op de pagina **Eigenschappen** van de beveiligingsgroep in de Azure-portal. In de afbeelding hieronder is de weergavenaam op de pagina **Eigenschappen** van de beveiligingsgroep in CamelCase weergegeven.  De titel wordt echter volledig in kleine letters weergegeven en mag niet in de Lookout-console worden ingevoerd.
>![schermopname van de Azure-portal, Azure Active Directory-service, eigenschappenpagina](../media/mtp/aad-group-display-name.png)

De huidige versie heeft de volgende beperkingen:  
* Er is geen validatie voor de weergavenamen van de groep.  Zorg ervoor dat u voor de Azure AD-de beveiligingsgroep de waarde gebruikt in het veld **WEERGAVENAAM** in de Azure-portal.
* Het maken van groepen binnen groepen wordt momenteel niet ondersteund.  Opgegeven Azure AD-beveiligingsgroepen mogen alleen gebruikers bevatten en geen geneste groepen.


### <a name="step-4-configure-state-sync"></a>Stap 4: statussynchronisatie configureren
Geef bij de optie **Statussynchronisatie** het type gegevens op dat naar Intune moet worden verzonden.  Nu moet u zowel de apparaatstatus als de bedreigingsstatus inschakelen voor een goede integratie van Lookout met Intune.  Deze worden standaard ingeschakeld.
### <a name="step-5-configure-error-report-email-recipient-information"></a>Stap 5: foutenrapport met informatie over geadresseerden configureren
Voer bij de optie **Foutbeheer** het e-mailadres in waarnaar het foutenrapport moet worden verzonden.

![schermopname van de foutenbeheerpagina van de Intune-connector](../media/mtp/lookout-mtp-connector-error-notifications.png)

### <a name="step-6-configure-enrollment-settings"></a>Stap 6. Registratie-instellingen configureren
Geef in de module **Systeem** op de pagina **Connectors** het aantal dagen op voordat een apparaat wordt beschouwd als niet-verbonden.  Niet-verbonden apparaten worden als niet-compatibel beschouwd en krijgen geen toegang meer tot uw bedrijfstoepassingen op basis van de Intune-beleidsregels voor voorwaardelijke toegang. U kunt waarden tussen 1 en 90 dagen opgeven.

![](../media/mtp/lookout-console-enrollment-settings.png)

### <a name="step-7-configure-email-notifications"></a>Stap 7: e-mailmeldingen configureren
Als u e-mailwaarschuwingen voor bedreigingen wilt ontvangen, meldt u zich aan bij de [Lookout-console](https://aad.lookout.com) met het gebruikersaccount waarnaar de meldingen moeten worden verzonden. Kies op het tabblad **Voorkeuren** van de **Systeem**-module de gewenste meldingen en stel ze in op **AAN**. Sla de wijzigingen op.

![schermopname van de pagina Voorkeuren met het gebruikersaccount weergegeven](../media/mtp/lookout-mtp-email-notifications.png) Als u geen e-mailmeldingen meer wilt ontvangen, stelt u de meldingen in op **UIT** en slaat u de wijzigingen op.
### <a name="step-8-configure-threat-classification"></a>Stap 8: bedreigingsclassificatie configureren
Mobiele bedreigingen worden in Lookout Device Threat Protection in verschillende typen ingedeeld. Aan de [bedreigingsclassificaties van Lookout](http://personal.support.lookout.com/hc/en-us/articles/114094130693) zijn standaardrisiconiveaus gekoppeld. Deze kunnen op elk gewenst moment worden aangepast aan de vereisten van uw bedrijf.

![schermopname van de beleidspagina met bedreiging en classificaties](../media/mtp/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> De risiconiveaus die hier worden opgegeven, zijn een belangrijk aspect van apparaatbescherming, omdat de Intune-integratie tijdens runtime de apparaatcompatibiliteit berekent op basis van deze risiconiveaus. Dat wil zeggen dat de Intune-beheerder een beleidsregel instelt om een apparaat te identificeren als niet-compatibel als het een actieve bedreiging heeft met een minimumniveau van Hoog, Gemiddeld of Laag. De berekening van de apparaatcompatibiliteit in Intune wordt rechtstreeks door het bedreigingsclassificatiebeleid in Lookout Device Threat Protection aangestuurd.

## <a name="watching-enrollment"></a>Registratie bewaken
Nadat de installatie is voltooid, wordt Azure AD met Lookout Device Threat Protection gecontroleerd op apparaten die met de opgegeven registratiegroepen overeenkomen.  In de module Apparaten vindt u informatie over de apparaten die zijn geregistreerd.  De initiële status van apparaten wordt weergegeven als In behandeling.  De apparaatstatus wordt gewijzigd nadat de Lookout for Work-app op het apparaat is geïnstalleerd, geopend en geactiveerd.  Zie voor neer informatie over het pushen van de Lookout for Work-app naar het apparaat het onderwerp [Configure and deploy Lookout for Work apps](configure-and-deploy-lookout-for-work-apps.md) (Lookout for Work-apps configureren en implementeren).
## <a name="next-steps"></a>Volgende stappen
[Lookout MTP-verbinding met Intune inschakelen](enable-lookout-mtp-connection-in-intune.md)



<!--HONumber=Nov16_HO1-->


