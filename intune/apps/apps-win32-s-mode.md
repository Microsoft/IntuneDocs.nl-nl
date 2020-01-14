---
title: Win32-apps inschakelen op S-modusapparaten
titleSuffix: Microsoft Intune
description: Meer informatie over het inschakelen van Win32-apps op S-modusapparaten met behulp van Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4b2a6019a0af33cd227d88444bb5ddda5bc22715
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75204898"
---
# <a name="enable-win32-apps-on-s-mode-devices"></a>Win32-apps inschakelen op S-modusapparaten

[Windows 10 S-modus](https://docs.microsoft.com/windows/deployment/s-mode) is een vergrendeld besturingssysteem dat alleen Store-apps uitvoert. Op Windows S-apparaten kunnen standaard geen Win32-apps worden geïnstalleerd en uitgevoerd. Deze apparaten bevatten één *Win 10S-basisbeleid*, waardoor het S-modusapparaat geen Win32-apps kan uitvoeren. Door echter een aanvullend **S-modusbeleid** te maken en te gebruiken in Intune, kunt u Win32-apps installeren en uitvoeren op beheerde Windows 10 S-modusapparaten. Met de PowerShell-hulpprogramma's van [Microsoft Defender Application Control (WDAC)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) kunt u een of meer aanvullende beleidsregels maken voor de Windows S-modus. U moet het aanvullende beleid ondertekenen met de [Device Guard Signing service (DGSS)](https://go.microsoft.com/fwlink/?linkid=2095629) of met [SignTool.exe](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/signing-policies-with-signtool) en vervolgens het beleid uploaden en distribueren via Intune. Als alternatief kunt u het aanvullende beleid ondertekenen met een codesigning-certificaat van uw organisatie, maar de voorkeur gaat uit naar DGSS. In het geval dat u het codesigning-certificaat van uw organisatie gebruikt, moet het basiscertificaat waaraan het codesigning-certificaat is gekoppeld, aanwezig zijn op het apparaat.

Door het aanvullende beleid voor de S-modus toe te wijzen in Intune, stelt u het apparaat in staat een uitzondering te maken op het bestaande S-modusbeleid van het apparaat, waardoor de geüploade bijbehorende ondertekende app-catalogus kan worden gebruikt. Het beleid stelt een lijst met toegestane apps in (de app-catalogus) die op het S-modusapparaat kan worden gebruikt.

> [!NOTE]
> Win32-apps op S-modus apparaten worden alleen ondersteund in de Windows 10-update van november 2019 (build 18363) of latere versies.

<!-- Add WDAC tooling diagram  -->

De stappen voor het uitvoeren van Win32-apps op een Windows 10-apparaat in de S-modus zijn als volgt:

1. Schakel S-modusapparaten in via Intune als onderdeel van het inschrijfproces van Windows 10 S.
2. Een aanvullend beleid maken om Win32-apps toe te staan:
   - U kunt [Microsoft Defender Application Control (WDAC)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)-hulpprogramma's gebruiken om een aanvullend beleid te maken. De basis-beleids-id binnen het beleid moet overeenkomen met de basis-beleids-id van het S-modusapparaat (die hard is gecodeerd op de client). Zorg er ook voor dat de versie van het beleid hoger is dan de vorige versie.
   - U gebruikt DGSS om uw aanvullende beleid te ondertekenen. Zie voor meer informatie [Sign code integrity policy with Device Guard signing](https://docs.microsoft.com/microsoft-store/sign-code-integrity-policy-with-device-guard-signing) (code-integriteitsbeleid ondertekenen met Device Guard-ondertekening).
   - U uploadt het ondertekende aanvullende beleid naar Intune door een aanvullende beleidsregel voor Windows 10 S-modus te maken (zie hieronder).
3. U staat Win32-app-catalogi toe via Intune:
   - U maakt catalogusbestanden (1 voor elke app) en ondertekent deze met DGSS of een andere certificaatinfrastructuur.
   - U verpakt de ondertekende catalogus in het *.intunewin*-bestand met behulp van de [Microsoft Win32 Content Prep Tool](https://go.microsoft.com/fwlink/?linkid=2065730). Zie voor meer informatie [Win32 app management - Prepare the Win32 app content for upload](~/apps/apps-win32-app-management.md#prepare-the-win32-app-content-for-upload) (de inhoud van de Win32-app voorbereiden voor uploaden).
   - Intune past de ondertekende app-catalogus toe om de Win32-app op het S-modusapparaat te installeren met behulp van de [Intune Management-extensie](~/apps/intune-management-extension.md).

> [!NOTE]
> Line-of-Business (LOB) `.appx`- en `.appx`-bundels in Windows 10 S-modus worden ondersteund via ondertekening van Microsoft Store for Business (MSFB).
>
> **Aanvullend S-modusbeleid** voor apps moet worden geleverd via Intune Management Extension.
>
> S-modusbeleidsregels worden afgedwongen op apparaatniveau. Meerdere gerichte beleidsregels worden samengevoegd op het apparaat. Het samengevoegde beleid wordt afgedwongen op het apparaat.

Gebruik de volgende stappen om een aanvullende beleidsregel voor Windows 10 S-modus te maken:

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Aanvullende beleidsregels S-modus** > **Beleid maken**.
3. Voordat u het **Beleidsbestand** kunt toevoegen, moet u het maken en ondertekenen. Zie voor meer informatie:
    - [Create a WDAC policy using PowerShell tools and convert it to a binary format](https://go.microsoft.com/fwlink/?linkid=2095387) (een WDAC-beleid maken en converteren naar een binaire indeling)
    - [Meld u aan met de Device Guard-ondertekeningsservice](https://go.microsoft.com/fwlink/?linkid=2095629) **(aanbevolen)**

4. Voeg op de pagina **Basisinformatie** de volgende waarden toe:

    | Waarde | Beschrijving |
    |--------------|------------------------------------------------|
    | Beleidsbestand | Het bestand dat het WDAC-beleid bevat. |
    | Naam | De naam van dit beleid. |
    | Beschrijving | [Optioneel] De beschrijving van dit beleid. |

5. Klik op **Volgende: Bereiktags**.<br>
   Op de pagina **Bereiktags** kunt u desgewenst bereiktags configureren om te bepalen wie het app-beleid in Intune kan zien. Zie [Use role-based access control and scope tags for distributed IT](~/fundamentals/scope-tags.md) (Op rollen gebaseerd toegangsbeheer en bereiktags gebruiken voor gedistribueerde IT) voor meer informatie over bereiktags.

6. Klik op **Volgende: toewijzingen**.<br>
   Op de pagina **Toewijzingen** kunt u het beleid toewijzen aan gebruikers en apparaten. Het is belangrijk dat u weet dat u een beleid kunt toewijzen aan een apparaat, ongeacht of het apparaat wordt beheerd in Intune.
7. Klik op **Volgende: beoordelen en maken** om de waarden te controleren die u hebt ingevoerd voor het profiel.
8. Wanneer u klaar bent, klikt u op **Maken** om het aanvullende S-modusbeleid in Intune te maken. 

Nadat het beleid is gemaakt, wordt het toegevoegd aan de lijst met aanvullende S-modusbeleidsregels in Intune. Nadat het beleid is toegewezen, wordt het beleid geïmplementeerd op de apparaten. Houd er rekening mee dat u de app in dezelfde beveiligingsgroep moet implementeren als het aanvullende beleid. U kunt beginnen met het toewijzen van doelen en apps aan deze apparaten. Hierdoor kunnen uw eindgebruikers de apps op de S-modusapparaten installeren en uitvoeren.

## <a name="removal-of-s-mode-policy"></a>S-modusbeleid verwijderen

Om het aanvullende S-modusbeleid van het apparaat te verwijderen, moet u momenteel een leeg beleid toewijzen en implementeren om het bestaande aanvullende S-modusbeleid te overschrijven.

## <a name="policy-reporting"></a>Beleidsrapportage

Het aanvullende S-modusbeleid, dat wordt afgedwongen op apparaatniveau, heeft alleen rapportage op apparaatniveau. Er is rapportage op apparaatniveau beschikbaar voor succes- en foutcondities. 

Rapportagewaarden die worden weergegeven in de Intune-console voor S-modusrapportagebeleid:
- **Geslaagd**: Het aanvullende S-modusbeleid is van kracht.
- **Onbekend**: De status van het aanvullende S-modusbeleid is niet bekend.
- **TokenError**: Het aanvullende S-modusbeleid is structureel in orde, maar er is een fout opgetreden bij het autoriseren van het token.
- **NotAuthorizedByToken**: Het token autoriseert dit aanvullende S-modusbeleid niet.
- **PolicyNotFound**: Het aanvullende S-modusbeleid kan niet worden gevonden.

## <a name="next-steps"></a>Volgende stappen

- Zie [Win32-apps in S-modus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/lob-win32-apps-on-s) voor meer informatie.
- Zie [Apps toevoegen aan Microsoft Intune](apps-add.md) voor meer informatie over apps toevoegen aan Intune.
- Zie [Intune Win32 app-beheer](~/apps/apps-win32-app-management.md) voor meer informatie over Win32-apps.
