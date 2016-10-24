---
title: Wi-Fi-verbindingen | Microsoft Intune
description: Gebruik Wi-Fi-profielen om gebruikers verbinding te laten maken met uw Wi-Fi-netwerken.
keywords: 
author: Nbigman
manager: angrobe
ms.date: 09/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0b1b86ed-2e80-474d-8437-17dd4bc07b55
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0ced62efd04803943cbbfd8cecef907409a03c0b
ms.openlocfilehash: beba0471f31a19dad78ddf71c07e323b18af18e8


---

# Apparaten configureren voor verbinding met uw Wi-Fi-bedrijfsnetwerken

Gebruik Wi-Fi-profielen van Microsoft Intune om instellingen voor draadloze netwerken te implementeren voor gebruikers en apparaten in uw organisatie. Wanneer u een Wi-Fi-profiel implementeert, hoeven uw gebruikers de toegang tot uw zakelijke Wi-Fi niet zelf te configureren.

Een voorbeeld: u installeert een nieuw Wi-Fi-netwerk met de naam **Contoso Wi-Fi** en wilt instellen dat alle iOS-apparaten verbinding met dit netwerk maken. Dit is het proces:

![Overzicht van proces voor Wi-Fi-profielen](..\media\wi-fi-process-diagram.png) 

1.   Maak een Wi-Fi-profiel met de instellingen die nodig zijn om verbinding te maken met het draadloze netwerk **Contoso Wi-Fi**.

2. Implementeer het profiel voor de groep gebruikers met iOS-apparaten.

3.   Gebruikers vinden het nieuwe **Contoso Wi-Fi**-netwerk in de lijst met draadloze netwerken en kunnen gemakkelijk verbinding met dit netwerk maken.


## Een Wi-Fi-profiel maken

U kunt Wi-Fi-profielen implementeren voor de volgende platforms:

-   Android 4.0 en hoger

-   iOS 8.0 en hoger

-   Mac OS X 10.9 en hoger

Voor apparaten met Windows 8.1 of Windows 10 Desktop of Mobile kunt u een Wi-Fi-configuratieprofiel importeren dat eerder naar een bestand is geëxporteerd. Zie [Een Wi-Fi-configuratieprofiel exporteren of importeren voor Windows-apparaten](#export-or-import-a-wi-fi-configuration-profile-for-windows-devices) voor meer informatie.

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Beleid** &gt; **Beleid toevoegen**.

2.  Selecteer een van de volgende beleidstypen en klik vervolgens op **Beleid maken**:

    -   Wi-Fi-profiel (Android 4 en hoger)

    -   Wi-Fi-profiel (iOS 8.0 en hoger)

    -   Wi-Fi-profiel (Mac OS X 10.9 en hoger)

    Er zijn geen aanbevolen instellingen voor dit beleidstype. U moet een aangepast beleid maken.

3.  Geef de naam en beschrijving voor het profiel op.

4. Geef de waarden voor **Netwerkverbindingen** op.
 - **SSID (serviceset-id)**: gebruikers zien de naam van het netwerk, niet de SSID.
 - **Verbinding maken als het netwerk de naam niet uitzendt (SSID)**: selecteer deze optie als u wilt dat apparaten verbinding met het netwerk maken wanneer dit niet zichtbaar is in de lijst met netwerken (omdat het netwerk verborgen is en zijn naam niet uitzendt).
 
5. Configureer de **beveiligingsinstellingen** voor het geselecteerde platform. De beschikbare instellingen zijn afhankelijk van de beveiligingstypen die u selecteert en zijn beschreven in [Beveiligingsinstellingen](#security-settings).

6. (alleen iOS en MAC OS X) **Proxy-instellingen** configureren

    |Naam van de instelling|Meer informatie|Gebruiken wanneer:|
    |----------------|-------------------|-------------|
    |**Proxy-instellingen voor deze Wi-Fi-verbinding**|Kies het type proxy-instelling:<br /><br />-   **Geen** (standaardinstelling)<br />-   **Handmatig**: geef handmatig de URL en het poortnummer van de proxyserver op.<br />-   **Automatisch**: gebruik een configuratiebestand om de proxyserver te configureren.|Altijd|
    |**Proxyserveradres** en **Poortnummer**|Geef de URL en het poortnummer van de proxyserver op.|**Proxy-instellingen voor deze Wi-Fi-verbinding** is ingesteld op **Handmatig**|
    |**URL van proxyserver**|Geef de URL van het bestand met de proxyserverinstellingen op.|**Proxy-instellingen voor deze Wi-Fi-verbinding** is ingesteld op **Automatisch**|

7.  het Wi-Fi-profiel opslaan

Het nieuwe beleid wordt weergegeven in het knooppunt **Configuratiebeleid** van de werkruimte **Beleid**. Zie **Vervolgstappen** voor informatie over het implementeren van het profiel.

## Een Wi-Fi-configuratieprofiel exporteren of importeren voor Windows-apparaten
 
Voor apparaten met Windows 8.1 of Windows 10 Desktop of Mobile kunt u een Wi-Fi-configuratieprofiel importeren dat eerder naar een bestand is geëxporteerd. 

### Een Wi-Fi-profiel exporteren
In Windows kunt u het hulpprogramma **netsh wlan** gebruiken om een bestaand Wi-Fi-profiel te exporteren naar een xml-bestand dat kan worden gelezen door Intune. Volg de volgende procedure op een Windows-computer waarop het vereiste Wi-Fi-profiel is geïnstalleerd.

1.  Maak een lokale map voor de geëxporteerde Wi-Fi-profielen, zoals c:\WiFi

2.  Open een opdrachtprompt als beheerder.

3.  Voer de opdracht `netsh wlan show profiles` uit en noteer de naam van het profiel dat u wilt exporteren.  In dit voorbeeld is de naam van het profiel *WiFiName*.

4.  Voer deze opdracht uit: `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Hiermee wordt in de doelmap een Wi-Fi-profielbestand met de naam Wi-Fi-WiFiName.xml gemaakt.

### Een Wi-Fi-profiel importeren
Gebruik het **Windows Wi-Fi-importbeleid** om een reek Wi-Fi-instellingen te importeren die u vervolgens kunt implementeren bij de vereiste groepen gebruikers of apparaten.


1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Beleid** &gt; **Beleid toevoegen**.

2.  Configureer een beleid van het type **Windows** &gt; **Wi-Fi-import (Windows 8.1 en hoger)**.

    Dit beleid kan worden toegepast op pc's en mobiele apparaten met Windows 8.1 en Windows 10.

    U kunt alleen een *aangepast* Windows Wi-Fi-importbeleid maken en implementeren. Aanbevolen instellingen zijn niet beschikbaar.

3.  Geef de volgende algemene waarden op voor het Windows Wi-Fi-importbeleid:

    |Naam van de instelling|Meer informatie|
    |----------------|--------------------|
    |**Naam**|Geef een unieke naam op voor het Wi-Fi-profiel, zodat u dit gemakkelijk in de Intune-console kunt herkennen.|
    |**Beschrijving**|Geef een beschrijving van het Wi-Fi-profiel en andere relevante informatie op om u bij het zoeken te helpen.|

4.  Geef de volgende waarden op onder de kop **Aangepast Wi-Fi-profiel**:

    |Naam van de instelling|Meer informatie|
    |----------------|--------------------|
    |**Configuratieprofielbestand**|Klik op **Importeren** om het xml-bestand met de Wi-Fi-profielinstellingen te selecteren dat u in Intune wilt importeren.|
    |**Aangepaste configuratieprofielnaam (weergegeven voor gebruikers)**|Geeft de naam weer die voor het Wi-Fi-configuratieprofiel wordt gebruikt op het apparaat van gebruikers.|
    |**Configuratieprofieldetails**|Geeft de XML-code weer voor het configuratieprofiel dat u hebt geselecteerd.|

5.  Wanneer u klaar bent, klikt u op **Beleid opslaan**.

6.  Het nieuwe beleid wordt weergegeven in het knooppunt **Configuratiebeleid** van de werkruimte **Beleid** .

## Het profiel implementeren

Een profiel is een soort beleid. Gebruik daarom de werkruimte Beleid om het te implementeren.

1.  Selecteer het beleid dat u wilt implementeren in de werkruimte **Beleid** en klik vervolgens op **Implementatie beheren**.

2.  In het dialoogvenster **Implementatie beheren** :

    -   **Het beleid implementeren**: selecteer een of meer groepen waarvoor u het beleid wilt implementeren en klik vervolgens op **Toevoegen** &gt; **OK**.

    -   **Het dialoogvenster sluiten zonder het beleid te implementeren**: klik op **Annuleren**.


Een statusoverzicht en waarschuwingen op de pagina **Overzicht** van de werkruimte **Beleid** identificeren beleidsproblemen die uw aandacht nodig hebben. Bovendien wordt er een statusoverzicht weergegeven in de werkruimte Dashboard.

## Beveiligingsinstellingen
In deze tabellen staan de details van de beveiligingsinstellingen die beschikbaar zijn voor Wi-Fi-profielen voor Android, iOS en Mac OS X. 

### Beveiligingsinstellingen voor Android-apparaten

  |Naam van de instelling|Meer informatie|Gebruiken wanneer:|
|----------------|--------------------|-------------|
|**Beveiligingstype**|Selecteer het beveiligingsprotocol voor het draadloze netwerk:<br /><br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **Geen verificatie (open)** als het netwerk niet beveiligd is.|Altijd|
|**EAP-type**|Kies het type Extensible Authentication Protocol (EAP) dat wordt gebruikt voor het verifiëren van beveiligde draadloze verbindingen:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TTLS**|Het beveiligingstype **WPA-Enterprise/WPA2-Enterprise** is geselecteerd.|
|**Basiscertificaten voor servervalidatie selecteren**|Klik op **Selecteren**en kies vervolgens het profiel voor een vertrouwd basiscertificaat dat wordt gebruikt om de verbinding te verifiëren. **Belangrijk:** voor het maken van het profiel voor vertrouwde basiscertificaten gaat u naar [Toegang tot beveiligde bronnen met certificaatprofielen](secure-resource-access-with-certificate-profiles.md).|Een **EAP-type** geselecteerd.|
|**Verificatiemethode**|Selecteer de verificatiemethode voor de verbinding:<br /><br />-   **Certificaten** om het clientcertificaat op te geven<br />-   **Gebruikersnaam en wachtwoord** om een andere methode voor verificatie op te geven|Het **EAP-type** is **PEAP** of **EAP-TTLS**.|
|**Een niet-EAP-methode voor verificatie selecteren (interne identiteit)**|Selecteer hoe de verbinding moet worden geverifieerd:<br /><br />-   **Geen**<br />-   **Niet-versleuteld wachtwoord (PAP)**<br />-   **Challenge Handshake Authentication Protocol (CHAP)**<br />-   **Microsoft CHAP (MS-CHAP)**<br />-   **Microsoft CHAP versie 2 (MS-CHAP v2)**<br /><br />De beschikbare opties zijn afhankelijk van het geselecteerde EAP-type.|De **verificatiemethode** is **Gebruikersnaam en wachtwoord**.|
|**Identiteitsprivacy inschakelen (externe identiteit)**|Geef de tekst op die wordt verzonden in antwoord op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben. Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.|Het **EAP-type** is **PEAP** of **EAP-TTLS**.|
|**Clientcertificaat selecteren voor clientverificatie (identiteitscertificaat)**|Klik op **Selecteren**en kies vervolgens het profiel voor een SCEP-certificaat dat wordt gebruikt om de verbinding te verifiëren. **Belangrijk:** voor het maken van het profiel voor SCEP-certificaten gaat u naar [Toegang tot beveiligde bronnen met certificaatprofielen](secure-resource-access-with-certificate-profiles.md).|Het beveiligingstype is **WPA-Enterprise/WPA2-Enterprise** en er is een **EAP-type** geselecteerd.|

### Beveiligingsinstellingen voor iOS- en Mac OS X-apparaten

  |Naam van de instelling|Meer informatie|Gebruiken wanneer:|
|----------------|--------------------|-------------|
|**Beveiligingstype**|Selecteer het beveiligingsprotocol voor het draadloze netwerk:<br /><br />-   **WPA-Personal/WPA2-Personal**<br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **WEP**<br />-   **Geen verificatie (open)** als het netwerk niet beveiligd is.|Altijd|
|**EAP-type**|Kies het type Extensible Authentication Protocol (EAP) dat wordt gebruikt voor het verifiëren van beveiligde draadloze verbindingen:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TLS**<br />-   **EAP-AST**<br />-   **LEAP**<br />-   **EAP-SIM**|Een beveiligingstype **WPA-Enterprise/WPA2-Enterprise** is geselecteerd.|
|**Namen van vertrouwde servercertificaten**|Selecteer het profiel voor een vertrouwd basiscertificaat dat wordt gebruikt om de verbinding te verifiëren. **Belangrijk:** voor het maken van het profiel voor vertrouwde basiscertificaten gaat u naar [Toegang tot beveiligde bronnen met certificaatprofielen](secure-resource-access-with-certificate-profiles.md).|Er is een EAP-type **EAP-TLS**, **PEAP**, **EAP-TTLS** of **EAP-FAST** geselecteerd.|
|**Protected Access Credential (PAC) gebruiken**|Selecteer dit om referenties voor beveiligde toegang te gebruiken om een geverifieerde tunnel tussen de client en de verificatieserver tot stand te brengen. Er wordt een bestaand PAC-bestand gebruikt, indien aanwezig.|Het **EAP-type** is **EAP-FAST**.|
|**PAC leveren**|Levert het PAC-bestand aan uw apparaten.<br /><br />Indien gebruikt, kunt u ook **PAC anoniem leveren** selecteren om ervoor te zorgen dat het PAC-bestand wordt geleverd zonder verificatie van de server.|**Protected Access Credential (PAC) gebruiken** is geselecteerd.|
|**Verificatiemethode**|Selecteer de verificatiemethode die wordt gebruikt voor de verbinding:<br /><br /><ul><li>**Certificaten** om het clientcertificaat op te geven</li><li>**Gebruikersnaam en wachtwoord** om een van de volgende niet-EAP-methoden voor verificatie op te geven (ook wel bekend als interne identiteit):<br /><br /><ul><li>**Geen**</li><li>**Niet-versleuteld wachtwoord (PAP)**</li><li>**Challenge Handshake Authentication Protocol (CHAP)**</li><li>**Microsoft CHAP (MS-CHAP)**</li><li>**Microsoft CHAP versie 2 (MS-CHAP v2)**</li><li>**EAP-TLS**</li></ul></li></ul>|Het **EAP-type** is **PEAP** of **EAP-TTLS**.|
|**Clientcertificaat selecteren voor clientverificatie (identiteitscertificaat)**|Selecteer het SCEP-certificaatprofiel dat wordt gebruikt om de verbinding te verifiëren. **Belangrijk:** voor het maken van het profiel voor SCEP-certificaten gaat u naar [Toegang tot beveiligde bronnen met certificaatprofielen](secure-resource-access-with-certificate-profiles.md).|Als het beveiligingstype **WPA-Enterprise/WPA2-Enterprise** en het **EAP type** **EAP-TLS**, **PEAP** of **EAP-TTLS** is.|
|**Identiteitsprivacy inschakelen (externe identiteit)**|Geef tekst op die wordt verzonden in antwoord op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben.<br /><br />Tijdens verificatie wordt deze anonieme identiteit in eerste instantie verzonden en wordt deze gevolgd door de echte identificatie in een beveiligde tunnel.|Wanneer het **EAP-type** is ingesteld op **PEAP**, **EAP-TTLS** of **EAP-FAST**.|


### Zie tevens
Zie [Wi-Fi-profiel met vooraf gedeelde sleutel](pre-shared-key-wi-fi-profile.md) voor meer informatie over het maken van een Wi-Fi-profiel met een vooraf gedeelde sleutel.



<!--HONumber=Sep16_HO3-->


