---
title: Include-bestand
description: Include-bestand
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 11/19/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 373aeea9ab4fcbd075ac2ab18f205f3ddd191a39
ms.sourcegitcommit: 29f3ba071c9348686d3ad6f3b8864d8557e05b97
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/26/2020
ms.locfileid: "77609294"
---
Deze mededelingen bevatten belangrijke informatie die u kan helpen om voorbereid te zijn op toekomstige wijzigingen en functies in Intune.

### <a name="microsoft-intune-support-for-windows-10-mobile-ending--3544938--"></a>Microsoft Intune-ondersteuning voor Windows 10 Mobile wordt afgeschaft<!--3544938-->
Microsoft-ondersteuning voor Windows 10 Mobile is in december 2019 afgeshaft. Zoals is vermeld in deze verklaring, komen gebruikers van Windows 10 Mobile niet meer in aanmerking voor nieuwe beveiligingspatches, hotfixes anders dan beveiligings, gratis ondersteuningsopties of online technische contentupdates van Microsoft. Op basis van de ondersteuning voor het mobiele besturingssysteem beëindigt Microsoft Intune op 11 mei 2020 de ondersteuning voor zowel de Bedrijfsportal voor de mobiele Windows 10-app als het besturingssysteem van Windows Mobile.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Als u Windows 10 Mobile-apparaten gebruikt in uw organisatie, kunt u tussen nu en 11 mei 2020 nieuwe apparaten inschrijven, beleid en apps toevoegen of verwijderen of beheerinstellingen bijwerken. Na 11 mei stoppen we nieuwe inschrijvingen en verwijderen we uiteindelijk Windows 10 Mobile-beheer uit de Intune-gebruikersinterface. Apparaten checken niet langer in bij de Intune-service en we verwijderen apparaat- en beleidsgegevens.  

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Controleer uw Intune-rapporten om na te gaan voor welke apparaten of gebruikers dit gevolgen kan hebben. Ga naar **Apparaten** > **Alle apparaten** en filter op besturingssysteem. U kunt extra kolommen toevoegen, zodat u eenvoudiger kunt vaststellen wie in uw organisatie apparaten met Windows 10 Mobile gebruikt. Vraag uw eindgebruikers hun apparaten te vernieuwen of stop het gebruik van deze apparaten voor zakelijke toegang.



### <a name="plan-for-change-change-in-experience-when-enrolling-android-enterprise-dedicated-devices-in-intune--6114580--"></a>Geplande wijziging: Gewijzigde ervaring bij het inschrijven van toegewezen Android Enterprise-apparaten in Intune<!--6114580-->
Bij de release van november kondigde we aan dat we ondersteuning toe gingen voegen voor de implementatie van SCEP-apparaatcertificaten aan toegewezen Android Enterprise-apparaten, om op certificaten gebaseerde toegang tot Wi-Fi-profielen mogelijk te maken. Voor deze wijziging waren enkele kleine wijzigingen nodig in de inschrijvingsstroom voor toegewezen Android Enterprise-apparaten. In de aanstaande service-update van maart (oftewel build 2003) zitten enkele aanvullende wijzigingen waar we u op willen wijzen.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Als u toegewezen Android Enterprise-apparaten in uw omgeving beheert, zult u in maart enkele veranderingen gaan zien.
- Voor bestaande toegewezen Android-apparaten die zijn ingeschreven vóór 22 november 2019 of de 1911-service-update: Op deze apparaten is de app Microsoft Intune geïnstalleerd. Nadat in maart wijzigingen in de back-end van de Intune-service worden doorgevoerd, worden SCEP-certificaten van kracht die op apparaten zijn geïmplementeerd en zijn gekoppeld aan wifi-profielen.
- Voor apparaten die zijn ingeschreven na 22 november 2019 en voordat deze wijziging in maart wordt doorgevoerd: Op deze apparaten is de app Microsoft Intune geïnstalleerd. SCEP-certificaten die zijn geïmplementeerd op apparaten en die zijn gekoppeld aan wifi-profielen, blijven van toepassing.
- Nieuwe inschrijvingen van toegewezen Android Enterprise-apparaten, nadat de wijzigingen in maart worden doorgevoerd: Eindgebruikers zien een andere reeks stappen op apparaten bij het inschrijven. De inschrijving start nog steeds zoals nu (met QR, NFC, Zero-touch of apparaat-id), maar er volgt geen verplichte stap voor app-installatie meer. In plaats daarvan wordt de Microsoft Intune-app automatisch op apparaten geïnstalleerd. Daarnaast hoeven eindgebruikers tijdens deze stroom niet op 'Intune-agent inschakelen' te tikken. Er kunnen op deze apparaten SCEP-certificaten worden geïmplementeerd die zijn gekoppeld aan wifi-profielen.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Wat kan ik doen om me voor te bereiden op deze wijziging?
U kunt uw eindgebruikersbegeleiding bijwerken en uw helpdesk op de hoogte brengen van deze wijziging. Wij werken de pagina Nieuwe functies bij en waarschuwen u via het Berichtencentrum wanneer deze wijziging wordt doorgevoerd.

#### <a name="additional-information"></a>Aanvullende informatie
[Ondersteuning voor SCEP-certificaten in toegewezen Android Enterprise-apparaten](https://aka.ms/Dedicated_devices_enrollment)

### <a name="updated-support-statement-for-adobe-acrobat-reader-for-intune-mobile-app--5746776--"></a>Bijgewerkte ondersteuningsmededeling over de mobiele app Adobe Acrobat Reader voor Intune<!--5746776-->
Eind augustus hebben we via MC188653 meegedeeld dat de mobiele app Adobe Acrobat Reader voor Intune op 1 december 2019 het eind van zijn levenscyclus heeft bereikt en dat Adobe van plan is om ondersteuning te bieden voor de app-beveiliging van Intune vanuit de belangrijkste Acrobat Reader-app. Sindsdien hebben we feedback van klanten ontvangen dat we IT-beheerders meer tijd moesten geven om zich bezig te houden met Adobe Acrobat Reader voor Intune en dat eindgebruikers meer tijd nodig hadden om zich Adobe Acrobat Reader voor Intune eigen te maken. Omdat Adobe Acrobat Reader voor Intune veel wordt gebruikt op apparaten van eindgebruikers en een belangrijke rol speelt in bedrijfsscenario's, willen we kunnen blijven garanderen dat elke ervaring voldoet aan de vereisten die uw organisatie stelt aan de bescherming van haar apps. 

Hoewel we nog steeds aanraden om uw beleid op de algemene mobiele Acrobat Reader-app toe te passen, omdat de mobiele Acrobat Reader-app beveiligingsbeleid voor apps ondersteunt en de Intune-SDK erin is geïntegreerd, wordt de Adobe Acrobat Reader voor Intune-app nog ondersteund tot en met 31 maart 2020. 

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
U ontvangt dit bericht omdat tijdens onze rapportage is gebleken dat er een of meer beleidsregels in uw organisatie zijn die zich richten op de toepassing Adobe Acrobat Reader voor Intune en/of omdat u onze vorige EOL-communicatie hebt ontvangen. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Breng uw eindgebruikers en helpdesk op de hoogte van deze wijziging. U kunt de [functionaliteit van de bedrijfsportal voor het afhandelen van ondersteuningsinformatie](../apps/company-portal-app.md#support-information) gebruiken om een kanaal op te zetten voor het stellen en beantwoorden van vragen met betrekking tot Intune.

#### <a name="additional-information"></a>Aanvullende informatie
https://helpx.adobe.com/acrobat/kb/intune-app-end-of-life.html


### <a name="take-action-use-microsoft-edge-for-your-protected-intune-browser-experience--5728447--"></a>Onderneem actie: Gebruik Microsoft Edge als uw beveiligde Intune-browser<!--5728447-->
Zoals we al hebben gecommuniceerd in het afgelopen jaar, ondersteunt Microsoft Edge voor mobiel dezelfde beheerfuncties als Managed Browser, maar is de ervaring voor de eindgebruiker sterk verbeterd. Om plaats te maken voor de nieuwe gebruikerservaring die met Microsoft Edge wordt geboden, wordt Intune Managed Browser buiten gebruik gesteld. Vanaf 27 januari 2020 wordt Intune Managed Browser niet meer ondersteund door Intune.  

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij? 
Vanaf 1 februari 2020 is Intune Managed Browser niet meer beschikbaar in de Google Play Store of de App Store voor iOS. Vanaf dan kunt u nog steeds nieuw app-beveiligingsbeleid toepassen op Intune Managed Browser, maar kunnen nieuwe gebruikers de Intune Managed Browser-app niet meer downloaden. In iOS worden bovendien nieuwe webclips die worden gepusht naar apparaten die via MDM zijn ingeschreven, geopend in Microsoft Edge in plaats van in Intune Managed Browser.  

Op 31 maart 2020 wordt Intune Managed Browser verwijderd uit de Azure-console. Dit betekent dat u geen nieuwe beleidsregels meer kunt maken voor Intune Managed Browser. Bestaand Intune Managed Browser-beleid dat u hebt geïmplementeerd, wordt hierdoor niet beïnvloed. Intune Managed Browser wordt weergegeven in de console als een LOB-app zonder pictogram en bestaande beleidsregels worden nog steeds weergegeven als gericht op de app. Vanaf dan wordt ook de optie voor het omleiden van webinhoud naar Intune Managed Browser verwijderd uit de sectie Gegevensbescherming van App-beveiligingsbeleid.  

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging? 
Voor een soepele overgang van Intune Managed Browser naar Microsoft Edge wordt u aangeraden de volgende stappen proactief uit te voeren: 

1. Stel Microsoft Edge voor iOS en Android in als doel met app-beveiligingsbeleid (ook wel MAM genoemd) en app-configuratie-instellingen. U kunt uw Intune Managed Browser-beleid opnieuw gebruiken voor Microsoft Edge door ook die bestaande beleidsregels te richten op Microsoft Edge.  
2. Voor alle apps in uw omgeving die met MAM worden beveiligd, moet de app-beveiligingsbeleidsinstelling 'Overdracht van webinhoud met andere apps beperken' zijn ingesteld op 'Browsers die worden beheerd met beleid'. 
3. Stel het doel in van alle apps die met MAM worden beveiligd, waarbij u de configuratie-instelling 'com.microsoft.intune.useEdge' van de beheerde app instelt op true (waar). Met ingang van de release van 1911 kunt u stap 2 en stap 3 eenvoudig uitvoeren door de instelling 'Overdracht van webinhoud met andere apps beperken' te configureren voor Microsoft Edge in de sectie Gegevensbescherming van uw app-beveiligingsbeleid. 

Ondersteuning voor webclips in iOS en Android is binnenkort beschikbaar. Wanneer deze ondersteuning wordt uitgebracht, moet u het doel van bestaande webclips opnieuw instellen om ervoor te zorgen dat ze worden geopend in Microsoft Edge in plaats van in Managed Browser. 

#### <a name="additional-information"></a>Aanvullende informatie
Bekijk onze documenten over het [gebruik van Microsoft Edge met app-beveiligingsbeleid](../apps/manage-microsoft-edge.md) voor meer informatie of lees onze [blogpost over ondersteuning](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Use-Microsoft-Edge-for-your-Protected-Intune-Browser-Experience/ba-p/1004269).


### <a name="end-of-support-for-legacy-pc-management"></a>Einde van ondersteuning voor verouderd pc-beheer

Verouderd pc-beheer wordt vanaf 15 oktober 2020 niet meer ondersteund. Werk apparaten bij naar Windows 10 en registreer deze opnieuw als MDM-apparaten (Mobile Device Management) om ze door Intune te blijven laten beheren.

[Meer informatie](https://go.microsoft.com/fwlink/?linkid=2107122)

### <a name="decreasing-support-for-android-device-administrator--5857738--"></a>Afgenomen ondersteuning voor Android-apparaatbeheerder<!--5857738-->
Android-apparaatbeheerder (soms aangeduid met het verouderde Android-beheer, uitgebracht met Android 2.2) is een manier om Android-apparaten te beheren. Er is nu echter verbeterde beheerfunctionaliteit beschikbaar met [Android Enterprise](../enrollment/connect-intune-android-enterprise.md) (uitgebracht met Android 5.0). In een poging om apparaatbeheer moderner, breder en veiliger te maken, vermindert Google ondersteuning voor apparaatbeheerder in nieuwe Android-versies.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Deze wijzigingen van Google zijn op de volgende manieren van invloed op Intune-gebruikers:  
- Intune biedt slechts tot het tweede kwartaal van 2020 nog ondersteuning voor Android-apparaten met Android 10 en hoger die door apparaatbeheerder worden beheerd. Apparaten die worden beheerd met apparaatbeheerder en worden uitgevoerd met Android 10 of hoger, kunnen na dit moment niet langer volledig worden beheerd. Betrokken apparaten ontvangen met name geen nieuwe wachtwoordvereisten meer.
    - Samsung Knox-apparaten worden gedurende deze periode niet beïnvloed, omdat uitgebreide ondersteuning wordt geboden via de integratie van Intune met het Knox-platform. Dit geeft u meer tijd om af te stappen van apparaatbeheerder.    
- Android-apparaten die worden beheerd met apparaatbeheerder en worden uitgevoerd met oudere versies dan Android 10, worden niet getroffen en kunnen volledig beheerd blijven worden met apparaatbeheerder.    
- Voor alle apparaten met Android 10 of hoger heeft Google de toegang voor apparaatbeheerderagents als de Bedrijfsportal tot apparaat-id's beperkt. Nadat een apparaat naar Android 10 of hoger is bijgewerkt, heeft deze beperking gevolgen voor de volgende Intune-functies:  
    - Netwerktoegangsbeheer voor VPN werkt niet meer.   
    - Als u apparaten identificeert als 'In bedrijfseigendom' met een IMEI of serienummer, wordt het apparaat niet automatisch gemarkeerd als 'In bedrijfseigendom'.  
    - Het IMEI en serienummers zijn niet langer zichtbaar voor IT-beheerder in Intune. 
        > [!NOTE]
        > Dit heeft alleen gevolgen voor apparaten die worden beheerder met apparaatbeheerder en worden uitgevoerd met Android 10 of hoger en is niet van invloed op apparaten die worden beheerd met Android Enterprise. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Volg de volgende aanbevelingen op om te voorkomen dat u in het derde kwartaal van 2020 te kampen hebt met beperkte functionaliteit:
- Leg geen nieuwe apparaten vast in apparaatbeheerder.
- Als bij een apparaat een update naar Android 10 wordt verwacht, migreert u deze van apparaatbeheerder naar Android Enterprise-beheer en/of app-beveiligingsbeleid.

#### <a name="additional-information"></a>Aanvullende informatie
- [Google-richtlijnen voor migratie van apparaatbeheerder naar Android Enterprise](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Google-documentatie over het plan om de apparaatbeheerder-API af te schaffen](https://developers.google.com/android/work/device-admin-deprecation)



