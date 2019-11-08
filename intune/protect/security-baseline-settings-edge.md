---
title: Instellingen voor beveiliging van intune-basis lijnen voor micro soft Edge
titleSuffix: Microsoft Intune
description: Instellingen voor de beveiligings basislijn die worden ondersteund door intune voor het beheren van micro soft Edge-browser
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/30/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8f4e56340d871ea5e0bcec7e541a418c32d021d0
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/01/2019
ms.locfileid: "73415643"
---
# <a name="microsoft-edge-baseline-settings-for-intune"></a>Micro soft Edge-basislijn instellingen voor intune

Bekijk de basis instellingen van de micro soft Edge-webbrowser die door Microsoft Intune worden ondersteund. De standaard waarden van de micro soft Edge-basis lijn vertegenwoordigen de aanbevolen configuratie voor micro soft Edge-browsers en komen mogelijk niet overeen met de standaard waarden voor de basis lijn voor andere beveiligings basislijnen

> [!NOTE]
> De basis lijn van micro soft Edge bevindt zich in de open bare preview. 

## <a name="microsoft-edge"></a>Microsoft Edge

- **Vragen om micro soft Defender SmartScreen-prompts voor sites voor komen**  
  **Standaardinstelling**: ingeschakeld  
  Micro soft Edge CSP: [browser-PreventSmartScreenPromptOverride](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverride)

  Met deze beleids instelling kunt u bepalen of gebruikers de waarschuwingen van micro soft Defender SmartScreen over mogelijk schadelijke websites kunnen negeren. 
  - Als u deze instelling inschakelt, kunnen gebruikers de waarschuwingen van micro soft Defender SmartScreen negeren en kunnen ze niet door gaan naar de site. 
  - Als u deze instelling uitschakelt of niet configureert, kunnen gebruikers de waarschuwingen van micro soft Defender SmartScreen negeren en door gaan naar de site.

- **De minimale SSL-versie is ingeschakeld**  
  **Standaardinstelling**: ingeschakeld  

  Stel een mini maal ondersteunde versie van SSL in. Als u dit beleid instelt op *niet geconfigureerd*, gebruikt micro soft Edge een standaard minimum versie van *TLS 1,0*. Als u deze optie instelt op *ingeschakeld*, kunt u een minimum versie selecteren uit de volgende waarden:

  - TLS 1.0
  - TLS 1.1
  - TLS 1.2

  - **De minimale SSL-versie is ingeschakeld**  
    **Standaard**: TLS 1,2

- **Negeren van waarschuwingen van micro soft Defender SmartScreen over down loads voor komen**  
  **Standaardinstelling**: ingeschakeld  
  Micro soft Edge CSP: [browser-PreventSmartScreenPromptOverrideForFiles](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventsmartscreenpromptoverrideforfiles)  

  Met dit beleid kunt u bepalen of gebruikers micro soft Defender SmartScreen-waarschuwingen over niet-geverifieerde down loads kunnen negeren.
  - Als u dit beleid inschakelt, kunnen gebruikers in uw organisatie micro soft Defender SmartScreen-waarschuwingen niet negeren en kunnen ze de niet-geverifieerde down loads niet volt ooien.
  - Als u dit beleid uitschakelt of niet configureert, kunnen gebruikers waarschuwingen van micro soft Defender SmartScreen negeren en niet-geverifieerde down loads volt ooien.

- **Gebruikers toestaan om door te gaan vanaf de pagina SSL-waarschuwing**  
  **Standaardinstelling**: uitgeschakeld  
  Micro soft Edge CSP: [browser-PreventCertErrorOverrides](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-preventcerterroroverrides)  

  Micro soft Edge toont een waarschuwings pagina wanneer gebruikers sites met SSL-fouten bezoeken. Als u dit beleid instelt op *ingeschakeld* of *niet geconfigureerd*, kunnen gebruikers door deze waarschuwings pagina's klikken. Wanneer dit beleid is *uitgeschakeld*, worden gebruikers geblokkeerd door een waarschuwings pagina te klikken. 

- **Standaard instelling voor Adobe Flash**  
  **Standaardinstelling**: ingeschakeld  
  Micro soft Edge CSP: [browser-AllowFlash](https://docs.microsoft.coms/windows/client-management/mdm/policy-csp-browser#browser-allowflash)en [browser-AllowFlashClickToRun](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowflashclicktorun)  

  Hiermee wordt bepaald of websites die niet worden gedekt door ' PluginsAllowedForUrls ' of ' PluginsBlockedForUrls ', automatisch de Adobe Flash-invoeg toepassing kunnen uitvoeren. 

  - Selecteer ' BlockPlugins ' om Adobe Flash op alle sites te blok keren
  - Selecteer ' ClickToPlay ' om Adobe Flash uit te voeren, maar de gebruiker moet op de tijdelijke aanduiding klikken om deze te starten.
  
   In elk geval hebben de beleids regels ' PluginsAllowedForUrls ' en ' PluginsBlockedForUrls ' prioriteit boven ' DefaultPluginsSetting '. Automatisch afspelen is alleen toegestaan voor domeinen die expliciet worden vermeld in het beleid ' PluginsAllowedForUrls '. 
   Als u automatisch afspelen voor alle sites wilt inschakelen, kunt u http://* en https://* toevoegen aan deze lijst. 
   
   - Als u dit beleid instelt op *niet geconfigureerd*, kan de gebruiker deze instelling hand matig wijzigen. * 2 = de Adobe Flash-invoeg toepassing blok keren * 3 = Klik om de eerste ' 1 ' optieset toestaan toe te spelen, maar deze functie wordt nu alleen verwerkt door het beleid ' PluginsAllowedForUrls '. Bestaande beleids regels die ' 1 ' gebruiken, worden in de klik-en-Play-modus uitgevoerd.  
 
  - **Standaard instelling voor Adobe Flash**  
    **Standaard**: de Adobe Flash-invoeg toepassing blok keren

- **Site-isolatie inschakelen voor elke site**  
  **Standaardinstelling**: ingeschakeld  

  Het beleid ' SitePerProcess ' kan worden gebruikt om te voor komen dat gebruikers het standaard gedrag van het isoleren van alle sites. U kunt ook het IsolateOrigins-beleid gebruiken om aanvullende, nauw keurige oorsprongen te isoleren.

  - Wanneer dit beleid is ingesteld op *ingeschakeld*, kunnen gebruikers niet deel nemen aan het standaard gedrag waarbij elke site wordt uitgevoerd in een eigen proces. 
  - Als u *uitgeschakeld* of *niet geconfigureerd*gebruikt, kan een gebruiker de site isolatie afmelden. (Bijvoorbeeld door het gebruik van de vermelding site-isolatie uitschakelen in edge://flags.) Als u het beleid uitschakelt of het beleid niet configureert, wordt de site isolatie uitgeschakeld.

- **Ondersteunde verificatie schema's**  
  **Standaardinstelling**: ingeschakeld  

  Hiermee geeft u op welke HTTP-verificatie schema's worden ondersteund. U kunt het beleid configureren met behulp van de volgende waarden: ' Basic ', ' Digest ', ' NTLM ' en ' Negotiate '. Scheid meerdere waarden met komma's. Als u dit beleid niet configureert, worden alle vier de schema's gebruikt.
 
  - **Ondersteunde verificatie schema's**  
    Maak een keuze uit de volgende opties: 
    - Eenvoudig
    - Samenvatting
    - NLTM *(standaard geselecteerd)*
    - Onderhandelen *(standaard geselecteerd)*

- **Opslaan van wacht woorden in wachtwoord beheer inschakelen**  
  **Standaardinstelling**: uitgeschakeld  
  Micro soft Edge CSP: [browser-AllowPasswordManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowpasswordmanager)  

  Schakel micro soft Edge in om gebruikers wachtwoorden op te slaan. 
  - Als u dit beleid inschakelt, kunnen gebruikers hun wacht woord opslaan in micro soft Edge. De volgende keer dat ze de site bezoeken, wordt het wacht woord automatisch door micro soft Edge ingevoerd. 
  - Als u dit beleid uitschakelt, kunnen gebruikers geen nieuwe wacht woorden opslaan, maar wel eerder opgeslagen wacht woorden gebruiken. 
  
  Wanneer u dit beleid instelt op *ingeschakeld* of *uitgeschakeld*, kunnen gebruikers dit beleid niet wijzigen of negeren in micro soft Edge. 
  
  Als u deze optie instelt op *niet geconfigureerd*, kunnen gebruikers wacht woorden opslaan en deze functie uitschakelen.

- **Bepalen welke extensies niet kunnen worden geïnstalleerd**  
  **Standaardinstelling**: ingeschakeld  

  Geef een lijst van de specifieke uitbrei dingen die gebruikers niet in micro soft Edge kunnen installeren. Wanneer u dit beleid implementeert, worden alle uitbrei dingen in deze lijst die eerder zijn geïnstalleerd, uitgeschakeld en kan de gebruiker deze niet inschakelen. Als u een item uit de lijst met geblokkeerde uitbrei dingen verwijdert, wordt deze extensie automatisch opnieuw ingeschakeld wanneer deze eerder is geïnstalleerd.
  
  Gebruik **\*** om alle uitbrei dingen te blok keren die niet expliciet worden vermeld in de acceptatie lijst. Als dit beleid is ingesteld op *niet geconfigureerd*, kunnen gebruikers een wille keurige uitbrei ding installeren in micro soft Edge. 
  
  Voorbeeld waarde: extension_id1 extension_id2.  
  <br>
  - **Extensie-Id's de gebruiker mag niet worden geïnstalleerd (of * voor alle)**  
    Selecteer Extra extensies **toevoegen** en opgeven. **\*** is standaard geselecteerd.

- **Micro soft Defender SmartScreen configureren**  
  **Standaardinstelling**: ingeschakeld  
  Micro soft Edge CSP: [browser-AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen)  
  
  Met deze beleids instelling kunt u configureren of micro soft Defender SmartScreen moet worden ingeschakeld. Micro soft Defender SmartScreen biedt waarschuwings berichten om uw gebruikers te beschermen tegen mogelijke phishing-prak tijken en schadelijke software. 
  
  - Micro soft Defender SmartScreen is standaard ingeschakeld. Als u deze instelling inschakelt, is micro soft Defender SmartScreen ingeschakeld en kunnen gebruikers het niet uitschakelen.
  - Als u deze instelling uitschakelt, wordt micro soft Defender SmartScreen uitgeschakeld en kunnen gebruikers deze niet inschakelen. 
  - Wanneer deze optie is ingesteld op *niet geconfigureerd*, kunnen gebruikers kiezen of ze micro soft Defender SmartScreen willen gebruiken. 
  
  Dit beleid is alleen beschikbaar voor Windows-exemplaren die zijn toegevoegd aan een micro soft Active Director-domein of op Windows 10 Pro-of ENTER prise-instanties die zijn geregistreerd voor Apparaatbeheer.

- **Hosts voor systeem eigen e-mail op gebruikers niveau toestaan (geïnstalleerd zonder beheerders machtigingen)**  
  **Standaardinstelling**: uitgeschakeld  

  Hiermee wordt installatie op gebruikers niveau van systeem eigen Messa ging-hosts ingeschakeld. 
  - Als u dit beleid uitschakelt, gebruikt micro soft Edge alleen native Messa ging-hosts die op het systeem niveau zijn geïnstalleerd. Als u dit beleid niet configureert, kan micro soft Edge standaard het gebruik van native Messa ging-hosts op gebruikers niveau toestaan.

## <a name="next-steps"></a>Volgende stappen

[Beveiligings basislijnen gebruiken in intune](security-baselines.md)
