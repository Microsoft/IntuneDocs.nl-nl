---
title: Afgeleide referenties voor mobiele apparaten gebruiken in Microsoft Intune - Azure | Microsoft Docs
description: Afgeleide referenties gebruiken op mobiele apparaten als verificatiemethode voor Intune VPN, e-mail, Wi-Fi-profielen, toepassingen en voor S/MIME en versleuteling. Afgeleide referenties zijn een implementatie van de NIST-richtlijnen voor Special Publication 800-157.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f9e8bc347dc6336f665fcabfb4e716fef4818515
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207197"
---
# <a name="use-derived-credentials-in-microsoft-intune"></a>Afgeleide referenties gebruiken in Microsoft Intune

*Dit artikel is van toepassing op apparaten met iOS*

In een omgeving waarin smartcards vereist zijn voor verificatie of versleuteling en ondertekening, kunt u nu Intune gebruiken om mobiele apparaten in te richten met een certificaat dat is afgeleid van de smartcard van een gebruiker. Dit certificaat wordt een *afgeleide referentie* genoemd. Intune [ondersteunt diverse verleners van afgeleide referenties](#supported-issuers), maar u kunt per tenant slechts één verlener tegelijk gebruiken.

Afgeleide referenties zijn een implementatie van de NIST-richtlijnen (National Institute of Standards and Technology) voor afgeleide PIV-referenties (Personal Identity Verification) als onderdeel van Special Publication (SP) 800-157.

**Voor de implementatie van Intune geldt het volgende**:

- De Intune-beheerder configureert de tenant zodanig dat deze werkt met een ondersteunde verlener van afgeleide referenties. U hoeft geen specifieke Intune-instellingen te configureren in het systeem van de verlener van afgeleide referenties.

- De Intune-beheerder geeft **Afgeleide referentie** op als de *Verificatiemethode* voor de volgende objecten:

  - Algemene profieltypen, zoals Wi-Fi, VPN en E-mail, inclusief de systeemeigen mail-app van iOS

  - App-verificatie

  - S/MIME-ondertekening en -versleuteling

- Gebruikers verkrijgen een afgeleide referentie door hun smartcard op een computer te gebruiken om zich te verifiëren bij de verlener van afgeleide referenties. De verlener verleent vervolgens een van de smartcard afgeleid certificaat aan het mobiele apparaat.

- Nadat de afgeleide referentie is ontvangen op het apparaat, wordt deze gebruikt voor verificatie en voor S/MIME-ondertekening en -versleuteling wanneer de afgeleide referentie vereist is volgens profielen voor toegang tot apps of resources. 

## <a name="prerequisites"></a>Vereisten

Controleer de volgende informatie voordat u uw tenant configureert voor het gebruik van afgeleide referenties.

### <a name="supported-platforms"></a>Ondersteunde platforms

Intune biedt ondersteuning voor afgeleide referenties in de volgende besturingssystemen:

- iOS/iPadOS

### <a name="supported-issuers"></a>Ondersteunde verleners

Intune biedt ondersteuning voor één verlener van afgeleide referenties per tenant. U kunt Intune configureren voor gebruik met de volgende verleners:

- **DISA Purebred**: https://cyber.mil/pki-pke/purebred/
- **Entrust Datacard**: https://www.entrustdatacard.com/
- **Intercede**: https://www.intercede.com/

Raadpleeg voor belangrijke informatie over het gebruik van de verschillende verleners de richtlijnen voor de betreffende verlener<!-- , including the issuers end-user workflow-->. Zie [Plan voor afgeleide referenties](#plan-for-derived-credentials) in dit artikel voor meer informatie.

> [!IMPORTANT]  
> Als u een verlener van afgeleide referenties verwijdert uit uw tenant, werken de afgeleide referenties die zijn ingesteld via die verlener niet meer.
>
> Zie [De verlener van afgeleide referenties wijzigen](#change-the-derived-credential-issuer) verderop in dit artikel.

### <a name="company-portal-app"></a>Bedrijfsportal-app

Plan de implementatie van de Intune-bedrijfsportal-app op apparaten die worden ingeschreven voor een afgeleide referentie. Apparaatgebruikers gebruiken de bedrijfsportal-app om het inschrijvingsproces voor referenties te starten.

Zie [iOS Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-ios.md) voor iOS-apparaten.

## <a name="plan-for-derived-credentials"></a>Plannen voor afgeleide referenties

Verdiep u in de volgende aandachtspunten voordat u een verlener van afgeleide referenties instelt.

### <a name="1-review-the-documentation-for-your-chosen-derived-credential-issuer"></a>1) Raadpleeg de documentatie voor de door u gekozen verlener van afgeleide referenties  

Raadpleeg voordat u een verlener configureert, de documentatie van de verlener om te doorgronden hoe via dit systeem afgeleide referenties worden verstrekt aan apparaten.

Afhankelijk van de verlener die u kiest, moeten er mogelijk medewerkers beschikbaar zijn op het inschrijvingsmoment om gebruikers te helpen bij het proces. U moet ook uw huidige Intune-configuraties controleren om ervoor te zorgen dat de benodigde toegang voor voltooiing van de referentieaanvraag niet wordt geblokkeerd voor apparaten of gebruikers.

Mogelijk gebruikt u bijvoorbeeld voorwaardelijke toegang om de toegang tot e-mail voor niet-compatibele apparaten te blokkeren. Als gebruikers via e-mail worden geïnstrueerd het inschrijvingsproces voor afgeleide referenties te starten, ontvangen ze deze instructies mogelijk pas als ze aan het beleid voldoen.

Ook is voor sommige werkstromen voor het aanvragen van afgeleide referenties het gebruik van de apparaatcamera vereist om een QR-code op het scherm te scannen. Met deze code wordt het apparaat gekoppeld aan de verificatieaanvraag die heeft plaatsgevonden voor de verlener van afgeleide referenties met de smartcardreferenties van de gebruiker. Als het gebruik van de camera wordt geblokkeerd door het apparaatconfiguratiebeleid, kan de gebruiker de inschrijvingsaanvraag voor afgeleide referenties niet voltooien.

Algemene informatie:

- U kunt per tenant slechts één verlener tegelijk configureren. Deze verlener is beschikbaar voor alle gebruikers en ondersteunde apparaten in uw tenant.

- Gebruikers krijgen pas een melding dat ze zich moeten inschrijven voor afgeleide referenties als u beleid voor hen instelt waarvoor afgeleide referenties vereist zijn.

- Ze kunnen hierover worden geïnformeerd via een app-melding voor de bedrijfsportal, via e-mail of beide. Als u e-mailmeldingen wilt gebruiken en u voorwaardelijke toegang hebt ingeschakeld, kunnen gebruikers de e-mailmelding mogelijk niet ontvangen als hun apparaat niet aan het beleid voldoet.

### <a name="2-review-the-end-user-workflow-for-your-chosen-issuer"></a>2) Controleer de eindgebruikerswerkstroom voor de door u gekozen verlener

De belangrijkste overwegingen voor elke ondersteunde partner zijn de volgende.  Verdiep u in deze informatie, zodat u kunt voorkomen dat gebruikers en apparaten de inschrijving voor een afgeleide referentie van die verlener niet kunnen voltooien vanwege blokkades in uw Intune-beleid en -configuraties.

#### <a name="disa-purebred"></a>DISA Purebred

Controleer de [gebruikerswerkstroom voor DISA Purebred](https://docs.microsoft.com/intune-user-help/enroll-ios-device-disa-purebred). De belangrijkste vereisten voor deze werkstroom zijn:

- Gebruikers moeten toegang hebben tot een computer of KIOSK waar ze hun smartcard kunnen gebruiken om zich te verifiëren bij de verlener.

- Op apparaten die worden ingeschreven voor een afgeleide referentie moet de Intune-bedrijfsportal-app worden geïnstalleerd.

- Gebruik Intune om [de DISA Purebred-app](#deploy-the-disa-purebred-app) te implementeren op apparaten die worden ingeschreven voor een afgeleide referentie. Deze app moet worden geïmplementeerd via Intune zodat deze wordt beheerd, waarna deze kan worden gebruikt met de Intune-bedrijfsportal-app. Deze app wordt door de apparaatgebruikers gebruikt om de aanvraag voor afgeleide referenties te voltooien.

- Voor de DISA Purebred-app is een [VPN per app](../configuration/vpn-settings-configure.md) vereist om ervoor te zorgen dat de app toegang heeft tot DISA Purebred tijdens de inschrijving voor de afgeleide referentie.

- Apparaatgebruikers moeten tijdens het inschrijvingsproces met een liveagent werken. Tijdens het inschrijvingsproces worden tijdelijke, eenmalige wachtwoordcodes aan de gebruiker verstrekt.

Zie [De DISA Purebred-app implementeren](#deploy-the-disa-purebred-app) verderop in dit artikel voor meer informatie over het ophalen en configureren van de DISA Purebred-app.

#### <a name="entrust-datacard"></a>Entrust Datacard

Controleer de [gebruikerswerkstroom voor Entrust Datacard](https://docs.microsoft.com/intune-user-help/enroll-ios-device-entrust-datacard). De belangrijkste vereisten voor deze werkstroom zijn:

- Gebruikers moeten toegang hebben tot een computer of KIOSK waar ze hun smartcard kunnen gebruiken om zich te verifiëren bij de verlener.

- Op apparaten die worden ingeschreven voor een afgeleide referentie moet de Intune-bedrijfsportal-app worden geïnstalleerd.

- Het gebruik van een apparaatcamera is nodig om een QR-code te scannen waarmee de verificatieaanvraag wordt gekoppeld aan de aanvraag voor afgeleide referenties van het mobiele apparaat.

#### <a name="intercede"></a>Intercede

Controleer de [gebruikerswerkstroom voor Intercede](https://docs.microsoft.com/intune-user-help/enroll-ios-device-intercede). De belangrijkste vereisten voor deze werkstroom zijn:

- Gebruikers moeten toegang hebben tot een computer of KIOSK waar ze hun smartcard kunnen gebruiken om zich te verifiëren bij de verlener.

- Op apparaten die worden ingeschreven voor een afgeleide referentie moet de Intune-bedrijfsportal-app worden geïnstalleerd.

- Het gebruik van een apparaatcamera is nodig om een QR-code te scannen waarmee de verificatieaanvraag wordt gekoppeld aan de aanvraag voor afgeleide referenties van het mobiele apparaat.

### <a name="3-deploy-a-trusted-root-certificate-to-devices"></a>3) Implementeer een vertrouwd basiscertificaat op apparaten

Een vertrouwd basiscertificaat wordt gebruikt met afgeleide referenties om te controleren of de certificaatketen voor afgeleide referenties geldig en vertrouwd is. Ook als er niet rechtstreeks naar wordt verwezen door beleid, is een vertrouwd basiscertificaat vereist. Zie [Een certificaatprofiel configureren voor uw apparaten in Microsoft Intune](certificates-configure.md).

### <a name="4-provide-end-user-instructions-for-how-to-get-the-derived-credential"></a>4) Geef eindgebruikers instructies voor het ophalen van de afgeleide referentie

Maak richtlijnen voor het starten van het inschrijvingsproces voor afgeleide referenties en voor navigatie naar de inschrijvingswerkstroom voor afgeleide referenties voor de door u gekozen verlener. Verstrek deze instructies aan uw gebruikers.

U wordt aangeraden een URL op te geven waarop uw richtlijnen worden gehost. U geeft deze URL op wanneer u de verlener voor afgeleide referenties voor uw tenant configureert, en deze URL wordt beschikbaar gesteld in de bedrijfsportal-app. Als u geen eigen URL opgeeft, wordt in Intune een koppeling naar algemene informatie aangeboden. Deze informatie dekt niet alle scenario's en is mogelijk niet geheel van toepassing op uw omgeving.

### <a name="5-deploy-intune-policies-that-require-derived-credentials"></a>5) Implementeer Intune-beleid waarvoor afgeleide referenties vereist zijn

Maak nieuwe beleidsregels of bewerk bestaande beleidsregels om afgeleide referenties te gebruiken. Afgeleide referenties vervangen andere verificatiemethoden voor app-verificatie, Wi-Fi, VPN, e-mail en voor S/MIME-ondertekening en -versleuteling.

Vermijd het gebruik van een afgeleide referentie om toegang te krijgen tot een proces dat u gaat gebruiken als onderdeel van het proces voor het ophalen van de afgeleide referentie, omdat gebruikers de aanvraag dan mogelijk niet kunnen voltooien.

## <a name="set-up-a-derived-credential-issuer"></a>Een verlener van afgeleide referenties instellen

Voordat u beleidsregels maakt waarvoor het gebruik van een afgeleide referentie vereist is, stelt u een referentieverlener in de Intune-console in. Een verlener van afgeleide referenties is een instelling voor de hele tenant. Tenants ondersteunen slechts één verlener tegelijk.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Tenantbeheer** > **Connectors en tokens** > **Afgeleide referenties**.

    > [!div class="mx-imgBorder"]
    > ![Afgeleide referenties configureren in de console](./media/derived-credentials/configure-provider.png)

3. Geef een beschrijvende **Weergavenaam** op voor het beleid voor verleners van afgeleide referenties.  Deze naam wordt niet weergegeven voor apparaatgebruikers.

4. Selecteer als **Verlener van afgeleide referenties** de verlener van afgeleide referenties die u hebt gekozen voor uw tenant:
   - DISA Purebred
   - Entrust Datacard
   - Intercede  

5. Geef een **Help-URL voor afgeleide referenties** op om een koppeling aan te bieden naar een locatie met aangepaste instructies om gebruikers te helpen afgeleide referenties voor uw organisatie op te halen. De instructies moeten specifiek voor uw organisatie zijn en voor de werkstroom die nodig is om een referentie op te halen van de door u gekozen verlener. De koppeling wordt weergegeven in de bedrijfsportal-app en moet toegankelijk zijn vanaf het apparaat.

   Als u geen eigen URL opgeeft, wordt in Intune een koppeling naar algemene informatie aangeboden, die niet alle scenario's dekt. Deze algemene richtlijnen zijn mogelijk niet geheel van toepassing op uw omgeving.

6. Selecteer een of meer opties als **Meldingstype**. Meldingstypen zijn de methoden die u gebruikt om gebruikers te informeren over de volgende scenario's:

   - Een apparaat inschrijven bij een verlener om een nieuwe afgeleide referentie te verkrijgen.
   - Een nieuwe afgeleide referentie ophalen wanneer de huidige referentie bijna is verlopen.
   - Een afgeleide referentie gebruiken met een beleidsregel voor Wi-Fi, VPN, e-mail of app-verificatie en voor S/MIME-ondertekening en -versleuteling.

7. Selecteer **Opslaan** als u klaar bent om de configuratie van de verlener van afgeleide referenties te voltooien.

Nadat u de configuratie hebt opgeslagen, kunt u wijzigingen aanbrengen in alle velden, met uitzondering van de *Verlener van afgeleide referenties*.  Zie [De verlener van afgeleide referenties wijzigen](#change-the-derived-credential-issuer) verderop in dit artikel als u de verlener wilt wijzigen.

## <a name="deploy-the-disa-purebred-app"></a>De DISA Purebred-app implementeren

*Deze sectie is alleen van toepassing wanneer u DISA Purebred gebruikt*.

Als u **DISA Purebred** als uw verlener van afgeleide referenties voor Intune wilt gebruiken, moet u de DISA Purebred-app verkrijgen en vervolgens Intune gebruiken om de app te implementeren op apparaten. Apparaatgebruikers gebruiken de app op hun apparaat om de afgeleide referentie aan te vragen bij DISA Purebred.

Naast implementatie van de app met Intune, configureert u een Intune-VPN per app voor de DISA Purebred-toepassing.

**Voer de volgende taken uit**:
  
1. Download de [DISA Purebred-toepassing](https://cyber.mil/pki-pke/purebred/).
2. Implementeer de DISA Purebred-toepassing in Intune.  Zie [Een iOS Line-Of-Business-app toevoegen aan Microsoft Intune](../apps/lob-apps-ios.md).
3. [Maak een VPN per app](../configuration/vpn-settings-configure.md) voor de DISA Purebred-toepassing.

## <a name="use-derived-credentials-for-authentication-and-smime-signing-and-encryption"></a>Afgeleide referenties gebruiken voor verificatie en S/MIME-ondertekening en -versleuteling

U kunt **afgeleide referentie** opgeven voor de volgende profieltypen en doeleinden:

- [Toepassingen](#use-derived-credentials-for-app-authentication)
- [E-mail](../configuration/email-settings-ios.md)
- [VPN](../configuration/vpn-settings-ios.md)
- [S/MIME-ondertekening en -versleuteling](certificates-s-mime-encryption-sign.md)
- [Wi-Fi](../configuration/wi-fi-settings-ios.md)

  Voor Wi-Fi-profielen is *Verificatiemethode* alleen beschikbaar wanneer het **EAP-type** is ingesteld op een van de volgende waarden:
  - EAP – TLS
  - EAP-TTLS
  - PEAP

### <a name="use-derived-credentials-for-app-authentication"></a>Afgeleide referenties gebruiken voor app-verificatie

Afgeleide referenties gebruiken voor verificatie op basis van certificaten voor websites en toepassingen. Ga als volgt te werk om een afgeleide referentie gebruiken voor app-verificatie:

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Configuratieprofielen** > **Profiel maken**.
3. Voer de volgende instellingen in:

    - **Naam**: Voer een beschrijvende naam in voor het profiel. Geef uw profielen een naam zodat u ze later eenvoudig kunt identificeren. Een goede profielnaam is bijvoorbeeld **Afgeleide referentie voor het profiel van iOS-apparaten**.
    - **Beschrijving**: Voer een beschrijving in met een overzicht van de instelling en eventuele andere belangrijke details.
    - **Platform**: Selecteer **iOS/iPadOS**.
    - **Profieltype**: Selecteer **Afgeleide referentie**.

4. Selecteer **OK** om uw wijzigingen op te slaan.
5. Wanneer u klaar bent, selecteert u **OK** > **Maken** om het Intune-profiel te maken. Wanneer het profiel is gemaakt, wordt dit weergegeven in de lijst **Apparaten - Configuratieprofielen**.
6. Selecteer het nieuwe profiel > **Toewijzingen**. Selecteer de groepen waarvoor het beleid moet worden gebruikt.
 
Gebruikers ontvangen de app- of e-mailmelding, afhankelijk van de instellingen die u hebt opgegeven bij het instellen van de verlener van afgeleide referenties. Via de melding wordt de gebruiker geïnstrueerd de bedrijfsportal te starten zodat het beleid voor afgeleide referenties kan worden verwerkt.

## <a name="renew-a-derived-credential"></a>Een afgeleide referentie vernieuwen

Afgeleide referenties kunnen niet worden verlengd of vernieuwd. In plaats daarvan moeten gebruikers de werkstroom voor referentieaanvragen gebruiken om een nieuwe afgeleide referentie voor hun apparaat aan te vragen.

Als u een of meer methoden als **Meldingstype**configureert, krijgen gebruikers automatisch een Intune-melding wanneer de huidige afgeleide referentie tachtig procent van de levensduur heeft bereikt. Via de melding worden gebruikers geïnstrueerd naar het referentieaanvraagproces te gaan om een nieuwe afgeleide referentie te verkrijgen.

Nadat een apparaat een nieuwe afgeleide referentie heeft ontvangen, worden de beleidsregels die gebruikmaken van afgeleide referenties opnieuw geïmplementeerd op dat apparaat.


## <a name="change-the-derived-credential-issuer"></a>De verlener van afgeleide referenties wijzigen

Op tenantniveau kunt u de referentieverlener wijzigen, hoewel er slechts één verlener tegelijk wordt ondersteund voor een tenant.

Nadat u de verlener hebt gewijzigd, krijgen gebruikers de instructie een nieuwe afgeleide referentie op te halen bij de nieuwe verlener. Ze moeten dit doen voordat ze een afgeleide referentie voor verificatie kunnen gebruiken.

### <a name="change-the-issuer-for-your-tenant"></a>De verlener voor uw tenant wijzigen

> [!IMPORTANT]  
> Als u een verlener verwijdert en dezelfde verlener onmiddellijk opnieuw configureert, moet u de profielen en apparaten toch bijwerken om afgeleide referenties van die verlener te gebruiken. Afgeleide referenties die zijn verkregen voordat u de uitgever verwijdert, zijn niet meer geldig.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Tenantbeheer** > **Connectors en tokens** > **Afgeleide referenties**.
3. Selecteer **Verwijderen** om de huidige verlener van afgeleide referenties te verwijderen.
4. Configureer een nieuwe verlener.

### <a name="update-profiles-that-use-derived-credentials"></a>Profielen bijwerken die gebruikmaken van afgeleide referenties

Nadat u een verlener hebt verwijderd en vervolgens een nieuwe hebt toegevoegd, moet u elk profiel bewerken dat gebruikmaakt van afgeleide referenties. Deze regel is ook van toepassing als u de vorige verlener herstelt. Bij elke bewerking van het profiel wordt een update geactiveerd, ook bij een eenvoudige bewerking van de *Beschrijving* van het profiel.

### <a name="update-derived-credentials-on-devices"></a>Afgeleide referenties op apparaten bijwerken

Nadat u een verlener hebt verwijderd en vervolgens een nieuwe hebt toegevoegd, moeten apparaatgebruikers een nieuwe afgeleide referentie aanvragen. Deze regel is ook van toepassing als u dezelfde uitgever toevoegt die u hebt verwijderd. Het aanvraagproces voor de nieuwe afgeleide referentie is hetzelfde als voor inschrijving van een nieuw apparaat of het vernieuwen van een bestaande referentie.

## <a name="next-steps"></a>Volgende stappen

[Apparaatconfiguratieprofielen maken](../configuration/device-profile-create.md).
