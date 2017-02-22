---
title: Een nalevingsbeleid maken voor iOS | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp vindt u informatie over het maken van een nalevingsbeleid voor iOS-apparaten.'
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7693d49e2f0fa6e4aa40b6bb71433a7eaab8dd15
ms.openlocfilehash: 334b22bedd0d08bb2294984b2ce5255029857700


---

# <a name="how-to-create-a-device-compliance-policy-for-ios-devices-in-intune-azure-preview"></a>Een apparaatnalevingsbeleid maken voor iOS-apparaten in Intune Azure Preview


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Voor elk platform wordt een nalevingsbeleid gemaakt.  U kunt een nalevingsbeleid maken in Azure Portal. Zie het onderwerp [What is device compliance?](what-is-device-compliance.md) (Wat is apparaatnaleving?) voor meer informatie over een nalevingsbeleid. Zie [Get started with device compliance](get-started-with-device-compliance.md) (Aan de slag met apparaatnaleving) voor informatie over de vereisten die moet uitvoeren voordat u een nalevingsbeleid gaat maken.

In de onderstaande tabel wordt beschreven hoe niet-compatibele instellingen worden beheerd wanneer een nalevingsbeleid wordt gebruikt in combinatie met beleid voor voorwaardelijke toegang.

-------------------------------


| **Beleidsinstelling** | **iOS 8.0 en hoger** |
| --- | --- |
| **Configuratie van pincode of wachtwoord** | Hersteld |   
| **Apparaatversleuteling** | Hersteld (door een pincode in te stellen) |
| **Opengebroken of geroot apparaat** | In quarantaine (geen instelling)
| **E-mailprofiel** | In quarantaine |
|**Minimale versie van het besturingssysteem** | In quarantaine |
| **Maximale versie van het besturingssysteem** | In quarantaine |  
| **Windows Health Attestation** | Niet van toepassing |  
----------------------------


**Hersteld** = het besturingssysteem van het apparaat dwingt naleving af. (De gebruiker wordt bijvoorbeeld gedwongen een pincode in te stellen.)

**In quarantaine** = het besturingssysteem van het apparaat dwingt geen naleving af. (Bij Android-apparaten bijvoorbeeld wordt de gebruiker niet gedwongen het apparaat te versleutelen.) Als het apparaat niet compatibel is, worden de volgende acties uitgevoerd:

- Het apparaat wordt geblokkeerd als een beleid voor voorwaardelijke toegang van toepassing is voor de gebruiker.
- De bedrijfsportal stelt de gebruiker op de hoogte van eventuele nalevingsproblemen.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Een nalevingsbeleid maken in Azure Portal

1. Kies **Apparaatcompatibiliteit instellen** op de blade **Intune**. Kies **Alle apparaatnalevingsbeleidsregels** onder **Beheren** en kies **Maken**.
2. Typ een naam, beschrijving en kies het platform waarop u dit beleid wilt toepassen.
3. Kies **Nalevingsvereisten** om de instellingen voor de **beveiliging**, **apparaatstatus** en **apparaateigenschappen** op te geven. Kies **OK** als u klaar bent.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Gebruikersgroepen toewijzen

Als u een nalevingsbeleid aan gebruikers wilt toewijzen, kiest u een beleid dat u hebt geconfigureerd. Bestaande beleidsregels vindt u op de blade **Naleving - Beleid**.

1. Kies het beleid dat u aan gebruikers wilt toewijzen en kies **Toewijzingen**. Hiermee opent u de blade waar u **Azure Active Directory-beveiligingsgroepen** kunt selecteren en aan het beleid kunt toewijzen.
2. Kies **Groepen selecteren** om de blade met de Azure AD-beveiligingsgroepen te openen.  Als u **Selecteren** kiest, wordt het beleid bij gebruikers geïmplementeerd.

U hebt het beleid toegepast op gebruikers.  De apparaten die worden gebruikt door de gebruikers op wie het beleid is toegepast, worden gecontroleerd om te zien of ze voldoen aan het beleid.

<!---## Compliance policy settings--->

## <a name="system-security-settings"></a>Systeembeveiligingsinstellingen

### <a name="password"></a>Wachtwoord

- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**: stel deze optie in op **Ja** als u wilt aangeven dat gebruikers een wachtwoord moeten invoeren om toegang te krijgen tot hun apparaat. iOS-apparaten die gebruikmaken van een wachtwoord, zijn versleuteld.
- **Eenvoudige wachtwoorden toestaan**: stel deze optie in op **Ja** zodat de gebruiker een eenvoudig wachtwoord kan maken, zoals **1234** of **1111**.
- **Minimale wachtwoordlengte**: hiermee geeft u het minimale aantal cijfers of tekens aan waaruit het wachtwoord moet bestaan.
- **Vereist wachtwoordtype**: geef aan of de gebruiker een **alfanumeriek** of een **numeriek** wachtwoord moet maken.
- **Minimum aantal tekensets**: als u **Vereist wachtwoordtype** instelt op **Alfanumeriek**, gebruikt u deze instelling om het minimum aantal tekensets op te geven dat het wachtwoord moet bevatten. De vier tekensets zijn:
  - Kleine letters
  - Hoofdletters
  - Symbolen
  - Getallen

Als u een hogere waarde instelt, moet de gebruiker een wachtwoord maken dat complexer is.

Voor iOS-apparaten verwijst deze instelling naar het aantal speciale tekens (bijvoorbeeld **!** , **#**, **&amp;**) dat in het wachtwoord moet worden opgenomen.

- **Minuten van inactiviteit voordat wachtwoord vereist is**: hiermee geeft u aan na hoeveel niet-actieve tijd de gebruiker het wachtwoord opnieuw moet invoeren.
- **Wachtwoord verloopt (in dagen)**: selecteer het aantal dagen waarna het wachtwoord verloopt en gebruikers een nieuw wachtwoord moeten maken.
- **Wachtwoordgeschiedenis onthouden**: gebruik deze instelling in combinatie met **Wachtwoorden niet opnieuw gebruiken** om te voorkomen dat gebruikers eerder gebruikte wachtwoorden opnieuw gebruiken.
- **Wachtwoorden niet opnieuw gebruiken**: als u **Wachtwoordgeschiedenis onthouden** hebt geselecteerd, geeft u het aantal eerder gebruikte wachtwoorden op dat niet opnieuw kan worden gebruikt.
- **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status**: gebruik deze instelling samen met de instelling **Minuten van inactiviteit voordat wachtwoord vereist is**. De gebruiker wordt gevraagd een wachtwoord op te geven om toegang te krijgen tot een apparaat dat inactief is geweest gedurende de tijd die is opgegeven bij de instelling **Minuten van inactiviteit voordat wachtwoord vereist is**.

### <a name="email-profile"></a>E-mailprofiel

- **E-mailaccount moet worden beheerd door Intune**: wanneer deze optie is ingesteld op **Ja**, moet het e-mailprofiel worden gebruikt dat is geïmplementeerd op het apparaat. Het apparaat wordt in de volgende situaties beschouwd als niet compatibel:
  - Het e-mailprofiel is geïmplementeerd voor een andere gebruikersgroep dan de gebruikersgroep waarvoor het nalevingsbeleid is bedoeld.
  - De gebruiker heeft al een e-mailaccount op het apparaat ingesteld dat overeenkomt met het Intune-e-mailprofiel dat op het apparaat is geïmplementeerd. Intune kan het door de gebruiker ingerichte profiel niet overschrijven en kan het daarom niet beheren. Om naleving te garanderen, moet de gebruiker de bestaande e-mailinstellingen verwijderen. Daarna kan Intune het beheerde e-mailprofiel installeren.
- **Selecteer het e-mailprofiel dat moet worden beheerd door Intune**: als de instelling **E-mailaccount moet worden beheerd door Intune** is geselecteerd, kiest u **Selecteren** om het e-mailprofiel voor Intune op te geven. Het e-mailprofiel moet aanwezig zijn op het apparaat.

Zie [De toegang tot zakelijke e-mail configureren met e-mailprofielen bij Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) voor meer informatie over e-mailprofielen.

## <a name="device-health-settings"></a>Instellingen voor de status van het apparaat

- **Apparaat mag niet zijn opengebroken of geroot**: als u deze instelling inschakelt, zijn apparaten die zijn opengebroken, niet compatibel.

## <a name="device-properties"></a>Apparaateigenschappen

- **Minimale versie van het besturingssysteem die is vereist**: wanneer een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt dit apparaat gerapporteerd als niet-compatibel. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De gebruiker kan kiezen om het apparaat bij te werken. Daarna zijn de bedrijfsbronnen toegankelijk.
- **Maximale versie van het besturingssysteem die is toegestaan**: wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die in de regel is opgegeven, wordt de toegang tot bedrijfsresources geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel die de versie van het besturingssysteem toestaat, kan dit apparaat niet worden gebruikt om toegang tot bedrijfsbronnen te krijgen.

<!--- ## Next steps

[How to monitor device compliance](monitor-device-compliance.md)--->



<!--HONumber=Feb17_HO1-->


