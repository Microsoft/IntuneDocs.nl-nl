---
title: Een iOS-nalevingsbeleid voor apparaten maken in Microsoft Intune - Azure | Microsoft Docs
description: U kunt in Microsoft Intune een nalevingsbeleid voor iOS-apparaten maken om een e-mailaccount in te voeren, opengebroken apparaten te controleren, de minimale en maximale versie van het besturingssysteem te controleren en wachtwoordbeperkingen in te stellen, waaronder de wachtwoordlengte en de inactiviteit van apparaten.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 887f45cdc79aa5e45de3e8a1df5d12665d2ed8ab
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="add-a-device-compliance-policy-for-ios-devices-in-intune"></a>Een apparaatnalevingsbeleid toevoegen voor iOS-apparaten in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Een Intune-apparaatnalevingsbeleid voor iOS bepaalt de regels en instellingen waaraan een iOS-apparaat moet voldoen om te voldoen aan het beleid. Wanneer u apparaatnalevingsbeleid gebruikt met voorwaardelijke toegang, kunt u toegang tot bedrijfsbronnen toestaan of blokkeren. U kunt ook apparaatrapporten krijgen en maatregelen nemen voor niet-naleving. Nalevingsbeleid voor apparaten kan voor elk platform worden gemaakt in de Intune Azure Portal. Zie [Aan de slag met apparaatnaleving](device-compliance-get-started.md) voor informatie over nalevingsbeleid en de vereisten waaraan u moet voldoen voordat u een nalevingsbeleid maakt.

In de volgende tabel wordt beschreven hoe niet-compatibele instellingen worden beheerd wanneer een nalevingsbeleid wordt gebruikt in combinatie met beleid voor voorwaardelijke toegang.

| **Beleidsinstelling** | **iOS 8.0 en hoger** |
| --- | --- |
| **Configuratie van pincode of wachtwoord** | Hersteld |
| **Apparaatversleuteling** | Hersteld (door een pincode in te stellen) |
| **Opengebroken of geroot apparaat** | In quarantaine (geen instelling)
| **E-mailprofiel** | In quarantaine |
|**Minimale versie van het besturingssysteem** | In quarantaine |
| **Maximale versie van het besturingssysteem** | In quarantaine |
| **Windows Health Attestation** | Niet van toepassing |

**Hersteld** = het besturingssysteem van het apparaat dwingt naleving af. (De gebruiker wordt bijvoorbeeld gedwongen een pincode in te stellen.)

**In quarantaine** = het besturingssysteem van het apparaat dwingt geen naleving af. (Bij Android-apparaten bijvoorbeeld wordt de gebruiker niet gedwongen het apparaat te versleutelen.) Als het apparaat niet compatibel is, worden de volgende acties uitgevoerd:

- Het apparaat wordt geblokkeerd als een beleid voor voorwaardelijke toegang van toepassing is voor de gebruiker.
- De bedrijfsportal stelt de gebruiker op de hoogte van eventuele nalevingsproblemen.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Een nalevingsbeleid maken in Azure Portal

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaatcompatibiliteit** > **Beleid** > **Beleid maken**.
4. Voer een naam en beschrijving in en kies het platform waarop u dit beleid wilt toepassen.
5. Kies **Instellingen** om instellingen op te geven voor het **e-mailadres**, de **apparaatstatus**, de **apparaateigenschappen** en de **systeembeveiliging**. Als u klaar bent, kiest u **OK**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Gebruikersgroepen toewijzen

Als u een nalevingsbeleid aan gebruikers wilt toewijzen, kiest u een beleid dat u hebt geconfigureerd. Bestaande beleidsregels vindt u in het deelvenster **Apparaatnaleving - beleid**.

1. Kies het beleid dat u aan gebruikers wilt toewijzen en kies **Toewijzingen**. Er wordt een deelvenster geopend waar u **Azure Active Directory-beveiligingsgroepen** kunt selecteren en aan het beleid kunt toewijzen.
2. Kies **Geselecteerde groepen** om het deelvenster met de Azure AD-beveiligingsgroepen te openen.  Als u **Opslaan** kiest, wordt het beleid bij gebruikers geïmplementeerd.

U hebt het beleid toegepast op gebruikers.  De apparaten die worden gebruikt door de gebruikers op wie het beleid is toegepast, worden gecontroleerd om te zien of ze compatibel zijn.

<!---## Compliance policy settings--->

## <a name="email"></a>E-mail

- **E-mailaccount moet worden beheerd door Intune**: wanneer deze optie is ingesteld op **Ja**, moet het e-mailprofiel worden gebruikt dat is geïmplementeerd op het apparaat. Het apparaat wordt in de volgende situaties beschouwd als niet compatibel:
  - Het e-mailprofiel is geïmplementeerd voor een andere gebruikersgroep dan de gebruikersgroep waarvoor het nalevingsbeleid is bedoeld.
  - De gebruiker heeft al een e-mailaccount op het apparaat ingesteld dat overeenkomt met het Intune-e-mailprofiel dat op het apparaat is geïmplementeerd. Intune kan het door de gebruiker ingerichte profiel niet overschrijven en kan het daarom niet beheren. Om naleving te garanderen, moet de gebruiker de bestaande e-mailinstellingen verwijderen. Daarna kan Intune het beheerde e-mailprofiel installeren.
- **Selecteer het e-mailprofiel dat moet worden beheerd door Intune**: als de instelling **E-mailaccount moet worden beheerd door Intune** is geselecteerd, kiest u **Selecteren** om het e-mailprofiel voor Intune op te geven. Het e-mailprofiel moet aanwezig zijn op het apparaat.

Zie [De toegang tot zakelijke e-mail configureren met e-mailprofielen bij Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) voor meer informatie over e-mailprofielen.

## <a name="device-health"></a>Device health

- **Apparaten die zijn opengebroken**: als u deze instelling inschakelt, geeft u aan dat opengebroken apparaten niet compatibel zijn.
- **Vereisen dat het apparaat het apparaatdreigingsniveau niet overschrijdt**: kies het maximale dreigingsniveau waarbij apparaten moeten worden gemarkeerd als niet-compatibel. Als u het dreigingsniveau bijvoorbeeld instelt op **Gemiddeld**, zijn apparaten met een gemiddeld, laag of beveiligd niveau compatibel. Apparaten met een hoog dreigingsniveau zijn niet compatibel.

## <a name="device-properties"></a>Apparaateigenschappen

- **Minimale versie van het besturingssysteem die is vereist**: wanneer een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt het apparaat gerapporteerd als niet-compatibel. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De gebruiker kan kiezen om het apparaat bij te werken. Daarna zijn de bedrijfsbronnen toegankelijk.
- **Maximale versie van het besturingssysteem die is toegestaan**: wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die in de regel is opgegeven, wordt de toegang tot bedrijfsbronnen geblokkeerd. De gebruiker wordt vervolgens gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel die de versie van het besturingssysteem toestaat, kan dit apparaat geen toegang tot bedrijfsbronnen krijgen.

## <a name="system-security"></a>Systeembeveiliging

### <a name="password"></a>Wachtwoord

> [!NOTE]
> Nadat een nalevings- of configuratiebeleid op een iOS-apparaat is toegepast, wordt gebruikers elke vijftien minuten gevraagd een wachtwoordcode in te stellen. Gebruikers wordt continu gevraagd een wachtwoordcode in te stellen totdat de code is ingesteld.

- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**: stel deze optie in op **Ja** als u wilt aangeven dat gebruikers een wachtwoord moeten invoeren om toegang te krijgen tot hun apparaat. iOS-apparaten die gebruikmaken van een wachtwoord, zijn versleuteld.
- **Eenvoudige wachtwoorden**: stel deze optie in op **Ja** zodat de gebruiker een wachtwoord zoals **1234** of **1111** kan maken.
- **Minimale wachtwoordlengte**: voer het minimale aantal cijfers of tekens aan waaruit het wachtwoord moet bestaan.
- **Vereist wachtwoordtype**: geef aan of de gebruiker een **alfanumeriek** of een **numeriek** wachtwoord moet maken.
- **Het minimumaantal niet-alfanumerieke tekens in een wachtwoord**: voer het aantal symbooltekens (zoals &, #, %, !, enzovoort) in dat het wachtwoord moet bevatten.

    Als u een hogere waarde instelt, moet de gebruiker een wachtwoord maken dat complexer is.

- **Maximum aantal minuten van inactiviteit voordat wachtwoord is vereist**: geef aan na hoeveel niet-actieve tijd de gebruiker het wachtwoord opnieuw moet invoeren.
- **Wachtwoord verloopt (in dagen)**: selecteer het aantal dagen waarna het wachtwoord verloopt en gebruikers een nieuw wachtwoord moeten maken.
- **Aantal vorige wachtwoorden om hergebruik te voorkomen**: geef op hoeveel eerder gebruikte wachtwoorden niet opnieuw mogen worden gebruikt.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
