---
title: VPN-verbindingen | Microsoft Docs
description: VPN-profielen gebruiken om VPN-instellingen te implementeren voor gebruikers en apparaten in uw organisatie.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: abc57093-7351-408f-9f41-a30877f96f73
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 0154e3bfeac0457de57257045e3e7ce833325bce
ms.openlocfilehash: a462bcfa107bf1a37ea4e84bc3d88d0dd81f9fc8


---

# <a name="vpn-connections-in-microsoft-intune"></a>VPN-verbindingen in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Met virtuele particuliere netwerken (VPN's) geeft u uw gebruikers veilige externe toegang tot uw bedrijfsnetwerk. Apparaten gebruiken een *VPN-verbindingsprofiel* om een verbinding met de VPN-server op te zetten. Gebruik *VPN-profielen* in Microsoft Intune om VPN-instellingen te implementeren voor gebruikers en apparaten in uw organisatie, zodat deze gemakkelijk en veilig verbinding met het netwerk kunnen maken.

U wilt bijvoorbeeld alle iOS-apparaten voorzien van de instellingen die vereist zijn om verbinding te maken met een bestandsshare op het bedrijfsnetwerk. U maakt een VPN-profiel met de instellingen die nodig zijn om verbinding te maken met het bedrijfsnetwerk en vervolgens implementeert u dit profiel voor alle gebruikers met iOS-apparaten. De gebruikers zien de VPN-verbinding in de lijst met beschikbare netwerken en kunnen moeiteloos verbinding maken.

U kunt de volgende typen apparaten configureren door gebruik te maken van VPN-profielen:

* Apparaten met Android 4 en hoger
* Apparaten met Android for Work
* Apparaten met iOS 8.0 en hoger
* Apparaten met Mac OS X 10.9 en hoger
* Geregistreerde apparaten met Windows 8.1 en hoger
* Apparaten met Windows Phone 8.1 en hoger
* Apparaten waarop Windows 10 Desktop en Mobile worden uitgevoerd

De configuratieopties voor het VPN-profiel zijn afhankelijk van het apparaattype dat u selecteert.

## <a name="vpn-connection-types"></a>VPN-verbindingstypen

Intune ondersteunt het maken van VPN-profielen die gebruikmaken van de volgende verbindingstypen:


Type verbinding |iOS en Mac OS X  |Android en Android for Work|Windows 8.1|Windows RT 8.1|Windows Phone 8,1|Windows 10 Desktop en Mobile |
----------------|------------------|-------|-----------|----------|--------------|-----------------|----------------------|
Cisco AnyConnect|Ja |Ja   |Nee    |Nee  |Nee    | Ja (OMA-URI, alleen Mobile)|     
Cisco (IPsec)|Yes |Ja   |Nee  |Nee  |Nee | Nee|
Citrix|Yes |Ja (alleen Android)   |Nee  |Nee  |Nee | Nee|
Pulse Secure|Ja  |Ja |Ja   |Ja  |Ja| Ja|        
F5 Edge Client|Ja |Ja |Ja |Ja  |   Ja |  Ja|   
Dell SonicWALL Mobile Connect|Ja |Ja |Ja |Ja |Ja |Ja|         
CheckPoint Mobile VPN|Ja |Ja |Ja |Ja|Ja|Ja|
Microsoft SSL (SSTP)|Nee |Nee |Nee |Nee|Nee|VPNv1 OMA-URI*|
Microsoft Automatic|Nee |Nee |Nee |Nee|Ja (OMA-URI)|Ja|
IKEv2|Aangepast iOS-profiel|Nee |Nee |Nee|Ja (OMA-URI)|Ja|
PPTP|Aangepast iOS-profiel|Nee |Nee |Nee|Nee|Ja|
L2TP|Aangepast iOS-profiel|Nee |Nee |Nee|Ja (OMA-URI)|Ja|

\* Zonder aanvullende instellingen die anderszins beschikbaar voor zijn voor Windows 10.

> [!IMPORTANT]
> Voordat u VPN-profielen die op een apparaat zijn geïmplementeerd kunt gebruiken, moet u de betreffende VPN-app voor het profiel installeren. U kunt de informatie in het onderwerp [Apps in Microsoft Intune implementeren](deploy-apps-in-microsoft-intune.md) gebruiken bij het implementeren van de betreffende app met behulp van Intune.  

 Zie [Custom configurations for VPN profiles](create-custom-vpn-profiles.md) (Aangepaste configuraties voor VPN-profielen) voor meer informatie over het maken van aangepaste VPN-profielen met behulp van URI-instellingen.     

## <a name="methods-of-securing-vpn-profiles"></a>Methoden voor het beveiligen van VPN-profielen

Voor VPN-profielen kan een aantal verschillende verbindingstypen en -protocollen van verschillende fabrikanten worden gebruikt. Deze verbindingen zijn doorgaans beveiligd met een van de volgende twee methoden.

### <a name="certificates"></a>Certificaten

Wanneer u het VPN-profiel maakt, kiest u een SCEP- of PFX-certificaatprofiel dat u eerder hebt gemaakt in Intune. Dit wordt het identiteitscertificaat genoemd. Het wordt gebruikt voor verificatie aan de hand van een vertrouwd-certificaatprofiel (*basiscertificaat*) dat u hebt gemaakt om te bepalen of het apparaat van de gebruiker verbinding mag maken. Het vertrouwde certificaat wordt geïmplementeerd op de computer die de VPN-verbinding verifieert, meestal is dat de VPN-server.

Zie [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Toegang tot beveiligde bronnen met certificaatprofielen) voor meer informatie over het gebruiken en maken van certificaatprofielen in Intune.

### <a name="user-name-and-password"></a>Gebruikersnaam en wachtwoord

De gebruiker wordt geverifieerd op de VPN-server door een gebruikersnaam en wachtwoord op te geven.

## <a name="create-a-vpn-profile"></a>Een VPN-profiel maken

1. Ga naar de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) en kies **Beleid** > **Beleid toevoegen**.
2. Selecteer een sjabloon voor het nieuwe beleid door het uitbreiden van de relevante apparaattype en kies vervolgens het VPN-profiel voor dat apparaat:
    * **VPN-profiel (Android 4 en hoger)**
    * **VPN-profiel (Android for Work)**
    * **VPN-profiel (iOS 8.0 en hoger)**
    * **VPN-profiel (Mac OS X 10.9 en hoger)**
    * **VPN-profiel (Windows 8.1 en hoger)**
    * **VPN-profiel (Windows Phone 8.1 en hoger)**
    * **VPN-profiel (Windows 10 Desktop en Mobile en hoger)**

 U kunt alleen een aangepast beleid voor een VPN-profiel maken en implementeren. Aanbevolen instellingen zijn niet beschikbaar.

> [!Note]
> Met een VPN-profiel voor Android for Work-apparaten kan alleen een VPN-verbinding tot stand worden gebracht voor apps die zijn geïnstalleerd in het werkprofiel van het apparaat.
>
> Sommige VPN-verbindingstypen ondersteunen per-app VPN voor Android for Work-apparaten en ondersteunen het inschakelen van per-app VPN op apps die worden gedistribueerd via Intune.  

3. Met behulp van de volgende tabel kunt u de instellingen voor het VPN-profiel configureren:

Naam van de instelling  |Meer informatie  
---------|---------
**Naam**     |Geef een unieke naam voor het VPN-profiel op om dit te herkennen in de Intune-console.         
**Beschrijving**     |Geef een beschrijving op die een overzicht geeft van het VPN-profiel en overige relevante informatie die u helpt bij het zoeken.         
**Naam van VPN-verbinding (weergegeven voor gebruikers)**     |Geef een naam voor het VPN-profiel. Dit is de naam die gebruikers te zien krijgen in de lijst met beschikbare VPN-verbindingen op hun apparaten.         
**Type verbinding**     |  Selecteer een van de volgende verbindingstypen voor gebruik in het VPN-profiel: **Cisco AnyConnect** (niet beschikbaar voor Windows 8.1 of Windows Phone 8.1), **Pulse Secure**, **Citrix**, **F5 Edge Client**, **Dell SonicWALL Mobile Connect**, **CheckPoint Mobile VPN**.
**Beschrijving van de VPN-server**     | Geef een beschrijving op voor de VPN-server waarmee apparaten verbinding maken. Voorbeeld: **Contoso VPN-server**. Als het verbindingstype **F5 Edge Client** is, gebruikt u het veld **Serverlijst** om een lijst met serverbeschrijvingen en IP-adressen op te geven.
**IP-adres of FQDN van server**    |Geef het IP-adres of de Fully Qualified Domain Name (FQDN) op van de VPN-server waarmee apparaten verbinding zullen maken. Voorbeelden: **192.168.1.1**, **vpn.contoso.com**.  Als het verbindingstype **F5 Edge Client** is, gebruikt u het veld **Serverlijst** om een lijst met serverbeschrijvingen en IP-adressen op te geven.         |         
**Serverlijst**     |Kies **Toevoegen** om een nieuwe VPN-server toe te voegen die moet worden gebruikt voor de VPN-verbinding. U kunt ook opgeven welke server de standaardserver voor de verbinding moet zijn. Deze optie wordt alleen weergegeven als het verbindingstype **F5 Edge Client** is.         
**Alle netwerkverkeer via de VPN-verbinding verzenden**     |Als u deze optie selecteert, wordt alle netwerkverkeer verzonden via de VPN-verbinding. Als u deze optie niet selecteert, zal de client dynamisch onderhandelen over de routes voor split tunneling wanneer verbinding wordt gemaakt met de VPN-server van derden. Alleen verbindingen met het bedrijfsnetwerk worden verzonden via een VPN-tunnel. VPN-tunneling wordt niet gebruikt wanneer u verbinding maakt met resources op internet.
**Verificatiemethode**| Selecteer de verificatiemethode die door de VPN-verbinding wordt gebruikt: **Certificaten** of **Gebruikersnaam en wachtwoord**. (**Gebruikersnaam en wachtwoord** is niet beschikbaar als het verbindingstype Cisco AnyConnect is.) De optie **Verificatiemethode** is niet beschikbaar voor Windows 8.1.
**Gebruikersreferenties onthouden bij elke aanmelding**|Selecteer deze optie om ervoor te zorgen dat de gebruikersreferenties worden onthouden zodat de gebruiker geen referenties hoeft in te voeren telkens wanneer een verbinding tot stand wordt gebracht.
**Clientcertificaat selecteren voor clientverificatie (identiteitscertificaat)**|Selecteer het SCEP-clientcertificaat dat u eerder hebt gemaakt en dat wordt gebruikt voor het verifiëren van de VPN-verbinding. Zie [Custom configurations for VPN profiles](secure-resource-access-with-certificate-profiles.md) (Toegang tot beveiligde bronnen met certificaatprofielen) voor meer informatie over het gebruik van certificaatprofielen in Intune. Deze optie wordt alleen weergegeven als **Certificaten** is geselecteerd als verificatiemethode.
**Rol**| Geef de naam op van de gebruikersrol die toegang tot deze verbinding heeft. Een gebruikersrol definieert persoonlijke instellingen en opties en schakelt bepaalde toegangsfuncties in of uit. Deze optie wordt alleen weergegeven als het verbindingstype **Pulse Secure** of **Citrix** is.
**Realm**|Geef de naam op van de verificatierealm die u wilt gebruiken. Een verificatierealm is een groepering van verificatieresources die worden gebruikt door het verbindingstype Pulse Secure of Citrix. Deze optie wordt alleen weergegeven als het verbindingstype **Pulse Secure** of **Citrix** is.
**Aanmeldingsgroep of -domein**|Geef de naam op van de aanmeldingsgroep of het aanmeldingsdomein waarmee u verbinding wilt maken. Deze optie wordt alleen weergegeven als het verbindingstype **Dell SonicWALL Mobile Connect** is.
**Vingerafdruk**|Geef een tekenreeks op (bijvoorbeeld 'Contoso-vingerafdrukcode') die wordt gebruikt om te controleren of de VPN-server kan worden vertrouwd. Een vingerafdruk kan worden verzonden naar de client zodat deze alle servers vertrouwt die dezelfde vingerafdruk presenteren wanneer er verbinding wordt gemaakt. Als het apparaat nog niet over de vingerafdruk beschikt, wordt de gebruiker gevraagd om de VPN-server waarmee deze verbinding maakt, te vertrouwen terwijl de vingerafdruk wordt weergegeven. (De gebruiker controleert de vingerafdruk handmatig en kiest **Vertrouwen** om verbinding te maken.) Deze optie wordt alleen weergegeven als het verbindingstype **CheckPoint Mobile VPN** is.
**VPN per app**|Selecteer deze optie als u deze VPN-verbinding wilt koppelen aan een iOS-app of een Max OS X-app zodat de verbinding wordt geopend wanneer de app wordt uitgevoerd. U kunt het VPN-profiel aan een app koppelen bij het implementeren van de software. Zie [Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md) (Apps implementeren in Microsoft Intune) voor meer informatie
**VPN op aanvraag**|U kunt VPN op aanvraag voor apparaten met iOS 8.0 en hoger instellen. Instructies hiervoor zijn beschikbaar in [VPN op aanvraag voor iOS-apparaten](#on-demand-vpn-for-ios-devices).
**Proxy-instellingen automatisch detecteren** (alleen voor iOS, Mac OS X, Windows 8.1 en Windows Phone 8.1)|Als de VPN-server een proxyserver voor de verbinding vereist, geeft u op of u wilt dat apparaten de verbindingsinstellingen automatisch detecteren. Raadpleeg de Windows Server-documentatie voor meer informatie.
**Automatisch configuratiescript gebruiken** (alleen voor iOS, Mac OS X, Windows 8.1 en Windows Phone 8.1)|Als uw VPN-server een proxyserver voor de verbinding vereist, geeft u op of u een automatisch configuratiescript wilt gebruiken om de instellingen te definiëren en geeft u vervolgens een URL naar het bestand met de instellingen op. Raadpleeg de Windows Server-documentatie voor meer informatie.
**Proxyserver gebruiken** (alleen voor iOS, Mac OS X, Windows 8.1 en Windows Phone 8.1)|Als de VPN-server een proxyserver voor de verbinding vereist, selecteert u deze optie en geeft u het adres en poortnummer van de proxyserver op. Raadpleeg de Windows Server-documentatie voor meer informatie.
**Proxy-instellingen overslaan voor lokale adressen** (alleen voor iOS, Mac OS X, Windows 8.1 en Windows Phone 8.1)|Als de VPN-server een proxyserver voor de verbinding vereist, selecteert u deze optie als u de proxyserver niet wilt gebruiken voor lokale adressen die u opgeeft. Raadpleeg de Windows Server-documentatie voor meer informatie.
**Aangepaste XML** (alleen Windows 8.1 en hoger, en Windows Phone 8.1 en hoger)|Geef aangepaste XML-opdrachten op waarmee de VPN-verbinding wordt geconfigureerd. Voorbeeld voor **Pulse Secure**: &lt;pulse-schema&gt;&lt;isSingleSignOnCredential&gt;true&lt;/isSingleSignOnCredential&gt;&lt;/pulse-schema&gt;. Voorbeeld voor **CheckPoint Mobile VPN**: &lt;CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" /&gt;. Voorbeeld voor **Dell SonicWALL Mobile Connect**: &lt;MobileConnect&gt;&lt;Compression&gt;false&lt;/Compression&gt;&lt;debugLogging&gt;True&lt;/debugLogging&gt;&lt;packetCapture&gt;False&lt;/packetCapture&gt;&lt;/MobileConnect&gt;. Voorbeeld voor **F5 Edge Client**: &lt;f5-vpn-conf&gt;&lt;single-sign-on-credential /&gt;&lt;f5-vpn-conf&gt;. Raadpleeg de VPN-documentatie van de respectievelijke fabrikanten voor meer informatie over het schrijven van aangepaste XML-opdrachten.
**Zoeklijst voor DNS-achtervoegsels** (alleen voor Windows Phone 8.1)|Geef per regel één DNS-achtervoegsel op. Elk DNS-achtervoegsel dat u opgeeft, wordt doorzocht wanneer met behulp van een korte naam verbinding met een website wordt gemaakt. Geef bijvoorbeeld de DNS-achtervoegsels **domain1.contoso.com** en **domain2.contoso.com** op. Wanneer u naar de URL **http://mywebsite**gaat, worden de URL's **http://mywebsite.domain1.contoso.com** en **http://mywebsite.domain2.contoso.com** doorzocht.
**VPN overslaan bij verbinding met Wi-Fi-netwerk van bedrijf** (alleen voor Windows Phone 8.1)|Selecteer deze optie om aan te geven dat de VPN-verbinding niet wordt gebruikt wanneer het apparaat is verbonden met het Wi-Fi-netwerk van het bedrijf.
**VPN overslaan bij verbinding met Wi-Fi-netwerk thuis** (alleen voor Windows Phone 8.1)|Selecteer deze optie om aan te geven dat de VPN-verbinding niet wordt gebruikt wanneer het apparaat is verbonden met een Wi-Fi-netwerk thuis.

De volgende aanvullende instellingen zijn beschikbaar voor Windows 10 Desktop- en Mobile-apparaten.

Naam van de instelling  |Meer informatie  
---------|---------
**Netwerkverkeersregels**|Selecteer welke protocollen en bereiken voor lokale en externe poorten voor de VPN-verbinding worden ingeschakeld. Als u geen netwerkverkeersregel maakt, worden alle protocollen, poorten en adresbereiken ingeschakeld. Nadat u een regel hebt gemaakt, worden door de VPN-verbinding alleen de protocollen, poorten en adresbereiken gebruikt die u in die regel opgeeft.
**Routes**|Selecteer welke routes de VPN-verbinding gebruiken.
**DNS-servers**| Selecteer welke DNS-servers de VPN-verbinding gebruiken nadat de verbinding tot stand is gebracht.         
**Gekoppelde apps**|Geef een lijst met apps op die automatisch gebruikmaken van de VPN-verbinding. De app-id is afhankelijk van het type app. Geef voor een universele app de naam van de productfamilie op waartoe het pakket behoort. Geef voor een bureaublad-app het bestandspad van de app op.          


> [!IMPORTANT]
> Het is raadzaam dat u alle lijsten met apps die u compileert voor gebruik in de configuratie van per-app VPN, beveiligt. Als een ongeautoriseerde gebruiker uw lijst wijzigt en u deze importeert in de app-lijst VPN per app, verleent u onbevoegde gebruikers mogelijk VPN-toegang tot apps die niet toegankelijk zouden moeten zijn. Een manier om uw lijsten met apps te beveiligen, is het gebruik van een toegangsbeheerlijst (ACL).

Hier volgt een voorbeeld van wanneer u instellingen voor bedrijfsgrenzen wilt gebruiken. Als u VPN alleen voor Extern bureaublad wilt inschakelen, dient u een netwerkverkeersregel te maken waarmee verkeer voor protocol 27 op externe poort 3996 wordt toegestaan. Er is geen ander verkeer dat de VPN-verbinding gebruikt.

Het definiëren van routes in bedrijfsgrenzen is handig als uw type VPN-verbinding u niet in staat stelt te definiëren hoe verkeer wordt verwerkt bij split tunneling. Gebruik in dat geval **Routes** om de routes weer te geven die de VPN gebruiken.

U kunt het VPN-gebruik door Windows 10-apparaten tot bepaalde apps beperken door een aangepaste OMA-URI-instelling te maken.

Het nieuwe beleid wordt weergegeven in het knooppunt **Configuratiebeleid** van de werkruimte **Beleid**.

### <a name="on-demand-vpn-for-ios-devices"></a>VPN op aanvraag voor iOS-apparaten
U kunt VPN op aanvraag voor apparaten met iOS 8.0 en hoger configureren.

> [!NOTE]
>  
> U kunt geen VPN per app en VPN per aanvraag in dezelfde beleidsregel gebruiken.

1. Zoek op de pagina voor de configuratie van beleidsregels naar **Regels voor deze VPN-verbinding op aanvraag**. De kolommen krijgen een label **Overeenkomst**, de voorwaarde die de regels controleert en **Actie**, de actie die door het beleid wordt geactiveerd wanneer aan de voorwaarde wordt voldaan.
2. Kies **Toevoegen** om een regel te maken. Er zijn twee soorten overeenkomsten die u in de regel kunt instellen. U kunt alleen een van de volgende typen per regel configureren.
  - **SSID's**, die verwijzen naar draadloze netwerken.
  - **DNS domeinen doorzoeken**, die...  U kunt volledige domeinnamen gebruiken, zoals *team. corp.contoso.com*, of domeinen gebruiken als *contoso.com*, het equivalent van het gebruik van * *. contoso.com*.
3. Optioneel: geef een URL-testtekenreeks op, een URL die gebruikmaakt van de regel als een test. Als het apparaat waarop dit profiel is geïnstalleerd, in staat is om toegang te krijgen tot deze URL zonder omleiding, wordt de VPN-verbinding tot stand gebracht en maakt het apparaat verbinding met de doel-URL. De gebruiker ziet de tekenreeks testsite voor de URL niet. Een voorbeeld van een URL-tekenreekstest is het adres van een controlewebserver die de apparaatcompatibiliteit controleert voordat u verbinding maakt met de VPN-verbinding. Een andere mogelijkheid is dat de URL de VPN-verbinding voor een site controleert, voordat het apparaat verbinding maakt met de doel-URL via de VPN-verbinding.
4. Kies een van de volgende acties:
  - **Verbinden**
  - **Verbinding evalueren**, waarvoor drie instellingen beschikbaar zijn. **Domeinactie**: kies **Verbinding indien nodig** of **Nooit verbinding maken met**
     b. **Door komma's gescheiden lijst met domeinen**: hiermee configureert u alleen een **Domeinactie** van het type **Verbinding indien nodig**
     c. **Vereiste tekenreeks van URL-test**: een HTTP of HTTPS (aanbevolen)-URL, zoals *https://vpntestprobe.contoso.com*. De regel controleert of er een reactie van dit adres is. Als dat niet het geval is en de **Domeinactie** is ingesteld op **Verbinding indien nodig**, wordt de VPN-verbinding geactiveerd.
     > [!TIP]
     >
     >Een voorbeeld van wanneer u deze actie kunt gebruiken wanneer sommige sites in uw bedrijfsnetwerk een directe of VPN-bedrijfsnetwerk vereisen, terwijl dit niet vereist is voor andere sites. Als u een lijst met **door komma's gescheiden lijst domeinen met een DNS-zoekopdracht** *corp.contoso.com*, hebt, kunt u **verbinding maken indien nodig** en vervolgens een lijst voor specifieke sites binnen dat netwerk die VPN weergeven, zoals *sharepoint.corp.contoso.com*. De regel controleert vervolgens of *vpntestprobe.contoso.com* kan worden bereikt. Als dit niet het geval is, wordt de VPN-verbinding geactiveerd voor de sharepoint-site.
  - **Negeren**: dit zorgt ervoor dat er geen wijzigingen zijn in de VPN-verbinding. Als de VPN is verbonden, laat u dit zo. Als er geen verbinding is, maakt u geen verbinding. U hebt bijvoorbeeld een VPN-verbinding voor al uw interne zakelijke websites, maar u wilt een van deze interne sites alleen toegankelijk maken wanneer het apparaat daadwerkelijk is verbonden met het bedrijfsnetwerk. In dat geval maakt u een negeerregel aan voor de desbetreffende site.
  - **Verbreken**: hiermee verbreekt u de VPN-verbinding met aangesloten apparaten als aan de voorwaarden wordt voldaan. U kunt bijvoorbeeld uw draadloze bedrijfsnetwerken in het veld **SSID** vermelden en een regel maken waarmee de VPN-verbinding wordt verbroken zodra de apparaten met een van deze netwerken verbinding maken.

Domeinspecifieke regels worden geëvalueerd voor regels die voor alle domeinen gelden.


## <a name="deploy-the-policy"></a>Het beleid implementeren

1.  Selecteer in de werkruimte **Beleid** het beleid dat u wilt implementeren en kies vervolgens **Implementatie beheren**.

2.  In het dialoogvenster **Implementatie beheren** :

    -   Om het beleid te implementeren, selecteert u een of meer groepen waarvoor u het beleid wilt implementeren en vervolgens klikt u op **Toevoegen** &gt; **OK**.

    -   Als u het dialoogvenster wilt sluiten zonder het beleid te implementeren, kiest u **Annuleren**.


Na een geslaagde implementatie zien gebruikers de naam van de VPN-verbinding die u hebt opgegeven in de lijst met VPN-verbindingen op hun apparaten.

Een statusoverzicht en waarschuwingen op de pagina **Overzicht** van de werkruimte **Beleid** identificeren beleidsproblemen die uw aandacht nodig hebben. Bovendien wordt er een statusoverzicht weergegeven in de werkruimte Dashboard.



<!--HONumber=Feb17_HO1-->


