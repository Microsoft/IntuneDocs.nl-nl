---
# required metadata

title: Rights Management-toepassing voor delen&colon; versiegeschiedenis van release | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 6751bd90-959f-4eba-91ed-6588ac983762

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Rights Management-toepassing voor delen: versiegeschiedenis van release

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management, Windows 10, Windows 7 met SP1, Windows 8, Windows 8.1*

Het Rights Management-team werkt de Rights Management-toepassing voor delen regelmatig bij voor oplossingen en nieuwe functies. Gebruik de volgende informatie om te zien wat er nieuw of gewijzigd is in een versie. De meest recente release wordt eerst weergegeven.

Versies vóór 1 januari 2015 worden niet weergegeven.

> [!NOTE]
> Hebt u feedback of een vraag over de RMS-toepassing voor delen? Stuur dan een e-mail naar [AskIPTeam](mailto:AskIPTeam@microsoft.com?subject=RMS%20sharing%20app:%20Feedback%20or%20question).

## Versie 1.0.2004.0
**Uitgebracht**: 11-12-2015

**Oplossingen**:

-   Alleen de bestandseigenaar en gebruikers met het machtigingsniveau **Mede-eigenaar** kunnen de beveiliging van bestanden opheffen. Voorheen was het zo dat de eigenaar en gebruikers met de machtigingsniveaus **Mede-auteur** en **Mede-eigenaar** de beveiliging van bestanden konden opheffen.

-   Systeemeigen beveiliging voor **.tif**-bestanden (in aanvulling op .tiff-bestanden) om een door RMS beveiligd, alleen-lezen **.ptif**-bestand te maken.

-   Verbeteringen voor foutberichten (nauwkeurige, heldere berichten).

-   Prestatieverbeteringen voor het versleutelen en ontsleutelen van inhoud.

**Nieuwe functies**:

-   Ondersteuning voor installatie door niet-beheerders, zodat standaardgebruikers de RMS-toepassing voor delen kunnen installeren.

    Er zijn enkele beperkingen voor standaardgebruikers met Office 2010. Zie voor meer informatie de sectie [Als u geen lokale beheerder bent en Office 2010 gebruikt](install-sharing-app.md#if-you-are-not-a-local-administrator-and-use-office-2010) in de gebruikersinstructies [De Rights Management-toepassing voor delen downloaden en installeren](install-sharing-app.md).

## Versie 1.0.1908.0
**Uitgebracht**: 16-9-2015

**Oplossingen**:

-   Ondersteuning voor Multi-factor Authentication (MFA) voor Azure RMS, waardoor toepassingen die gebruikmaken van moderne verificatie, niet langer afhankelijk zijn van de Microsoft-aanmeldhulp.

    Zie voor meer informatie de sectie [Multi-factor Authentication (MFA) en Azure RMS](../get-started/requirements-azure-ad.md#multi-factor-authentication-mfa-and-azure-rms) in [Vereisten voor Azure Rights Management](../get-started/requirements-azure-rms.md).

## Versie 1.0.1784.0
**Uitgebracht**: 30-7-2015

**Oplossingen**:

-   Het standaardvernieuwingsinterval voor rechtenbeleidssjablonen is verkort van 7 dagen tot 1 dag.

-   Klein aantal regressies en kleine fouten.

## Versie 1.0.1770.0
**Uitgebracht**: 25-4-2015

**Oplossingen**:

-   Nu kunnen alleen de eigenaar en mede-eigenaren beveiliging opheffen. Mede-auteurs kunnen de beveiliging niet opheffen.

-   Bestanden die zich op een netwerkshare bevinden, kunnen nu worden beveiligd.

**Nieuwe functies**:

-   Ondersteuning voor het bijhouden en intrekken van documenten. Zie [Uw documenten bijhouden en intrekken met gebruik van de RMS-toepassing voor delen](sharing-app-track-revoke.md) voor meer informatie..

-   Sjabloonondersteuning wanneer u kiest voor **Beveiligd delen**:

    -   U kunt nu sjablonen selecteren.

    -   In plaats van de schuifregelaar ziet u een lijst met sjablonen en aangepaste machtigingen.

    -   De opties **Gebruik op alle apparaten toestaan** en **Gebruiksbeperkingen afdwingen** worden niet meer weergegeven. In plaats daarvan wordt **Algemene beveiliging** automatisch geselecteerd, afhankelijk van het bestandstype.

    Zie [De opties in het dialoogvenster voor de Rights Management-toepassing voor delen](sharing-app-dialog-box.md) voor meer informatie.

## Versie 1.0.1667.0
**Uitgebracht**: 19-1-2015

**Oplossingen**:

-   Ondersteuning voor Chinese lettertypen in de PPDF-viewer van de RMS sharing-app.

-   Verbeterde foutafhandeling en -berichten.

-   Oplossing voor een probleem met de melding van automatische updates wanneer er een nieuwere versie van de app kan worden gedownload.

**Nieuwe functies**:

-   **Ondersteuning voor meerdere e-maildomeinen binnen uw organisatie**: als u AD RMS gebruikt en gebruikers in uw organisatie meerdere e-maildomeinen hebben, kunnen gebruikers met deze update inhoud gebruiken die beveiligd is door gebruikers in uw organisatie in andere domeinen. Zie voor meer informatie de sectie [Alleen AD RMS: ondersteuning voor meerdere e-maildomeinen binnen uw organisatie](sharing-app-admin-guide.md#ad-rms-only-support-for-multiple-email-domains-within-your-organization) in de [Beheerdershandleiding voor de Rights Management-toepassing voor delen](sharing-app-admin-guide.md).



<!--HONumber=Apr16_HO4-->


