---
title: Een Intune-ontwerp maken | Microsoft Docs
description: Dit artikel helpt u bij het maken van een ontwerp voor een Microsoft Intune-ontwerp en -implementatie die uitsluitend voor de cloud zijn bestemd.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a8e38e29-f5e3-4a71-a170-d3b1a06e37c6
ms.reviewer: jeffbu, cgerth
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fa33bd3833f7f7198eed3f4f486c27bae3ba47d7
ms.openlocfilehash: 5f05aa4a27be14a05663aa9de82af63291699403


---

# <a name="create-an-intune-design"></a>Een Intune-ontwerp maken

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

De sectie van de handleiding moet worden gebruikt in combinatie met andere onderwerpen in sectie 2. Dit ontwerp wordt gebaseerd op de informatie die u verzamelt en besluiten die u neemt bij het voltooien van de voorgaande secties in deze handleiding. In deze ontwerpsectie gaan we uit van een zelfstandige Intune-versie, die bestaat uit een Microsoft-cloudservice die zich in de cloud bevindt.

Hoewel er een minimum aan vereisten voor de lokale infrastructuur is, wordt het wel aanbevolen om te werken aan een ontwerpplan om ervoor te zorgen dat u de juiste beheeroplossing voor mobiele apparaten hebt die aansluit bij uw doelen, doelstellingen en vereisten.

Bovendien is het gebruikelijk dat er tijdens de implementatie- en testfases ontwerpwijzigingen nodig zijn. Vergeet dan ook niet om dergelijke wijzigingen en de gedachte achter te documenteren, wanneer die situatie zich voordoet. De volgende gebieden komen aan bod:

-   De huidige omgeving

-   Intune-implementatieopties

-   Identiteitsvereisten voor externe afhankelijkheden

-   Overwegingen met betrekking tot het apparaatplatform

-   Vereisten waaraan moet worden voldaan  

Laten we elk van deze gebieden eens nader bekijken. 

## <a name="record-your-environment"></a>Uw omgeving vastleggen

De eerste stap voordat u een ontwerp kunt maken, is het vastleggen van uw huidige omgeving. De huidige omgeving kan van invloed zijn op ontwerpbeslissingen en moet daarom worden gedocumenteerd als referentie bij het maken van andere Intune-ontwerpbeslissingen. Hieronder vindt u enkele voorbeelden van hoe u de huidige omgeving kunt vastleggen:

-   **Identiteit in de cloud**

    -   Gebruikt u DirSync of Azure Active Directory (AAD) Connect?

    -   Is uw omgeving federatief?

    -   Is Multi-Factor Authentication ingeschakeld?

-   **E-mailomgeving**

    -   Wordt Exchange gebruikt en wordt dat on-premises of in de cloud toegepast?

    -   Zit u midden in een project en wilt u Exchange naar de cloud migreren?

-   **Huidige MDM-oplossing**

    -   Gebruikt u momenteel andere MDM-oplossingen?

    -   Welke MDM-oplossingen gebruikt u voor zakelijke scenario's en BOYD-scenario's?

    -   Van welke mogelijkheden maakt u gebruik (bijvoorbeeld apparaatinstellingen voor apps, Wi-Fi-configuraties, enzovoort)?

    -   Welke apparaatplatformen worden ondersteund?

    -   Welke groepen en hoeveel gebruikers werken er met de MDM-oplossing?

-   **Certificaatoplossing**

    -   Hebt u een certificaatoplossing geïmplementeerd?

    -   Wat voor soort certificaten gebruikt u?

-   **Beheer van systemen**

    -   Hoe beheert u uw pc- en serveromgeving?

    -   Wordt System Center Configuration Manager gebruikt? Werkt u met een platform voor systeembeheer van derden?

-   **VPN-oplossing**

    -   Wat is uw VPN-oplossing?

    -   Wordt deze gebruikt voor zowel zakelijke als BYOD-scenario's?

Wanneer u de huidige MDM-omgeving vastlegt, moet u niet vergeten een notitie te maken van alle projecten of eventuele andere in gebruik zijnde plannen die wijzigingen zouden kunnen aanbrengen in uw omgeving. Hieronder ziet u een voorbeeld van een manier om de huidige omgeving vast te leggen als hulp bij het maken van uw Intune-ontwerp:

| **Gebied waarvoor de oplossing geldt** | **Huidige omgeving** | **Opmerkingen** |
|:---:|:---:|:---:|
| **Identiteit** | Azure AD, Azure AD Connect, niet federatief, geen MFA | Project aanwezig om MFA tegen het eind van het jaar in te schakelen |                 
| **E-mailomgeving** | Exchange On-premises, Exchange Online | Momenteel vindt migratie plaats van Exchange On-premises naar Exchange Online. 75% van postvakken gemigreerd. De laatste 25% wordt gemigreerd voordat Intune-pilot begint. |                
| **SharePoint** | SharePoint On-premises | Er zijn geen plannen om over te stappen op SharePoint Online |  
| **Huidig MDM** | Exchange ActiveSync |  |
| **Certificaatoplossing** | Microsoft Server 2012 R2, AD Certificate Services | Gebruik alleen PKI voor websiteservers |
| **Systeembeheer** | System Center Configuration Manager CB 1606 | Wil een hybride oplossing met Intune onderzoeken |
| **VPN-oplossing** | Cisco AnyConnect |  |

## <a name="choose-an-intune-deployment-option"></a>Kies een optie voor Intune-implementatie

Intune biedt twee opties voor implementatie: zelfstandig en hybride. U dient te beslissen welke het meest geschikt is voor uw zakelijke vereisten. Zelfstandig verwijst naar de Intune-service die wordt uitgevoerd in de cloud, hybride verwijst naar de integratie van Intune met System Center Configuration Manager.

- Meer informatie over [de keuze tussen de zelfstandige en hybride optie van Microsoft Intune voor het beheren van mobiele apparaten met System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management)

## <a name="intune-tenant-location"></a>Locatie van Intune-tenant

Als uw organisatie wereldwijd opereert, moet u ook een beslissing nemen over de juiste locatie van uw tenant wanneer u zich abonneert op de service. Het land wordt gedefinieerd wanneer u zich voor het eerst aanmeldt voor een Intune-abonnement en maak toewijzingen voor regio's wereldwijd die hieronder worden gedefinieerd:

-   Noord-Amerika

-   Europa, Midden-Oosten en Afrika

-   Azië en Pacific

>[!IMPORTANT] 
> Het is niet mogelijk het land of de tenantlocatie naderhand te wijzigen.

## <a name="external-dependencies"></a>Externe afhankelijkheden

Externe afhankelijkheden zijn services en producten die geen deel uitmaken van Intune, maar wel een vereiste van Intune zijn of kunnen worden geïntegreerd met Intune. Het is belangrijk om vereisten voor alle externe afhankelijkheden vast te stellen en hoe deze zullen worden geconfigureerd. Enkele voorbeelden van algemene externe afhankelijkheden zijn hieronder te vinden.

-   Identiteit

-   Gebruikers- en apparaatgroepen

-   PKI

Deze algemene externe afhankelijkheden worden hieronder nader onderzocht

### <a name="identity"></a>Identiteit 

Identiteit is de manier waarop we de gebruikers identificeren die tot uw organisatie behoren en een apparaat registreren. Intune vereist Azure Active Directory (Azure AD) als provider van gebruiker-id's. Als u deze service al gebruikt, kunt u gebruikmaken van uw bestaande identiteit in de cloud. Azure AD Connect is bovendien het aanbevolen hulpmiddel om uw lokale gebruikers-id's te synchroniseren met Microsoft-cloudservices. Als uw organisatie al met Office 365 werkt, is het belangrijk dat Intune van dezelfde Azure Active Directory-omgeving gebruikmaakt.

U vindt hieronder meer informatie over de id-vereisten van Intune.

-   Meer informatie over [id-vereisten](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).

-   Meer informatie over [adreslijstsynchronisatie](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).

-   Meer informatie over [vereisten voor Multi-Factor Authentication](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).

### <a name="user-and-device-groups"></a>Gebruikers- en apparaatgroepen

Gebruikers- en apparaatgroepen bepalen het doel van een implementatie. Dat kan bijvoorbeeld betrekking hebben op implementatiedoelen voor beleidsregels, toepassingen en profielen. Intune biedt alleen ondersteuning voor gebruikers- en apparaatgroepen. U moet bepalen welke gebruikers- en apparaatgroepen vereist zijn. Het is raadzaam dat alle groepen worden gemaakt in de on-premises Active Directory en vervolgens worden gesynchroniseerd met Azure Active Directory. Hieronder vindt u meer informatie over het plannen en maken van gebruikers- en apparaatgroepen.

-   Meer informatie over [het plannen van gebruikers- en apparaatgroepen](https://docs.microsoft.com/intune/deploy-use/plan-your-user-and-device-groups).

-   Informatie over [het maken van gebruikers- en apparaatgroepen](https://docs.microsoft.com/en-us/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

### <a name="public-key-infrastructure-pki"></a>Public Key Infrastructure (PKI)

Public Key Infrastructure verstrekt certificaten aan apparaten of gebruikers voor een veilige verificatie van services. Intune biedt ondersteuning voor een Microsoft PKI-infrastructuur. Apparaat- en gebruikerscertificaten kunnen worden uitgegeven voor een mobiel apparaat om te voldoen aan verificatievereisten op basis van certificaten. Voorafgaand aan de implementatie van certificaten moet u vaststellen of er daadwerkelijk certificaten nodig zijn, of de netwerkinfrastructuur verificatie op basis van certificaten kan ondersteunen en of er momenteel in de bestaande omgeving certificaten worden gebruikt.

Als u van plan bent voor Intune certificaten te gebruiken met VPN-, Wi-Fi- of e-mailprofielen, moet u controleren of er een ondersteunde [PKI-infrastructuur](https://docs.microsoft.com/intune/deploy-use/secure-resource-access-with-certificate-profiles) is, die geschikt is om certificaatprofielen te maken en implementeren.

Als er SCEP-certificaten worden uitgegeven, moet u bovendien bepalen welke server fungeert als host voor de functie Network Device Enrollment Service (NDES) en hoe de communicatie wordt uitgevoerd.

Meer informatie over het configureren van certificaten in Intune:

-   [De certificaatinfrastructuur voor SCEP configureren](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-scep).

-   [De certificaatinfrastructuur voor PFX configureren](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-pfx).

-   [Intune-certificaatprofielen configureren](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles).

-   [Toegangsbeleid voor resources configureren](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

## <a name="device-platform-considerations"></a>Overwegingen met betrekking tot het apparaatplatform

Neem uw apparaten eens onder de loep om te begrijpen hoe ze precies werken.

-   Ondersteunde apparaatplatformen vaststellen

-   Apparaten

-   Apparaateigendom

-   Bulkinschrijving

Laten we deze gebieden eens nader bekijken.

### <a name="determine-supported-device-platforms"></a>Ondersteunde apparaatplatformen vaststellen

U moet tijdens het maken van uw ontwerp weten welke apparaten in de omgeving worden opgenomen en controleren of ze al dan niet worden ondersteund door Intune. Intune biedt ondersteuning voor iOS-, Android- en Windows-platforms.

-   Meer informatie over [door Intune ondersteunde apparaten](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers).

### <a name="devices"></a>Apparaten

Intune beheert mobiele apparaten ter beveiliging van zakelijke gegevens en om ervoor te zorgen dat eindgebruikers vanaf meer locaties kunnen werken. Omdat Intune meerdere apparaatplatformen ondersteunt, is het raadzaam om de apparaten en OS-platformen vast te leggen die worden ondersteund in het ontwerp van uw organisatie. Dit wordt uitgebreid voor de apparaten en platformen die zijn gemaakt in sectie (gebruik case-vereisten).

Het is ook raadzaam om de versies te kennen bij verwijzingen naar de lijst tijdens het controleren op apparaatmogelijkheden per OS-platform en -versie. Hier volgt een voorbeeld:

| **Apparaatplatform** | **Besturingssysteemversies** |
|:---:|:---:|
| iOS - iPhone | 9.0+ |                
| iOS - iPad | 8.0+ |               
| Android – Samsung Knox Standard | 4.0+ |
| Windows 10-tablet | 10+ |

### <a name="device-ownership"></a>Apparaateigendom

Intune ondersteunt zowel apparaten in bedrijfseigendom als BYOD-apparaten. Een apparaat wordt beschouwd als bedrijfseigendom als dat is geregistreerd via een apparaatinschrijvingsbeheerder of apparaatinschrijvingsprogramma. Een apparaat kan bijvoorbeeld worden geregistreerd via Apple DEP, worden gemarkeerd als bedrijfseigendom en worden geplaatst in een apparaatgroep die specifieke beleidsregels en apps van het bedrijf ontvangt.

Raadpleeg [Sectie 3: use-casescenariovereisten bepalen](section-3-determine-use-case-requirements.md) voor meer informatie over gebruiksvoorbeelden van apparaten in bedrijfseigendom en BYOD-apparaten.

### <a name="bulk-enrollment"></a>Bulkregistratie

Er zijn meerdere registratieopties beschikbaar voor het registreren van een apparaat in Intune naast de handmatige registratie via de bedrijfsportal. Bulkregistratie kan op verschillende manieren worden uitgevoerd, afhankelijk van het platform. Als bulkregistratie is vereist, bepaalt u eerst de juiste methode voor bulkregistratie die u vervolgens opneemt in uw ontwerp. Meer informatie over verschillende methoden van bulkregistratie vindt u hieronder.

-   Meer informatie over [bulkregistratie](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune).

## <a name="feature-requirements"></a>Functievereisten

In deze secties worden de volgende functies en mogelijkheden beschreven die zijn afgestemd op uw use-casescenariovereisten:

-   Beleidsregels voor voorwaarden

-   Configuratiebeleid

-   Resourceprofielen

-   Apps

-   Nalevingsbeleid

-   Voorwaardelijke toegang

Laten we elk van deze gebieden eens nader bekijken.

### <a name="terms-and-conditions-policies"></a>Beleidsregels voor voorwaarden

Voorwaarden kunnen worden gebruikt om beleidsregels of voorwaarden uit te leggen die een eindgebruiker voorafgaand aan de registratie moet accepteren. Intune ondersteunt de mogelijkheid om meerdere beleidsregels voor voorwaarden toe te voegen aan en te implementeren voor gebruikersgroepen. U moet zelf bepalen of er beleidsregels voor voorwaarden nodig zijn. Als dat inderdaad het geval is, wie is er dan verantwoordelijk voor het verspreiden van deze informatie in de organisatie.

-   Informatie over [beleidsregels voor voorwaarden maken](https://docs.microsoft.com/intune/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune) in Intune. Hieronder ziet u een voorbeeld van het vastleggen van de beleidsregels voor voorwaarden.

| **Naam van de voorwaarden** | **Use case** | **Doelgroep** |
|:---:|:---:|:---:|
| Bedrijfsvoorwaarden | Zakelijk | Zakelijke gebruikers |                 
| Voorwaarden BYOD | BYOD | BYOD-gebruikers |                

### <a name="configuration-policies"></a>Configuratiebeleid

Configuratiebeleid wordt gebruikt om beveiligingsinstellingen en -functies op een apparaat te beheren. Raadpleeg bij het ontwerpen van uw configuratiebeleid de sectie met de casevereisten om de voor Intune-apparaten vereiste configuraties te bepalen. Leg de gebruikte instellingen vast en hoe deze moeten worden geconfigureerd. Leg ook vast op welke gebruikers- of apparaatgroepen ze van toepassing zijn.

U moet ten minste één configuratiebeleid per platform maken. U kunt desgewenst meer dan één configuratiebeleid per platform maken. Hieronder ziet u een voorbeeld van het ontwerpen van de vier verschillende configuratiebeleidsregels voor verschillende platformen en use-casescenario's.

| **Naam van beleid** | **Apparaatplatform** | **Instellingen** | **Doelgroep** |   
|:---:|:---:|:---:|:---:|
| Bedrijfseigendom - iOS | iOS | Pincode is vereist, lengte: 6, cloudback-up beperken | Bedrijfsapparaten |                                                           
| Bedrijfseigendom - Android | Android | Pincode is vereist, lengte: 6, cloudback-up beperken | Bedrijfsapparaten |                                                           
| BYOD - iOS  | iOS | Pincode is vereist, lengte: 4 | BYOD-apparaten | 
| BYOD - Android  | Android | Pincode is vereist, lengte: 4 | BYOD-apparaten |

### <a name="profiles"></a>Profielen

Profielen worden gebruikt om de eindgebruiker verbinding te laten maken met bedrijfsgegevens. Intune ondersteunt veel typen profielen. Raadpleeg de gebruiksvoorbeelden en vereisten om te bepalen wanneer de [profielen](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune) worden geconfigureerd. Alle apparaatprofielen worden gecategoriseerd per platformtype en moeten worden opgenomen in de ontwerpdocumentatie.

-   Certificaatprofielen

-   Wi-Fi-profiel

-   VPN-profiel

-   E-mailprofiel

Laten we elk profieltype eens nader onderzoeken.

##### <a name="certificate-profiles"></a>Certificaatprofielen

Met behulp van certificaatprofielen kan Intune een certificaat uitgeven aan een gebruiker of apparaat. Intune ondersteunt het volgende:

-   Simple Certificate Enrollment Protocol (SCEP)

-   Vertrouwd basis-CA-certificaat

-   PFX-certificaat.

Het verdient aanbeveling om vast te leggen welke gebruikersgroep een certificaat nodig heeft, hoeveel certificaatprofielen er nodig zijn en voor welke gebruikersgroepen ze moeten worden geïmplementeerd.

>[!NOTE] 
> Houd er rekening mee dat het vertrouwde basiscertificaat vereist is voor het SCEP-certificaat. Zorg er daarom voor dat alle gebruikers met het SCEP-certificaat ook een vertrouwd basiscertificaat krijgen toegewezen. Als er SCEP-certificaten nodig zijn, ontwerpt u de daarvoor bestemde SCEP-certificaatsjablonen en legt u deze vast.

Hier volgt een voorbeeld van hoe u de certificaten tijdens het ontwerpen kunt vastleggen:

| **Type** | **Profielnaam** | **Apparaatplatform** | **Use cases** |   
|:---:|:---:|:---:|:---:|
| Basis-CA | Bedrijfseigendom, Basis-CA | Android, iOS, Windows Mobile | Bedrijfseigendom, BYOD  |                                                           
| SCEP | Gebruikerscertificaat | Android, iOS, Windows Mobile | Bedrijfseigendom, BYOD |                                                           

##### <a name="wi-fi-profile"></a>Wi-Fi-profiel

Wi-Fi-profielen worden gebruikt om een mobiel apparaat automatisch te verbinden met een draadloos netwerk. Intune biedt ondersteuning voor het implementeren van Wi-Fi-profielen op alle ondersteunde platformen.

-   Meer informatie over [hoe Intune Wi-Fi-profielen ondersteunt.](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune)

Hieronder ziet u een voorbeeld van een ontwerp voor een Wi-Fi-profiel:

| **Type** | **Profielnaam** | **Apparaatplatform** | **Use cases** |   
|:---:|:---:|:---:|:---:|
| Wi-Fi | Wi-Fi-profiel Azië | Android | Bedrijfseigendom, BYOD regio Azië|                                                           
| Wi-Fi | Wi-Fi-profiel Noord-Amerika | Android, iOS, Windows 10 Mobile | Bedrijfseigendom, BYOD regio Noord-Amerika |                                                           

##### <a name="vpn-profile"></a>VPN-profiel

Met VPN-profielen kunnen gebruikers veilig toegang krijgen tot uw netwerk vanaf externe locaties. Intune ondersteunt VPN-profielen van systeemeigen mobiele VPN-verbindingen en externe leveranciers.

-   Meer informatie over [VPN-profielen en leveranciers die worden ondersteund door Intune](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune).

Hieronder ziet u een voorbeeld van het vastleggen van het ontwerp van een VPN-profiel.

| **Type** | **Profielnaam** | **Apparaatplatform** | **Use cases** |   
|:---:|:---:|:---:|:---:|
| VPN | VPN Cisco, alle verbindingsprofielen | Android, iOS, Windows 10 Mobile | Bedrijfseigendom, BYOD Noord-Amerika en Duitsland|                                                           
| VPN | Pulse Secure | Android | Bedrijfseigendom, BYOD regio Azië |                                                           

##### <a name="email-profile"></a>E-mailprofiel

Met e-mailprofielen kan een e-mailclient automatisch worden ingesteld met verbindingsgegevens en e-mailconfiguratie. Intune ondersteunt e-mailprofielen op sommige apparaten.

-   Meer informatie over [e-mailprofielen](https://docs.microsoft.com/en-us/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) en welke platformen worden ondersteund.

Hieronder ziet u een voorbeeld van het vastleggen van het ontwerp van e-mailprofielen:

| **Type** | **Profielnaam** | **Apparaatplatform** | **Use cases** |   
|:---:|:---:|:---:|:---:|
| E-mailprofiel | E-mailprofiel voor iOS | iOS | Bedrijfseigendom - Informatiemedewerker BYOD |                                                           
| E-mailprofiel | E-mailprofiel Android Knox | Android Knox | BYOD |

### <a name="apps"></a>Apps

Intune ondersteunt op verschillende manieren het leveren van apps aan gebruikers of apparaten. Het type app kan bestaan uit apps voor software-installatie, apps uit een openbare app-store, externe koppelingen of beheerde iOS-apps. Naast de afzonderlijke app-implementaties kunnen in volumes aangeschafte apps worden beheerd en geïmplementeerd via de volume-aankoopprogramma's voor iOS en Windows. Hieronder vindt u meer informatie over hoe apps en de volume-aankoopprogramma's worden ondersteund in Intune.

-   Meer informatie over [typen apps](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune)

-   Meer informatie over [het iOS-volume-aankoopprogramma voor bedrijven](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune).

-   Meer informatie over [Windows Store voor Bedrijven](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune).

#### <a name="app-type-requirements"></a>Vereisten voor app-typen

Aangezien apps kunnen worden geïmplementeerd voor gebruikers en apparaten, is het raadzaam om te beslissen welke apps door Intune worden beheerd. Probeer de volgende vragen te beantwoorden tijdens het samenstellen van de lijst:

-   Is voor de apps integratie met cloudservices vereist?

-   Zullen alle apps beschikbaar zijn voor BYOD-gebruikers?

-   Welke implementatieopties zijn er voor deze apps beschikbaar?

-   Moet uw bedrijf zijn partners toegang verlenen tot gegevens van SaaS-apps (Software as a Service)?

-   Hebben de apps internettoegang vanaf de apparaten van de gebruikers nodig?

-   Zijn de apps openbaar beschikbaar in een app-store of zijn het aangepaste Line-Of-Business-apps?


>[!TIP] 
> Bekijk de [verschillende typen apps die ondersteuning bieden voor Intune](https://docs.microsoft.com/intune/deploy-use/add-apps).

#### <a name="app-protection-policies"></a>Beleid voor app-beveiliging

Met beleid voor app-beveiliging kan het verlies van gegevens tot een minimum worden beperkt door te definiëren hoe de app de bedrijfsgegevens beheert. Intune ondersteunt beleid voor app-beveiliging voor elke app die functioneert met beheer van mobiele apps. Bij het ontwerpen van het beleid voor app-beveiliging moet u bepalen welke beperkingen u instelt voor bedrijfsgegevens in een bepaalde app. Het is raadzaam om te bekijken hoe [beleid voor app-beveiliging](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) werkt. Hieronder ziet u een voorbeeld van het vastleggen van de bestaande apps en welke beveiliging er nodig is.

| **App** | **Doel** | **Platformen** | **Use case** | **Beleid voor app-beveiliging** |
|:---:|:---:|:---:|:---:|:---:|
| Outlook Mobile  | Beschikbaar | iOS | Bedrijfseigendom - leidinggevenden | Apparaat kan niet jailbroken zijn, bestanden versleutelen |                                                         
| Word | Beschikbaar | iOS, Android - Samsung Knox, niet-Knox, Windows 10 Mobile | Bedrijfseigendom, BYOD | Apparaat kan niet jailbroken zijn, bestanden versleutelen |                                                         

#### <a name="compliance-policies"></a>Nalevingsbeleid

Nalevingsbeleid bepaalt of een apparaat aan bepaalde vereisten voldoet. Intune hanteert nalevingsbeleid om te bepalen of een apparaat als compatibel of niet-compatibel wordt beschouwd. De nalevingsstatus kan vervolgens worden gebruikt om de toegang tot bedrijfsbronnen te beperken. Als voorwaardelijke toegang is vereist, is het raadzaam om een [nalevingsbeleid voor apparaten](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) te ontwerpen. Raadpleeg de vereisten en gebruiksvoorbeelden om te bepalen hoeveel nalevingsbeleidsregels voor apparaten er nodig zijn en op welke gebruikersgroepen die van toepassing zijn. Daarnaast moet u bepalen hoe lang een apparaat offline kan zijn zonder in te checken voordat het als niet-compatibel wordt beschouwd.

Hieronder ziet u een voorbeeld van het ontwerpen van nalevingsbeleid:

| **Naam van beleid** | **Apparaatplatform** | **Instellingen** | **Doelgroep** |   
|:---:|:---:|:---:|:---:|
| Nalevingsbeleid | iOS, Android - Samsung Knox, niet-Knox, Windows 10 Mobile | PIN - vereist, kan niet jailbroken zijn | Bedrijfseigendom, BYOD |

#### <a name="conditional-access-policies"></a>Beleid voor voorwaardelijke toegang

Voorwaardelijke toegang wordt gebruikt om alleen compatibele apparaten toegang tot bedrijfsbronnen te verlenen. Intune werkt met de volledige Enterprise Mobility + Security (EMS) om toegang tot bedrijfsbronnen te beheren. U moet vaststellen of voorwaardelijke toegang vereist is en wat er moet worden beveiligd.

-   Meer informatie over [voorwaardelijke toegang](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

Bepaal met het oog op online toegang voor welke platformen en gebruikersgroepen beleidsregels voor voorwaardelijke toegang gelden.

Daarnaast moet u bepalen of de service-naar-service-connector van Intune moet worden geïnstalleerd/geconfigureerd voor Exchange Online of Exchange On-premises.

Meer informatie over het installeren en configureren van de service-naar-service-connectors van Intune:

-   [Exchange Online](https://docs.microsoft.com/intune/deploy-use/intune-service-to-service-exchange-connector)

-   [Exchange On-premises](https://docs.microsoft.com/intune/deploy-use/intune-on-premises-exchange-connector)

Hieronder ziet u een voorbeeld van het vastleggen van beleidsregels voor voorwaardelijke toegang:

| **Service** | **Platformen voor moderne verificatie** | **Basisverificatie** | **Use cases** |   
|:---:|:---:|:---:|:---:|
| Exchange Online | iOS, Android | Niet-compatibele apparaten blokkeren op platforms die worden ondersteund door Intune | Bedrijfseigendom, BYOD |
| SharePoint Online | iOS, Android |  | Bedrijfseigendom, BYOD |

## <a name="next-section"></a>Volgende sectie

De volgende sectie bevat richtlijnen voor het [Intune-implementatieproces](section-8-onboarding-process.md).



<!--HONumber=Dec16_HO5-->


