---
# required metadata

title: Veelgestelde vragen over Azure Rights Management | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 05/13/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 71ce491f-41c1-4d15-9646-455a6eaa157d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Veelgestelde vragen over Azure Rights Management

*Van toepassing op: Azure Rights Management, Office 365*

Een paar veelgestelde vragen over Microsoft [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)], ook wel aangeduid als Azure RMS:

## Wat heb ik nodig om Azure RMS te implementeren en hoe ga ik aan de slag?
Controleer eerst [Vereisten voor Azure Rights Management](requirements-azure-rms.md), dat informatie bevat over de opties voor cloudabonnementen, hoe u uw lokale servers kunt gebruiken met Azure RMS, welke implementatiescenario's momenteel niet worden ondersteund, welke apparaten en toepassingen Azure RMS ondersteunen en een koppeling als u een lijst met IP-adressen en domeinnamen nodig hebt voor firewalls en proxyservers. Het is wellicht ook verstandig de andere artikelen in deze sectie **Aan de slag ** en de sectie **Begrijpen en verkennen** te lezen voor meer algemene informatie over hoe [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] kan helpen de gegevens van uw organisatie te beveiligen, hoe het product werkt met toepassingen, wat de verschillen zijn met de on-premises versie van Active Directory Rights Management en om inzicht te krijgen in de termen en afkortingen die specifiek zijn voor [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)].

## Moeten bestanden in de cloud staan om te worden beveiligd met Azure RMS?
Nee, dit is een veelvoorkomend misverstand. De Azure Rights Management-service (en Microsoft) kunnen uw gegevens niet weergeven of opslaan. Dit is een vereiste van het proces voor informatiebeveiliging. Informatie die u beveiligt, wordt nooit verzonden naar of opgeslagen in Azure, tenzij u de informatie zelf expliciet opslaat in Azure of een andere cloudservice gebruikt waarmee informatie wordt opgeslagen in Azure. 

Zie voor meer informatie [Hoe werkt Azure RMS? Achter de schermen](../understand-explore/how-does-it-work.md) om te begrijpen hoe een geheim colarecept, dat lokaal is gemaakt en opgeslagen, wordt beveiligd met Azure RMS, maar lokaal aanwezig blijft.

## Kan ik Azure RMS integreren in mijn lokale servers?
Ja. Azure RMS kan worden geïntegreerd in uw lokale servers, zoals Exchange Server, SharePoint en Windows-bestandsservers. U doet dat met de [Rights Management-connector](../deploy-use/deploy-rms-connector.md). Of als u alleen geïnteresseerd bent in het gebruik van File Classification Infrastructure (FC) in combinatie met Windows Server, kunt u de [cmdlets voor RMS-beveiliging](https://technet.microsoft.com/library/mt601315%28v=ws.10%29.aspx) gebruiken. U kunt uw Active Directory-domeincontrollers ook synchroniseren met Azure AD voor een meer naadloze verificatiebeleving door gebruikers. U kunt dat bijvoorbeeld doen met [Azure AD Connect](http://azure.microsoft.com/documentation/articles/active-directory-aadconnect/).

Azure RMS genereert en beheert automatisch XrML-certificaten zoals vereist en gebruikt dus geen lokale PKI. Zie de sectie [Walkthrough of how Azure RMS works: First use, content protection, content consumption](../understand-explore/how-does-it-work.md#walkthrough-of-how-azure-rms-works-first-use-content-protection-content-consumption) (Overzicht van de werking van Azure RMS: eerste gebruik, beveiliging van inhoud, verbruik van inhoud) in het artikel [How does Azure RMS work?](../understand-explore/how-does-it-work.md) (Hoe werkt Azure RMS?) voor meer informatie over de manier waarop certificaten worden gebruikt in Azure RMS.

## Ik heb een hybride implementatie van Exchange waarbij sommige gebruikers op Exchange Online zitten en andere op Exchange Server. Wordt dit ondersteund door Azure RMS?
Absoluut, en het prettige is dat gebruikers beveiligde e-mailberichten en bijlagen naadloos kunnen beveiligen en verbruiken op beide Exchange-implementaties. Voor deze configuratie moet u [Azure RMS activeren](../deploy-use/activate-service.md), [IRM voor Exchange Online inschakelen](https://technet.microsoft.com/library/dn151475%28v=exchg.150%29.aspx) en vervolgens [de RMS-connector implementeren en configureren](../deploy-use/deploy-rms-connector.md) voor Exchange-Server.

## Zijn er stapsgewijze instructies om Exchange Online te configureren voor gebruik van Azure RMS?

Ja. Zie [Exchange Online: IRM configureren](../deploy-use/configure-office365.md#exchange-online-irm-configuration.md ) voor een typische reeks opdrachten waarmee Exchange Online wordt ingeschakeld voor gebruik van Azure RMS, voor de redenen waarom de Outlook Web App niet onmiddellijk de menuopties **Machtigingen instellen** weergeeft en voor de opdracht die u moet uitvoeren als u de sjablonen voor Azure RMS bijwerkt of wijzigt. 

## Als ik Azure RMS voor productie implementeer, zit mijn bedrijf dan vast aan deze oplossing of lopen we het risico de toegang te verliezen tot inhoud die werd beveiligd met Azure RMS?
Nee, u behoudt altijd de controle over uw gegevens en kunt deze blijven gebruiken, zelfs als u besluit niet langer met Azure RMS te werken. Zie [Azure Rights Management uit bedrijf nemen en deactiveren](../deploy-use/decommission-deactivate.md)voor meer informatie.

Voordat u echter uw Azure RMS-implementatie uit bedrijf neemt, willen we graag van u horen waarom u deze beslissing hebt genomen. Als Azure RMS niet voldoet aan uw zakelijke vereisten, kunt u contact met ons opnemen om te zien of er voor de nabije toekomst nieuwe functies zijn gepland en of er alternatieven zijn. Stuur een e-mailbericht naar [AskIPTeam@Microsoft.com](mailto:askipteam@microsoft.com?subject=Planning%20to%20decommission%20Azure%20RMS) zodat we uw technische en zakelijke vereisten met u kunnen bespreken.

## Kan ik controleren welke van mijn gebruikers Azure RMS kunnen gebruiken om inhoud te beveiligen?
Ja, Azure RMS heeft voor dit scenario controlemiddelen voor de onboarding van gebruikers. Zie voor meer informatie het gedeelte [Controlemiddelen voor onboarding configureren voor een gefaseerde implementatie](../deploy-use/activate-service.md#configuring-onboarding-controls-for-a-phased-deployment) in het artikel [Azure Rights Management activeren](../deploy-use/activate-service.md).

## Kan ik voorkomen dat gebruikers beveiligde documenten delen met specifieke organisaties?
Een van de grootste voordelen van Azure RMS is dat het business-to-business samenwerking ondersteunt zonder dat u expliciete vertrouwensrelaties hoeft te configureren voor elke partnerorganisatie, omdat Azure AD de verificatie voor u verzorgt.

Er is geen beheeroptie om te voorkomen dat gebruikers documenten veilig delen met specifieke organisaties. U wilt bijvoorbeeld een organisatie blokkeren die u niet vertrouwt of die een concurrent is. Voorkomen dat Azure RMS beveiligde documenten verzendt naar gebruikers in deze organisaties, heeft geen zin omdat uw gebruikers hun documenten dan zonder beveiliging zouden gaan delen. En dat is waarschijnlijk het laatste wat u binnen dit scenario zou willen. U zou bijvoorbeeld niet kunnen bepalen wie vertrouwelijke bedrijfsdocumenten deelt met welke gebruikers in deze organisaties. Dat kunt u wel wanneer het document (of e-mailbericht) is beveiligd met Azure RMS.

## Wanneer ik een beveiligd document deel met iemand buiten mijn bedrijf, hoe wordt die gebruiker dan geverifieerd?
Azure RMS gebruikt altijd een Azure Active Directory-account en een bijbehorend e-mailadres voor gebruikersverificatie, waardoor business-to-business samenwerking naadloos verloopt voor beheerders. Als de andere organisatie Azure-services gebruikt, hebben de gebruikers al accounts in Azure Active Directory, zelfs als deze accounts lokaal worden gemaakt en beheerd en vervolgens worden gesynchroniseerd naar Azure.  Als de organisatie werkt met Office 365, gebruikt deze service ook Azure Active Directory voor de gebruikersaccounts.  Als de organisatie van de gebruiker geen beheerde accounts in Azure heeft, kunnen gebruikers zich aanmelden voor [RMS voor individuen](../understand-explore/rms-for-individuals.md). Hierbij worden automatisch een niet-beheerde Azure-tenant en -map voor de organisatie gemaakt met een account voor de gebruiker, zodat deze gebruiker vervolgens kan worden geverifieerd voor Azure RMS.

De verificatiemethode voor deze accounts kan variëren, afhankelijk van hoe de beheerder in de andere organisatie de Azure Active Directory-accounts heeft geconfigureerd. Ze kunnen bijvoorbeeld gebruik maken van wachtwoorden die zijn gemaakt voor deze accounts, van Multi-Factor Authentication (MFA), van federatie of van wachtwoorden die zijn gemaakt in Active Directory Domain Services en vervolgens zijn gesynchroniseerd met Azure Active Directory.

## Kan ik gebruikers van buiten mijn bedrijf toevoegen aan aangepaste sjablonen?
Ja.  Wanneer u aangepaste sjablonen maakt die eindgebruikers (en beheerders) kunnen selecteren in toepassingen, kunnen zij gegevensbeveiliging snel en eenvoudig toepassen met de vooraf door u gedefinieerde beleidsregels. U kunt in de sjabloon onder andere instellen wie toegang heeft tot de inhoud. U kunt daarbij gebruikers en groepen van binnen uw organisatie en gebruikers van buiten uw organisatie opgeven.

Gebruik de [Windows PowerShell-module voor Azure Rights Management](../deploy-use/install-powershell.md) om gebruikers van buiten uw organisatie op te geven:

-   **Gebruik een rechtendefinitieobject om een sjabloon te maken of bij te werken**.    Geef de externe e-mailadressen en de bijbehorende rechten op in een rechtendefinitieobject, dat u vervolgens kunt gebruiken om een sjabloon te maken of bij te werken. U geeft het rechtendefinitieobject op met de cmdlet [New-AadrmRightsDefinition](https://msdn.microsoft.com/library/azure/dn727080.aspx) om een variabele te maken en geeft deze variabele vervolgens door aan de parameter -RightsDefinition met de cmdlet [Add-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727075.aspx) (voor een nieuwe sjabloon) of met de cmdlet [Set-AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727076.aspx) (als u een bestaande sjabloon wijzigt). Als u deze gebruikers echter aan een bestaande sjabloon toevoegt, moet u rechtendefinitieobjecten definiëren voor de bestaande groepen in de sjablonen en niet alleen voor de externe gebruikers.

Zie [Aangepaste sjablonen configureren voor Azure Rights Management](../deploy-use/configure-custom-templates.md) voor meer informatie over aangepaste sjablonen.

## Werkt Azure RMS met dynamische groepen in Azure AD?
Met een Azure AD Premium-functie kunt u een dynamisch lidmaatschap voor groepen configureren door [op kenmerken gebaseerde regels](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) op te geven. Wanneer u een beveiligingsgroep in Azure AD maakt, biedt dit groepstype ondersteuning voor dynamisch lidmaatschap, maar biedt het geen ondersteuning voor een e-mailadres en kan het dus niet worden gebruikt met Azure RMS. U kunt nu echter een nieuw groepstype in Azure AD maken dat dynamisch lidmaatschap en e-mail beide ondersteunt. Wanneer u een nieuwe groep toevoegt in de klassieke Azure-portal, kunt u het **GROEPSTYPE** **Office 365 "Voorbeeld"** kiezen. Omdat dit een groep met e-mail is, kunt u deze met Azure RMS gebruiken.

Zoals de optienaam duidelijk aangeeft, is dit nieuwe groepstype alleen nog maar een voorbeeld. Extra functies en nieuwe documentatie komen later. In afwachting daarvan wilden we bevestigen dat u dit nieuwe groepstype met Azure RMS kunt gebruiken.


## Welke apparaten en welke typen worden ondersteund door Azure RMS?
Zie [Clientapparaten die Azure RMS ondersteunen](../get-started/requirements-client-devices.md) voor een lijst met ondersteunde apparaten. Omdat niet alle ondersteunde apparaten momenteel alle functies van RMS ondersteunen, moet u in hetzelfde artikel ook de tabel [Functies van clientapparaat](../get-started/requirements-client-devices.md#client-device-capabilities) raadplegen.

Azure RMS kan alle bestandstypen ondersteunen. Voor tekst-, afbeeldings-, Microsoft Office- (Word, Excel, PowerPoint), .pdf-bestanden en sommige andere bestandstypen, biedt Azure RMS systeemeigen beveiliging zoals versleuteling en het afdwingen van rechten (machtigingen). Voor alle andere toepassingen en bestandstypen biedt algemene beveiliging bestandsinkapseling en verificatie om te controleren of een gebruiker is gemachtigd om het bestand te openen.

Zie voor een lijst met bestandnaamsextensies die systeemeigen worden ondersteund door Azure RMS, het gedeelte [Ondersteunde bestandstypen en bestandsnaamextensies](../rms-client/sharing-app-admin-guide-technical.md#supported-file-types-and-file-name-extensions) in de [Beheerdershandleiding voor de Rights Management-toepassing voor delen](../rms-client/sharing-app-admin-guide.md). Bestandsnaamextensies die niet worden vermeld, worden ondersteund via de RMS-toepassing voor delen die automatisch algemene beveiliging toepast op deze bestanden.

## Is het gekoppelde tijdelijke bestand ook met RMS beveiligd wanneer ik een Office-document dat met RMS is beveiligd open?

Nee. In dit scenario bevat het geassocieerde tijdelijke bestand geen gegevens van het originele document maar alleen wat de gebruiker invoert terwijl het bestand is geopend. In tegenstelling tot het oorspronkelijke bestand, is het tijdelijke bestand natuurlijk niet bedoeld om gedeeld te worden. Deze bestanden blijven op het apparaat en worden beveiligd met lokale beveiligingsmaatregelen zoals BitLocker en EFS.

## Wanneer ondersteunt u migratie vanaf AD RMS?
In eerste instantie bood Azure RMS geen ondersteuning voor migratie vanaf een lokale implementatie van Rights Management, zoals AD RMS. Maar nu wordt dat wel ondersteund.

Zie voor meer informatie [Migreren van AD RMS naar Azure Rights Management](../plan-design/migrate-from-ad-rms-to-azure-rms.md).

## We willen heel graag BYOK gebruiken met Azure RMS, maar hebben vernomen dat dit niet kan met Exchange Online. Wat is uw advies?
Laat deze huidige beperking u er niet van weerhouden Azure RMS te implementeren. Als u Exchange Online en BYOK (Bring Your Own Key) wilt gebruiken, raden wij u aan Azure RMS nu te implementeren in de standaardmodus voor sleutelbeheer, waarbij Microsoft uw sleutel genereert en beheert. Op die manier zijn al uw belangrijke bestanden en e-mailberichten nu beschermd en kunt u later overstappen op BYOK (bijvoorbeeld zodra Exchange Online BYOK wel gaat ondersteunen).

Als uw bedrijfsbeleid echter het gebruik van een Hardware Security Module (HSM) voorschrijft en dit anders uw Azure RMS-implementatie blokkeert, is een andere mogelijkheid Azure RMS nu met BYOK te implementeren met een verminderde RMS-functionaliteit voor Exchange. Zie voor meer informatie [BYOK-prijzen en beperkingen](../plan-design/byok-price-restrictions.md) in [Uw Azure Rights Management-tenantsleutel plannen en implementeren](../plan-design/plan-implement-tenant-key.md).

## Een functie die ik nodig heb, lijkt niet te werken met door SharePoint beveiligde bibliotheken. Wordt ondersteuning voor mijn functie gepland?
Op dit moment ondersteunt SharePoint met RMS beveiligde documenten via met IRM beveiligde bibliotheken, die geen ondersteuning bieden voor aangepaste sjablonen, documenten bijhouden en bepaalde andere functies. Zie voor meer informatie het gedeelte [SharePoint Online en SharePoint Server](../understand-explore/office-apps-services-support.md#sharepoint-online-and-sharepoint-server) in het artikel [Office-toepassingen en -services](../understand-explore/office-apps-services-support.md).

Als u geïnteresseerd bent in een specifieke functie die nog niet wordt ondersteund, raden we u aan de aankondigingen op de [RMS-teamblog](http://blogs.technet.com/b/rms/) goed in het oog te houden.

## Hoe configureer ik OneDrive voor Bedrijven in SharePoint Online, zodat gebruikers hun bestanden veilig met mensen binnen en buiten het bedrijf kunnen delen?
Standaard configureert u dit als Office 365-beheerder niet. De gebruikers doen dat.

Net zoals een SharePoint-sitebeheerder IRM inschakelt en configureert voor een SharePoint-bibliotheek waarvan deze eigenaar is, is OneDrive voor Bedrijven bedoeld voor gebruikers die IRM voor hun eigen OneDrive voor Bedrijven-bibliotheek willen inschakelen en configureren.  U kunt dit met PowerShell echter in hun plaats doen. Zie voor instructies het gedeelte [SharePoint Online en OneDrive voor Bedrijven: IRM-configuratie](../deploy-use/configure-office365.md#sharepoint-online-and-onedrive-for-business-irm-configuration) in het artikel [Office 365: configuratie voor clients en onlineservices](../deploy-use/configure-office365.md).

## Hebt u tips of trucs voor een succesvolle RMS-implementatie?
Na veel implementaties te hebben overzien en te hebben geluisterd naar onze klanten, partners, adviseurs en supporttechnici, is een van de beste tips die we op grond van onze ervaring kunnen geven: **ontwerp en implementeer een eenvoudig rechtenbeleid**.

Omdat Azure RMS veilig delen met iedereen ondersteunt, kunt u ambitieus zijn wat betreft het bereik van uw beveiligingssystemen. Maar wees voorzichtig met uw rechtenbeleid. Voor veel organisaties vloeit de grootste impact op de bedrijfsactiviteiten voort uit het voorkomen van gegevenslekken door toepassing van de standaardrechtenbeleidssjabloon, die de toegang beperkt tot mensen in uw organisatie. Natuurlijk kunt u veel meer granulair te werk gaan als dat nodig is: voorkomen dat mensen afdrukken, bewerken, enzovoort. Maar gebruik deze meer granulaire beperkingen bij wijze van uitzondering voor documenten die echt beveiliging op hoog niveau nodig hebben. Implementeer deze meer beperkende beleidsregels niet op de eerste dag, maar plan een meer gefaseerde benadering.

## Welke functies kunnen wel of niet met de verschillende abonnementen op Azure RMS worden gebruikt?
Voor de betaalde abonnementen die Azure RMS (Office 365, Azure RMS Premium en Enterprise Mobility Suite) ondersteunen, zijn er een paar verschillen in de RMS-functies die worden ondersteund. Zie voor een lijst hiervan [Vergelijking van Rights Management Services (RMS)-aanbiedingen](http://technet.microsoft.com/dn858608).

Het gratis abonnement dat Azure RMS (RMS voor individuen) ondersteunt, ondersteunt het verbruik van inhoud die is beveiligd met Azure RMS. Zie voor meer informatie [RMS voor personen en Azure Rights Management](../understand-explore/rms-for-individuals.md).

## Waar vind ik technische gegevens over het gratis abonnement op Azure RMS (RMS voor individuen)? Bijvoorbeeld over hoe het werkt, hoe ik controle kan krijgen over de accounts en welke domeinen niet kunnen worden gebruikt?
U vindt antwoorden op deze vragen in [RMS voor individuen en Azure Rights Management](../understand-explore/rms-for-individuals.md) en verwante artikelen.

## Hoe krijgen we weer toegang tot bestanden die zijn beveiligd door een medewerker die de organisatie heeft verlaten?
Gebruik daarvoor de functie Supergebruiker van Azure RMS. Hiermee krijgen gemachtigde gebruikers volledige eigenaarsrechten voor alle gebruikslicenties die zijn verleend door de RMS-tenant van uw organisatie. Via deze zelfde functie kunnen bestanden naar behoefte met gemachtigde services worden geïndexeerd en geïnspecteerd.

Zie voor meer informatie [Supergebruikers configureren voor Azure Rights Management en detectieservices of gegevensherstel](../deploy-use/configure-super-users.md).

## Kan met Rights Management het maken van schermopnamen worden voorkomen?
Als u het [gebruiksrecht](../deploy-use/configure-usage-rights.md) **Kopiëren** niet verleent, kan met Rights Management worden voorkomen dat er schermopnamen worden gemaakt met veel van de algemeen gebruikte hulpprogramma's voor het vastleggen van schermopnamen van de Windows-platformen (Windows 7, Windows 8.1, Windows 10, Windows Phone) en Android. Op iOS- en Mac-apparaten kunnen schermopnamen echter niet worden geblokkeerd en browsers (bijvoorbeeld indien gebruikt met Outlook Web App en Office Online) kunnen schermopnamen evenmin voorkomen

Het blokkeren van schermopnamen kan helpen voorkomen dat vertrouwelijke of gevoelige informatie per ongeluk of uit nalatigheid wordt geopenbaard. Maar er zijn veel manieren waarop een gebruiker gegevens kan delen die op een scherm worden weergegeven, en een schermopname is daar maar één voorbeeld van. Een gebruiker die weergegeven informatie wil delen, kan deze bijvoorbeeld fotograferen met een mobiele telefoon, de gegevens overtypen of ze gewoon aan iemand anders vertellen.

Zoals blijkt uit deze voorbeelden, kan met technologie niet altijd worden voorkomen dat gebruikers ongewenste informatie delen, zelfs niet als alle platforms en alle software de Rights Management-API's voor het blokkeren van schermopnamen zouden ondersteunen. Rights Management kan helpen uw belangrijke gegevens te beschermen met een machtigings- en gebruiksbeleid, maar deze beheeroplossing voor bedrijfsrechten moet worden gebruikt in combinatie met andere controlemiddelen. Implementeer bijvoorbeeld fysieke beveiliging, controleer en bewaak personen die officieel toegang hebben tot de gegevens van uw organisatie en investeer in gebruikerseducatie, zodat gebruikers weten welke gegevens niet mogen worden gedeeld.

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

-   Azure Active Directory-bibliotheek: [Azure Active Directory](http://msdn.microsoft.com/library/azure/jj673460.aspx)

-   Office 365-bibliotheek: [Office 365](http://technet.microsoft.com/library/dn127064%28v=office.14%29.aspx)

## Wat moet ik doen als ik mijn vraag hier niet vind?
Gebruik de koppelingen en resources die worden vermeld in [Information and support for Azure Rights Management](information-support.md) (Informatie en ondersteuning voor Azure Rights Management).

Daarnaast zijn er Veelgestelde vragen voor eindgebruikers:

-   [Veelgestelde vragen over Rights Management-toepassing voor delen voor Windows](https://technet.microsoft.com/dn467883)

-   [Veelgestelde vragen over Rights Management-toepassing voor delen voor mobiele en Mac-platforms](https://technet.microsoft.com/dn451248)

-   [Veelgestelde vragen over het bijhouden van documenten](http://go.microsoft.com/fwlink/?LinkId=523977)

Deze pagina met veelgestelde vragen wordt regelmatig bijgewerkt met nieuwe toevoegingen, die worden vermeld in de maandelijkse aankondigingen van documentatie-updates op de blog van het [Microsoft Rights Management (RMS)-team](http://blogs.technet.com/b/rms/).

> [!TIP] U deze documentatieaankondigingen met de [docs tag](http://blogs.technet.com/b/rms/archive/tags/docs/) gemakkelijk terugvinden op de blog.




<!--HONumber=May16_HO2-->


