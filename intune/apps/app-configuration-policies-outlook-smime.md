---
title: S/MIME configureren met Outlook voor iOS in Microsoft Intune
description: Informatie over S/MIME met Outlook voor iOS in Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lance
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c9572f4accb1be232d4667d99b98beff90d81379
ms.sourcegitcommit: edd06a494a241d198ca9b0d3030c92195976e0d3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2019
ms.locfileid: "75000411"
---
# <a name="configure-smime-with-outlook-for-ios"></a>S/MIME configureren met Outlook voor iOS

Secure/Multipurpose Internet Mail Extensions (S/MIME) biedt een extra beveiligingslaag voor e-mail die wordt verzonden naar en vanaf een EAS-account (Exchange ActiveSync). [Microsoft Outlook](https://aka.ms/omsmime) kan gebruikmaken van S/MIME om gebruikers toe te staan zowel uitgaande berichten als bijlagen te versleutelen, zodat alleen de bedoelde ontvanger berichtinhoud kan lezen en openen wanneer deze een Office 365-account gebruikt. Gebruikers kunnen een bericht ook digitaal ondertekenen, zodat de ontvangers de identiteit van de afzender kunnen verifiëren en bevestigen dat er niet met het bericht is geknoeid. Van deze mogelijkheid kan gebruik worden gemaakt door middel van certificaten. Zie [Understanding S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)?redirectedfrom=MSDN) (Informatie over S/MIME) voor meer informatie.

> [!NOTE]
> Deze functie is vertraagd, maar wordt binnenkort vrijgegeven.

> [!NOTE]
> In dit onderwerp wordt beschreven hoe u vertrouwde basiscertificaten kunt implementeren via [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431). Microsoft Endpoint Manager is een zelfstandig, geïntegreerd eindpuntbeheerplatform voor het beheren van al uw eindpunten. In dit Microsoft Endpoint Manager-beheercentrum is ConfigMgr en Microsoft Intune geïntegreerd.

## <a name="about-message-encryption"></a>Berichtversleuteling
Gebruikers kunnen een versleuteld bericht verzenden naar personen in zowel de eigen organisatie als daarbuiten als ze over het openbare gedeelte van de versleutelingscertificaten beschikken. Persoonlijke sleutels met versleutelingscertificaten moeten altijd worden beveiligd door de ontvanger van het versleutelde bericht. De persoonlijke sleutel van het versleutelingscertificaat wordt gebruikt om het bericht door de ontvanger te laten ontsleutelen.

Versleutelde berichten kunnen alleen worden gelezen door ontvangers met het certificaat dat overeenkomt met het certificaat waarmee het bericht is versleuteld. Als u een versleuteld bericht probeert te verzenden naar een of meer ontvangers waarvan het versleutelingscertificaat niet beschikbaar is, wordt u gevraagd deze ontvangers te verwijderen voordat u het e-mailbericht verzendt.

## <a name="about-digital-signatures"></a>Digitale handtekeningen
Een digitaal ondertekend bericht garandeert de ontvanger dat er niet met het bericht is geknoeid en dat de identiteit van de afzender authentiek is. Ontvangers kunnen de digitale handtekening alleen controleren als ze een e-mailclient gebruiken die ondersteuning biedt voor S/MIME.

## <a name="prerequisites"></a>Vereisten
- Outlook voor iOS ondersteunt alleen S/MIME voor Office 365-accounts.
- S/MIME moet worden geconfigureerd voor Office 365. Zie [S/MIME in Office 365 configureren](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/How-to-Configure-S-MIME-in-Office-365/ba-p/584516) voor meer informatie.
- Er moet een certificeringsinstantie zijn die certificaten kan uitgeven die voor ondertekening en versleuteling kunnen worden gebruikt.
- Implementeer vertrouwde basiscertificaten via Endpoint Manager. Zie [Vertrouwde certificaatprofielen maken](~/protect/certificates-configure.md#create-trusted-certificate-profiles) voor meer informatie.
- Versleutelingscertificaten moeten worden geïmporteerd in Endpoint Manager. Zie [Geïmporteerde PKCS-certificaten configureren en gebruiken met Intune](~/protect/certificates-imported-pfx-configure.md) voor meer informatie.
- PFX-connector voor Microsoft Intune installeren en configureren. Zie [De PFX-certificaatconnector voor Microsoft Intune downloaden, installeren en configureren](~/protect/certificates-imported-pfx-configure.md#download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune) voor meer informatie.
- Apparaten moeten worden ingeschreven bij MDM voor het automatisch ontvangen van vertrouwde basis- en S/MIME-certificaten van Endpoint Manager.

> [!IMPORTANT]
> U moet de bijgewerkte PFX-connector (versie 6.1911.11.0 of hoger) downloaden en installeren zodat Microsoft Intune S/MIME-versleutelingscertificaten kan gebruiken voor Outlook voor iOS.

## <a name="smime-support-in-outlook-for-ios"></a>S/MIME-ondersteuning in Outlook voor iOS
Outlook voor iOS ondersteunt S/MIME-ondertekening en -versleuteling van berichten met behulp van certificaten. Veel klanten hebben afzonderlijke handtekening- en versleutelingscertificaten in plaats van één certificaat dat zowel ondertekening als versleuteling ondersteunt. De ingeschreven apparaten van een individuele gebruiker hebben gewoonlijk een uniek handtekeningcertificaat, terwijl versleutelingscertificaten worden gedeeld over de ingeschreven apparaten van een individuele gebruiker. Vaak hebben gebruikers jarenlang van S/MIME gebruikgemaakt en hebben ze in de loop van de tijd verschillende versleutelingscertificaten gebruikt als de certificaten worden vernieuwd. De geschiedenis van een versleutelingscertificaat, inclusief de persoonlijke sleutels, moet aanwezig zijn op het apparaat van de gebruiker, zodat eventueel versleutelde e-mail met een van deze certificaten uit het verleden kan worden gelezen. Het is ook mogelijk om één certificaat te hebben dat ondersteuning biedt voor ondertekening en versleuteling.

Outlook voor iOS ondersteunt twee manieren om certificaten aan apparaten te leveren, zodat deze voor S/MIME kunnen worden gebruikt:

- **Gebruikers** kunnen S/MIME-certificaten per e-mail naar zichzelf sturen en ze in Outlook voor iOS vanuit een bijlage op hun mobiele apparaten installeren.
- **Beheerders** kunnen geschiedenissen van versleutelingscertificaten vanuit een willekeurige certificeringsinstantie importeren in Endpoint Manager. Endpoint Manager levert vervolgens automatisch die certificaten aan elk apparaat dat door de gebruiker wordt ingeschreven. In het algemeen wordt SCEP (Simple Certificate Enrollment Protocol) gebruikt voor het ondertekenen van certificaten. Met SCEP wordt de persoonlijke sleutel gegenereerd en opgeslagen op het ingeschreven apparaat en wordt er een uniek certificaat afgeleverd bij elk apparaat dat een gebruiker inschrijft, en dat kan worden gebruikt voor onweerlegbaarheid. Beheerders importeren voor hun gebruikers geschiedenissen van versleutelingscertificaten in Endpoint Manager, dat vervolgens alle versleutelingscertificaten van de gebruiker levert aan elk apparaat dat ze inschrijven. Ten slotte ondersteunt Endpoint Manager afgeleide referenties voor klanten die ondersteuning nodig hebben voor de NIST 800-157-standaard. Op iOS wordt de bedrijfsportal gebruikt om handtekening- en versleutelingscertificaten uit Intune op te halen.

## <a name="configuring-outlook-for-ios-smime-in-endpoint-manager"></a>Outlook voor iOS S/MIME configureren in Endpoint Manager
Als u Outlook voor iOS S/MIME in Endpoint Manager wilt configureren, inclusief het automatisch leveren van S/MIME-certificaten die door Outlook voor iOS kunnen worden gebruikt, voert u de volgende stappen uit:

### <a name="add-the-microsoft-outlook-app"></a>De Microsoft Outlook-app toevoegen
1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Voeg de Microsoft Outlook voor iOS-app vanuit de App Store toe aan Endpoint Manager of synchroniseer Outlook voor iOS vanuit het Apple Volume Purchase Program. Zie [iOS- en macOS-apps uit de App Store toevoegen aan Microsoft Intune](~/apps/store-apps-ios.md) en [iOS- en macOS-apps beheren die zijn aangeschaft via een Apple Volume Purchase Program met Microsoft Intune](~/apps/vpp-apps-ios.md) voor meer informatie.

### <a name="create-the-outlook-for-ios-smime-configuration-policy"></a>S/MIME-configuratiebeleid voor Outlook voor iOS maken

Met de volgende stappen kunt u het S/MIME-beleid voor Outlook voor iOS in Endpoint Manager maken en configureren. Deze instellingen bieden een geautomatiseerde levering van de handtekening- en versleutelingscertificaten.

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en selecteer **Apps** > **App-configuratiebeleid** > **Toevoegen**.<br>
Het deelvenster **Configuratiebeleid toevoegen** wordt weergegeven.
2. Voer de **naam** en **beschrijving** van het configuratiebeleid in.
3. Selecteer **Beheerde apparaten** als **Type apparaatregistratie**.
4. Selecteer **iOS/iPadOS** als **Platform**.
5. Klik op **Selecteer de vereiste app** om de Microsoft Outlook voor iOS-app die u eerder hebt toegevoegd, te zoeken en te koppelen. 
6. Klik op **Configuratie-instellingen** om configuratie-instellingen toe te voegen. 
    - Selecteer **Configuratieontwerper gebruiken** naast **Indeling van de configuratie-instellingen** en accepteer de standaardinstellingen. Zie [Configuratie-instellingen voor Microsoft Outlook](~/apps/app-configuration-policies-outlook.md) voor meer informatie.
7. Klik op **S/MIME** om de **S/MIME-instellingen voor Outlook** weer te geven.
8. Stel **S/MIME inschakelen** in op **Ja**.
9. Stel **S/MIME-certificaten implementeren via Intune** in op **ja**.
10. Kies onder **Handtekeningcertificaten**, naast **Type van het certificaatprofiel**, een van de volgende opties:
    - **SCEP**: maakt een certificaat dat uniek is voor het apparaat en de gebruiker die door Microsoft Outlook voor ondertekening kan worden gebruikt. Zie [Infrastructuur configureren voor ondersteuning van SCEP met Intune](~/protect/certificates-scep-configure.md) en [Een SCEP-certificaatprofiel maken](~/protect/certificates-profile-scep.md#create-a-scep-certificate-profile) voor meer informatie. 
    - **PKCS geïmporteerde certificaten**: maakt gebruik van een certificaat dat uniek is voor de gebruiker, maar dat kan worden gedeeld op verschillende apparaten en dat namens de gebruiker door de beheerder in Endpoint Manager is geïmporteerd. Het certificaat wordt geleverd op elk apparaat dat door een gebruiker wordt ingeschreven. Endpoint Manager kiest automatisch het geïmporteerde certificaat dat ondersteuning biedt voor ondertekening voor levering aan het apparaat dat met de ingeschreven gebruiker overeenkomt.
    - **Afgeleide referenties**: maakt gebruik van een certificaat dat zich al op het apparaat bevindt dat voor ondertekening kan worden gebruikt. Het certificaat moet worden opgehaald op het apparaat met behulp van de afgeleide referentiestromen in Intune.
11. Kies onder **Versleutelingscertificaten**, naast **Type van het certificaatprofiel**, een van de volgende opties:
    - **PKCS geïmporteerde certificaten**: levert versleutelingscertificaten die door de beheerder op elk apparaat dat door een gebruiker wordt geregistreerd, in Endpoint Manager zijn geïmporteerd. Endpoint Manager kiest automatisch een of meer geïmporteerde certificaten die versleuteling ondersteunen voor levering aan het apparaat dat met de ingeschreven gebruiker overeenkomt.
    - **Afgeleide referenties**: maakt gebruik van een certificaat dat zich al op het apparaat bevindt dat voor ondertekening kan worden gebruikt. Het certificaat moet worden opgehaald op het apparaat met behulp van de afgeleide referentiestromen in Intune.
12. Naast **Meldingen voor eindgebruikers** kiest u ervoor eindgebruikers op de hoogte te stellen door **Bedrijfsportal** of **E-mail** te selecteren om S/MIME-certificaten voor Outlook voor iOS op te halen.

    Op iOS moeten gebruikers de app Bedrijfsportal gebruiken om hun S/MIME-certificaten op te halen. Endpoint Manager stelt de gebruiker op de hoogte dat ze de bedrijfsportal moeten starten om hun S/MIME-certificaten op te halen via de sectie Meldingen van Bedrijfsportal, een pushmelding en/of een e-mailbericht. Als de gebruiker op een van de meldingen klikt, wordt de landingspagina geopend, waarop de voortgang van het ophalen van de certificaten wordt weergegeven. Zodra de certificaten zijn opgehaald, kan de gebruiker S/MIME gebruiken in Microsoft Outlook voor iOS om e-mail te ondertekenen en versleutelen.
    
    De meldingen voor eindgebruikers bevatten de volgende opties:
       - **Bedrijfsportal**: als deze is geselecteerd, ontvangen gebruikers een pushmelding op hun apparaat, waarna de landingspagina in Bedrijfsportal wordt geopend, waar S/MIME-certificaten worden opgehaald.
        - **E-mail**: stuurt een e-mailbericht naar de eindgebruiker om deze te informeren dat Bedrijfsportal moet worden gestart om de S/MIME-certificaten op te halen. Als de gebruiker zich op een ingeschreven iOS-apparaat bevindt wanneer ze op de koppeling in het e-mail bericht klikken, wordt hij of zij omgeleid naar de Bedrijfsportal om de certificaten op te kunnen halen.
    
13. Selecteer **Toewijzingen** om het beleid voor configuratie van apps toe te wijzen aan de Azure AD-groepen. Zie [Apps aan groepen toewijzen met Microsoft Intune](~/apps/apps-deploy.md) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

- Zie [App-configuratiebeleidsregels voor Microsoft Intune](app-configuration-policies-overview.md) voor meer informatie.
