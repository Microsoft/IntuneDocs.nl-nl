---
title: Nalevingsinstellingen voor iOS-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een overzicht van alle instellingen die u kunt gebruiken bij het instellen van naleving voor uw iOS-apparaten in Microsoft Intune. Een e-mailprofiel vereisen, controleren op opengebroken of geroote apparaten, de toegestane minimum- en maximumversie van het besturingssysteem instellen, wachtwoordbeperkingen instellen, waaronder wachtwoordlengte en de inactiviteit van apparaten, apps beperken en meer.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/07/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e9bcfed67eda96bb4d79317bcc69d21a5f8197bc
ms.sourcegitcommit: 2b905913840d4133a7964fe4f54a58ea6e421e12
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2020
ms.locfileid: "77074628"
---
# <a name="ios-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>iOS-instellingen om te markeren of apparaten wel of niet conform zijn met behulp van Intune

Dit artikel bevat een overzicht en beschrijving van de verschillende nalevingsinstellingen die u kunt configureren op iOS-apparaten in Intune. Gebruik deze instellingen als onderdeel van uw MDM-oplossing (Mobile Device Management) om een e-mailprofiel te vereisen, geroote (opengebroken) apparaten als niet-conform te markeren, een toegestaan bedreigingsniveau in te stellen, in te stellen dat wachtwoorden verlopen en meer.

Deze functie is van toepassing op:

- iOS
- iPadOS

Gebruik deze nalevingsinstellingen als Intune-beheerder om de resources van uw organisatie beter te beschermen. Zie [Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md) voor meer informatie over nalevingsbeleid en wat dit doet.

## <a name="before-you-begin"></a>Voordat u begint

[Een nalevingsbeleid maken](create-compliance-policy.md#create-the-policy). Voor **Platform**, selecteer **iOS/iPadOS**.

## <a name="email"></a>E-mail

- **Vereisen dat mobiele apparaten een beheerd e-mailprofiel hebben**:  
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Vereisen** - Apparaten die geen e-mailprofiel hebben dat door Intune wordt beheerd, worden als niet-compatibel beschouwd. Een apparaat kan geen beheerd e-mailprofiel hebben als het niet correct is gekoppeld of als de gebruiker het e-mailaccount handmatig op het apparaat heeft ingesteld.

  Het apparaat wordt in de volgende situaties beschouwd als niet-conform:  
  - Het e-mailprofiel is toegewezen aan een andere gebruikersgroep dan de gebruikersgroep waarvoor het nalevingsbeleid is bedoeld.
  - De gebruiker heeft al een e-mailaccount op het apparaat ingesteld dat overeenkomt met het Intune-e-mailprofiel dat op het apparaat is geïmplementeerd. Het profiel dat door de gebruiker is geconfigureerd, kan niet worden overschreven en worden beheerd door Intune. De eindgebruiker moet de bestaande e-mailinstellingen verwijderen om aan het beleid te voldoen. Daarna kan Intune het beheerde e-mailprofiel installeren.  

Zie [De toegang tot zakelijke e-mail configureren met e-mailprofielen bij Intune](../configuration/email-settings-configure.md) voor meer informatie over e-mailprofielen.

## <a name="device-health"></a>Apparaatstatus

- **Opengebroken apparaten**:  
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Blokkeren** - Geroote (jailbroken) apparaten als niet-compatibel markeren.  

- **Vereisen dat het apparaat zich op of onder het apparaatbedreigingsniveau bevindt** *(iOS 8.0 en hoger)* :  
  Gebruik deze instelling om de risicobeoordeling uit te voeren als voorwaarde voor naleving. Kies het toegestane bedreigingsniveau:  
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Beveiligd** - Deze optie is het veiligst en betekent dat het apparaat geen bedreigingen kan hebben. Als een van de bedreigingsniveaus voor het apparaat wordt gedetecteerd, wordt het apparaat geëvalueerd als niet-conform.
  - **Laag** - Het apparaat wordt als compatibel beoordeeld als er alleen bedreigingen met een laag niveau op staan. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld** - Het apparaat wordt als compatibel beoordeeld als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als bedreigingen met hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-conform beoordeeld.
  - **Hoog** - Deze optie is het minst veilig, omdat alle bedreigingsniveaus zijn toegestaan. Deze optie kan handig zijn als u deze alleen gebruikt voor rapportagedoeleinden.

## <a name="device-properties"></a>Apparaateigenschappen

### <a name="operating-system-version"></a>Versie van besturingssysteem  

- **Minimale versie van het besturingssysteem** *(iOS 8.0 en hoger)* :  
  Als een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt dit apparaat gerapporteerd als niet-conform. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De eindgebruiker kan kiezen om het apparaat bij te werken. Daarna zijn de resources van de organisatie toegankelijk.

- **Maximale versie van het besturingssysteem** *iOS 8.0 en hoger)* :  
  Wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie in de regel, wordt de toegang tot organisatieresources geblokkeerd. De eindgebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Op dit apparaat kan geen toegang worden verkregen tot organisatieresources zolang een regel niet zodanig is gewijzigd dat de versie van het besturingssysteem is toegestaan.

- **Minimale build-versie van het besturingssysteem** *(iOS 8.0 en hoger)* :  
  Als Apple beveiligingsupdates publiceert, wordt het buildnummer meestal bijgewerkt, niet de versie van het besturingssysteem. Gebruik deze functie om het buildnummer in te voeren dat minimaal is toegestaan op het apparaat.

- **Maximale build-versie van het besturingssysteem** *(iOS 8.0 en hoger)* :  
  Als Apple beveiligingsupdates publiceert, wordt het buildnummer meestal bijgewerkt, niet de versie van het besturingssysteem. Gebruik deze functie om het buildnummer in te voeren dat maximaal is toegestaan op het apparaat.

## <a name="system-security"></a>Systeembeveiliging

### <a name="password"></a>Wachtwoord

> [!NOTE]
> Nadat een nalevings- of configuratiebeleid op een iOS-apparaat is toegepast, wordt gebruikers elke vijftien minuten gevraagd een wachtwoordcode in te stellen. Gebruikers wordt continu gevraagd een wachtwoordcode in te stellen totdat de code is ingesteld. Wanneer een wachtwoordcode is ingesteld voor het iOS-apparaat, wordt het versleutelingsproces automatisch gestart. Het apparaat blijft versleuteld totdat de wachtwoordcode is uitgeschakeld.

- **Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**:  
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.  
  - **Vereisen** - Gebruikers moeten een wachtwoord invoeren voordat ze toegang kunnen krijgen tot hun apparaat. iOS-apparaten die gebruikmaken van een wachtwoord, zijn versleuteld.

- **Eenvoudige wachtwoorden**:  
  - **Niet geconfigureerd** (*standaard*): gebruikers kunnen eenvoudige wachtwoorden maken, zoals **1234** of **1111**.
  - **Blokkeren** - Gebruikers kunnen geen eenvoudige wachtwoorden maken, zoals **1234** of **1111**. 

- **Minimale wachtwoordlengte**:  
  Voer het aantal cijfers of tekens in waaruit het wachtwoord minimaal moet bestaan.  

- **Vereist wachtwoordtype**:  
  Kies of een wachtwoord alleen **numerieke** tekens mag bevatten of uit een combinatie van cijfers en andere tekens moet bestaan (**alfanumeriek**).

- **Het aantal niet-alfanumerieke tekens in het wachtwoord**:  
  Voer het minimumaantal speciale tekens (zoals `&`, `#`, `%`, `!` enz.) in dat het wachtwoord moet bevatten. 

  Als u een hogere waarde instelt, moet de gebruiker een wachtwoord maken dat complexer is.

- **Maximum aantal minuten na schermvergrendeling voordat een wachtwoord is vereist** *(iOS 8.0 en hoger)* :  
  Geef op hoe snel nadat het scherm is vergrendeld, een gebruiker een wachtwoord moet invoeren om toegang tot het apparaat te krijgen. De opties zijn de standaardwaarde *Niet geconfigureerd*, *Onmiddellijk* en van *1 minuut* tot *4 uur*.

- **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**:  
  Voer de niet-actieve tijd in waarna het scherm van het apparaat wordt vergrendeld. De opties zijn de standaardwaarde *Niet geconfigureerd*, *Onmiddellijk* en van *1 minuut* tot *15 minuten*.

- **Wachtwoordverlooptijd (dagen)** :  
  selecteer het aantal dagen waarna het wachtwoord verloopt en gebruikers een nieuw wachtwoord moeten maken. 

- **Aantal vorige wachtwoorden dat niet opnieuw mag worden gebruikt** *(iOS 8.0 en hoger)* :   
  Voer het aantal eerder gebruikte wachtwoorden in dat niet opnieuw mag worden gebruikt.

### <a name="device-security"></a>Apparaatbeveiliging

- **Beperkte apps**:  
  U kunt apps beperken door de bundel-id’s toe te voegen aan het beleid. Als de app op een apparaat is geïnstalleerd, wordt het apparaat gemarkeerd als niet-conform.

  - **App-naam** - Voer een gebruiksvriendelijke naam in om u te helpen de bundel-id te identificeren.
  - **App-bundel-id** - Voer de unieke bundel-id in die is toegewezen door de app-provider. Zie [De bundel-id vinden voor een iOS-app](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app) (hiermee wordt een andere Microsoft-website geopend) om de bundel-id te vinden.  

## <a name="next-steps"></a>Volgende stappen

- [Voeg acties voor niet-conforme apparaten toe](actions-for-noncompliance.md) en [gebruik bereiktags om beleidsregels te filteren](../fundamentals/scope-tags.md).
- [Controleer uw nalevingsbeleid](compliance-policy-monitor.md).
- Zie de [Instellingen voor nalevingsbeleid voor macOS](compliance-policy-create-mac-os.md)-apparaten.
