---
title: Veelgestelde vragen over Azure Rights Management | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 06/30/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 71ce491f-41c1-4d15-9646-455a6eaa157d
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b73c83b91a6b00e44ff6c8fe7f8e954bd9713e34
ms.openlocfilehash: a3ed9e8de496741fae8904481edb1177762a12c0


---

# Veelgestelde vragen over Azure Rights Management

*Van toepassing op: Azure Rights Management, Office 365*

Een paar veelgestelde vragen over Microsoft [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)], ook wel aangeduid als Azure RMS:

## Wat heb ik nodig om Azure RMS te implementeren en hoe ga ik aan de slag?
Controleer eerst [Vereisten voor Azure Rights Management](requirements-azure-rms.md), dat informatie bevat over de opties voor cloudabonnementen, hoe u uw lokale servers kunt gebruiken met Azure RMS, welke implementatiescenario's momenteel niet worden ondersteund, welke apparaten en toepassingen Azure RMS ondersteunen en een koppeling als u een lijst met IP-adressen en domeinnamen nodig hebt voor firewalls en proxyservers. 

Het is wellicht ook verstandig de andere artikelen in deze sectie **Get Started ** (Aan de slag) en de sectie **Understand & Explore** (Begrijpen en verkennen) te lezen voor meer algemene informatie over hoe [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] kan helpen de gegevens van uw organisatie te beveiligen, hoe het product werkt met toepassingen, wat de verschillen zijn met de on-premises versie van Active Directory Rights Management en om inzicht te krijgen in de termen en afkortingen die specifiek zijn voor [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)].

Als u vervolgens aan de slag wilt, gebruikt u het [Azure Rights Management-implementatieschema](../plan-design/deployment-roadmap.md).

## Moeten bestanden in de cloud staan om te worden beveiligd met Azure RMS?
Nee, dit is een veelvoorkomend misverstand. De Azure Rights Management-service (en Microsoft) kunnen uw gegevens niet weergeven of opslaan. Dit is een vereiste van het proces voor informatiebeveiliging. Informatie die u beveiligt, wordt nooit verzonden naar of opgeslagen in Azure, tenzij u de informatie zelf expliciet opslaat in Azure of een andere cloudservice gebruikt waarmee informatie wordt opgeslagen in Azure. 

Zie voor meer informatie [Hoe werkt Azure RMS? Achter de schermen](../understand-explore/how-does-it-work.md) om te begrijpen hoe een geheim colarecept, dat lokaal is gemaakt en opgeslagen, wordt beveiligd met Azure RMS, maar lokaal aanwezig blijft.

## Kan ik Azure RMS integreren in mijn lokale servers?
Ja. Azure RMS kan worden geïntegreerd in uw lokale servers, zoals Exchange Server, SharePoint en Windows-bestandsservers. U doet dat met de [Rights Management-connector](../deploy-use/deploy-rms-connector.md). Of als u alleen geïnteresseerd bent in het gebruik van File Classification Infrastructure (FCI) in combinatie met Windows Server, kunt u de [cmdlets voor RMS-beveiliging](https://technet.microsoft.com/library/mt601315%28v=ws.10%29.aspx) gebruiken. U kunt uw Active Directory-domeincontrollers ook synchroniseren met Azure AD voor een meer naadloze verificatiebeleving door gebruikers. U kunt dat bijvoorbeeld doen met [Azure AD Connect](http://azure.microsoft.com/documentation/articles/active-directory-aadconnect/).

Azure RMS genereert en beheert automatisch XrML-certificaten zoals vereist en gebruikt dus geen lokale PKI. Zie de sectie [Walkthrough of how Azure RMS works: First use, content protection, content consumption](../understand-explore/how-does-it-work.md#walkthrough-of-how-azure-rms-works-first-use-content-protection-content-consumption) (Overzicht van de werking van Azure RMS: eerste gebruik, beveiliging van inhoud, verbruik van inhoud) in het artikel [How does Azure RMS work?](../understand-explore/how-does-it-work.md) (Hoe werkt Azure RMS?) voor meer informatie over de manier waarop certificaten worden gebruikt in Azure RMS.

## Waar vind ik informatie over oplossingen van derden die zijn geïntegreerd met Azure RMS?

Veel softwareleveranciers hebben al oplossingen of zijn bezig met het implementeren van oplossingen die kunnen worden geïntegreerd met Azure RMS, en de lijst groeit snel. Misschien vindt u het nuttig een kijkje te nemen in het [Enterprise Mobility and Security-blog](https://blogs.technet.microsoft.com/enterprisemobility/?product=azure-rights-management-services) en de laatste updates te downloaden van [Dan Plastina @TheRMSGuy](https://twitter.com/TheRMSGuy) op Twitter. Als u echter een specifieke vraag hebt, kunt u een e-mailbericht verzenden naar het team dat zich bezighoudt met informatiebeveiliging: askipteam@microsoft.com.

## Is er een management pack of een vergelijkbaar bewakingsmechanisme voor de RMS-connector?

Hoewel informatie-, waarschuwings- en foutberichten met de Rights Management-connector worden geregistreerd, is er geen management pack waarmee deze gebeurtenissen kunnen worden bewaakt. Zie [De Azure Rights Management-connector controleren](../deploy-use/monitor-rms-connector.md) voor de lijst met gebeurtenissen en bijbehorende beschrijvingen, en meer informatie over u corrigerende maatregelen kunt nemen.

## Moet ik een globale beheerder zijn om Azure RMS te configureren of kan ik delegeren aan andere beheerders?

Globale beheerders voor een Office 365- of Azure AD-tenant kunnen natuurlijk alle beheertaken uitvoeren voor Azure RMS. Als u echter beheerdersmachtigingen aan andere gebruikers wilt toewijzen, kunt u dit doen via de PowerShell-cmdlet voor Azure RMS [Add-AadrmRoleBasedAdministrator](https://msdn.microsoft.com/library/dn629417.aspx). U kunt deze beheerdersrol toewijzen per gebruikersaccount of per groep. Er zijn twee rollen beschikbaar: **Globale beheerder** en **Connector Administrator**. 

Zoals u kunt afleiden uit deze rolnamen, worden met de eerste rol machtigingen verleend voor het uitvoeren van alle beheertaken voor Azure Rights Management (zonder dat de beheerder een globale beheerder wordt voor cloudservices) en worden met de tweede rol machtigingen verleend voor het uitvoeren van alleen de Rights Management (RMS)-connector.

Let op het volgende:

- Alleen globale beheerders voor Office 365 en globale beheerders voor Azure AD kunnen gebruikmaken van de beheerportals (Office 365-beheercentrum of de klassieke Azure-portal) voor het configureren van Azure RMS. Gebruikers aan wie u de globale beheerdersrol voor Azure RMS toewijst, moeten de PowerShell-opdrachten voor Azure RMS gebruiken voor het configureren van Azure RMS. Zie [Beheer van Azure Rights Management met Windows PowerShell](../deploy-use/administer-powershell.md) voor een overzicht van de juiste cmdlets voor specifieke taken.

- Als u [controlemiddelen voor onboarding](../deploy-use/activate-service.md#configuring-onboarding-controls-for-a-phased-deployment) hebt geconfigureerd, is dit niet van invloed op de mogelijkheid voor het beheer van Azure RMS, met uitzondering van de RMS-connector. Stel dat u als controlemiddel voor onboarding hebt geconfigureerd dat de mogelijkheid om inhoud te beheren is beperkt tot de groep IT-afdeling. Het account dat u gebruikt voor het installeren en configureren van de RMS-connector, moet dan lid zijn van die groep. 

- Beheerders voor Azure RMS (de globale beheerder van de tenant of de globale beheerder van Azure RMS) kunnen niet automatisch de beveiliging verwijderen van documenten en e-mails die met Azure RMS worden beveiligd. Alleen gebruikers aan wie de rol Supergebruiker voor Azure RMS is toegewezen, kunnen dit doen en alleen wanneer de functie Supergebruiker is ingeschakeld. De globale beheerder van de tenant en alle globale beheerders van Azure RMS kunnen de rol van supergebruiker aan gebruikers toewijzen, ook aan uw eigen account. Daarnaast kunnen zij de functie Supergebruiker inschakelen. Deze acties worden vastgelegd in het Azure RMS-beheerderslogboek. Zie de sectie met best practices voor beveiliging in [Supergebruikers configureren voor Azure Rights Management en detectieservices of gegevensherstel](../deploy-use/configure-super-users.md) voor meer informatie. 


## Ik heb een hybride implementatie van Exchange waarbij sommige gebruikers op Exchange Online zitten en andere op Exchange Server. Wordt dit ondersteund door Azure RMS?
Absoluut, en het prettige is dat gebruikers beveiligde e-mailberichten en bijlagen naadloos kunnen beveiligen en verbruiken op beide Exchange-implementaties. Voor deze configuratie moet u [Azure RMS activeren](../deploy-use/activate-service.md), [IRM voor Exchange Online inschakelen](https://technet.microsoft.com/library/dn151475%28v=exchg.150%29.aspx) en vervolgens [de RMS-connector implementeren en configureren](../deploy-use/deploy-rms-connector.md) voor Exchange-Server.

## Zijn er stapsgewijze instructies om Exchange Online te configureren voor gebruik van Azure RMS?

Ja. Zie [Exchange Online: IRM configureren](../deploy-use/configure-office365.md#exchange-online-irm-configuration) voor een gebruikelijke reeks opdrachten waarmee Exchange Online wordt ingeschakeld voor gebruik van Azure RMS, voor de redenen waarom de Outlook Web App niet onmiddellijk de menuopties **Machtigingen instellen** weergeeft en voor de opdracht die u moet uitvoeren als u de sjablonen voor Azure RMS bijwerkt of wijzigt. 

## Als ik Azure RMS voor productie implementeer, zit mijn bedrijf dan vast aan deze oplossing of lopen we het risico de toegang te verliezen tot inhoud die werd beveiligd met Azure RMS?
Nee, u behoudt altijd de controle over uw gegevens en kunt deze blijven gebruiken, zelfs als u besluit niet langer met Azure RMS te werken. Zie [Decommissioning and deactivating Azure Rights Management](../deploy-use/decommission-deactivate.md) (Azure Rights Management uit bedrijf nemen en deactiveren) voor meer informatie.

Voordat u echter uw Azure RMS-implementatie uit bedrijf neemt, willen we graag van u horen waarom u deze beslissing hebt genomen. Als Azure RMS niet voldoet aan uw zakelijke vereisten, kunt u contact met ons opnemen om te zien of er voor de nabije toekomst nieuwe functies zijn gepland en of er alternatieven zijn. Stuur een e-mailbericht naar [AskIPTeam@Microsoft.com](mailto:askipteam@microsoft.com?subject=Planning%20to%20decommission%20Azure%20RMS) zodat we uw technische en zakelijke vereisten met u kunnen bespreken.

## Kan ik controleren welke van mijn gebruikers Azure RMS kunnen gebruiken om inhoud te beveiligen?
Ja, Azure RMS heeft voor dit scenario controlemiddelen voor de onboarding van gebruikers. Zie voor meer informatie het gedeelte [Controlemiddelen voor onboarding configureren voor een gefaseerde implementatie](../deploy-use/activate-service.md#configuring-onboarding-controls-for-a-phased-deployment) in het artikel [Azure Rights Management activeren](../deploy-use/activate-service.md).

## Kan ik voorkomen dat gebruikers beveiligde documenten delen met specifieke organisaties?
Een van de grootste voordelen van Azure RMS is dat het business-to-business samenwerking ondersteunt zonder dat u expliciete vertrouwensrelaties hoeft te configureren voor elke partnerorganisatie, omdat Azure AD de verificatie voor u verzorgt.

Er is geen beheeroptie om te voorkomen dat gebruikers documenten veilig delen met specifieke organisaties. U wilt bijvoorbeeld een organisatie blokkeren die u niet vertrouwt of die een concurrent is. Voorkomen dat Azure RMS beveiligde documenten verzendt naar gebruikers in deze organisaties, heeft geen zin omdat uw gebruikers hun documenten dan zonder beveiliging zouden gaan delen. En dat is waarschijnlijk het laatste wat u binnen dit scenario zou willen. U zou bijvoorbeeld niet kunnen bepalen wie vertrouwelijke bedrijfsdocumenten deelt met welke gebruikers in deze organisaties. Dat kunt u wel wanneer het document (of e-mailbericht) is beveiligd met Azure RMS.

## Wanneer ik een beveiligd document deel met iemand buiten mijn bedrijf, hoe wordt die gebruiker dan geverifieerd?
Azure RMS gebruikt altijd een Azure Active Directory-account en een bijbehorend e-mailadres voor gebruikersverificatie, waardoor business-to-business samenwerking naadloos verloopt voor beheerders. Als de andere organisatie Azure-services gebruikt, hebben de gebruikers al accounts in Azure Active Directory, zelfs als deze accounts lokaal worden gemaakt en beheerd en vervolgens worden gesynchroniseerd naar Azure. Als de organisatie werkt met Office 365, gebruikt deze service ook Azure Active Directory voor de gebruikersaccounts. Als de organisatie van de gebruiker geen beheerde accounts in Azure heeft, kunnen gebruikers zich aanmelden voor [RMS voor personen](../understand-explore/rms-for-individuals.md). Hierbij worden automatisch een niet-beheerde Azure-tenant en -map voor de organisatie gemaakt met een account voor de gebruiker (en toekomstige gebruikers), zodat deze gebruiker vervolgens kan worden geverifieerd voor Azure RMS.

De verificatiemethode voor deze accounts kan variëren, afhankelijk van hoe de beheerder in de andere organisatie de Azure Active Directory-accounts heeft geconfigureerd. Ze kunnen bijvoorbeeld gebruik maken van wachtwoorden die zijn gemaakt voor deze accounts, van Multi-Factor Authentication (MFA), van federatie of van wachtwoorden die zijn gemaakt in Active Directory Domain Services en vervolgens zijn gesynchroniseerd met Azure Active Directory.

## Kan ik gebruikers van buiten mijn bedrijf toevoegen aan aangepaste sjablonen?
Ja. Wanneer u aangepaste sjablonen maakt die eindgebruikers (en beheerders) kunnen selecteren in toepassingen, kunnen zij gegevensbeveiliging snel en eenvoudig toepassen met de vooraf door u gedefinieerde beleidsregels. U kunt in de sjabloon onder andere instellen wie toegang heeft tot de inhoud. U kunt daarbij gebruikers en groepen van binnen uw organisatie en gebruikers van buiten uw organisatie opgeven.

U kunt gebruikers van buiten uw organisatie opgeven door ze toe te voegen als contactpersonen aan een groep die u selecteert in de klassieke Azure-portal tijdens het configureren van uw sjablonen. U kunt ook de [Windows PowerShell-module voor Azure Rights Management](../deploy-use/install-powershell.md) gebruiken:

-   **Gebruik een rechtendefinitieobject om een sjabloon te maken of bij te werken**.    Geef de externe e-mailadressen en de bijbehorende rechten op in een rechtendefinitieobject, dat u vervolgens kunt gebruiken om een sjabloon te maken of bij te werken. U geeft het rechtendefinitieobject op met de cmdlet [New-AadrmRightsDefinition](https://msdn.microsoft.com/library/azure/dn727080.aspx) om een variabele te maken en geeft deze variabele vervolgens door aan de parameter -RightsDefinition met de cmdlet [Add-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727075.aspx) (voor een nieuwe sjabloon) of met de cmdlet [Set-AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727076.aspx) (als u een bestaande sjabloon wijzigt). Als u deze gebruikers echter aan een bestaande sjabloon toevoegt, moet u rechtendefinitieobjecten definiëren voor de bestaande groepen in de sjablonen en niet alleen voor de externe gebruikers.

Zie [Configuring custom templates for Azure Rights Management](../deploy-use/configure-custom-templates.md) (Aangepaste sjablonen configureren voor Azure Rights Management) voor meer informatie over aangepaste sjablonen.

## Werkt Azure RMS met dynamische groepen in Azure AD?
Met een Azure AD Premium-functie kunt u een dynamisch lidmaatschap voor groepen configureren door [op kenmerken gebaseerde regels](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) op te geven. Wanneer u een beveiligingsgroep in Azure AD maakt, biedt dit groepstype ondersteuning voor dynamisch lidmaatschap, maar biedt het geen ondersteuning voor een e-mailadres en kan het dus niet worden gebruikt met Azure RMS. U kunt nu echter een nieuw groepstype in Azure AD maken dat dynamisch lidmaatschap en e-mail beide ondersteunt. Wanneer u een nieuwe groep toevoegt in de klassieke Azure-portal, kunt u het **GROEPSTYPE** **Office 365 "Voorbeeld"** kiezen. Omdat dit een groep met e-mail is, kunt u deze met Azure RMS gebruiken.

Zoals de optienaam duidelijk aangeeft, is dit nieuwe groepstype alleen nog maar een voorbeeld. Extra functies en nieuwe documentatie komen later. In afwachting daarvan wilden we bevestigen dat u dit nieuwe groepstype met Azure RMS kunt gebruiken.


## Welke apparaten en welke typen worden ondersteund door Azure RMS?
Zie [Azure RMS-vereisten: clientapparaten die Azure RMS ondersteunen](../get-started/requirements-client-devices.md) voor een lijst met ondersteunde apparaten. Omdat niet alle ondersteunde apparaten momenteel alle functies van RMS ondersteunen, moet u in hetzelfde artikel ook de tabel in [Azure RMS requirements: Applications](../get-started/requirements-applications.md) (Azure RMS-vereisten: toepassingen) raadplegen.

Azure RMS kan alle bestandstypen ondersteunen. Voor tekst-, afbeeldings-, Microsoft Office- (Word, Excel, PowerPoint), .pdf-bestanden en sommige andere bestandstypen, biedt Azure RMS systeemeigen beveiliging zoals versleuteling en het afdwingen van rechten (machtigingen). Voor alle andere toepassingen en bestandstypen biedt algemene beveiliging bestandsinkapseling en verificatie om te controleren of een gebruiker is gemachtigd om het bestand te openen.

Zie voor een lijst met bestandnaamsextensies die systeemeigen worden ondersteund door Azure RMS, het gedeelte [Ondersteunde bestandstypen en bestandsnaamextensies](../rms-client/sharing-app-admin-guide-technical.md#supported-file-types-and-file-name-extensions) in de [Beheerdershandleiding voor de Rights Management-toepassing voor delen](../rms-client/sharing-app-admin-guide.md). Bestandsnaamextensies die niet worden vermeld, worden ondersteund via de RMS-toepassing voor delen die automatisch algemene beveiliging toepast op deze bestanden.

## Is het gekoppelde tijdelijke bestand ook met RMS beveiligd wanneer ik een Office-document open dat is beveiligd met RMS?

Nee. In dit scenario bevat het gekoppelde tijdelijke bestand geen gegevens van het originele document maar alleen wat de gebruiker invoert terwijl het bestand is geopend. In tegenstelling tot het oorspronkelijke bestand, is het tijdelijke bestand natuurlijk niet bedoeld om gedeeld te worden. Deze bestanden blijven op het apparaat en worden beveiligd met lokale beveiligingsmaatregelen zoals BitLocker en EFS.

## Wanneer ondersteunt u migratie vanaf AD RMS?
In eerste instantie bood Azure RMS geen ondersteuning voor migratie vanaf een lokale implementatie van Rights Management, zoals AD RMS. Maar nu wordt dat wel ondersteund.

Zie [Migrating from AD RMS to Azure Rights Management](../plan-design/migrate-from-ad-rms-to-azure-rms.md) (Migreren van AD RMS naar Azure Rights Management) voor meer informatie.

## We willen heel graag BYOK gebruiken met Azure RMS, maar hebben vernomen dat dit niet kan met Exchange Online. Wat is uw advies?
Laat deze huidige beperking u er niet van weerhouden Azure RMS te implementeren. Als u Exchange Online en BYOK (Bring Your Own Key) wilt gebruiken, raden wij u aan Azure RMS nu te implementeren in de standaardmodus voor sleutelbeheer, waarbij Microsoft uw sleutel genereert en beheert. Op die manier zijn al uw belangrijke bestanden en e-mailberichten nu beschermd en kunt u later overstappen op BYOK (bijvoorbeeld zodra Exchange Online BYOK wel gaat ondersteunen).

Als uw bedrijfsbeleid echter het gebruik van een Hardware Security Module (HSM) voorschrijft en dit anders uw Azure RMS-implementatie blokkeert, is een andere mogelijkheid Azure RMS nu met BYOK te implementeren met een verminderde RMS-functionaliteit voor Exchange. Zie [BYOK pricing and restrictions](../plan-design/byok-price-restrictions.md) (BYOK-prijzen en beperkingen) in [Planning and iplementing your Azure Rights Management tenant key](../plan-design/plan-implement-tenant-key.md) (Uw Azure Rights Management-tenantsleutel plannen en implementeren) voor meer informatie.

## Een functie die ik nodig heb, lijkt niet te werken met door SharePoint beveiligde bibliotheken. Wordt ondersteuning voor mijn functie gepland?
Op dit moment ondersteunt SharePoint met RMS beveiligde documenten via met IRM beveiligde bibliotheken, die geen ondersteuning bieden voor aangepaste sjablonen, documenten bijhouden en bepaalde andere functies. Zie voor meer informatie het gedeelte [SharePoint Online en SharePoint Server](../understand-explore/office-apps-services-support.md#sharepoint-online-and-sharepoint-server) in het artikel [Office-toepassingen en -services](../understand-explore/office-apps-services-support.md).

Als u geïnteresseerd bent in een specifieke functie die nog niet wordt ondersteund, is het verstandig de aankondigingen in het [Enterprise Mobility and Security Blog-blog](https://blogs.technet.microsoft.com/enterprisemobility/?product=azure-rights-management-services) goed in de gaten te houden.

## Hoe configureer ik OneDrive voor Bedrijven in SharePoint Online, zodat gebruikers hun bestanden veilig met mensen binnen en buiten het bedrijf kunnen delen?
Standaard configureert u dit als Office 365-beheerder niet. De gebruikers doen dat.

Net zoals een SharePoint-sitebeheerder IRM inschakelt en configureert voor een SharePoint-bibliotheek waarvan deze eigenaar is, is OneDrive voor Bedrijven bedoeld voor gebruikers die IRM voor hun eigen OneDrive voor Bedrijven-bibliotheek willen inschakelen en configureren.  U kunt dit met PowerShell echter in hun plaats doen. Zie voor instructies het gedeelte [SharePoint Online en OneDrive voor Bedrijven: IRM-configuratie](../deploy-use/configure-office365.md#sharepoint-online-and-onedrive-for-business-irm-configuration) in het artikel [Office 365: configuratie voor clients en onlineservices](../deploy-use/configure-office365.md).

## Hebt u tips of trucs voor een succesvolle RMS-implementatie?
Na veel implementaties te hebben overzien en te hebben geluisterd naar onze klanten, partners, adviseurs en supporttechnici, is een van de beste tips die kan worden gegeven op grond van onze ervaring: **ontwerp en implementeer een eenvoudig rechtenbeleid**.

Omdat Azure RMS veilig delen met iedereen ondersteunt, kunt u ambitieus zijn wat betreft het bereik van uw beveiligingssystemen. Maar wees voorzichtig met uw rechtenbeleid. Voor veel organisaties vloeit de grootste impact op de bedrijfsactiviteiten voort uit het voorkomen van gegevenslekken door toepassing van de standaardrechtenbeleidssjabloon, die de toegang beperkt tot mensen in uw organisatie. Natuurlijk kunt u veel meer granulair te werk gaan als dat nodig is: voorkomen dat mensen afdrukken, bewerken, enzovoort. Maar gebruik deze meer granulaire beperkingen bij wijze van uitzondering voor documenten die echt beveiliging op hoog niveau nodig hebben. Implementeer deze meer beperkende beleidsregels niet op de eerste dag, maar plan een meer gefaseerde benadering.

## Welke functies kunnen wel of niet met de verschillende abonnementen op Azure RMS worden gebruikt?
Voor de betaalde abonnementen die Azure RMS (Office 365, Azure RMS Premium en Enterprise Mobility Suite) ondersteunen, zijn er een paar verschillen in de RMS-functies die worden ondersteund. Zie [Comparison of Rights Management Services (RMS) Offerings](http://technet.microsoft.com/dn858608) (Vergelijking van Rights Management Services (RMS)-aanbiedingen) voor een lijst hiervan.

Het gratis abonnement dat Azure RMS (RMS voor individuen) ondersteunt, ondersteunt het verbruik van inhoud die is beveiligd met Azure RMS. Zie voor meer informatie [RMS voor personen en Azure Rights Management](../understand-explore/rms-for-individuals.md).

## Waar vind ik technische gegevens over het gratis abonnement op Azure RMS (RMS voor individuen)? Bijvoorbeeld over hoe het werkt, hoe ik controle kan krijgen over de accounts en welke domeinen niet kunnen worden gebruikt?
U vindt antwoorden op deze vragen in [RMS voor individuen en Azure Rights Management](../understand-explore/rms-for-individuals.md) en verwante artikelen.

## Hoe krijgen we weer toegang tot bestanden die zijn beveiligd door een medewerker die de organisatie heeft verlaten?
Gebruik daarvoor de functie Supergebruiker van Azure RMS. Hiermee krijgen gemachtigde gebruikers volledige eigenaarsrechten voor alle gebruikslicenties die zijn verleend door de RMS-tenant van uw organisatie. Via deze zelfde functie kunnen bestanden naar behoefte met gemachtigde services worden geïndexeerd en geïnspecteerd.

Zie [Configuring super users for Azure Rights Management and discovery services or data recovery](../deploy-use/configure-super-users.md) (Supergebruikers configureren voor Azure Rights Management en detectieservices of gegevensherstel) voor meer informatie.

## Kan met Rights Management het maken van schermopnamen worden voorkomen?
Als u het [gebruiksrecht](../deploy-use/configure-usage-rights.md) **Kopiëren** niet verleent, kan met Rights Management worden voorkomen dat er schermopnamen worden gemaakt met veel van de algemeen gebruikte hulpprogramma's voor het vastleggen van schermopnamen van de Windows-platformen (Windows 7, Windows 8.1, Windows 10, Windows Phone) en Android. Op iOS- en Mac-apparaten kunnen schermopnamen echter niet worden geblokkeerd en browsers (bijvoorbeeld indien gebruikt met Outlook Web App en Office Online) kunnen schermopnamen evenmin voorkomen

Het blokkeren van schermopnamen kan helpen voorkomen dat vertrouwelijke of gevoelige informatie per ongeluk of uit nalatigheid wordt geopenbaard. Maar er zijn veel manieren waarop een gebruiker gegevens kan delen die op een scherm worden weergegeven, en een schermopname is daar maar één voorbeeld van. Een gebruiker die weergegeven informatie wil delen, kan deze bijvoorbeeld fotograferen met een mobiele telefoon, de gegevens overtypen of ze gewoon aan iemand anders vertellen.

Zoals blijkt uit deze voorbeelden, kan met technologie niet altijd worden voorkomen dat gebruikers ongewenste informatie delen, zelfs niet als alle platforms en alle software de Rights Management-API's voor het blokkeren van schermopnamen zouden ondersteunen. Rights Management kan helpen uw belangrijke gegevens te beschermen met een machtigings- en gebruiksbeleid, maar deze beheeroplossing voor bedrijfsrechten moet worden gebruikt in combinatie met andere controlemiddelen. Implementeer bijvoorbeeld fysieke beveiliging, controleer en bewaak personen die officieel toegang hebben tot de gegevens van uw organisatie en investeer in gebruikerseducatie, zodat gebruikers weten welke gegevens niet mogen worden gedeeld.

## Wat is het verschil tussen een gebruiker die een e-mail beveiligt met de optie Niet doorsturen en een sjabloon dat niet het recht Doorsturen bevat?

Ondanks de naam en het uiterlijk, is **Niet doorsturen** niet het tegenovergestelde van het recht Doorsturen en geen sjabloon. Het is in werkelijkheid een set rechten met onder andere rechten voor het kopiëren, afdrukken en opslaan van bijlagen, naast het beperken van het doorsturen van e-mails. De rechten worden dynamisch toegepast op gebruikers via de gekozen ontvangers, en worden niet statisch toegewezen door de beheerder. Zie de sectie [Do Not Forward option for emails](../deploy-use/configure-usage-rights.md#do-not-forward-option-for-emails) (De optie voor Niet doorsturen voor e-mails) in [Configuring usage rights for Azure Rights Management](../deploy-use/configure-usage-rights.md) (Gebruiksrechten configureren voor Azure Rights Management) voor meer informatie.

## Waar vind ik ondersteunende informatie voor Azure RMS, zoals informatie over wetgeving, compatibiliteit en SLA's?
Azure RMS ondersteunt andere services en maakt ook gebruik van andere services. Als u op zoek bent naar informatie die verband houdt met Azure RMS, maar geen betrekking heeft op het gebruik van de Azure RMS-service, kunt u de volgende bronnen raadplegen:

**Wettelijke informatie en privacy:**

-   Voor informatie over Microsoft Azure-overeenkomsten: [Microsoft Azure-overeenkomst](http://azure.microsoft.com/support/legal/subscription-agreement/)

-   Voor informatie over de Microsoft Azure Privacyverklaring: [Microsoft Azure Privacyverklaring](http://azure.microsoft.com/support/legal/privacy-statement/)

**Beveiliging, naleving en controle:**

Zie de sectie [Security, compliance, and regulatory requirements](../understand-explore/azure-rms-problems-it-solves.md#security-compliance-and-regulatory-requirements) (Beveiliging, naleving en wettelijke voorschriften) in het artikel [What problems does Azure RMS solve?](../understand-explore/azure-rms-problems-it-solves.md) (Welke problemen lost Azure RMS op?). Daarnaast:

-   Voor externe certificeringen voor Azure RMS: [Microsoft Azure Vertrouwenscentrum](http://azure.microsoft.com/support/trust-center/)

-   Voor FIPS 140-informatie: [FIPS 140-validatie](https://technet.microsoft.com/library/security/cc750357.aspx)

**Serviceovereenkomsten:**

-   Serviceovereenkomst voor Azure RMS op geselecteerde regio: [Downloaden van de zoekpagina Productlicentieverlening](http://microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37)

    - Klik bijvoorbeeld op **OnlineSvcsConsolidatedSLA(WW)(English)(March2016)** om de serviceovereenkomst van maart 2016 voor Noord-Amerika te downloaden.

-   Serviceovereenkomst voor Azure Active Directory: [Serviceovereenkomsten](http://azure.microsoft.com/support/legal/sla/)

**Documentatie:**

-   Documentatiesite voor Azure Active Directory: [Azure Active Directory](http://azure.microsoft.com/documentation/services/active-directory/)

-   Azure Active Directory-bibliotheek: [Azure Active Directory](https://msdn.microsoft.com/library/azure/mt168838.aspx)

-   Office 365-bibliotheek: [Office 365](http://technet.microsoft.com/library/dn127064%28v=office.14%29.aspx)

## Ik heb gehoord dat binnenkort een nieuwe versie beschikbaar is voor Azure RMS. Wanneer wordt deze versie uitgebracht?

De technische documentatie bevat geen informatie over toekomstige versies. Dergelijke informatie en aankondigingen over versies vindt u in het [Enterprise Mobility and Security-blog](https://blogs.technet.microsoft.com/enterprisemobility/?product=azure-rights-management-services). De laatste updates leest u via [Dan Plastina @TheRMSGuy](https://twitter.com/TheRMSGuy) op Twitter. Als u geïnteresseerd bent in een bepaalde Office-versie, kunt u ook een kijkje nemen in het [Office-blog[(https://blogs.office.com/).

## Wat moet ik doen als ik mijn vraag hier niet vind?
Gebruik de koppelingen en resources die worden vermeld in [Information and support for Azure Rights Management](information-support.md) (Informatie en ondersteuning voor Azure Rights Management).

Daarnaast zijn er Veelgestelde vragen voor eindgebruikers:

-   [Veelgestelde vragen over Rights Management-toepassing voor delen voor Windows](https://technet.microsoft.com/dn467883)

-   [Veelgestelde vragen over Rights Management-toepassing voor delen voor mobiele en Mac-platforms](https://technet.microsoft.com/dn451248)

-   [Veelgestelde vragen over het bijhouden van documenten](http://go.microsoft.com/fwlink/?LinkId=523977)

Deze pagina met veelgestelde vragen wordt regelmatig bijgewerkt met nieuwe toevoegingen, die worden vermeld in de maandelijkse aankondigingen van documentatie-updates in het [Enterprise Mobility and Security-blog](https://blogs.technet.microsoft.com/enterprisemobility/?product=azure-rights-management-services).





<!--HONumber=Jul16_HO1-->


