---
title: Problemen bij clientinstallaties oplossen
description: Algemene problemen met de clientinstallatie oplossen.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 02/22/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e46d292b-1d16-46db-a87f-d53eefa4d22a
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 39c0b0997bdbf229064e6b5ef25ab559b9252f83
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31028075"
---
# <a name="troubleshoot-client-setup-in-microsoft-intune"></a>Problemen met de clientinstallatie oplossen in Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Gebruik de volgende informatie voor hulp bij het oplossen van algemene problemen met clientinstallaties. Zie [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md) voor meer manieren om hulp te krijgen als u het probleem niet kunt oplossen met deze informatie.

## <a name="client-installation-fails"></a>De clientinstallatie is mislukt

-   Als er bij de implementatie van clientsoftware geen waarschuwingen voor de computer worden weergegeven in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/), controleert u de internetverbinding en proxyconfiguratie van de computer en zorgt u dat de computer kan communiceren met de service-URL: [https://manage.microsoft.com](https://manage.microsoft.com/). Probeer de clientsoftware vervolgens opnieuw te installeren.

-   U kunt een e-mailbericht laten verzenden naar geselecteerde ontvangers wanneer er een waarschuwing voor een fout bij de implementatie van clientsoftware optreedt, door een meldingsregel te configureren in de werkruimte **Beheer** . Zie [Blijf op de hoogte met Microsoft Intune-waarschuwingen](/intune-classic/deploy-use/get-notified-by-alerts) voor meer informatie.

-   In Intune wordt de kritieke waarschuwing **Mislukte implementatie van de clientsoftware** weergegeven als de implementatie van de clientsoftware mislukt. Deze waarschuwing wordt weergegeven op de pagina **Systeemoverzicht** en op de pagina **Waarschuwingen** in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/). Ga als volgt te werk om op waarschuwingen te controleren:

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) **Waarschuwingen** &gt; **Overzicht**.

2.  Op de pagina **Waarschuwingsoverzicht** pagina kunt u de volgende informatie bekijken:

    -   De belangrijkste drie waarschuwingen, die kunnen worden gerangschikt op datum, categorie of ernst

    -   Het totale aantal actieve waarschuwingen

3.  Kies **Alle waarschuwingen** om de volgende informatie weer te geven op de pagina **Waarschuwingen**. Kritieke waarschuwingen worden eerst weergegeven:

    -   **Naam** : de naam van het waarschuwingstype dat de waarschuwing heeft gegenereerd.

    -   **Bron** : een koppeling naar de bron van de waarschuwing.  Als de drempelwaarde voor weergave van het waarschuwingstype is ingesteld op **Alle**, zal via deze koppeling een enkel betrokken apparaat worden weergeven.  Als de drempelwaarde voor weergave van het waarschuwingstype is ingesteld op een waarde, zal via deze koppeling een lijst worden weergegeven met alle apparaten waarop deze waarschuwing betrekking heeft.

    -   **Laatst bijgewerkt** : geeft de tijd aan waarop de waarschuwing voor het laatst is gewijzigd. Als een waarschuwing is gesloten, wordt de tijd weergegeven waarop de waarschuwing is gesloten.

    -   **Ernst** : dit geeft de ernst van waarschuwing aan

## <a name="computer-enrollment-package-doesnt-download"></a>Het computerregistratiepakket wordt niet gedownload
**Probleem:** het volgende gebeurt wanneer u een computer registreert:
-  Het registratiepakket wordt niet gedownload
-  Het downloadvenster wordt weergegeven, maar er treedt een time-out op

**Oplossing:** controleer in de browser die u voor het downloaden gebruikt, of downloads zijn ingeschakeld gedurende de periode waarin het downloaden plaatsvindt en of er versleutelde bestanden kunnen worden opgeslagen op uw lokale schijf.

## <a name="client-installation-hangs-with-error-code-0x80040154"></a>De installatie van de client reageert niet meer en geeft de foutcode 0x80040154
**Probleem:**

-  De installatie van de client reageert niet meer tijdens de registratie

-  Kan apparaat niet registreren

-  Fout 0x80040154 in WindowsUpdate.log

Dit kan worden veroorzaakt door het ontbreken van essentiële software-updates op de pc.

**Oplossing:** zorg ervoor dat met uw beleid voor software-updates de installatie van essentiële updates is toegestaan, zoals is beschreven in [Windows-pc's up-to-date houden met software-updates in Microsoft Intune](/intune-classic/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)


## <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Aan Microsoft Intune-beleid gerelateerde fouten in policyplatform.log
Bij niet-MDM-Windows-apparaten kunnen beleidsfouten in het bestand policyplatform.log het gevolg zijn van niet-standaardinstellingen in Windows Gebruikersaccountbeheer (UAC) op het apparaat. Bepaalde niet-standaard-UAC-instellingen kunnen invloed hebben op Microsoft Intune-clientinstallaties en de beleidsuitvoering.

### <a name="to-resolve-uac-issues"></a>UAC-problemen oplossen

1.  Stel de computer buiten gebruik, zoals is beschreven in [Gegevens en apparaten buiten gebruik stellen vanuit Microsoft Intune-beheer](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management).

2.  Wacht twintig minuten tot de clientsoftware is verwijderd.

    > [!NOTE]
    > Probeer niet om de client te verwijderen vanuit Programma's en onderdelen.

3.  Typ **UAC** in het startmenu om de instellingen voor Gebruikersaccountbeheer te openen.

4.  Verplaats de schuifregelaar voor meldingen naar de standaardinstelling.

## <a name="what-to-do-if-the-client-will-not-uninstall-from-the-microsoft-intune-administrator-console"></a>Wat te doen als de client niet kan worden verwijderd uit de Microsoft Intune-beheerconsole

### <a name="to-remove-the-client-software-by-using-the-microsoft-intune-command-line-tool"></a>De clientsoftware verwijderen via het Microsoft Intune-opdrachtregelprogramma

1.  Open een opdrachtprompt in de beheerdersmodus.

2.  Ga naar de map *%programfiles%\Microsoft\OnlineManagement\Common*

3.  Voer de volgende opdracht uit ``ProvisioningUtil.exe /UninstallAgents /MicrosoftIntune``

## <a name="client-installation-error-codes"></a>Foutcodes voor clientinstallatie
In de volgende tabel worden foutcodes beschreven die worden weergegeven in **Waarschuwingen** als de installatie van clientsoftware mislukt. De tabel bevat suggesties voor het oplossen van het probleem dat door elke foutcode wordt vertegenwoordigd.


|                                                                   Foutcode                                                                    |                                                          Mogelijk probleem                                                          |                                                                                                                                                                                                Voorgestelde oplossing                                                                                                                                                                                                 |
|-------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                           <strong>0x80CF0437</strong>                                                           |                                  De klok op de clientcomputer is niet ingesteld op de juiste tijd.                                  |                                                                                                                                                    Zorg ervoor dat de klok en de tijdzone op de clientcomputer zijn ingesteld op de juiste tijd en tijdzone.                                                                                                                                                     |
|                              <strong>0x80240438</strong>, <strong>0x80CF0438</strong>, <strong>0x80CF401B</strong>                              |                               Kan geen verbinding maken met de Intune-service. Controleer de proxy-instellingen voor de client.                               |                   Controleer of de proxyconfiguratie op de clientcomputer wordt ondersteund door Intune en of de clientcomputer internettoegang heeft. Zie [Help Windows-pc's beveiligen met Endpoint Protection voor Microsoft Intune](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune) voor meer informatie over ondersteunde proxyconfiguraties.                    |
|                                                           <strong>0x80CF402C</strong>                                                           |                                 Kan geen verbinding maken met de Intune-service. Controleer de netwerkverbinding.                                  |                                                                                                                                                   Controleer of de computer netwerkverbinding heeft. Controleer of de netwerkkabel is verbonden en of het draadloze netwerk is ingeschakeld.                                                                                                                                                    |
|                                                     <strong>0x80240438, 0x80CF0438</strong>                                                     |                              Proxy-instellingen in Internet Explorer en lokaal systeem zijn niet geconfigureerd.                              | Controleer de proxyinstellingen van de client en verzeker u ervan dat de proxyconfiguratie op de clientcomputer wordt ondersteund door Intune. Controleer ook of de clientcomputer internettoegang heeft. Zie [Help Windows-pc's beveiligen met Endpoint Protection voor Microsoft Intune](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune) voor meer informatie over ondersteunde proxyconfiguraties. |
|                                                           <strong>0x80043001</strong>                                                           |                                                 Inschrijvingspakket is verouderd.                                                 |                                                                     Download en installeer het huidige clientsoftwarepakket uit de werkruimte <strong>Beheer</strong> . Zie het onderwerp [Installeer de Windows-pc-client met Microsoft Intune](/intune-classic/deploy-use/install-the-windows-pc-client-with-microsoft-intune) voor instructies.                                                                      |
|                                                           <strong>0x80043004</strong>                                                           |                                            Abonnement bestaat niet of is uitgeschakeld.                                            |                                                                                                   Controleer of uw account en abonnement op Intune nog actief zijn. U kunt uw accountinstellingen weergeven door u in het [Office 365-beheercentrum](http://go.microsoft.com/fwlink/?LinkId=698854%20) aan te melden bij uw account.                                                                                                   |
|                                                           <strong>0x80043002</strong>                                                           |                                                  Account is in onderhoudsmodus.                                                   |                                                                                             U kunt geen nieuwe clientcomputers inschrijven wanneer de account in onderhoudsmodus is. U kunt uw accountinstellingen weergeven door u in het [Office 365-beheercentrum](http://go.microsoft.com/fwlink/?LinkId=698854%20) aan te melden bij uw account.                                                                                              |
|                                                           <strong>0x80043003</strong>                                                           |                                                        Account is verwijderd.                                                         |                                                                                                                                            Controleer of uw account en abonnement op Intune nog actief zijn. Meld u aan bij uw account om uw accountinstellingen weer te geven.                                                                                                                                             |
|                                                           <strong>0x80043005</strong>                                                           |                                                  De clientcomputer is buiten gebruik gesteld.                                                   |                                                                  Wacht enkele uren, verwijder oudere versies van de clientsoftware van de computer en voer de installatie van de clientsoftware opnieuw uit. Voor instructies raadpleegt u <strong>Wat te doen als de client niet kan worden verwijderd uit de Microsoft Intune-beheerconsole?</strong> hierboven.                                                                  |
|                                                           <strong>0x80043006</strong>                                                           |                                  Het maximumaantal plaatsen dat is toegestaan voor de account, is bereikt.                                   |                                                                                                                                                    Uw organisatie moet extra plaatsen aanschaffen voordat u meer clientcomputers in de service kunt inschrijven.                                                                                                                                                     |
|                                                           <strong>0x80043007</strong>                                                           |                          Kan het certificaatbestand niet vinden in dezelfde map als het installatieprogramma.                          |                                 Pak alle bestanden uit voordat u de installatie start. Wijzig of verplaats de uitgepakte bestanden niet: alle bestanden moeten aanwezig zijn in dezelfde map, anders mislukt de installatie. Zie [Installeer de Windows-pc-client met Microsoft Intune](/intune-classic/deploy-use/install-the-windows-pc-client-with-microsoft-intune) voor meer informatie.                                  |
| <strong>0x8024D015</strong>, <strong>0x00240005</strong>, <strong>0x80070BC2</strong>, <strong>0x80070BC9</strong>, <strong>0x80CFD015</strong> |                       De software kan niet worden geïnstalleerd omdat een herstart van de client in behandeling is.                        |                                                                                                                                                                        Start de computer opnieuw op en voer de installatie van de clientsoftware opnieuw uit.                                                                                                                                                                        |
|                                                           <strong>0x80070032</strong>                                                           |                Een of meer vereisten voor het installeren van de clientsoftware zijn niet gevonden op de clientcomputer.                 |                            Zorg ervoor dat alle vereiste updates zijn geïnstalleerd op de clientcomputer en voer de installatie van de clientsoftware opnieuw uit. Zie [Vereisten voor de netwerkinfrastructuur voor Microsoft Intune](/intune-classic/get-started/network-infrastructure-requirements-for-microsoft-intune) voor meer informatie over de vereisten voor de installatie van de clientsoftware.                             |
|                                                           <strong>0x80043008</strong>                                                           |                                  De updateservice voor Microsoft Online Management kan niet worden gestart.                                  |                                                                                                                                               Neem contact op met Ondersteuning, zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).                                                                                                                                                |
|                                                           <strong>0x80043009</strong>                                                           |                                     De clientcomputer is al ingeschreven bij de service.                                      |                                                                                        U moet de clientcomputer buiten gebruik stellen voordat u deze opnieuw in de service kunt inschrijven. Zie [Retire devices from Microsoft Intune management](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management) (Apparaten buiten gebruik stellen vanuit Microsoft Intune-beheer) voor instructies.                                                                                         |
|                                                           <strong>0x8004300A</strong>                                                           |  (Stap 21) Fout treedt op wanneer het registratiepakket wordt geïmplementeerd in het groepsbeleidsobject dat moet worden geïnstalleerd in het gebruikersbereik en niet het computerbereik.   |                                                               Zorg ervoor dat het groepsbeleidsobject correct via GPSI op het computerbereik is gericht. Voor forumberichten over dit onderwerp, raadpleegt u dit [TechNet-Forum](https://social.technet.microsoft.com/Forums/en-US/bb9fa71c-c132-4954-abb0-70be8acbd925/failed-to-install-windows-intune?forum=microsoftintuneprod).                                                                |
|                                                           <strong>0x8004300B</strong>                                                           | Het installatiepakket voor de clientsoftware kan niet worden uitgevoerd omdat de versie van Windows die op de client wordt uitgevoerd, niet wordt ondersteund. |                                                               Intune biedt geen ondersteuning voor de versie van Windows die wordt uitgevoerd op de clientcomputer. Zie [Vereisten voor de netwerkinfrastructuur voor Microsoft Intune](/intune-classic/get-started/network-infrastructure-requirements-for-microsoft-intune) voor een lijst met ondersteunde besturingssystemen.                                                               |
|                                                             <strong>0xAB2</strong>                                                              |                           Windows Installer heeft geen toegang tot VBScript-runtime voor aangepaste actie.                            |                                                      Deze fout wordt veroorzaakt door een aangepaste actie die is gebaseerd op DLL-bestanden. Wanneer u problemen met de DLL oplost, moet u mogelijk gebruikmaken van de hulpprogramma's die worden beschreven in [Microsoft Ondersteuning KB198038: Useful Tools for Package and Deployment Issues (Nuttige hulpprogramma's voor pakket- en implementatieproblemen)](http://go.microsoft.com/fwlink/?LinkID=234255).                                                       |
|                                                           <strong>0x8004300f</strong>                                                           |           De software kan niet worden geïnstalleerd omdat de System Center Configuration Manager-client al is geïnstalleerd.            |                                                                                                                                                              Verwijder de Configuration Manager-client en voer de installatie van de clientsoftware opnieuw uit.                                                                                                                                                               |
|                                                           <strong>0x80043010</strong>                                                           |      De software kan niet worden geïnstalleerd omdat de Open Mobile Alliance Device Management-client (OMADM) al is geïnstalleerd.      |                                                                                                                                                                     Maak de inschrijving van de OMADM-client ongedaan en probeer de clientsoftware vervolgens opnieuw te installeren.                                                                                                                                                                     |

Als de installatieproblemen zich blijven voordoen, neemt u contact op met Ondersteuning, zoals wordt beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md). Zorg ervoor dat u het registratielogboek van de clientcomputer (in %*programfiles*%\Microsoft\OnlineManagement\Logs\Enrollment.log en %*userprofile*%\AppData\Local\Microsoft\OnlineManagement\Logs\Enrollment.log) en het Windows Update-logboek (%*windir*%\windowsupdate.log) bij de hand hebt om aan ondersteuningstechnici te laten zien.

## <a name="what-to-do-if-endpoint-protection-is-not-uninstalled-when-you-uninstall-the-client"></a>Wat te doen als Endpoint Protection niet is verwijderd wanneer u de client verwijdert

Soms kan de Host Protection-agent (Endpoint Protection) achter zijn gebleven nadat u de bovenstaande opdrachten hebt uitgevoerd. Als dit gebeurt, kunt u deze opdracht uitvoeren vanaf een opdrachtprompt met verhoogde bevoegdheden:

    ```
    "C:\Program Files\Managed Defender\Setup.exe" /x /q /s
    ```


### <a name="next-steps"></a>Volgende stappen
Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).
