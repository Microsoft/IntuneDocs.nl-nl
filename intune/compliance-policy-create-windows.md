---
title: Een Windows-nalevingsbeleid voor apparaten maken in Microsoft Intune - Azure | Microsoft Docs
description: Maak een Microsoft Intune-nalevingsbeleid voor apparaten voor Windows-apparaten zodat u kunt opgeven aan welke vereisten een apparaat moet voldoen om te conformeren.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 211b3c94dd7172d1755e3c12bb4d90dbcf28750d
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="how-to-create-a-device-compliance-policy-for-windows-devices-in-intune"></a>Een apparaatnalevingsbeleid maken voor Windows-apparaten in Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Een Intune-apparaatnalevingsbeleid voor Windows bepaalt de regels en instellingen waaraan een Windows-apparaat moet voldoen om te voldoen aan het beleid. U kunt deze beleidsregels gebruiken met voorwaardelijke toegang om toegang tot bedrijfsbronnen toe te staan of te blokkeren. U kunt ook apparaatrapporten krijgen en acties voor niet-naleving treffen. U maakt nalevingsbeleid voor apparaten voor elk platform in Intune Azure Portal. Zie [Aan de slag met apparaatnaleving](device-compliance-get-started.md) voor informatie over nalevingsbeleid en de vereisten die u moet afhandelen voordat u een nalevingsbeleid maakt.

In de volgende tabel wordt beschreven hoe niet-compatibele instellingen worden beheerd wanneer een nalevingsbeleid wordt gebruikt in combinatie met beleid voor voorwaardelijke toegang.

---------------------------

| **Beleidsinstelling** | **Windows 8.1 en hoger** | **Windows Phone 8.1 en hoger** |
|----| ----| --- |
| **Configuratie van pincode of wachtwoord** | Hersteld | Hersteld |   
| **Apparaatversleuteling** | Niet van toepassing | Hersteld |   
| **Opengebroken of geroot apparaat** | Niet van toepassing | Niet van toepassing |  
| **E-mailprofiel** | Niet van toepassing | Niet van toepassing |   
| **Minimale versie van het besturingssysteem** | In quarantaine | In quarantaine |   
| **Maximale versie van het besturingssysteem** | In quarantaine | In quarantaine |   
| **Windows Health Attestation** | In quarantaine: Windows 10 en Windows 10 Mobile|Niet van toepassing: Windows 8.1 |

-------------------------------

**Hersteld** = het besturingssysteem van het apparaat dwingt naleving af. (De gebruiker wordt bijvoorbeeld gedwongen een pincode in te stellen.)

**In quarantaine** = het besturingssysteem van het apparaat dwingt geen naleving af. (Bij Android-apparaten bijvoorbeeld wordt de gebruiker niet gedwongen het apparaat te versleutelen.) Als het apparaat niet compatibel is, worden de volgende acties uitgevoerd:

- Het apparaat wordt geblokkeerd als een beleid voor voorwaardelijke toegang van toepassing is voor de gebruiker.
- De bedrijfsportal stelt de gebruiker op de hoogte van eventuele nalevingsproblemen.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Een nalevingsbeleid maken in Azure Portal

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
1. Kies in het deelvenster **Intune** de optie **Apparaatnaleving**. Kies onder **Beheren** de optie **Beleid** en vervolgens **Beleid maken**.
2. Typ een naam, beschrijving en kies het platform waarop u dit beleid wilt toepassen.
3. Kies **Instellingen configuren** om de instellingen **Systeembeveiliging**, **Apparaatstatus** en **Apparaateigenschappen** hier op te geven. Kies **OK** als u klaar bent.

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

U hebt het beleid toegepast op gebruikers. De apparaten die worden gebruikt door de gebruikers op wie het beleid is toegepast, worden gecontroleerd om te zien of ze voldoen aan het beleid.

<!---## Compliance policy settings--->

## <a name="system-security-settings"></a>Systeembeveiligingsinstellingen

### <a name="password"></a>Wachtwoord

- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten:** stel deze optie in op **Ja** als u gebruikers wilt verplichten een wachtwoord in te voeren om toegang te krijgen tot hun apparaat.
- **Eenvoudige wachtwoorden toestaan:** stel deze optie in op **Ja** zodat gebruikers eenvoudige wachtwoorden kunnen maken, zoals '**1234**' of '**1111**'.
- **Minimale wachtwoordlengte**: hiermee geeft u het minimale aantal cijfers of tekens aan waaruit het wachtwoord van de gebruiker moet bestaan.
- **Vereist wachtwoordtype:** geef aan of gebruikers een **alfanumeriek** of een **numeriek** wachtwoord moeten maken.

Bij Windows-apparaten die met een Microsoft-account toegankelijk zijn, kan het nalevingsbeleid geen goede controle uitvoeren als de minimale wachtwoordlengte langer is dan acht tekens of als het minimale aantal tekensets meer is dan twee.

- **Minimum aantal tekensets:** als **Vereist wachtwoordtype** is ingesteld op **Alfanumeriek**, wordt met deze instelling het minimum aantal tekensets opgegeven waaruit het wachtwoord moet bestaan. De vier tekensets zijn:
  - Kleine letters
  - Hoofdletters
  - Symbolen
  - Getallen

Hoe hoger de waarde is die u instelt, hoe complexer de gebruikers hun wachtwoorden moeten maken. Bij Windows-apparaten die met een Microsoft-account toegankelijk zijn, kan het nalevingsbeleid geen goede controle uitvoeren als de minimale wachtwoordlengte langer is dan acht tekens of als het minimale aantal tekensets meer is dan twee.

- **Minuten inactief voordat wachtwoord is vereist:** hiermee geeft u op na hoeveel niet-actieve tijd gebruikers hun wachtwoord opnieuw moeten invoeren.
- **Wachtwoord verloopt (in dagen)**: selecteer het aantal dagen waarna het wachtwoord van gebruikers verloopt en ze een nieuw wachtwoord moeten maken.
- **Wachtwoordgeschiedenis onthouden:** gebruik deze instelling in combinatie met **Wachtwoorden niet opnieuw gebruiken** om te voorkomen dat gebruikers eerder gebruikte wachtwoorden opnieuw gebruiken.
- **Wachtwoorden niet opnieuw gebruiken:** als **Wachtwoordgeschiedenis onthouden** is geselecteerd, geeft u het aantal eerder gebruikte wachtwoorden op dat niet opnieuw kan worden gebruikt.
- **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status:** deze instelling moet worden gebruikt samen met de instelling **Minuten van inactiviteit voordat wachtwoord vereist is**. Eindgebruikers wordt gevraagd een wachtwoord op te geven om toegang te krijgen tot een apparaat dat langer inactief is geweest dan de tijd die is opgegeven bij de instelling **Minuten van inactiviteit voordat wachtwoord vereist is**.

**Deze instelling geldt alleen voor Windows 10 Mobile-apparaten.**

### <a name="encryption"></a>Versleuteling

- **Versleuteling vereisen op een mobiel apparaat:** stel deze optie in op **Ja** als u wilt dat apparaten moeten worden versleuteld om verbinding te maken met resources.



## <a name="device-health-settings"></a>Instellingen voor de status van het apparaat

- **Vereisen dat apparaten worden gerapporteerd als goed:** u kunt een regel instellen om te vereisen dat **Windows 10 Mobile** apparaten als goed rapporteert bij nieuw of bestaand nalevingsbeleid. Als deze instelling is ingeschakeld, worden Windows 10-apparaten via de Health Attestation-service (HAS) op de volgende gegevenspunten geëvalueerd:
  - **BitLocker is ingeschakeld:** wanneer BitLocker is ingeschakeld, kan het apparaat gegevens die zijn opgeslagen op de schijf, beschermen tegen onbevoegde toegang wanneer het systeem wordt uitgeschakeld of naar de slaapstand overschakelt. Windows BitLocker-stationsversleuteling versleutelt alle gegevens die zijn opgeslagen op het volume met het Windows-besturingssysteem. BitLocker gebruikt de TPM om het Windows-besturingssysteem en de gebruikersgegevens te beschermen en ervoor te zorgen dat een computer niet kan worden gemanipuleerd, zelfs niet als deze onbeheerd, verloren of gestolen is. Als de computer is uitgerust met een compatibele TPM, gebruikt BitLocker de TPM om de versleutelingssleutels te vergrendelen die de gegevens beschermen. Als gevolg hiervan kunnen de sleutels niet worden gebruikt tot de TPM de status van de computer heeft gecontroleerd
  - **Code-integriteitsbeleidsbestand is ingeschakeld:** code-integriteit is een functie die voortdurend de integriteit valideert van een stuurprogramma- of systeembestand wanneer dat bestand in het geheugen wordt geladen. Code-integriteit detecteert of een niet-ondertekend stuurprogramma- of systeembestand in de kernel wordt geladen, of dat een systeembestand is gewijzigd door schadelijke software die wordt uitgevoerd door een gebruikersaccount met beheerdersbevoegdheden.
  - **Beveiligd opstarten is ingeschakeld:** als beveiligd opstarten is ingeschakeld, wordt het systeem gedwongen om in een vertrouwde fabrieksstatus op te starten. Als beveiligd opstarten is ingeschakeld, moeten de belangrijkste onderdelen van de computer de juiste cryptografische handtekeningen hebben die worden vertrouwd door de organisatie die het apparaat heeft gemaakt. De UEFI-firmware verifieert dit voordat de computer kan worden opgestart. Als er bestanden zijn gemanipuleerd, waardoor de handtekening ongeldig is geworden, kan het systeem niet worden opgestart.

Zie [Health Attestation CSP](https://msdn.microsoft.com/library/dn934876.aspx) voor meer informatie over de werking van de HAS-service.

## <a name="device-property-settings"></a>Instellingen voor apparaateigenschappen

- **Minimale versie van het besturingssysteem die is vereist:** wanneer een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem wordt dit apparaat gerapporteerd als niet-compatibel. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De eindgebruiker kan dan kiezen of hij een upgrade van zijn apparaat wil uitvoeren, waarna hij toegang tot bedrijfsbronnen krijgt.
- **Maximale versie van het besturingssysteem die is toegestaan:** wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die in de regel is opgegeven, wordt de toegang tot bedrijfsresources geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel die de versie van het besturingssysteem toestaat, kan dit apparaat niet worden gebruikt om toegang tot bedrijfsbronnen te krijgen.

<!---## Compliance policy settings for Windows PCs--->

## <a name="system-security-settings"></a>Systeembeveiligingsinstellingen

### <a name="password"></a>Wachtwoord

- **Minimale wachtwoordlengte:** ondersteund op Windows 8.1.

Hiermee geeft u het minimale aantal cijfers of tekens op waaruit het wachtwoord van de gebruiker moet bestaan.

Voor apparaten die zijn beveiligd met een Microsoft-account, kunnen met het nalevingsbeleid geen goede controles worden uitgevoerd als **Minimale wachtwoordlengte** meer dan acht tekens is of als **Minimum aantal tekensets** meer dan twee tekens is.

- **Vereist wachtwoordtype**: wordt ondersteund op Windows RT, Windows RT 8.1 en Windows 8.1.

Hiermee geeft u aan of gebruikers een **alfanumeriek** of een **numeriek** wachtwoord moeten maken.

- **Minimum aantal tekensets**: wordt ondersteund op Windows RT, Windows RT 8.1 en Windows 8.1. Als **Vereist wachtwoordtype** is ingesteld op **Alfanumeriek**, wordt hier het minimale aantal tekensets opgegeven waaruit het wachtwoord moet bestaan. De vier tekensets zijn:
  - Kleine letters
  - Hoofdletters
  - Symbolen
  - Nummers: hoe hoger de waarde is die u instelt, hoe complexer gebruikers hun wachtwoorden moeten maken.

Voor apparaten die zijn beveiligd met een Microsoft-account, kunnen met het nalevingsbeleid geen goede controles worden uitgevoerd als **Minimale wachtwoordlengte** meer dan acht tekens is of als **Minimum aantal tekensets** meer dan twee tekens is.

- **Minuten van inactiviteit voordat wachtwoord vereist is:** wordt ondersteund op Windows RT, Windows RT 8.1 en Windows 8.1

Hiermee geeft u aan na hoeveel niet-actieve tijd gebruikers hun wachtwoord opnieuw moeten invoeren.

- **Wachtwoord verloopt (dagen)**: wordt ondersteund op Windows RT, Windows RT 8.1 en Windows 8.1.

Selecteer het aantal dagen waarna het wachtwoord van gebruikers verloopt en ze een nieuw wachtwoord moeten maken.

- **Wachtwoordgeschiedenis onthouden:** wordt ondersteund op Windows RT, Windows RT en Windows 8.1.

Gebruik deze instelling in combinatie met **Wachtwoorden niet opnieuw gebruiken** om te voorkomen dat gebruikers eerder gebruikte wachtwoorden opnieuw gebruiken.

- **Wachtwoorden niet opnieuw gebruiken:** wordt ondersteund op Windows RT, Windows RT 8.1 en Windows 8.1

Als **Wachtwoordgeschiedenis onthouden:** is geselecteerd, geeft u aan hoeveel eerder gebruikte wachtwoorden er niet opnieuw kunnen worden gebruikt.


## <a name="device-health-settings"></a>Instellingen voor de status van het apparaat

- **Vereisen dat apparaten worden gerapporteerd als goed:** wordt ondersteund op Windows 10-apparaten. U kunt een regel instellen die vereist dat Windows 10-apparaten in nieuw of bestaand nalevingsbeleid als goed moeten worden gerapporteerd. Als deze instelling is ingeschakeld, worden Windows 10-apparaten via de Health Attestation-service (HAS) op de volgende gegevenspunten geëvalueerd:
  - **BitLocker is ingeschakeld:** wanneer BitLocker is ingeschakeld, kan het apparaat gegevens die zijn opgeslagen op de schijf, beschermen tegen onbevoegde toegang wanneer het systeem wordt uitgeschakeld of naar de slaapstand overschakelt. Windows BitLocker-stationsversleuteling versleutelt alle gegevens die zijn opgeslagen op het volume met het Windows-besturingssysteem. BitLocker gebruikt de TPM om het Windows-besturingssysteem en de gebruikersgegevens te beschermen en ervoor te zorgen dat een computer niet kan worden gemanipuleerd, zelfs niet als deze onbeheerd, verloren of gestolen is. Als de computer is uitgerust met een compatibele TPM, gebruikt BitLocker de TPM om de versleutelingssleutels te vergrendelen die de gegevens beschermen. Als gevolg hiervan kunnen de sleutels niet worden gebruikt tot de TPM de status van de computer heeft gecontroleerd
  - **Code-integriteitsbeleidsbestand is ingeschakeld:** code-integriteit is een functie die voortdurend de integriteit valideert van een stuurprogramma- of systeembestand wanneer dat bestand in het geheugen wordt geladen. Code-integriteit detecteert of een niet-ondertekend stuurprogramma- of systeembestand in de kernel wordt geladen, of dat een systeembestand is gewijzigd door schadelijke software die wordt uitgevoerd door een gebruikersaccount met beheerdersbevoegdheden.
  - **Beveiligd opstarten is ingeschakeld:** als beveiligd opstarten is ingeschakeld, wordt het systeem gedwongen om in een vertrouwde fabrieksstatus op te starten. Als beveiligd opstarten is ingeschakeld, moeten de belangrijkste onderdelen van de computer de juiste cryptografische handtekeningen hebben die worden vertrouwd door de organisatie die het apparaat heeft gemaakt. De UEFI-firmware verifieert dit voordat de computer kan worden opgestart. Als er bestanden zijn gemanipuleerd, waardoor de handtekening ongeldig is geworden, kan het systeem niet worden opgestart.
  - **Early Launch Antimalware is ingeschakeld:** Early Launch Anti-Malware (ELAM) biedt de computers in uw netwerk bescherming wanneer ze worden opgestart en wanneer stuurprogramma’s van derden worden geïnitialiseerd.

Zie [Health Attestation CSP](https://msdn.microsoft.com/library/dn934876.aspx) voor meer informatie over de werking van de HAS-service.

## <a name="device-property-settings"></a>Instellingen voor apparaateigenschappen

- **Minimale versie van het besturingssysteem die is vereist:** wordt ondersteund op Windows 8.1 en Windows 10.

Geef hier het nummer van de major.minor.build.CU op. Het versienummer moet overeenkomen met de versie die wordt geretourneerd door de opdracht ```winver```.

Wanneer een apparaat een eerdere versie heeft dan de opgegeven versie van het besturingssysteem, wordt de versie als niet-compatibel gerapporteerd. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De eindgebruiker kan dan kiezen of hij een upgrade van zijn apparaat wil uitvoeren, waarna hij toegang tot bedrijfsbronnen krijgt.

- **Maximale versie van het besturingssysteem die is toegestaan:** wordt ondersteund op Windows 8.1 en Windows 10.

Wanneer een apparaat een versie van het besturingssysteem gebruikt dat hoger is dan wat in de regel is bepaald, wordt de toegang tot bedrijfsbronnen geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met zijn IT-beheerder. Tot er een wijziging is doorgevoerd in de regel die de versie van het besturingssysteem toestaat, kan dit apparaat niet worden gebruikt om toegang tot bedrijfsbronnen te krijgen.

Als u de versie van het besturingssysteem wilt vinden die u voor de instellingen **Minimale versie van het besturingssysteem die is vereist** en **Maximale versie van het besturingssysteem dat is toegestaan** wilt gebruiken, voert u via de opdrachtregel de opdracht **winver** uit. De opdracht winver retourneert de gemelde versie van het besturingssysteem.

- Windows 8.1-pc's retourneren versie **3**. Als de besturingssysteemversieregel is ingesteld op Windows 8.1 voor Windows, wordt het apparaat als in strijd met het nalevingsbeleid gerapporteerd, zelfs als het apparaat Windows 8.1 heeft.
- Voor Windows 10-computers moet de versie worden ingesteld op 10.0, gevolgd door het build-nummer van het besturingssysteem dat wordt geretourneerd door de opdracht winver.

## <a name="windows-holographic-for-business-support"></a>Ondersteuning voor Windows Holographic for Business

De volgende instelling wordt in Windows Holographic for Business ondersteund:

- Systeembeveiliging/versleuteling

  **Versleuteling van gegevensopslag  op apparaat**.

Zie [Verify device encryption](https://docs.microsoft.com/hololens/hololens-encryption#verify-device-encryption) (Apparaatversleuteling controleren) om apparaatversleuteling te controleren op de Microsoft HoloLens.

## <a name="next-steps"></a>Volgende stappen

Zie het volgende onderwerp voor meer informatie over het bewaken van de apparaatcompatibiliteit:

- [Apparaatcompatibiliteit bewaken](device-compliance-monitor.md)
