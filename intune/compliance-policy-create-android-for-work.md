---
title: Een Android Enterprise-nalevingsbeleid maken in Microsoft Intune - Azure | Microsoft Docs
description: Een Microsoft Intune-apparaatnalevingsbeleid maken of configureren voor apparaten met Android Enterprise of een werkprofiel. Kies ervoor opengebroken apparaten toe te staan, stel het acceptabele dreigingsniveau in, controleer op Google Play, voer de minimale en maximale besturingssysteemversie in, kies uw wachtwoordvereisten en sta sideloading van toepassingen toe.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/19/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a6f1f07c1cb7b5dbe81120fd678f429a996f230e
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566230"
---
# <a name="add-a-device-compliance-policy-for-android-enterprise-devices-in-intune"></a>Een apparaatnalevingsbeleid toevoegen voor Android Enterprise-apparaten in Intune

Nalevingsbeleid voor apparaten is belangrijk voor het beveiligen van de resources van uw organisatie als u gebruikmaakt van Intune. In Intune kunt u regels en instellingen maken waar apparaten zich aan moeten houden om te voldoen; zo kunt u bijvoorbeeld eisen stellen aan de wachtwoordlengte. Als het apparaat niet voldoet, kunt u toegang tot gegevens en resources blokkeren middels [voorwaardelijke toegang](conditional-access.md). 

U kunt ook apparaatrapporten verkrijgen en maatregelen nemen bij niet-naleving; zo kunt u bijvoorbeeld een e-mailmelding naar de gebruiker verzenden. Zie [Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md) voor meer informatie over nalevingsbeleid en eventuele vereisten.

In dit artikel leest u meer over de instellingen die u in een nalevingsbeleid voor apparaten met Android Enterprise kunt gebruiken.

## <a name="non-compliance-and-conditional-access"></a>Niet-naleving en voorwaardelijke toegang

In de volgende tabel wordt beschreven hoe niet-compatibele instellingen worden beheerd wanneer een nalevingsbeleid wordt gebruikt in combinatie met beleid voor voorwaardelijke toegang.

--------------------------

|**Beleidsinstelling**| **Android Enterprise-profiel** |
| --- | --- |
| **Configuratie van pincode of wachtwoord** |  In quarantaine |
| **Apparaatversleuteling** |  In quarantaine |
| **Opengebroken of geroot apparaat** | In quarantaine (geen instelling) |
| **E-mailprofiel** | Niet van toepassing |
| **Minimale versie van het besturingssysteem** | In quarantaine |
| **Maximale versie van het besturingssysteem** | In quarantaine |
| **Windows Health Attestation** |Niet van toepassing |

**Hersteld** = het besturingssysteem van het apparaat dwingt naleving af. De gebruiker wordt bijvoorbeeld gedwongen een pincode in te stellen.

**In quarantaine** = het besturingssysteem van het apparaat dwingt geen naleving af. Bij Android-apparaten wordt de gebruiker bijvoorbeeld niet gedwongen het apparaat te versleutelen. Als het apparaat niet compatibel is, worden de volgende acties uitgevoerd:

  - Het apparaat wordt geblokkeerd als een beleid voor voorwaardelijke toegang van toepassing is voor de gebruiker.
  - De bedrijfsportal stelt de gebruiker op de hoogte van eventuele nalevingsproblemen.

## <a name="create-a-device-compliance-policy"></a>Een nalevingsbeleid voor apparaten maken

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. Selecteer voor **Platform** de optie **Android Enterprise**. 
5. Kies **Instellingen configureren**. Geef instellingen op voor de **apparaatstatus**, de **apparaateigenschappen** en de **systeembeveiliging**, zoals in dit artikel wordt beschreven.

## <a name="device-health"></a>Device health

- **Geroote apparaten**: kies **Blokkeren** om geroote (jailbroken) apparaten als niet compatibel te markeren. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.
- **Vereisen dat het apparaat het apparaatdreigingsniveau niet overschrijdt**: gebruik deze instelling om de risicobeoordeling uit de Lookout MTP-oplossing als voorwaarde voor naleving te gebruiken. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving. Als u deze instelling wilt gebruiken, kiest u het toegestane bedreigingsniveau:
  - **Beveiligd**: deze optie is het veiligst en betekent dat het apparaat geen bedreigingen kan hebben. Als een van de bedreigingsniveaus voor het apparaat wordt gedetecteerd, wordt het apparaat geëvalueerd als niet-compatibel.
  - **Laag**: het apparaat wordt als compatibel geëvalueerd als er bedreigingen van een laag niveau aanwezig zijn. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld**: Het apparaat wordt als compatibel geëvalueerd als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als bedreigingen met hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-compatibel beoordeeld.
  - **Hoog**: deze optie is het minst veilig, omdat alle bedreigingsniveaus zijn toegestaan. Deze optie kan handig zijn als u deze alleen gebruikt voor rapportagedoeleinden.
- **Google Play Services is geconfigureerd**: hiermee kunt u **vereisen** dat de app Google Play Services wordt geïnstalleerd en ingeschakeld. Google Play Services maakt beveiligingsupdates mogelijk en vormt een basisafhankelijkheid voor veel beveiligingsfuncties op door Google gecertificeerde apparaten. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.
- **Bijgewerkte beveiligingsprovider**: hiermee kunt u **vereisen** dat het apparaat tegen bekende beveiligingsproblemen wordt beschermd door een bijgewerkte beveiligingsprovider. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.
- **SafetyNet-apparaatattestation**: hiermee kunt u instellen aan welk integriteitsniveau voor [SafetyNet-attestation](https://developer.android.com/training/safetynet/attestation.html) het apparaat moet voldoen. Uw opties zijn:
  - **Niet geconfigureerd** (standaard): deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Basisintegriteit controleren**
  - **Basisintegriteit en gecertificeerde apparaten controleren**

#### <a name="threat-scan-on-apps"></a>Bedreigingsscan voor apps

Op apparaten met Android Enterprise is de instelling **Bedreigingsscan voor apps** een configuratiebeleidsregel. Zie [Android Enterprise-apparaatbeperkingsinstellingen](device-restrictions-android-for-work.md).

## <a name="device-properties-settings"></a>Apparaateigenschapsinstellingen

- **Minimale versie van het besturingssysteem**: als een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt het gerapporteerd als niet-conform. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. Gebruikers kunnen dan kiezen om een upgrade van hun apparaat uit te voeren, waarna ze toegang tot bedrijfsresources krijgen.
- **Maximale versie van het besturingssysteem**: wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie in de regel, wordt de toegang tot bedrijfsresources geblokkeerd. De gebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel om de versie van het besturingssysteem toe te staan, kan dit apparaat geen toegang tot bedrijfsresources krijgen.

## <a name="system-security-settings"></a>Systeembeveiligingsinstellingen

### <a name="password"></a>Wachtwoord

- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**: **verplicht** gebruikers een wachtwoord in te voeren om toegang te krijgen tot hun apparaat. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving. Deze instelling wordt toegepast op apparaatniveau. Als alleen op het niveau van het werkprofiel een wachtwoord vereist is, dient u een configuratiebeleid te gebruiken. Zie [Configuratie-instellingen voor Android Enterprise-apparaat](device-restrictions-android-for-work.md).
- **Minimale wachtwoordlengte**: voer het minimale aantal cijfers of tekens in waaruit het wachtwoord van de gebruiker moet bestaan.
- **Vereist wachtwoordtype**: kies of een wachtwoord alleen numerieke tekens mag bevatten of ook een combinatie van cijfers en andere tekens. Uw opties zijn:
  - **Standaardwaarde apparaat**
  - **Lage beveiligingsbiometrie**
  - **Ten minste numeriek** (standaard)
  - **Complex numeriek**
  - **Ten minste alfabetisch**
  - **Ten minste alfanumeriek**
  - **Minstens alfanumeriek met symbolen**

- **Maximum aantal minuten van inactiviteit voordat wachtwoord is vereist**: geef aan na hoeveel niet-actieve tijd de gebruiker het wachtwoord opnieuw moet invoeren. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.
- **Wachtwoord verloopt (in dagen)**: selecteer het aantal dagen waarna het wachtwoord verloopt en gebruikers een nieuw wachtwoord moeten maken.
- **Aantal vorige wachtwoorden om hergebruik te voorkomen**: geef het aantal recente wachtwoorden op dat niet opnieuw mag worden gebruikt. Gebruik deze instelling om te voorkomen dat de gebruiker eerder gebruikte wachtwoorden hergebruikt.

### <a name="encryption"></a>Versleuteling

- **Versleuteling van gegevensopslag op een apparaat**: kies **Vereisen** om gegevensopslag op uw apparaten te versleutelen. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving. 

  U hoeft deze instelling niet te configureren omdat versleuteling wordt afgedwongen op apparaten met een Android-werkprofiel.

### <a name="device-security"></a>Apparaatbeveiliging

- **Apps van onbekende bronnen blokkeren**: kies deze optie om apparaten te **blokkeren** waarvoor 'Beveiliging > Onbekende bronnen' is ingeschakeld (ondersteund in Android 4.0 - Android 7.x, niet ondersteund in Android 8.0 en hoger). Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.

  Als u sideloading wilt uitvoeren voor apps, moeten onbekende bronnen worden toegestaan. Als u Android-apps niet met behulp van sideloading laadt, stelt u deze functie in op **Blokkeren** om dit nalevingsbeleid in te schakelen. 

  > [!IMPORTANT]
  > Voor sideloading van toepassingen moet de instelling **Apps uit onbekende bronnen blokkeren** zijn ingeschakeld. Dwing dit nalevingsbeleid alleen af als u Android-apps niet met behulp van sideloading op apparaten laadt.

  U hoeft deze instelling niet te configureren omdat installatie vanuit onbekende bronnen altijd wordt voorkomen op apparaten met een Android-werkprofiel.

- **Runtime-integriteit van de bedrijfsportal-app**: kies **Vereisen** om te bevestigen dat de bedrijfsportal-app aan de volgende vereisten voldoet:

  - De reguliere runtime-omgeving is geïnstalleerd
  - Is correct ondertekend
  - Bevindt zich niet in de foutopsporingsmodus
  - Is geïnstalleerd via een bekende bron

  Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.

- **USB-foutopsporing op apparaat blokkeren**: kies **Blokkeren** om te voorkomen dat apparaten de functie voor USB-foutopsporing gebruiken. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.

  U hoeft deze instelling niet te configureren omdat USB-foutopsporing altijd al is uitgeschakeld op apparaten met een Android-werkprofiel.

- **Minimaal beveiligingspatchniveau**: selecteer het oudste beveiligingspatchniveau dat een apparaat kan hebben. Apparaten die niet ten minste dit patchniveau hebben, zijn niet-conform. De datum moet worden opgegeven in de indeling *jjjj-mm-dd*.

Wanneer u klaar bent, selecteert u **OK** > **OK** om uw wijzigingen op te slaan.

## <a name="actions-for-noncompliance"></a>Acties voor niet-naleving

Selecteer **Acties voor niet-naleving**. De standaardactie markeert het apparaat onmiddellijk als niet-compatibel.

U kunt het schema veranderen wanneer het apparaat wordt gemarkeerd als niet-compatibel, zoals na één dag. U kunt ook een tweede actie toevoegen, waarbij een e-mailbericht wordt verzonden naar de gebruiker wanneer het apparaat niet voldoet.

[Acties voor niet-compatibele apparaten toevoegen](actions-for-noncompliance.md) biedt meer informatie, onder andere over het maken van een e-mailmelding voor uw gebruikers.

## <a name="scope-tags"></a>Bereiktags

Met bereiktags kunt u eenvoudig beleidsregels toewijzen aan specifieke groepen, zoals Verkoop, Engineering, HR en zo verder. U kunt bereiktags toevoegen aan nalevingsbeleid. Zie [Bereiktags gebruiken om beleidsregels te filteren](scope-tags.md). 

## <a name="assign-user-groups"></a>Gebruikersgroepen toewijzen

Wanneer een beleid is gemaakt, doet dit beleid niets tot u het ergens aan toewijst. Het beleid toewijzen: 

1. Kies een beleid dat u hebt geconfigureerd. Bestaande beleidsregels bevinden zich in **Apparaatcompatibiliteit** > **Beleid**.
2. Kies het beleid en kies **Toewijzingen**. U kunt Azure Active Directory-beveiligingsgroepen (AD) opnemen of uitsluiten.
3. Kies **Geselecteerde groepen** om uw Azure AD-beveiligingsgroepen te zien. Selecteer de gebruikersgroepen waarop u dit beleid wilt toepassen en kies **Opslaan** om het beleid te implementeren op gebruikers.

U hebt het beleid toegepast op gebruikers. De apparaten die worden gebruikt door de gebruikers op wie het beleid wordt toegepast, worden gecontroleerd om te zien of ze voldoen aan de vereisten.

## <a name="next-steps"></a>Volgende stappen
[E-mail automatiseren en acties voor niet-conforme apparaten toevoegen](actions-for-noncompliance.md)  
[Nalevingsbeleid voor Intune-apparaten controleren](compliance-policy-monitor.md)  
[Instellingen voor het nalevingsbeleid voor Android](compliance-policy-create-android.md)
