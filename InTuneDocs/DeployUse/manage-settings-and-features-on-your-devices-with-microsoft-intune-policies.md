---
title: Apparaatinstellingen beheren met beleid | Microsoft Intune
description: Gebruik Intune om beleid te maken en implementeren waarmee instellingen en functies worden beheerd op ingeschreven apparaten die u beheert.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fa665c758460b8bbd95b237da6a22eda741b8b95
ms.openlocfilehash: 0dc10ea029d078840a584424f7900f340189b960


---

# Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid
Microsoft Intune-*beleid* bestaat uit groepen instellingen waarmee functies worden beheerd op mobiele apparaten en computers. U maakt beleidsregels met behulp van sjablonen die aanbevolen of aangepaste instellingen bevatten, en u implementeert deze vervolgens op apparaat- of gebruikersgroepen.

## Typen beleidsregels

Intune-beleid valt in de volgende categorieën: De categorie die u gebruikt, is van invloed op hoe u het beleid maakt en implementeert.


- **Configuratiebeleid:** dit wordt vaak gebruikt om beveiligingsinstellingen en -functies op uw apparaten te beheren. Gebruik de informatie in dit onderwerp voor meer inzicht in het maken en implementeren van dit beleid en bekijk de beschikbare instellingen.
- **Nalevingsbeleid:** dit definieert de regels en instellingen waaraan een apparaat moet voldoen om ook te voldoen aan het beleid voor voorwaardelijke toegang. U kunt nalevingsbeleid ook gebruiken om de naleving van apparaten te bewaken en te herstellen, onafhankelijk van voorwaardelijke toegang.
Zie [Nalevingsbeleid voor apparaten in Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md) voor meer informatie.
- **Beleid voor voorwaardelijke toegang:** dit beleid helpt u bij het beveiligen van e-mail en andere services op basis van de door u opgegeven voorwaarden.
Zie [De toegang tot e-mail en O365-services beperken met Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) voor meer informatie.
- **Inschrijvingsbeleid voor bedrijfsapparaten:** zie [iOS- en Mac-beheer instellen met Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md) voor meer informatie over het inschrijvingsbeleid voor bedrijfsapparaten.
- **Resourcetoegangsbeleid:** deze beleidsregels werken samen om uw gebruikers toegang te verlenen tot de bestanden en bronnen die ze nodig hebben om hun werk te doen, waar ze ook zijn.
Zie [Toegang tot bedrijfsresources inschakelen met Microsoft Intune](enable-access-to-company-resources-with-microsoft-intune.md) voor meer informatie.


Zie [Documentatie voor Microsoft Intune-beleid](microsoft-intune-policy-reference.md) voor een volledige lijst met Intune-beleidsregels.




## Een configuratiebeleid maken

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) de optie **Beleid** &gt; **Configuratiebeleid** &gt; **Toevoegen**.

2.  Kies het gewenste beleid. Kies de aanbevolen instellingen voor het beleid (indien beschikbaar; u kunt deze instellingen later wijzigen) of kies ervoor een aangepast beleid te maken met uw eigen instellingen.

    > [!TIP]
    > Zie de [Documentatie voor Microsoft Intune-beleid](microsoft-intune-policy-reference.md) voor meer informatie over het kiezen van het juiste beleid.

3.  Als u klaar bent, kiest u **Beleid maken**.

4.  Configureer op de pagina **Beleid maken** een naam en optionele beschrijving voor het beleid.

5.  Configureer de vereiste beleidsinstellingen en kies vervolgens **Beleid opslaan**.

    Als u hulp nodig hebt met de beleidsinstellingen, kiest u uw beleidstype in de volgende lijst:

    - [Instellingen voor iOS-apparaten](ios-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor Android-apparaten](android-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor Windows 8- en Windows 8.1-apparaten](windows-configuration-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor Windows Phone 8.1-apparaten](windows-phone-8-1-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor Windows 10 Desktop- en Mobile-apparaten](windows-10-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor Windows Team-apparaten](windows-team-configuration-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor upgrades van de Windows-editie](edition-upgrade-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor Mac OS X-apparaten](mac-os-x-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor Exchange Active Sync](exchange-activesync-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor het beleid voor voorwaarden](terms-and-condition-policy-settings-in-microsoft-intune.md)
    - [Algemene instellingen voor mobiele apparaten (verouderd)](mobile-device-security-policy-settings-in-microsoft-intune.md)

4.  Kies in het bevestigingsdialoogvenster **Ja** om het beleid nu te implementeren of kies **Nee** om het beleid te maken zonder het te implementeren.

U kunt het nieuwe beleid bekijken en bewerken door te bladeren door de secties voor elk beleidstype in de werkruimte **Beleid** .

Wanneer u een beleid maakt dat gebruikmaakt van de aanbevolen instellingen, is de naam van het nieuwe beleid een combinatie van de sjabloonnaam, de datum en de tijd. Wanneer u het beleid bewerkt, wordt de naam bijgewerkt met de tijd en de datum van de bewerking.

Nadat u een beleid hebt gemaakt, wilt u dit waarschijnlijk implementeren op een of meer groepen gebruikers of apparaten.

> [!TIP]
> U kunt niet alle beleidstypen implementeren. Het beleid voor het beheren van mobiele toepassingen (MAM) bijvoorbeeld wordt niet geïmplementeerd. Dit beleidstype wordt in plaats daarvan gekoppeld aan een app, dat u vervolgens implementeert.

## Een configuratiebeleid implementeren

1.  Selecteer in de werkruimte **Beleid** het beleid dat u wilt implementeren en kies vervolgens **Implementatie beheren**.

2.  In het dialoogvenster **Implementatie beheren** :

    -   Om het beleid te implementeren, selecteert u een of meer groepen waarvoor u het beleid wilt implementeren en vervolgens klikt u op **Toevoegen** &gt; **OK**.

    -   Kies **Annuleren** om het dialoogvenster te sluiten zonder het beleid te implementeren.

Wanneer u een geïmplementeerde beleid selecteert, kunt u meer informatie over de implementatie weergeven onder in de lijst met beleidsregels.

## Beleid beheren

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) de optie **Beleid** en selecteer vervolgens het beleid dat u wilt beheren.

2.  Selecteer een van de volgende acties:

- **Bewerken**: hiermee opent u de eigenschappen voor het geselecteerde beleid, zodat u wijzigingen kunt aanbrengen.
- **Verwijderen**: hiermee verwijdert u het geselecteerde beleid.<br>Wanneer u een beleid verwijdert, wordt dit verwijderd uit alle groepen waarop het was geïmplementeerd.
- **Implementatie beheren**: selecteer de groep waarvoor u het beleid wilt implementeren en kies vervolgens **Toevoegen**.


## Veelgestelde vragen over het Intune-beleid

### Hoe lang duurt het voor mobiele apparaten een beleid of apps hebben ontvangen nadat deze zijn geïmplementeerd?
Wanneer er een beleid of een app wordt geïmplementeerd, probeert Intune het apparaat onmiddellijk te melden dat het een controle bij de Intune-service moet uitvoeren. Dit vindt meestal binnen vijf minuten plaats.

Als een apparaat geen controle uitvoert of het beleid niet kan worden opgehaald nadat de eerste melding daarover is verzonden, doet Intune nog drie pogingen.  Als het apparaat offline is (bijvoorbeeld omdat het is uitgeschakeld of niet is verbonden met een netwerk), kan het geen meldingen ontvangen. In dat geval ontvangt het apparaat het beleid bij de volgende geplande controle bij de Intune-service en wel als volgt:

- iOS en Mac OS X: om de 6 uur.
- Android: om de 8 uur.
- Windows Phone: om de 8 uur.
- Ingeschreven Windows RT-apparaten: elke 24 uur.
- Windows 8.1- en Windows 10-pc's die als apparaten zijn ingeschreven: om de 8 uur.

Als het apparaat zojuist is ingeschreven, is de controlefrequentie hoger, en wel als volgt:

- iOS en Mac OS X: om de 15 minuten gedurende 6 uur en daarna om de 6 uur.
- Android: om de 3 minuten gedurende 15 minuten, daarna om de 15 minuten gedurende 2 uur en vervolgens om de 8 uur.
- Windows Phone: om de 5 minuten gedurende 15 minuten, daarna om de 15 minuten gedurende 2 uur en vervolgens om de 8 uur.
- Windows-computers die als apparaten zijn ingeschreven: om de 3 minuten gedurende 30 minuten en vervolgens om de 8 uur.

Gebruikers kunnen ook de bedrijfsportal-app openen en het apparaat onmiddellijk synchroniseren om op elk gewenst moment op aanwezig beleid te controleren.

### Welke acties zorgen ervoor dat Intune onmiddellijk een melding naar een apparaat verzendt?
Apparaten voeren een controle uit in Intune wanneer ze een melding ontvangen waarin staat dat ze dit moeten doen of wanneer het tijd is voor een geplande periodieke controle.  Wanneer u een actie specifiek op een apparaat of gebruiker richt, zoals de actie wissen, vergrendelen, wachtwoord opnieuw instellen, app implementeren, profiel implementeren (Wi-Fi, VPN, e-mail, enz.) of beleidsregels implementeren, probeert Intune het apparaat onmiddellijk te melden dat het een controle bij de Intune-service moet uitvoeren om deze updates te ontvangen.

Andere wijzigingen zoals het wijzigen van de contactgegevens in de bedrijfsportal zorgen niet voor een onmiddellijke melding aan apparaten.

### Als er meerdere beleidsregels worden geïmplementeerd voor dezelfde gebruiker of hetzelfde apparaat, hoe weet ik dan welke instellingen worden toegepast?
Wanneer er twee of meer sets beleidsregels naar dezelfde gebruiker of hetzelfde apparaat worden geïmplementeerd, vindt de beoordeling van welke instelling wordt toegepast plaats op het niveau van de individuele instelling:

-   Nalevingsbeleidsinstellingen hebben altijd voorrang op configuratiebeleidsinstellingen.

-   De strengste nalevingsbeleidsinstelling wordt toegepast als dit beleid wordt vergeleken met dezelfde instelling in een ander nalevingsbeleid.

-   Als een configuratiebeleidsinstelling een conflict veroorzaakt met een instelling in een ander configuratiebeleid, wordt dit conflict weergegeven in de Intune-console. U moet dergelijke conflicten handmatig oplossen.

### Wat gebeurt er wanneer MAM-beleidsregels elkaar tegenspreken? Welke regel wordt toegepast op de app?
Conflictwaarden zijn de meest beperkende instellingen die beschikbaar zijn in MAM-beleid, uitgezonderd cijferinvoervelden (zoals aantal pincodepogingen voorafgaand aan opnieuw instellen).  De cijferinvoervelden worden op hetzelfde ingesteld als de waarden, alsof u een MAM-beleid hebt gemaakt in de console met behulp van de aanbevolen instellingenoptie.

Er treden conflicten op wanneer twee beleidsinstellingen hetzelfde zijn.  Bijvoorbeeld als u twee MAM-beleidsregels hebt geconfigureerd die identiek zijn met uitzondering van de instelling voor kopiëren en plakken.  In dit scenario wordt de instelling voor kopiëren en plakken ingesteld op de meest beperkende waarde, maar de overige instellingen worden toegepast zoals die zijn geconfigureerd.

Als er een beleid is geïmplementeerd voor de app en dat beleid is van kracht geworden, en er wordt vervolgens een tweede beleid geïmplementeerd, heeft het eerste beleid prioriteit en dit blijft toegepast, terwijl het tweede als conflicterend wordt beschouwd. Indien ze beide op hetzelfde moment worden toegepast, wanneer er dus geen voorafgaand beleid is, worden ze allebei als conflicterend beschouwd. Eventueel conflicterende instellingen worden ingesteld op de meest beperkende waarden.

### Wat gebeurt er als aangepaste iOS-beleidsregels conflicteren?
Intune beoordeelt de nettolading van Apple-configuratiebestanden of een aangepast beleid voor de Open Mobile Alliance Uniform Resource Identifier (OMA-URI) niet. Het fungeert alleen als bezorgingsmechanisme.

Zorg er voor dat wanneer u een aangepast beleid implementeert dat de geconfigureerde instellingen niet conflicteren met het nalevingsbeleid, configuratiebeleid of ander aangepast beleid. Als er bij een aangepast beleid sprake is van conflicterende instellingen, worden instellingen in willekeurige volgorde toegepast.

### Wat gebeurt er wanneer een beleid wordt verwijderd of niet langer van toepassing is?
Wanneer u een beleid verwijdert of een apparaat verwijdert uit een groep waarop een beleid is geïmplementeerd, worden het beleid en de instellingen van het apparaat verwijderd, volgens de volgende lijsten.

#### Ingeschreven apparaten

- Wi-Fi-, VPN-, certificaat- en e-mailprofielen: deze profielen worden verwijderd van alle ondersteunde ingeschreven apparaten.
- Alle andere beleidstypen:
    - **Windows- en Android-apparaten**: de instellingen worden niet van het apparaat verwijderd.
    - **Windows Phone 8.1-apparaten**: de volgende instellingen worden verwijderd:
        - Wachtwoord vereist voor het ontgrendelen van mobiele apparaten
        - Eenvoudige wachtwoorden toestaan
        - Minimale wachtwoordlengte
        - Vereist wachtwoordtype
        - Wachtwoordverlooptijd (dagen)
        - Wachtwoordgeschiedenis onthouden
        - Aantal mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist
        - Minuten inactief voordat wachtwoord is vereist
        - Vereist wachtwoordtype – minimum aantal tekensets
        - Camera toestaan
        - Versleuteling vereisen voor mobiel apparaat
        - Verwisselbare opslag toestaan
        - Webbrowser toestaan
        - Toepassingsarchief toestaan
        - Schermafbeelding toestaan
        - Geolocatie toestaan
        - Microsoft-account toestaan
        - Kopiëren en plakken toestaan
        - Wi-Fi-tethering toestaan
        - Automatische verbinding met gratis Wi-Fi-hotspots toestaan
        - Melden van Wi-Fi-hotspots toestaan
        - Terugzetten op fabrieksinstellingen toestaan
        - Bluetooth toestaan
        - NFC toestaan
        - Wi-Fi toestaan

    - **iOS**: alle instellingen worden verwijderd, met uitzondering van:
        - Spraakroaming toestaan
        - Gegevensroaming toestaan
        - Automatische synchronisatie tijdens roamen toestaan

#### Windows-pc's met de Intune-clientsoftware

- **Instellingen voor Endpoint Protection**: de instellingen worden teruggezet naar de aanbevolen waarden. De enige uitzondering hierop is de instelling **Deelnemen aan Microsoft Active Protection Service** waarvoor de standaardwaarde **Nee** is. Zie [Windows-pc's beter beveiligen met Endpoint Protection voor Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) voor meer informatie.
- **Instellingen voor software-updates**: de instellingen worden opnieuw ingesteld op de standaardstatus voor het besturingssysteem. Zie [Windows-pc's up-to-date houden met software-updates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) voor meer informatie.
- **Instellingen Microsoft Intune Center**: alle contactgegevens voor ondersteuning die door het beleid zijn geconfigureerd, worden van de computers verwijderd.
- **Instellingen voor Windows Firewall**: de instellingen worden opnieuw ingesteld op de standaardwaarde voor het computerbesturingssysteem. Zie [Windows-pc's beter beveiligen met Endpoint Protection voor Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) voor meer informatie.


### Hoe kan ik het beleid vernieuwen op een apparaat zodat dit actueel is? (Alleen van toepassing op Windows-pc's met de Intune-clientsoftware.)

1.  Selecteer in een apparaatgroep de apparaten waarvoor u het beleid wilt vernieuwen, en kies vervolgens **Externe taken** &gt; **Beleid vernieuwen**.
2.  Kies in de rechterbenedenhoek van de Intune-beheerconsole **Externe taken** om de taakstatus te controleren.

### Waar vind ik meer informatie over het oplossen van beleidsproblemen?

Zie [Beleidsproblemen oplossen in Microsoft Intune](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune).



<!--HONumber=Aug16_HO4-->


