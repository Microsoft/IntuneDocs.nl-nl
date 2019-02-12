---
title: Uw Microsoft Intune-ontwerp maken
titlesuffix: Microsoft Intune
description: Dit artikel helpt u bij het maken van een ontwerp voor een Microsoft Intune-ontwerp en -implementatie die uitsluitend voor de cloud zijn bestemd.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 10/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a8e38e29-f5e3-4a71-a170-d3b1a06e37c6
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 192e0ac0e67fb519f1dcd2ff9faf0d7748942997
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55834531"
---
# <a name="create-a-design"></a>Een ontwerp maken

Uw Intune-ontwerp is gebaseerd op de informatie die u verzamelt en besluiten die u neemt bij het doorlopen van de overige [secties in deze handleiding](planning-guide.md). De volgende zaken worden bijeengebracht:

-   De huidige omgeving

-   Intune-implementatieopties

-   Identiteitsvereisten voor externe afhankelijkheden

-   Overwegingen met betrekking tot het apparaatplatform

-   Vereisten waaraan moet worden voldaan  

Hoewel er een minimum aan vereisten voor de on-premises infrastructuur is, is een ontwerpplan nog steeds nuttig omdat u over de juiste beheeroplossing voor mobiele apparaten beschikt die aansluit bij uw doelen, doelstellingen en vereisten.

Laten we elk van deze gebieden eens nader bekijken. 

## <a name="record-your-current-environment"></a>Uw huidige omgeving vastleggen
Bovendien vinden er tijdens de implementatie- en testfase regelmatig wijzigingen aan het ontwerp plaats. Gebruik het ontwerpplan om deze wijzigingen te documenteren zodra ze plaatsvinden, evenals de achterliggende idee.

Uw huidige omgeving kan van invloed zijn op ontwerpbeslissingen en moet daarom worden gedocumenteerd als referentie bij het maken van andere Intune-ontwerpbeslissingen. Hieronder vindt u enkele voorbeelden van hoe u de huidige omgeving kunt vastleggen:

-   **Identiteit in de cloud**

    -   Gebruikt u DirSync of Azure Active Directory Connect (Azure AD)?

    -   Is uw omgeving federatief?

    -   Is meervoudige authenticatie (MFA) ingeschakeld?

-   **E-mailomgeving**

    -   Gebruikt u Exchange? On-premises of in de cloud?

    -   Zit u midden in een project en wilt u Exchange naar de cloud migreren?

-   **Huidige oplossing met Mobile Device Management (MDM)**

    -   Gebruikt u momenteel andere MDM-oplossingen?

    -   Welke MDM-oplossingen gebruikt u voor zakelijke en BOYD-scenario's?

    -   Van welke mogelijkheden maakt u gebruik (bijvoorbeeld apparaatinstellingen voor apps of Wi-Fi-configuraties)?

    -   Welke apparaatplatformen worden ondersteund?

    -   Welke groepen en hoeveel gebruikers werken er met de MDM-oplossing?

-   **Certificaatoplossing**

    -   Hebt u een certificaatoplossing geïmplementeerd?

    -   Wat voor soort certificaten gebruikt u?

-   **Beheer van systemen**

    -   Hoe beheert u uw pc- en serveromgeving?

    -   Gebruikt u System Center Configuration Manager? Werkt u met een platform voor systeembeheer van derden?

-   **VPN-oplossing**

    -   Wat is uw VPN-oplossing?

    -   Wordt deze gebruikt voor zowel zakelijke als BYOD-scenario's?

Wanneer u de huidige MDM-omgeving vastlegt, moet u rekening houden met alle projecten of eventuele andere in gebruik zijnde plannen die van invloed kunnen zijn op uw omgeving. Hieronder ziet u een voorbeeld van een manier om de huidige omgeving vast te leggen bij het maken van uw Intune-ontwerp:

| **Gebied waarvoor de oplossing geldt** | **Huidige omgeving** | **Opmerkingen** |
|---|---|---|
| **Identiteit** | Azure AD, Azure AD Connect, niet federatief, geen MFA | Project aanwezig om MFA tegen het eind van het jaar in te schakelen |                 
| **E-mailomgeving** | Exchange On-premises, Exchange Online | Momenteel vindt migratie plaats van Exchange On-premises naar Exchange Online. 75% van postvakken gemigreerd. De laatste 25% wordt gemigreerd voordat Intune-pilot begint. |                
| **SharePoint** | SharePoint On-premises | Er zijn geen plannen om over te stappen op SharePoint Online |  
| **Huidig MDM** | Exchange ActiveSync |  |
| **Certificaatoplossing** | Microsoft Server 2012 R2, AD Certificate Services | Gebruik alleen PKI voor websiteservers |
| **Systeembeheer** | System Center Configuration Manager CB 1606 | Wil een hybride oplossing met Intune onderzoeken |
| **VPN-oplossing** | Cisco AnyConnect |  |


U kunt [een sjabloon van de bovenstaande tabel downloaden](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) om als leidraad te gebruiken bij het ontwikkelen van uw Intune-ontwerpplan.

## <a name="choose-an-intune-deployment-option"></a>Kies een optie voor Intune-implementatie

Intune biedt twee opties voor implementatie: zelfstandig en hybride. Zelfstandig verwijst naar de Intune-service die wordt uitgevoerd in de cloud, hybride verwijst naar de integratie van Intune met System Center Configuration Manager. Deze handleiding is voornamelijk bedoeld voor het gebruik van de zelfstandige optie. [Beslis welke optie het beste aansluit op uw bedrijfsbehoeften.](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management)

## <a name="intune-tenant-location"></a>Locatie van Intune-tenant

Als uw organisatie wereldwijd opereert, moet u ook bepalen wat de locatie van uw tenant is wanneer u zich abonneert op de service. Het land wordt gedefinieerd wanneer u zich voor het eerst aanmeldt voor een Intune-abonnement en de regio's kiest die voor u van belang zijn, zoals hieronder worden gedefinieerd:

-   Noord-Amerika

-   Europa, Midden-Oosten en Afrika

-   Azië en Pacific

>[!IMPORTANT]
> Het is niet mogelijk het land of de tenantlocatie naderhand te wijzigen.

## <a name="external-dependencies"></a>Externe afhankelijkheden

Externe afhankelijkheden zijn services en producten die geen deel uitmaken van Intune, maar wel een vereiste van Intune zijn of kunnen worden geïntegreerd met Intune. Het is belangrijk om vereisten voor alle externe afhankelijkheden vast te stellen en hoe ze moeten worden geconfigureerd. Enkele voorbeelden van veelvoorkomende externe afhankelijkheden zijn:

-   Identiteit

-   Gebruikers- en apparaatgroepen

-   Public Key Infrastructure (PKI)

Deze algemene externe afhankelijkheden worden hieronder nader onderzocht

### <a name="identity"></a>Identiteit

Identiteit is de manier waarop de gebruikers worden geïdentificeerd die tot uw organisatie behoren en die een apparaat registreren. Intune vereist Azure Active Directory (Azure AD) als provider van gebruiker-id's. Als u deze service al gebruikt, kunt u gebruikmaken van uw bestaande identiteit in de cloud. Azure AD Connect is bovendien het aanbevolen hulpmiddel om uw lokale gebruikers-id's te synchroniseren met Microsoft-cloudservices. Als uw organisatie al met Office 365 werkt, is het belangrijk dat Intune van dezelfde Azure AD-omgeving gebruikmaakt.

Meer informatie over de volgende Intune-identiteitsvereisten :

- [Identiteitsvereisten](https://docs.microsoft.com/azure/active-directory/understand-azure-identity-solutions).

- [Vereisten voor adreslijstsynchronisatie](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

- [Vereisten voor meervoudige verificatie](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).

### <a name="user-and-device-groups"></a>Gebruikers- en apparaatgroepen

De gebruikers- en apparaatgroepen bepalen het doel van een implementatie, waaronder het beleid, de toepassingen en de profielen. U dient te bepalen welke gebruikers- en apparaatgroepen er vereist zijn.

U wordt aangeraden alle groepen te maken in de on-premises Active Directory en vervolgens met Azure AD te synchroniseren. Meer informatie over het plannen en maken van gebruikers- en apparaatgroepen:

-   [Uw gebruikers- en apparaatgroepen plannen.](users-add.md)

-   [Gebruikers- en apparaatgroepen maken.](groups-add.md)

### <a name="public-key-infrastructure-pki"></a>Public Key Infrastructure (PKI)
Public Key Infrastructure verstrekt certificaten aan apparaten of gebruikers voor een veilige verificatie van services. Intune biedt ondersteuning voor een Microsoft PKI-infrastructuur. Apparaat- en gebruikerscertificaten kunnen worden uitgegeven voor een mobiel apparaat om te voldoen aan verificatievereisten op basis van certificaten. Voordat u certificaten gaat gebruiken, moet u vaststellen of u ze nodig hebt, of de netwerkinfrastructuur verificatie op basis van certificaten kan ondersteunen en of er momenteel in de bestaande omgeving certificaten worden gebruikt.

Als u van plan bent voor Intune certificaten te gebruiken met VPN-, Wi-Fi- of e-mailprofielen, moet u controleren of er een ondersteunde [PKI-infrastructuur](certificates-configure.md) is, die geschikt is om certificaatprofielen te maken en implementeren.

Als er SCEP-certificaten worden uitgegeven, moet u bovendien bepalen welke server fungeert als host voor de functie Network Device Enrollment Service (NDES) en hoe de communicatie wordt uitgevoerd.

Meer informatie over:

-   [Intune-certificaatprofielen configureren](certificates-configure.md)

-   [De certificaatinfrastructuur voor SCEP configureren](certificates-scep-configure.md)

-   [De certificaatinfrastructuur voor PFX configureren](certficates-pfx-configure.md)




## <a name="device-platform-considerations"></a>Overwegingen met betrekking tot het apparaatplatform

Kijk eens goed naar de volgende aspecten van uw apparaten, zodat u beter begrijpt hoe u ze op de juiste wijze moet beheren.

-   Ondersteunde apparaatplatformen

-   Apparaten

-   Apparaateigendom

-   Bulkinschrijving

Laten we deze gebieden eens nader bekijken.

### <a name="determine-supported-device-platforms"></a>Ondersteunde apparaatplatformen vaststellen

U moet tijdens het maken van uw ontwerp weten welke apparaten in de omgeving worden opgenomen en controleren of ze al dan niet worden ondersteund door Intune. Intune biedt ondersteuning voor iOS-, Android- en Windows-platforms.

[Volledige lijst met ondersteunde apparaten voor Intune.](supported-devices-browsers.md)

### <a name="devices"></a>Apparaten

Intune beheert mobiele apparaten ter beveiliging van zakelijke gegevens en om ervoor te zorgen dat eindgebruikers vanaf meer locaties kunnen werken. Omdat Intune talloze apparaatplatformen ondersteunt, is het raadzaam om de apparaten, OS-platformen en versies te documenteren die worden ondersteund in het ontwerp van uw organisatie. Bijvoorbeeld:

| **Apparaatplatform** | **Besturingssysteemversies** |
|:---:|:---:|
| iOS - iPhone | 10.0+ |                
| iOS - iPad | 10.0+ |               
| Android – Samsung Knox Standard | 4.0+ |
| Windows 10-tablet | 10+ |


U kunt [een sjabloon van de bovenstaande tabel downloaden](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) om als leidraad te gebruiken bij het ontwikkelen van uw lijst met apparaten.
### <a name="device-ownership"></a>Apparaateigendom

Intune ondersteunt zowel bedrijfseigen apparaten als persoonlijke apparaten. Een apparaat wordt beschouwd als bedrijfseigendom als u het inschrijft bij een apparaatinschrijvingsbeheerder of apparaatinschrijvingsprogramma. Een apparaat kan bijvoorbeeld worden ingeschreven via Apple Device Enrollment Program (DEP), worden gemarkeerd als bedrijfseigendom en in een apparaatgroep worden geplaatst die specifieke beleidsregels en apps van het bedrijf ontvangt.

Zie [sectie 3: use-casescenariovereisten bepalen](planning-guide-requirements.md) voor meer informatie over voorbeelden van apparaten in bedrijfseigendom en BYOD-apparaten.

### <a name="bulk-enrollment"></a>Bulkinschrijving

 U kunt apparaten bulksgewijs op verschillende manieren inschrijven, afhankelijk van het platform. Als bulksgewijze inschrijving is vereist, bepaalt u eerst [de juiste methode voor bulksgewijze inschrijving](device-enrollment.md), die u vervolgens opneemt in uw ontwerp.

## <a name="feature-requirements"></a>Functievereisten

In deze secties worden de volgende functies en mogelijkheden beschreven die zijn afgestemd op de vereisten voor uw use-case-scenario:

-   Beleidsregels voor voorwaarden

-   Configuratiebeleid

-   Resourceprofielen

-   Apps

-   Nalevingsbeleid

-   Voorwaardelijke toegang

Laten we elk van deze gebieden eens nader bekijken.

### <a name="terms-and-conditions-policies"></a>Beleidsregels voor voorwaarden

U kunt [voorwaarden](terms-and-conditions-create.md) gebruiken om beleidsregels of voorwaarden uit te leggen die een eindgebruiker voordat deze een apparaat kan inschrijven. Intune ondersteunt de mogelijkheid om meerdere beleidsregels voor voorwaarden toe te voegen aan en te implementeren voor gebruikersgroepen.

U moet zelf bepalen of er beleidsregels voor voorwaarden nodig zijn. Als dat inderdaad het geval is, wie is er dan verantwoordelijk voor het verspreiden van deze informatie in de organisatie. Hieronder ziet u een voorbeeld van het vastleggen van de beleidsregels voor voorwaarden.

| **Naam van de voorwaarden** | **Use case** | **Doelgroep** |
|:---:|:---:|:---:|
| Bedrijfsvoorwaarden | Bedrijf | Zakelijke gebruikers |                 
| Voorwaarden BYOD | BYOD | BYOD-gebruikers |                


U kunt [een sjabloon uit de bovenstaande tabel downloaden](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) om uw voorwaarden aan uw gebruikersgroepen toe te wijzen.

### <a name="configuration-policies"></a>Configuratiebeleid

Gebruik configuratiebeleid wordt om beveiligingsinstellingen en -functies op een apparaat te beheren. Raadpleeg bij het ontwerpen van uw configuratiebeleid de sectie met de casevereisten om de voor Intune-apparaten vereiste configuraties te bepalen. Documenteer de instellingen en de wijze waarop ze worden geconfigureerd. Documenteer ook voor welke gebruikers- of apparaatgroepen ze worden gebruikt.

U moet ten minste één configuratiebeleid per platform maken. U kunt desgewenst meer dan één configuratiebeleid per platform maken. Hieronder ziet u een voorbeeld van het ontwerpen van de vier verschillende configuratiebeleidsregels voor verschillende platformen en use-case-scenario's.

| **Naam van beleid** | **Apparaatplatform** | **Instellingen** | **Doelgroep** |   
|:---:|:---:|:---:|:---:|
| Bedrijfseigendom - iOS | iOS | Pincode is vereist, lengte: 6, Cloudback-up beperken | Bedrijfsapparaten |                                                           
| Bedrijfseigendom - Android | Android | Pincode is vereist, lengte: 6, Cloudback-up beperken | Bedrijfsapparaten |                                                           
| BYOD - iOS  | iOS | Pincode is vereist, lengte: 4 | BYOD-apparaten |
| BYOD - Android  | Android | Pincode is vereist, lengte: 4 | BYOD-apparaten |


U kunt [een sjabloon uit de bovenstaande tabel downloaden](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) om de behoeften van uw configuratiebeleid vast te stellen.

### <a name="profiles"></a>Profielen

Gebruik profielen om de eindgebruiker verbinding te laten maken met bedrijfsgegevens. Intune ondersteunt veel typen profielen. Raadpleeg de use-cases en vereisten om te bepalen wanneer de profielen worden geconfigureerd. Alle apparaatprofielen worden gecategoriseerd op platformtype en moeten worden opgenomen in de ontwerpdocumentatie.

-   Certificaatprofielen

-   Wi-Fi-profiel

-   VPN-profiel

-   E-mailprofiel

Laten we elk profieltype eens nader onderzoeken.

#### <a name="certificate-profiles"></a>Certificaatprofielen

Met behulp van certificaatprofielen kan Intune een certificaat uitgeven aan een gebruiker of apparaat. Intune ondersteunt het volgende:

-   Simple Certificate Enrollment Protocol (SCEP)

-   Vertrouwd basis-CA-certificaat

-   PFX-certificaat.

Het verdient aanbeveling om vast te leggen welke gebruikersgroep een certificaat nodig heeft, hoeveel certificaatprofielen u nodig hebt en voor welke gebruikersgroepen ze moeten worden geïmplementeerd.

>[!NOTE]
> Houd er rekening mee dat het vertrouwde basiscertificaat vereist is voor het SCEP-certificaat. Zorg er daarom voor dat alle gebruikers met het SCEP-certificaat ook een vertrouwd basiscertificaat krijgen toegewezen. Als u SCEP-certificaten nodig hebt, ontwerpt u welke SCEP-certificaatsjablonen u nodig hebt en legt u deze vast.

Hier volgt een voorbeeld van hoe u de certificaten tijdens het ontwerpen kunt vastleggen:

| **Type** | **Profielnaam** | **Apparaatplatform** | **Use cases** |   
|:---:|:---:|:---:|:---:|
| Basis-CA | Bedrijfseigendom, Basis-CA | Android, iOS, Windows Mobile | Bedrijfseigendom, BYOD  |                                                           
| SCEP | Gebruikerscertificaat | Android, iOS, Windows Mobile | Bedrijfseigendom, BYOD |                                                           


U kunt [een sjabloon uit de bovenstaande tabel downloaden](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) om de behoeften van uw certificaatprofiel vast te stellen.

#### <a name="wi-fi-profile"></a>Wi-Fi-profiel

Wi-Fi-profielen worden gebruikt om een mobiel apparaat automatisch te verbinden met een draadloos netwerk. Intune biedt ondersteuning voor het implementeren van Wi-Fi-profielen op alle ondersteunde platformen. Meer informatie over [hoe Intune Wi-Fi-profielen ondersteunt.](wi-fi-settings-configure.md)

Hieronder ziet u een voorbeeld van een ontwerp voor een Wi-Fi-profiel:

| **Type** | **Profielnaam** | **Apparaatplatform** | **Use cases** |   
|:---:|:---:|:---:|:---:|
| Wi-Fi | Wi-Fi-profiel Azië | Android | Bedrijfseigendom, BYOD regio Azië|                                                           
| Wi-Fi | Wi-Fi-profiel Noord-Amerika | Android, iOS, Windows 10 Mobile | Bedrijfseigendom, BYOD regio Noord-Amerika |                                                           


U kunt [een sjabloon uit de bovenstaande tabel downloaden](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) om de behoeften van uw Wi-Fi-profiel vast te stellen.

#### <a name="vpn-profile"></a>VPN-profiel

Met VPN-profielen kunnen gebruikers veilig toegang krijgen tot uw netwerk vanaf externe locaties. Intune ondersteunt VPN-profielen van systeemeigen mobiele VPN-verbindingen en externe leveranciers. Meer informatie over [VPN-profielen en leveranciers die worden ondersteund door Intune](vpn-settings-configure.md).

Hieronder ziet u een voorbeeld van het vastleggen van het ontwerp van een VPN-profiel.

| **Type** | **Profielnaam** | **Apparaatplatform** | **Use cases** |   
|:---:|:---:|:---:|:---:|
| VPN | VPN Cisco, alle verbindingsprofielen | Android, iOS, Windows 10 Mobile | Bedrijfseigendom, BYOD Noord-Amerika en Duitsland|                                                           
| VPN | Pulse Secure | Android | Bedrijfseigendom, BYOD regio Azië |                                                           


U kunt [een sjabloon uit de bovenstaande tabel downloaden](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) om de behoeften van uw VPN-profiel vast te stellen.
#### <a name="email-profile"></a>E-mailprofiel

Met e-mailprofielen kan een e-mailclient automatisch worden ingesteld met verbindingsgegevens en e-mailconfiguratie. Intune ondersteunt e-mailprofielen op sommige apparaten. Meer informatie over [e-mailprofielen en welke platformen worden ondersteund](email-settings-configure.md).

Hieronder ziet u een voorbeeld van het vastleggen van het ontwerp van e-mailprofielen:

| **Type** | **Profielnaam** | **Apparaatplatform** | **Use cases** |   
|:---:|:---:|:---:|:---:|
| E-mailprofiel | E-mailprofiel voor iOS | iOS | Bedrijfseigendom - Informatiemedewerker BYOD |                                                           
| E-mailprofiel | E-mailprofiel Android Knox | Android Knox | BYOD |


U kunt [een sjabloon uit de bovenstaande tabel downloaden](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) om de behoeften van uw e-mailprofiel vast te stellen.
### <a name="apps"></a>Apps

U kunt Intune gebruiken om de gebruikers of apparaten op verschillende manieren van apps te voorzien. Het type app kan bestaan uit apps voor software-installatie, apps uit een openbare app-store, externe koppelingen of beheerde iOS-apps. Naast de afzonderlijke app-implementaties kunt u in volumes aangeschafte apps beheren en implementeren via de volume-aankoopprogramma's voor iOS en Windows. Meer informatie over:

-   [De typen apps die u kunt leveren](app-management.md)

-   [iOS Volume Purchase Program for Business (VPP)](vpp-apps-ios.md)

-   [Microsoft Store voor Bedrijven-apps](windows-store-for-business.md)

#### <a name="app-type-requirements"></a>Vereisten voor app-typen

Aangezien apps kunnen worden geïmplementeerd voor gebruikers en apparaten, wordt u aangeraden te beslissen welke apps door Intune worden beheerd. Probeer de volgende vragen te beantwoorden tijdens het samenstellen van de lijst:

-   Is voor de apps integratie met cloudservices vereist?

-   Zullen alle apps beschikbaar zijn voor BYOD-gebruikers?

-   Welke implementatieopties zijn er voor deze apps beschikbaar?

-   Moet uw bedrijf zijn partners toegang verlenen tot gegevens van SaaS-apps (Software-as-a-Service)?

-   Hebben de apps internettoegang vanaf de apparaten van de gebruikers nodig?

-   Zijn de apps openbaar beschikbaar in een app-store of zijn het aangepaste LOB-apps (Line-Of-Business)?


#### <a name="app-protection-policies"></a>Beleid voor app-beveiliging

Met beleid voor app-beveiliging kan het verlies van gegevens tot een minimum worden beperkt door te definiëren hoe de app de bedrijfsgegevens beheert. Intune ondersteunt beleid voor app-beveiliging voor elke app die functioneert met beheer van mobiele apps. Bij het ontwerpen van het beleid voor app-beveiliging moet u besluiten welke beperkingen u wilt instellen voor bedrijfsgegevens in een bepaalde app. Het is raadzaam om te bekijken hoe [beleid voor app-beveiliging](app-protection-policy.md) werkt. Hieronder ziet u een voorbeeld van het vastleggen van de bestaande apps en welke beveiliging er nodig is.

| **App** | **Doel** | **Platformen** | **Use case** | **Beleid voor app-beveiliging** |
|:---:|:---:|:---:|:---:|:---:|
| Outlook Mobile  | Beschikbaar | iOS | Bedrijfseigendom - leidinggevenden | Apparaat kan niet jailbroken zijn, bestanden versleutelen |                                                         
| Word | Beschikbaar | iOS, Android - Samsung Knox, niet-Knox, Windows 10 Mobile | Bedrijfseigendom, BYOD | Apparaat kan niet jailbroken zijn, bestanden versleutelen |                                                         


U kunt [een sjabloon uit de bovenstaande tabel downloaden](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) om de behoeften van uw beleid voor app-beveiliging vast te stellen.
#### <a name="compliance-policies"></a>Nalevingsbeleid

Nalevingsbeleid bepaalt of een apparaat aan bepaalde vereisten voldoet. Intune hanteert nalevingsbeleid om te bepalen of een apparaat als compatibel of niet-compatibel wordt beschouwd. De nalevingsstatus kan vervolgens worden gebruikt om de toegang tot bedrijfsbronnen te beperken of toe te staan. Als voorwaardelijke toegang is vereist, is het raadzaam een [nalevingsbeleid voor apparaten](device-compliance.md) te ontwerpen.

Raadpleeg de vereisten en gebruiksvoorbeelden om te bepalen hoeveel nalevingsbeleidsregels voor apparaten u nodig hebt en op welke gebruikersgroepen die van toepassing zijn. Daarnaast moet u besluiten hoe lang een apparaat offline kan zijn zonder in te checken, voordat het als niet-compatibel wordt beschouwd.

Hieronder ziet u een voorbeeld van het ontwerpen van nalevingsbeleid:

| **Naam van beleid** | **Apparaatplatform** | **Instellingen** | **Doelgroep** |   
|:---:|:---:|:---:|:---:|
| Nalevingsbeleid | iOS, Android - Samsung Knox, niet-Knox, Windows 10 Mobile | PIN - vereist, kan niet jailbroken zijn | Bedrijfseigendom, BYOD |


U kunt [een sjabloon uit de bovenstaande tabel downloaden](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) om de behoeften van uw nalevingsbeleid vast te stellen.
#### <a name="conditional-access-policies"></a>Beleid voor voorwaardelijke toegang

Voorwaardelijke toegang wordt gebruikt om alleen compatibele apparaten toegang tot e-mail en andere bedrijfsbronnen te verlenen. Intune werkt met Enterprise Mobility + Security (EMS) om toegang tot bedrijfsbronnen te bewaken. U moet besluiten of voorwaardelijke toegang is vereist en wat er moet worden beveiligd. Meer informatie over [voorwaardelijke toegang](conditional-access.md).

Besluit met het oog op onlinetoegang voor welke platformen en gebruikersgroepen beleidsregels voor voorwaardelijke toegang gelden. Daarnaast moet u bepalen of de service-naar-service-connector van Intune moet worden geïnstalleerd of geconfigureerd voor Exchange Online of Exchange On-premises. Meer informatie over het installeren en configureren van de service-naar-service-connectors van Intune: <!---these links are correct--->

-   [Exchange Online](exchange-service-connector-configure.md)

-   [Exchange On-premises](exchange-connector-install.md)

Hieronder ziet u een voorbeeld van het vastleggen van beleidsregels voor voorwaardelijke toegang:

| **Service** | **Platformen voor moderne verificatie** | **Basisverificatie** | **Use cases** |   
|:---:|:---:|:---:|:---:|
| Exchange Online | iOS, Android | Niet-compatibele apparaten blokkeren op platforms die worden ondersteund door Intune | Bedrijfseigendom, BYOD |
| SharePoint Online | iOS, Android |  | Bedrijfseigendom, BYOD |

U kunt [een sjabloon uit de bovenstaande tabel downloaden](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) om de behoeften van uw beleid voor voorwaardelijke toegang vast te stellen.

## <a name="next-steps"></a>Volgende stappen

De volgende sectie bevat richtlijnen voor het [Intune-implementatieproces](planning-guide-onboarding.md).
