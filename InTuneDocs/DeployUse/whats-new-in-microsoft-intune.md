---
title: Wat is er nieuw? | Microsoft Intune
description: Ontdek wat er nieuw is in de release van Microsoft Intune van deze maand en in oudere releases
keywords: 
author: Lindavr
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 68af4d7f0b082f14e6f9c06f8739805f9590384e
ms.openlocfilehash: 64bd2e3c8e8da3949634a544eb2c582e889c8209


---

# Wat is er nieuw in Microsoft Intune?
Ontdek wat er nieuw is in deze release van Microsoft Intune. U vindt hier ook informatie over toekomstige wijzigingen waar u rekening mee moet houden én informatie over oudere releases.

Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## Augustus 2016
## Updates voor de bedrijfsportal

### Android
- **Android-bedrijfsportal-app**<br/>
De Intune-bedrijfsportal-app voor Android biedt 'day 0'-ondersteuning voor het toekomstige Android 7.0-besturingssysteem voor mobiele apparaten.  

- **Google verwijdert het op afstand opnieuw instellen van de wachtwoordcode voor Android 7.0-apparaten**<br/>
Op apparaten met Android 7.0 kunnen Intune IT-beheerders en eindgebruikers de wachtwoordcode van het apparaat niet op afstand opnieuw instellen, omdat Google die mogelijkheid voor Android 7.0-apparaten heeft verwijderd. Voor oudere versies van Android kunnen IT-beheerders de wachtwoordcode van een gebruiker nog wel op afstand opnieuw instellen, en kunnen eindgebruikers nog steeds hun wachtwoordcodes opnieuw instellen via de bedrijfsportal-website.

## Juli 2016
## Appbeheer
### De update-ervaring van het inrichtingsprofiel van de app verbeteren
Apple iOS mobiele Line-Of-Business-apps zijn gebouwd met een inrichtingsprofiel en code die is ondertekend met een certificaat. Wanneer de app wordt uitgevoerd op een iOS-apparaat, bevestigt iOS de integriteit van de iOS-app en worden beleidsregels afgedwongen die zijn gedefinieerd door het inrichtingsprofiel.

Het handtekeningcertificaat voor ondernemingen dat u gebruikt om apps te ondertekenen is doorgaans 3 jaar geldig. Het inrichtingsprofiel verloopt echter na één jaar. Met deze update biedt Intune u de hulpmiddelen om proactief een nieuw beleid voor inrichtingsprofielen te implementeren op apparaten met apps die bijna zijn verlopen terwijl het certificaat nog geldig is. Zie voor meer informatie [iOS-beleid voor mobiele inrichtingsprofielen gebruiken om uw Line-Of-Business-apps up-to-date te houden](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->
### Xamarin SDK voor Intune-apps is beschikbaar
Met het onderdeel Intune App SDK Xamarin kunt u de beheerfuncties voor Intune Mobile App inschakelen in mobiele iOS- en Android-apps die zijn gebouwd met Xamarin. U vindt het onderdeel in de [Xamarin Store](https://components.xamarin.com/view/Microsoft.Intune.MAM) of op de [Microsoft Intune Github-pagina](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

## Apparaatbeheer
### Verbeterde limieten voor apparaatinschrijvingen
Intune heeft de maximaal configureerbare limiet voor apparaatinschrijvingen verhoogd van 5 naar 15 apparaten per gebruiker.
<!---TFS 1289896 --->

### TeamViewer-integratie voor Windows-pc's met de Intune-clientsoftware
Dankzij de integratie van [TeamViewer](https://www.teamviewer.com) voor Windows-pc's die worden beheerd met de Intune-client kunt u, ter ondersteuning van uw helpdeskafdeling, sessies voor hulp op afstand met Windows-pc's uitvoeren. Dit is van toepassing op Windows 7, 8, 8.1 en 10. Zie [Algemene beheertaken voor Windows-pc’s met de Microsoft Intune-computerclient voor meer informatie](intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

## Updates voor de bedrijfsportal
### Bedrijfsportalwebsite
- **Verbeterde ervaring voor de eindgebruiker bij het inschrijven van Windows-apparaten**<br/>
Wanneer u voorwaardelijke toegang gebruikt, zijn de stappen voor inschrijving voor Windows 8.1, Windows 10 Desktop en Windows 10 Mobile verbeterd op de bedrijfsportalwebsite. Gebruikers zien nu de afzonderlijke stappen 'Apparaatinschrijving' en 'Workplace Join', waardoor de status van hun apparaat beter zichtbaar is en het proces eenvoudiger kan worden voltooid wanneer er een fout optreedt met Workplace Join (WPJ). De afzonderlijke stappen vereenvoudigen tevens de probleemoplossing voor IT-beheerders. Wanneer eindgebruikers voorheen probeerden in te schrijven en alle inschrijvingsstappen waren geslaagd behalve WPJ, dan werd het ingeschreven apparaat niet weergegeven in de lijst met apparaten voor gebruikers, wat verwarrend was voor gebruikers.

### Android
- **Android-bedrijfsportal-app**<br/>
Als Android-eindgebruikers een foutmelding krijgen dat er een vereist certificaat ontbreekt voor hun apparaat, dan kunnen zij op een knop 'Oplossing' tikken voor [stappen](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) om het ontbrekende certificaat te installeren. Als gebruikers de stappen voltooien, maar er nogmaals een foutmelding over een ontbrekend certificaat wordt weergegeven, dan wordt hen gevraagd contact op te nemen met de IT-beheerder en deze [koppeling](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues) door te geven die de stappen bevat waarmee IT-beheerders het certificaatprobleem kunnen oplossen.

- **Beperken van extern geladen (ofwel 'side-loaded') app-installaties op ingeschreven apparaten**<br/>
Android-apparaten kunnen geen toepassingen meer installeren via de bedrijfsportalwebsite tenzij deze apparaten zijn ingeschreven bij Intune via de Intune-bedrijfsportal-app voor Android.
<!---TFS 1299082--->

### iOS
- **Wijzigingen in de beheeraccounts voor apparaatinschrijving in de iOS-bedrijfsportal-app**<br/>
Om de prestaties en schaalbaarheid te verbeteren, worden in het deelvenster **Mijn apparaten** van de iOS-bedrijfsportal-app niet meer alle Device Enrollment Managers (DEM)-apparaten weergegeven door Intune. Alleen het lokale apparaat waarop de app wordt uitgevoerd, wordt weergegeven en wel alleen als het apparaat is geregistreerd via de bedrijfsportal-app.

    De DEM-gebruiker kan acties op het lokale apparaat uitvoeren, maar extern beheer van andere geregistreerde apparaten kan alleen worden uitgevoerd vanuit de Intune-beheerconsole. Daarnaast is het gebruik in Intune van DEM-accounts met het Apple Device Enrollment Program of het hulpprogramma Apple Configurator beëindigd. Deze twee registratiemethoden bieden al ondersteuning voor gebruikersloze registratie voor gedeelde iOS-apparaten.

    Gebruik alleen DEM-accounts wanneer gebruikersloze registratie voor gedeelde apparaten niet beschikbaar is. Zie voor meer informatie [Apparaten in bedrijfseigendom inschrijven met de apparaatinschrijvingsbeheerder in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

## Wijziging van de namen voor Windows-functies
- [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) is nu bekend als **Windows Hello for Business**.
- [Ondernemingsgegevensbescherming](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) is nu bekend als **Windows Information Protection**.

## Binnenkort
### Intune-groepen stappen over naar Azure Active Directory-groepen met ingang van augustus 2016
Intune is bezig met het creëren van een nieuwe ervaring voor het beheer van groepen die gebruikmaakt van Azure Active Directory (AAD)-beveiligingsgroepen. Deze op Azure AD gebaseerde beveiligingsgroepen kunnen gebruikers en apparaten bevatten en worden gebruikt voor alle groepsbeheer, en voor implementatie van beleid en profielen wanneer wij het nieuwe op Azure gebaseerde Intune-beheerportal introduceren.

Deze nieuwe ervaring zorgt ervoor dat:
- U niet langer groepen hoeft te dupliceren tussen services.
- U toegang hebt tot een aantal nieuwe groepsfuncties van Azure Active Directory Premium (AADP).
- U profiteert van uitbreidbaarheid met behulp van PowerShell en Graph.
- De ervaring voor groepsbeheer uniform wordt voor het gehele beheer van bedrijfsmobiliteit.

Om de overstap naar beveiligingsgroepen mogelijk te maken, wordt de ervaring in de huidige beheerconsole ietwat gewijzigd. Deze wijzigingen, en het gebruik van Azure AD-beveiligingsgroepen, worden beschreven in de Intune-documentatie.

Voor nieuwe Intune-klanten worden bepaalde wijzigingen van beveiligingsgroepen eerder doorgevoerd dan voor bestaande klanten.

Naast de wijzigingen in het groepsbeheer, wordt de volgende functionaliteit afgeschaft:
- Uitsluiten van leden of groepen tijdens het maken van een nieuwe groep
- Groepen van **Niet-gegroepeerde gebruikers** en **Niet-gegroepeerde apparaten**
- **Groepen beheren** in de rol van servicebeheerder
- Aangepaste waarschuwingen op basis van groepen voor meldingsregels
- Draaien met groepen in rapporten

Meer informatie over hoe deze afschaffingen kunnen worden opgevangen volgt in augustus.

### Toevoeging van 'Meldingen' aan de bedrijfsportal voor Android
In september brengen wij een update uit van de bedrijfsportal voor Android, waarmee een nieuw pictogram **Meldingen** wordt geïntroduceerd op de startpagina. Door op dit pictogram te tikken wordt de pagina **Meldingen** geopend waar de eindgebruiker alle items ziet die aandacht vereisen in de bedrijfsportal-app, zoals niet-compatibele apparaten, inschrijvingsupdates en activering van inschrijvingen. Als u ook de iOS-bedrijfsportal-app gebruikt, kunt u de meldingen al zien. Door de introductie van de pagina **Meldingen** ziet u niet langer de pagina **Bedrijfstoegang instellen** wanneer u de bedrijfsportal voor Android start of hervat als het apparaat reeds is ingeschreven. Wij weten dat velen van u een handleiding hebben gemaakt voor eindgebruikers en stellen het op prijs wanneer u ons tijdig informeert wanneer uw handleiding en/of schermafbeeldingen moeten worden bijgewerkt. Werk uw documentatie bij zodat toekomstige wijzigingen in de gebruikerservaring goed worden beschreven. Bijgewerkte schermafbeeldingen vindt u hier: https://aka.ms/androidcpupdate.  



### Cloudroadmap
Blijf op de hoogte van toekomstige ontwikkelingen op het gebied van Intune met de [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Serviceafschaffing
- **Wijzigingen in de ondersteuning voor de iOS-bedrijfsportal-app**<br/>
In september moeten alle gebruikers van de Microsoft Intune-bedrijfsportal-app voor iOS overstappen naar de nieuwste versie. Nieuwe gebruikers kunnen alleen de nieuwste versie downloaden en bestaande gebruikers moeten bijwerken naar de nieuwe versie. De meest recente versie vereist iOS 8.0 of hoger, zodat apparaten met oudere versies van iOS de bedrijfsportal niet kunnen gebruiken en niet kunnen registreren totdat ze hun apparaat naar hebben bijgewerkt naar iOS 8.0 of hoger en vervolgens de bedrijfsportal-app bijwerken naar de nieuwste versie. Geregistreerde apparaten met een versie lager dan iOS 8.0 worden gewoon nog worden beheerd met en vermeld in de Intune-beheerconsole.  

- **Minimale iOS Managed Browser-versie is bijgewerkt naar 8.0**<br/>
In augustus brengt Intune een bijgewerkte Microsoft Intune Managed Browser-app uit voor iOS die alleen apparaten ondersteund waarop iOS 8.0 of later wordt uitgevoerd. Hoewel iOS 7.1-apparaten nog steeds de bestaande Managed Browser-app kunnen gebruiken, dient u uw gebruikers aan te moedigen bij te werken naar iOS 8.0 of later om volledig te kunnen profiteren van nieuwe functies van Managed Browser.  
<!---TFS 1313253--->

- **Bedrijfsportal-apps voor Windows 8 en Windows Phone 8 worden vanaf september 2016 afgeschaft** <br/>
Vanaf september 2016 biedt Microsoft Intune geen ondersteuning meer voor de Microsoft Intune-bedrijfsportal-apps voor Windows Phone 8 en Windows 8. Apparaten bijwerken naar Windows 8.1 en Windows Phone 8.1 en de bijbehorende bedrijfsportal-app voor Windows 8.1 en Windows Phone 8.1 gebruiken om door te gaan met het distribueren van apps naar deze apparaten.
<!---TFS 1255391--->

- **Intune-viewer-apps** <br/>
Met het uitbrengen van de nieuwe RMS-app voor delen, worden volgende Intune-viewer-apps vanaf augustus 2016 verwijderd:
    - Intune AV-viewer
    - Intune PDF-viewer
    - Intune-afbeeldingsviewer voor Android van Google Play

  In plaats van de viewer-apps van Intune kunt u beter de nieuwe [Rights Management-app (RMS sharing) voor Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app) gebruiken, zodat u één app in plaats van drie afzonderlijke apps kunt implementeren om veilig bedrijfsbestanden op Android-apparaten te bekijken. Als de Intune-viewer-app niet meer wordt ondersteund, wordt deze verwijderd uit de Google Store en zal deze niet meer beschikbaar zijn voor toekomstig gebruik.

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->



## Vorige versies van Intune
Raadpleeg het artikel over [Vorige versies van Intune](previous-intune-releases.md) als u wilt zien wat er de afgelopen zes maanden voor Intune is uitgekomen.

### Zie tevens
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Aug16_HO2-->


