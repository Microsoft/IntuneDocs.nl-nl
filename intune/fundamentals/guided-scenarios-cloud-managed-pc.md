---
title: 'Begeleid scenario: in de cloud beheerde moderne desktop'
titleSuffix: Microsoft Intune
description: Meer informatie over het begeleide scenario voor het instellen en configureren van een moderne basisdesktop vanuit de portal voor Microsoft 365-apparaatbeheer.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f78f3696827ebd50084f0e4b012c5f94427eeb35
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74164583"
---
# <a name="guided-scenario---cloud-managed-modern-desktop"></a>Begeleid scenario: in de cloud beheerde moderne desktop

De moderne desktop is het geavanceerde productiviteitsplatform voor de informatiemedewerker. Office 365 ProPlus en Windows 10 zijn de kernonderdelen van de moderne desktop, samen met de nieuwste beveiligingsbasislijnen voor Windows 10 en Microsoft Defender Advanced Threat Protection. 

Het beheer van de moderne desktop vanuit de cloud biedt internetbrede externe acties als extra voordeel. In cloudbeheer wordt gebruikgemaakt van het ingebouwde Windows Mobile Device Management-beleid en worden afhankelijkheden van het lokale Active Directory-groepsbeleid verwijderd. 

Voor het geval u een in de cloud beheerde moderne desktop wilt evalueren in uw eigen organisatie, zijn in dit begeleide scenario alle benodigde configuraties voor een basisimplementatie vooraf gedefinieerd. In dit begeleide scenario maakt u een veilige omgeving waarin u beheermogelijkheden voor Intune-apparaten kunt uitproberen. 

## <a name="prerequisites"></a>Vereisten
- [De MDM-instantie instellen op Intune](~/fundamentals/mdm-authority-set.md#set-mdm-authority-to-intune): Met de MDM-instantie (Mobile Device Management) wordt bepaald hoe u uw apparaten beheert. Als IT-beheerder moet u een MDM-instantie instellen voordat gebruikers apparaten voor beheer kunnen inschrijven.
- Minimaal M365 E3 (of M365 E5 voor de beste beveiliging)
- Windows 10 1903-apparaat (geregistreerd bij Windows Autopilot voor de beste ervaring voor eindgebruikers)
- Er zijn Intune-beheerdersmachtigingen vereist om dit begeleide scenario te voltooien:
  - Apparaatconfiguratie: lezen, maken, verwijderen, toewijzen en bijwerken
  - Inschrijvingsprogramma's: apparaat lezen, profiel lezen, profiel maken, profiel toewijzen, profiel verwijderen
  - Mobiele apps: lezen, maken, verwijderen, toewijzen en bijwerken
  - Organisatie: lezen en bijwerken
  - Beveiligingsbasislijnen: lezen, maken, verwijderen, toewijzen en bijwerken
  - Beleidssets: lezen, maken, verwijderen, toewijzen en bijwerken

## <a name="step-1---introduction"></a>Stap 1: inleiding

Met behulp van dit begeleide scenario stelt u een testgebruiker in, schrijft u een apparaat in bij Intune en implementeert u het apparaat met aanbevolen Intune-instellingen en met Windows 10 en Office ProPlus. Uw apparaat wordt ook geconfigureerd voor Microsoft Defender Advanced Threat Protection als u ervoor kiest om [deze beveiliging in te inschakelen in Intune](~/protect/advanced-threat-protection.md#enable-microsoft-defender-atp-in-intune). De gebruiker die u instelt en het apparaat dat u inschrijft worden toegevoegd aan een nieuwe beveiligingsgroep en geconfigureerd met de aanbevolen instellingen voor beveiliging en productiviteit. 

### <a name="what-you-will-need-to-continue"></a>Wat u nodig hebt om verder te gaan

U moet uw testapparaat en testgebruiker in dit begeleide scenario opgeven. Zorg ervoor dat u de volgende taken uitvoert:
- Stel een testgebruikersaccount in Azure Active Directory in.
- Maak een testapparaat met Windows 10, versie 1903 of later.
- (Optioneel) [Registreer het testapparaat bij Windows Autopilot](~/enrollment/enrollment-autopilot.md#add-devices).
- (Optioneel) [Schakel huisstijl in voor de Azure Active Directory-aanmeldingspagina van uw organisatie](https://go.microsoft.com/fwlink/?linkid=2102455).

## <a name="step-2---user"></a>Stap 2: gebruiker

Kies een gebruiker om in te stellen op het apparaat. Deze persoon wordt de primaire gebruiker van het apparaat.

Als u meer gebruikers of apparaten wilt toevoegen aan deze configuratie, voegt u de gebruikers en apparaten simpelweg toe aan de AAD-beveiligingsgroepen die worden gegenereerd door de wizard. In tegenstelling tot andere begeleide scenario's hoeft u de wizard niet meer dan één keer uit te voeren, aangezien de configuratie niet kan worden aangepast. U voegt gewoon meer gebruikers en apparaten toe aan de gemaakte AAD-groepen. Nadat u de wizard hebt voltooid, kunt u de groep weergeven die is gegenereerd met de geïmplementeerde aanbevolen beleidsregels. 

## <a name="step-3---device"></a>Stap 3: apparaat

Zorg ervoor dat op uw apparaat Windows 10, versie 1903 of later wordt uitgevoerd.  De primaire gebruiker moet het apparaat bij ontvangst instellen. Er zijn twee instelopties beschikbaar voor de gebruiker. 

### <a name="option-a--windows-autopilot"></a>Optie A: Windows Autopilot
Met Windows Autopilot wordt de configuratie van nieuwe apparaten geautomatiseerd, zodat gebruikers deze direct uit de doos kunnen instellen, zonder IT-assistentie. Als uw apparaat al is geregistreerd bij Windows Autopilot, selecteert u het via het serienummer. Zie [Apparaat registreren bij Windows Autopilot (optioneel)](~/fundamentals/guided-scenarios-cloud-managed-pc.md#register-device-with-windows-autopilot-optional) voor meer informatie over het gebruik van Windows Autopilot.

### <a name="option-b--manual-device-enrollment"></a>Optie B: handmatige inschrijving van apparaten
Gebruikers kunnen hun nieuwe apparaat handmatig instellen en inschrijven bij Mobile Device Management. Nadat u dit scenario hebt voltooid, stelt u het apparaat opnieuw in en geeft u de primaire gebruiker de inschrijvingsinstructies voor Windows-apparaten. Zie [Een Windows 10-apparaat toevoegen aan Azure AD tijdens de first-run experience](https://docs.microsoft.com/azure/active-directory/devices/azuread-joined-devices-frx#joining-a-device) voor meer informatie.

## <a name="step-4---review--create"></a>Stap 4: beoordelen en maken

In de laatste stap kunt u een samenvatting beoordelen van de instellingen die u hebt geconfigureerd. Nadat u uw keuzes hebt beoordeeld, klikt u op **Implementeren** om het begeleide scenario te voltooien. Zodra het begeleide scenario is voltooid, wordt er een tabel met resources weergegeven. U kunt deze resources later bewerken, maar bij het verlaten van de samenvattingsweergave wordt de tabel niet opgeslagen.

> [!IMPORTANT]
> Als het begeleide scenario is voltooid, wordt een samenvatting weergegeven. U kunt de resources in de samenvatting later wijzigen, maar de tabel waarin deze resources worden weergegeven, wordt niet opgeslagen.

### <a name="verification"></a>Verificatie
1. Controleren of het geselecteerde is toegewezen aan het gebruikersbereik van MDM
    - Zorg ervoor dat het [gebruikersbereik van MDM](~/enrollment/windows-enroll.md#enable-windows-10-automatic-enrollment) is:
        - Ingesteld op **Alle** voor de app **Microsoft Intune** of,
        - Ingesteld op **Sommige**. Voeg ook de gebruikersgroep toe die is gemaakt in dit begeleide scenario.
2. Controleer of de geselecteerde gebruiker apparaten kan toevoegen aan Azure Active Directory.
    - Zorg ervoor dat AAD-deelname is:
        - Ingesteld op **Alle** of,
        - Ingesteld op **Sommige**. Voeg ook de gebruikersgroep toe die is gemaakt in dit begeleide scenario.
3. Volg de relevante stappen op het apparaat om het toe te voegen aan Azure AD op basis van het volgende:
    - Met Autopilot. Zie [Windows Autopilot-gebruikersmodus](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven) voor meer informatie.
    - Zonder Autopilot: Zie [Een Windows 10-apparaat toevoegen aan Azure AD tijdens de first-run experience](https://docs.microsoft.com/azure/active-directory/devices/azuread-joined-devices-frx#joining-a-device) voor meer informatie.

### <a name="what-happens-when-i-click-deploy"></a>Wat gebeurt er als ik op Implementeren klik?
De gebruiker en het apparaat worden toegevoegd aan nieuwe beveiligingsgroepen. Deze worden ook geconfigureerd met voor Intune aanbevolen instellingen voor beveiliging en productiviteit op het werk of op school. Nadat de gebruiker het apparaat aan Azure AD heeft toegevoegd, worden er extra apps en instellingen aan het apparaat gekoppeld. Zie voor meer informatie over deze aanvullende configuraties [Quickstart: uw Windows 10-apparaat inschrijven](~/enrollment/quickstart-enroll-windows-device.md).

## <a name="additional-information"></a>Aanvullende informatie

### <a name="register-device-with-windows-autopilot-optional"></a>Het apparaat registreren bij Windows Autopilot (optioneel)

U kunt desgewenst kiezen voor het gebruik van een geregistreerd Autopilot-apparaat. Voor Autopilot wordt in dit begeleide scenario een Autopilot-implementatieprofiel en een profiel voor de pagina Status van de inschrijving toegewezen. Het Autopilot-implementatieprofiel wordt als volgt geconfigureerd:
- Gebruikersmodus, wat inhoudt dat de eindgebruiker de gebruikersnaam en het wachtwoord moet invoeren tijdens Windows Setup.
- Azure AD-deelname.
- Pas de Windows Setup aan:
  - Verberg het scherm met de licentievoorwaarden voor Microsoft-software
  - Verberg de privacyinstellingen 
  - Maak het lokale profiel van de gebruiker zonder lokale beheerdersbevoegdheden
  - Verberg de opties voor het wijzigen van het account op de aanmeldingspagina van het bedrijf

De pagina Inschrijvingsstatus wordt zo geconfigureerd dat deze alleen wordt ingeschakeld voor Autopilot-apparaten en niet wordt geblokkeerd tot alle apps zijn geïnstalleerd.

In het begeleide scenario wordt de gebruiker ook toegewezen aan het geselecteerde Autopilot-apparaat voor een persoonlijke Setup-ervaring.

#### <a name="post-requisites"></a>Navolgende vereisten
Zodra de gebruiker het apparaat heeft toegevoegd aan Azure Active Directory worden de volgende configuraties toegepast op het apparaat:
1. Office 365 ProPlus wordt automatisch geïnstalleerd op de in de cloud beheerde pc. Hierin bevinden zich vertrouwde toepassingen als Access, Excel, OneNote, Outlook, PowerPoint, Publisher, Skype voor Bedrijven en Word. U kunt deze toepassingen gebruiken om verbinding te maken met Office 365-services zoals SharePoint Online, Exchange Online en Skype voor Bedrijven Online. Office 365 ProPlus wordt regelmatig bijgewerkt met nieuwe functies, in tegenstelling tot niet-abonnementsversies van Office. Zie Nieuwe functies in Office 365 voor een lijst met nieuwe functies.
2. Er worden Windows-beveiligingsbasislijnen geïnstalleerd op de in de cloud beheerde pc. Als u Microsoft Defender Advanced Threat Protection hebt ingesteld, worden in het begeleide scenario ook basislijninstellingen voor Defender geconfigureerd. Defender Advanced Threat Protection biedt een nieuwe beveiligingslaag na schending in de Windows 10-beveiligingsstack. Met een combinatie van clienttechnologie die is ingebouwd in Windows 10 en een robuuste cloudservice helpt deze laag bij het detecteren van bedreigingen die door andere beveiligingsmethoden heen zijn gekomen. 

## <a name="next-steps"></a>Volgende stappen

- Als u Microsoft Defender Advanced Threats Detection wilt gebruiken, moet u [Intune-nalevingsbeleid maken](~/protect/advanced-threat-protection.md#create-and-assign-the-compliance-policy) om Defender Threat Analysis te laten voldoen aan de vereisten.
- Maak [beleid voor voorwaardelijke toegang op basis van het apparaat](~/protect/advanced-threat-protection.md#create-a-conditional-access-policy) om de toegang te blokkeren als het apparaat niet voldoet aan de Intune-vereisten.
