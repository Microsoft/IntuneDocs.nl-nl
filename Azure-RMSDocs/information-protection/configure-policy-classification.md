---
title: Voorwaarden voor automatische en aanbevolen classificatie voor Azure Information Protection configureren | Azure Rights Management
description: 
author: cabailey
manager: mbaldwin
ms.date: 08/10/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: e915f959-eafb-4375-8d2c-2f312edf2d29
translationtype: Human Translation
ms.sourcegitcommit: b2263c212a1b869b778767493645f10ad821828f
ms.openlocfilehash: 80c201dcf316a5aa5e123645d47c6741f8b61f05


---

# Voorwaarden voor automatische en aanbevolen classificatie voor Azure Information Protection configureren

>*Van toepassing op: Azure Information Protection preview*

**[ Deze informatie is voorlopig en kan worden gewijzigd. ]**

Wanneer u voorwaarden voor een label configureert, kunt u automatisch een label aan een document of e-mailbericht toewijzen. Of u kunt gebruikers vragen om het label te selecteren dat u aanbeveelt: 

- Automatische classificatie is van toepassing op Word, Excel en PowerPoint wanneer bestanden worden opgeslagen en op Outlook wanneer e-mailberichten worden verzonden. U kunt automatische classificatie niet gebruiken voor bestanden die eerder handmatig zijn gelabeld.
 
- Aanbevolen classificatie is van toepassing op Word, Excel en PowerPoint wanneer bestanden worden opgeslagen.

Wanneer u voorwaarden configureert, kunt u gebruikmaken van vooraf gedefinieerde patronen, zoals creditcardnummers of sociaal-fiscale nummers. U kunt ook een aangepaste tekenreeks of aangepast patroon definiëren als voorwaarde voor automatische classificatie. Zie de sectie [Information about the built-in conditions](#information-about-the-built-in-conditions) (Informatie over de ingebouwde voorwaarden) voor meer informatie over de voorwaarden.

Hoe meerdere voorwaarden worden geëvalueerd wanneer deze van toepassing zijn op meer dan een label:

1. De labels worden voor evaluatie gerangschikt overeenkomstig hun positie die u in het beleid opgeeft: het eerst geplaatste label heeft de laagste positie (minst gevoelig) en het laatst geplaatste label de hoogste positie (meest gevoelig).

2. Het meest gevoelige label wordt toegepast.
 
3. Het laatste sublabel wordt toegepast.

> [!TIP]
>We raden u voor de beste gebruikerservaring en om de bedrijfscontinuïteit te waarborgen aan te starten met de door de gebruiker aanbevolen classificatie in plaats van automatische classificatie. Deze configuratie geeft uw gebruikers de mogelijkheid om de label- of beveiligingsactie te accepteren of om deze suggesties te negeren als ze niet geschikt zijn voor hun document of e-mailbericht.

Een voorbeeldprompt voor wanneer u een voorwaarde configureert om een label als aanbevolen actie toe te passen, inclusief een aangepaste beveiligingstip:

![Azure Information Protection-detectie en aanbeveling](../media/info-protect-recommend-callouts.png)

In dit voorbeeld kan de gebruiker op **Nu wijzigen** klikken om het aanbevolen label toe te passen of de aanbeveling negeren door de balk te sluiten.

## Aanbevolen of automatische classificatie voor een label configureren

1. Als u zich nog niet bij [Azure Portal](https://portal.azure.com) hebt aangemeld, meldt u zich nu aan en navigeert u vervolgens naar de blade **Azure Information Protection**. 
    
    Klik bijvoorbeeld in het hub-menu op **Bladeren** en begin met het typen van **Information** in het filtervak. Selecteer **Azure Information Protection**.

2. Selecteer op de blade **Azure Information Protection** het label dat u wilt configureren voor automatische of aanbevolen classificatie.

3. Klik op de blade **Label** in de sectie **Configure conditions for automatically applying this label (Voorwaarden voor het automatisch toepassen van dit label configureren)** op **Een nieuwe voorwaarde toevoegen**.

4. Selecteer op de blade **Voorwaarde** de optie **Ingebouwd** als u een vooraf gedefinieerde voorwaarde wilt gebruiken of **Aangepast** als u een eigen voorwaarde wilt opgeven en klik vervolgens op **Opslaan**:

    - Voor **Ingebouwd**: selecteer een voorwaarde in de lijst met beschikbare voorwaarden en selecteer vervolgens het minimum aantal exemplaren en of het exemplaar een unieke waarde moet hebben om in het aantal exemplaren te worden opgenomen.
        
        Zie de sectie [Informatie over de ingebouwde voorwaarden](#information-about-the-built-in-conditions) voor meer informatie over de detectieregels voor deze voorwaarden en enkele voorbeelden.

    - Voor **Aangepast**: geef een naam en woordgroep op die moeten overeenkomen (deze mogen geen aanhalingstekens en speciale tekens bevatten). Geef vervolgens op of deze als reguliere expressie moeten overeenkomen, geef op er hoofdlettergevoeligheid moet worden gebruikt, geef het minimum aantal exemplaren op en geef op of het exemplaar een unieke waarde moet hebben om in het aantal exemplaren te worden opgenomen.
        
    **Voorbeeld van de opties voor exemplaren**: u selecteert de ingebouwde optie voor het sociaal-fiscale nummer en stelt het minimum aantal exemplaren in op 2, en een document bevat hetzelfde sociaal-fiscale nummer twee keer. Als u **Count occurrences with unique values only (Alleen exemplaren met unieke waarden tellen)** instelt op **Aan**, wordt niet aan de voorwaarde voldaan. En als u deze optie instelt op **Uit**, wordt wel aan de voorwaarde voldaan.

5. Configureer op de blade **Label** het volgende en klik vervolgens op **Opslaan**:

    - Automatische of aanbevolen classificatie kiezen: selecteer voor **Selecteren hoe dit label wordt toegepast: automatisch of aanbevolen aan gebruiker** de optie **Automatisch** of **Aanbevolen**.

    - Geef de tekst voor de gebruikersprompt of beleidstip op: behoud de standaardtekst of geef uw eigen tekenreeks op.

6. Maak de wijzigingen beschikbaar voor gebruikers door op de blade **Azure Information Protection** op **Publiceren** te klikken.

## Informatie over de ingebouwde voorwaarden

Tijdens de evaluatieperiode kunt u de volgende voorwaarden selecteren:

- [SWIFT-code](#swift-code )

- [Creditcardnummer](#credit-card-number )

- [ABA-routenummer](#aba-routing-number )

- [Sociaal-fiscaal nummer (sofinummer)](#usa-social-security-number-ssn)

- [IBAN (International Banking Account Number)](#international-banking-account-number-iban)


### SWIFT-code

Dit informatietype komt overeen wanneer de inhoud het volgende bevat:  

1. Een van de volgende items: **swift**, **swiftnumber**, **swiftroutingnumber** 

2. Een SWIFT-code, in een opgemaakt patroon:  

    a. 4 letters (bankcode)  

    b. 2 letters (landcode)  

    c. 2 letters of cijfers (vestiging)  

    d. Optionele 3 letters of cijfers (filiaal)  


Voorbeelden voor het testen:

- **NEDSZAJJXXX Swiftroutingnumber**

- **NEDSZAJJ100 Swiftnumber** 

----


### Creditcardnummer

Dit informatietype komt overeen wanneer de inhoud het volgende bevat:  

- Een geldig creditcardnummer, in een opgemaakt of niet-opgemaakt patroon, dat voldoet aan de [Luhn-controle](https://wikipedia.org/wiki/Luhn_algorithm). Met dit informatietype worden kaarten van alle belangrijke merken over de hele wereld gedetecteerd, waaronder Visa, MasterCard, Discover Card, American Express en Diners.

    - **Opgemaakt**:
    
        - 16 cijfers: (xxxx-xxxx-xxxx-xxxx)  
        
    - **Niet-opgemaakt**:
    
        - (xxxxxxxxxxxxxxxx)  


Voorbeelden voor het testen:

- **4242-4242-4242-4242**

- **4242424242424242** 

----

### ABA-routenummer

Dit informatietype komt overeen wanneer de inhoud het volgende bevat:  

1. Ten minste een van de volgende items: **aba**, **rtn**, **routing number** 

2. Een ABA-routenummer dat negen cijfers in een opgemaakt of niet-opgemaakt patroon bevat: 

    - **Opgemaakt**: 
        
        a. Vier cijfers die beginnen met 0, 1, 2, 3, 6, 7 of 8 
        
        b. Een afbreekstreepje 
        
        c. Vier cijfers 
        
        d. Een afbreekstreepje 
        
        e. Een cijfer 
        
        Voorbeeld: 3456-9876-1 ABA 
        
    - **Niet-opgemaakt**: 
        
        Negen opeenvolgende cijfers die met 0, 1, 2, 3, 6, 7 of 8 beginnen 
        
        Voorbeeld: 345698761 RTN 
 

Voorbeelden voor het testen:

- **3456-9876-1 ABA**

- **345698761 RTN** 

----

### Sociaal-fiscaal nummer (sofinummer)

Dit informatietype komt overeen wanneer de inhoud het volgende bevat:  

1. Ten minste een van de volgende items: **ssn**, **social security**, **ssid**, **ss#** 

2. Een sociaal-fiscaal nummer: negen cijfers die een opgemaakt of niet-opgemaakt patroon kunnen hebben:

    - **Opgemaakt**: 
    
        - Negen cijfers in de volgende notatie: xxx-xx-xxxx OF xxx xx xxxx 
        
    - **Niet-opgemaakt**: 
    
        - Negen cijfers in de volgende notatie: xxxxxxxxx 


Voorbeelden voor het testen:

- **SSN 123-45-6789**

- **SS# 123456789** 


----

### IBAN (International Banking Account Number)

Dit informatietype komt overeen wanneer de inhoud het volgende bevat:  

1. Het volgende item: **IBAN** 

2. Een IBAN-nummer: begint met een landcode (twee letters), vervolgens controlecijfers (twee cijfers) en ten slotte bban-nummer (tot en met 30 cijfers).


Voorbeelden voor het testen:

- **GB29 NWBK 6016 1331 9268 19 IBAN**


## Volgende stappen

Gebruik de koppelingen in de sectie [Het beleid van uw organisatie configureren](configure-policy.md#configuring-your-organization-s-policy) voor meer informatie over het configureren van uw Azure Information Protection-beleid.  






<!--HONumber=Aug16_HO2-->


