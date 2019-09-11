---
title: Veelgestelde vragen over MAM en app-beveiliging
description: In dit artikel vindt u antwoorden op enkele veelgestelde vragen over Intune Mobile Application Management (MAM) en de bescherming van apps met Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 149def73-9d08-494b-97b7-4ba1572f0623
ms.reviewer: erikre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 28a7838e174d84dd15592c9e4f6d3e40bc679a90
ms.sourcegitcommit: a25cd79a33feb536d9b2fc11aa7d3e3972f1ca5a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2019
ms.locfileid: "70842104"
---
# <a name="frequently-asked-questions-about-mam-and-app-protection"></a>Veelgestelde vragen over MAM en app-beveiliging

In dit artikel vindt u antwoorden op enkele veelgestelde vragen over Intune Mobile Application Management (MAM) en de bescherming van apps met Intune.

## <a name="mam-basics"></a>Basisinformatie over MAM

**Wat is MAM?**<br></br>
[Intune Mobile Application Management](/intune/app-lifecycle) verwijst naar de suite met Intune-beheerfuncties waarmee u mobiele apps voor uw gebruikers kunt publiceren, pushen, configureren, beveiligen, controleren en bijwerken.

**Wat zijn de voordelen van het beveiligen van apps met MAM?**<br></br>
Met MAM worden de gegevens van een organisatie in een toepassing beveiligd. Met MAM zonder registratie (MAM-WE) kunt u op bijna elk apparaat, inclusief persoonlijke apparaten in BYOD-scenario's (Bring-Your-Own-Device), een werk- of schoolgerelateerde app beheren die gevoelige gegevens bevat. Veel productiviteits-apps, zoals Microsoft Office-apps, kunnen worden beheerd met Intune MAM. Bekijk de officiële lijst met de [door Intune beheerde apps](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) die beschikbaar zijn voor openbaar gebruik.

**Welke apparaatconfiguraties ondersteunt MAM?**<br></br>
Intune MAM ondersteunt twee configuraties:
- **Intune MDM + MAM**: IT-beheerders kunnen apps alleen met MAM en beleidsregels voor de beveiliging van apps beheren op apparaten die zijn geregistreerd bij Intune Mobile Device Management (MDM). Als klanten apps willen beheren met MDM + MAM, moeten zij de Intune-console Azure Portal op https://portal.azure.com gebruiken.

- **MAM zonder apparaatregistratie**: MAM zonder apparaatregistratie, of MAM-WE, biedt IT-beheerders de mogelijkheid apps te beheren met MAM en beleidsregels voor app-beveiliging op apparaten die niet zijn geregistreerd met Intune MDM. Dit betekent dat apps door Intune kunnen worden beheerd op apparaten die zijn geregistreerd bij externe EMM providers. Als klanten apps willen beheren met MAM-WE, moeten zij de Intune-console in Azure Portal op https://portal.azure.com gebruiken. Apps kunnen ook door Intune worden beheerd op apparaten die zijn geregistreerd bij externe Enterprise Mobility Management-providers of die helemaal niet bij een MDM zijn geregistreerd.


## <a name="app-protection-policies"></a>Beleid voor app-beveiliging

**Wat zijn beleidsregels voor de beveiliging van apps?**<br></br>
Beleidsregels voor de beveiliging van apps zijn regels die ervoor zorgen dat de bedrijfsgegevens die zijn opgenomen in een app, veilig of binnen de app blijven. Een beleidsregel kan een regel zijn die wordt afgedwongen wanneer de gebruiker bedrijfsgegevens probeert te openen of te verplaatsen, of een reeks acties die zijn verboden of worden gecontroleerd wanneer de gebruiker zich in de app bevindt.

**Wat zijn voorbeelden van beleidsregels voor de beveiliging van apps?**<br></br>
Zie de [beleidsinstellingen voor de beveiliging van Android-apps](app-protection-policy-settings-android.md) en de [beleidsinstellingen voor de beveiliging van iOS-apps](app-protection-policy-settings-ios.md) voor gedetailleerde informatie over elke beleidsinstelling voor de beveiliging van apps.

**Is het mogelijk om op hetzelfde moment, maar voor verschillende apparaten, beleid van zowel MDM als MAM toe te passen op dezelfde gebruiker? Bijvoorbeeld in een situatie waarin een gebruiker thuis toegang kan krijgen tot bedrijfsresources vanaf een eigen computer met MAM, maar ook op kantoor vanaf een apparaat dat met Intune MDM wordt beheerd. Zijn er nog aandachtspunten voor dit idee?**<br></br>
Als u een MAM-beleid toepast op de gebruiker zonder de apparaatstatus in te stellen, krijgt de gebruiker het MAM-beleid op zowel het BYOD-apparaat als het door Intune beheerde apparaat. U kunt een MAM-beleid ook toepassen op basis van de beheerde status. Bij het maken van een beleid voor de beveiliging van apps selecteert u dan Nee voor Doel voor alle app-typen. Ga vervolgens op een van de volgende manieren te werk:
- Pas een minder streng MAM-beleid toe op apparaten die met Intune worden beheerd en een meer beperkend MAM-beleid op apparaten die niet bij MDM zijn ingeschreven.
- Pas alleen een MAM-beleid toe op niet-ingeschreven apparaten.

Zie [How to monitor app protection policies](app-protection-policies-monitor.md) (App-beveiligingsbeleid controleren) voor meer informatie.

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Apps die u kunt beheren met beleidsregels voor de beveiliging van apps

**Welke apps kunnen worden beheerd door beleidsregels voor de beveiliging van apps?**<br></br>
Alle apps die zijn geïntegreerd met de [Intune App SDK](/intune/app-sdk) of die zijn ingepakt met de [Intune App Wrapping Tool](/intune/apps-prepare-mobile-application-management), kunnen worden beheerd met Intune-beleidsregels voor de beveiliging van apps. Bekijk de officiële lijst met de [door Intune beheerde apps](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) die beschikbaar zijn voor openbaar gebruik.

**Wat zijn de basisvereisten voor het gebruik van app-beveiligingsbeleidsregels voor een app die door Intune wordt beheerd?**

- De eindgebruiker moet een AAD-account (Azure Active Directory) hebben. Zie [Gebruikers toevoegen en beheerdersmachtigingen aan Intune toekennen](/intune/users-permissions-add) voor informatie over het maken van Intune-gebruikers in Azure Active Directory.

- Er moet een licentie voor Microsoft Intune Azure aan het Azure Active Directory-account van de eindgebruiker zijn toegewezen. Zie [Intune-licenties beheren](/intune/licenses-assign) voor informatie over het toewijzen van Intune-licenties aan eindgebruikers.

- De eindgebruiker moet behoren tot een beveiligingsgroep waarop een beleidsregel voor de beveiliging van apps is gericht. Dezelfde beleidsregel voor de beveiliging van apps moet ook zijn gericht op de specifieke app die wordt gebruikt. Beleidsregels voor de beveiliging van apps kunnen worden gemaakt en geïmplementeerd in de Intune-console in [Azure Portal](https://portal.azure.com). Beveiligingsgroepen kunnen op dit moment worden gemaakt in het [Microsoft 365-beheercentrum](https://admin.microsoft.com).

- De eindgebruiker moet zich bij de app aanmelden met zijn AAD-account.

**Wat zijn de mogelijkheden als ik een app met Intune-app-beveiliging wil inschakelen, maar die app geen ondersteund platform voor app-ontwikkeling gebruikt?** 

Het Intune SDK-ontwikkelingsteam houdt zich actief bezig met het testen en onderhouden van ondersteuning voor apps die zijn gebouwd met de systeemeigen Android-, iOS- (Objective-C, Swift), Xamarin-, Xamarin.Forms- en Cordova-platforms. Hoewel het sommige klanten is gelukt om de Intune SDK te integreren in andere platforms, zoals React Native en NativeScript, bieden we geen specifieke instructies of plug-ins voor app-ontwikkelaars die andere platforms gebruiken dan de platforms die door ons worden ondersteund.

**Ondersteunt de Intune APP SDK de bibliotheek voor Microsoft-verificatie (MSAL) of sociale accounts?**<br></br>
De Intune APP SDK gebruikt enkele geavanceerde mogelijkheden van ADAL voor zowel eigen als externe versies van de SDK. Hierdoor werkt MSAL niet goed met de meeste belangrijkste scenario's, zoals verificatie in de Intune-app-beveiligingsservice en voorwaardelijk starten. Gezien het feit dat het Identity-team van Microsoft gebruikers over het algemeen aanraadt om voor alle Microsoft Office-apps over te stappen naar MSAL, zal de Intune SDK daar uiteindelijk ondersteuning voor moeten gaan bieden, maar hier zijn momenteel nog geen plannen voor.

**Wat zijn de aanvullende vereisten voor het gebruik van de [mobiele app van Outlook](https://products.office.com/outlook)?**

- De eindgebruiker moet de mobiele app van Outlook op zijn apparaat hebben geïnstalleerd.

- De eindgebruiker moet een [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online)-postvak en -licentie aan het Azure Active Directory-account hebben gekoppeld.

  >[!NOTE]
  > De mobiele app van Outlook ondersteunt momenteel alleen Intune-app-beveiliging voor Microsoft Exchange Online en [Exchange Server met hybride moderne verificatie](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx) en biedt geen ondersteuning voor Exchange in Office 365 Dedicated.

**Wat zijn de aanvullende vereisten voor het gebruik van de apps [Word, Excel en PowerPoint](https://products.office.com/business/office)?**

- De eindgebruiker moet een licentie voor [Office 365 Business of Enterprise](https://products.office.com/business/compare-more-office-365-for-business-plans) aan zijn Azure Active Directory-account hebben gekoppeld. Het abonnement moet de Office-apps voor mobiele apparaten bevatten en kan een cloudopslagaccount met [OneDrive voor Bedrijven](https://onedrive.live.com/about/business/) bevatten. Office 365-licenties kunnen aan de hand van de volgende [instructies](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc) worden toegewezen in het [Microsoft 365-beheercentrum](https://admin.microsoft.com).

- De eindgebruiker moet een beheerde locatie hebben die is geconfigureerd met de gedetailleerde functie voor 'opslaan als', onder de instelling 'Opslaan als voorkomen' van het beveiligingsbeleid voor toepassingen. Als bijvoorbeeld OneDrive de beheerde locatie is, moet de [OneDrive](https://onedrive.live.com/about/)-app worden geconfigureerd in de Word-, Excel- of PowerPoint-app van de eindgebruiker.

- Als OneDrive de beheerde locatie is, moet de app het doel zijn van het app-beveiligingsbeleid dat voor de eindgebruiker is geïmplementeerd.

  >[!NOTE]
  > De mobiele Office-apps bieden momenteel alleen ondersteuning voor SharePoint Online en niet voor SharePoint On-Premises.

**Waarom is er een beheerde locatie (bijvoorbeeld OneDrive) voor Office nodig?**<br></br>
Intune markeert alle gegevens in de app als 'zakelijk' of 'persoonlijk'. Gegevens worden als 'zakelijk' beschouwd wanneer ze afkomstig zijn van een bedrijfslocatie. Voor Office-apps worden de volgende locaties door Intune beschouwd als bedrijfslocaties: e-mail (Exchange) of cloudopslag (OneDrive-app met een OneDrive voor Bedrijven-account).

**Wat zijn de aanvullende vereisten voor het gebruik van Skype voor Bedrijven?**<br></br>
Zie de licentievereisten voor [Skype voor Bedrijven](https://products.office.com/skype-for-business/it-pros). Zie respectievelijk [Hybride moderne verificatie voor SfB en Exchange wordt algemeen beschikbaar (GA)](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Hybrid-Modern-Auth-for-SfB-and-Exchange-goes-GA/ba-p/134756) en [Moderne verificatie voor on-premises SfB met AAD](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Modern-Auth-for-SfB-OnPrem-with-AAD/ba-p/180910) voor hybride en on-premises configuraties van Skype voor Bedrijven (SfB).

## <a name="app-protection-features"></a>Functies voor app-beveiliging

**Wat is ondersteuning voor meerdere identiteiten?**<br></br>
Via ondersteuning voor meerdere identiteiten kan de Intune App SDK beleidsregels voor de beveiliging van apps toepassen op alleen het werk- of schoolaccount dat is aangemeld bij de app. Als een persoonlijk account is aangemeld bij de app, blijven de gegevens ongewijzigd.

**Wat is het doel van ondersteuning voor meerdere identiteiten?**<br></br>
Dankzij ondersteuning voor meerdere identiteiten kunnen apps met zowel een zakelijke als een particuliere doelgroep (oftewel de Office-apps) openbaar worden vrijgegeven met app-beveiligingsfuncties van Intune voor de 'zakelijke' accounts.

**Outlook en meerdere identiteiten**<br></br>
Aangezien Outlook een gecombineerde e-mailweergave heeft met zowel persoonlijke als 'zakelijke' e-mails, wordt er naar de Intune-pincode gevraagd zodra Outlook wordt gestart.

**Wat is de pincode voor de Intune-app?**<br></br>
De pincode is een wachtwoordcode die wordt gebruikt om te verifiëren of de juiste gebruiker de bedrijfsgegevens in een app benadert.

- **Wanneer wordt de gebruiker gevraagd een pincode op te geven?**<br></br> Intune vraagt naar de pincode van de gebruiker wanneer de gebruiker 'zakelijke' gegevens benadert. In apps met functionaliteit voor meerdere identiteiten, zoals Word/Excel/PowerPoint, wordt de gebruiker naar een de pincode gevraagd wanneer ze een 'zakelijk' document of bestand willen openen. In apps waarvoor maar één identiteit kan worden gebruikt, zoals Line-Of-Business-apps die worden beheerd met de Intune App Wrapping Tool-functionaliteit, wordt gelijk bij het starten van de app om de pincode gevraagd, omdat de Intune App SDK weet dat de gebruiker de app uitsluitend 'zakelijk' gebruikt.

- **Hoe vaak wordt de gebruiker gevraagd de pincode voor Intune in te voeren?**<br></br> De IT-beheerder kan de beleidsinstelling voor beveiliging van de Intune-app in de Intune-beheerconsole instellen op Toegangsvereisten opnieuw controleren na (minuten). Deze instelling geeft de hoeveelheid tijd aan voordat de toegangsvereisten op het apparaat worden gecontroleerd en het scherm voor de pincode opnieuw wordt weergegeven. Belangrijke informatie over de pincode die van invloed is op hoe vaak de gebruiker om de pincode wordt gevraagd, is: 

  - **De pincode wordt gedeeld door apps van dezelfde uitgever om de bruikbaarheid te verbeteren:** Op iOS wordt één pincode voor apps gedeeld door alle apps **van dezelfde app-uitgever**. Op Android wordt één pincode voor apps gedeeld met alle andere apps.
  - **Het gedrag van 'Toegangsvereisten opnieuw controleren na (minuten)' na het opnieuw opstarten van een apparaat:** een 'timer van de pincode' houdt het aantal minuten van inactiviteit bij waarna de pincode voor de Intune-app opnieuw moet worden weergegeven. In iOS wordt de timer van de pincode niet beïnvloed door het opnieuw starten van het apparaat. Het opnieuw starten van het apparaat is dus niet van invloed op het aantal minuten dat de gebruiker niet actief is in een iOS-app waarvoor het Intune-pincodebeleid is ingesteld. In Android wordt de timer van de pincode opnieuw ingesteld bij het opnieuw starten van het apparaat. Hierdoor vragen Android-apps waarvoor het Intune-pincodebeleid is ingesteld waarschijnlijk om de pincode voor de app, ongeacht de instelling 'Toegangsvereisten opnieuw controleren na (minuten)' **na het opnieuw starten van een apparaat**.  
  - **De werking van de timer die aan de pincode is gekoppeld:** zodra een pincode wordt ingevoerd voor toegang tot een app (app A) en de app de voorgrond (primaire invoerfocus) op het apparaat verlaat, wordt de timer voor die pincode opnieuw ingesteld. Voor elke app (app B) die deze pincode deelt, wordt de gebruiker niet om de pincode gevraagd, omdat de timer opnieuw is ingesteld. De prompt verschijnt zodra opnieuw aan de waarde voor Toegangsvereisten opnieuw controleren na (minuten) is voldaan.

Zelfs als de pincode wordt gedeeld met apps van andere uitgevers verschijnt bij iOS-apparaten de prompt opnieuw wanneer opnieuw is voldaan aan de waarde **Toegangsvereisten na (minuten) opnieuw controleren** voor de app die niet de belangrijkste invoerfocus is. Een gebruiker heeft bijvoorbeeld app _A_ van uitgever _X_ en app _B_ van uitgever _Y_ en deze twee apps delen dezelfde pincode. De gebruiker is gericht op app _A_ (voorgrond) en app _B_ wordt geminimaliseerd. Nadat is voldaan aan de waarde **Toegangsvereisten na (minuten) opnieuw controleren** en de gebruiker overschakelt naar de app _B_, is de pincode vereist.

  >[!NOTE] 
  > Als u wilt dat de toegangsvereisten van de gebruiker vaker worden gecontroleerd (oftewel dat er om een pincode wordt gevraagd), met name voor een veelgebruikte app, wordt aanbevolen om de waarde voor de instelling 'Toegangsvereisten opnieuw controleren na (minuten)' te verlagen. 
      
- **Hoe werkt de pincode van Intune met de ingebouwde pincodes van apps voor Outlook en OneDrive?**<br></br>
De pincode van Intune werkt op basis van een timer van inactiviteit (ofwel de waarde voor Toegangsvereisten opnieuw controleren na (minuten)). Er wordt dus gevraagd om de pincode van Intune. Dit is onafhankelijk van de prompts voor de pincode van de app voor Outlook en OneDrive, die vaak standaard verschijnen bij het starten van de app. Als beide prompts tegelijk worden weergegeven, moet de pincode van Intune voorrang krijgen. 

- **Is de pincode veilig?**<br></br> De pincode zorgt ervoor dat alleen de juiste gebruiker toegang heeft tot de gegevens van de organisatie in de app. Daarom moet een eindgebruiker zich aanmelden met een werk- of schoolaccount voordat de pincode voor de Intune-app kan worden ingesteld of hersteld. Deze verificatie wordt verwerkt door Azure Active Directory via uitwisseling van een beveiligde token en is niet transparant voor de Intune App SDK. Vanuit het oogpunt van veiligheid kunt u werk- of schoolgerelateerde gegevens het beste versleutelen. Versleuteling is niet gerelateerd aan de pincode van de app, maar is een eigen app-beveiligingsbeleid.

- **Hoe beschermt Intune de pincode tegen beveiligingsaanvallen?**<br></br> Als onderdeel van het app-pincodebeleid kan de IT-beheerder een maximumaantal verificatiepogingen voor gebruikers instellen voordat de app wordt vergrendeld. Na het toegestane aantal aanmeldingspogingen kan de Intune App SDK de 'zakelijke' gegevens in de app wissen.
  
- **Waarom moet ik een pincode tweemaal instellen voor apps van dezelfde uitgever?**<br></br> Voor MAM (op iOS) kan momenteel een pincode op toepassingsniveau worden gebruikt met alfanumerieke tekens en speciale tekens (wachtwoordcode genoemd) waarvoor de deelname van toepassingen (zoals WXP, Outlook, Managed Browser, Yammer) is vereist om te integreren met de Intune App SDK voor iOS. Zonder deze deelname, worden de instellingen voor de wachtwoordcode niet goed afgedwongen voor de betreffende toepassingen. Dit is een functie die is uitgebracht in de Intune SDK voor iOS v. 7.1.12. <br><br> Om deze functie te ondersteunen en te zorgen voor compatibiliteit met eerdere versies van de Intune SDK voor iOS, worden alle pincodes (numeriek of als wachtwoordcode) in 7.1.12+ los van de pincode in eerdere versies van de SDK verwerkt. Dus als een apparaat toepassingen met Intune SDK voor iOS-versies lager dan 7.1.12 EN hoger dan 7.1.12 van dezelfde uitgever heeft, moeten er twee pincodes worden ingesteld. <br><br> Die twee pincodes (voor elke app) staan echter volledig los van elkaar: ze moeten voldoen aan het app-beveiligingsbeleid dat voor die app geldt. Dus *alleen* als voor app A en app B hetzelfde beleid is toegepast (met betrekking tot pincodes), kan de gebruiker dezelfde pincode tweemaal instellen. <br><br> Dit gedrag is specifiek voor de pincode voor iOS-toepassingen die ingeschakeld zijn met het Intune-beheer van mobiele apps. Na verloop van tijd, wanneer toepassingen nieuwere versies van de Intune SDK voor iOS overnemen, wordt het tweemaal instellen van een pincode voor apps van dezelfde uitgever minder problematisch. Zie de opmerking hieronder voor een voorbeeld.

  >[!NOTE]
  > Als app A bijvoorbeeld gemaakt is met een eerdere versie dan 7.1.12 en app B met een versie die hoger is dan of gelijk is aan 7.1.12 van dezelfde uitgever, moet de eindgebruiker afzonderlijke pincodes instellen voor A en B als beide op een iOS-apparaat zijn geïnstalleerd. <br><br> Als een app C met SDK-versie 7.1.9 op het apparaat is geïnstalleerd, gebruikt die app dezelfde pincode als app A. <br><br> Een app D die gemaakt is met 7.1.14, gebruikt dezelfde pincode als app B. <br><br> Als alleen app A en app C op een apparaat zijn geïnstalleerd, hoeft er maar één pincode worden ingesteld. Hetzelfde geldt als alleen app B en app D op een apparaat zijn geïnstalleerd.

**Versleuteling**<br></br>
IT-beheerders kunnen een app-beveiligingsbeleid instellen dat vereist dat de gegevens in de app worden versleuteld. De IT-beheerder kan als onderdeel van het beleid ook opgeven wanneer de inhoud wordt versleuteld.

- **Hoe worden gegevens versleuteld met Intune?**<br></br> Zie de [beleidsinstellingen voor de beveiliging van Android-apps](app-protection-policy-settings-android.md) en de [beleidsinstellingen voor de beveiliging van iOS-apps](app-protection-policy-settings-ios.md) voor gedetailleerde informatie over elke beleidsinstelling voor de beveiliging van apps.

- **Wat wordt versleuteld?**<br></br> Alleen gegevens die zijn gemarkeerd als 'zakelijk' worden versleuteld overeenkomstig het app-beveiligingsbeleid van de IT-beheerder. Gegevens worden als 'zakelijk' beschouwd wanneer ze afkomstig zijn van een bedrijfslocatie. Voor Office-apps worden de volgende locaties door Intune beschouwd als bedrijfslocaties: e-mail (Exchange) of cloudopslag (OneDrive-app met een OneDrive voor Bedrijven-account). Alle app-gegevens in Line-Of-Business-apps die worden beheerd door de Intune App Wrapping Tool-functionaliteit, worden beschouwd als 'zakelijk'.

**Hoe worden gegevens extern gewist met Intune?**<br></br>
In Intune kunnen app-gegevens op drie verschillende manieren worden gewist: volledig apparaat wissen, selectief wissen voor MDM en selectief wissen voor MAM. Raadpleeg [Apparaten verwijderen door wissen of buiten gebruik stellen](devices-wipe.md) voor meer informatie over wissen op afstand voor MDM. Raadpleeg [de actie Buiten gebruik stellen](devices-wipe.md#retire) en [Alleen zakelijke gegevens wissen uit apps](apps-selective-wipe.md) voor meer informatie over selectief wissen met behulp van MAM.

- **Wat is wissen?**<br></br> Met [Wissen](devices-wipe.md) verwijdert u alle gebruikersgegevens en instellingen van **het apparaat** door op het apparaat de fabrieksinstellingen te herstellen. Het apparaat wordt uit Intune verwijderd.
  >[!NOTE]
  > Alleen apparaten die zijn geregistreerd bij Intune Mobile Device Management (MDM) kunnen worden gewist.

- **Wat is selectief wissen voor MDM?**<br></br> Raadpleeg [Apparaten verwijderen - buiten gebruik stellen](devices-wipe.md#retire) voor meer informatie over het verwijderen van zakelijke gegevens.

- **Wat is selectief wissen voor MAM?**<br></br> Bij selectief wissen voor MAM worden gegevens van bedrijfs-apps gewoon gewist uit een app. De aanvraag wordt gestart via de Intune Azure-portal. Raadpleeg [Alleen zakelijke gegevens wissen uit door Intune beheerde apps](apps-selective-wipe.md) voor meer informatie over hoe u een verzoek om te wissen aanvraagt.

- **Hoe snel wordt selectief wissen voor MAM uitgevoerd?**<br></br> Als de gebruiker de app gebruikt wanneer selectief wissen wordt gestart, controleert de Intune App SDK om de 30 minuten op aanvragen van de MAM-service voor selectief wissen. Daarnaast wordt er gecontroleerd of er een aanvraag voor selectief wissen is verzonden wanneer de gebruiker de app voor de eerste keer start en zich aanmeldt met een werk- of schoolaccount.

**Waarom kunnen er geen on-premises services (on-prem) worden gebruikt in combinatie met apps die zijn beveiligd met Intune?**<br></br>
Voor de app-beveiliging van Intune moet de identiteit van de gebruiker voor de toepassing en Intune App SDK consistent zijn. Dit kan alleen worden gegarandeerd via moderne verificatie. Er zijn scenario's waarin apps met een on-premisses configuratie werken, maar deze zijn niet consistent en kunnen ook niet worden gegarandeerd.

**Is er een veilige manier om webkoppelingen te openen vanuit beheerde apps?**<br></br>
Ja. De IT-beheerder kan een app-beveiligingsbeleid implementeren en instellen voor de [Intune Managed Browser-app](app-configuration-managed-browser.md), een webbrowser die is ontwikkeld door Microsoft Intune en eenvoudig kan worden beheerd met Intune. De IT-beheerder kan ervoor zorgen dat alle webkoppelingen in de door Intune beheerde apps moeten worden geopend met de Managed Browser-app.



## <a name="app-experience-on-android"></a>Apps op Android gebruiken

**Waarom is de bedrijfsportal-app op Android-apparaten nodig voor app-beveiliging met Intune?**<br></br>
Veel van de functies voor het beveiligen van apps zijn ingebouwd in de bedrijfsportal-app. Hoewel de bedrijfsportal-app altijd vereist is, hoeft een apparaat _niet te worden geregistreerd_. Voor MAM-WE moet de eindgebruiker de bedrijfsportal-app op het apparaat hebben geïnstalleerd.

**Hoe werken meerdere toegangsinstellingen voor Intune-app-beveiliging die zijn geconfigureerd voor dezelfde set apps en gebruikers die op Android werken?**<br></br>
Het Intune-app-beveiligingsbeleid voor toegang wordt in een bepaalde volgorde toegepast op apparaten van eindgebruikers wanneer ze vanaf hun bedrijfsaccount proberen toegang te krijgen tot een doel-app. In het algemeen krijgt een blokkering voorrang, dan volgt een waarschuwing die kan worden gesloten. Indien van toepassing op de specifieke gebruiker/app wordt een instelling van een minimumversie van een Android-patch die een gebruiker waarschuwt om een patchupgrade uit te voeren, bijvoorbeeld toegepast na de instelling van de minimumversie van de Android-patch die toegang door de gebruiker blokkeert. Dus in het scenario waarin de IT-beheerder de minimumversie van de Android-patch configureert naar 2018-03-01 en de minimumversie van de Android-patch (alleen Waarschuwing) naar 2018-02-01, terwijl het apparaat dat de app probeert te openen op de patchversie 2018-01-01 zit, wordt de eindgebruiker geblokkeerd op basis van de restrictievere instelling voor de minimumversie van de Android-patch die resulteert in geblokkeerde toegang. 

Wanneer u te maken hebt met verschillende soorten instellingen, krijgt een app-versievereiste voorrang, gevolgd door de versievereiste van het Android-besturingssysteem en de versievereiste van de Android-patch. Vervolgens worden eventuele waarschuwingen voor alle typen instellingen in dezelfde volgorde gecontroleerd.

**Intune-app-beveiligingsbeleid biedt beheerders de mogelijkheid om eindgebruikers te verplichten om aan de SafetyNet Attestation van Google voor Android-apparaten te voldoen. Hoe vaak wordt een nieuwe SafetyNet Attestation-resultaat naar de service verzonden?** <br><br> Er wordt een nieuwe Google Play-servicebepaling naar de IT-beheerder gerapporteerd, volgens een interval die door de Intune-service wordt bepaald. Hoe vaak de serviceaanroep wordt uitgevoerd, wordt vertraagd door de belasting. Deze waarde wordt daarom intern onderhouden en kan niet worden geconfigureerd. Elke actie voor de Google SafetyNet Attestation-instelling die door een IT-beheerder is geconfigureerd, wordt uitgevoerd op basis van het meest recent gerapporteerde resultaat naar de Intune-service op het moment van de voorwaardelijke start. Als er geen gegevens zijn, wordt toegang verleend als er geen andere voorwaardelijke opstartcontroles zijn mislukt, en start de Google Play Store-cyclus voor het bepalen van de attestation-resultaten in de back-end en wordt de gebruiker asynchroon gevraagd of het apparaat is mislukt. Als er verouderde gegevens zijn, wordt toegang geblokkeerd of toegestaan op basis van het laatst gerapporteerde resultaat, en start ook de Google Play Store-cyclus voor het bepalen van de attestation-resultaten en wordt de gebruiker asynchroon gevraagd of het apparaat is mislukt.

**Intune-app-beveiligingsbeleid biedt beheerders de mogelijkheid om eindgebruikers te verplichten om signalen te verzenden via de Verify Apps-API van Google voor Android-apparaten. Hoe kunnen eindgebruikers de app-scan inschakelen zodat toegang niet voor hen als gevolg hiervan wordt geblokkeerd?**<br><br> De instructies hiervoor kunnen per apparaat enigszins verschillen. Bij het algemene proces gaat u naar de Google Play Store en klikt u op **Mijn apps en games**. Klik vervolgens op het resultaat van de laatste app-scan om naar het menu Play Protect te gaan. Zorg ervoor dat de wisselknop voor **Apparaat scannen op beveiligingsrisico's** is ingesteld op Aan.

**Wat wordt er op Android-apparaten precies gecontroleerd met de SafetyNet Attestation-API van Google? Wat is het verschil tussen de configureerbare waarden van Basisintegriteit controleren en Basisintegriteit en gecertificeerde apparaten controleren?** <br><br>
Intune gebruikt Google Play Protect SafetyNet-API's om aan onze bestaande rootdetectiecontroles toe te voegen voor niet-ingeschreven apparaten. Google heeft deze API-set ontwikkeld en onderhouden die door Android-apps kan worden gebruikt als deze niet op geroote apparaten moeten worden uitgevoerd. Dit is bijvoorbeeld opgenomen in de Android Pay-app. Hoewel Google niet de volledige rootdetectiecontroles die plaatsvinden openbaar deelt, verwachten we wel dat deze API's gebruikers detecteren die hun apparaten hebben geroot. Toegang van deze gebruikers kan vervolgens worden geblokkeerd, of hun zakelijke accounts kunnen worden gewist uit via beleid ingeschakelde apps. Bij Basisintegriteit controleren ziet u de algemene integriteit van het apparaat. Geroote apparaten, emulators, virtuele apparaten en apparaten met zichtbare sabotagesporen voldoen niet aan de basisintegriteit. Bij Basisintegriteit en gecertificeerde apparaten controleren krijgt u informatie over de compatibiliteit van het apparaat met de services van Google. Alleen niet-aangepaste apparaten die door Google zijn gecertificeerd, voldoen aan deze controle. De volgende apparaten zullen niet voldoen:
* Apparaten die niet aan de basisintegriteit voldoen
* Apparaten met een ontgrendelde bootloader
* Apparaten met een aangepaste systeemkopie/ROM
* Apparaten waarvoor de fabrikant geen Google-certificering heeft aangevraagd of die niet aan de Google-certificering voldoen 
* Apparaten waarbij de systeemkopie rechtstreeks vanuit de bronbestanden van het Android open source-programma zijn is gemaakt
* Apparaten met een preview-versie van de systeemkopie voor de bètaversie/ontwikkelaars

Raadpleeg [De documentatie van Google over SafetyNet Attestation](https://developer.android.com/training/safetynet/attestation) voor technische informatie.

**In het gedeelte Voorwaardelijke start staan twee vergelijkbare controles wanneer er een Intune-app-beveiligingsbeleid voor Android-apparaten wordt gemaakt. Moet ik de instelling SafetyNet Attestion voor apparaten of de instelling Jailbroken/geroote apparaten vereisen?** <br><br>
Voor de SafetyNet-API-controles van Google Play is het vereist dat eindgebruikers online zijn voor ten minste de periode waarin de volledige cyclus voor het bepalen van de attestation-resultaten wordt uitgevoerd. Als eindgebruikers offline zijn, kunnen IT-beheerders er alsnog van uitgaan dat voor een resultaat de instelling Jailbroken/geroote apparaten wordt vereist. Dit gezegd hebbende: als de eindgebruiker te lang offline is geweest, wordt de waarde Offlinerespijtperiode geactiveerd en wordt de toegang tot alle werk- of schoolgegevens geblokkeerd zodra die timerwaarde is bereikt, tot de netwerktoegang weer beschikbaar is. Als beide instellingen worden ingeschakeld, is een gelaagde methode mogelijk om de apparaten van eindgebruikers gezond te houden. Dit is belangrijk als eindgebruikers hun werk- of schoolgegevens op een mobiel apparaat openen. 

**Google Play Services moet actief zijn voor de instellingen van het app-beveiligingsbeleid die gebruikmaken van de Google Play Protect-API's. Wat moet ik doen als Google Play Services niet zijn toegestaan op de mogelijke locatie van de eindgebruiker?**<br><br>
Voor zowel de instelling SafetyNet Attestion voor apparaten als de instelling Bedreigingsscan op apps moet de door Google bepaalde versie van Google Play Services naar behoren werken. Aangezien dit de instellingen zijn die in het gebied van beveiliging vallen, wordt de eindgebruiker geblokkeerd als deze instellingen op deze gebruiker zijn gericht en niet voldoen aan de juiste versie van Google Play Services of geen toegang hebben tot Google Play Services. 

## <a name="app-experience-on-ios"></a>Apps op iOS gebruiken
**Wat gebeurt er als ik een vingerafdruk of gezicht toevoeg of verwijder op mijn apparaat?**<br></br>
Het Intune-beleid voor app-beveiliging geeft u de mogelijkheid app-toegang te beperken tot enkel de gebruiker met een Intune-licentie. Een van de manieren om toegang tot de app te beheren, is op ondersteunde apparaten Touch ID of Face ID van Apple te vereisen. Intune implementeert een gedrag waarbij Intune, na iedere wijziging in de biometrische database van het apparaat, de gebruiker vraagt een pincode in te voeren wanneer aan de volgende time-outwaarde voor inactiviteit wordt voldaan. Wijzigingen in biometrische gegevens omvatten het toevoegen of verwijderen van een vingerafdruk of gezicht. Als de Intune-gebruiker geen pincode heeft ingesteld, wordt gevraagd om een Intune-pincode in te stellen.
 
De heeft als doel de gegevens van uw organisatie in de app op app-niveau veilig en beschermd te houden. Deze functie is alleen beschikbaar voor iOS en vereist het gebruik van toepassingen die de Intune-APP SDK voor iOS, versie 9.0.1 of hoger, hebben geïntegreerd. Integratie van de SDK is nodig om het gedrag te kunnen afdwingen in de betreffende toepassingen. Deze integratie vindt doorlopend plaats en is afhankelijk van de specifieke toepassingsteams. Apps die hieraan deelnemen, zijn onder meer WXP, Outlook, Managed Browser en Yammer. 
  
**Ik kan de iOS-extensie voor delen gebruiken om werk- of schoolgegevens te openen in niet-beheerde apps, zelfs wanneer het beleid voor het overdragen van gegevens is ingesteld op 'alleen voor beheerde apps' of 'geen apps'. Ontstaat hierdoor geen gegevenslek?**<br></br>
De iOS-extensie voor delen kan alleen met het app-beveiligingsbeleid worden beheerd als ook het apparaat wordt beheerd. Daarom worden _**'zakelijke' gegevens door Intune versleuteld voordat ze buiten de app worden gedeeld**_ . U kunt dit controleren door een 'zakelijk' bestand te openen buiten de beheerde app. Het bestand moet zijn versleuteld en kan niet worden geopend bijten de beheerde app.

**Hoe werken meerdere toegangsinstellingen voor Intune-app-beveiliging die zijn geconfigureerd voor dezelfde set apps en gebruikers op iOS?**<br></br>
Het Intune-app-beveiligingsbeleid voor toegang wordt in een bepaalde volgorde toegepast op apparaten van eindgebruikers wanneer ze vanaf hun bedrijfsaccount proberen toegang te krijgen tot een doel-app. In het algemeen krijgt wissen voorrang, dan volgt een waarschuwing die kan worden gesloten. Indien van toepassing op de specifieke gebruiker/app, wordt een instelling van een minimumversie van het iOS-besturingssysteem die een gebruiker waarschuwt om de iOS-versie bij te werken bijvoorbeeld toegepast na de instelling van de minimumversie van het iOS-besturingssysteem die toegang door de gebruiker blokkeert. Dus in het scenario waarin de IT-beheerder de minimumversie van het iOS-besturingssysteem configureert naar 11.0.0.0 en de minimumversie van het iOS-besturingssysteem (alleen Waarschuwing) naar 11.1.0.0, terwijl het apparaat dat de app probeert te openen op iOS 10 zit, wordt de eindgebruiker geblokkeerd op basis van de restrictievere instelling voor de minimumversie van het iOS-besturingssysteem die resulteert in geblokkeerde toegang.

Wanneer u te maken hebt met verschillende soorten instellingen, krijgt een Intune App SDK-versie voorrang, dan een app-versievereiste, gevolgd door de versievereisten van het iOS-besturingssysteem. Vervolgens worden eventuele waarschuwingen voor alle typen instellingen in dezelfde volgorde gecontroleerd. We raden u aan om de Intune App SDK-versievereisten alleen te configureren op advies van het Intune-productteam voor essentiële blokkerende scenario's.


## <a name="see-also"></a>Zie tevens
- [Uw Intune-abonnement implementeren](planning-guide-onboarding.md)
- [Intune testen en valideren](planning-guide-test-validation.md)
- [Mobile Application Management-beleidsinstellingen voor Android in Microsoft Intune](app-protection-policy-settings-android.md)
- [Mobile Application Management-beleidsinstellingen voor iOS](app-protection-policy-settings-ios.md)
- [Beveiligingsbeleid voor apps: vernieuwen van het beleid](app-protection-policy-delivery.md)
- [Beveiligingsbeleid voor apps valideren](app-protection-policy-delivery.md)
- [App-configuratiebeleidsregels toevoegen voor beheerde apps zonder apparaatinschrijving](app-configuration-policies-managed-app.md)
- [Ondersteuning voor Microsoft Intune krijgen](get-support.md)
