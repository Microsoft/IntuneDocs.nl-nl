---
title: Een Android-nalevingsbeleid voor apparaten maken in Microsoft Intune - Azure | Microsoft Docs
description: Een Microsoft Intune-apparaatnalevingsbeleid maken of configureren voor Android-apparaten. Kies ervoor opengebroken apparaten toe te staan, stel het acceptabele dreigingsniveau in, controleer op Google Play, voer de minimale en maximale besturingssysteemversie in, kies uw wachtwoordvereisten en sta sideloading van toepassingen toe.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2277da45ad1404269571f36dec0c16443409b39f
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744700"
---
# <a name="add-a-device-compliance-policy-for-android-devices-in-intune"></a>Een apparaatnalevingsbeleid toevoegen voor Android-apparaten in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Een Intune-apparaatnalevingsbeleid voor Android bepaalt de regels en instellingen waaraan een Android-apparaat moet voldoen om te voldoen aan het beleid. U kunt dit beleid met voorwaardelijke toegang gebruiken om toegang tot bedrijfsresources toe te staan of te blokkeren. U kunt ook apparaatrapporten krijgen en maatregelen nemen voor niet-naleving. U maakt nalevingsbeleid voor apparaten voor elk platform in Intune Azure Portal. Zie [Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md) voor meer informatie over nalevingsbeleid en eventuele vereisten.

In de volgende tabel wordt beschreven hoe niet-compatibele instellingen worden beheerd wanneer een nalevingsbeleid wordt gebruikt in combinatie met beleid voor voorwaardelijke toegang.

--------------------

|**Beleidsinstelling**| **Android 4.0 of hoger, Samsung Knox Standard 4.0 of hoger** |
| --- | ----|
| **Configuratie van pincode of wachtwoord** |  In quarantaine |
| **Apparaatversleuteling** | In quarantaine |
| **Opengebroken of geroot apparaat** | In quarantaine (geen instelling) |
| **E-mailprofiel** | Niet van toepassing |
| **Minimale versie van het besturingssysteem** | In quarantaine |
| **Maximale versie van het besturingssysteem** |   In quarantaine |
| **Windows Health Attestation** | Niet van toepassing |

--------------------------

**Hersteld** = het besturingssysteem van het apparaat dwingt naleving af. (De gebruiker wordt bijvoorbeeld gedwongen een pincode in te stellen.)

**In quarantaine** = het besturingssysteem van het apparaat dwingt geen naleving af. (Bij Android-apparaten bijvoorbeeld wordt de gebruiker niet gedwongen het apparaat te versleutelen.) Als het apparaat niet compatibel is, worden de volgende acties uitgevoerd:

- Het apparaat wordt geblokkeerd als een beleid voor voorwaardelijke toegang van toepassing is voor de gebruiker.
- De bedrijfsportal stelt de gebruiker op de hoogte van eventuele nalevingsproblemen.

## <a name="create-a-device-compliance-policy"></a>Een nalevingsbeleid voor apparaten maken

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. Selecteer voor **Platform** de optie **Android**. Kies **Instellingen configureren** om instellingen op te geven voor de **Apparaatstatus**, de **Apparaateigenschappen** en de **Systeembeveiliging**. Wanneer u klaar bent, selecteert u **OK** en **Maken**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant based on the configured settings in this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **OK** when you are finished creating all the actions.--->

<!---##  Compliance policy settings--->

## <a name="device-health"></a>Device health

- **Geroote apparaten**: als u deze instelling inschakelt, geeft u aan dat geroote apparaten niet als conform worden beoordeeld.
- **Vereisen dat het apparaat het apparaatdreigingsniveau niet overschrijdt**: gebruik deze instelling om de risicobeoordeling uit de Lookout MTP-oplossing als voorwaarde voor naleving te gebruiken. Kies het maximaal toegestane bedreigingsniveau:
  - **Beveiligd**: deze optie is het veiligst, omdat het apparaat geen bedreigingen kan hebben. Als een van de bedreigingsniveaus voor het apparaat wordt gedetecteerd, wordt het apparaat geëvalueerd als niet-compatibel.
  - **Laag**: het apparaat wordt als compatibel geëvalueerd als er bedreigingen van een laag niveau aanwezig zijn. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld**: het apparaat wordt als conform geëvalueerd als bestaande bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als bedreigingen met hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-compatibel beoordeeld.
  - **Hoog**: deze optie is het minst veilig, omdat alle bedreigingsniveaus zijn toegestaan. Deze optie kan handig zijn als u deze alleen gebruikt voor rapportagedoeleinden.
- **Google Play Services is geconfigureerd**: hiermee kunt u vereisen dat de app Google Play Services is geïnstalleerd en ingeschakeld. Google Play Services maakt beveiligingsupdates mogelijk en vormt een basisafhankelijkheid voor veel beveiligingsfuncties op door Google gecertificeerde apparaten.
- **Bijgewerkte beveiligingsprovider**: hiermee kunt u vereisen dat het apparaat tegen bekende beveiligingsproblemen wordt beschermd door een bijgewerkte beveiligingsprovider.
- **Bedreigingsscan voor apps**: hiermee kunt u vereisen dat de Android-functie **Apps controleren** is ingeschakeld.

  > [!NOTE]
  > Deze functie is op oudere Android-platforms een nalevingsinstelling. Intune kan alleen controleren of deze instelling is ingeschakeld op het apparaatniveau. Op apparaten met werkprofielen, (Android for Work) is deze instelling te vinden als een configureerbare beleidsinstelling. Hiermee kunnen beheerders de instelling voor een apparaat inschakelen.

  Als uw bedrijf Android-werkprofielen gebruikt, kunt u **Bedreigingsscan voor apps** inschakelen voor uw geregistreerde apparaten. Hiermee kunt u een apparaatprofiel instellen en de systeembeveiligingsinstelling verplicht stellen. Zie [Android for Work-apparaatbeperkingsinstellingen in Intune](device-restrictions-android-for-work.md) voor meer informatie.

- **SafetyNet-apparaatattestation**: hiermee kunt u instellen aan welk integriteitsniveau voor [SafetyNet-attestation](https://developer.android.com/training/safetynet/attestation.html) het apparaat moet voldoen. Uw opties zijn:
  - **Niet geconfigureerd**
  - **Basisintegriteit controleren**
  - **Basisintegriteit en gecertificeerde apparaten controleren**

## <a name="device-property-settings"></a>Instellingen voor apparaateigenschappen

- **Minimale versie van het besturingssysteem**: als een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt het gerapporteerd als niet-conform. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. Gebruikers kunnen dan kiezen om een upgrade van hun apparaat uit te voeren, waarna ze toegang tot bedrijfsresources krijgen.
- **Maximale versie van het besturingssysteem**: wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die is opgegeven in de regel, wordt de toegang tot bedrijfsresources geblokkeerd. De gebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel om de versie van het besturingssysteem toe te staan, kan dit apparaat geen toegang tot bedrijfsresources krijgen.

## <a name="system-security-settings"></a>Systeembeveiligingsinstellingen

### <a name="password"></a>Wachtwoord

- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**: **verplicht** gebruikers een wachtwoord in te voeren om toegang te krijgen tot hun apparaat.
- **Minimale wachtwoordlengte**: voer het minimale aantal cijfers of tekens aan waaruit het wachtwoord van de gebruiker moet bestaan.
- **Vereist wachtwoordtype**: selecteer of een wachtwoord alleen numerieke tekens mag bevatten of uit een combinatie van cijfers en andere tekens moet bestaan. U kunt kiezen uit:
  - **Standaardwaarde apparaat**
  - **Lage beveiligingsbiometrie**
  - **Ten minste numeriek**
  - **Numeriek complex**: herhaalde of opeenvolgende cijfers (zoals 1111 of 1234) zijn niet toegestaan.
  - **Ten minste alfabetisch**
  - **Ten minste alfanumeriek**
  - **Minstens alfanumeriek met symbolen**
- **Maximum aantal minuten van inactiviteit voordat wachtwoord is vereist**: geef aan na hoeveel niet-actieve tijd de gebruiker het wachtwoord opnieuw moet invoeren.
- **Wachtwoord verloopt (in dagen)**: selecteer het aantal dagen waarna het wachtwoord verloopt en de gebruiker een nieuw wachtwoord moet maken.
- **Aantal vorige wachtwoorden om hergebruik te voorkomen**: geef het aantal recente wachtwoorden op dat niet opnieuw mag worden gebruikt. Gebruik deze instelling om te voorkomen dat de gebruiker eerder gebruikte wachtwoorden hergebruikt.

### <a name="encryption"></a>Versleuteling

- **Versleuteling van gegevensopslag op een apparaat** (Android 4.0 en hoger of KNOX 4.0 en hoger): kies **Vereisen** om gegevensopslag op uw apparaten te versleutelen. Apparaten worden versleuteld wanneer u de instelling **Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten** kiest.

### <a name="device-security"></a>Apparaatbeveiliging

- **Apps van onbekende bronnen blokkeren**: kies deze optie om apparaten te blokkeren waarvoor 'Beveiliging > Onbekende bronnen' is ingeschakeld (Android 4.0 - Android 7.x. Niet ondersteund door Android 8.0 en hoger). Als u sideloading wilt uitvoeren voor apps, moeten onbekende bronnen worden toegestaan. Schakel dit nalevingsbeleid in als u Android-apps niet met behulp van sideloading laadt.

  > [!IMPORTANT]
  > Voor sideloading van toepassingen moet de instelling **Apps uit onbekende bronnen blokkeren** zijn ingeschakeld. Dwing dit nalevingsbeleid alleen af als u Android-apps niet met behulp van sideloading op apparaten laadt.

- **Runtime-integriteit van de bedrijfsportal-app**: hiermee controleert u of in de bedrijfsportal-app de standaardruntime-omgeving is geïnstalleerd, correct is ondertekend, niet in de foutopsporingsmodus is en is geïnstalleerd vanuit een bekende bron.
- **USB-foutopsporing op apparaat blokkeren** (Android 4.2 of hoger): kies deze optie om te voorkomen dat apparaten de functie voor USB-foutopsporing gebruiken.
- **Minimaal beveiligingspatchniveau**(Android 6.0 of hoger): selecteer het oudste beveiligingspatchniveau dat een apparaat kan hebben. Apparaten die niet ten minste dit patchniveau hebben, zijn niet-conform. De datum moet worden opgegeven in de indeling `YYYY-MM-DD`.

## <a name="locations"></a>Locaties

Maak in uw beleid een keuze uit bestaande locaties. Hebt u nog geen locatie? In [Locaties (netwerk fence) in Intune gebruiken](use-network-locations.md) vindt u enkele richtlijnen.

1. Kies **Locaties selecteren**.
2. Controleer uw locatie in de lijst en kies **Selecteren**.
3. U kunt nu het beleid **opslaan**.
4. Selecteer **Acties voor niet-naleving**. De standaardactie markeert het apparaat onmiddellijk als niet-compatibel. Deze actie is van toepassing wanneer u ten minste één locatie selecteert en als het apparaat niet is gekoppeld aan de geselecteerde locaties.

  U kunt deze actie veranderen om het schema wanneer het apparaat wordt gemarkeerd als niet-compatibel bij te werken, zoals na één dag. U kunt ook een tweede actie toevoegen, waarbij een e-mailbericht wordt verzonden naar de gebruiker wanneer het apparaat niet meer voldoet aan de locaties.

## <a name="assign-user-groups"></a>Gebruikersgroepen toewijzen

1. Kies een beleid dat u hebt geconfigureerd. Bestaande beleidsregels bevinden zich in **Apparaatcompatibiliteit** > **Beleid**.
2. Kies het beleid en kies **Toewijzingen**. U kunt Azure Active Directory-beveiligingsgroepen (AD) opnemen of uitsluiten.
3. Kies **Geselecteerde groepen** om uw Azure AD-beveiligingsgroepen te zien. Selecteer de gebruikersgroepen waarop u dit beleid wilt toepassen en kies **Opslaan** om het beleid te implementeren op gebruikers.

U hebt het beleid toegepast op gebruikers. De apparaten die worden gebruikt door de gebruikers op wie het beleid is toegepast, worden gecontroleerd om te zien of ze compatibel zijn.

## <a name="next-steps"></a>Volgende stappen
[E-mail automatiseren en acties voor niet-conforme apparaten toevoegen](actions-for-noncompliance.md)  
[Nalevingsbeleid voor Intune-apparaten controleren](compliance-policy-monitor.md)