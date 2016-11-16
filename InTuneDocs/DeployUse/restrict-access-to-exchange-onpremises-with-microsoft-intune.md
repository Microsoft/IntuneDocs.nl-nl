---
title: Toegang tot e-mail beperken op Exchange On-premises | Microsoft Intune
description: Toegang tot bedrijfse-mail op Exchange On-premises beschermen en controleren met voorwaardelijke toegang.
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a55071f5-101e-4829-908d-07d3414011fc
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6e647c66d6de7d455d290dfa3358499a3f13453
ms.openlocfilehash: e5c9d2a19f588ddd067a1e194568186f66afb85b


---

# Toegang tot e-mail beperken op Exchange On-premises en oudere Exchange Online Dedicated met Microsoft Intune


Als u een Exchange Online Dedicated-omgeving hebt en wilt weten of deze de nieuwe of oudere configuratie heeft, neemt u contact op met uw accountmanager.


Als u de toegang tot e-mail op Exchange On-premises of de oude Exchange Online-specifieke omgeving wilt beheren, configureer dan beleid voor voorwaardelijke toegang tot Exchange On-premises in Intune.
Zie het artikel [De toegang tot e-mail en O365-service beperken]( restrict-access-to-email-and-o365-services-with-microsoft-intune.md) voor meer informatie over hoe voorwaardelijke toegang werkt.

Controleer **voordat** u voorwaardelijke toegang configureert. het volgende:

-   Uw versie van Exchange moet **Exchange 2010 of hoger** zijn. De CAS-matrix (Client Access Server) voor Exchange-servers wordt ondersteund.

-   U moet de **Exchange On-premises-connector** gebruiken die [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] koppelt aan Microsoft Exchange On-premises. Hiermee kunt u apparaten beheren via de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-console. Zie [Intune On-premises Exchange-connector](intune-on-premises-exchange-connector.md) voor meer informatie over de connector.

    -   De Exchange On-premises-connector die u in de Intune-console vindt, is uitsluitend bestemd voor uw Intune-tenant en mag niet worden gebruikt met een andere tenant. U moet er ook voor zorgen dat de Exchange-connector voor uw tenant **op slechts één machine** is geïnstalleerd.

        Deze connector moet worden gedownload vanuit de Intune-beheerconsole.  Zie [On-premises Exchange-connector configureren voor on-premises of gehoste Exchange](intune-on-premises-exchange-connector.md) voor een overzicht over het configureren van de on-premises Exchange-connector.

    -   De connector kan op elke machine worden geïnstalleerd, zolang die machine maar kan communiceren met de Exchange-server.

    -   De connector ondersteunt de **Exchange CAS-omgeving**. Vanuit technisch oogpunt kunt u de connector desgewenst rechtstreeks op de Exchange CAS-server installeren, maar dit wordt niet aangeraden, omdat hiermee de belasting van de server wordt verhoogd.
    Wanneer u de connector configureert, moet u deze zodanig instellen dat deze communiceert met een van de Exchange CAS-servers.

-   **Exchange ActiveSync** kan worden geconfigureerd met verificatie op basis van certificaten of het invoeren van gebruikersreferenties.

Wanneer beleid voor voorwaardelijke toegang wordt geconfigureerd en een gebruiker deel uitmaakt van de doelgroep voor het beleid, moet het volgende met het **apparaat** zijn gedaan voordat een gebruiker verbinding kan maken met zijn e-mail:

-  Het apparaat moet zijn **ingeschreven** bij [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] of lid zijn van een domein.

-  Het apparaat moet zijn **geregistreerd bij Azure Active Directory**. Bovendien moet de client-id van Exchange ActiveSync zijn geregistreerd bij Azure Active Directory.

  AAD DRS wordt automatisch geactiveerd voor Intune- en Office 365-klanten. Klanten die de ADFS Device Registration Service al hebben geïmplementeerd, zien geen geregistreerde apparaten in hun on-premises Active Directory. **Dit geldt niet voor Windows-pc's en Windows Phone-apparaten**.

-   **Voldoen** aan [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-nalevingsbeleid dat op dat apparaat is geïmplementeerd.

Het volgende diagram illustreert de werkstroom die door beleid voor voorwaardelijke toegang voor Exchange On-premises wordt gebruikt om te bepalen of apparaten moeten worden geblokkeerd of toegestaan.

![Diagram met de beslissingspunten die bepalen of aan een apparaat toegang wordt verleend tot Exchange On-premises of dat deze wordt geblokkeerd](../media/ConditionalAccess8-2.png) Als er niet wordt voldaan aan een beleid voor voorwaardelijke toegang, krijgt de gebruiker een van de volgende berichten te zien wanneer deze zich aanmeldt:

- Als het apparaat niet is ingeschreven bij [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] of niet is geregistreerd bij Azure Active Directory, wordt er een bericht weergegeven met instructies over hoe de bedrijfsportalapp moet worden geïnstalleerd, het apparaat moet worden ingeschreven en e-mail moet worden geactiveerd. Dit proces zorgt er ook voor dat de Exchange ActiveSync-id van het apparaat wordt gekoppeld aan het apparaatrecord in Azure Active Directory.

-   Als het apparaat niet aan het beleid voldoet, wordt er een bericht weergegeven dat de eindgebruiker omleidt naar de website of app van de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-bedrijfsportal. Hier vindt de gebruiker informatie over het probleem en aanwijzingen om dit op te lossen.

## Ondersteuning voor mobiele apparaten
-   Windows Phone 8.1 en hoger

-   Systeemeigen e-mailapp voor iOS.

-   EAS-mailclients zoals Gmail op Android 4 of hoger.
- EAS-mailclients **Android for Work-apparaten:** alleen de apps **Gmail** en **Nine Work** in het **werkprofiel** worden ondersteund op Android for Work-apparaten. Voorwaardelijke toegang werkt alleen in combinatie met Android for Work als u een e-mailprofiel voor de app Gmail of Nine Work implementeert en die apps ook implementeert als verplicht te installeren apps. 

> [!NOTE]
> De Microsoft Outlook-app voor Android en iOS wordt niet ondersteund.

## Ondersteuning voor pc's

De **Mail**-toepassing voor Windows 8.1 en hoger (indien geregistreerd bij [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)])

##  Beleid voor voorwaardelijke toegang configureren

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) achtereenvolgens **Beleid** > **Voorwaardelijke toegang** > **Beleid voor Exchange On-premises**.
![IntuneSA5aSelectExchOnPremPolicy](../media/IntuneSA5aSelectExchOnPremPolicy.png)

2.  Configureer het beleid met de gewenste instellingen: ![Schermafbeelding van de pagina Beleid voor Exchange On-premises](../media/IntuneSA5bExchangeOnPremPolicy.png)

  - **De toegang tot Exchange On-premises blokkeren voor e‑mailapps indien het apparaat niet voldoet aan het beleid of niet is ingeschreven voor Microsoft Intune:** wanneer u deze optie selecteert, worden apparaten geblokkeerd die niet worden beheerd door [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] of niet voldoen aan het nalevingsbeleid van Exchange-services.

  - **Standaardregel negeren - Ingeschreven en compatibele apparaten altijd toegang geven tot Exchange:** als u deze optie inschakelt, is het apparaten die zijn geregistreerd bij Intune en die voldoen aan het nalevingsbeleid, toegestaan toegang tot Exchange te krijgen.  
  Met deze regel wordt de **Standaardregel** genegeerd. Dit houdt in dat ingeschreven apparaten die voldoen aan het beleid, nog steeds toegang kunnen krijgen tot Exchange, zelfs als u de **Standaardregel** instelt op het in quarantaine plaatsen van het apparaat of op het blokkeren van toegang.

  - **Doelgroepen:** selecteer de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-gebruikersgroepen die hun apparaat moeten inschrijven bij [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] voordat ze toegang kunnen krijgen tot Exchange.

  - **Uitgesloten groepen:** selecteer de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-gebruikersgroepen die zijn uitgesloten van het beleid voor voorwaardelijke toegang. Gebruikers in deze lijst zijn uitgesloten, zelfs als ze ook op de lijst **Doelgroepen** staan.

  - **Platformuitzonderingen:** kies **Regel toevoegen** om een regel te configureren waarin de toegangsniveaus voor bepaalde mobiele-apparaatreeksen en -modellen worden gedefinieerd. Omdat deze apparaten van elk type kunnen zijn, kunt u ook apparaattypen configureren die niet worden ondersteund door [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

  - **Standaardregel:** als er apparaten zijn die niet onder de andere regels vallen, kunt u zelf kiezen of deze toegang krijgen tot Exchange, worden geblokkeerd of in quarantaine worden geplaatst. Wanneer u de regel instelt op het toestaan van toegang, wordt e-mailtoegang automatisch verleend aan iOS-, Windows- en Samsung KNOX-apparaten wanneer deze zijn ingeschreven en voldoen aan het beleid. De eindgebruiker hoeft geen procedure te doorlopen om de e-mail op te halen.  Op Android-apparaten die niet werken op Samsung KNOX, krijgen eindgebruikers een quarantaine-e-mail met aanwijzingen voor de verificatie van de inschrijving en de naleving van het beleid voordat ze toegang krijgen tot e-mail. Als u de regel zo instelt dat de toegang wordt geblokkeerd of dat het apparaat in quarantaine wordt geplaatst, wordt de toegang tot Exchange voor alle apparaten geblokkeerd, ongeacht of deze al zijn ingeschreven in Intune of niet. Als u wilt voorkomen dat de regel betrekking heeft op apparaten die zijn ingeschreven en voldoen aan het beleid, schakelt u de optie **Standaardregel negeren** in.
>[!TIP]
>Als het uw bedoeling is om eerst alle apparaten te blokkeren voordat u toegang verleent tot e-mail, kiest u Toegang blokkeren, of Quarantaineregel. De standaardregel geldt voor alle apparaattypen. Apparaattypen die u als platformuitzondering opgeeft en die niet worden ondersteund door [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], vallen hier dus ook onder.

  - **Gebruikersmelding:** naast de meldings-e-mail die vanuit Exchange wordt verzonden, verstuurt Intune ook een e-mail waarin wordt beschreven hoe de blokkering van het apparaat kan worden opgeheven. U kunt het standaardbericht aanpassen aan uw behoeften. Omdat de Intune-meldings-e-mail met herstelinstructies wordt bezorgd in het Exchange-postvak van de gebruiker, kan de gebruiker ook een niet-geblokkeerd apparaat of een andere methode gebruiken om Exchange te openen en het bericht weer te geven, mocht het apparaat van de gebruiker worden geblokkeerd voordat deze het e-mailbericht heeft ontvangen. Dit is vooral van toepassing wanneer de **Standaardregel** is ingesteld op het blokkeren van toegang of het in quarantaine plaatsen van het apparaat.  In dat geval moet de eindgebruiker naar de app-store gaan, de Microsoft-bedrijfsportalapp downloaden en het apparaat inschrijven. Dit geldt voor iOS-, Windows- en Samsung KNOX-apparaten.  Bij apparaten die niet over Samsung KNOX beschikken, moet de IT-beheerder de quarantaine-e-mail naar een ander e-mailaccount verzenden. De eindgebruiker moet deze vervolgens naar het geblokkeerde apparaat kopiëren om de procedure voor inschrijving en naleving uit te voeren.
  > [!NOTE]
  > Als u ervoor wilt zorgen dat Exchange de e-mailmelding kan verzenden, moet u het account opgeven dat moet worden gebruikt om de e-mailmelding te verzenden.
  >
  > Zie [Exchange On-premises-connector configureren voor on-premises of gehoste Exchange](intune-on-premises-exchange-connector.md) voor meer informatie.

3.  Als u klaar bent, kiest u **Opslaan**.

-   U hoeft het beleid voor voorwaardelijke toegang niet te implementeren; het wordt direct van kracht.

-   Wanneer een gebruiker een Exchange ActiveSync-profiel heeft ingesteld, kan het één tot drie uur duren voor het apparaat is geblokkeerd (als het niet wordt beheerd door [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]).

-   Als een geblokkeerde gebruiker vervolgens het apparaat inschrijft bij [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] (en niet-naleving oplost), krijgt deze binnen twee minuten toegang tot e-mail.

-   Als de gebruiker de inschrijving van het apparaat verwijdert uit [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], wordt de toegang tot e-mail na 1-3 uur geblokkeerd.

**Raadpleeg [Voorbeeldscenario's voor het beperken van toegang tot e-mail](restrict-email-access-example-scenarios.md) voor enkele scenario's met voorbeelden van het configureren van beleid voor voorwaardelijke toegang om de toegang voor apparaten te beperken.**

## Volgende stappen
[Toegang tot SharePoint Online beperken](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

[Toegang tot Skype voor Bedrijven Online beperken](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


