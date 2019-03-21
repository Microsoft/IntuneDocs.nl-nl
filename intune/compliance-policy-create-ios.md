---
title: Een iOS-nalevingsbeleid voor apparaten maken in Microsoft Intune - Azure | Microsoft Docs
description: Een Microsoft Intune-nalevingsbeleid voor iOS-apparaten maken of configureren om een e-mailaccount in te voeren, opengebroken apparaten te controleren, de minimale en maximale versie van het besturingssysteem te controleren en wachtwoordbeperkingen in te stellen, waaronder de wachtwoordlengte en de inactiviteit van apparaten.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/14/2018
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
ms.openlocfilehash: 42ce05d2f726147caee198c79db185b87854cffb
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566145"
---
# <a name="add-a-device-compliance-policy-for-ios-devices-in-intune"></a>Een apparaatnalevingsbeleid toevoegen voor iOS-apparaten in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Een Intune-apparaatnalevingsbeleid voor iOS bepaalt de regels en instellingen waaraan een iOS-apparaat moet voldoen om te voldoen aan het beleid. Wanneer u apparaatnalevingsbeleid gebruikt met voorwaardelijke toegang, kunt u toegang tot bedrijfsbronnen toestaan of blokkeren. U kunt ook apparaatrapporten krijgen en maatregelen nemen voor niet-naleving. Nalevingsbeleid voor apparaten kan voor elk platform worden gemaakt in de Intune Azure Portal. Zie [Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md) voor meer informatie over nalevingsbeleid en eventuele vereisten.

In de volgende tabel wordt beschreven hoe niet-compatibele instellingen worden beheerd wanneer een nalevingsbeleid wordt gebruikt in combinatie met beleid voor voorwaardelijke toegang.

---------------------------

| **Beleidsinstelling** | **iOS 8.0 en hoger** |
| --- | --- |
| **Configuratie van pincode of wachtwoord** | Hersteld |
| **Apparaatversleuteling** | Hersteld (door een pincode in te stellen) |
| **Opengebroken of geroot apparaat** | In quarantaine (geen instelling)
| **E-mailprofiel** | In quarantaine |
|**Minimale versie van het besturingssysteem** | In quarantaine |
| **Maximale versie van het besturingssysteem** | In quarantaine |
| **Windows Health Attestation** | Niet van toepassing |

---------------------------

**Hersteld** = het besturingssysteem van het apparaat dwingt naleving af. (De gebruiker wordt bijvoorbeeld gedwongen een pincode in te stellen.)

**In quarantaine** = het besturingssysteem van het apparaat dwingt geen naleving af. (Bij Android-apparaten bijvoorbeeld wordt de gebruiker niet gedwongen het apparaat te versleutelen.) Als het apparaat niet compatibel is, worden de volgende acties uitgevoerd:

- Het apparaat wordt geblokkeerd als een beleid voor voorwaardelijke toegang van toepassing is voor de gebruiker.
- De bedrijfsportal stelt de gebruiker op de hoogte van eventuele nalevingsproblemen.

## <a name="create-a-device-compliance-policy"></a>Een nalevingsbeleid voor apparaten maken

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. Selecteer voor **Platform** de optie **iOS**. 
5. Kies **Instellingen configureren** om instellingen op te geven voor **E-mailadres**, **Apparaatstatus**, **Apparaateigenschappen** en **Systeembeveiliging** zoals wordt beschreven in dit onderwerp. Selecteer **OK** en **Maken** als u klaar bent.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="email"></a>E-mail

- **Vereisen dat mobiele apparaten een beheerd e-mailprofiel hebben**: als u deze optie instelt op Vereisen, worden apparaten die geen e-mailprofiel hebben dat door Intune wordt beheerd als niet-conform gezien. Een apparaat heeft mogelijk geen beheerd e-mailprofiel als het niet correct is gekoppeld of als de gebruiker de e-mailaccount handmatig op het apparaat heeft ingesteld.

  Het apparaat wordt in de volgende situaties beschouwd als niet compatibel:
  - Het e-mailprofiel is geïmplementeerd voor een andere gebruikersgroep dan de gebruikersgroep waarvoor het nalevingsbeleid is bedoeld.
  - De gebruiker heeft al een e-mailaccount op het apparaat ingesteld dat overeenkomt met het Intune-e-mailprofiel dat op het apparaat is geïmplementeerd. Intune kan het door de gebruiker ingerichte profiel niet overschrijven en kan het daarom niet beheren. Om naleving te garanderen, moet de gebruiker de bestaande e-mailinstellingen verwijderen. Daarna kan Intune het beheerde e-mailprofiel installeren.

- **Selecteer het e-mailprofiel dat moet worden beheerd door Intune**: als de instelling **E-mailaccount moet worden beheerd door Intune** is geselecteerd, kiest u **Selecteren** om het e-mailprofiel voor Intune op te geven. Het e-mailprofiel moet aanwezig zijn op het apparaat.

Zie [De toegang tot zakelijke e-mail configureren met e-mailprofielen bij Microsoft Intune](email-settings-configure.md) voor meer informatie over e-mailprofielen.

## <a name="device-health"></a>Device health

- **Apparaten die zijn opengebroken**: als u deze instelling inschakelt, geeft u aan dat opengebroken apparaten niet compatibel zijn.
- **Vereisen dat het apparaat het apparaatdreigingsniveau niet overschrijdt**: (iOS 8.0 en nieuwer) kies het maximale dreigingsniveau waarbij apparaten moeten worden gemarkeerd als niet-conform. Apparaten die dit dreigingsniveau overschrijden, worden gemarkeerd als niet-conform:
  - **Beveiligd**: deze optie is het veiligst, omdat het apparaat geen bedreigingen kan hebben. Als een van de bedreigingsniveaus voor het apparaat wordt gedetecteerd, wordt het apparaat geëvalueerd als niet-compatibel.
  - **Laag**: het apparaat wordt als compatibel geëvalueerd als er bedreigingen van een laag niveau aanwezig zijn. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld**: het apparaat wordt als conform geëvalueerd als bestaande bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als bedreigingen met hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-compatibel beoordeeld.
  - **Hoog**: deze optie is het minst veilig, omdat alle bedreigingsniveaus zijn toegestaan. Deze optie kan handig zijn als u deze alleen gebruikt voor rapportagedoeleinden.

## <a name="device-properties"></a>Apparaateigenschappen

- **Minimale versie van het besturingssysteem die is vereist**: wanneer een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt het apparaat gerapporteerd als niet-compatibel. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De gebruiker kan kiezen om het apparaat bij te werken. Daarna zijn de bedrijfsbronnen toegankelijk.
- **Maximale versie van het besturingssysteem die is toegestaan**: wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die in de regel is opgegeven, wordt de toegang tot bedrijfsbronnen geblokkeerd. De gebruiker wordt vervolgens gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel die de versie van het besturingssysteem toestaat, kan dit apparaat geen toegang tot bedrijfsbronnen krijgen.
- **Minimale buildversie van het besturingssysteem**: als Apple beveiligingsupdates publiceert, wordt het buildnummer meestal bijgewerkt, niet de versie van het besturingssysteem. Gebruik deze functie om het buildnummer in te voeren dat minimaal is toegestaan op het apparaat. Deze controle op naleving biedt ondersteuning voor apparaten met iOS 8.0 en hoger. 
- **Maximale buildversie van het besturingssysteem**: als Apple beveiligingsupdates publiceert, wordt het buildnummer meestal bijgewerkt, niet de versie van het besturingssysteem. Gebruik deze functie om het buildnummer in te voeren dat maximaal is toegestaan op het apparaat. Deze controle op naleving biedt ondersteuning voor apparaten met iOS 8.0 en hoger.

## <a name="system-security"></a>Systeembeveiliging

### <a name="password"></a>Wachtwoord

> [!NOTE]
> Nadat een nalevings- of configuratiebeleid op een iOS-apparaat is toegepast, wordt gebruikers elke vijftien minuten gevraagd een wachtwoordcode in te stellen. Gebruikers wordt continu gevraagd een wachtwoordcode in te stellen totdat de code is ingesteld.

- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**: **verplicht** gebruikers een wachtwoord in te voeren om toegang te krijgen tot hun apparaat. iOS-apparaten die gebruikmaken van een wachtwoord, zijn versleuteld.
- **Eenvoudige wachtwoorden**: stel deze optie in op **Blokkeren** zodat de gebruiker geen eenvoudig wachtwoord kan maken, zoals **1234** of **1111**. Stel deze optie in op **Niet geconfigureerd** om gebruikers toe te staan wachtwoorden als **1234** of **1111** te maken.
- **Minimale wachtwoordlengte**: voer het minimale aantal cijfers of tekens aan waaruit het wachtwoord moet bestaan.
- **Vereist wachtwoordtype**: kies of een wachtwoord alleen **numerieke** tekens mag bevatten of uit een combinatie van cijfers en andere tekens moet bestaan (**alfanumeriek**).
- **Het minimumaantal niet-alfanumerieke tekens in een wachtwoord**: voer het aantal symbooltekens (zoals &, #, %, !, enzovoort) in dat het wachtwoord moet bevatten.

    Als u een hogere waarde instelt, moet de gebruiker een wachtwoord maken dat complexer is.

- **Maximum aantal minuten van inactiviteit voordat wachtwoord is vereist**: geef aan na hoeveel niet-actieve tijd de gebruiker het wachtwoord opnieuw moet invoeren.
- **Wachtwoord verloopt (in dagen)**: selecteer het aantal dagen waarna het wachtwoord verloopt en gebruikers een nieuw wachtwoord moeten maken.
- **Aantal vorige wachtwoorden om hergebruik te voorkomen**: geef op hoeveel eerder gebruikte wachtwoorden niet opnieuw mogen worden gebruikt.

### <a name="restricted-applications"></a>Beperkte toepassingen 
U kunt apps beperken door de bundel-id’s toe te voegen aan het beleid. Als vervolgens de app op een apparaat is geïnstalleerd, wordt het apparaat gemarkeerd als niet-compatibel. 
- **App-naam**: geef een gebruiksvriendelijke naam op om u te helpen de bundel-id te identificeren. 
- **App-bundel-id**: Geef de unieke bundel-id op die is toegewezen door de app-provider. Zie [De bundel-id vinden voor een iOS-app](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app) om de bundel-id te vinden.  

## <a name="assign-user-groups"></a>Gebruikersgroepen toewijzen

1. Kies een beleid dat u hebt geconfigureerd. Bestaande beleidsregels bevinden zich in **Apparaatcompatibiliteit** > **Beleid**.
2. Kies het beleid en kies **Toewijzingen**. U kunt Azure Active Directory-beveiligingsgroepen (AD) opnemen of uitsluiten.
3. Kies **Geselecteerde groepen** om uw Azure AD-beveiligingsgroepen te zien. Selecteer de gebruikersgroepen waarop u dit beleid wilt toepassen en kies **Opslaan** om het beleid te implementeren op gebruikers.

U hebt het beleid toegepast op gebruikers. De apparaten die worden gebruikt door de gebruikers op wie het beleid is toegepast, worden gecontroleerd om te zien of ze compatibel zijn.

## <a name="next-steps"></a>Volgende stappen
[E-mail automatiseren en acties voor niet-conforme apparaten toevoegen](actions-for-noncompliance.md)  
[Nalevingsbeleid voor Intune-apparaten controleren](compliance-policy-monitor.md)
