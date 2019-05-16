---
title: Naleving voor Android Enterprise in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een overzicht van alle instellingen die u kunt gebruiken bij het instellen van naleving voor uw Android Enterprise-apparaten in Microsoft Intune. Stel regels voor wachtwoorden in, kies een minimum- of maximumversie van het besturingssysteem, beperk bepaalde apps, voorkomen hergebruik van wachtwoorden, en meer.
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
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 16db0acab84a1095c40e9a92648c75c2581187cd
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423557"
---
# <a name="android-enterprise-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Android Enterprise-instellingen om te markeren of apparaten wel of niet conform zijn met behulp van Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Dit artikel bevat een overzicht en beschrijving van de verschillende instellingen die u kunt configureren op Android Enterprise-apparaten in Intune. Gebruik deze instellingen als onderdeel van uw MDM-oplossing (Mobile Device Management) om geroote (opengebroken) apparaten als niet-conform te markeren, een toegestaan bedreigingsniveau in te stellen, Google Play Protect in te schakelen, en meer.

Deze functie is van toepassing op:

- Android Enterprise

Gebruik deze nalevingsinstellingen als Intune-beheerder om de resources van uw organisatie beter te beschermen. Zie [Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md) voor meer informatie over nalevingsbeleid en wat dit doet.

## <a name="before-you-begin"></a>Voordat u begint

[Een nalevingsbeleid maken](create-compliance-policy.md#create-the-policy). Selecteer voor **Platform** de optie **Android Enterprise**.

## <a name="device-health"></a>Device health

- **Geroote apparaten**: kies **Blokkeren** om geroote (jailbroken) apparaten als niet compatibel te markeren. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.
- **Vereisen dat het apparaat het apparaatdreigingsniveau niet overschrijdt**: gebruik deze instelling om de risicobeoordeling uit de Lookout MTP-oplossing als voorwaarde voor naleving te gebruiken. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving. Als u deze instelling wilt gebruiken, kiest u het toegestane bedreigingsniveau:
  - **Beveiligd**: deze optie is het veiligst en betekent dat het apparaat geen bedreigingen kan hebben. Als een van de bedreigingsniveaus voor het apparaat wordt gedetecteerd, wordt het apparaat geëvalueerd als niet-compatibel.
  - **Laag**: het apparaat wordt als compatibel geëvalueerd als er bedreigingen van een laag niveau aanwezig zijn. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld**: Het apparaat wordt als compatibel geëvalueerd als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als bedreigingen met hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-compatibel beoordeeld.
  - **Hoog**: deze optie is het minst veilig, omdat alle bedreigingsniveaus zijn toegestaan. Deze optie kan handig zijn als u deze alleen gebruikt voor rapportagedoeleinden.

### <a name="google-play-protect"></a>Google Play Protect

- **Google Play Services is geconfigureerd**: hiermee kunt u **vereisen** dat de app Google Play Services wordt geïnstalleerd en ingeschakeld. Google Play Services maakt beveiligingsupdates mogelijk en vormt een basisafhankelijkheid voor veel beveiligingsfuncties op door Google gecertificeerde apparaten. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.
- **Bijgewerkte beveiligingsprovider**: hiermee kunt u **vereisen** dat het apparaat tegen bekende beveiligingsproblemen wordt beschermd door een bijgewerkte beveiligingsprovider. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.
- **SafetyNet-apparaatattestation**: hiermee kunt u instellen aan welk integriteitsniveau voor [SafetyNet-attestation](https://developer.android.com/training/safetynet/attestation.html) het apparaat moet voldoen. Uw opties zijn:
  - **Niet geconfigureerd** (standaard): deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Basisintegriteit controleren**
  - **Basisintegriteit en gecertificeerde apparaten controleren**

> [!NOTE]
> Op apparaten met Android Enterprise is **Bedreigingsscan voor apps** een configuratiebeleidsregel voor apparaten. Met behulp van een configuratiebeleidsregel kunnen beheerders de instelling op een apparaat inschakelen. Zie [Android Enterprise-apparaatbeperkingsinstellingen](device-restrictions-android-for-work.md).

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

  U hoeft deze instelling niet te configureren omdat versleuteling op apparaten met Android Enterprise wordt afgedwongen.

### <a name="device-security"></a>Apparaatbeveiliging

- **Apps van onbekende bronnen blokkeren**: kies deze optie om apparaten te **blokkeren** waarvoor 'Beveiliging > Onbekende bronnen' is ingeschakeld (ondersteund in Android 4.0 - Android 7.x, niet ondersteund in Android 8.0 en hoger). Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.

  Als u sideloading wilt uitvoeren voor apps, moeten onbekende bronnen worden toegestaan. Als u Android-apps niet met behulp van sideloading laadt, stelt u deze functie in op **Blokkeren** om dit nalevingsbeleid in te schakelen. 

  > [!IMPORTANT]
  > Voor sideloading van toepassingen moet de instelling **Apps uit onbekende bronnen blokkeren** zijn ingeschakeld. Dwing dit nalevingsbeleid alleen af als u Android-apps niet met behulp van sideloading op apparaten laadt.

  U hoeft deze instelling niet te configureren omdat installatie vanuit onbekende bronnen altijd wordt voorkomen op apparaten met Android Enterprise.

- **Runtime-integriteit van de bedrijfsportal-app**: kies **Vereisen** om te bevestigen dat de bedrijfsportal-app aan de volgende vereisten voldoet:

  - De reguliere runtime-omgeving is geïnstalleerd
  - Is correct ondertekend
  - Bevindt zich niet in de foutopsporingsmodus
  - Is geïnstalleerd via een bekende bron

  Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.

- **USB-foutopsporing op apparaat blokkeren**: kies **Blokkeren** om te voorkomen dat apparaten de functie voor USB-foutopsporing gebruiken. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.

  U hoeft deze instelling niet te configureren omdat USB-foutopsporing altijd al is uitgeschakeld op apparaten met Android Enterprise.

- **Minimaal beveiligingspatchniveau**: selecteer het oudste beveiligingspatchniveau dat een apparaat kan hebben. Apparaten die niet ten minste dit patchniveau hebben, zijn niet-conform. De datum moet worden opgegeven in de indeling *jjjj-mm-dd*.

Selecteer **OK** > **Maken** om uw wijzigingen op te slaan.

## <a name="next-steps"></a>Volgende stappen

- [Voeg acties voor niet-conforme apparaten toe](actions-for-noncompliance.md) en [gebruik bereiktags om beleidsregels te filteren](scope-tags.md).
- [Controleer uw nalevingsbeleid](compliance-policy-monitor.md).
- Zie de [Instellingen voor nalevingsbeleid voor Android-apparaten](compliance-policy-create-android.md).
