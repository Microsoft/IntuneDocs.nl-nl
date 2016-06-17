---
# required metadata

title: Problemen met de clientinstallatie oplossen | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 05/26/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e46d292b-1d16-46db-a87f-d53eefa4d22a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Problemen met de clientinstallatie oplossen in Microsoft Intune
Gebruik de volgende informatie voor hulp bij het oplossen van algemene problemen met clientinstallaties. Zie [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md) voor meer manieren om hulp te krijgen als u het probleem niet kunt oplossen met deze informatie.

## De clientinstallatie is mislukt

-   Als er bij de implementatie van clientsoftware geen waarschuwingen voor de computer worden weergegeven in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/), controleert u de internetverbinding en proxyconfiguratie van de computer en zorgt u ervoor dat de computer kan communiceren met de service-URL, [https://manage.microsoft.com](https://manage.microsoft.com/). Probeer de clientsoftware vervolgens opnieuw te installeren.

-   U kunt een e-mailbericht laten verzenden naar geselecteerde ontvangers wanneer er een waarschuwing voor een fout bij de implementatie van clientsoftware optreedt, door een meldingsregel te configureren in de werkruimte **Beheer** . Zie [Blijf op de hoogte met Microsoft Intune-waarschuwingen](/intune/deploy-use/get-notified-by-microsoft-intune-alerts) voor meer informatie.

-   In Intune wordt de kritieke waarschuwing **Mislukte implementatie van de clientsoftware** weergegeven als de implementatie van de clientsoftware mislukt. Deze waarschuwing wordt weergegeven op de pagina **Systeemoverzicht** en de **Waarschuwingen**-pagina's van de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/). Ga als volgt te werk om op waarschuwingen te controleren:

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) **Waarschuwingen** &gt; **Overzicht**.

2.  Op de pagina **Waarschuwingsoverzicht** pagina kunt u de volgende informatie bekijken:

    -   De belangrijkste drie waarschuwingen, die kunnen worden gerangschikt op datum, categorie of ernst

    -   Het totale aantal actieve waarschuwingen

3.  Kies **Alle waarschuwingen** om de volgende informatie weer te geven op de pagina **Waarschuwingen**. Kritieke waarschuwingen worden eerst weergegeven:

    -   **Naam** : de naam van het waarschuwingstype dat de waarschuwing heeft gegenereerd.

    -   **Bron** : een koppeling naar de bron van de waarschuwing.  Als de drempelwaarde voor weergave van het waarschuwingstype is ingesteld op **Alle**, zal via deze koppeling een enkel betrokken apparaat worden weergeven.  Als de drempelwaarde voor weergave van het waarschuwingstype is ingesteld op een waarde, zal via deze koppeling een lijst worden weergegeven met alle apparaten waarop deze waarschuwing betrekking heeft.

    -   **Laatst bijgewerkt** : geeft de tijd aan waarop de waarschuwing voor het laatst is gewijzigd. Als een waarschuwing is gesloten, wordt de tijd weergegeven waarop de waarschuwing is gesloten.

    -   **Ernst** : dit geeft de ernst van waarschuwing aan

## Het computerregistratiepakket wordt niet gedownload
**Probleem:** het volgende gebeurt wanneer u een computer registreert:
-  Het registratiepakket wordt niet gedownload 
-  Het downloadvenster wordt weergegeven, maar er treedt een time-out op

**Oplossing:** controleer in de browser die u voor het downloaden gebruikt, of downloads zijn ingeschakeld gedurende de periode waarin het downloaden plaatsvindt. Controleer ook of versleutelde bestanden kunnen worden opgeslagen op uw lokale schijf.

## De installatie van de client reageert niet meer en geeft de foutcode 0x80040154
**Probleem:**
 
-  De installatie van de client reageert niet meer tijdens de registratie

-  Kan apparaat niet registreren 

-  Fout 0x80040154 in WindowsUpdate.log

Dit kan worden veroorzaakt door het ontbreken van essentiële software-updates op de pc.

**Oplossing:** zorg ervoor dat met uw beleid voor software-updates de installatie van essentiële updates is toegestaan, zoals is beschreven in [Windows-pc's up-to-date houden met software-updates in Microsoft Intune](/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune) 


## Aan Microsoft Intune-beleid gerelateerde fouten in policyplatform.log
Voor niet-MDM Windows-apparaten kunnen beleidsfouten in het bestand policyplatform.log het gevolg zijn van niet-standaardinstellingen in Windows Gebruikersaccountbeheer (UAC) op het apparaat. Bepaalde niet-standaard-UAC-instellingen kunnen Microsoft Intune-clientinstallaties en de uitvoering van het beleid beïnvloeden.

### UAC-problemen oplossen

1.  Stel de computer buiten gebruik, zoals is beschreven in [Gegevens en apparaten buiten gebruik stellen vanuit Microsoft Intune-beheer](/intune/deploy-use/retire-devices-from-microsoft-intune-management).

2.  Wacht twintig minuten tot de clientsoftware is verwijderd.

    > [!NOTE] Verwijder de client niet vanuit Programma's en onderdelen.

3.  Typ **UAC** in het startmenu om de instellingen voor Gebruikersaccountbeheer te openen.

4.  Verplaats de schuifregelaar voor meldingen naar de standaardinstelling.

## Wat te doen als de client niet kan worden verwijderd uit de Microsoft Intune-beheerconsole

### De clientsoftware verwijderen via het Microsoft Intune-opdrachtregelprogramma

1.  Open een opdrachtprompt in de beheerdersmodus.

2.  Ga naar de map *%programfiles%\Microsoft\OnlineManagement\Common*

3.  Voer de volgende opdracht uit ``ProvisioningUtil.exe /UninstallAgents /MicrosoftIntune``

## Foutcodes voor clientinstallatie
In de volgende tabel worden foutcodes beschreven die worden weergegeven in **Waarschuwingen** als de installatie van clientsoftware mislukt. De tabel bevat suggesties voor het oplossen van het probleem dat door elke foutcode wordt vertegenwoordigd.

|Foutcode|Mogelijk probleem|Voorgestelde oplossing|
|--------------|--------------------|------------------------|
|**0x80CF0437**|De klok op de clientcomputer is niet ingesteld op de juiste tijd.|Zorg ervoor dat de klok en de tijdzone op de clientcomputer zijn ingesteld op de juiste tijd en tijdzone.|
|**0x80240438**, **0x80CF0438**, **0x80CF401B**|Kan geen verbinding maken met de Intune-service. Controleer de proxy-instellingen voor de client.|Controleer of de proxyconfiguratie op de clientcomputer wordt ondersteund door Intune en of de clientcomputer internettoegang heeft. Zie [Help Windows-pc's beveiligen met Endpoint Protection voor Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune) voor meer informatie over ondersteunde proxyconfiguraties.|
|**0x80CF402C**|Kan geen verbinding maken met de Intune-service. Controleer de netwerkverbinding.|Controleer of de computer netwerkverbinding heeft. Controleer of de netwerkkabel is verbonden en of het draadloze netwerk is ingeschakeld.|
|**0x80240438, 0x80CF0438**|Proxy-instellingen in Internet Explorer en lokaal systeem zijn niet geconfigureerd.|Controleer de proxyinstellingen van de client en verzeker u ervan dat de proxyconfiguratie op de clientcomputer wordt ondersteund door Intune. Controleer ook of de clientcomputer internettoegang heeft. Zie [Help Windows-pc's beveiligen met Endpoint Protection voor Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune) voor meer informatie over ondersteunde proxyconfiguraties.|
|**0x80043001**|Inschrijvingspakket is verouderd.|Download en installeer het huidige clientsoftwarepakket uit de werkruimte **Beheer** . Zie het onderwerp [Installeer de Windows-pc-client met Microsoft Intune](/intune/deploy-use/install-the-windows-pc-client-with-microsoft-intune) voor instructies.|
|**0x80043004**|Abonnement bestaat niet of is uitgeschakeld.|Controleer of uw account en abonnement op Intune nog actief zijn. U kunt uw accountinstellingen weergeven door u in het [Office 365-beheercentrum](http://go.microsoft.com/fwlink/?LinkId=698854%20) aan te melden bij uw account.|
|**0x80043002**|Account is in onderhoudsmodus.|U kunt geen nieuwe clientcomputers inschrijven wanneer de account in onderhoudsmodus is. U kunt uw accountinstellingen weergeven door u in het [Office 365-beheercentrum](http://go.microsoft.com/fwlink/?LinkId=698854%20) aan te melden bij uw account.|
|**0x80043003**|Account is verwijderd.|Controleer of uw account en abonnement op Intune nog actief zijn. Meld u aan bij uw account om uw accountinstellingen weer te geven.|
|**0x80043005**|De clientcomputer is buiten gebruik gesteld.|Wacht enkele uren, verwijder oudere versies van de clientsoftware van de computer en voer de installatie van de clientsoftware opnieuw uit. Zie **Wat te doen als de client niet kan worden verwijderd uit de Microsoft Intune-beheerconsole** hierboven voor instructies.|
|**0x80043006**|Het maximumaantal plaatsen dat is toegestaan voor de account, is bereikt.|Uw organisatie moet extra plaatsen aanschaffen voordat u meer clientcomputers in de service kunt inschrijven.|
|**0x80043007**|Kan het certificaatbestand niet vinden in dezelfde map als het installatieprogramma.|Pak alle bestanden uit voordat u de installatie start. Wijzig of verplaats de uitgepakte bestanden niet: alle bestanden moeten aanwezig zijn in dezelfde map, anders mislukt de installatie. Zie [Installeer de Windows-pc-client met Microsoft Intune](/intune/deploy-use/install-the-windows-pc-client-with-microsoft-intune) voor meer informatie.|
|**0x8024D015**, **0x00240005**, **0x80070BC2**, **0x80070BC9**, **0x80CFD015**|De software kan niet worden geïnstalleerd omdat een herstart van de client in behandeling is.|Start de computer opnieuw op en voer de installatie van de clientsoftware opnieuw uit.|
|**0x80070032**|Een of meer vereisten voor het installeren van de clientsoftware zijn niet gevonden op de clientcomputer.|Zorg ervoor dat alle vereiste updates zijn geïnstalleerd op de clientcomputer en voer de installatie van de clientsoftware opnieuw uit. Zie [Vereisten voor de netwerkinfrastructuur voor Microsoft Intune](/intune/get-started/network-infrastructure-requirements-for-microsoft-intune) voor meer informatie over de vereisten voor de installatie van de clientsoftware.|
|**0x80043008**|De updateservice voor Microsoft Online Management kan niet worden gestart.|Neem contact op met Ondersteuning, zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).|
|**0x80043009**|De clientcomputer is al ingeschreven bij de service.|U moet de clientcomputer buiten gebruik stellen voordat u deze opnieuw in de service kunt inschrijven. Zie [Retire devices from Microsoft Intune management](/intune/deploy-use/retire-devices-from-microsoft-intune-management) (Apparaten buiten gebruik stellen vanuit Microsoft Intune-beheer) voor instructies.|
|**0x8004300B**|Het installatiepakket voor de clientsoftware kan niet worden uitgevoerd omdat de versie van Windows die op de client wordt uitgevoerd, niet wordt ondersteund.|Intune biedt geen ondersteuning voor de versie van Windows die wordt uitgevoerd op de clientcomputer. Zie [Vereisten voor de netwerkinfrastructuur voor Microsoft Intune](/intune/get-started/network-infrastructure-requirements-for-microsoft-intune) voor een lijst met ondersteunde besturingssystemen.|
|**0xAB2**|Windows Installer heeft geen toegang tot VBScript-runtime voor aangepaste actie.|Deze fout wordt veroorzaakt door een aangepaste actie die is gebaseerd op DLL-bestanden. Wanneer u problemen met DLL oplost, moet u mogelijk gebruikmaken van de hulpprogramma’s die worden beschreven in [Microsoft Ondersteuning KB198038: Useful Tools for Package and Deployment Issues (Nuttige hulpprogramma’s voor pakket- en implementatieproblemen)](http://go.microsoft.com/fwlink/?LinkID=234255).|
|**0x8004300f**|De software kan niet worden geïnstalleerd omdat de System Center Configuration Manager-client al is geïnstalleerd.|Verwijder de Configuration Manager-client en voer de installatie van de clientsoftware opnieuw uit.|
|**0x80043010**|De software kan niet worden geïnstalleerd omdat de Open Mobile Alliance Device Management-client (OMADM) al is geïnstalleerd.|Maak de inschrijving van de OMADM-client ongedaan en probeer de clientsoftware vervolgens opnieuw te installeren.|
Als de installatieproblemen zich blijven voordoen, neemt u contact op met Ondersteuning, zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md). Zorg ervoor dat u het registratielogboek van de clientcomputer (in %*programfiles*%\Microsoft\OnlineManagement\Logs\Enrollment.log en %*userprofile*%\AppData\Local\Microsoft\OnlineManagement\Logs\Enrollment.log) en het Windows Update-logboek (%*windir*%\windowsupdate.log) bij de hand hebt om aan ondersteuningstechnici te laten zien.

### Volgende stappen
Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).


<!--HONumber=Jun16_HO1-->


