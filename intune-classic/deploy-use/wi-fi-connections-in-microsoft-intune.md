---
title: Wi-Fi-verbindingen
description: Gebruik Wi-Fi-profielen om gebruikers verbinding te laten maken met uw Wi-Fi-netwerken.
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0b1b86ed-2e80-474d-8437-17dd4bc07b55
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5d021abec31a38d7135828fbe06acd4a1a10ee42
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2017
---
# <a name="configure-devices-to-connect-to-your-corporate-wi-fi-networks"></a>Apparaten configureren voor verbinding met uw Wi-Fi-bedrijfsnetwerken

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Gebruik Wi-Fi-profielen van Microsoft Intune om instellingen voor draadloze netwerken te implementeren voor gebruikers en apparaten in uw organisatie. Wanneer u een Wi-Fi-profiel implementeert, hebben uw gebruikers toegang tot uw zakelijke Wi-Fi zonder dat ze dit zelf hoeven te configureren.

Een voorbeeld: u installeert een nieuw Wi-Fi-netwerk met de naam **Contoso Wi-Fi** en wilt instellen dat alle iOS-apparaten verbinding met dit netwerk maken. Dit is het proces:

![Overzicht van proces voor Wi-Fi-profielen](..\media\wi-fi-process-diagram.png)

1.   Maak een Wi-Fi-profiel met de instellingen die nodig zijn om verbinding te maken met het draadloze netwerk **Contoso Wi-Fi**.

2.   Implementeer het profiel voor de groep gebruikers met iOS-apparaten.

3.   Gebruikers vinden het nieuwe **Contoso Wi-Fi**-netwerk in de lijst met draadloze netwerken en kunnen gemakkelijk verbinding met dit netwerk maken.


## <a name="create-a-wi-fi-profile"></a>Een Wi-Fi-profiel maken

U kunt Wi-Fi-profielen implementeren voor de volgende platforms:

-   Android 4.0 en hoger

-   Android for Work   

-   iOS 8.0 en hoger

-   Mac OS X 10.9 en hoger

Voor apparaten met het besturingssysteem Windows 8.1 of Windows 10 Desktop of Mobile kunt u een Wi-Fi-configuratieprofiel importeren dat eerder naar een bestand is geëxporteerd. Zie [Een Wi-Fi-configuratieprofiel exporteren of importeren voor Windows-apparaten](#export-or-import-a-wi-fi-configuration-profile-for-windows-devices) voor meer informatie.

1.  Ga naar de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) en kies**Beleid** &gt; **Beleid toevoegen**.

2.  Selecteer een van de volgende beleidstypen en kies vervolgens **Beleid maken**:

    -   Wi-Fi-profiel (Android 4 en hoger)

    -   Wi-Fi-profiel (Android for Work)

    -   Wi-Fi-profiel (iOS 8.0 en hoger)

    -   Wi-Fi-profiel (Mac OS X 10.9 en hoger)


Er zijn geen aanbevolen instellingen voor dit beleidstype. U moet een aangepast beleid maken.

3.  Geef de naam en beschrijving voor het profiel op.

4. Geef de waarden voor **Netwerkverbindingen** op.
 - **SSID (Service Set Identifier)**: selecteer deze optie als u wilt dat gebruikers de netwerknaam en niet de SSID zien.
 - **Verbinding maken als het netwerk de naam (SSID) niet uitzendt**: selecteer deze optie als u wilt dat apparaten verbinding maken met het netwerk wanneer dit niet zichtbaar is in de lijst met netwerken (omdat het netwerk verborgen is en zijn naam niet uitzendt).

5. Configureer de **beveiligingsinstellingen** voor het geselecteerde platform. De beschikbare instellingen zijn afhankelijk van de beveiligingstypen die u selecteert. Deze worden beschreven in de [Beveiligingsinstellingen](#security-settings).

6. Configureer de **Proxy-instellingen** (alleen voor iOS en MAC OS X).

    |Naam van de instelling|Meer informatie|Gebruik|
    |----------------|-------------------|-------------|
    |**Proxy-instellingen voor deze Wi-Fi-verbinding**|Kies het type proxy-instelling:<br /><br />-   **Geen** (standaardinstelling)<br />-   **Handmatig**: geef handmatig de URL en het poortnummer van de proxyserver op.<br />-   **Automatisch**: gebruik een configuratiebestand om de proxyserver te configureren.|Altijd|
    |**Proxyserveradres** en **Poortnummer**|Geef de URL en het poortnummer van de proxyserver op.|Als **Proxy-instellingen voor deze Wi-Fi-verbinding** is ingesteld op **Handmatig**|
    |**URL van proxyserver**|Geef de URL van het bestand met de proxyserverinstellingen op.|Als **Proxy-instellingen voor deze Wi-Fi-verbinding** is ingesteld op **Automatisch**|

7.  het Wi-Fi-profiel opslaan

Het nieuwe beleid wordt weergegeven in het knooppunt **Configuratiebeleid** van de werkruimte **Beleid**. Zie **Vervolgstappen** voor informatie over het implementeren van het profiel.

## <a name="export-or-import-a-wi-fi-configuration-profile-for-windows-devices"></a>Een Wi-Fi-configuratieprofiel exporteren of importeren voor Windows-apparaten

Voor apparaten met het besturingssysteem Windows 8.1 of Windows 10 Desktop of Mobile kunt u een Wi-Fi-configuratieprofiel importeren dat eerder naar een bestand is geëxporteerd.

### <a name="export-a-wi-fi-profile"></a>Een Wi-Fi-profiel exporteren
In Windows kunt u het hulpprogramma **netsh wlan** gebruiken om een bestaand Wi-Fi-profiel te exporteren naar een xml-bestand dat kan worden gelezen door Intune. Voer de volgende stappen uit op een Windows-computer waarop het vereiste Wi-Fi-profiel is geïnstalleerd:

1.  Maak een lokale map voor de geëxporteerde Wi-Fi-profielen. Maak bijvoorbeeld een map met de naam **c:\WiFi**.

2.  Open een opdrachtprompt als beheerder.

3.  Voer de opdracht `netsh wlan show profiles` uit en noteer de naam van het profiel dat u wilt exporteren.  In dit voorbeeld is de naam van het profiel **WiFiName**.

4.  Voer deze opdracht uit: `netsh wlan export profile name="ProfileName" folder=c:\Wifi`. Hiermee wordt in de doelmap een Wi-Fi-profielbestand gemaakt met de naam **Wi-Fi-WiFiName.xml**.

### <a name="import-a-wi-fi-profile"></a>Een Wi-Fi-profiel importeren
Gebruik het **Windows Wi-Fi-importbeleid** om een reek Wi-Fi-instellingen te importeren die u vervolgens kunt implementeren bij de vereiste groepen gebruikers of apparaten.


1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Beleid** &gt; **Beleid toevoegen**.

2.  Configureer een beleid van het type **Windows** &gt; **Wi-Fi-import (Windows 8.1 en hoger)**.

    Dit beleid kan worden toegepast op apparaten met het besturingssysteem Windows 8.1 en Windows 10 Desktop en Mobile.

    U kunt alleen een *aangepast* Windows Wi-Fi-importbeleid maken en implementeren. Aanbevolen instellingen zijn niet beschikbaar.

3.  Geef de volgende algemene waarden op voor het Windows Wi-Fi-importbeleid:

    |Naam van de instelling|Meer informatie|
    |----------------|--------------------|
    |**Naam**|Geef een unieke naam op voor het Wi-Fi-profiel, zodat u dit gemakkelijk in de Intune-console kunt herkennen.|
    |**Beschrijving**|Geef een beschrijving van het Wi-Fi-profiel en andere relevante informatie op om u bij het zoeken te helpen.|

4.  Geef de volgende waarden op onder de kop **Aangepast Wi-Fi-profiel**:

    |Naam van de instelling|Meer informatie|
    |----------------|--------------------|
    |**Configuratieprofielbestand**|Kies **Importeren** om het xml-bestand met de Wi-Fi-profielinstellingen te selecteren dat u in Intune wilt importeren.|
    |**Aangepaste configuratieprofielnaam (weergegeven voor gebruikers)**|Kies hoe u de naam van het Wi-Fi-configuratieprofiel wilt weergeven op het apparaat van gebruikers.|
    |**Configuratieprofieldetails**|Kies hoe u de XML-code voor het geselecteerde configuratieprofiel wilt weergeven.|

5.  Als u klaar bent, kiest u **Beleid opslaan**.

6.  Het nieuwe beleid wordt weergegeven in het knooppunt **Configuratiebeleid** van de werkruimte **Beleid** .

## <a name="deploy-the-profile"></a>Het profiel implementeren

Een profiel is een type beleid. Gebruik daarom de werkruimte **Beleid** om het te implementeren.

1.  Selecteer het beleid dat u wilt implementeren in de werkruimte **Beleid** en kies vervolgens **Implementatie beheren**.

2.  In het dialoogvenster **Implementatie beheren** :

    -   **Het beleid implementeren**: selecteer een of meer groepen waarop u het beleid wilt implementeren. Kies vervolgens **Toevoegen** &gt; **OK**.

    -   **Het dialoogvenster sluiten zonder het beleid te implementeren**: klik op **Annuleren**.


Op de pagina **Overzicht** van de werkruimte **Beleid** worden beleidsproblemen weergegeven die uw aandacht vereisen. Bovendien wordt er een statusoverzicht weergegeven in de werkruimte Dashboard.

## <a name="security-settings"></a>Beveiligingsinstellingen
In deze tabellen staan de details van de beveiligingsinstellingen die beschikbaar zijn voor Wi-Fi-profielen voor Android, iOS en Mac OS X.

### <a name="security-settings-for-android-devices"></a>Beveiligingsinstellingen voor Android-apparaten

  |Naam van de instelling|Meer informatie|Gebruik|
|----------------|--------------------|-------------|
|**Beveiligingstype**|Selecteer het beveiligingsprotocol voor het draadloze netwerk:<br /><br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **Geen verificatie (open)** als het netwerk niet is beveiligd.|Altijd|
|**EAP-type**|Kies het type Extensible Authentication Protocol (EAP) dat wordt gebruikt voor het verifiëren van beveiligde draadloze verbindingen:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TTLS**|Als u het beveiligingstype **WPA-Enterprise/WPA2-Enterprise** hebt geselecteerd.|
|**Basiscertificaten voor servervalidatie selecteren**|Klik op **Selecteren** en kies vervolgens het profiel voor een vertrouwd basiscertificaat dat wordt gebruikt om de verbinding te verifiëren. Zie [Toegang tot beveiligde bronnen met certificaatprofielen](secure-resource-access-with-certificate-profiles.md) voor meer informatie over het gebruik van certificaatprofielen in Intune.|Als u een **EAP-Type** hebt geselecteerd.|
|**Verificatiemethode**|Selecteer de verificatiemethode die wordt gebruikt voor de verbinding:<br /><br />-   **Certificaten** om het clientcertificaat op te geven<br />-   **Gebruikersnaam en wachtwoord** om een andere methode voor verificatie op te geven|Het **EAP-type** is **PEAP** of **EAP-TTLS**.|
|**Een niet-EAP-methode voor verificatie selecteren (interne identiteit)**|Selecteer hoe de verbinding moet worden geverifieerd:<br /><br />-   **Geen**<br />-   **Niet-versleuteld wachtwoord (PAP)**<br />-   **Challenge Handshake Authentication Protocol (CHAP)**<br />-   **Microsoft CHAP (MS-CHAP)**<br />-   **Microsoft CHAP versie 2 (MS-CHAP v2)**<br /><br />De beschikbare opties zijn afhankelijk van het EAP-type dat u hebt geselecteerd.|De **verificatiemethode** is **Gebruikersnaam en wachtwoord**.|
|**Identiteitsprivacy inschakelen (externe identiteit)**|Geef de tekst op die wordt verzonden in antwoord op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben. Tijdens verificatie wordt in eerste instantie deze anonieme identiteit verzonden. De echte identificatie wordt in een beveiligde tunnel verzonden.|Als het **EAP-type** **PEAP** of **EAP-TTLS** is.|
|**Clientcertificaat selecteren voor clientverificatie (identiteitscertificaat)**|Klik op **Selecteren** en kies vervolgens het SCEO-profiel dat wordt gebruikt om de verbinding te verifiëren. Zie [Toegang tot beveiligde bronnen met certificaatprofielen](secure-resource-access-with-certificate-profiles.md) voor meer informatie over het maken van een SCEP-certificaatprofiel in Intune.|Als het beveiligingstype **WPA-Enterprise/WPA2-Enterprise** is en er een **EAP-type** is geselecteerd.|

### <a name="security-settings-for-ios-and-mac-os-x-devices"></a>Beveiligingsinstellingen voor iOS- en Mac OS X-apparaten

  |Naam van de instelling|Meer informatie|Gebruik|
|----------------|--------------------|-------------|
|**Beveiligingstype**|Selecteer het beveiligingsprotocol voor het draadloze netwerk:<br /><br />-   **WPA-Personal/WPA2-Personal**<br />-   **WPA-Enterprise/WPA2-Enterprise**<br />-   **WEP**<br />-   **Geen verificatie (open)** als het netwerk niet is beveiligd.|Altijd|
|**EAP-type**|Kies het type Extensible Authentication Protocol (EAP) dat wordt gebruikt voor het verifiëren van beveiligde draadloze verbindingen:<br /><br />-   **EAP-TLS**<br />-   **PEAP**<br />-   **EAP-TLS**<br />-   **EAP-AST**<br />-   **LEAP**<br />-   **EAP-SIM**|Als een beveiligingstype **WPA-Enterprise/WPA2-Enterprise** is geselecteerd.|
|**Namen van vertrouwde servercertificaten**|Selecteer het profiel voor een vertrouwd basiscertificaat dat wordt gebruikt om de verbinding te verifiëren. Zie [Toegang tot beveiligde bronnen met certificaatprofielen](secure-resource-access-with-certificate-profiles.md) voor meer informatie over het gebruik van certificaatprofielen in Intune.|Als een EAP-type **EAP-TLS**, **PEAP**, **EAP-TTLS** of **EAP-FAST** is geselecteerd.|
|**Protected Access Credential (PAC) gebruiken**|Selecteer dit om referenties voor beveiligde toegang te gebruiken om een geverifieerde tunnel tussen de client en de verificatieserver tot stand te brengen. Er wordt een bestaand PAC-bestand gebruikt, indien aanwezig.|Als het **EAP-type** **EAP-FAST** is.|
|**PAC inrichten**|Hiermee wordt het PAC-bestand op uw apparaten ingesteld.<br /><br />Indien gebruikt, kunt u ook **PAC anoniem leveren** selecteren om ervoor te zorgen dat het PAC-bestand wordt ingesteld zonder verificatie van de server.|Als **Protected Access Credential (PAC) gebruiken** is geselecteerd.|
|**Verificatiemethode**|Selecteer de verificatiemethode die wordt gebruikt voor de verbinding:<br /><br /><ul><li>**Certificaten** om het clientcertificaat op te geven</li><li>**Gebruikersnaam en wachtwoord** om een van de volgende niet-EAP-methoden voor verificatie op te geven (ook wel bekend als interne identiteit):<br /><br /><ul><li>**Geen**</li><li>**Niet-versleuteld wachtwoord (PAP)**</li><li>**Challenge Henshake Authentication Protocol (CHAP)**</li><li>**Microsoft CHAP (MS-CHAP)**</li><li>**Microsoft CHAP versie 2 (MS-CHAP v2)**</li><li>**EAP-TLS**</li></ul></li></ul>|Als het **EAP-type** **PEAP** of **EAP-TTLS** is.|
|**Clientcertificaat selecteren voor clientverificatie (identiteitscertificaat)**|Selecteer het SCEP-certificaatprofiel dat wordt gebruikt om de verbinding te verifiëren. Zie [Toegang tot beveiligde bronnen met certificaatprofielen](secure-resource-access-with-certificate-profiles.md) voor meer informatie over het maken van een SCEP-certificaatprofiel in Intune.|Als het beveiligingstype **WPA-Enterprise/WPA2-Enterprise** en het **EAP-type** **EAP-TLS**, **PEAP** of **EAP-TTLS** is.|
|**Identiteitsprivacy inschakelen (externe identiteit)**|Geef tekst op die wordt verzonden in antwoord op een EAP-identiteitsaanvraag. Deze tekst kan elke waarde hebben.<br /><br />Tijdens verificatie wordt in eerste instantie deze anonieme identiteit verzonden. De echte identificatie wordt in een beveiligde tunnel verzonden.|Als het **EAP-type** is ingesteld op **PEAP**, **EAP-TTLS** of **EAP-FAST**.|


### <a name="see-also"></a>Zie tevens
Zie [Wi-Fi-profiel met vooraf gedeelde sleutel](pre-shared-key-wi-fi-profile.md) voor meer informatie over het maken van een Wi-Fi-profiel met een vooraf gedeelde sleutel.
