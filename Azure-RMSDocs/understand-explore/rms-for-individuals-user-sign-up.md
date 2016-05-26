---
# required metadata

title: Hoe gebruikers zich aanmelden voor RMS voor personen | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: a60731bd-f78d-4f00-bb3e-354637b312ab

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Hoe gebruikers zich aanmelden voor RMS voor personen

*Van toepassing op: Azure Rights Management*

Als gebruikers zich voor dit gratis account willen aanmelden, kunnen zij dit aanvragen door naar de [Microsoft Rights Management-pagina](https://portal.aadrm.com/) te gaan en hun e-mailadres van werk of school op te geven. 

Meestal worden gebruikers naar deze aanmeldpagina doorgeleid via een e-mailbericht met een beveiligde bijlage waarin instructies staan hoe zij zich kunnen aanmelden. Ze ontvangen als reactie van Microsoft een e-mailbericht en kunnen vervolgens het aanmeldingsproces voltooien door gegevens in te voeren om hun account te maken. Wanneer ze van Microsoft een e-mailbevestiging ontvangen, worden ze via dit laatste e-mailbericht doorgeleid naar een pagina waar ze de toepassing voor delen voor verschillende apparaten en een koppeling naar de gebruikershandleiding kunnen downloaden.

## Aanmelden voor RMS voor personen

1.  Ga op een Windows- of Mac-computer naar de pagina [Microsoft Rights Management](https://portal.aadrm.com).

2.  Voer het e-mailadres in dat u voor uw organisatie gebruikt, zoals **janetm@contoso.com** of **p.dover@fabrikam.com**.

    > [!IMPORTANT]
    > Persoonlijke e-mailaccounts worden niet ondersteund. Voer dus geen Microsoft-account (voorheen bekend als een Microsoft Live ID-account) of een ander persoonlijk account in dat u thuis via uw internetprovider gebruikt.

3.  Klik op **Aan de slag**.

    Microsoft gebruikt uw e-mailadres om te controleren of uw organisatie al beschikt over een [betaald abonnement dat Azure RMS bevat](../get-started/requirements-subscriptions.md). Als dat het geval is, heeft u geen RMS voor personen nodig. U wordt dan direct aangemeld en de selfserviceaanmelding voor RMS voor personen wordt geannuleerd. Als er geen betaald abonnement voor Azure RMS wordt gevonden, gaat u verder met de volgende stap.

4.  Wacht op een e-mailbevestiging die wordt verzonden naar het adres dat u hebt opgegeven. Het is afkomstig van Microsoft (DoNotReply@microsoft.com) en heeft als onderwerp **Microsoft RMS**.

5.  Wanneer u het e-mailbericht ontvangt, klikt u op de koppeling in de instructies om het aanmeldingsproces te voltooien.

6.  U wordt via de koppeling doorgeleid naar een nieuwe **Microsoft Rights Management**-pagina waarop u de gegevens voor uw account opgeeft. Voer uw voor- en achternaam in. Voer een wachtwoord naar keuze in en bevestig dit. Selecteer in de vervolgkeuzelijst uw land (of het dichtstbijzijnde land als uw land niet wordt vermeld) en klik vervolgens op **Maken**.

7.  Wacht op een ander e-mailbericht van Microsoft waarin wordt bevestigd dat uw account klaar is voor gebruik.

8.  Wanneer u het e-mailbericht ontvangt, klikt u op de koppeling om u aan te melden en de instructies voor het downloaden en installeren van de toepassing voor delen te lezen. U kunt ook op de Help-koppeling klikken om de gebruikershandleiding voor de toepassing voor delen te lezen.

Uw account is gemaakt en u kunt nu bestanden beveiligen of bestanden lezen die anderen hebben beveiligd. Als u wordt gevraagd om u aan te melden voor het beveiligen van bestanden of het lezen van beveiligde bestanden, voert u het e-mailadres en wachtwoord in die u hebt gebruikt voor het maken van het account voor RMS voor personen.

## Technisch overzicht van het aanmeldingsproces
RMS voor personen maakt gebruik van een aanmeldingsproces via de selfservice. Dit wordt ook gebruikt door andere services die gebruikmaken van Microsoft-cloudtechnologie om gebruikers te verifiëren.

Het volgende vindt plaats op de achtergrond wanneer gebruikers zich aanmelden voor RMS voor personen en hun organisatie niet over een Office 365-abonnement of Azure-abonnement, en dus geen map in Azure om gebruikers te verifiëren, beschikt:

1.  Wanneer de eerste gebruiker van een organisatie een abonnement voor RMS voor personen aanvraagt, wordt de domeinnaam die is opgegeven in het e-mailadres gecontroleerd om te zien of het al is gekoppeld aan een Azure-tenant. Als er geen bestaande tenant voorkomt, wordt er voor de organisatie automatisch een nieuwe tenant en Azure-map gemaakt, die een account voor deze eerste gebruiker bevat. In tegenstelling tot een betaald abonnement voor Azure is dit eerste account niet voor een hoofdbeheerder, maar voor een standaardgebruiker. Het nieuwe account maakt gebruik van het e-mailadres en het wachtwoord die de gebruiker heeft opgegeven.

    > [!NOTE]
    > Sommige domeinnamen kunnen niet worden gebruikt voor het maken van de map en kunnen daarom niet worden gebruikt voor RMS voor personen. De lijst met geblokkeerde domeinnamen kan worden bekeken in dit JSON-bestand (JavaScript Object Notation): [http://portal.aadrm.com/content/blocked_domains.json](http://portal.aadrm.com/content/blocked_domains.json)

    Als een bestaande tenant wordt gevonden, wordt gecontroleerd of deze al een abonnement heeft voor Azure RMS. Wanneer er geen abonnement wordt gevonden, kan het gratis abonnement voor RMS voor personen worden toegevoegd.

2.  Het abonnement voor RMS voor personen wordt aan de organisatie toegekend. Deze gebruiker kan nu door Azure worden geverifieerd en kan vervolgens bestanden beveiligen en bestanden lezen die anderen met Azure Rights Management hebben beveiligd. Als de gebruikers bestanden willen beveiligen en beveiligde bestanden willen lezen, moeten ze beschikken over een toepassing met RMS-functionaliteit, zoals de gratis [Rights Management-toepassing voor delen](../rms-client/sharing-app-windows.md).

3.  Wanneer de tweede gebruiker van dezelfde organisatie een abonnement voor RMS voor personen aanvraagt, wordt er met behulp van het abonnement voor RMS voor personen van de organisatie een nieuw gebruikersaccount toegevoegd aan de eerder gemaakte Azure-map. Deze tweede gebruiker kan alles doen wat de eerste gebruiker kan doen (bestanden beveiligen en beveiligde bestanden lezen). Bovendien kunnen deze twee gebruikers nu eenvoudiger veilig samenwerken omdat ze snel standaardsjablonen kunnen toepassen op bestanden waarmee de toegang wordt beperkt tot accounts in de Azure-map van hun organisatie.

4.  Toekomstige gebruikers van dezelfde organisatie volgen hetzelfde patroon en voegen gebruikersaccounts toe (wanneer nieuwe gebruikers zich aanmelden) aan de Azure-map van de organisatie. Des te meer accounts aan de map worden toegevoegd, des te meer gebruikers veilig kunnen samenwerken met collega's en partners en des te gemakkelijker wordt voorkomen dat onbevoegde personen hun bestanden lezen wanneer ze hiertoe geen toegang zouden moeten hebben.

Tijdens dit proces worden er voor de organisatie geen kosten in rekening gebracht en hoeft de IT-afdeling geen werkzaamheden te verrichten. De IT-afdeling kan er echter voor kiezen om het volgende te doen:

-   **De accounts en het aanmeldingsproces beheren**: IT-beheerders kunnen zichzelf eigenaar maken van de automatisch gemaakte map en accounts in Azure. Vervolgens kunnen ze de accounts beheren door oplossingen voor directory-integratie zoals wachtwoordsynchronisatie en eenmalige aanmelding te implementeren. Ze kunnen ook voorkomen dat gebruikers accounts maken of zich aanmelden voor RMS voor personen.

    Zie [Hoe beheerders accounts kunnen beheren die zijn gemaakt voor RMS voor personen](rms-for-individuals-take-control.md) voor meer informatie.

-   **Rights Management beheren**: IT-beheerders kunnen voor de organisatie het abonnement voor RMS voor personen omzetten in een betaald abonnement dat Azure Rights Management bevat. Wanneer ze dit doen, worden de bestaande Azure-map en -accounts bewaard voor een naadloze overgang voor bestaande gebruikers die RMS voor personen al gebruikten. Bestanden die eerder door gebruikers werden beveiligd, blijven gewoon beveiligd volgens dezelfde beleidsregels. Daarnaast kunnen de personen die gemachtigd waren om de bestanden te gebruiken de bestanden nog steeds op dezelfde manier gebruiken.

    Wanneer u voor bovenstaande optie kiest, heeft uw organisatie het voordeel dat Rights Management kan worden geïntegreerd met de eigen werkstromen, services en gegevensopslag. Bovendien kunt u nu Rights Management beheren omdat u beschikt over de tenantsleutel van uw organisatie voor Azure Rights Management. U kunt nu het volgende doen:

    -   Exchange en SharePoint configureren ter ondersteuning van Azure Rights Management, zelfs als deze on-premises worden uitgevoerd. Exchange en SharePoint worden standaard ondersteund voor de online services en ze worden ondersteund door een connector voor de on-premises servers. Zie voor meer informatie de volgende onderwerpen:

        -   De secties Exchange Online en SharePoint Online van [Office 365: configuratie voor clients en online services](../deploy-use/configure-office365.md)

        -   [De Azure Rights Management-connector implementeren](../deploy-use/deploy-rms-connector.md)

    -   E-Discovery uitvoeren voor gegevens die eigendom zijn van het bedrijf zodat u zo nodig bestanden kunt ontsleutelen die zijn beveiligd door Rights Management. Zie [Supergebruikers configureren voor Azure Rights Management en detectieservices of gegevensherstel](../deploy-use/configure-super-users.md) voor meer informatie.

    -   Registreer alle activiteiten voor Rights Management die in uw organisatie worden uitgevoerd. Dit is zeer belangrijk omdat u zo niet alleen kunt controleren welke bestanden worden beveiligd en wie deze beveiligde bestanden opent, maar u kunt ook mogelijk verdacht gedrag vaststellen van onbevoegde personen die toegang proberen te krijgen tot beveiligde bestanden. Zie [Azure Rights Management-gebruik analyseren en vastleggen in een logboek](../deploy-use/log-analyze-usage.md) voor meer informatie.

    -   Bied gebruikers de mogelijkheid om hun beveiligde documenten bij te houden en in te trekken, als deze functies worden ondersteund door uw [Azure RMS-abonnement](https://technet.microsoft.com/dn858608). Zie [Uw bestanden bijhouden en intrekken](../rms-client/sharing-app-track-revoke.md) in de [gebruikershandleiding voor de RMS-toepassing voor delen](../rms-client/sharing-app-user-guide.md) voor meer informatie.

    -   Implementeer een BYOK-oplossing (Bring Your Own Key) zodat uw tenantsleutel voor Azure Rights Management on-premises wordt gegenereerd volgens uw IT-beleid en veilig aan Microsoft wordt overgedragen via een HSM (Hardware Security Module). Zie [Uw Azure Rights Management-tenantsleutel plannen en implementeren](../plan-design/plan-implement-tenant-key.md) voor meer informatie.


## Volgende stappen
Zie [Hoe beheerders accounts kunnen beheren die zijn gemaakt voor RMS voor personen](rms-for-individuals-take-control.md).




<!--HONumber=Apr16_HO4-->


