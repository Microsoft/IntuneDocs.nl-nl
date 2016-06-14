---
# required metadata

title: Veelgestelde vragen | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a8126cca-9ec4-454b-a20b-dc1bb6797327

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Veelgestelde vragen over Microsoft Intune
In dit artikel worden enkele veelgestelde vragen over Intune beantwoord. Als u hier geen antwoord op uw vraag vindt, [laat het ons dan weten](https://microsoftintune.uservoice.com/)..

## Algemene problemen

-   **Hoe weet ik wanneer de Intune-service is bijgewerkt?**

    Meld u aan bij uw account op manage.microsoft.com. Selecteer **Servicestatus weergeven** in Overzicht beheer. Hier worden de locatie van uw tenant en de onderhoudsplanning weergegeven. Lees meer informatie over de service-updates in het artikel [Wat is er nieuw?](/intune/deploy-use/whats-new-in-microsoft-intune)

-   **Als een gebruiker de naam van een apparaat wijzigt in de bedrijfsportal-app, verandert de naam dan ook in Intune of Configuration Manager?**

    Nee, de naamswijziging dient alleen voor het gemak van de gebruiker.

-   **Is er een Hulp op afstand-functionaliteit voor mobiele apparaten in Intune?**

    Nee, die is er niet. Apps van derden, zoals [Bomgar](http://www.bomgar.com/) en [TeamViewer](https://www.teamviewer.com/), kunnen handig zijn.

## Accounts

-   **Als ik de evaluatie van Intune start en een nieuwe tenant voor de evaluatieversie maak, kan ik Office 365 dan met dezelfde tenant aan de evaluatie toevoegen?**

    Ja. Meld u via uw bestaande Intune-tenant/-abonnement aan met een global admin-account, bijvoorbeeld *globaladmin@&lt;company&gt;.onmicrosoft.com*..

-   **Als ik MDM-instantie aan Intune toewijs tijdens een proefabonnement toewijzen, is het dan moeilijker om over te schakelen naar de service van een ander bedrijf als ik van gedachten verander over Intune?**

    Hoewel we ons moeilijk kunnen voorstellen dat Intune u niet bevalt, heeft uw keuze voor de MDM-instantie geen invloed op de mogelijkheid om over te stappen op een andere service. Dit gaat specifiek over kiezen voor Intune of Intune met System Center Configuration Manager.

-   **Kan ik mijn bestaande Office 365-domeinnaam voor mijn toekomstige Intune-account gebruiken?**

    Ja, als u zich met de organisatie-ID die is gekoppeld aan uw bestaande Office 365-tenant en gecontroleerde domein, aanmeldt wanneer u de desbetreffende proefversie van Intune maakt of uw licenties activeert.

    Intune gebruikt vervolgens hetzelfde domein/dezelfde gebruikers/enzovoort als in uw Office 365-account. Houd er rekening mee dat elke Office 365-gebruiker met behulp van een Intune-licentie moet worden ingeschakeld als Intune-gebruiker. Dit is de taak van de hoofdbeheerder die de tenant beheert.

## Inschrijving

-   **Waar kunnen mijn gebruikers lezen hoe ze hun apparaten kunnen inschrijven?**

    U kunt de informatie uit de [Inschrijvingsinstructies voor Intune-IT-beheerders](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) gebruiken of aanpassen..

-   **Hoe kan ik problemen met apparaatinschrijving oplossen?**

    Manieren om algemene inschrijvingsproblemen op te lossen, worden beschreven in [Problemen bij de apparaatinschrijving in Intune oplossen](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune)..

-   **Hoe kan ik inschrijvingslogboeken verzamelen als een gebruiker een inschrijvingsprobleem heeft?**

    Volg [deze instructies](http://www.microsoft.com/en-us/download/46391)..

## Beheer van mobiele apparaten

-   **Algemeen beheer mobiele apparaten**

    -   **Kan Intune detecteren of een apparaat is opengebroken?**

        Ja, voor sommige besturingssystemen. Zie [Een nalevingsbeleid maken voor apparaten](/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune.md) voor meer informatie over het beheren van apparaten die zijn opengebroken..

    -   **Kan ik bedrijfsgegevens selectief van een apparaat wissen?**

        Ja. Zie [Help uw gegevens beschermen met wissen op afstand, vergrendelen op afstand of opnieuw instellen van wachtwoordcode](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune.md) voor meer informatie over selectief wissen..

    -   **Is er een manier om bepaalde websites op de browser van een mobiel apparaat te blokkeren via Intune?**

        Niet met de eigen browser van een platform. U kunt URL's echter toestaan of blokkeren wanneer u de door Intune beheerde webbrowser hebt geïmplementeerd op iOS- en Android-apparaten. Zie [Internettoegang beheren met beleid voor beheerde browsers](/intune/Deploy-Use/Manage-Internet-access-using-managed-browser-policies-with-Microsoft-Intune.md) voor meer informatie..

    -   **Kunnen we verhinderen dat een gebruiker een app verwijdert?**

        Meestal niet. Op een iOS-apparaat onder supervisie kunt u echter wel voorkomen dat een gebruiker een app verwijdert die werd gedistribueerd met behulp van Apple Configurator. 

    -   **Is er een manier voor het beheren van het gebruik van mobiele gegevens?**

        Niet rechtstreeks, maar u kunt ervoor zorgen dat Wi-Fi de voorkeursmethode voor verbinding is, door Wi-Fi-profielen naar de apparaten te pushen, zoals omschreven in [Gebruikers helpen verbinding te maken met bedrijfsnetwerken via Wi-Fi-profielen](/intune/Deploy-Use/wi-fi-connections-in-microsoft-intune.md). Sommige platformen (zoals iOS en Android KNOX) bieden ook de mogelijkheid om instellingen zoals spraak en gegevensroaming te beheren.

    -   **Is er een manier om te voorkomen dat een gebruiker de inschrijving van een apparaat ongedaan maakt? Stel dat het een apparaat betreft dat bedrijfseigendom is?**

        In het algemeen niet. Met aangepaste instellingen voor Windows Phone kunt u inschrijving van gebruikers echter wel voorkomen op Windows Phone 8.1. Voor IOS-apparaten die onder supervisie staan en zijn geregistreerd in het Device Enrollment Program (DEP) van Apple is het bovendien mogelijk om te voorkomen dat een gebruiker de inschrijving van een apparaat ongedaan maakt.

    -   **Kan ik van gekozen MDM-instantie verwisselen?**

        In sommige gevallen kunt u van MDM-instantie verwisselen. Neem hiervoor contact op met de ondersteuning, zoals beschreven in [Ondersteuning voor Microsoft Intune krijgen](/intune/Troubleshoot/How-to-get-support-for-Microsoft-Intune.md). In de volgende tabel wordt beschreven welke wijzigingen mogelijk zijn. Wanneer de MDM-instantie wordt gewijzigd, moeten apparaten opnieuw worden ingeschreven.

        ||**Naar:** Intune!**Naar:** O365|**Naar:** Configuration Manager met Intune|
        |**Van:** Intune| |Ja&#42;|Ja|
        |**Van:** O365||Ja&#42;||Ja|
        |**Van:** Configuration Manager met Intune|Ja|Ja| |
        
        &#42;MDM-instanties van O365 en Intune kunnen naast elkaar bestaan. U hoeft mobiele apparaten dus niet opnieuw in te schrijven.



-   **Windows**

    -   **Kan ik Windows Store-apps sideloaden?**

        Openbare apps kunnen niet extern worden geladen. U kunt de XAP downloaden, maar u kunt deze niet uploaden naar Intune omdat het een openbare XAP betreft die is versleuteld en ondertekend met het certificaat voor codeondertekening van de ontwikkelaar. U kunt alleen apps sideloaden die u zelf hebt ontwikkeld en met uw eigen certificaat voor codeondertekening hebt ondertekend.

    -   **Moet de gebruiker over een Microsoft-account beschikken voor Windows Phone Store-apps die worden gedistribueerd via de bedrijfsportal?**

        Ja, de eindgebruiker heeft een Microsoft-account nodig om de apps te verkrijgen. Uitzondering hierop zijn sideloaded, persoonlijke LOB-apps, die zonder Microsoft-account op een apparaat kunnen worden geïmplementeerd.

    -   **Is een Microsoft-account vereist op een Windows Phone 8.1-apparaat om dit te beheren met Intune?**

        Nee. Een Microsoft-account is echter wel vereist voor het installeren van de meeste apps uit de openbare store.

        **Waarom vereist Windows Phone een Symantec-certificaat voor het beheer?**
        Windows Phone bepaalt hoe u apps kunt installeren. Elke gebruiker met een Microsoft-account kan apps uit de Windows Phone Store installeren of bedrijven kunnen hun intern ontwikkelde Line-of-Business-apps (LOB) installeren of sideloaden via een speciaal proces dat wordt beschreven in de Windows Phone-documentatie. Wanneer u LOB-apps installeert, vertrouwen Windows Phone-toestellen slechts één speciaal soort certificaat dat wordt uitgegeven door Symantec. U kunt geen ander commercieel of particulier gegenereerd certificaat gebruiken. Deze vereiste geldt voor alle beheeroplossingen voor mobiele apparaten, niet alleen voor Intune.

        Het Symantec-certificaat maakt een inschrijvingstoken voor toepassingen (AET). De AET kan op een apparaat worden geïnstalleerd wanneer het apparaat wordt ingeschreven voor beheer van mobiele apparaten, maar kan worden geïnstalleerd vanaf een veilige website of vanuit een e-mailbijlage. Beheerders moeten elke LOB-app met het Symantec-certificaat ondertekenen met de hulpprogramma's die beschikbaar zijn in de [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=268439). Wanneer gebruikers LOB-apps proberen te installeren, vergelijkt het Windows Phone-besturingssysteem de handtekening in de AET met de handtekening in de app. Als de handtekeningen overeenkomen, kan de installatie doorgaan. Als de AET niet kan worden geverifieerd, mislukt de installatie. Er zijn diverse redenen waarom de AET niet kan worden geverifieerd:

        -   De AET is nooit op het apparaat geïnstalleerd

        -   De AET is verlopen

        -   De AET is niet gemaakt met het Symantec-certificaat dat is gebruikt om de app te ondertekenen

        Windows Phone vereist niet dat de AET aanwezig is tijdens de inschrijving in Beheer van mobiele apparaten. Vóór de release van november 2014 vereiste Intune de AET en een ondertekend ssp.xap echter omdat de AET en ssp.xap alleen konden worden geïnstalleerd tijdens de inschrijving.

    **Hoe wordt de AET gemaakt voor Intune-gebruikers?**
  Wanneer beheerders het PFX-bestand voor hun Symantec-certificaat uploaden, wordt de AET door Intune automatisch gemaakt en geïmplementeerd op ingeschreven mobiele apparaten met Windows Phone. Intune-beheerders hoeven het AET Generator-hulpprogramma in de Windows Phone SDK Intune niet te gebruiken.

      > [!IMPORTANT]
        > Intune biedt geen ondersteuning voor het handmatig maken en out-of-band implementeren van de AET.

    **Wat is er veranderd zodat de vereiste voor het Symantec-certificaat is afgezwakt?**
       Voor de release van november 2014 zijn wijzigingen aangebracht in Intune zodat nu ook scenario's worden toegestaan waarin bedrijven geen Symantec-certificaat hebben.

       -   De bedrijfsportal voor Windows Phone 8.1 kan worden geïnstalleerd uit de Store en hoeft dus niet te worden ondertekend met een Symantec-certificaat en te worden gevalideerd met een AET. De app wordt al gevalideerd tijdens het publicatieproces voor de Store.

        -   Windows Phone 8.1-apparaten kunnen worden ingeschreven ongeacht of de telefoon de AET bevat. Als een AET beschikbaar is, wordt deze geïnstalleerd de eerste keer dat het apparaat wordt gesynchroniseerd met Intune. Als er geen AET is, kan het apparaat toch worden beheerd door Intune. Gebruikers kunnen de bedrijfsportal installeren via de Store en de meeste functies van de bedrijfsportal gebruiken zonder dat ze een Symantec-certificaat hebben om apps te ondertekenen.

        Er zijn geen wijzigingen in de vereiste voor het Symantec-certificaat op Windows Phone 8-apparaten. Op Windows Phone 8-apparaten moeten de ondertekende ssp.xap en de AET aanwezig zijn tijdens de registratie, anders kunnen deze apparaten niet worden ingeschreven.

        **Welke functionaliteit wordt ondersteund als een Windows Phone 8.1-apparaat wordt ingeschreven, maar er geen Symantec-certificaat is?**
        Als een Windows Phone 8.1-apparaat wordt ingeschreven, terwijl er geen Symantec-certificaat is, kunt u:

        -   Beleid maken en toepassen op het apparaat

        -   Contactgegevens voor de IT-afdeling configureren voor weergave in de bedrijfsportal

        -   Dieptekoppelingen naar de Store maken en deze implementeren in de bedrijfsportal

        -   Koppelingen naar webpagina's maken en deze implementeren in de bedrijfsportal

        -   Voorwaarden en bepalingen maken die door gebruikers moeten worden geaccepteerd voordat ze de bedrijfsportal kunnen gebruiken

        Zonder Symantec-certificaat is het alleen niet mogelijk om LOB-apps te implementeren.

        > [!IMPORTANT]
        > De Intune-software-uitgever controleert tijdens het uploaden niet of apps zijn ondertekend. Als u niet-ondertekende apps implementeert, mislukken deze apps wanneer gebruikers ze proberen te installeren.

        **Wat kunnen gebruikers doen als ze over de bedrijfsportal beschikbaar, maar geen Symantec-certificaat hebben?**
        Windows Phone 8.1-apparaten hoeven niet te worden ingeschreven voordat gebruikers de bedrijfsportal installeren via de Store. Als het apparaat niet is ingeschreven, wordt aan de gebruikers gevraagd om het in te schrijven. Door in de bedrijfsportal op de prompt te tikken, kunnen gebruikers rechtstreeks naar **Instellingen / Werkplek** gaan, waar ze hun apparaten kunnen inschrijven.

        Ook zonder het apparaat in te schrijven, kunnen gebruikers de volgende acties uitvoeren als de bedrijfsportal is geïnstalleerd via de Store:

        -   Bepalingen en voorwaarden accepteren of weigeren die zijn geconfigureerd door de beheerder. Als gebruikers de voorwaarden en bepalingen weigeren, wordt de bedrijfsportal gesloten.

        -   De contactgegevens voor de IT-afdeling weergeven.

        -   Ingeschreven apparaten, zoals iOS-, Android- en Windows-apparaten, weergeven.

        -   Dieptekoppelingen naar apps in de Store gebruiken.

        -   Webkoppelingen gebruiken om webpagina's te openen.

        Nadat het apparaat is ingeschreven, kunnen gebruikers het apparaat bekijken in de lijst **Mijn apparaten** . Nadat het apparaat is ingeschreven, is het onderworpen aan het geïmplementeerde Intune-beleid. Apparaten moeten zijn ingeschreven om de AET te ontvangen en LOB-apps te installeren. Een niet-ingeschreven apparaat dat probeert een LOB-app te installeren, wordt omgeleid om te worden ingeschreven.

        Wanneer het bedrijf geen Symantec-certificaat heeft, kunnen gebruikers LOB-apps alleen installeren als deze zijn geïmplementeerd door de beheerder.

        **Ons bedrijf heeft al een certificaat en heeft al Windows Phone 8.1-apparaten ingeschreven. Moet ik iets anders doen nu de bedrijfsportal beschikbaar is in de Store?**
        De huidige ssp.xap van het downloadcentrum werkt nog altijd op Windows Phone 8.1-apparaten. U kunt gebruikers blijven doorsturen om hun apparaat in te schrijven en de bedrijfsportal op te halen tijdens de installatie.

        **Wat zijn de voor- en nadelen van het ophalen van de bedrijfsportal uit de Store?**
        Voordelen:

        -   Gebruikers krijgen dieptekoppelingen en webkoppelingen, ook als het Windows Phone 8.1-apparaat niet is ingeschreven.

        -   Wanneer de bedrijfsportal door Microsoft wordt bijgewerkt, wordt de app uit de Store automatisch bijgewerkt zonder dat u de ssp.xap opnieuw hoeft te downloaden, te ondertekenen en te implementeren.

        -   Documentatie voor gebruikers van Windows Phone 8.1, iOS, Android en Windows is consistent: 'Ga naar de Store en installeer de bedrijfsportal.'

        -   Gebruikers zien hoe de app wordt geïnstalleerd en ontvangen instructies om de app in te schrijven wanneer deze wordt geopend.

        Nadelen:

        -   Gebruikers zien een selectievakje om een**bedrijfshub**te installeren, maar ze worden niet omgeleid naar de bedrijfsportal in de lijst met apps op het apparaat.

        -   Gebruikers hoeven geen aangepaste voorwaarden en bepalingen te accepteren totdat ze de bedrijfsportal openen.

        In de volgende situaties kunt u gebruikers blijven doorsturen om hun apparaat in te schrijven en ssp.xap te installeren tijdens de inschrijving:

        -   Als het bedrijf toegang tot de Store blokkeert op mobiele apparaten met Windows Phone, moeten gebruikers ssp.xap installeren tijdens de inschrijving.

        -   Als voor gebruikers geen Microsoft-account is geconfigureerd op hun mobiele apparaat met Windows Phone, kunnen ze de bedrijfsportal niet installeren via de Store.

        -   Als de bestaande documentatie voor Windows Phone-inschrijving gebruikers eerst vraagt om naar Instellingen en Werkplek te gaan, kan het even duren om de documenten bij te werken en gebruikers om te leiden naar de Store.

        **Wat is het verschil tussen ssp.xap in het downloadcentrum en de app in de Store?**

        -   De bedrijfsportal in de Store hoeft niet te worden ondertekend met een Symantec-certificaat voordat de app kan worden geïnstalleerd.

        -   De bedrijfsportal in de Store biedt de gebruiker de voorwaarden en bepalingen aan, maar ssp.xap in het downloadcentrum doet dit niet.

        -   De bedrijfsportal in de Store is een .appx in plaats van een .xap.

        **Kan ik het bedrijfsportalbestand ophalen en dit doorgeven aan mijn gebruikers in plaats van ze naar de Store te sturen?**
        Ja. De bedrijfsportal-app kan voor de volgende besturingssystemen worden gedownload uit het Downloadcentrum:

        -   Windows Phone 8.1: [http://go.microsoft.com/fwlink/?LinkId=615799](http://go.microsoft.com/fwlink/?LinkId=615799)

        -   Windows Phone 8.0: [http://go.microsoft.com/fwlink/?LinkId=268440](http://go.microsoft.com/fwlink/?LinkId=268440)

        -   Windows 8.1: [http://go.microsoft.com/fwlink/?LinkId=615800](http://go.microsoft.com/fwlink/?LinkId=615800)

        **Kunnen bedrijven nog steeds het ondersteuningsprogramma voor Windows Intune-proefbeheer van Windows Phone gebruiken als ze geen Symantec-certificaat hebben en kunnen hun gebruikers de bedrijfsportal nog steeds installeren via de Store?**
        Ja. Als u het concept wilt testen dat de installatie van LOB-apps omvat, werkt het proefbeheerprogramma met de Store-versie van de bedrijfsportal. Omdat de AET van het Symantec-certificaat niet langer vereist is voor de inschrijving van Windows Phone 8.1-apparaten, kunnen bedrijven de installatie van apps testen met dieptekoppelingen naar apps in de Store.

        Het ondersteuningsprogramma voor Windows Intune-proefbeheer van Windows Phone is alleen voor proefabonnementen van Intune.

        > [!IMPORTANT]
        > Gebruik alleen het proefbeheerprogramma alleen voor testdoeleinden. Apparaten die zijn ingeschreven met de AET van het proefbeheerprogramma, moeten worden uitgeschreven en vervolgens weer worden ingeschreven als het Symantec-certificaat voor het proefbeheerprogramma niet langer beschikbaar is, of als het bedrijf een eigen Symantec-certificaat heeft gekocht om apps te ondertekenen.

        **Kunnen bedrijven starten zonder Symantec-certificaat en er later een toevoegen, zelfs nadat Windows Phone 8.1-apparaten zijn ingeschreven?**
        Ja. Ook als Windows Phone 8.1-apparaten al zijn ingeschreven, kunt u een Symantec-certificaat kopen, ssp.xap ondertekenen en ssp.xap en het PFX-bestand uploaden. Vervolgens wordt de AET door Intune gegenereerd. Windows Phone 8.1-apparaten ontvangen de AET bij de volgende synchronisatie (kan tot acht uur duren). Wacht ten minste acht uur nadat het XAP- en PFX-bestand zijn geüpload, voordat u de Line-of-Business-apps implementeert.


-   **Android**

    -   **Hoe lang duurt het om een Android-apparaat te versleutelen?**

        Dit is vooral afhankelijk van de snelheid van de processor van het apparaat en de totale en gebruikte hoeveelheid geheugen. Dit is geen functie van Intune.

-   **iOS**

    -   **Moet op het apparaat een Apple-id worden opgegeven om door te gaan met installeren als bij het implementeren van iOS-apps met Intune het IPA- en het manifestbestand van de toepassing zijn geüpload?**

        Nee. Wanneer Intune de bits biedt (IPA is geüpload naar Intune), zijn de toepassingen sideloaded en is geen Apple-id vereist.

    -   **Is er een manier om de installatie van apps in iOS in te schakelen zonder toegang tot de Apple Store toe te staan?**

        Nee, maar u kunt wel de App Store inschakelen en toegestane en geblokkeerde apps in iOS gebruiken om te controleren wat gebruikers doen. Sideloaded LOB-apps hebben geen toegang tot de Apple App Store nodig.

    -   **Moet de eindgebruiker over een iTunes-account beschikken voor Apple Store-apps die worden gedistribueerd via de bedrijfsportal?**

        Ja, de eindgebruiker heeft een iTunes-account nodig om de apps te kunnen downloaden.

    -   **Kan ik de App Store blokkeren?**

        Ja, dat is mogelijk. Hierdoor worden echter alle installaties en updates van apps uit de App Store geblokkeerd, niet alleen de installaties en updates die door de gebruiker werden gestart. Dit betekent dat apps uit de openbare app store die u via Intune implementeert, ook mislukken.

## App-implementatie

-   **Hoe kan ik een aanbevolen app toevoegen?**

    In Intune worden dit 'aanbevolen apps' genoemd. Deze worden beschreven in [Apps in Microsoft Intune implementeren](/Intune/Deploy-Use/deploy-apps-in-microsoft-intune.md)..

-   **Kan ik extra cloudopslag krijgen voor apps die ik wil implementeren?**

    Ja. Meer informatie hierover vindt u in [Apps implementeren](/Intune/Deploy-Use/deploy-apps.md), in de sectie *Vereisten voor cloudopslag*..

## Beveiliging

-   **Kan BitLocker worden afgedwongen door Intune?**

    Met de OMA-DM-agent in Windows 8.1/RT kunt u de versleutelingsstatus lezen (get). U kunt deze niet instellen. Dit geldt voor Intune en voor andere beheerservices voor mobiele apparaten.

-   **Als ik een Windows 8-tablet versleutel met BitLocker, kan ik dan het wissen van het volledige apparaat afdwingen als de aanmeldingspoging van een gebruiker meerdere keren opeenvolgend mislukt?**

    Er is geen optie voor volledig wissen op Windows 8.1/RT-apparaten voor beheerservices van mobiele apparaten, inclusief Intune. Intune biedt selectief wissen voor deze apparaten. Zie [Apps en gegevens beschermen met Microsoft Intune](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md) voor meer informatie over wissen/selectief wissen in Intune..

## Bedrijfsportal

-   **Kan ik mijn bedrijfsportal aanpassen?**

    Ja. Voor deze instellingen gaat u in de Intune-beheerconsole naar **Beheer&gt;Bedrijfsportal**.

## Microsoft Intune met Configuration Manager

-   **Wanneer ik Configuration Manager met Intune gebruik, waar beheer ik mijn apparaten?**

    Beheer al uw apparaten via de Configuration Manager-console, ook al worden apparaten die met de Intune-agent zijn geïnstalleerd weergegeven in de Intune-console. Mobiele apparaten worden niet weergegeven in de Intune-console.

-   **Kan ik selectief wissen op apparaten?**

    Als u System Center 2012 R2 Configuration Manager of later samen met Intune gebruikt, kunt u selectief wissen om bedrijfsgegevens te verwijderen. Zie [Apps en gegevens beschermen met Microsoft Intune](/intune/Deploy-Use/protect-apps-and-data-with-microsoft-intune.md) voor meer informatie..

-   **Als ik Configuration Manager met Intune gebruik, kan ik dan nog steeds de Intune-beheerportal gebruiken?**

    Dat kan, maar alleen pc's waarop de Intune-agent is geïnstalleerd, kunnen via deze portal worden beheerd. De portal biedt ook andere nuttige informatie met betrekking tot waarschuwingen over de service, de status van de service, enzovoort. Instellingen voor apparaatbeheer op de portal zijn echter niet van toepassing op ingeschreven apparaten.



<!--HONumber=May16_HO1-->


