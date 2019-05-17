---
title: Nalevingsinstellingen voor iOS-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een overzicht van alle instellingen die u kunt gebruiken bij het instellen van naleving voor uw iOS-apparaten in Microsoft Intune. Een e-mailprofiel vereisen, controleren op opengebroken of geroote apparaten, de toegestane minimum- en maximumversie van het besturingssysteem instellen, wachtwoordbeperkingen instellen, waaronder wachtwoordlengte en de inactiviteit van apparaten, apps beperken en meer.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ec071622a2e0d49068864f8bfb47954f54c8ba4
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423608"
---
# <a name="ios-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>iOS-instellingen om te markeren of apparaten wel of niet conform zijn met behulp van Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Dit artikel bevat een overzicht en beschrijving van de verschillende nalevingsinstellingen die u kunt configureren op iOS-apparaten in Intune. Gebruik deze instellingen als onderdeel van uw MDM-oplossing (Mobile Device Management) om een e-mailprofiel te vereisen, geroote (opengebroken) apparaten als niet-conform te markeren, een toegestaan bedreigingsniveau in te stellen, in te stellen dat wachtwoorden verlopen en meer.

Deze functie is van toepassing op:

- iOS

Gebruik deze nalevingsinstellingen als Intune-beheerder om de resources van uw organisatie beter te beschermen. Zie [Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md) voor meer informatie over nalevingsbeleid en wat dit doet.

## <a name="before-you-begin"></a>Voordat u begint

[Een nalevingsbeleid maken](create-compliance-policy.md#create-the-policy). Selecteer voor **Platform** de optie **iOS**.

## <a name="email"></a>E-mail

- **Vereisen dat mobiele apparaten een beheerd e-mailprofiel hebben**: Als **Vereisen** is ingesteld, worden apparaten die geen e-mailprofiel hebben dat door Intune wordt beheerd als niet-conform gezien. Een apparaat kan geen beheerd e-mailprofiel hebben als het niet correct is gekoppeld of als de gebruiker het e-mailaccount handmatig op het apparaat heeft ingesteld. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.

  Het apparaat wordt in de volgende situaties beschouwd als niet-conform:

  - Het e-mailprofiel is toegewezen aan een andere gebruikersgroep dan de gebruikersgroep waarvoor het nalevingsbeleid is bedoeld.
  - De gebruiker heeft al een e-mailaccount op het apparaat ingesteld dat overeenkomt met het Intune-e-mailprofiel dat op het apparaat is geïmplementeerd. Het profiel dat door de gebruiker is geconfigureerd, kan niet worden overschreven en worden beheerd door Intune. De eindgebruiker moet de bestaande e-mailinstellingen verwijderen om aan het beleid te voldoen. Daarna kan Intune het beheerde e-mailprofiel installeren.

- **Selecteer het e-mailprofiel dat moet worden beheerd door Intune**: Als de instelling **E-mailaccount moet worden beheerd door Intune** is geselecteerd, kiest u **Selecteren** om het e-mailprofiel voor Intune in te voeren. Het e-mailprofiel moet bestaan op het apparaat.

Zie [De toegang tot zakelijke e-mail configureren met e-mailprofielen bij Intune](email-settings-configure.md) voor meer informatie over e-mailprofielen.

## <a name="device-health"></a>Device health

- **Opengebroken apparaten**: Kies **Blokkeren** om geroote (opengebroken) apparaten als niet-conform te markeren. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.
- **Vereisen dat het apparaat het apparaatdreigingsniveau niet overschrijdt** (iOS 8.0 en hoger): gebruik deze instelling om de risicobeoordeling als voorwaarde voor naleving te gebruiken. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving. Als u deze instelling wilt gebruiken, kiest u het toegestane bedreigingsniveau:
  - **Beveiligd**: deze optie is het veiligst en betekent dat het apparaat geen bedreigingen kan hebben. Als een van de bedreigingsniveaus voor het apparaat wordt gedetecteerd, wordt het apparaat geëvalueerd als niet-conform.
  - **Laag**: het apparaat wordt als compatibel geëvalueerd als er bedreigingen van een laag niveau aanwezig zijn. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld**: Het apparaat wordt als compatibel geëvalueerd als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als bedreigingen met hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-conform beoordeeld.
  - **Hoog**: deze optie is het minst veilig, omdat alle bedreigingsniveaus zijn toegestaan. Deze optie kan handig zijn als u deze alleen gebruikt voor rapportagedoeleinden.

## <a name="device-properties"></a>Apparaateigenschappen

- **Minimale versie van het besturingssysteem die is vereist** (iOS 8.0 en hoger): wanneer een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt dit apparaat gerapporteerd als niet-conform. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De eindgebruiker kan kiezen om het apparaat bij te werken. Daarna zijn de resources van de organisatie toegankelijk.
- **Maximale versie van het besturingssysteem die is toegestaan** (iOS 8.0 en hoger): Als een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie in de regel, wordt de toegang tot organisatieresources geblokkeerd. De eindgebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Op dit apparaat kan geen toegang worden verkregen tot organisatieresources zolang een regel niet zodanig is gewijzigd dat de versie van het besturingssysteem is toegestaan.
- **Minimale versie van OS-build** (iOS 8.0 en later): Als Apple beveiligingsupdates publiceert, wordt het buildnummer meestal bijgewerkt, niet de versie van het besturingssysteem. Gebruik deze functie om het buildnummer in te voeren dat minimaal is toegestaan op het apparaat.
- **Maximale versie van OS-build** (iOS 8.0 en later): Als Apple beveiligingsupdates publiceert, wordt het buildnummer meestal bijgewerkt, niet de versie van het besturingssysteem. Gebruik deze functie om het buildnummer in te voeren dat maximaal is toegestaan op het apparaat.

## <a name="system-security"></a>Systeembeveiliging

### <a name="password"></a>Wachtwoord

> [!NOTE]
> Nadat een nalevings- of configuratiebeleid op een iOS-apparaat is toegepast, wordt gebruikers elke vijftien minuten gevraagd een wachtwoordcode in te stellen. Gebruikers wordt continu gevraagd een wachtwoordcode in te stellen totdat de code is ingesteld.

- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**: **verplicht** gebruikers een wachtwoord in te voeren om toegang te krijgen tot hun apparaat. iOS-apparaten die gebruikmaken van een wachtwoord, zijn versleuteld.
- **Eenvoudige wachtwoorden**: stel deze optie in op **Blokkeren** zodat de gebruiker geen eenvoudig wachtwoord kan maken, zoals **1234** of **1111**. Stel deze optie in op **Niet geconfigureerd** om gebruikers toe te staan wachtwoorden als **1234** of **1111** te maken.
- **Minimale wachtwoordlengte**: voer het minimale aantal cijfers of tekens aan waaruit het wachtwoord moet bestaan.
- **Vereist wachtwoordtype**: kies of een wachtwoord alleen **numerieke** tekens mag bevatten of uit een combinatie van cijfers en andere tekens moet bestaan (**alfanumeriek**).
- **Het minimumaantal niet-alfanumerieke tekens in een wachtwoord**: voer het minimale aantal speciale tekens (zoals `&`, `#`, `%`, `!` enzovoort) in dat het wachtwoord moet bevatten.

    Als u een hogere waarde instelt, moet de gebruiker een wachtwoord maken dat complexer is.

- **Maximum aantal minuten van inactiviteit voordat wachtwoord is vereist**: geef aan na hoeveel niet-actieve tijd de gebruiker het wachtwoord opnieuw moet invoeren.
- **Wachtwoord verloopt (in dagen)**: selecteer het aantal dagen waarna het wachtwoord verloopt en gebruikers een nieuw wachtwoord moeten maken.
- **Aantal eerdere wachtwoorden dat niet opnieuw mag worden gebruikt**: voer het aantal eerder gebruikte wachtwoorden in dat niet opnieuw mag worden gebruikt.

### <a name="device-security"></a>Apparaatbeveiliging

- **Beperkte apps**: u kunt apps beperken door de bundel-id's toe te voegen aan het beleid. Als de app op een apparaat is geïnstalleerd, wordt het apparaat gemarkeerd als niet-conform.

  - **App-naam**: geef een gebruiksvriendelijke naam op om u te helpen de bundel-id te identificeren.
  - **App-bundel-id**: Geef de unieke bundel-id op die is toegewezen door de app-provider. Zie [De bundel-id vinden voor een iOS-app](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app) (hiermee wordt een andere Microsoft-website geopend) om de bundel-id te vinden.  

Selecteer **OK** > **Maken** om uw wijzigingen op te slaan.

## <a name="next-steps"></a>Volgende stappen

- [Voeg acties voor niet-conforme apparaten toe](actions-for-noncompliance.md) en [gebruik bereiktags om beleidsregels te filteren](scope-tags.md).
- [Controleer uw nalevingsbeleid](compliance-policy-monitor.md).
- Zie de [Instellingen voor nalevingsbeleid voor macOS](compliance-policy-create-mac-os.md)-apparaten.
