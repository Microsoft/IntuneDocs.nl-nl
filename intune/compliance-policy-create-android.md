---
title: Een nalevingsbeleid maken voor Android
titleSuffix: Azure portal
description: Meer informatie over het maken van nalevingsbeleid voor Android-apparaten.
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b67314ec37198553adc226424bc226293350453b
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-create-a-device-compliance-policy-for-android-devices-in-intune"></a>Een apparaatnalevingsbeleid maken voor Android-apparaten in Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Nalevingsbeleid voor apparaten wordt voor elk platform gemaakt in Intune Azure Portal. 

- Zie het onderwerp [What is device compliance?](device-compliance.md) (Wat is apparaatnaleving?) voor meer informatie over een nalevingsbeleid.
- Zie [Get started with device compliance](device-compliance-get-started.md) (Aan de slag met apparaatnaleving) voor informatie over de vereisten die moet uitvoeren voordat u een nalevingsbeleid gaat maken.

## <a name="to-create-a-device-compliance-policy"></a>Een nalevingsbeleid voor apparaten maken

1. Kies **Apparaatcompatibiliteit instellen** op de blade **Intune**. Kies **Alle apparaatnalevingsbeleidsregels** onder **Beheren** en kies **Maken**.
2. Typ een naam, beschrijving en kies het platform waarop u dit beleid wilt toepassen.
3. Kies **Nalevingsvereisten** om de instellingen voor de **beveiliging**, **apparaatstatus** en **apparaateigenschappen** op te geven. Kies **OK** als u klaar bent.

<!-- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant based on the configured settings in this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **OK** when you are finished creating all the actions.-->

## <a name="to-assign-user-groups"></a>Gebruikersgroepen toewijzen

Als u een nalevingsbeleid aan gebruikers wilt toewijzen, kiest u een beleid dat u hebt geconfigureerd. Bestaande beleidsregels vindt u op de blade **Naleving - Beleid**.

1. Kies het beleid en kies **Toewijzingen**. Hiermee opent u de blade waar u **Azure Active Directory-beveiligingsgroepen** kunt selecteren en aan het beleid kunt toewijzen.
2. Kies **Groepen selecteren** om de blade met de Azure AD-beveiligingsgroepen te openen. Hier vindt u de beveiligingsgroepen in uw Azure Active Directory.  Selecteer de gebruikersgroepen waarop u dit beleid wilt toepassen en kies **Selecteren**. Als u **Selecteren** kiest, wordt het beleid bij gebruikers geïmplementeerd.

U hebt het beleid toegepast op gebruikers.  De apparaten die worden gebruikt door de gebruikers op wie het beleid is toegepast, worden gecontroleerd om te zien of ze voldoen aan het beleid.

<!---##  Compliance policy settings--->

## <a name="device-health-and-security-settings"></a>Status en beveiligingsinstellingen van apparaat

- **Jailbreaken of uitvoeren als rootgebruiker niet toegestaan**: als u deze instelling inschakelt, worden apparaten waarop jailbreaking is uitgevoerd of die als rootgebruiker worden uitgevoerd, als niet-compatibel beschouwd.
- **Vereisen dat de installatie van apps van onbekende bronnen wordt voorkomen (Android 4.0 en hoger)**: als u apparaten wilt blokkeren waarop **Beveiliging** > **Onbekende bronnen** op het apparaat is ingeschakeld, schakelt u deze instelling in en stelt u deze in op **Ja**.

### <a name="important"></a>Belangrijk

Voor sideloading-toepassingen moet de instelling **Onbekende bronnen** zijn ingeschakeld. Dwing dit nalevingsbeleid alleen af als u Android-apps niet met behulp van sideloading op apparaten laadt.

- **Vereisen dat de USB-foutopsporing is uitgeschakeld (Android 4.2 of hoger)**: deze instelling bepaalt of moet worden gedetecteerd of de USB-foutopsporingsoptie op het apparaat is ingeschakeld.
- **Vereisen dat Apparaat scannen op beveiligingsbedreigingen is ingeschakeld op apparaten (Android 4.2 - 4.4)**: deze instelling geeft aan dat de functie **Apps controleren** is ingeschakeld op het apparaat.
- **Minimaal niveau voor de Android-beveiligingspatch (Android 6.0 of hoger)**: gebruik deze instelling om het minimale Android-patchniveau op te geven. Apparaten die niet ten minste dit patchniveau hebben, worden als niet-compatibel gezien. De datum moet de volgende notatie hebben: dd-mm-jjjj.
- **Vereisen dat Device Threat Protection wordt ingeschakeld**: gebruik deze instelling om de risicobeoordeling uit de Lookout MTP-oplossing als voorwaarde voor naleving te gebruiken. Kies het maximaal toegestane bedreigingsniveau. U kunt daarbij kiezen uit:
  - **Geen (beveiligd)**: dit is het meest veilige niveau. Dit betekent dat er op het apparaat geen bedreigingen mogen staan. Als een van de bedreigingsniveaus voor het apparaat wordt gedetecteerd, wordt het apparaat geëvalueerd als niet-compatibel.
  - **Laag**: het apparaat wordt geëvalueerd als compatibel als er alleen bedreigingen van laag niveau aanwezig zijn. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld**: het apparaat wordt geëvalueerd als compatibel als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als bedreigingen met hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-compatibel beoordeeld.
  - **Hoog**: dit is de minst veilige optie. In principe zijn hierdoor alle bedreigingsniveaus toegestaan. Het is wellicht het beste als u deze oplossing alleen gebruikt voor rapportagedoeleinden.

Zie [De regel Device Threat Protection inschakelen in het nalevingsbeleid](https://docs.microsoft.com/intune-classic/deploy-use/enable-device-threat-protection-rule-in-compliance-policy) voor meer informatie.

## <a name="system-security-settings"></a>Systeembeveiligingsinstellingen

### <a name="password"></a>Wachtwoord

- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**: stel deze optie in op **Ja** als u wilt aangeven dat gebruikers een wachtwoord moeten invoeren om toegang te krijgen tot hun apparaat.
- **Minimale wachtwoordlengte**: hiermee geeft u het minimale aantal cijfers of tekens aan waaruit het wachtwoord van de gebruiker moet bestaan.
- **Wachtwoordkwaliteit**: met deze instelling wordt gedetecteerd of de vereisten voor het wachtwoord die u opgeeft, op het apparaat zijn geconfigureerd. Gebruik deze instelling als u wilt afdwingen dat gebruikers voldoen aan bepaalde wachtwoordvereisten voor Android-apparaten. U kunt kiezen uit:
  - **Lage beveiligingsbiometrie**
  - **Vereist**
  - **Ten minste numeriek**
  - **Ten minste alfabetisch**
  - **Ten minste alfanumeriek**
  - **Alfanumeriek met tekens**
- **Minuten van inactiviteit voordat wachtwoord vereist is**: hiermee geeft u aan na hoeveel niet-actieve tijd de gebruiker het wachtwoord opnieuw moet invoeren.
- **Wachtwoord verloopt (in dagen)**: selecteer het aantal dagen waarna het wachtwoord verloopt en gebruikers een nieuw wachtwoord moeten maken.
- **Wachtwoordgeschiedenis onthouden:** gebruik deze instelling samen met **Wachtwoorden niet opnieuw gebruiken** om te voorkomen dat gebruikers eerder gebruikte wachtwoorden opnieuw gebruiken.
- **Wachtwoorden niet opnieuw gebruiken**: als u **Wachtwoordgeschiedenis onthouden** hebt geselecteerd, geeft u het aantal eerder gebruikte wachtwoorden op dat niet opnieuw kan worden gebruikt.
- **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status**: gebruik deze instelling samen met de instelling **Minuten van inactiviteit voordat wachtwoord vereist is**. De gebruiker wordt gevraagd een wachtwoord op te geven om toegang te krijgen tot een apparaat dat inactief is geweest gedurende de tijd die is opgegeven bij de instelling **Minuten van inactiviteit voordat wachtwoord vereist is**.

### <a name="encryption"></a>Versleuteling

- **Versleuteling vereisen op een mobiel apparaat:** stel deze optie in op **Ja** als u wilt aangeven dat apparaten moeten worden versleuteld om verbinding te maken met resources. Apparaten worden versleuteld wanneer u de instelling **Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten** kiest.

## <a name="device-property-settings"></a>Instellingen voor apparaateigenschappen

- **Minimale versie van het besturingssysteem die is vereist**: wanneer een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt dit apparaat gerapporteerd als niet-compatibel. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. Gebruikers kunnen dan kiezen om een upgrade van hun apparaat uit te voeren, waarna ze toegang tot bedrijfsbronnen krijgen.
- **Maximale versie van het besturingssysteem die is toegestaan**: wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die in de regel is opgegeven, wordt de toegang tot bedrijfsresources geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met de IT-beheerder. Totdat er een wijziging is doorgevoerd in regels om de versie van het besturingssysteem toe te staan, kan dit apparaat niet worden gebruikt om toegang tot bedrijfsbronnen te krijgen.

## <a name="how-non-compliant-settings-work-with-conditional-access-policies"></a>De werking van niet-compatibele instellingen met beleid voor voorwaardelijke toegang?

In de onderstaande tabel wordt beschreven hoe niet-compatibele instellingen worden beheerd wanneer een nalevingsbeleid wordt gebruikt in combinatie met beleid voor voorwaardelijke toegang.

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

**Hersteld** = het besturingssysteem van het apparaat dwingt naleving af. (De gebruiker moet bijvoorbeeld een pincode instellen.)+

**In quarantaine** = het besturingssysteem van het apparaat dwingt geen naleving af. (Bij Android-apparaten bijvoorbeeld wordt de gebruiker niet gedwongen het apparaat te versleutelen.) Als het apparaat niet compatibel is, worden de volgende acties uitgevoerd:+

- Het apparaat wordt geblokkeerd als een beleid voor voorwaardelijke toegang van toepassing is voor de gebruiker.
- De bedrijfsportal stelt de gebruiker op de hoogte van eventuele nalevingsproblemen.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
