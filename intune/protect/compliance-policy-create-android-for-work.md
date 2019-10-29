---
title: Naleving voor Android Enterprise in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een overzicht van alle instellingen die u kunt gebruiken bij het instellen van naleving voor uw Android Enterprise-apparaten in Microsoft Intune. Stel regels voor wachtwoorden in, kies een minimum- of maximumversie van het besturingssysteem, beperk bepaalde apps, voorkomen hergebruik van wachtwoorden, en meer.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/16/2019
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
ms.openlocfilehash: be1fbb72821b61566da84d6f98094c9a2f6ffef2
ms.sourcegitcommit: 3ace4cba6e2f6fefa9120be3807387a49b200c9b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/23/2019
ms.locfileid: "72810258"
---
# <a name="android-enterprise-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Android Enterprise-instellingen om te markeren of apparaten wel of niet conform zijn met behulp van Intune

Dit artikel bevat een overzicht en beschrijving van de verschillende instellingen die u kunt configureren op Android Enterprise-apparaten in Intune. Gebruik deze instellingen als onderdeel van uw MDM-oplossing (Mobile Device Management) om geroote (opengebroken) apparaten als niet-conform te markeren, een toegestaan bedreigingsniveau in te stellen, Google Play Protect in te schakelen, en meer.

Deze functie is van toepassing op:

- Android Enterprise

Gebruik deze nalevingsinstellingen als Intune-beheerder om de resources van uw organisatie beter te beschermen. Zie [Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md) voor meer informatie over nalevingsbeleid en wat dit doet.

> [!IMPORTANT]
> Het nalevings beleid is ook van toepassing op speciale Android-apparaten. Als er een nalevings beleid is toegewezen aan een toegewezen apparaat, wordt het apparaat mogelijk weer gegeven als **niet-compatibel**. Voorwaardelijke toegang en handhaving van naleving is niet beschikbaar op specifieke apparaten. Zorg ervoor dat u alle taken of acties uitvoert om de toegewezen apparaten compatibel te maken met uw toegewezen beleid.

## <a name="before-you-begin"></a>Voordat u begint

[Een nalevingsbeleid maken](create-compliance-policy.md#create-the-policy). Selecteer voor **Platform** de optie **Android Enterprise**.

## <a name="device-owner"></a>Eigenaar van het apparaat

### <a name="device-health"></a>Apparaatstatus

- **Vereisen dat het apparaat zich op of onder het bedreigings niveau van het apparaat**bevond: Selecteer het Maxi maal toegestane bedreigings niveau voor apparaten, geëvalueerd door uw [Mobile Threat verdediging-service](mobile-threat-defense.md). Apparaten die dit dreigingsniveau overschrijden, worden gemarkeerd als niet-conform. Als u deze instelling wilt gebruiken, kiest u het toegestane bedreigingsniveau:

  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Beveiligd** - Deze optie is het veiligst en betekent dat het apparaat geen bedreigingen kan hebben. Als een van de bedreigingsniveaus voor het apparaat wordt gedetecteerd, wordt het apparaat geëvalueerd als niet-compatibel.
  - **Laag** - Het apparaat wordt als compatibel beoordeeld als er alleen bedreigingen met een laag niveau op staan. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld** - Het apparaat wordt als compatibel beoordeeld als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als bedreigingen met hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-compatibel beoordeeld.
  - **Hoog** - Deze optie is het minst veilig, omdat alle bedreigingsniveaus zijn toegestaan. Deze optie kan handig zijn als u deze alleen gebruikt voor rapportagedoeleinden.
  
> [!NOTE] 
> De volgende providers van de Mobile Threat verdediging (MTD) ondersteunen de implementaties van Android Enter prise-apparaten met behulp van app-configuratie:
> - Better Mobile 
> - Pradeo
> - Sophos Mobile
> - Zimperium 
>  
>  Neem contact op met uw MTD-provider voor de exacte configuratie die nodig is voor de ondersteuning van Android Enter prise Device owner-platforms in intune. Deze lijst wordt bijgewerkt als MTD Parters ondersteuning bieden voor Android-scenario's voor bedrijfs eigen aars. 

#### <a name="google-play-protect"></a>Google Play Protect

- **SafetyNet-apparaatattestation**: hiermee kunt u instellen aan welk integriteitsniveau voor [SafetyNet-attestation](https://developer.android.com/training/safetynet/attestation.html) het apparaat moet voldoen. Uw opties zijn:
  - **Niet geconfigureerd** (*standaard*) - Instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Basisintegriteit controleren**
  - **Basisintegriteit en gecertificeerde apparaten controleren**

### <a name="device-properties"></a>Apparaateigenschappen

#### <a name="operating-system-version"></a>Versie van besturingssysteem

- **Minimale versie van het besturingssysteem**: als een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt het gerapporteerd als niet-conform. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De eind gebruiker kan het apparaat upgraden en vervolgens toegang krijgen tot de bronnen van de organisatie.

  *Standaard wordt er geen versie geconfigureerd*.

- **Maximale versie van het besturingssysteem**: wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie in de regel, wordt de toegang tot organisatieresources geblokkeerd. De gebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Op dit apparaat kan geen toegang worden verkregen tot organisatieresources totdat de regel wordt aangepast om de versie van het besturingssysteem toe te staan.

  *Standaard wordt er geen versie geconfigureerd*.

- **Minimaal beveiligingspatchniveau** - Selecteer het oudste beveiligingspatchniveau dat een apparaat kan hebben. Apparaten die niet ten minste dit patchniveau hebben, zijn niet-conform. De datum moet worden opgegeven in de indeling JJJJ-MM-DD.

  *Standaard is er geen datum geconfigureerd*.


### <a name="system-security"></a>Systeembeveiliging

- **Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**: 
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Vereisen** - Gebruikers moeten een wachtwoord invoeren voordat ze toegang kunnen krijgen tot hun apparaat. 

  Deze instelling is van toepassing op apparaatniveau. Als alleen op het niveau van het werkprofiel een wachtwoord vereist is, dient u een configuratiebeleid te gebruiken. Zie [Configuratie-instellingen voor Android Enterprise-apparaat](../configuration/device-restrictions-android-for-work.md).

  - **Vereist wachtwoordtype**: kies of een wachtwoord alleen numerieke tekens mag bevatten of ook een combinatie van cijfers en andere tekens. Uw opties zijn:
    - **Standaard waarde voor apparaat** : als u wachtwoord compatibiliteit wilt evalueren, moet u een andere wachtwoord sterkte selecteren dan **standaard waarde**voor het apparaat.  
    - **Wachtwoord vereist, geen beperkingen**
    - **Zwakke biometrie** - [Sterke versus zwakke biometrie](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (hiermee wordt een Android-website geopend)
    - **Numeriek** (*standaard*) - Het wachtwoord mag alleen uit getallen bestaan, zoals `123456789`. Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
    - **Numeriek complex** - Herhaalde of opeenvolgende cijfers, zoals '1111' of '1234', zijn niet toegestaan. Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
    - **Alfabetisch** - Letters uit het alfabet zijn vereist. Er zijn geen cijfers en symbolen vereist. Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
    - **Alfanumeriek** - Dit zijn hoofdletters, kleine letters en numerieke tekens. Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
    - **Alfanumeriek met symbolen** - Dit zijn hoofdletters, kleine letters, numerieke tekens, leestekens en symbolen. Voer ook in:
    
    Afhankelijk van het *wachtwoord type* dat u selecteert, zijn de volgende instellingen beschikbaar:  
    - **Minimale wachtwoordlengte**: voer de minimale lengte van het wachtwoord in, tussen 4 en 16 tekens.  

    - **Het vereiste aantal tekens**: voer het aantal tekens in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.

    - **Het vereiste aantal kleine letters**: voer het aantal kleine letters in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.

    - **Het vereiste aantal hoofdletters**: voer het aantal hoofdletters in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.

    - **Het vereiste aantal andere tekens dan letters**: voer het aantal andere tekens dan alfabetische letters in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.

    - **Het vereiste aantal numerieke tekens**: voer het numerieke tekens (`1`, `2`, `3` enzovoort) in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.
    
    - **Het vereiste aantal symbolen**: voer het aantal symbolen (`&`, `#`, `%` enzovoort) in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.
 
- **Maximum aantal minuten van inactiviteit voordat wachtwoord is vereist**: geef aan na hoeveel niet-actieve tijd de gebruiker het wachtwoord opnieuw moet invoeren. De opties zijn de standaard waarde *niet geconfigureerd*en van *1 minuut* tot *8 uur*.

- **Het aantal dagen totdat het wachtwoord verloopt**: Voer het aantal dagen in voordat het wachtwoord voor het apparaat moet worden gewijzigd, tussen 1 en 365. Als u bijvoorbeeld wilt dat het wachtwoord na zestig dagen moet worden gewijzigd, voert u `60` in. Wanneer het wachtwoord is verlopen, wordt gebruikers gevraagd een nieuw wachtwoord te maken.

   *Standaard is er geen waarde geconfigureerd*.

- **Het vereiste aantal wachtwoorden voordat de gebruiker een wachtwoord opnieuw kan gebruiken**: voer het aantal recente wachtwoorden in dat niet opnieuw mag worden gebruikt, tussen 1 en 24. Gebruik deze instelling om te voorkomen dat de gebruiker eerder gebruikte wachtwoorden hergebruikt.  

    *Standaard wordt er geen versie geconfigureerd*.

#### <a name="encryption"></a>Versleuteling

- **Versleuteling van gegevensopslag op apparaat**: 
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Verplicht** -versleutelen van gegevens opslag op uw apparaten.  

  U hoeft deze instelling niet te configureren omdat versleuteling op apparaten met Android Enterprise wordt afgedwongen.

## <a name="work-profile"></a>Werkprofiel

### <a name="device-health"></a>Apparaatstatus

- **Geroote apparaten**: 
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Blokkeren** - Geroote (jailbroken) apparaten als niet-compatibel markeren.  

- **Vereisen dat het apparaat zich op of onder het bedreigings niveau van het apparaat**bevond: Selecteer het Maxi maal toegestane bedreigings niveau voor apparaten, geëvalueerd door uw [Mobile Threat verdediging-service](mobile-threat-defense.md). Apparaten die dit dreigingsniveau overschrijden, worden gemarkeerd als niet-conform. Als u deze instelling wilt gebruiken, kiest u het toegestane bedreigingsniveau:

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
  - **vereisen** - Vereisen dat het apparaat tegen bekende beveiligingsproblemen wordt beveiligd door een actuele beveiligingsprovider. 
  
- **SafetyNet-apparaatattestation**: hiermee kunt u instellen aan welk integriteitsniveau voor [SafetyNet-attestation](https://developer.android.com/training/safetynet/attestation.html) het apparaat moet voldoen. Uw opties zijn:
  - **Niet geconfigureerd** (*standaard*) - Instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Basisintegriteit controleren**
  - **Basisintegriteit en gecertificeerde apparaten controleren**

> [!NOTE]
> Op apparaten met Android Enterprise is **Bedreigingsscan voor apps** een configuratiebeleidsregel voor apparaten. Met behulp van een configuratiebeleidsregel kunnen beheerders de instelling op een apparaat inschakelen. Zie [Android Enterprise-apparaatbeperkingsinstellingen](../configuration/device-restrictions-android-for-work.md).

### <a name="device-properties"></a>Apparaateigenschappen

#### <a name="operating-system-version"></a>Versie van besturingssysteem

- **Minimale versie van het besturingssysteem**: als een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt het gerapporteerd als niet-conform. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De eind gebruiker kan het apparaat upgraden en vervolgens toegang krijgen tot de bronnen van de organisatie.

  *Standaard wordt er geen versie geconfigureerd*.

- **Maximale versie van het besturingssysteem**: wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie in de regel, wordt de toegang tot organisatieresources geblokkeerd. De gebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Op dit apparaat kan geen toegang worden verkregen tot organisatieresources totdat de regel wordt aangepast om de versie van het besturingssysteem toe te staan.

  *Standaard wordt er geen versie geconfigureerd*.

### <a name="system-security"></a>Systeembeveiliging

- **Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**: 
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving. 
  - **Vereisen** - Gebruikers moeten een wachtwoord invoeren voordat ze toegang kunnen krijgen tot hun apparaat.  

  Deze instelling is van toepassing op apparaatniveau. Als alleen op het niveau van het werkprofiel een wachtwoord vereist is, dient u een configuratiebeleid te gebruiken. Zie [Configuratie-instellingen voor Android Enterprise-apparaat](../configuration/device-restrictions-android-for-work.md).

- **Vereist wachtwoordtype**: kies of een wachtwoord alleen numerieke tekens mag bevatten of ook een combinatie van cijfers en andere tekens. Uw opties zijn:
  - **Standaardwaarde apparaat**
  - **Lage beveiligingsbiometrie**
  - **Minstens numeriek** (*standaard*) - Voer de **minimale wachtwoordlengte** in die een gebruiker moet opgeven (tussen 4 en 16 tekens).
  - **Complex numeriek** (standaard): voer de **minimale wachtwoordlengte** in die een gebruiker moet opgeven (tussen 4 en 16 tekens).
  - **Minstens alfabetisch** (standaard): voer de **minimale wachtwoordlengte** in die een gebruiker moet opgeven (tussen 4 en 16 tekens).
  - **Minstens alfanumeriek** (standaard): voer de **minimale wachtwoordlengte** in die een gebruiker moet opgeven (tussen 4 en 16 tekens).
  - **Minstens alfanumeriek met symbolen**: voer de **minimale wachtwoordlengte** in die een gebruiker moet opgeven (tussen 4 en 16 tekens).

  Afhankelijk van het *wachtwoord type* dat u selecteert, zijn de volgende instellingen beschikbaar:  
  - **Maximum aantal minuten van inactiviteit voordat wachtwoord is vereist**: geef aan na hoeveel niet-actieve tijd de gebruiker het wachtwoord opnieuw moet invoeren. De opties zijn de standaard waarde *niet geconfigureerd*en van *1 minuut* tot *8 uur*.

  - **Het aantal dagen totdat het wachtwoord verloopt**: Voer het aantal dagen in voordat het wachtwoord voor het apparaat moet worden gewijzigd, tussen 1 en 365. Als u bijvoorbeeld wilt dat het wachtwoord na zestig dagen moet worden gewijzigd, voert u `60` in. Wanneer het wachtwoord is verlopen, wordt gebruikers gevraagd een nieuw wachtwoord te maken.

  - **Minimale wachtwoordlengte**: voer de minimale lengte van het wachtwoord in, tussen 4 en 16 tekens. 
  
  - **Aantal vorige wachtwoorden om hergebruik te voorkomen**: geef het aantal recente wachtwoorden op dat niet opnieuw mag worden gebruikt. Gebruik deze instelling om te voorkomen dat de gebruiker eerder gebruikte wachtwoorden hergebruikt.

#### <a name="encryption"></a>Versleuteling

- **Versleuteling van gegevensopslag op apparaat**: 
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Verplicht** -versleutelen van gegevens opslag op uw apparaten.  

  U hoeft deze instelling niet te configureren omdat versleuteling op apparaten met Android Enterprise wordt afgedwongen.

#### <a name="device-security"></a>Apparaatbeveiliging

- **Apps van onbekende bronnen blokkeren**: 
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Blok** keren: apparaten met **beveiliging** > **onbekende** bronnen (*ondersteund op Android 4,0 via Android 7. x). Niet ondersteund door Android 8.0 en hoger*).  

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

- **Minimaal beveiligingspatchniveau** - Selecteer het oudste beveiligingspatchniveau dat een apparaat kan hebben. Apparaten die niet ten minste dit patchniveau hebben, zijn niet-conform. De datum moet worden opgegeven in de indeling JJJJ-MM-DD.

  *Standaard is er geen datum geconfigureerd*.

## <a name="next-steps"></a>Volgende stappen

- [Voeg acties voor niet-conforme apparaten toe](actions-for-noncompliance.md) en [gebruik bereiktags om beleidsregels te filteren](../fundamentals/scope-tags.md).
- [Controleer uw nalevingsbeleid](compliance-policy-monitor.md).
- Zie de [Instellingen voor nalevingsbeleid voor Android-apparaten](compliance-policy-create-android.md).
