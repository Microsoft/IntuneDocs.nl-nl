---
title: UI-updates voor Intune-apps voor eindgebruikers | Microsoft Docs
description: Ontdek wat is gewijzigd in de gebruikersinterface voor apps op eindgebruikersapparaten met Intune.
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 629a091c1016186700a95bf76b9feed9ef0adb79
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---
# <a name="ui-updates-for-intune-end-user-apps"></a>UI-updates voor Intune-apps voor eindgebruikers
Lees welke updates we hebben aangebracht in de gebruikersinterface voor apps die uw eindgebruikers zien in deze versie van Microsoft Intune. Dit kan u helpen bij de communicatie met gebruikers en het bijwerken van eventuele aangepaste documentatie die u hebt gemaakt om uw implementatie te ondersteunen. Zo kunt u beter problemen oplossen wanneer ze de helpdesk bellen voor ondersteuning via de bedrijfsportal.

## <a name="coming-soon-in-the-ui"></a>Binnenkort beschikbaar in de gebruikersinterface
Dit zijn de plannen voor manieren waarop we de gebruikerservaring gaan verbeteren door onze gebruikersinterface bij te werken.

> [!Note]
> De onderstaande afbeeldingen zijn voorbeelden en het aangekondigde product kan verschillen van de weergegeven versies.

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Verbeterde aanmeldervaring in de bedrijfsportal-apps voor alle platformen <!--User Story 1132123-->

Dit is de aankondiging van een wijziging die in de komende maanden wordt geïntroduceerd en waarmee de aanmeldervaring wordt verbeterd voor apps in de Intune-bedrijfsportal voor Android, iOS en Windows. De nieuwe gebruikerservaring wordt automatisch toegepast op alle platformen voor de bedrijfsportal-app wanneer deze wijziging wordt doorgevoerd in Azure AD. Bovendien kunnen gebruikers nu zich aanmelden bij de bedrijfsportal vanaf een ander apparaat met een gegenereerde code voor eenmalig gebruik. Dit is vooral nuttig in gevallen wanneer gebruikers zich moeten aanmelden zonder referenties.  

Hieronder ziet u de vorige aanmeldingservaring, de nieuwe aanmeldingservaring met referenties en de nieuwe aanmeldingservaring vanaf een ander apparaat.

__Vorige aanmeldingservaring__

![De aanmeldingspagina van de bedrijfsportal met een pictogram van een persoon voor een grafische weergave van een website. Hieronder staat de knop Aanmelden. Een koppeling onder aan de pagina leidt naar informatie over privacy en cookies van Microsoft.](./media/cp_ios_aad_signin_before_1704_001.png)

![Nadat de gebruiker op Aanmelden heeft getikt, vult de gebruiker de referenties in op deze pagina waarop wordt gevraagd om het e-mailadres en wachtwoord van de gebruiker. Ook worden verschillende manieren gegeven om problemen met wachtwoorden op te lossen.](./media/cp_ios_aad_signin_before_1704_002.png)

![Na het invoeren van het wachtwoord, wordt de gebruiker aangemeld met de bedrijfsportal-app. Hierbij wordt een laadbalk weergegeven.](./media/cp_ios_aad_signin_before_1704_003.png)

__Nieuwe aanmeldingservaring__

![De aanmeldingspagina van de bedrijfsportal met een pictogram van een persoon voor een grafische weergave van een website. Hieronder staat de knop Aanmelden. Een koppeling onder aan de pagina leidt naar informatie over privacy en cookies van Microsoft.](./media/cp_ios_aad_signin_after_1704_001.png)

![De gebruiker wordt gevraagd alleen een e-mailadres in te voeren in plaats van het e-mailadres en wachtwoord op hetzelfde scherm.](./media/cp_ios_aad_signin_after_1704_002.png)

![De gebruiker wordt gevraagd om het wachtwoord nadat het e-mailadres is geaccepteerd.](./media/cp_ios_aad_signin_after_1704_003.png)

![Nadat het verificatieproces is doorlopen, wordt er aangemeld met de bedrijfsportal-app. Hierbij wordt een laadbalk weergegeven.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

__Nieuwe aanmeldingservaring bij aanmelding vanaf een ander apparaat__

![De aanmeldingspagina van de bedrijfsportal met een pictogram van een persoon voor een grafische weergave van een website. Hieronder staat de knop Aanmelden. Een koppeling onder aan de pagina leidt naar informatie over privacy en cookies van Microsoft.](./media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

Tik op de koppeling __Aanmelding vanaf een ander apparaat__.

![U vindt hier instructies om naar de pagina aka.ms/devicelogin te gaan met een unieke wachtwoordcode vanaf uw werkcomputer en de code te gebruiken om u aan te melden.](./media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

Open een browser en ga naar [https://aka.ms/devicelogin](https://aka.ms/devicelogin).

![Een afbeelding van de browser van de gebruiker op de werkcomputer in plaats van de bedrijfsportal-app. Op de weergegeven pagina Apparaataanmelding wordt de gebruiker gevraagd om de code in de bedrijfsportal-app is ontvangen.](./media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

Voer de code die werd weergegeven in de bedrijfsportal-app. Wanneer u __Doorgaan__ selecteert, kunt u zich verifiëren op alle manieren die worden ondersteund door uw bedrijf, zoals een smartcard.

![De gebruiker heeft de unieke code ingevoerd in het veld en op de site Apparaataanmelding is gevraagd om te bevestigen dat de Intune bedrijfsportal-app de juiste app is om autorisatie te ontvangen voor aanmelding.](./media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

![Een bevestigingspagina met de mededeling dat de gebruiker nu is aangemeld bij de bedrijfsportal-app op hun apparaat en dat deze pagina kan worden gesloten.](./media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

De bedrijfsportal-app begint met aanmelden.

![Nadat het verificatieproces is doorlopen, wordt er aangemeld met de bedrijfsportal-app. Hierbij wordt een laadbalk weergegeven.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="april-2017"></a>April 2017

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Nieuwe pictogrammen voor Managed Browser en de bedrijfsportal <!--918433, 918431-->

Zowel de Android- als iOS-versie van de Managed Browser heeft een nieuw pictogram. Het nieuwe pictogram bevat het bijgewerkte Intune-logo om het consistenter te maken met de andere apps in Enterprise Mobility + Security (EM+S).

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune-classic/whats-new/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune-classic/whats-new/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

De pictogrammen voor de Android-, iOS- en Windows-versies van de app in de bedrijfsportal worden ook vernieuwd voor meer consistentie met de andere apps in EM+S. Deze pictogrammen worden in de periode van april tot eind mei geleidelijk in gebruik genomen op de verschillende platforms.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Voortgangsindicator voor aanmelden bij Android-bedrijfsportal <!--953374-->

De Android-bedrijfsportal-app is bijgewerkt met een voortgangsindicator voor het aanmelden wanneer de gebruiker de app opent of hervat. De indicator geeft de verschillende statussen weer, beginnend bij ‘Verbinden...’, gevolgd door ‘Aanmelden...’ en ‘Beveiligingseisen controleren...’, voordat de gebruiker de app kan gebruiken.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune-classic/whats-new/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune-classic/whats-new/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="/intune-classic/whats-new/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Verbeterde app-installatiestatus voor de Windows 10-bedrijfsportal-app <!--676495-->
De Windows 10-bedrijfsportal-app heeft op de app-detailpagina nu een voortgangsbalk voor installatie. Dit wordt ondersteund voor moderne apps op apparaten met Windows 10 Jubileumupdate en hoger.

__Voor__
  ![Een afbeelding van de vorige versie van het laadscherm, waarbij voor de status alleen installeren stond vermeld.](./media/cp_win10_install_status_before_1704.png)

__Na__
  ![Een afbeelding van de bijgewerkte versie van het laadscherm, waarbij nu een voortgangsbalk voor de installatie wordt weergegeven.](./media/cp_win10_install_status_after_1704.png)

## <a name="february-2017"></a>Februari 2017

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622-announced-1702--"></a>Nieuwe gebruikerservaring voor de bedrijfsportal-app voor Android <!--621622, announced 1702-->
Vanaf maart volgt de bedrijfsportal-app voor Android [richtlijnen voor het ontwerpen van materiaal](https://material.io/guidelines/material-design/introduction.html) voor een moderne vormgeving. Deze verbeterde gebruikerservaring omvat het volgende:

* __Kleuren__: tabbladkoppen kunnen worden gekleurd volgens uw aangepaste kleurenpalet.

![De afbeelding links toont de bedrijfsportal-app voor Android vóór de update. De afbeelding rechts toont de bedrijfsportal-app voor Android na de update. In beide afbeeldingen is het tabblad Apparaten geselecteerd uit de drie beschikbare tabbladen Apps, Apparaten en Contact opnemen met IT.](./media/CP_Android_DevicesTab_BeforeAfter.png)

* __Interface__: de knoppen __Aanbevolen apps__ en __Alle apps__ op het tabblad __Apps__ zijn bijgewerkt. De knop __Zoeken__ is nu een zwevende actieknop.

![De afbeelding links toont de bedrijfsportal-app voor Android vóór de update. De afbeelding rechts toont de bedrijfsportal-app voor Android na de update. In beide afbeeldingen is het tabblad Apps geselecteerd uit de drie beschikbare tabbladen Apps, Apparaten en Contact opnemen met IT.](./media/CP_Android_AppsTab_BeforeAfter.png)

* __Navigatie__: Alle apps biedt een tabbladweergave van de opties __Aanbevolen__, __Alle__ en __Categorieën__ om de navigatie te vereenvoudigen. __Contact opnemen met IT__ is gestroomlijnd voor een betere leesbaarheid.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune-classic/whats-new/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a>Januari 2017

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a>De bedrijfsportalwebsite moderniseren <!--753980, announced 1701-->
Te beginnen in februari ondersteunt de bedrijfsportalwebsite apps die zijn gericht op gebruikers die geen beheerde apparaten hebben. De website wordt in overeenstemming gebracht met andere Microsoft-producten en -services met een nieuw contrasterend kleurenschema, dynamische illustraties en een 'hamburgermenu', ![Kleine afbeelding van het hamburgermenu dat nu is toegevoegd in de linkerbovenhoek van de bedrijfsportalwebsite](./media/CP_hamburger_menu.png) dat contactgegevens van de helpdesk bevat, alsmede informatie over bestaande beheerde apparaten. De landingspagina wordt opnieuw ingedeeld om de nadruk te leggen op apps die beschikbaar zijn voor gebruikers, met carrousels voor uitgelichte en recent bijgewerkte apps.

![Aan de linkerkant een afbeelding van de huidige versie van de bedrijfsportal-website met de vorige versie van Apps, mijn apparaten en speciale en categorieënweergaven. Aan de rechterkant een afbeelding van de bijgewerkte versie van de bedrijfsportal-website met een vernieuwde app-carrousel, een lijst met onlangs gepubliceerde apps en bijgewerkte categorieën-weergave.](./media/CP_Website_BeforeAfter_Feb2016.png)


### <a name="see-also"></a>Zie tevens
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap voor cloudplatform](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Wat is nieuw in de Azure-preview?](https://docs.microsoft.com/intune/whats-new)
* [Wat is er nieuw (archief)](whats-new-archive.md)

