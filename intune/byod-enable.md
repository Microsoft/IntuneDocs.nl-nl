---
title: BYOD met Microsoft Intune inschakelen
description: 
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: 880b83a63eefe13a96ab8838c7092c185aa32cd0
ms.sourcegitcommit: ce363409d1206e4a3d669709863ccc9eb22b7d5f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/11/2017
---
# <a name="enable-byod-with-intune"></a>BYOD met Intune inschakelen

Dit onderwerp bevat een werkstroom op hoog niveau voor het instellen van Intune om een bring-your-own-device (BYOD)-oplossing voor uw organisatie mogelijk te maken. De taak wordt in drie processen georganiseerd en bevat koppelingen naar procedures voor ondersteuning.

De werkstroom is onderverdeeld in de volgende drie processen. U kunt aspecten van elk proces aanpassen om te voldoen aan de vereisten van uw organisatie.

-   In **[Apparaten registreren en controleren op naleving](#enroll-devices-and-check-for-compliance)** wordt beschreven hoe u gebruikers in staat stelt hun persoonlijke apparaten te registreren voor beheer met Intune. Intune beheert iOS-, Mac OS-, Android- en Windows- apparaten. Deze sectie beschrijft ook hoe beleid wordt geïmplementeerd op apparaten en ervoor zorgt dat ze voldoen aan de basisvereisten voor beveiliging.

- **[Toegang tot bedrijfsbronnen verlenen](#provide-access-to-company-resources)** laat u zien hoe de IT-afdeling het mogelijk kan maken dat gebruikers eenvoudig en veilig toegang krijgen tot bedrijfsbronnen. U doet dit door toegangsprofielen te implementeren op beheerde apparaten. In deze sectie wordt ook uitgelegd hoe u in grote aantallen gekochte app-implementaties beheert met Intune.

-   In **[Bedrijfsgegevens beschermen](#protect-company-data)** wordt uitgelegd hoe u voorwaardelijk toegang kunt verlenen tot bedrijfsresources, gegevensverlies kunt voorkomen en bedrijfsapps en -gegevens kunt verwijderen van apparaten die niet langer voor werk worden gebruikt of die zijn zoekgeraakt of gestolen.

[![Diagram van werkstroom op hoog niveau voor het inschakelen van BYOD met Microsoft Intune](./media/workflow-diagram-for-byod.png)](./media/workflow-diagram-for-byod.png)

<!--- > <sup>You can download this infographic at https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup> --->

## <a name="before-you-begin"></a>Voordat u begint
Voordat gebruikers apparaten kunnen registreren, moet u eerst de Intune-service zelf voorbereiden. Om dit te doen, moet u [licenties toewijzen aan gebruikers](licenses-assign.md) en [de instantie voor Mobile Device Management instellen](mdm-authority-set.md).

Terwijl u bezig bent, moet u ook [de bedrijfsportal aanpassen](company-portal-customize.md). Voeg een huisstijl toe en voorzie gebruikers van informatie over ondersteuning. Hiermee maakt u een vertrouwde registratie- en ondersteuningservaring voor uw gebruikers.

## <a name="enroll-devices-and-check-for-compliance"></a>Apparaten registreren en controleren op naleving

Nadat u de Intune-service hebt voorbereid, moet u voldoen aan de verschillende registratievereisten voor de verschillende apparaattypen die u wilt beheren. Het proces om apparaten voor beheer te registreren is vrij eenvoudig, maar is enigszins anders op basis van apparaattype.

-   **iOS- en Mac-apparaten** U hebt een [APNs-certificaat (Apple Push Notification service)](apple-mdm-push-certificate-get.md) nodig om iPads, iPhones of macOS-apparaten te registreren. Nadat u het APNs-certificaat hebt geüpload naar Intune, kunnen gebruikers [iOS-apparaten registreren](/intune-user-help/enroll-your-device-in-intune-ios) met de bedrijfsportal-app en de bedrijfsportalwebsite gebruiken om [macOS-apparaten te registreren](/intune-user-help/enroll-your-device-in-intune-macos).

-   **Android-apparaten** U hoeft niets te doen om de Intune-service gereed te maken voor het registreren van Android-apparaten. Gebruikers kunnen [hun Android-apparaten registreren](/intune-user-help/enroll-your-device-in-intune-android.md) voor beheer met de bedrijfsportal-app die beschikbaar is via Google Play.

-   **Windows Phones en pc’s** U moet een [DNS-alias instellen voor de registratieserver](windows-enroll.md#enable-windows-enrollment-without-azure-ad-premium) om het registreren van Windows-apparaten eenvoudiger te maken. Anders kunnen gebruikers [Windows-apparaten registreren](/intune-user-help/enroll-your-w10-phone-or-w10-pc-windows) door een werk- of schoolaccount toe te voegen.

  - Als u Azure AD Premium hebt, kunt u het nog eenvoudiger maken voor uw gebruikers om Windows-apparaten te registreren door het [inschakelen van de automatische registratiefunctie](windows-enroll.md). Deze functie registreert een apparaat automatisch in Intune wanneer gebruikers een account voor werk of school toevoegen om hun persoonlijke apparaten te registreren. Het werkt ook voor een apparaat in bedrijfseigendom dat lid wordt van uw organisatie in Azure AD.


### <a name="make-sure-that-managed-devices-meet-basic-security-requirements"></a>Ervoor zorgen dat beheerde apparaten aan de basisvereisten voor beveiliging voldoen

Nadat gebruikers hun apparaten hebben geregistreerd voor beheer, moet de IT-afdeling ervoor zorgen dat apparaten die worden gebruikt voor toegang tot bedrijfsapps en -gegevens aan de basisvereisten voor beveiliging voldoen. Deze regels kunnen bijvoorbeeld zijn dat voor toegang tot apparaten een pincode moet worden opgegeven en dat gegevens op apparaten moeten zijn versleuteld. Een verzameling van dergelijke regels wordt een [nalevingsbeleid](device-compliance.md) genoemd.

Wanneer u een [nalevingsbeleid implementeert](device-compliance-get-started.md) voor een gebruiker, worden alle apparaten van deze gebruiker die door Intune worden beheerd, gecontroleerd om na te gaan of deze voldoen aan de basisvereisten voor beveiliging die u hebt gedefinieerd als onderdeel van uw BYOD-beleid. Nadat is geëvalueerd of een apparaat het beleid naleeft, wordt de status hiervan gerapporteerd aan Intune. In sommige gevallen wordt gebruikers mogelijk gevraagd om instellingen aan te passen, zoals de codering van hun pincode of de apparaatversleuteling. In andere gevallen meldt de bedrijfsportal-app gewoon de instellingen die niet voldoen aan uw beleid aan de gebruiker.

## <a name="provide-access-to-company-resources"></a>Toegang tot bedrijfsresources verlenen

Het eerste wat de meeste werknemers op hun mobiele apparaat willen, is toegang tot de e-mail en documenten van het bedrijf. En ze verwachten dat ze dit kunnen instellen zonder complexe stappen te doorlopen of de helpdesk te bellen. U kunt met Intune gemakkelijk [e-mailinstellingen maken en implementeren](conditional-access-intune-common-ways-use.md) voor systeemeigen e-mail-apps die vooraf worden geïnstalleerd op mobiele apparaten.
<!--- this was old link: (https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune). check with Andre--->

> [!NOTE]
> Intune biedt ondersteuning voor het configureren van Android for Work-e-mailprofielen voor de Gmail- en Nine Work-e-mail-apps in de Google Play Store.

Intune helpt u ook bij het beheren en beveiligen van toegang tot on-premises bedrijfsgegevens wanneer gebruikers op een externe locatie werken. [Wifi-](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune), [VPN-](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile) en e-mailprofielen van Intune geven uw gebruikers toegang tot de bestanden en bronnen die ze nodig hebben om hun werk te doen, waar ze zich ook bevinden. De webtoepassingen en -services van uw bedrijf die on-premises worden gehost, kunnen ook op een veilige manier worden gebruikt en worden beschermd met de Azure Active Directory-toepassingsproxy en voorwaardelijke toegang.

### <a name="manage-volume-purchased-apps"></a>Apps beheren die zijn gekocht via het volume-aankoopprogramma
Met Intune is het eenvoudig om:
* de volumelicentie-informatie uit elke appstore te importeren
* na te gaan hoeveel licenties u hebt gebruikt
* te voorkomen dat uw gebruikers meer exemplaren van de app installeren dan u hebt gekocht
* [store-apps te leveren op beheerde apparaten](apps-deploy.md)
* apps te zenden naar niet-beheerde apparaten met de bedrijfsportal-website

Met Intune kunt u ook apps beheren en implementeren die u via een volume-aankoop hebt aangeschaft in de iOS App Store en de Windows Store voor Bedrijven. Zo beperkt u de administratieve overhead voor het bijhouden van apps die zijn aangeschaft via een volume-aankoopprogramma.

> [!TIP]
> U kunt [enkelvoudige aanmelding (SSO) configureren met Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect). Met SSO kunnen gebruikers zich aanmelden bij apps met de domeingebruikersnaam en het -wachtwoord dat ze on-premises gebruiken. Daarnaast kunt u de toepassingsproxy voor Azure Active Directory gebruiken om [internettoegang te leveren aan web-apps die on-premises worden gehost](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).

-   [Apps voor iOS-apparaten beheren die u hebt aangeschaft via een volume-aankoopprogramma](vpp-apps-ios.md). U koopt meerdere licenties voor iOS-apps via het [Apple Volume Purchase Program voor bedrijven](http://www.apple.com/business/vpp/). U moet een Apple VPP-account via de website van Apple instellen en het Apple VPP-token uploaden naar Intune. U kunt uw gegevens over volume-aankopen vervolgens synchroniseren met Intune en het gebruik bijhouden van uw via het volume-aankoopprogramma gekochte apps.

-   [Apps beheren die zijn aangeschaft in Windows Store voor Bedrijven](windows-store-for-business.md). [Windows Store voor Bedrijven](https://www.microsoft.com/business-store) biedt een centrale locatie om apps te zoeken en aan te schaffen voor uw organisatie. U kunt zowel afzonderlijke exemplaren van een app als grotere volumes aanschaffen. Als u de store aan Intune koppelt, kunt u apps die in grotere volumes zijn aangeschaft, beheren vanuit de Intune-portal.

## <a name="protect-company-data"></a>Bedrijfsgegevens beveiligen

Intune beveiligt bedrijfsgegevens via veel lagen van de technologie. Op de identiteitslaag beveiligt voorwaardelijke toegang de toegang tot services. Voorwaardelijke toegang verleent alleen beheerde en compatibele apparaten toegang tot bedrijfsbronnen. Op de clienttoepassingslaag beveiligt beheer van mobiele toepassingen (MAM) tegen gegevensverlies.  App-beleid voor gegevensbeveiliging voorkomt dat gegevens naar apps of opslaglocaties die niet zijn beveiligd worden verplaatst. Met deze beleidsregels kunt u bedrijfsgegevens wissen wanneer een apparaat is vermist of gestolen.

### <a name="enforce-conditional-access-to-company-resources"></a>Voorwaardelijke toegang tot bedrijfsresources afdwingen

U kunt nalevingsbeleid combineren met [beleid voor voorwaardelijke toegang](device-compliance.md) om te controleren of apparaten voldoen aan de basisvereisten voor beveiliging van uw BYOD-beleid. Als een apparaat niet voldoet aan de vereisten, worden regels afgedwongen en de toegang geweigerd totdat het apparaat voldoet aan de beleidsvereisten. Op deze manier hebben alleen beheerde en compatibele apparaten toegang tot bedrijfsgegevens van de services zoals Exchange ([Exchange On-Premises](exchange-connector-install.md) of [Exchange Online](conditional-access-exchange-create.md)), SharePoint Online, Skype voor Bedrijven Online en andere services.
<!---first link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)
third link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune). check with Andre--->

> [!IMPORTANT]
> Beleid met voorwaardelijke toegang werkt niet als er geen nalevingsbeleid is om naleving te controleren.

### <a name="prevent-data-loss-of-company-data-with-application-protection-policies"></a>Verlies van bedrijfsgegevens voorkomen met beveiligingsbeleid voor toepassingen

Met het beveiligingsbeleid voor toepassingen van Intune kunt u bepalen hoe toegang tot uw gegevens wordt verkregen - met of zonder apparaatregistratie. Door deze veelzijdigheid kunt u bedrijfsgegevens beveiligen zodat gebruikers, zelfs als ze hun apparaat niet bij Intune registreren, toch veilige toegang tot bedrijfsgegevens hebben.

U kunt gebruikmaken van [Intune-beveiligingsbeleid voor apps](app-protection-policies.md) om de bedrijfsgegevens te beveiligen waartoe uw gebruikers toegang hebben met hun iOS- en Android-apparaten. Als u dit beleid op app-niveau gebruikt, kunt u beheren hoe werknemers bedrijfsgegevens gebruiken en delen, zelfs als het apparaat niet wordt beheerd met Intune

U kunt [beleid voor Windows-gegevensbescherming](app-protection-policies-configure-windows-10.md) gebruiken om hetzelfde te doen voor beheerde Windows 10-apparaten. Deze beleidsregels werken zonder dat de gebruikerservaring van werknemers hierdoor wordt beïnvloed. Er zijn geen wijzigingen in uw netwerkomgeving of andere apps nodig.

### <a name="wipe-company-data-while-leaving-personal-data-intact"></a>Bedrijfsgegevens wissen met behoud van persoonlijke gegevens

Wanneer een apparaat niet langer nodig is voor het werk, voor een ander doel wordt gebruikt of is kwijtgeraakt, moet u de bedrijfs-apps en -gegevens van het apparaat kunnen verwijderen. U kunt dit doen door de mogelijkheden voor wissen en selectief wissen van Intune te gebruiken. Gebruikers kunnen via de Intune-bedrijfsportal ook op afstand gegevens wissen van de apparaten die hun persoonlijke eigendom zijn, als die zijn geregistreerd in Intune.

Met [Volledig wissen](devices-wipe.md) worden de fabrieksinstellingen van een apparaat hersteld en worden alle gebruikersgegevens en -instellingen verwijderd. Met [selectief wissen](devices-wipe.md#selective-wipe) worden alleen bedrijfsgegevens van het apparaat verwijderd, maar blijven de persoonlijke gegevens van de gebruiker intact.

Na het starten wordt het proces voor selectief wissen onmiddellijk uitgevoerd om het apparaat uit het beheer te verwijderen. Wanneer het proces is voltooid, zijn alle bedrijfsgegevens verwijderd en is de naam van het apparaat verwijderd uit de Intune-beheerconsole. Hiermee wordt het levenscyclusbeheer van het apparaat voltooid.
