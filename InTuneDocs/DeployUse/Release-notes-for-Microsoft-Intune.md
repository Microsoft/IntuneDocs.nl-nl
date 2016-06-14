---
# required metadata

title: Opmerkingen bij de release van Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Opmerkingen bij de release van Microsoft Intune
Microsoft Intune is een geïntegreerde cloudoplossing voor clientbeheer die voorziet in hulpprogramma's, rapporten en upgradelicenties voor de nieuwste versie van Windows, en die u helpt uw computers up-to-date en beveiligd te houden. Bovendien kunt u met Intune mobiele apparaten in het netwerk beheren via Exchange ActiveSync of rechtstreeks via Intune. In de volgende opmerkingen bij de release staat belangrijke informatie en worden bekende problemen in Microsoft Intune beschreven.


## Android-gebruikers kunnen geen e-mail verzenden wanneer voorwaardelijke toegang voor Exchange Online is geïmplementeerd

Gebruikers die op hun apparaten werken met Samsung Android 5.1.1 en later, kunnen geen e-mail verzenden wanneer voorwaardelijke toegang voor Exchange Online is geconfigureerd. Samsung bevestigt dat het probleem te maken heeft met de ingebouwde e-mailclient in Android 5.1.1 en later, en zoekt momenteel naar een oplossing.

**Tijdelijke oplossing 1:** adviseer eindgebruikers de Outlook-app voor Android te gebruiken.

**Tijdelijke oplossing 2:** volg deze stappen zodat betrokken gebruikers e-mail kunnen verzenden:

1. Plaats de betrokken gebruiker in een beveiligingsgroep in het gedeelte 'Uitgesloten groepen' van het beleid voor voorwaardelijke toegang voor Exchange Online.
2. Laat de gebruiker tijdelijk e-mail synchroniseren met de ingebouwde e-mailclient.
3. Verwijder de betrokken gebruiker uit de uitgesloten groep en controleer of de gebruiker nu e-mail kan verzenden.

Microsoft blijft nauw met Samsung samenwerken aan een oplossing of aanvullende tijdelijke oplossingen.



## Het wijzigen van brontoegangsprofielen tussen groepen voor iOS en Android kan mislukken
**Probleem:** wanneer u brontoegangsprofielen voor e-mail of het Simple Certificate Enrollment Protocol (SCEP) tussen groepen wijzigt, kan er een profielconflict optreden, waardoor het wijzigen mislukt. Stel dat u een bestaand e-mailprofiel hebt dat verwijst naar een lokale Exchange-server, met als doel Groep A, en u vervolgens een nieuw e-mailprofiel maakt dat naar Exchange Online verwijst, met als doel Groep B. Wanneer u gebruikers van groep A naar groep B verplaatst, blijft het lokale Exchange-e-mailprofiel op de apparaten behouden en wordt geprobeerd het e-mailprofiel van Exchange Online te installeren dat groep B als doel heeft.

Op dat moment wordt een van de volgende scenario’s van kracht: 
* Als e-mailprofiel A en B identiek zijn, verwerpt het apparaat e-mailprofiel B omdat e-mailprofiel B al e-mailprofiel A bevat.
* Als e-mailprofiel A anders is dan e-mailprofiel B, zoals in bovenstaand voorbeeld het geval is, heeft het apparaat twee e-mailprofielen.

**Opmerking:** de hostnaam en het kenmerk die voor de gebruikersnaam worden gebruikt, worden gecontroleerd om het ene e-mailprofiel van het andere te onderscheiden.

In beide bovenstaande gevallen is het brontoegangsprofiel (e-mailprofiel) niet van het apparaat verwijderd om te voorkomen dat de toegang van een gebruiker tot e-mail of het SCEP-certificaat van een client wordt verwijderd.

**Tijdelijke oplossing:** geen.

## Wanneer u een Windows 8.1-apparaat inschrijft dat moet worden geverifieerd met een proxyserver, mislukt het inschrijvingsproces zonder zichtbare aanwijzing van de oorzaak van de fout
**Probleem:** wanneer u een Windows 8.1-apparaat inschrijft en het apparaat moet tijdens het inschrijvingsproces worden geverifieerd bij een proxyserver, mislukt de inschrijving als de referenties voor de proxyserver niet zijn opgeslagen in de cache van het apparaat. Wanneer de referenties voor de proxyserver niet in de cache van het apparaat zijn opgeslagen, wordt het inschrijvingsproces opgeschort totdat de gebruiker de referenties invoert. De vraag om de proxyserverreferenties op te geven wordt echter niet weergegeven tijdens het inschrijvingsproces. Het resultaat is dat het inschrijvingsproces niet kan worden geverifieerd met de proxyserver en er geen zichtbare indicatie van het mislukken wordt weergegeven voor de gebruiker.

**Tijdelijke oplossing:** voor Windows 8.1-apparaten die moeten worden ingeschreven in een netwerk waarvoor het gebruik van een geverifieerde proxyserver is vereist, moet u de referenties voor de proxyserver configureren en opslaan voordat het apparaat wordt ingeschreven. Ga als volgt te werk om de referenties te configureren en op te slaan op een Windows 8.1-apparaat:

1.  Open **Internet Explorer** op het Windows 8.1-apparaat.

2.  Als u wordt gevraagd naar de referenties voor de proxyserver, voert u de referenties in en selecteert u vervolgens de optie **Mijn referenties onthouden**.

3.  Het apparaat inschrijven.

## Inschrijving van Windows Phone 8.1-apparaten bij Microsoft Intune mislukt wanneer apparaatverificatie is ingeschakeld in AD FS
**Probleem:** wanneer u een Windows Phone 8.1-apparaat inschrijft, mislukt de inschrijving als de optionele instelling voor apparaatverificatie is ingeschakeld als onderdeel van het algemene verificatiebeleid in Active Directory Federated Services (AD FS).

**Tijdelijke oplossing:** schakel de apparaatverificatie uit op de AD FS-server door de optie **Apparaatverificatie inschakelen** uit te schakelen in **Algemeen verificatiebeleid bewerken**. Zie [Verificatiebeleid configureren](http://technet.microsoft.com/library/dn486781.aspx)voor meer informatie


## De Microsoft Intune App Wrapping Tool voor Android bevat geen ingebouwde mogelijkheid om het programma te verwijderen
**Probleem:** de **Microsoft App Wrapping Tool voor Android** heeft geen ingebouwde functionaliteit voor het verwijderen van het hulpprogramma.

**Tijdelijke oplossing:** blader naar de locatie waar u het hulpprogramma hebt geïnstalleerd en verwijder de map. De standaardlocatie voor de installatie is: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**. Zie [Android-apps voorbereiden voor beheer met de App Wrapping Tool](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) voor meer informatie over de App Wrapping Tool.

## Hulp op afstand is niet beschikbaar op computers met Windows 8 of Windows 8.1
**Probleem:** in deze release is de functie Hulp op afstand niet beschikbaar op computers met Windows 8 of Windows 8.1.

**Tijdelijke oplossing:** geen.

## Waarschuwingsmeldingen voor geadresseerden die automatisch worden toegevoegd, werken niet
**Probleem:** als een geadresseerde automatisch aan een waarschuwingsmelding wordt toegevoegd, is het mogelijk dat deze de melding niet altijd ontvangt.

**Tijdelijke oplossing:** om ervoor te zorgen dat geadresseerden meldingen ontvangen, moet u geadresseerden handmatig toevoegen aan waarschuwingsmeldingen.

## Taalondersteuning in de Azure Preview-portal
De Azure Preview-portal is gemaakt op een nieuw platform en biedt ondersteuning voor de volgende talen: Chinees (Vereenvoudigd), Chinees (Traditioneel), Duits, Engels, Frans, Hongaars, Italiaans, Japans, Koreaans, Nederlands, Pools, Portugees (Brazilië), Portugees (Portugal), Russisch, Spaans, Tsjechisch, Turks en Zweeds.

De Intune-beheerconsole en mobiele eindgebruikers worden ondersteund in de talen Deens, Fins, Grieks, Noors en Roemeens, en in alle talen die worden ondersteund door de Azure Preview-portal.


<!--HONumber=May16_HO1-->


