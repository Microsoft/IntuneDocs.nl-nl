---
title: Veelgestelde vragen over MAM en app-beveiliging
description: In dit artikel vindt u antwoorden op enkele veelgestelde vragen over Intune Mobile Application Management (MAM) en de bescherming van apps met Intune.
keywords: ''
author: oydang
ms.author: oydang
manager: dougeby
ms.date: 01/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 149def73-9d08-494b-97b7-4ba1572f0623
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7654e5235fc30f46f67d35544a92c4bd25ac5c86
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="frequently-asked-questions-about-mam-and-app-protection"></a>Veelgestelde vragen over MAM en app-beveiliging

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In dit artikel vindt u antwoorden op enkele veelgestelde vragen over Intune Mobile Application Management (MAM) en de bescherming van apps met Intune.

## <a name="mam-basics"></a>Basisinformatie over MAM


**Wat is MAM?** [Intune Mobile Application Management](/intune/app-lifecycle) verwijst naar de suite met Intune-beheerfuncties waarmee u mobiele apps voor uw gebruikers kunt publiceren, pushen, configureren, beveiligen, controleren en bijwerken.

**Wat zijn de voordelen van het beveiligen van apps met MAM?** Met MAM worden de gegevens van een organisatie in een toepassing beveiligd. Met MAM-WE kunt u op bijna elk apparaat, inclusief persoonlijke apparaten in BYOD-scenario's (Bring-Your-Own-Device), een werk- of schoolgerelateerde app beheren die gevoelige gegevens bevat. Veel productiviteits-apps, zoals Microsoft Office-apps, kunnen worden beheerd met Intune MAM. Bekijk de officiële lijst met de [door Intune beheerde apps](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) die beschikbaar zijn voor openbaar gebruik.

**Welke apparaatconfiguraties ondersteunt MAM?** Intune MAM ondersteunt twee configuraties:
  1. **Intune MDM + MAM**: dit is de eerste configuratie die door MAM wordt ondersteund wanneer de app voor het eerst wordt gestart. IT-beheerders kunnen apps alleen met MAM en beleidsregels voor de beveiliging van apps beheren op apparaten die zijn geregistreerd bij Intune Mobile Device Management (MDM). Als klanten apps willen beheren met MDM + MAM, moeten zij de zelfstandige Intune-console op https://manage.microsoft.com gebruiken.

  2. **MAM zonder apparaatregistratie**: MAM zonder apparaatregistratie, of MAM-WE, biedt IT-beheerders de mogelijkheid apps te beheren met MAM en beleidsregels voor de beveiliging van apps op apparaten die niet zijn geregistreerd bij Intune MDM. Dit betekent dat apps door Intune kunnen worden beheerd op apparaten die zijn geregistreerd bij externe EMM providers. Als klanten apps willen beheren met MAM-WE, moeten zij de Intune-console in Azure Portal op http://portal.azure.com gebruiken.


## <a name="app-protection-policies"></a>Beleid voor app-beveiliging

**Wat zijn beleidsregels voor de beveiliging van apps**? Beleidsregels voor de beveiliging van apps zijn regels die ervoor zorgen dat de bedrijfsgegevens die zijn opgenomen in een app, veilig of binnen de app blijven. Een beleidsregel kan een regel zijn die wordt afgedwongen wanneer de gebruiker bedrijfsgegevens probeert te openen of te verplaatsen, of een reeks acties die zijn verboden of worden gecontroleerd wanneer de gebruiker zich in de app bevindt.

**Wat zijn voorbeelden van beleidsregels voor de beveiliging van apps?** Zie de [beleidsinstellingen voor de beveiliging van Android-apps](../deploy-use/android-mam-policy-settings.md) en de [beleidsinstellingen voor de beveiliging van iOS-apps](../deploy-use/ios-mam-policy-settings.md) voor gedetailleerde informatie over elke beleidsinstelling voor de beveiliging van apps.

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Apps die u kunt beheren met beleidsregels voor de beveiliging van apps

**Welke apps kunnen worden beheerd door beleidsregels voor de beveiliging van apps?** Alle apps met de functionaliteit van de [Intune App SDK](/intune/app-sdk) of die zijn ingepakt met de [Intune App Wrapping Tool](/intune/apps-prepare-mobile-application-management) kunnen worden beheerd met Intune-beleidsregels voor de beveiliging van apps. Bekijk de officiële lijst met de [door Intune beheerde apps](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) die beschikbaar zijn voor openbaar gebruik.

**Wat zijn de basisvereisten voor het gebruik van app-beveiligingsbeleidsregels voor een app die door Intune wordt beheerd?**
  1. De eindgebruiker moet een AAD-account (Azure Active Directory) hebben. Zie [Gebruikers toevoegen en beheerdersmachtigingen aan Intune toekennen](/intune/users-permissions-add) voor informatie over het maken van Intune-gebruikers in Azure Active Directory.

  2. Er moet een licentie voor Microsoft Intune Azure aan het Azure Active Directory-account van de eindgebruiker zijn toegewezen. Zie [Intune-licenties beheren](/intune/licenses-assign) voor informatie over het toewijzen van Intune-licenties aan eindgebruikers.

  3. De eindgebruiker moet behoren tot een beveiligingsgroep waarop een beleidsregel voor de beveiliging van apps is gericht. Dezelfde beleidsregel voor de beveiliging van apps moet ook zijn gericht op de specifieke app die wordt gebruikt. Beleidsregels voor de beveiliging van apps kunnen worden gemaakt en geïmplementeerd in de Intune-console in [Azure Portal](http://portal.azure.com). Beveiligingsgroepen kunnen op dit moment worden gemaakt in de [Office-portal](http://portal.office.com).

  4. De eindgebruiker moet zich aanmelden bij de app met zijn of haar AAD-account.

**Wat zijn de aanvullende vereisten voor het gebruik van de [mobiele app van Outlook](https://www.microsoft.com/outlook-com/mobile/)?**

  1. Eindgebruikers moeten de mobiele app van Outlook op hun apparaat hebben geïnstalleerd.

  2. De eindgebruiker moet een [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online)-postvak en -licentie aan het Azure Active Directory-account hebben gekoppeld.

  >[!NOTE]
  > De mobiele app van Outlook ondersteunt momenteel alleen Microsoft Exchange Online en biedt geen ondersteuning voor Exchange On-Premises of Exchange in Office 365 Dedicated.

**Wat zijn de aanvullende vereisten voor het gebruik van de apps [Word, Excel en PowerPoint](https://products.office.com/business/office)?**

  1. Eindgebruikers moeten een licentie voor [Office 365 Business of Enterprise](https://products.office.com/business/compare-more-office-365-for-business-plans) aan hun Azure Active Directory-account hebben gekoppeld. Het abonnement moet de Office-apps voor mobiele apparaten bevatten en kan een cloudopslagaccount met [OneDrive voor Bedrijven](https://onedrive.live.com/about/business/) bevatten. Office 365-licenties kunnen aan de hand van de volgende [instructies](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc) worden toegewezen in de [Office-portal](http://portal.office.com).

  2. De eindgebruiker moet een beheerde locatie hebben die is geconfigureerd met de gedetailleerde functie voor opslaan als, onder de instelling Opslaan als voorkomen van het beveiligingsbeleid voor toepassingen. Bijvoorbeeld, als OneDrive de beheerde locatie is, moet de [OneDrive](https://onedrive.live.com/about/)-app worden geconfigureerd in de Word-, Excel- of PowerPoint-app van de eindgebruiker.

  3. Als OneDrive de beheerde locatie is, moet de app het doel zijn van het app-beveiligingsbeleid dat voor de eindgebruiker is geïmplementeerd.

  >[!NOTE]
  > De mobiele Office-apps bieden momenteel alleen ondersteuning voor SharePoint Online en niet voor SharePoint On-Premises.

**Waarom is een beheerde locatie (bijvoorbeeld OneDrive) voor Office nodig?** Intune markeert alle gegevens in de app als 'zakelijk' of 'persoonlijk'. Gegevens worden als 'zakelijk' beschouwd wanneer ze afkomstig zijn van een bedrijfslocatie. Voor Office-apps worden de volgende locaties door Intune beschouwd als bedrijfslocaties: e-mail (Exchange) of cloudopslag (OneDrive-app met een OneDrive voor Bedrijven-account).

**Wat zijn de aanvullende vereisten voor het gebruik van Skype voor Bedrijven?** Zie de licentievereisten voor [Skype voor Bedrijven](https://products.office.com/skype-for-business/it-pros).
  >[!NOTE]
  > De mobiel app van Skype voor Bedrijven biedt momenteel alleen ondersteuning voor Skype voor Bedrijven Online.

## <a name="app-protection-features"></a>Functies voor app-beveiliging

**Wat is ondersteuning voor meerdere identiteiten?** Via ondersteuning voor meerdere identiteiten kan de Intune App SDK beleidsregels voor de beveiliging van apps toepassen op alleen het werk- of schoolaccount dat is aangemeld bij de app. Als een persoonlijk account is aangemeld bij de app, blijven de gegevens ongewijzigd.

**Wat is het doel van ondersteuning voor meerdere identiteiten?** Dankzij ondersteuning voor meerdere identiteiten kunnen apps met zowel een zakelijke als particuliere doelgroep (oftewel de Office-apps) openbaar worden vrijgegeven met app-beveiligingsfuncties van Intune voor de 'zakelijke' accounts.

**Outlook en meerdere identiteiten** Aangezien Outlook een gecombineerde e-mailweergave heeft met zowel persoonlijke als 'zakelijke' e-mails, wordt er naar de Intune-pincode gevraagd zodra Outlook wordt gestart.

**Wat is de pincode voor de Intune-app?** De pincode is een wachtwoordcode die wordt gebruikt om te verifiëren of de juiste gebruiker de bedrijfsgegevens in een app benadert.

  1. **Wanneer wordt de gebruiker gevraagd een pincode op te geven?** Intune vraagt alleen naar de pincode van de gebruiker wanneer de gebruiker 'zakelijke' gegevens benadert. In apps met functionaliteit voor meerdere identiteiten, zoals Word/Excel/PowerPoint, wordt de gebruiker naar een de pincode gevraagd wanneer ze een 'zakelijk' document of bestand willen openen. In apps waarvoor maar één identiteit kan worden gebruikt, zoals Line-Of-Business-apps met de Intune App Wrapping Tool-functionaliteit, wordt gelijk bij het starten van de app om de pincode gevraagd, omdat de Intune App SDK weet dat de gebruik de app uitsluitend 'zakelijk' gebruikt.

2. **Hoe vaak wordt de gebruiker gevraagd de pincode voor Intune in te voeren?**
De IT-beheerder kan de beleidsinstelling voor beveiliging van de Intune-app in de Intune-beheerconsole instellen op Toegangsvereisten opnieuw controleren na (minuten). Deze instelling geeft de hoeveelheid tijd aan voordat de toegangsvereisten op het apparaat worden gecontroleerd en het scherm voor de pincode opnieuw wordt weergegeven. Belangrijke informatie over de pincode die van invloed is op hoe vaak de gebruiker om de pincode wordt gevraagd, is: 

* **De pincode wordt gedeeld tussen apps van dezelfde uitgever om de bruikbaarheid te verbeteren:** In iOS wordt de pincode voor apps gedeeld met alle apps **van dezelfde uitgever**. Op Android wordt één pincode voor apps gedeeld met alle andere apps.
* **De werking van de timer die aan de pincode is gekoppeld:** Zodra een pincode wordt ingevoerd voor toegang tot een app (app A) en de app de voorgrond op het apparaat verlaat, wordt de timer voor die pincode opnieuw ingesteld. Voor elke app (app B) die deze pincode deelt, wordt de gebruiker niet om de pincode gevraagd, omdat de timer opnieuw is ingesteld. De prompt verschijnt zodra opnieuw aan de waarde voor Toegangsvereisten opnieuw controleren na (minuten) is voldaan. 

>[!NOTE] 
> On de toegangsvereisten van gebruikers vaker te controleren, met name voor een veelgebruikte app, wordt aanbevolen om de waarde voor de instelling Toegangsvereisten opnieuw controleren na (minuten) te verlagen. 

  3. **Is de pincode veilig?** De pincode zorgt ervoor dat alleen de juiste gebruiker toegang heeft tot de gegevens van de organisatie in de app. Daarom moet een eindgebruikers zich aanmelden met een werk- of schoolaccount voordat de pincode voor de Intune-app kan worden ingesteld of hersteld. Deze verificatie wordt verwerkt door Azure Active Directory via uitwisseling van een beveiligde token en is niet transparant voor de Intune App SDK. Vanuit het oogpunt van veiligheid kunt u werk- of schoolgerelateerde gegevens het beste versleutelen. Versleuteling is niet gerelateerd aan de pincode van de app, maar is een eigen app-beveiligingsbeleid.

  4. **Hoe beschermt Intune de pincode tegen beveiligingsaanvallen?** Als onderdeel van het app-pincodebeleid kan de IT-beheerder een maximumaantal verificatiepogingen voor gebruikers instellen voordat de app wordt vergrendeld. Na het toegestane aantal aanmeldingspogingen kan de Intune App SDK de 'zakelijke' gegevens in de app wissen.
  
  5. **Waarom moet ik een pincode tweemaal instellen voor apps van dezelfde uitgever?**
Voor MAM (op iOS) kan momenteel een pincode op toepassingsniveau worden gebruikt met alfanumerieke tekens en speciale tekens (wachtwoordcode genoemd) waarvoor de deelname van toepassingen (zoals WXP, Outlook, Managed Browser, Yammer) is vereist om de Intune APP SDK voor iOS te integreren. Zonder deze deelname, worden de instellingen voor de wachtwoordcode niet goed afgedwongen voor de betreffende toepassingen. Dit is een functie die is uitgebracht in de Intune SDK voor iOS v. 7.1.12. <br> Om deze functie te ondersteunen en te zorgen voor compatibiliteit met eerdere versies van de Intune SDK voor iOS, worden alle pincodes (numeriek of als wachtwoordcode) in 7.1.12+ los van de pincode in eerdere versies van de SDK verwerkt. Dus als een apparaat toepassingen met Intune SDK voor iOS-versies lager dan 7.1.12 EN hoger dan 7.1.12 van dezelfde uitgever heeft, moeten er twee pincodes worden ingesteld. <br><br> Die twee pincodes (voor elke app) staan echter volledig los van elkaar: ze moeten voldoen aan het app-beveiligingsbeleid dat voor die app geldt. Dus *alleen* als voor app A en app B hetzelfde beleid is toegepast (met betrekking tot pincodes), kan de gebruiker dezelfde pincode tweemaal instellen. <br><br> Dit gedrag is specifiek voor de pincode voor iOS-toepassingen die ingeschakeld zijn met het Intune-beheer van mobiele apps. Na verloop van tijd, wanneer toepassingen nieuwere versies van de Intune SDK voor iOS overnemen, wordt het tweemaal instellen van een pincode voor apps van dezelfde uitgever minder problematisch. Zie de opmerking hieronder voor een voorbeeld.

>[!NOTE]
> Als app A bijvoorbeeld gemaakt is met een eerdere versie dan 7.1.12 en app B met een versie die hoger is dan of gelijk is aan 7.1.12 van dezelfde uitgever, moet de eindgebruiker afzonderlijke pincodes instellen voor A en B als beide op een iOS-apparaat zijn geïnstalleerd. <br> Als een app C met SDK-versie 7.1.9 op het apparaat is geïnstalleerd, gebruikt die app dezelfde pincode als app A. <br> Een app D die gemaakt is met 7.1.14, gebruikt dezelfde pincode als app B. <br> Als alleen app A en app C op een apparaat zijn geïnstalleerd, hoeft er maar één pincode worden ingesteld. Hetzelfde geldt als alleen app B en app D op een apparaat zijn geïnstalleerd.

**Versleuteling** IT-beheerders kunnen een app-beveiligingsbeleid instellen dat vereist dat de gegevens in de app worden versleuteld. De IT-beheerder kan als onderdeel van het beleid ook opgeven wanneer de inhoud wordt versleuteld.

  1. **Hoe worden gegevens versleuteld met Intune?** Zie de [beleidsinstellingen voor de beveiliging van Android-apps](../deploy-use/android-mam-policy-settings.md) en de [beleidsinstellingen voor de beveiliging van iOS-apps](../deploy-use/ios-mam-policy-settings.md) voor gedetailleerde informatie over elke beleidsinstelling voor de beveiliging van apps.

  2. **Wat wordt versleuteld?** Alleen gegevens die zijn gemarkeerd als 'zakelijk' worden versleuteld overeenkomstig het app-beveiligingsbeleid van de IT-beheerder. Gegevens worden als 'zakelijk' beschouwd wanneer ze afkomstig zijn van een bedrijfslocatie. Voor Office-apps worden de volgende locaties door Intune beschouwd als bedrijfslocaties: e-mail (Exchange) of cloudopslag (OneDrive-app met een OneDrive voor Bedrijven-account). Alle app-gegevens in Line-Of-Business-apps met Intune App Wrapping Tool-functionaliteit worden beschouwd als 'zakelijk'.

**Hoe worden gegevens extern gewist met Intune?** In Intune kunnen app-gegevens op drie verschillende manieren worden gewist: volledig apparaat wissen, selectief wissen voor MDM en selectief wissen voor MAM. Zie [Uw gegevens beveiligen met volledig wissen of selectief wissen met Microsoft Intune](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) voor meer informatie over wissen op afstand voor MDM. Zie [Bedrijfsgegevens van beheerde apps wissen met Microsoft Intune](../deploy-use/wipe-managed-company-app-data-with-microsoft-intune.md) voor meer informatie over selectief wissen met MAM.

  1. **Wat is volledig wissen?** Met [Volledig wissen](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe) verwijdert u alle gebruikersgegevens en instellingen van **het apparaat** door het apparaat terug te zetten op de standaardfabrieksinstellingen. Het apparaat wordt uit Intune verwijderd.
  >[!NOTE]
  > Alleen apparaten die zijn geregistreerd bij Intune Mobile Device Management (MDM) kunnen volledig worden gewist.

  2. **Wat is selectief wissen voor MDM?** Zie [Uw gegevens beveiligen met volledig wissen of selectief wissen met Microsoft Intune](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) voor meer informatie over selectief wissen.

  3. **Wat is selectief wissen voor MAM?** Bij selectief wissen voor MAM worden gegevens van bedrijfs-apps gewoon gewist uit een app. De aanvraag wordt gestart via de Intune Azure-portal. Zie [Bedrijfsgegevens van beheerde apps wissen met Microsoft Intune](../deploy-use/wipe-managed-company-app-data-with-microsoft-intune.md) voor meer informatie over het initiëren van een wisaanvraag.

  4. **Hoe snel wordt selectief wissen voor MAM uitgevoerd?** Als de gebruiker de app gebruikt wanneer selectief wissen wordt gestart, controleert de Intune App SDK om de 30 minuten op aanvragen van de MAM-service voor selectief wissen. Daarnaast wordt er gecontroleerd of er een aanvraag voor selectief wissen is verzonden wanneer de gebruiker de app voor de eerste keer start en zich aanmeldt met een werk- of schoolaccount.

**Waarom kunnen er geen on-premises services (on-prem) worden gebruikt in combinatie met apps die zijn beveiligd met Intune?** Voor de app-beveiliging van Intune moet de identiteit van de gebruiker voor de toepassing en Intune App SDK consistent zijn. Dit kan alleen worden gegarandeerd via moderne verificatie. Er zijn scenario's waarin apps met een on-premisses configuratie werken, maar deze zijn niet consistent en kunnen ook niet worden gegarandeerd.

**Is er een veilige manier om webkoppelingen te openen vanuit beheerde apps?** Ja. De IT-beheerder kan een app-beveiligingsbeleid implementeren en instellen voor de [Intune Managed Browser-app](../deploy-use/manage-internet-access-using-managed-browser-policies.md), een webbrowser die is ontwikkeld door Microsoft Intune en eenvoudig kan worden beheerd met Intune. De IT-beheerder kan ervoor zorgen dat alle webkoppelingen in de door Intune beheerde apps moeten worden geopend met de Managed Browser-app.


## <a name="app-experience-on-android"></a>Apps op Android gebruiken

**Waarom is de bedrijfsportal-app op Android-apparaten nodig voor app-beveiliging met Intune?** Veel van de functies voor het beveiligen van apps zijn ingebouwd in de bedrijfsportal-app. Hoewel de bedrijfsportal-app altijd vereist is, hoeft een apparaat _niet te worden geregistreerd_. Voor MAM-WE moet de eindgebruiker de bedrijfsportal-app op het apparaat hebben geïnstalleerd.

## <a name="app-experience-on-ios"></a>Apps op iOS gebruiken

**Ik kan de iOS-extensie voor delen gebruiken om werk- of schoolgegevens te openen in niet-beheerde apps, zelfs wanneer het beleid voor het overdragen van gegevens is ingesteld op 'alleen voor beheerde apps' of 'geen apps'. Ontstaat hierdoor geen gegevenslek?** De iOS-extensie voor delen kan alleen met het app-beveiligingsbeleid worden beheerd als ook het apparaat wordt beheerd. Daarom worden _**'zakelijke' gegevens door Intune versleuteld voordat ze buiten de app worden gedeeld**_. U kunt dit controleren door een 'zakelijk' bestand te openen buiten de beheerde app. Het bestand moet zijn versleuteld en kan niet worden geopend bijten de beheerde app.

### <a name="see-also"></a>Zie ook
- [Mobile Application Management-beleidsinstellingen voor Android in Microsoft Intune](../deploy-use/android-mam-policy-settings.md)
- [Mobile Application Management-beleidsinstellingen voor iOS](../deploy-use/ios-mam-policy-settings.md)
- [De Mobile Application Management-configuratie valideren](../deploy-use/validate-mobile-application-management.md)
- [Voorbereidingen voor het configureren van beleid voor het beheer van mobiele apps (Mobile App Management) met Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
- [Ondersteuning voor Microsoft Intune krijgen](../troubleshoot/how-to-get-support-for-microsoft-intune.md)
