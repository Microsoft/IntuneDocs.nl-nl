---
title: Nalevingsinstellingen voor Android-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een overzicht van alle instellingen die u kunt gebruiken bij het instellen van naleving voor uw Android-apparaten in Microsoft Intune. Stel regels voor wachtwoorden in, kies een minimum- of maximumversie van het besturingssysteem, beperk bepaalde apps, voorkomen hergebruik van wachtwoorden, en meer.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/25/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4237b54b3ea89fcf75ce5a21f08012f384eed95c
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502520"
---
# <a name="android-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Android-instellingen om te markeren of apparaten wel of niet conform zijn met behulp van Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Dit artikel bevat een overzicht en beschrijving van de verschillende nalevingsinstellingen die u kunt configureren op Android-apparaten in Intune. Gebruik deze instellingen als onderdeel van uw MDM-oplossing (Mobile Device Management) om geroote (opengebroken) apparaten als niet-conform te markeren, een toegestaan bedreigingsniveau in te stellen, Google Play Protect in te schakelen, en meer.

Deze functie is van toepassing op:

- Android

Gebruik deze nalevingsinstellingen als Intune-beheerder om de resources van uw organisatie beter te beschermen. Zie [Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md) voor meer informatie over nalevingsbeleid en wat dit doet.

## <a name="before-you-begin"></a>Voordat u begint

[Een nalevingsbeleid maken](create-compliance-policy.md#create-the-policy). Selecteer voor **Platform** de optie **Android**.

## <a name="device-health"></a>Device health

- **Geroote apparaten**: kies **Blokkeren** om geroote (jailbroken) apparaten als niet compatibel te markeren. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.
- **Vereisen dat het apparaat het apparaatdreigingsniveau niet overschrijdt**: gebruik deze instelling om de risicobeoordeling uit de Lookout Mobile Endpoint Security-oplossing als voorwaarde voor naleving te gebruiken. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving. Als u deze instelling wilt gebruiken, kiest u het toegestane bedreigingsniveau:
  - **Beveiligd**: deze optie is het veiligst, omdat het apparaat geen bedreigingen kan hebben. Als een van de bedreigingsniveaus voor het apparaat wordt gedetecteerd, wordt het apparaat geëvalueerd als niet-compatibel.
  - **Laag**: het apparaat wordt als compatibel geëvalueerd als er bedreigingen van een laag niveau aanwezig zijn. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld**: het apparaat wordt als conform geëvalueerd als bestaande bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als bedreigingen met hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-compatibel beoordeeld.
  - **Hoog**: deze optie is het minst veilig, omdat alle bedreigingsniveaus zijn toegestaan. Deze optie kan handig zijn als u deze alleen gebruikt voor rapportagedoeleinden.

### <a name="google-play-protect"></a>Google Play Protect

- **Google Play Services is geconfigureerd**: hiermee kunt u **vereisen** dat de app Google Play Services wordt geïnstalleerd en ingeschakeld. Google Play Services maakt beveiligingsupdates mogelijk en vormt een basisafhankelijkheid voor veel beveiligingsfuncties op door Google gecertificeerde apparaten. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.
- **Bijgewerkte beveiligingsprovider**: hiermee kunt u **vereisen** dat het apparaat tegen bekende beveiligingsproblemen wordt beschermd door een bijgewerkte beveiligingsprovider. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.
- **Bedreigingsscan voor apps**: hiermee kunt u **vereisen** dat de Android-functie **Apps controleren** is ingeschakeld. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.

  > [!NOTE]
  > Deze functie is op oudere Android-platforms een nalevingsinstelling. Intune kan alleen controleren of deze instelling is ingeschakeld op het apparaatniveau.

- **SafetyNet-apparaatattestation**: hiermee kunt u instellen aan welk integriteitsniveau voor [SafetyNet-attestation](https://developer.android.com/training/safetynet/attestation.html) het apparaat moet voldoen. Uw opties zijn:
  - **Niet geconfigureerd** (standaard): deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Basisintegriteit controleren**
  - **Basisintegriteit en gecertificeerde apparaten controleren**

> [!NOTE]
> Zie [Beveiligingsbeleidsinstellingen voor Intune-apps](../apps/app-protection-policy-settings-android.md#conditional-launch) in Android om Google Play Protect-instellingen te configureren met behulp van beveiligingsbeleid voor apps.

## <a name="device-property-settings"></a>Instellingen voor apparaateigenschappen

- **Minimale versie van het besturingssysteem**: als een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt het gerapporteerd als niet-conform. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. Gebruikers kunnen dan kiezen om een upgrade van hun apparaat uit te voeren, waarna ze toegang tot bedrijfsresources krijgen.
- **Maximale versie van het besturingssysteem**: wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die is opgegeven in de regel, wordt de toegang tot bedrijfsresources geblokkeerd. De gebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel om de versie van het besturingssysteem toe te staan, kan dit apparaat geen toegang tot bedrijfsresources krijgen.

## <a name="system-security-settings"></a>Systeembeveiligingsinstellingen

### <a name="password"></a>Wachtwoord

- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**: **verplicht** gebruikers een wachtwoord in te voeren om toegang te krijgen tot hun apparaat. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.
- **Minimale wachtwoordlengte**: voer het minimale aantal cijfers of tekens aan waaruit het wachtwoord van de gebruiker moet bestaan.
- **Vereist wachtwoordtype**: kies of een wachtwoord alleen numerieke tekens mag bevatten of ook een combinatie van cijfers en andere tekens. Uw opties zijn:
  - **Standaard waarde voor apparaat**: als u wachtwoord compatibiliteit wilt evalueren, moet u een andere wachtwoord sterkte selecteren dan **standaard waarde**voor het apparaat.
  - **Lage beveiligingsbiometrie**
  - **Ten minste numeriek** (standaard)
  - **Numeriek complex**: herhaalde of opeenvolgende cijfers (zoals `1111` of `1234`) zijn niet toegestaan.
  - **Ten minste alfabetisch** 
  - **Ten minste alfanumeriek**
  - **Minstens alfanumeriek met symbolen**

- **Maximum aantal minuten van inactiviteit voordat wachtwoord is vereist**: geef aan na hoeveel niet-actieve tijd de gebruiker het wachtwoord opnieuw moet invoeren. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.
- **Wachtwoord verloopt (in dagen)** : selecteer het aantal dagen waarna het wachtwoord verloopt en de gebruiker een nieuw wachtwoord moet maken.
- **Aantal vorige wachtwoorden om hergebruik te voorkomen**: geef het aantal recente wachtwoorden op dat niet opnieuw mag worden gebruikt. Gebruik deze instelling om te voorkomen dat de gebruiker eerder gebruikte wachtwoorden hergebruikt.

### <a name="encryption"></a>Versleuteling

- **Versleuteling van gegevensopslag op een apparaat** (Android 4.0 en hoger of KNOX 4.0 en hoger): kies **Vereisen** om gegevensopslag op uw apparaten te versleutelen. Apparaten worden versleuteld wanneer u de instelling **Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten** kiest. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.

### <a name="device-security"></a>Apparaatbeveiliging

- **Apps van onbekende bronnen blokkeren**: kies deze optie om apparaten te **blokkeren** waarvoor 'Beveiliging > Onbekende bronnen' is ingeschakeld (ondersteund in Android 4.0 - Android 7.x, niet ondersteund in Android 8.0 en hoger). Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.

  Als u sideloading wilt uitvoeren voor apps, moeten onbekende bronnen worden toegestaan. Als u Android-apps niet met behulp van sideloading laadt, stelt u deze functie in op **Blokkeren** om dit nalevingsbeleid in te schakelen. 

  > [!IMPORTANT]
  > Voor sideloading van toepassingen moet de instelling **Apps uit onbekende bronnen blokkeren** zijn ingeschakeld. Dwing dit nalevingsbeleid alleen af als u Android-apps niet met behulp van sideloading op apparaten laadt.

- **Runtime-integriteit van de bedrijfsportal-app**: kies **Vereisen** om te bevestigen dat de bedrijfsportal-app aan de volgende vereisten voldoet:

  - De reguliere runtime-omgeving is geïnstalleerd
  - Is correct ondertekend
  - Bevindt zich niet in de foutopsporingsmodus
  - Is geïnstalleerd via een bekende bron

  Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.

- **USB-foutopsporing op apparaat blokkeren** (Android 4.2 of hoger): kies **Blokkeren** om te voorkomen dat apparaten de functie voor USB-foutopsporing gebruiken. Als u **Niet geconfigureerd** (standaard) kiest, wordt deze instelling niet beoordeeld op naleving of niet-naleving.
- **Minimaal beveiligingspatchniveau**(Android 6.0 of hoger): selecteer het oudste beveiligingspatchniveau dat een apparaat kan hebben. Apparaten die niet ten minste dit patchniveau hebben, zijn niet-conform. De datum moet worden opgegeven in de indeling `YYYY-MM-DD`.
- **Beperkte apps**: voer de **appnaam** en de **app-bundel-id** in van apps die moeten worden beperkt. Kies **Toevoegen**. Een apparaat waarop ten minste één beperkte app is geïnstalleerd, wordt gemarkeerd als niet-compatibel.

Selecteer **OK** > **Maken** om uw wijzigingen op te slaan.

## <a name="locations"></a>Locaties

In uw beleid kunt u naleving afdwingen op basis van de locatie van het apparaat. Kies uit bestaande locaties. Hebt u nog geen locatie? [Locaties (netwerkgrens) gebruiken](use-network-locations.md) in Intune biedt enige richtlijnen.

1. Kies **Locaties** > **Locaties selecteren**.
2. Controleer uw locatie in de lijst en kies **Selecteren**.
3. U kunt nu het beleid **opslaan**.

## <a name="next-steps"></a>Volgende stappen

- [Voeg acties voor niet-conforme apparaten toe](actions-for-noncompliance.md) en [gebruik bereiktags om beleidsregels te filteren](../fundamentals/scope-tags.md).
- [Controleer uw nalevingsbeleid](compliance-policy-monitor.md).
- Zie [Instellingen voor nalevingsbeleid voor Android Enterprise](compliance-policy-create-android-for-work.md)-apparaten.
