---
# required metadata

title: Hoe werkt Azure RMS | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: ed6c964e-4701-4663-a816-7c48cbcaf619

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Hoe werkt Azure RMS Onderhuids

*Van toepassing op: Azure Rights Management, Office 365*

Een van de belangrijke dingen die u moet weten om te begrijpen hoe Azure RMS werkt, is dat de Rights Management-service (en Microsoft) uw gegevens niet zien of opslaan als onderdeel van het gegevensbeveiligingsproces. Gegevens die u beveiligt, worden nooit verzonden naar of opgeslagen in Azure, tenzij u deze gegevens zelf expliciet opslaat in Azure of een andere cloudservice gebruikt waarmee gegevens worden opgeslagen in Azure. Azure RMS maakt alleen de gegevens in een document onleesbaar, behalve voor gemachtigde gebruikers en services:

-   De gegevens worden versleuteld op toepassingsniveau en het proces omvat een beleid dat geautoriseerd gebruik van dat document bepaalt.

-   Wanneer een beveiligd document wordt gebruikt door een geldige gebruiker of wordt verwerkt door een gemachtigde service, worden de gegevens in het document ontsleuteld en worden de rechten afgedwongen die zijn gedefinieerd in het beleid.

De volgende afbeelding bevat een overzicht, waarmee u kunt zien hoe dit proces werkt. Een document dat de geheime formule bevat, wordt beveiligd en vervolgens geopend door een geautoriseerde gebruiker of -service. Het document wordt beveiligd door een inhoudssleutel (de groene sleutel in deze afbeelding). Deze sleutel is voor elk document uniek en wordt geplaatst in bestands-header, waar deze wordt beveiligd door de basissleutel van uw RMS-tenant (de rode sleutel in deze afbeelding). Uw tenantsleutel kan worden gegenereerd en beheerd door Microsoft, maar u kunt ook uw eigen tenantsleutel genereren en beheren.

Gedurende het hele beveiligingsproces, waarbij Azure RMS versleutelt, ontsleutelt, goedkeurt en beperkingen afdwingt, wordt de geheime formule nooit wordt verzonden naar Azure.

![Hoe een bestand wordt beveiligd met Azure RMS](../media/AzRMS_SecretColaFormula_final.png)

Zie de sectie [Walkthrough over de werking van Azure RMS: eerste gebruik, inhoudsbeveiliging, inhoudverbruik](#walkthrough-of-how-azure-rms-works-first-use-content-protection-content-consumption) in dit artikel voor een gedetailleerde omschrijving van de bewerkingen.

Zie de volgende sectie voor technische gegevens over de algoritmen en sleutellengten die Azure RMS gebruikt.

## Cryptografische besturingselementen die worden gebruikt door Azure RMS: algoritmen en sleutellengten.
Zelfs als u niet hoeft te weten zelf hoe RMS werkt, wordt u mogelijk gevraagd over de cryptografische besturingselementen die worden gebruikt, om ervoor te zorgen dat de beveiliging voldoet aan de industrienorm.


|Cryptografische besturingselementen|Gebruik in Azure RMS|
|-|-|
|Algoritme: AES<br /><br />Sleutellengte: 128-bits en 256-bits [[1]](#footnote-1)|Documentatiebeveiliging|
|Algoritme: RSA<br /><br />Sleutellengte: 2048-bits|Sleutelbeveiliging|
|SHA-256|Certificaatondertekening|

###### Voetnoot 1 

De lengte 256-bits wordt gebruikt door de Rights Management-toepassing voor delen voor algemene beveiliging en systeemeigen beveiliging als het bestand de extensie .ppdf heeft of een beveiligd tekst- of afbeeldingsbestand (zoals .ptxt of .pjpg) is.

Hoe de cryptografische sleutels worden opgeslagen en beveiligd:

- Voor elk document of e-mailbericht dat wordt beveiligd door Azure RMS, maakt Azure RMS een enkele AES-sleutel (de 'inhoudssleutel'). Deze sleutel wordt in het document ingesloten en blijft behouden in alle versies van het document. 

- De inhoudssleutel wordt beschermd met de RSA-sleutel van de organisatie (de 'Azure RMS-tenantsleutel') als onderdeel van het beleid in het document. Het beleid wordt ook ondertekend door de auteur van het document. Deze tenantsleutel is gebruikelijk voor alle documenten en e-mails die voor de organisatie worden beveiligd door Azure RMS en deze sleutel kan alleen worden gewijzigd door een Azure RMS-beheerder als de organisatie een tenantsleutel die door de klant wordt beheerd (ook wel 'bring your own key', of BYOK). 

    Deze tenantsleutel wordt beveiligd in de onlineservices van Microsoft, in een uiterst gecontroleerde omgeving en met maximale bewaking. Wanneer u een klant-beheerde tenantsleutel (BYOK) gebruikt, wordt deze beveiliging verbeterd door het gebruik van een matrix geavanceerde Hardware Security Modules (HSM's) in elke Azure-regio, zonder dat de sleutels onder welke voorwaarde ook kunnen worden geëxtraheerd, geëxporteerd of gedeeld. Zie [Uw Azure Rights Management-tenantsleutel plannen en implementeren](../plan-design/plan-implement-tenant-key.md) voor meer informatie over de tenantsleutel en BYOK.

- Licenties en certificaten die worden verzonden naar een Windows-apparaat, worden beveiligd met de persoonlijke apparaatsleutel van de client, die wordt gemaakt wanneer een gebruiker op het apparaat voor de eerste keer Azure RMS gebruikt. Deze persoonlijke sleutel wordt op zijn beurt beveiligd met de DPAPI op de client, die deze geheime gegevens beveiligd met een sleutel die is afgeleid van het wachtwoord van de gebruiker. Op mobiele apparaten wordt de sleutel slechts eenmaal gebruikt. Omdat de sleutels niet worden opgeslagen op de clients, hoeven deze sleutels dus niet te worden beveiligd op het apparaat. 



## Walkthrough over de werking van Azure RMS: eerste gebruik, inhoudsbeveiliging, inhoudverbruik
Voor een gedetailleerder inzicht in de werking van Azure RMS, doorlopen we een typische stroom nadat de [Azure RMS-service is geactiveerd](../deploy-use/activate-service.md) en wanneer een gebruiker voor het eerst gebruikmaakt van RMS op een Windows-computer (een proces dat ook wel **initialisatie van de gebruikersomgeving** of opstarten wordt genoemd), **inhoud beveiligt** (een document of e-mailadres) en vervolgens inhoud **verbruikt** (opent en gebruikt) die is beveiligd door iemand anders.

Nadat de gebruikersomgeving is geïnitialiseerd, kan die gebruiker vervolgens documenten beveiligen of beveiligde documenten op die computer verbruiken.

> [!NOTE]
> Als deze gebruiker naar een andere Windows-computer verplaatst of een andere gebruiker deze dezelfde Windows-computer gebruikt, wordt het initialisatieproces herhaald.

### Initialisatie van de gebruikersomgeving
Voordat een gebruiker inhoud kan beveiligen of beveiligde inhoud op een Windows-computer kan verbruiken, moet de gebruikersomgeving worden voorbereid op het apparaat. Dit is een eenmalige proces en dat automatisch plaatsvindt zonder tussenkomst van de gebruiker wanneer een gebruiker inhoud beveiligt of beveiligde inhoud verbruikt:

![Activering van de RMS-client - stap 1](../media/AzRMS.png)

**Wat gebeurt er in stap 1**: de RMS-client op de computer maakt eerst verbinding met Azure RMS en verifieert de gebruiker met het Azure Active Directory-account.

Wanneer het gebruikersaccount met Azure Active Directory is gefedereerd, is deze verificatie automatisch en wordt de gebruiker niet gevraagd om referenties.|

![Activering van de RMS-client - stap 2](../media/AzRMS_useractivation2.png)

**Wat gebeurt er in stap 2**: nadat de gebruiker is geverifieerd, wordt de verbinding automatisch omgeleid naar de RMS-tenant van de organisatie. De tenant geeft certificaten uit waarmee de gebruiker wordt geverifieerd bij Azure RMS zodat deze beveiligde inhoud kan verbruiken en offline inhoud kan beveiligen.

Een kopie van het certificaat van de gebruiker wordt opgeslagen in Azure RMS, zodat de certificaten met dezelfde worden sleutels gemaakt als de gebruiker naar een ander apparaat verplaatst.

### Inhoudsbeveiliging.
Wanneer een gebruiker een document beveiligt, voert de RMS-client de volgende acties uit op een niet-beveiligd document:

![RMS-beveiliging voor documenten - stap 1](../media/AzRMS_documentprotection1.png)

**Wat gebeurt er in stap 1**: de RMS-client maakt een willekeurige sleutel voor de inhoud (de inhoudssleutel) en versleutelt het document met deze sleutel met het symmetrische versleutelingsalgoritme AES.

![RMS-beveiliging voor documenten - stap 2](../media/AzRMS_documentprotection2.png)

**Wat gebeurt er in stap 2**: de RMS-client maakt vervolgens een certificaat met een beleid voor het document, op basis van een sjabloon of door het opgeven van specifieke rechten voor het document. Dit beleid bevat de rechten voor verschillende gebruikers of groepen en andere beperkingen, zoals een vervaldatum.

De RMS-client gebruikt vervolgens de sleutel van de organisatie die is verkregen toen de gebruikersomgeving werd geïnitialiseerd, en gebruikt deze sleutel om het beleid en de symmetrische inhoudssleutel te versleutelen. De RMS-client ondertekent het beleid ook met het gebruikerscertificaat dat is verkregen toen de gebruikersomgeving werd geïnitialiseerd.|

![RMS-beveiliging voor documenten - stap 3](../media/AzRMS_documentprotection3.png)

**Wat gebeurt er in stap 3**: tot slot sluit de RMs-client het beleid in een bestand in met de hoofdtekst van het document dat eerder werd versleuteld. Dit geheel vormt een beveiligd document.

Dit document kan overal worden opgeslagen of op welke manier dan ook worden gedeeld en het beleid blijft altijd behouden bij het versleutelde document.

### Inhoudsverbruik
Wanneer een gebruiker een beveiligd document wil verbruiken, begint de RMS-client met het aanvragen van toegang tot de Azure RMS-service:

![RMS documentverbruik - stap 1](../media/AzRMS_documentconsumption1.png)

**Wat gebeurt er in stap 1**: de geverifieerde gebruiker verzendt het documentbeleid en de certificaten van de gebruiker naar Azure RMS. De service ontsleutelt en evalueert het beleid en stelt een lijst met rechten samen (indien aanwezig) die de gebruiker heeft voor het document.

![RMS documentverbruik - stap 2](../media/AzRMS_documentconsumption2.png)

**Wat gebeurt er in stap 2**: de service extraheert vervolgens de AES-inhoudssleutel uit het ontsleutelde beleid. Deze sleutel wordt vervolgens versleuteld met de openbare RSA-sleutel van de gebruiker die is verkregen tijdens de aanvraag.

De opnieuw versleutelde inhoudssleutel wordt vervolgens ingebed in een versleutelde gebruikslicentie met de lijst met gebruikersrechten, die vervolgens wordt geretourneerd naar de RMS-client.

![RMS documentverbruik - stap 3](../media/AzRMS_documentconsumption3.png)

**Wat gebeurt er in stap 3**: tot slot neemt de RMS-client de versleutelde gebruikslicentie en ontsleutelt deze met de eigen persoonlijke sleutel van de gebruiker. Hiermee kan de RMS-client de hoofdtekst van het document ontsleutelen wanneer dit gewenst is, en deze op het scherm weergeven.

De client ontsleutelt tevens de lijst met rechten en geeft deze door aan de toepassing, waardoor deze rechten in de gebruikersinterface van de toepassing worden afgedwongen.

### Variaties
De voorgaande walkthrough behandelt de standaardscenario's, maar er zijn enkele variaties:

-   **Mobiele apparaten**: wanneer mobiele apparaten bestanden beveiligen of verbruiken met Azure RMS, zijn de processtromen veel eenvoudiger. Mobiele apparaten gaan doorlopen niet eerst door het initialisatieproces voor de gebruiker omdat in plaats daarvan elke transactie (om inhoud te beveiligen of verbruiken) onafhankelijk is. Net zoals Windows-computers, maken mobiele apparaten verbinding met de Azure RMS-service voor verificatie. Voor het beveiligen van inhoud, dienen mobiele apparaten een beleid in en stuurt Azure RMS een publicatielicentie en symmetrische sleutel om het document te beveiligen. Als een gebruiker op een mobiel apparaat inhoud wil verbruiken, maakt het mobiele apparaten verbinding met de Azure RMS-service voor verificatie, wordt een documentbeleid naar Azure RMS verzonden en een licentie aangevraagd om het document te mogen verbruiken. Als antwoord verzendt Azure RMS de benodigde sleutels en beperkingen voor de mobiele apparaten. Voor beide processen wordt TLS gebruikt voor de beveiliging van de sleuteluitwisseling en andere berichten.

-   **RMS-connector**: wanneer Azure RMS wordt gebruikt met de RMS-connector, blijven de processtromen ongewijzigd. Het enige verschil is dat de connector fungeert als een relay tussen de on-premises services (zoals Exchange Server en SharePoint Server) en Azure RMS. De connector voert zelf geen bewerkingen uit, zoals de initialisatie van de gebruikersomgeving, of versleutelen of ontsleutelen. In plaats daarvan stuurt de connector de communicatie door die meestal naar een AD RMS-server wordt verzonden, en handelt deze de vertaling af tussen de protocollen die aan beide zijden worden gebruikt. Met dit scenario kunt u Azure RMS gebruiken met on-premises services.

-   **Algemene beveiliging (.pfile)**: wanneer Azure RMS een bestand algemeen beveiligt, is de stroom in wezen hetzelfde voor inhoudsbeveiliging, behalve dat de RMS-client een beleid maakt dat alle rechten verleend. Wanneer het bestand wordt verbruikt, wordt dit ontsleuteld voordat het aan de doeltoepassing wordt doorgegeven. Met dit scenario kunt u alle bestanden beveiligen, zelfs als deze geen systeemeigen ondersteuning bieden voor RMS.

-   **Beveiligd PDF-bestand (.ppdf)**: wanneer Azure RMS eigen beveiliging biedt voor een Office-bestand, wordt tevens een kopie van dat bestand gemaakt dat op dezelfde manier worden beschermd. Het enige verschil is dat het bestand wordt gekopieerd in de PPDF-bestandsindeling, dat door de RMS-toepassing voor delen kan worden geopend als alleen-lezen. In dit scenario kunt u beveiligde bijlagen verzenden via e-mail, met de zekerheid dat de ontvanger op een mobiel apparaat de bijlagen altijd kan lezen, zelfs als het mobiele apparaat geen app heeft die systeemeigen ondersteuning biedt voor beveiligde Office-bestanden.

## Volgende stappen

Als u meer wilt weten over Azure RMS, leest u de andere artikelen in het gedeelte **Begrijpen en verkennen**, zoals [Hoe toepassingen ondersteuning bieden voor Azure Rights Management](applications-support.md) voor meer informatie over hoe u uw huidige toepassingen kunt integreren met Azure RMS om een oplossing voor gegevensbeveiliging te bieden. 

Lees [Terminologie voor Azure Rights Management](../get-started/terminology.md) zodat u vertrouwd met de termen die u kunt tegenkomen tijdens het configureren en gebruiken van Azure RMS, en lees tevens [Vereisten voor Azure Rights Management](../get-started/requirements-azure-rms.md) voordat u begint met de implementatie. Als u meteen van start wilt gaan en het zelf wilt proberen, gebruikt u de [Zelfstudie voor snel starten met Azure Rights Management](../get-started/quick-start-tutorial.md).

Als u klaar bent om Azure RMS in uw organisatie te implementeren, gebruikt u het [Azure Rights Management-implementatieschema](../plan-design/deployment-roadmap.md) voor de implementatiestappen en koppelingen naar instructies.

> [!TIP]
> Gebruik de resources en koppelingen in [Informatie en ondersteuning voor Azure Rights Management](../get-started/information-support.md) voor extra informatie en hulp.


<!--HONumber=Apr16_HO4-->


