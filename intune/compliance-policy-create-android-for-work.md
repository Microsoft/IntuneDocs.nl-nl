---
title: Nalevingsbeleid voor Android for Work maken
titleSuffix: Microsoft Intune
description: Maak een Intune-nalevingsbeleid voor apparaten voor Android for Work-apparaten zodat u kunt opgeven aan welke vereisten een apparaat moet voldoen om te conformeren.
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8ca31d4c83ccc6b786933080b96f66953cf1a108
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-create-a-device-compliance-policy-for-android-for-work-devices-in-intune"></a>Nalevingsbeleid voor Android for Work-apparaten maken in Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Een Intune-apparaatnalevingsbeleid voor Android for Work bepaalt de regels en instellingen waaraan een Android for Work-apparaat moet voldoen om te voldoen aan het beleid. U kunt deze beleidsregels gebruiken met voorwaardelijke toegang om toegang tot bedrijfsbronnen toe te staan of te blokkeren. U kunt ook apparaatrapporten krijgen en acties voor niet-naleving treffen. U maakt nalevingsbeleid voor apparaten voor elk platform in Intune Azure Portal. Zie [Aan de slag met apparaatnaleving](device-compliance-get-started.md) voor informatie over nalevingsbeleid en de vereisten die u moet afhandelen voordat u een nalevingsbeleid maakt.

In de volgende tabel wordt beschreven hoe niet-compatibele instellingen worden beheerd wanneer een nalevingsbeleid wordt gebruikt in combinatie met beleid voor voorwaardelijke toegang.

--------------------------

|**Beleidsinstelling**| **Android for Work** |
| --- | --- |
| **Configuratie van pincode of wachtwoord** |  In quarantaine |
| **Apparaatversleuteling** |  In quarantaine |
| **Opengebroken of geroot apparaat** | In quarantaine (geen instelling) |
| **E-mailprofiel** | Niet van toepassing |
| **Minimale versie van het besturingssysteem** | In quarantaine |
| **Maximale versie van het besturingssysteem** | In quarantaine |
| **Windows Health Attestation** |Niet van toepassing |

**Hersteld** = het besturingssysteem van het apparaat dwingt naleving af. (De gebruiker moet bijvoorbeeld een pincode instellen.)+

**In quarantaine** = het besturingssysteem van het apparaat dwingt geen naleving af. (Bij Android-apparaten bijvoorbeeld wordt de gebruiker niet gedwongen het apparaat te versleutelen.) Als het apparaat niet compatibel is, worden de volgende acties uitgevoerd:

- Het apparaat wordt geblokkeerd als een beleid voor voorwaardelijke toegang van toepassing is voor de gebruiker.
- De bedrijfsportal stelt de gebruiker op de hoogte van eventuele nalevingsproblemen.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Een nalevingsbeleid maken in Azure Portal

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
1. Kies in het deelvenster **Intune** de optie **Apparaatnaleving**. Kies onder **Beheren** de optie **Beleid** en vervolgens **Beleid maken**.
2. Typ een naam, beschrijving en kies het platform waarop u dit beleid wilt toepassen.
3. Kies **Instellingen configureren** om de instellingen **Systeembeveiliging**, **Apparaatstatus** en **Apparaateigenschappen** hier op te geven. Kies **OK** als u klaar bent.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Gebruikersgroepen toewijzen

Als u een nalevingsbeleid aan gebruikers wilt toewijzen, kiest u een beleid dat u hebt geconfigureerd. Bestaande beleidsregels vindt u in het deelvenster **Apparaatnaleving - beleid**.

1. Kies het beleid dat u aan gebruikers wilt toewijzen en kies **Toewijzingen**. Hiermee opent u het deelvenster waar u **Azure Active Directory-beveiligingsgroepen** kunt selecteren en aan het beleid kunt toewijzen.
2. Kies **Geselecteerde groepen** om het deelvenster met de Azure AD-beveiligingsgroepen te openen.  Als u **Opslaan** kiest, wordt het beleid bij gebruikers geïmplementeerd.

U hebt het beleid toegepast op gebruikers.  De apparaten die worden gebruikt door de gebruikers op wie het beleid is toegepast, worden gecontroleerd om te zien of ze voldoen aan het beleid.

<!--- ##  Compliance policy settings--->

## <a name="system-security-settings"></a>Systeembeveiligingsinstellingen

### <a name="password"></a>Wachtwoord

- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten:** stel deze optie in op **Ja** als u gebruikers wilt verplichten een wachtwoord in te voeren om toegang te krijgen tot hun apparaat.
- **Minimale wachtwoordlengte**: hiermee geeft u het minimale aantal cijfers of tekens op waaruit het wachtwoord moet bestaan.
- **Wachtwoordkwaliteit:** met deze instelling wordt gedetecteerd of de vereisten voor het wachtwoord die u opgeeft op het apparaat zijn geconfigureerd. Gebruik deze instelling als u wilt afdwingen dat gebruikers bepaalde wachtwoordvereisten voor Android-apparaten instellen. U kunt kiezen uit:
  - **Lage beveiligingsbiometrie**
  - **Vereist**
  - **Ten minste numeriek**
  - **Ten minste alfabetisch**
  - **Ten minste alfanumeriek**
  - **Alfanumeriek met tekens**
- **Minuten inactief voordat wachtwoord is vereist:** hiermee geeft u op na hoeveel niet-actieve tijd gebruikers hun wachtwoord opnieuw moeten invoeren.
- **Wachtwoord verloopt (in dagen):** selecteer het aantal dagen waarna het wachtwoord van gebruikers verloopt en ze een nieuw wachtwoord moeten maken.
- **Wachtwoordgeschiedenis onthouden**: gebruik deze instelling in combinatie met **Wachtwoorden niet opnieuw gebruiken** om te voorkomen dat gebruikers eerder gebruikte wachtwoorden opnieuw gebruiken.
- **Wachtwoorden niet opnieuw gebruiken:** als **Wachtwoordgeschiedenis onthouden** is geselecteerd, geeft u het aantal eerder gebruikte wachtwoorden op dat niet opnieuw kan worden gebruikt.
- **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status:** deze instelling moet worden gebruikt met de instelling **Minuten van inactiviteit voordat wachtwoord vereist is**. Eindgebruikers wordt gevraagd een wachtwoord op te geven om toegang te krijgen tot een apparaat dat inactief is geweest gedurende de tijd die is opgegeven bij de instelling **Minuten van inactiviteit voordat wachtwoord vereist is**.


### <a name="encryption"></a>Versleuteling

- **Versleuteling vereisen op mobiel apparaat:** u hoeft deze instelling niet te configureren, omdat versleuteling wordt afgedwongen op Android for Work-apparaten.


## <a name="device-health-and-security-settings"></a>Status en beveiligingsinstellingen van apparaat

- **Apparaat mag niet gekraakt of geroot zijn**: als u deze instelling inschakelt, worden apparaten die zijn gekraakt of waarvoor roottoegang is verkregen als niet-compatibel beschouwd.
- **Vereisen dat de installatie van apps van onbekende bronnen worden voorkomen:** u hoeft deze instelling niet te configureren, omdat installatie van onbekende bronnen altijd wordt voorkomen op Android for Work-apparaten.
- **Vereisen dat USB-foutopsporing is uitgeschakeld**: u hoeft deze instelling niet te configureren, omdat USB-foutopsporing altijd al is uitgeschakeld op Android for Work-apparaten.
- **Minimaal niveau voor de Android-beveiligingspatch**: gebruik deze instelling om het minimale Android-patchniveau op te geven. Apparaten die niet ten minste dit patchniveau hebben, worden als niet-compatibel gezien. De datum moet de volgende notatie hebben: dd-mm-jjjj.
- **Vereisen dat Device Threat Protection wordt ingeschakeld**: Gebruik deze instelling om de risicobeoordeling uit de Lookout MTP-oplossing als voorwaarde voor naleving te gebruiken. Selecteer het maximaal toegestane bedreigingsniveau. U kunt daarbij kiezen uit:
  - **Geen (beveiligd)**: Dit is het veiligste niveau. Dit betekent dat er op het apparaat geen bedreigingen mogen staan. Als een van de bedreigingsniveaus voor het apparaat wordt gedetecteerd, wordt het apparaat geëvalueerd als niet-compatibel.
  - **Laag**: Het apparaat wordt als compatibel geëvalueerd als er bedreigingen met een laag niveau op staan. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld**: het apparaat wordt als compatibel geëvalueerd als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als bedreigingen met hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-compatibel beoordeeld.
  - **Hoog**: dit is de minst veilige optie. Het komt erop neer dat alle bedreigingsniveaus worden toegestaan. Dit is mogelijk alleen nuttig als u deze oplossing slechts voor rapportagedoeleinden gebruikt.

## <a name="device-property-settings"></a>Instellingen voor apparaateigenschappen

- **Minimale versie van het besturingssysteem die is vereist**: wanneer een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt het apparaat gerapporteerd als niet-compatibel. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De eindgebruiker kan dan kiezen of hij een upgrade van zijn apparaat wil uitvoeren, waarna hij toegang tot bedrijfsbronnen krijgt.
- **Maximale versie van het besturingssysteem die is toegestaan:** wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die in de regel is opgegeven, wordt de toegang tot bedrijfsresources geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel die de versie van het besturingssysteem toestaat, kan dit apparaat niet worden gebruikt om toegang tot bedrijfsbronnen te krijgen.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
