---
title: Naleving voor Android Enterprise in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een overzicht van alle instellingen die u kunt gebruiken bij het instellen van naleving voor uw Android Enterprise-apparaten in Microsoft Intune. Stel regels voor wachtwoorden in, kies een minimum- of maximumversie van het besturingssysteem, beperk bepaalde apps, voorkomen hergebruik van wachtwoorden, en meer.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/07/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 163f5dd246fb17e7d67a8baffbae9926f2f4bc79
ms.sourcegitcommit: a25f556aa9df4fcd9fdacccd12c9029bc6c5fe20
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2020
ms.locfileid: "78256438"
---
# <a name="android-enterprise-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Android Enterprise-instellingen om te markeren of apparaten wel of niet conform zijn met behulp van Intune

Dit artikel bevat een overzicht en beschrijving van de verschillende instellingen die u kunt configureren op Android Enterprise-apparaten in Intune. Gebruik deze instellingen als onderdeel van uw MDM-oplossing (Mobile Device Management) om geroote (opengebroken) apparaten als niet-conform te markeren, een toegestaan bedreigingsniveau in te stellen, Google Play Protect in te schakelen, en meer.

Deze functie is van toepassing op:

- Android Enterprise

Gebruik deze nalevingsinstellingen als Intune-beheerder om de resources van uw organisatie beter te beschermen. Zie [Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md) voor meer informatie over nalevingsbeleid en wat dit doet.

> [!IMPORTANT]
> Nalevingsbeleidsregels zijn ook van toepassing op toegewezen Android Enterprise-apparaten. Als een nalevingsbeleid aan een toegewezen apparaat is toegewezen, wordt het apparaat mogelijk weergegeven als **Niet compatibel**. Voorwaardelijke toegang en het afdwingen van naleving is niet beschikbaar op toegewezen apparaten. Zorg ervoor dat u alle taken of acties uitvoert om de toegewezen apparaten compatibel te maken met uw toegewezen beleid.

## <a name="before-you-begin"></a>Voordat u begint

[Een nalevingsbeleid maken](create-compliance-policy.md#create-the-policy). Selecteer voor **Platform** de optie **Android Enterprise**.

## <a name="device-owner"></a>Eigenaar van het apparaat

### <a name="device-health"></a>Apparaatstatus

- **Vereisen dat het apparaat zich op of onder het apparaatdreigingsniveau bevindt**: Selecteer welk bedreigingsniveau voor apparaten maximaal is toegestaan dat door uw [Mobile Threat Defense-service](mobile-threat-defense.md) wordt geëvalueerd. Apparaten die dit dreigingsniveau overschrijden, worden gemarkeerd als niet-conform. Als u deze instelling wilt gebruiken, kiest u het toegestane bedreigingsniveau:

  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Beveiligd** - Deze optie is het veiligst en betekent dat het apparaat geen bedreigingen kan hebben. Als een van de bedreigingsniveaus voor het apparaat wordt gedetecteerd, wordt het apparaat geëvalueerd als niet-compatibel.
  - **Laag** - Het apparaat wordt als compatibel beoordeeld als er alleen bedreigingen met een laag niveau op staan. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld** - Het apparaat wordt als compatibel beoordeeld als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als bedreigingen met hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-compatibel beoordeeld.
  - **Hoog** - Deze optie is het minst veilig, omdat alle bedreigingsniveaus zijn toegestaan. Deze optie kan handig zijn als u deze alleen gebruikt voor rapportagedoeleinden.
  
> [!NOTE] 
> Alle Mobile Threat Defense-providers (MTD) worden ondersteund op implementaties van Android Enterprise-apparaateigenaren door middel van app-configuratie. Neem contact op met uw MTD-provider voor de exacte configuratie die nodig is voor de ondersteuning van platformen voor Android Enterprise-apparaten op Intune.

#### <a name="google-play-protect"></a>Google Play Protect

- **SafetyNet-attestation voor apparaat**: hiermee kunt u instellen aan welk integriteitsniveau voor [SafetyNet-attestation](https://developer.android.com/training/safetynet/attestation.html) het apparaat moet voldoen. Uw opties zijn:
  - **Niet geconfigureerd** (*standaard*) - Instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Basisintegriteit controleren**
  - **Basisintegriteit en gecertificeerde apparaten controleren**

### <a name="device-properties"></a>Apparaateigenschappen

#### <a name="operating-system-version"></a>Versie van besturingssysteem

- **Minimale versie van het besturingssysteem**: Als een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt dit apparaat gerapporteerd als niet-conform. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. Eindgebruikers kunnen hun apparaat upgraden, waarna ze toegang tot resources van de organisatie krijgen.

  *Standaard is er geen versie geconfigureerd*.

- **Maximale versie van het besturingssysteem**: Wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie in de regel, wordt de toegang tot organisatieresources geblokkeerd. De gebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Op dit apparaat kan geen toegang worden verkregen tot organisatieresources totdat de regel wordt aangepast om de versie van het besturingssysteem toe te staan.

  *Standaard is er geen versie geconfigureerd*.

- **Minimaal beveiligingspatchniveau**:  selecteer het oudste beveiligingspatchniveau dat een apparaat mag hebben. Apparaten die niet ten minste dit patchniveau hebben, zijn niet-conform. De datum moet worden opgegeven in de indeling JJJJ-MM-DD.

  *Standaard is er geen datum geconfigureerd*.


### <a name="system-security"></a>Systeembeveiliging

- **Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**: 
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Vereisen** - Gebruikers moeten een wachtwoord invoeren voordat ze toegang kunnen krijgen tot hun apparaat.
  - **Vereist wachtwoordtype**: kies of een wachtwoord alleen numerieke tekens mag bevatten of ook een combinatie van cijfers en andere tekens. Uw opties zijn:
    - **Standaardwaarde apparaat**: als u de naleving van wachtwoorden wilt evalueren, selecteert u een andere wachtwoordsterkte dan **Standaardwaarde apparaat**.  
    - **Wachtwoord vereist, geen beperkingen**
    - **Zwakke biometrie** - [Sterke versus zwakke biometrie](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (hiermee wordt een Android-website geopend)
    - **Numeriek** (*standaard*): Het wachtwoord mag alleen uit getallen bestaan, bijvoorbeeld `123456789`. Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
    - **Numeriek complex** - Herhaalde of opeenvolgende cijfers, zoals '1111' of '1234', zijn niet toegestaan. Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
    - **Alfabetisch** - Letters uit het alfabet zijn vereist. Er zijn geen cijfers en symbolen vereist. Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
    - **Alfanumeriek** - Dit zijn hoofdletters, kleine letters en numerieke tekens. Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
    - **Alfanumeriek met symbolen** - Dit zijn hoofdletters, kleine letters, numerieke tekens, leestekens en symbolen. Voer ook in:
    
    Afhankelijk van het *wachtwoordtype* dat u selecteert, zijn de volgende instellingen beschikbaar:  
    - **Minimale wachtwoordlengte**: Voer de minimale lengte van het wachtwoord in, tussen 4 en 16 tekens.  

    - **Het vereiste aantal tekens**: Voer het aantal tekens in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.

    - **Het vereiste aantal kleine letters**: Voer het aantal kleine letters in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.

    - **Het vereiste aantal hoofdletters**: Voer het aantal hoofdletters in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.

    - **Het vereiste aantal andere tekens dan letters**: Voer het aantal andere tekens dan alfabetische letters in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.

    - **Het vereiste aantal numerieke tekens**: Voer het aantal numerieke tekens (`1`, `2`, `3` enzovoort) in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.
    
    - **Het vereiste aantal symbolen**: Voer het aantal symbolen (`&`, `#`, `%` enzovoort) in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.
 
- **Maximum aantal minuten inactief voordat wachtwoord is vereist**: Voer in na hoeveel niet-actieve tijd gebruikers hun wachtwoord opnieuw moeten invoeren. De opties zijn de standaardwaarde *Niet geconfigureerd* en van *1 minuut* tot *8 uur*.

- **Het aantal dagen totdat het wachtwoord verloopt**: Voer het aantal dagen in voordat het wachtwoord voor het apparaat moet worden gewijzigd, tussen 1 en 365. Als u bijvoorbeeld wilt dat het wachtwoord na zestig dagen moet worden gewijzigd, voert u `60` in. Wanneer het wachtwoord is verlopen, wordt gebruikers gevraagd een nieuw wachtwoord te maken.

   *Standaard is er geen waarde geconfigureerd*.

- **Het vereiste aantal wachtwoorden voordat de gebruiker een wachtwoord opnieuw kan gebruiken**: Voer het aantal recente wachtwoorden in dat niet opnieuw mag worden gebruikt, tussen 1 en 24. Gebruik deze instelling om te voorkomen dat de gebruiker eerder gebruikte wachtwoorden hergebruikt.  

    *Standaard is er geen versie geconfigureerd*.

#### <a name="encryption"></a>Versleuteling

- **Versleuteling van gegevensopslag op apparaat**: 
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Vereisen**: de gegevensopslag op uw apparaten versleutelen.  

  U hoeft deze instelling niet te configureren omdat versleuteling op apparaten met Android Enterprise wordt afgedwongen.

## <a name="work-profile"></a>Werkprofiel

### <a name="device-health"></a>Apparaatstatus

- **Geroote apparaten**: 
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Blokkeren** - Geroote (jailbroken) apparaten als niet-compatibel markeren.  

- **Vereisen dat het apparaat zich op of onder het apparaatdreigingsniveau bevindt**: Selecteer welk bedreigingsniveau voor apparaten maximaal is toegestaan dat door uw [Mobile Threat Defense-service](mobile-threat-defense.md) wordt geëvalueerd. Apparaten die dit dreigingsniveau overschrijden, worden gemarkeerd als niet-conform. Als u deze instelling wilt gebruiken, kiest u het toegestane bedreigingsniveau:

  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Beveiligd** - Deze optie is het veiligst en betekent dat het apparaat geen bedreigingen kan hebben. Als een van de bedreigingsniveaus voor het apparaat wordt gedetecteerd, wordt het apparaat geëvalueerd als niet-compatibel.
  - **Laag** - Het apparaat wordt als compatibel beoordeeld als er alleen bedreigingen met een laag niveau op staan. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld** - Het apparaat wordt als compatibel beoordeeld als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als bedreigingen met hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-compatibel beoordeeld.
  - **Hoog** - Deze optie is het minst veilig, omdat alle bedreigingsniveaus zijn toegestaan. Deze optie kan handig zijn als u deze alleen gebruikt voor rapportagedoeleinden.

#### <a name="google-play-protect"></a>Google Play Protect

- **Google Play Services is geconfigureerd**: 
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Vereisen** - Vereisen dat de app Google Play Services is geïnstalleerd en ingeschakeld. Google Play Services maakt beveiligingsupdates mogelijk en vormt een basisafhankelijkheid voor veel beveiligingsfuncties op door Google gecertificeerde apparaten. 
  
- **Bijgewerkte beveiligingsprovider**: 
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Vereisen** - Vereisen dat het apparaat tegen bekende beveiligingsproblemen wordt beveiligd door een actuele beveiligingsprovider. 
  
- **SafetyNet-attestation voor apparaat**: hiermee kunt u instellen aan welk integriteitsniveau voor [SafetyNet-attestation](https://developer.android.com/training/safetynet/attestation.html) het apparaat moet voldoen. Uw opties zijn:
  - **Niet geconfigureerd** (*standaard*) - Instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Basisintegriteit controleren**
  - **Basisintegriteit en gecertificeerde apparaten controleren**

> [!NOTE]
> Op apparaten met Android Enterprise is **Bedreigingsscan voor apps** een configuratiebeleidsregel voor apparaten. Met behulp van een configuratiebeleidsregel kunnen beheerders de instelling op een apparaat inschakelen. Zie [Android Enterprise-apparaatbeperkingsinstellingen](../configuration/device-restrictions-android-for-work.md).

### <a name="device-properties"></a>Apparaateigenschappen

#### <a name="operating-system-version"></a>Versie van besturingssysteem

- **Minimale versie van het besturingssysteem**: Als een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt dit apparaat gerapporteerd als niet-conform. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. Eindgebruikers kunnen hun apparaat upgraden, waarna ze toegang tot resources van de organisatie krijgen.

  *Standaard is er geen versie geconfigureerd*.

- **Maximale versie van het besturingssysteem**: Wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie in de regel, wordt de toegang tot organisatieresources geblokkeerd. De gebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Op dit apparaat kan geen toegang worden verkregen tot organisatieresources totdat de regel wordt aangepast om de versie van het besturingssysteem toe te staan.

  *Standaard is er geen versie geconfigureerd*.

### <a name="system-security"></a>Systeembeveiliging

- **Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**: 
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving. 
  - **Vereisen** - Gebruikers moeten een wachtwoord invoeren voordat ze toegang kunnen krijgen tot hun apparaat.  

  Deze instelling wordt toegepast op apparaatniveau. Als alleen op het niveau van het werkprofiel een wachtwoord vereist is, dient u een configuratiebeleid te gebruiken. Zie [Configuratie-instellingen voor Android Enterprise-apparaat](../configuration/device-restrictions-android-for-work.md).

- **Vereist wachtwoordtype**: kies of een wachtwoord alleen numerieke tekens mag bevatten of ook een combinatie van cijfers en andere tekens. Uw opties zijn:
  - **Standaardwaarde apparaat**
  - **Lage beveiligingsbiometrie**
  - **Ten minste numeriek** (*standaard*): Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
  - **Complex numeriek**: Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
  - **Ten minste alfabetisch**: Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
  - **Ten minste alfanumeriek**: Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
  - **Ten minste alfanumeriek met symbolen**: Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.

  Afhankelijk van het *wachtwoordtype* dat u selecteert, zijn de volgende instellingen beschikbaar:  
  - **Maximum aantal minuten inactief voordat wachtwoord is vereist**: Voer in na hoeveel niet-actieve tijd gebruikers hun wachtwoord opnieuw moeten invoeren. De opties zijn de standaardwaarde *Niet geconfigureerd* en van *1 minuut* tot *8 uur*.

  - **Het aantal dagen totdat het wachtwoord verloopt**: Voer het aantal dagen in voordat het wachtwoord voor het apparaat moet worden gewijzigd, tussen 1 en 365. Als u bijvoorbeeld wilt dat het wachtwoord na zestig dagen moet worden gewijzigd, voert u `60` in. Wanneer het wachtwoord is verlopen, wordt gebruikers gevraagd een nieuw wachtwoord te maken.

  - **Minimale wachtwoordlengte**: Voer de minimale lengte van het wachtwoord in, tussen 4 en 16 tekens. 
  
  - **Aantal eerdere wachtwoorden dat niet opnieuw mag worden gebruikt**: voer het aantal recente wachtwoorden in dat niet opnieuw mag worden gebruikt. Gebruik deze instelling om te voorkomen dat de gebruiker eerder gebruikte wachtwoorden hergebruikt.

#### <a name="encryption"></a>Versleuteling

- **Versleuteling van gegevensopslag op apparaat**: 
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Vereisen**: de gegevensopslag op uw apparaten versleutelen.  

  U hoeft deze instelling niet te configureren omdat versleuteling op apparaten met Android Enterprise wordt afgedwongen.

#### <a name="device-security"></a>Apparaatbeveiliging

- **Apps van onbekende bronnen blokkeren**: 
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Blokkeren**: blokkeer apparaten waarop **Beveiliging** > **Onbekende bronnen** is ingeschakeld (*wordt ondersteund op apparaten met Android 4.0 tot en met Android 7.x. Niet ondersteund in Android 8.0 en hoger*).  

  Als u sideloading wilt uitvoeren voor apps, moeten onbekende bronnen worden toegestaan. Als u Android-apps niet met behulp van sideloading laadt, stelt u deze functie in op **Blokkeren** om dit nalevingsbeleid in te schakelen.

  > [!IMPORTANT]
  > Voor sideloading van toepassingen moet de instelling **Apps uit onbekende bronnen blokkeren** zijn ingeschakeld. Dwing dit nalevingsbeleid alleen af als u Android-apps niet met behulp van sideloading op apparaten laadt.

  U hoeft deze instelling niet te configureren omdat installatie vanuit onbekende bronnen altijd wordt voorkomen op apparaten met Android Enterprise.

- **Runtime-integriteit van de bedrijfsportal-app**: 
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Vereisen** - Kies *Vereisen* om te bevestigen dat de bedrijfsportal-app aan alle volgende vereisten voldoet:
    - De reguliere runtime-omgeving is geïnstalleerd
    - Is correct ondertekend
    - Bevindt zich niet in de foutopsporingsmodus
    - Is geïnstalleerd via een bekende bron

- **USB-foutopsporing op apparaat blokkeren**: 
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Blokkeren** - Voorkomen dat apparaten de functie voor USB-foutopsporing gebruiken.  

  U hoeft deze instelling niet te configureren omdat USB-foutopsporing altijd al is uitgeschakeld op apparaten met Android Enterprise.

- **Minimaal beveiligingspatchniveau**:  selecteer het oudste beveiligingspatchniveau dat een apparaat mag hebben. Apparaten die niet ten minste dit patchniveau hebben, zijn niet-conform. De datum moet worden opgegeven in de indeling JJJJ-MM-DD.

  *Standaard is er geen datum geconfigureerd*.

## <a name="next-steps"></a>Volgende stappen

- [Voeg acties voor niet-conforme apparaten toe](actions-for-noncompliance.md) en [gebruik bereiktags om beleidsregels te filteren](../fundamentals/scope-tags.md).
- [Controleer uw nalevingsbeleid](compliance-policy-monitor.md).
- Zie de [Instellingen voor nalevingsbeleid voor Android-apparaten](compliance-policy-create-android.md).
