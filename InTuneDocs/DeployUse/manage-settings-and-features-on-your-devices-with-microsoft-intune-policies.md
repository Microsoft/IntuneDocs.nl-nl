---
# required metadata

title: Instellingen en functies op uw apparaten beheren met beleid | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid
Microsoft Intune-**beleid** bestaat uit groepen instellingen waarmee functies op mobiele apparaten en computers worden beheerd. U maakt beleidsregels met behulp van sjablonen die aanbevolen of aangepaste instellingen bevatten, en u implementeert ze vervolgens op apparaat- of gebruikersgroepen.

## Welke typen beleid kunt u gebruiken?

Intune-beleid is ingedeeld in de volgende categorieën. De categorie die u gebruikt, is van invloed op hoe u het beleid maakt en implementeert.


- **Configuratiebeleid:** dit wordt vaak gebruikt om beveiligingsinstellingen en -functies op uw apparaten te beheren. Gebruik de informatie in dit onderwerp voor meer informatie over het maken en implementeren van dit beleid en bekijk de beschikbare instellingen.
- **Nalevingsbeleid voor apparaten:** dit definieert de regels en instellingen waaraan een apparaat moet voldoen om ook te voldoen aan het beleid voor voorwaardelijke toegang. U kunt nalevingsbeleid ook gebruiken om onafhankelijk van voorwaardelijke toegang te controleren of en ervoor te zorgen dat apparaten aan het beleid voldoen.
Zie [Nalevingsbeleid voor apparaten in Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md) voor meer informatie.
- **Beleid voor voorwaardelijke toegang:** dit beleid helpt u bij het beveiligen van e-mail en andere services, afhankelijk van de door u opgegeven voorwaarden.
Zie [De toegang tot e-mail en O365-services beperken met Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) voor meer informatie.
- **Registratiebeleid voor bedrijfsapparaten:** zie [iOS- en Mac-beheer instellen met Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md) voor meer informatie over het registratiebeleid voor bedrijfsapparaten.
- **Brontoegangsbeleid:** deze groep beleidsregels werkt samen om uw gebruikers de gelegenheid te bieden om toegang te krijgen tot de bestanden en bronnen die ze nodig hebben om hun werk te doen, waar ze ook zijn.
Zie [Toegang tot bedrijfsbronnen inschakelen met Microsoft Intune](enable-access-to-company-resources-with-microsoft-intune.md) voor meer informatie.


Zie [Documentatie voor Microsoft Intune-beleid](microsoft-intune-policy-reference.md) voor een volledige lijst met Intune-beleidsmogelijkheden.




## Een configuratiebeleid maken

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) op **Beleid** &gt; **Configuratiebeleid** &gt; **Toevoegen**.

2.  Kies het gewenste beleid. Kies de aanbevolen instellingen voor het beleid (indien beschikbaar; u kunt deze instellingen later wijzigen) of kies ervoor een aangepast beleid te maken met uw eigen instellingen.

    > [!TIP] Zie [Documentatie voor Microsoft Intune-beleid](microsoft-intune-policy-reference.md) voor meer informatie over het kiezen van het juiste beleid.

3.  Als u klaar bent, klikt u op **Beleid maken**.

4.  Configureer in het scherm **Beleid maken** een naam en optionele beschrijving voor het beleid.

5.  Configureer de vereiste beleidsinstellingen en klik vervolgens op **Beleid opslaan**.

    Als u hulp nodig hebt met de beleidsinstellingen, kiest u uw beleidstype in de volgende lijst:

    - [Instellingen voor iOS-apparaten](ios-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor Android-apparaten](android-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor Windows 8- en Windows 8.1-apparaten](windows-configuration-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor Windows Phone 8.1-apparaten](windows-phone-8-1-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor Windows 10 Desktop- en mobiele apparaten](windows-10-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor Windows Team-apparaten](windows-team-configuration-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor upgrades van de Windows-editie](edition-upgrade-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor Mac OS X-apparaten](mac-os-x-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor Exchange Active Sync](exchange-activesync-policy-settings-in-microsoft-intune.md)
    - [Instellingen voor het beleid voor voorwaarden](terms-and-condition-policy-settings-in-microsoft-intune.md)
    - [Algemene instellingen voor mobiele apparaten (verouderd)](mobile-device-security-policy-settings-in-microsoft-intune.md)

4.  Klik in het bevestigingsdialoogvenster op **Ja** om het beleid nu te implementeren of klik op **Nee** om het beleid te maken zonder het te implementeren.

U kunt het nieuwe beleid bekijken en bewerken door te bladeren door de secties voor elk beleidstype in de werkruimte **Beleid** .

Wanneer u een beleid maakt dat gebruikmaakt van de aanbevolen instellingen, is de naam van het nieuwe beleid een combinatie van de sjabloonnaam, de datum en de tijd. Wanneer u het beleid bewerkt, wordt de naam bijgewerkt met de tijd en de datum van de bewerking.

Nu u een beleid hebt gemaakt, wilt u dit waarschijnlijk implementeren op een of meer groepen gebruikers of apparaten.

> [!TIP]
> U kunt niet alle beleidstypen implementeren. Het beleid voor het beheren van mobiele toepassingen bijvoorbeeld wordt niet geïmplementeerd. Dit beleidstype wordt in plaats daarvan gekoppeld aan een app, dat u vervolgens implementeert.

## Een configuratiebeleid implementeren

1.  Selecteer het beleid dat u wilt implementeren in de werkruimte **Beleid** en klik vervolgens op **Implementatie beheren**.

2.  In het dialoogvenster **Implementatie beheren** :

    -   **Het beleid implementeren**: selecteer een of meer groepen waarvoor u het beleid wilt implementeren, en klik vervolgens op **Toevoegen** &gt; **OK**.

    -   **Het dialoogvenster sluiten zonder het beleid te implementeren**: klik op **Annuleren**.

Wanneer u een geïmplementeerde beleid selecteert, kunt u meer informatie over de implementatie weergeven onder in de lijst met beleidsregels.

## Beleid beheren

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/)op **Beleid**en selecteer het beleid dat u wilt beheren.

2.  Selecteer een van de volgende acties:

- **Bewerken**: hiermee opent u de eigenschappen voor het geselecteerde beleid zodat u wijzigingen kunt aanbrengen.
- **Verwijderen**: hiermee verwijdert u het geselecteerde beleid.<br>Wanneer u een beleid verwijdert, wordt dit verwijderd uit alle groepen waarop het was geïmplementeerd.
- **Implementatie beheren**: selecteer de groep waarvoor u het beleid wilt implementeren, en klik op **Toevoegen**.

## Taken voor Intune-beleid

### Het beleid vernieuwen op een apparaat zodat het actueel is (alleen van toepassing op Windows-pc's met de Intune-clientsoftware)

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/)op **Groepen**en selecteer vervolgens een apparaatgroep.

2.  Selecteer de apparaten waarop u het beleid wilt vernieuwen, en klik vervolgens op **Externe taken** &gt; **Beleid vernieuwen**.

3.  Klik op **Externe taken** in de rechterbenedenhoek van de Intune-beheerconsole om de taakstatus te controleren.

## Veelgestelde vragen over het Intune-beleid

### Hoe lang duurt het voor mobiele apparaten beleid of apps hebben ontvangen nadat deze zijn geïmplementeerd?
Wanneer er beleid of een app wordt geïmplementeerd, informeert Intune het apparaat onmiddellijk dat het bij de Intune-service moet worden ingecheckt. Dit vindt meestal binnen 5 minuten plaats.

Als een apparaat geen controle uitvoert of het beleid niet kan worden opgehaald nadat de eerste melding daarover is verzonden, vinden er nog 3 pogingen plaats.  Als het apparaat offline is (bijvoorbeeld omdat het is uitgeschakeld of niet is verbonden met een netwerk), kan het geen meldingen ontvangen.

In dat geval ontvangt het apparaat het beleid bij de volgende keer dat het volgens de planning incheckt bij de Intune-service, en wel als volgt:

- iOS: om de 6 uur
- Android: om de 8 uur
- Windows Phone: om de 8 uur
- Ingeschreven Windows RT-apparaten: elke 24 uur
- Windows 8.1- en Windows 10-computers die als apparaten zijn ingeschreven: om de 8 uur

Als het apparaat zojuist is ingeschreven, is de controlefrequentie hoger, en wel als volgt:

- iOS: om de 15 minuten gedurende 6 uur en daarna om de 6 uur
- Android: om de 3 minuten gedurende 15 minuten en daarna om de 15 minuten gedurende 2 uur en vervolgens om de 8 uur
- Windows Phone: om de 5 minuten gedurende 15 minuten en daarna om de 15 minuten gedurende 2 uur en vervolgens om de 8 uur
- Windows-computers die als apparaten zijn ingeschreven: om de 3 minuten gedurende 30 minuten en vervolgens om de 24 uur

Gebruikers kunnen ook de bedrijfsportal-app starten en het apparaat onmiddellijk synchroniseren om op elk gewenst moment op aanwezig beleid te controleren.

### Welke acties zorgen ervoor dat Intune onmiddellijk een melding naar een apparaat verzendt?
Apparaten worden bij Intune ingecheckt wanneer ze een melding ontvangen waarin staat dat ze moeten worden ingecheckt of bij het inchecken volgens de planning zoals weergegeven in de bovenstaande tabellen.  Wanneer u een actie specifiek op een apparaat of gebruiker richt, zoals wissen, vergrendelen, wachtwoord opnieuw instellen, app implementeren, profiel implementeren (Wi-Fi, VPN, e-mail enzovoort) of beleid implementeren, zal Intune onmiddellijk het apparaat proberen te informeren dat het moet worden ingecheckt bij de Intune-service om deze updates te ontvangen.

Andere wijzigingen zoals het wijzigen van de contactgegevens in de bedrijfsportal zorgen niet voor een onmiddellijke melding aan apparaten.

> [!TIP]
> Wanneer een beleid met instellingen wordt geïmplementeerd op een Android-apparaat, krijgt de gebruiker een melding dat deze actie moet ondernemen om te voldoen aan het beleid. De nieuwe instellingen gaan pas van kracht als de gebruiker deze actie heeft ondernomen of het apparaat opnieuw is gestart.

### Als er meerdere beleidsregels worden geïmplementeerd voor dezelfde gebruiker of hetzelfde apparaat, hoe weet ik dan welke instellingen worden toegepast?
Het is belangrijk te weten dat wanneer er twee of meer sets beleidsregels naar dezelfde gebruiker of hetzelfde apparaat worden geïmplementeerd de beoordeling van welke instelling wordt toegepast wordt uitgevoerd op het niveau van de individuele instelling.

-   Nalevingsbeleidsinstellingen hebben altijd voorrang op configuratiebeleidsinstellingen

-   De strengste nalevingsbeleidsinstelling wordt toegepast als dit beleid wordt vergeleken met dezelfde instelling in een ander nalevingsbeleid

-   De strengste configuratiebeleidsinstelling wordt toegepast als dit beleid wordt vergeleken met dezelfde instelling in een ander configuratiebeleid

### Wat gebeurt er wanneer MAM-beleidsregels met elkaar conflicteren? Welke regel wordt toegepast op de app?
Conflictwaarden zijn de meest beperkende instellingen die beschikbaar zijn in MAM-beleid, uitgezonderd cijferinvoervelden (zoals aantal pincodepogingen voorafgaand aan opnieuw instellen).  De cijferinvoervelden worden op hetzelfde ingesteld als de waarden, alsof u een MAM-beleid maakt in de console met de aanbevolen instellingenoptie.

Er treden conflicten op wanneer twee beleidsinstellingen hetzelfde zijn.  Bijvoorbeeld als u twee MAM-beleidsregels hebt geconfigureerd die identiek zijn met uitzondering van de instelling voor kopiëren en plakken.  In dit scenario wordt de instelling voor kopiëren en plakken ingesteld op de meest beperkende waarde, maar de overige instellingen worden toegepast zoals die zijn geconfigureerd.

Als er een beleid is geïmplementeerd voor de app en dat beleid is van kracht geworden, en er wordt vervolgens een tweede beleid geïmplementeerd, heeft het beleid dat als eerste is geïmplementeerd prioriteit en dit blijft toegepast, terwijl de tweede als conflicterend wordt beschouwd. Als ze echter allebei tegelijkertijd worden toegepast, wat betekent dat er geen voorafgaand beleid is, worden ze allebei als conflicterend beschouwd en alle eventueel conflicterende instellingen worden op de meest beperkende waarden ingesteld.

### Wat gebeurt er als aangepaste iOS-beleidsregels conflicteren?
Intune beoordeelt de nettolading van Apple-configuratiebestanden of aangepaste OMA-URI-beleid niet, maar fungeert alleen als bezorgingsmechanisme.

Zorg er daarom voor dat wanneer u een aangepast beleid implementeert dat de geconfigureerde instellingen niet conflicteren met het nalevingsbeleid, configuratiebeleid of ander aangepast beleid. Als er bij een aangepast beleid sprake is van conflicterende instellingen, worden instellingen in willekeurige volgorde toegepast.

### Wat gebeurt er wanneer een beleid wordt verwijderd of niet langer van toepassing is?
Wanneer u een beleid verwijdert of een apparaat verwijdert uit een groep waarop een beleid is geïmplementeerd, worden het beleid en de instellingen van het apparaat verwijderd, volgens de volgende tabellen:

#### Ingeschreven apparaten

- Wi-Fi-, VPN-, certificaat- en e-mailprofielen: deze profielen worden verwijderd van alle ondersteunde ingeschreven apparaten.
- Alle andere beleidstypen
    - **Windows- en Android-apparaten**: instellingen worden niet verwijderd van het apparaat.
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

- **Instellingen voor Endpoint Protection**: instellingen worden teruggezet naar de aanbevolen waarden. De enige uitzondering hierop is de instelling **Deelnemen aan Microsoft Active Protection Service** waarvoor de standaardwaarde **Nee**is. Zie [Help Windows-pc's beveiligen met Endpoint Protection voor Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) voor meer informatie.
- **Instellingen voor software-updates**: instellingen worden opnieuw ingesteld op de standaardstatus voor het besturingssysteem. Zie [Windows-pc's up-to-date houden met software-updates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) voor meer informatie.
- **Instellingen voor Microsoft Intune Center**: alle contactgegevens voor ondersteuning die door het beleid zijn geconfigureerd, worden verwijderd van computers.
- **Instellingen voor Windows Firewall**: instellingen worden opnieuw ingesteld op de standaardwaarde voor het computerbesturingssysteem. Zie [Help Windows-pc's beveiligen met Endpoint Protection voor Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) voor meer informatie.





<!--HONumber=May16_HO3-->


