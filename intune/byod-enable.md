---
title: BYOD met Microsoft Intune inschakelen
description: Een werkstroom op hoog niveau voor het instellen van Intune om een bring-your-own-device (BYOD)-oplossing voor uw organisatie mogelijk te maken.
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: fa70e21b9e9f7adfc508e24bd442a48c834ed7db
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/25/2017
---
# <a name="enable-byod-with-intune"></a>BYOD met Intune inschakelen

Dit onderwerp bevat een werkstroom op hoog niveau voor het instellen van Intune om een bring-your-own-device (BYOD)-oplossing voor uw organisatie mogelijk te maken. De taak wordt in drie processen georganiseerd en bevat koppelingen naar procedures voor ondersteuning.

De werkstroom is onderverdeeld in de volgende drie processen. U kunt aspecten van elk proces aanpassen om te voldoen aan de vereisten van uw organisatie.

-   In **[Apparaten registreren en controleren op naleving](#enroll-devices-and-check-for-compliance)** wordt beschreven hoe u gebruikers in staat stelt hun persoonlijke apparaten te registreren voor beheer met Intune. Intune beheert iOS-, Mac OS-, Android- en Windows- apparaten. Deze sectie beschrijft ook hoe beleid wordt geïmplementeerd op apparaten en ervoor zorgt dat ze voldoen aan de basisvereisten voor beveiliging.

- **[Toegang tot bedrijfsbronnen verlenen](#provide-access-to-company-resources)** laat zien hoe u gebruikers eenvoudig en veilig toegang kunt geven tot bedrijfsbronnen. U doet dit door toegangsprofielen te implementeren op beheerde apparaten. In deze sectie wordt ook uitgelegd hoe u in grote aantallen gekochte app-implementaties beheert met Intune.

-   In **[Bedrijfsgegevens beschermen](#protect-company-data)** wordt uitgelegd hoe u voorwaardelijk toegang kunt verlenen tot bedrijfsresources, gegevensverlies kunt voorkomen en bedrijfsapps en -gegevens kunt verwijderen van apparaten die niet langer voor werk worden gebruikt of die zijn zoekgeraakt of gestolen.

[![Diagram van werkstroom op hoog niveau voor het inschakelen van BYOD met Microsoft Intune](./media/workflow-diagram-for-byod.png)](./media/workflow-diagram-for-byod.png)

<!--- > <sup>You can download this infographic at https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup> --->

## <a name="before-you-begin"></a>Voordat u begint
Voordat gebruikers apparaten kunnen registreren, moet u eerst de Intune-service zelf voorbereiden. Om dit te doen, moet u [licenties toewijzen aan gebruikers](licenses-assign.md) en [de instantie voor Mobile Device Management instellen](mdm-authority-set.md).

Terwijl u bezig bent, moet u ook [de bedrijfsportal aanpassen](company-portal-customize.md). Voeg een huisstijl toe en voorzie gebruikers van informatie over ondersteuning. Hiermee maakt u een vertrouwde registratie- en ondersteuningservaring voor uw gebruikers. U kunt ook [voorwaarden](terms-and-conditions-create.md) opstellen die gebruikers moeten accepteren voordat ze zich inschrijven, of [apparaatbeperkingen](enrollment-restrictions-set.md) om op te geven welke platformen worden ondersteund.

## <a name="enroll-devices-and-check-for-compliance"></a>Apparaten registreren en controleren op naleving

Nadat u de Intune-service hebt voorbereid, moet u voldoen aan de verschillende registratievereisten voor de verschillende apparaattypen die u wilt beheren. Het proces om apparaten voor beheer te registreren is vrij eenvoudig, maar is enigszins anders op basis van apparaattype.

-   **iOS- en Mac-apparaten** U hebt een [Apple MDM-pushcertificaat](apple-mdm-push-certificate-get.md) nodig om iPads, iPhones of macOS-apparaten te registreren. Nadat u het MDM-pushcertificaat hebt geüpload naar Intune, kunnen gebruikers [iOS-apparaten registreren](/intune-user-help/enroll-your-device-in-intune-ios) met de bedrijfsportal-app en de bedrijfsportalwebsite gebruiken om [macOS-apparaten te registreren](/intune-user-help/enroll-your-device-in-intune-macos).

-   **Android-apparaten** U hoeft niets te doen om de Intune-service gereed te maken voor het registreren van Android-apparaten. Gebruikers kunnen [hun Android-apparaten registreren](/intune-user-help/enroll-your-device-in-intune-android) voor beheer met de bedrijfsportal-app die beschikbaar is via Google Play.

-   **Windows-telefoons en pc's** Windows-apparaten kunnen worden geregistreerd met extra configuratie. U kunt automatisch registreren voor Windows 10-pc's en mobiele Windows 10-apparaten inschakelen in Azure Active Directory (AD) Premium om de ervaring van de eindgebruiker te vereenvoudigen. Als u niet beschikt over Azure AD Premium of als u ondersteuning mogelijk wilt maken voor Windows 8.1, kunt u [een DNS-alias voor de registratieserver](windows-enroll.md#enable-windows-enrollment-without-azure-ad-premium) maken om de registratie te vereenvoudigen.


### <a name="make-sure-that-managed-devices-meet-basic-security-requirements"></a>Ervoor zorgen dat beheerde apparaten aan de basisvereisten voor beveiliging voldoen

Nadat gebruikers hun apparaten hebben geregistreerd voor beheer, moet de IT-afdeling ervoor zorgen dat apparaten die worden gebruikt voor toegang tot bedrijfsapps en -gegevens aan de basisvereisten voor beveiliging voldoen. Deze regels kunnen bijvoorbeeld zijn dat voor toegang tot apparaten een pincode moet worden opgegeven en dat gegevens op apparaten moeten zijn versleuteld. Een verzameling van dergelijke regels wordt een [nalevingsbeleid](device-compliance.md) genoemd.

Wanneer u een [nalevingsbeleid implementeert](device-compliance-get-started.md) voor een gebruiker, controleert Intune alle apparaten van deze gebruiker die door Intune worden beheerd om na te gaan of deze voldoen aan de basisvereisten voor beveiliging die u hebt gedefinieerd als onderdeel van uw BYOD-beleid. Nadat is geëvalueerd of een apparaat het beleid naleeft, wordt de status hiervan gerapporteerd aan Intune. In sommige gevallen wordt gebruikers mogelijk gevraagd om instellingen aan te passen, zoals de codering van hun pincode of de apparaatversleuteling. In andere gevallen meldt de bedrijfsportal-app gewoon de instellingen die niet voldoen aan uw beleid aan de gebruiker.

## <a name="provide-access-to-company-resources"></a>Toegang tot bedrijfsresources verlenen

Het eerste wat de meeste werknemers op hun mobiele apparaat willen openen, zijn de e-mail en documenten van het bedrijf. Ze verwachten dat ze dit kunnen instellen zonder complexe stappen te doorlopen of de helpdesk te bellen. U kunt met Intune gemakkelijk [e-mailinstellingen maken en implementeren](email-settings-configure.md) voor systeemeigen e-mail-apps die vooraf worden geïnstalleerd op mobiele apparaten.


> [!NOTE]
> Intune biedt ondersteuning voor het configureren van Android for Work-e-mailprofielen voor de Gmail- en Nine Work-e-mail-apps in de Google Play Store.

Intune helpt u ook bij het beheren en beveiligen van toegang tot on-premises bedrijfsgegevens wanneer gebruikers op een externe locatie werken. Met [Wi-Fi-](wi-fi-settings-configure.md), [VPN-](vpn-settings-configure.md) en e-mailprofielen van Intune hebben uw gebruikers toegang tot de bestanden en bronnen die ze nodig hebben om hun werk te doen, waar ze zich ook bevinden. De webtoepassingen en -services van uw bedrijf die on-premises worden gehost, kunnen ook op een veilige manier worden gebruikt en worden beschermd met de Azure Active Directory-toepassingsproxy en voorwaardelijke toegang.

### <a name="manage-volume-purchased-apps"></a>Apps beheren die zijn gekocht via het volume-aankoopprogramma
Met Intune is het eenvoudig om:
* de volumelicentie-informatie uit elke appstore te importeren
* na te gaan hoeveel licenties u hebt gebruikt
* te voorkomen dat uw gebruikers meer exemplaren van de app installeren dan u hebt gekocht
* [store-apps te leveren op beheerde apparaten](apps-deploy.md)
* apps te zenden naar niet-beheerde apparaten met de bedrijfsportal-website

U kunt met Intune ook apps beheren en implementeren die u via een volume-aankoop hebt aangeschaft in iOS App Store en Microsoft Store voor Bedrijven. Zo beperkt u de administratieve overhead voor het bijhouden van apps die zijn aangeschaft via een volume-aankoopprogramma.

> [!TIP]
> U kunt [enkelvoudige aanmelding (SSO) configureren met Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect). Met SSO kunnen gebruikers zich aanmelden bij apps met de domeingebruikersnaam en het -wachtwoord dat ze on-premises gebruiken. Daarnaast kunt u de toepassingsproxy voor Azure Active Directory gebruiken om [internettoegang te leveren aan web-apps die on-premises worden gehost](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).

-   [Apps voor iOS-apparaten beheren die u hebt aangeschaft via een volume-aankoopprogramma](vpp-apps-ios.md). U koopt meerdere licenties voor iOS-apps via het [Apple Volume Purchase Program voor bedrijven](http://www.apple.com/business/vpp/). U moet een Apple VPP-account via de website van Apple instellen en het Apple VPP-token uploaden naar Intune. U kunt uw gegevens over volume-aankopen vervolgens synchroniseren met Intune en het gebruik bijhouden van uw via het volume-aankoopprogramma gekochte apps.

-   [Apps beheren die zijn aangeschaft in Microsoft Store voor Bedrijven](windows-store-for-business.md). [Microsoft Store voor Bedrijven](https://www.microsoft.com/business-store) biedt een centrale locatie om apps te zoeken en te kopen voor uw organisatie. U kunt zowel afzonderlijke exemplaren van een app als grotere volumes aanschaffen. Als u de store aan Intune koppelt, kunt u apps die in grotere volumes zijn aangeschaft, beheren vanuit de Intune-portal.

## <a name="protect-company-data"></a>Bedrijfsgegevens beveiligen

Intune beveiligt bedrijfsgegevens via veel lagen van de technologie. Op de identiteitslaag beveiligt voorwaardelijke toegang de toegang tot services. Voorwaardelijke toegang verleent alleen beheerde en compatibele apparaten toegang tot bedrijfsbronnen. Op de client-app-laag beschermt app-beveiligingsbeleid tegen gegevensverlies. App-beleid voor gegevensbeveiliging voorkomt dat gegevens naar apps of opslaglocaties die niet zijn beveiligd worden verplaatst. Met deze beleidsregels kunt u bedrijfsgegevens wissen wanneer een apparaat is vermist of gestolen.

### <a name="enforce-conditional-access-to-company-resources"></a>Voorwaardelijke toegang tot bedrijfsresources afdwingen

U kunt nalevingsbeleid combineren met [beleid voor voorwaardelijke toegang](device-compliance.md) om te controleren of apparaten voldoen aan de basisvereisten voor beveiliging van uw BYOD-beleid. Als een apparaat niet voldoet aan de vereisten, worden regels afgedwongen en de toegang geweigerd totdat het apparaat voldoet aan de beleidsvereisten. Op deze manier hebben alleen beheerde en compatibele apparaten toegang tot bedrijfsgegevens van de services zoals Exchange ([Exchange On-Premises](exchange-connector-install.md) of [Exchange Online](conditional-access-exchange-create.md)), SharePoint Online, Skype voor Bedrijven Online en andere services.
<!---first link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)
third link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune). check with Andre--->

> [!IMPORTANT]
> Beleid met voorwaardelijke toegang werkt niet als er geen nalevingsbeleid is om naleving te controleren.

### <a name="prevent-data-loss-of-company-data-with-app-protection-policies"></a>Verlies van bedrijfsgegevens voorkomen met app-beveiligingsbeleid

Met het app-beveiligingsbeleid van Intune kunt u bepalen hoe toegang tot uw gegevens wordt verkregen: met of zonder apparaatregistratie. Door deze veelzijdigheid kunt u bedrijfsgegevens beveiligen zodat gebruikers, zelfs als ze hun apparaat niet bij Intune registreren, toch veilige toegang tot bedrijfsgegevens hebben.

U kunt gebruikmaken van [Intune-beveiligingsbeleid voor apps](app-protection-policies.md) om de bedrijfsgegevens te beveiligen waar iOS- en Android-apparaten toegang tot hebben. Als u dit beleid op app-niveau gebruikt, kunt u beheren hoe werknemers bedrijfsgegevens gebruiken en delen, zelfs als het apparaat niet wordt beheerd met Intune

U kunt [Windows Information Protection (WIP)](app-protection-policies-configure-windows-10.md) gebruiken om hetzelfde te doen voor beheerde Windows 10-apparaten. Deze beleidsregels werken zonder dat de gebruikerservaring van werknemers hierdoor wordt beïnvloed. Er zijn geen wijzigingen in uw netwerkomgeving of andere apps nodig.

### <a name="remove-company-data-while-leaving-personal-data-intact"></a>Bedrijfsgegevens verwijderen met behoud van persoonlijke gegevens

Wanneer een apparaat niet langer nodig is voor het werk, voor een ander doel wordt gebruikt of is kwijtgeraakt, kunt u de bedrijfs-apps en -gegevens van het apparaat verwijderen. Hiervoor kunt u Intune-functies voor het verwijderen van bedrijfsgegevens en het terugzetten van de fabrieksinstellingen gebruiken. Gebruikers kunnen via de Intune-bedrijfsportal ook op afstand gegevens verwijderen van de apparaten die hun persoonlijke eigendom zijn, als die zijn geregistreerd in Intune.

Met [Fabrieksinstellingen terugzetten](devices-wipe.md) wordt een apparaat teruggezet op de standaardfabrieksinstellingen, worden de gebruikersgegevens en -instellingen verwijderd en wordt het apparaat verwijderd uit de beheerfunctie van Intune. Met [Bedrijfsgegevens verwijderen](devices-wipe.md#remove-company-data) worden alleen bedrijfsgegevens van het apparaat verwijderd, maar blijven de persoonlijke gegevens van de gebruiker intact.

Zodra dit proces is gestart, wordt het apparaat onmiddellijk opnieuw ingesteld. Wanneer het proces is voltooid, zijn alle bedrijfsgegevens verwijderd en is de naam van het apparaat verwijderd uit Intune. Hiermee wordt het levenscyclusbeheer van het apparaat voltooid.
