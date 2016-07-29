---
title: Beheerdershandleiding voor de Rights Management-toepassing voor delen | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 07/21/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: d9992e30-f3d1-48d5-aedc-4e721f7d7c25
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a58d50b33db95570b43fe1ec0f76bdf490ddd024
ms.openlocfilehash: 164df467632b38f179d1c1192835f919641331a5


---


# Beheerdershandleiding voor de Rights Management-toepassing voor delen

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management, Windows 10, Windows 7 met SP1, Windows 8, Windows 8.1*


Gebruik de volgende informatie als u verantwoordelijk bent voor de Microsoft Rights Management-toepassing voor delen op een bedrijfsnetwerk, of als u meer technische informatie wilt dan wordt vermeld in de [gebruikershandleiding voor de Rights Management-toepassing voor delen](sharing-app-user-guide.md) of de [veelgestelde vragen over de Microsoft Rights Management-toepassing voor delen voor Windows](http://go.microsoft.com/fwlink/?LinkId=303971).

De RMS-toepassing voor delen is het meest geschikt voor gebruik met Azure RMS, omdat deze implementatieconfiguratie ondersteuning biedt voor het verzenden van beveiligde bijlagen naar gebruikers in een andere organisatie, en opties, zoals e-mailmeldingen en documenttracking met intrekken van de toegang.  Met een aantal beperkingen kan het echter ook worden gebruikt met de on-premises versie, AD RMS. Zie [Azure Rights Management en AD RMS vergelijken](../understand-explore/compare-azure-rms-ad-rms.md) voor een uitgebreide vergelijking van functies die worden ondersteund door Azure RMS en AD RMS. Zie [Migreren van AD RMS naar Azure Rights Management](../plan-design/migrate-from-ad-rms-to-azure-rms.md) als u over AD RMS beschikt en wilt migreren naar Azure RMS.

Zie [Technisch overzicht en beveiligingsdetails voor de Rights Management-toepassing](sharing-app-admin-guide-technical.md) voor aanvullende technische informatie met uitleg over het verschil tussen de beveiligingsniveaus (systeemeigen en algemeen), de ondersteunde bestandstypen en bestandsextensies, en het wijzigen van het standaardbeveiligingsniveau. 

## Automatische implementatie voor de Microsoft Rights Management-toepassing voor delen
De Windows-versie van de RMS-toepassing voor delen ondersteunt een scriptinstallatie, waardoor het geschikt is voor bedrijfsimplementaties.

De enige vereisten voor installatie zijn dat op de computers minimaal de versie Windows 7 Service Pack 1 wordt uitgevoerd en dat minimaal versie 4.0 van Microsoft Framework op de computers is geïnstalleerd. Als u Microsoft .NET Framework 4.0 moet installeren, kunt u [dit vanuit het Microsoft Downloadcentrum downloaden voor installatie](http://www.microsoft.com/download/details.aspx?id=17718).

### De RMS-toepassing voor delen downloaden voor automatische implementatie

1.  Ga in het Microsoft Downloadcentrum naar de pagina [Microsoft Rights Management-toepassing voor delen voor Windows](http://www.microsoft.com/download/details.aspx?id=40857) en klik op **Downloaden**.

2.  Selecteer en download de bestanden die u nodig hebt. Er zijn twee clientinstallatiepakketten: een voor Windows 64-bits (Microsoft Rights Management-toepassing voor delen x64.zip) en een voor Windows 32-bits (Microsoft Rights Management-toepassing voor delen x86.zip).

3.  Pak de gecomprimeerde installatiepakketten uit door er bijvoorbeeld op te dubbelklikken. Kopieer de uitgepakte bestanden naar een netwerklocatie waartoe clientcomputers toegang hebben.

De installatiepakketten voor de RMS-toepassing voor delen ondersteunen verschillende implementatiescenario's waaronder de volgende:

|Beschrijving|Implementatiescenario|
|---------------|-----------------------|
|Microsoft Online-aanmeldhulp|Office 2010 en Azure RMS<br /><br />Office 2013 en Azure RMS als u de [update van 9 juni 2015 voor Office 2013](https://support.microsoft.com/kb/3054853) niet hebt geïnstalleerd (KB3054853)|
|Hotfix voor Office (KB 2596501)|Office 2010 en Azure RMS<br /><br />Office 2010 en Active Directory RMS|
|Hotfix zodat AD RMS-client 1.0 kan worden gebruikt met Azure RMS (KB 2843630)|Office 2010 en Azure RMS<br /><br />Office 2010 en Active Directory RMS|
|AD RMS-client en de RMS-toepassing voor delen|Office 2016 of Office 2013 en Azure RMS of Active Directory RMS<br /><br />Office 2010 en Azure RMS<br /><br />Office 2010 en Active Directory RMS<br /><br />Alleen RMS-toepassing voor delen en Office-invoegtoepassing|
|Office-invoegtoepassing voor het lint|Office 2016 of Office 2013 en Azure RMS of Active Directory RMS<br /><br />Office 2010 en Azure RMS<br /><br />Office 2010 en Active Directory RMS<br /><br />Alleen RMS-toepassing voor delen en Office-invoegtoepassing|
|Azure Active Directory Rights Management-hulpprogramma voor systeemvoorbereiding|Office 2010 en Azure RMS|
Gebruik de volgende procedures om de opdrachten op te sporen die zijn vereist voor de implementatie van de RMS-toepassing voor delen voor deze implementatiescenario's:

-   **Office 2016 of Office 2013 en Azure RMS of Active Directory RMS**

    Uw gebruikers werken met Office 2016 of Office 2013, uw organisatie gebruikt Azure RMS of Active Directory RMS en gebruikers werken samen met andere organisaties die Azure RMS of Active Directory RMS gebruiken.

-   **Office 2010 en Azure RMS**

    Uw gebruikers werken met Office 2010, uw organisatie gebruikt Azure RMS en gebruikers werken samen met andere organisaties die Azure RMS of Active Directory RMS gebruiken.

-   **Office 2010 en Active Directory RMS**

    Uw gebruikers werken met Office 2010, uw organisatie gebruikt AD RMS en gebruikers werken samen met andere organisaties die Azure RMS gebruiken.

-   **Alleen RMS-toepassing voor delen en Office-invoegtoepassing**

    Uw gebruikers werken met Office 2016, Office 2013 of Office 2010, uw organisatie gebruikt AD RMS en gebruikers hoeven niet samen te werken met andere organisaties die Azure RMS gebruiken. Met deze installatie kunt u alleen de toepassing voor delen en de Office-invoegtoepassing installeren.

> [!NOTE]
> Als uw organisatie AD RMS gebruikt, kunnen uw gebruikers in deze scenario's beveiligde inhoud ontvangen van andere organisaties die Azure RMS gebruiken. Uw gebruikers kunnen echter geen beveiligde inhoud verzenden naar gebruikers in organisaties die Azure RMS gebruiken. Als uw organisatie echter Azure RMS uitvoert, dan kunnen gebruikers beveiligde inhoud van andere organisaties verzenden en ontvangen.

De computer moet eerst opnieuw starten om de installatie voor elke procedure te voltooien. U kunt het automatisch opnieuw opstarten initiëren met een opdracht als **shutdown /i**.

### De RMS-toepassing voor delen voor Office 2016 of Office 2013 en Azure RMS of Active Directory RMS implementeren

-   Voer de volgende opdracht met verhoogde bevoegdheden uit op alle computers waar u de RMS-toepassing voor delen en gerelateerde onderdelen wilt installeren:

    ```
    setup.exe /s
    ```

Zie de sectie [Controleren of de installatie is geslaagd](#verifying-installation-success) om te controleren of de toepassing is geïnstalleerd.

### De RMS-toepassing voor delen voor Office 2010 en Azure RMS

1.  U moet de globale beheerder zijn voor uw Office 365- of Azure Active Directory-tenant zodat u de URL voor de certificeringsservice van uw organisatie kunt ophalen door het Azure Active Directory Rights Management-hulpprogramma voor systeemvoorbereiding uit te voeren. U hoeft dit hulpprogramma slechts een keer uit te voeren op één computer. Gebruik de certificeringsservice-url tijdens de installatie van de RMS-toepassing voor delen op elke computer:

    1.  Aanmelden bij een computer met een lokaal beheerdersaccount.

    2.  [Download en installeer de Microsoft Online-aanmeldhulp](http://www.microsoft.com/download/details.aspx?id=28177) op die computer.

    3.  Voer de volgende opdracht uit om de certificeringsservice-url op het scherm weer te geven, welke u vervolgens kunt kopiëren en opslaan voor de volgende stap:

        -   Voor Windows 8.1 en Windows 8, 64 bitsversie:

            ```
            x64\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        -   Voor Windows 8.1 en Windows 8, 32 bitsversie:

            ```
            X86\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        -   Voor Windows 7, 64 bitsversie:

            ```
            x64\win7\aadrmprep.exe /findCertificationUrl /logfile "<log file path and name>"
            ```

        > [!NOTE]
        > Met deze opdracht moet u mogelijk uw referenties invoeren voor Azure. Als de computer niet is toegevoegd aan een domein, dan wordt u gevraagd om dit te doen. Als de computer is toegevoegd aan een domein, kan het hulpprogramma mogelijk in de cache opgeslagen referenties gebruiken.

2.  Voer de volgende opdracht met verhoogde bevoegdheden één keer uit op elke computer waarop u de RMS-toepassing voor delen installeert:

    ```
    setup.exe /s /configureO2010Admin /certificationUrl <certification_url>
    ```

3.  Op elke computer waarop u de RMS-toepassing voor delen wilt installeren, moet elke gebruiker de volgende opdracht uitvoeren (heeft geen verhoogde bevoegdheden nodig). Er zijn verschillende manieren om dit te bereiken, zoals gebruikers vragen om de opdracht uit te voeren (door bijvoorbeeld een koppeling in een e-mailbericht te plaatsen of een koppeling op een helpdeskportal) of u kunt deze toevoegen aan hun aanmeldingsscript:

    ```
    bin\RMSSetup.exe /configureO2010Only
    ```

Zie de sectie [Controleren of de installatie is geslaagd](#verifying-installation-success) om te controleren of de toepassing is geïnstalleerd.

### De RMS-toepassing voor delen voor Office 2010 en Active Directory RMS implementeren

1.  Voer de volgende opdracht met verhoogde bevoegdheden uit op elke computer waarop u de RMS-toepassing voor delen installeert:

    ```
    setup.exe /s /configureO2010Admin
    ```

2.  Op elke computer waarop u de RMS-toepassing voor delen wilt installeren, moeten gebruikers de volgende opdracht uitvoeren (heeft geen verhoogde bevoegdheden nodig). Er zijn verschillende manieren om dit te bereiken, zoals gebruikers vragen om de opdracht uit te voeren (door bijvoorbeeld een koppeling in een e-mailbericht te plaatsen of een koppeling op een helpdeskportal) of u kunt deze toevoegen aan hun aanmeldingsscript:

    -   Voor Windows 10, Windows 8.1 en Windows 8, 64 bitsversie:

        ```
        x64\aadrmprep.exe /configureO2010
        ```

    -   Voor Windows 10, Windows 8.1 en Windows 8, 32 bitsversie:

        ```
        X86\aadrmprep.exe /configureO2010
        ```

    -   Voor Windows 7, 64 bitsversie:

        ```
        x64\win7\aadrmpep.exe /configureO2010
        ```

Zie de sectie [Controleren of de installatie is geslaagd](#verifying-installation-success) om te controleren of de toepassing is geïnstalleerd.

### Alleen de RMS-toepassing voor delen en de Office-invoegtoepassing installeren

1.  De AD RMS-client en de RMS-toepassing voor delen met de volgende opdracht installeren:

    -   Voor 64-bits Windows:

        ```
        x64\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "<log file path and name>"
        ```

    -   Voor de 32 bitsversie van Windows:

        ```
        X86\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "<log file path and name>"
        ```

    Bijvoorbeeld: `\\server5\apps\rms\x64\setup_ipviewer.exe /norestart /quiet /msicl "MSIRESTARTMANAGERCONTROL=Disable" /log "C:\Log files\ipviewerinstall.log"`

2.  De Office-invoegtoepassing installeren met de volgende opdrachten:

    -   Voor 64-bits versie van Office:

        ```
        msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x64\Setup64.msi" /L*v "<log file path and name>"
        ```

    -   Voor de 32 bitsversie van Office:

        ```
        msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x86\Setup.msi" /L*v "<log file path and name>"
        ```

    Bijvoorbeeld: `\\server5\apps\rms\msiexec.exe /norestart /quiet MSIRESTARTMANAGERCONTROL=Disable /i "x64\Setup64.msi" /L*v "C:\Log files\rmsofficeinstall.log"`

Zie de sectie [Controleren of de installatie is geslaagd](#verifying-installation-success) om te controleren of de toepassing is geïnstalleerd.

## Installatie verifiëren
Met de logboekbestanden van de installatie kunt u controleren of deze is geïnstalleerd.

### Controleren of de RMS-toepassing voor delen voor Office 2016 of Office 2013 en Azure RMS of Active Directory RMS is geïnstalleerd

-   Als u wilt controleren of de Setup.exe-opdracht goed is uitgevoerd, gaat u op elke computer naar het installatielogboekbestand **RMInstaller.log** in de map *%temp%\RMS_installer_&lt;guid&gt;* en controleert u de afsluitcode.

    Een geslaagde installatie heeft een afsluitcode 0. Elk ander getal geeft een mislukte installatie aan.

    Voorbeeld van een logboekbestandnaam: **C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0\RMInstaller.log**

### Controleren of de RMS-toepassing voor delen voor Office 2010 en Azure RMS is geïnstalleerd

1.  Als u wilt controleren of de Setup.exe-opdracht goed is uitgevoerd, gaat u op elke computer naar het installatielogboekbestand **RMInstaller.log** in de map *%temp%\RMS_installer_&lt;guid&gt;* en controleert u de afsluitcode.

    Een geslaagde installatie heeft een afsluitcode 0. Elk ander getal geeft een mislukte installatie aan.

    Voorbeeld van een logboekbestandnaam: **C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0**

2.  Als de gebruiker wil controleren of de RMSSetup.exe-opdracht goed is uitgevoerd, moet deze de volgende bestanden hebben gemaakt in de map *%localappdata%\microsoft\drm*:

    -   CERT-Machine-2048.drm

    -   CERT-Machine.drm

    -   CLC-&#42;.drm

    -   GIC-&#42;.drm

    Voorbeeld van een CLC-&#42;.drm-bestand:

    **CLC-alice@isvtenant999.onmicrosoft.com-{1b9cfccf;k5b11;k4a10;kac15;k29b2b6980f4c}.drm**

### De installatie van de RMS-toepassing voor delen voor Office 2010 en Active Directory RMS controleren

1.  Als u wilt controleren of de Setup.exe-opdracht goed is uitgevoerd, gaat u op elke computer naar het installatielogboekbestand in de map *%temp%\RMS_installer_&lt;guid&gt;* en controleert u de afsluitcode.

    Een geslaagde installatie heeft een afsluitcode 0. Elk ander getal geeft een mislukte installatie aan.

    Voorbeeld van een logboekbestandnaam: **C:\temp\RMS_Installer_9352fc91-1982-43bf-958a-2ef1fe9c2ed0**

2.  Als u wilt controleren of de aadrmprep.exe-opdracht goed is uitgevoerd, zoekt u op elke computer in het installatielogboekbestand naar de volgende tekst: **aadrmprep.exe exited with status SUCCESS**

    > [!NOTE]
    > Soms wordt deze installatie twee keer uitgevoerd. De eerste poging is mislukt en de tweede geslaagd.

    Als u handmatig de registerwijzigingen wilt controleren die dit hulpprogramma maakt, dan zijn ze als volgt:

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\Federation]

        "FederationHomeRealm"="urn:HostedRmsOnlineService:Certification"

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSDRM\Federation]

        "FederationHomeRealm"="urn:HostedRmsOnlineService:Certification"

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSDRM\ServiceLocation\Activation]

        @="&lt;certificerings-URL&gt;"

    -   [HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\14.0\Common\DRM]

        DefaultUser = "&lt;standaard_gebruiker&gt;"

### Alleen de installatie van de RMS-toepassing voor delen en de Office-invoegtoepassing verifiëren

1.  Als u wilt controleren of de Setup_ipviewer.exe-opdracht juist is uitgevoerd, zoekt u in het installatielogboekbestand naar de volgende tekst: **Installation success or error status: 0**

    Voorbeeldregels van een geslaagde installatie:

    **MSI (s) (F0:B8) [14:19:57:854]: Product: Active Directory Rights Management Services Client 2.1 -- Installation completed successfully.**

    **MSI (s) (F0:B8) [14:19:57:854]: Windows Installer installed the product. Product Name: Active Directory Rights Management Services Client 2.1. Product Version: 1.0.1179.1. Product Language: 1033. Manufacturer: Microsoft Corporation. Installation success or error status: 0.**

2.  Als u wilt controleren of de Office-invoegtoepassing is geïnstalleerd, zoekt u op elke computer in het installatielogboekbestand naar de volgende tekst: **Installation success or error status: 0**

    Voorbeeldregels van een geslaagde installatie:

    **MSI (s) (9C:88) [18:49:04:007]: Product: Microsoft RMS Office Addins -- Installation completed successfully.**

    **MSI (s) (9C:88) [18:49:04:007]: Windows Installer installed the product. Product Name: Microsoft RMS Office Addins. Product Version: 1.0.7. Product Language: 1033. Manufacturer: Microsoft. Installation success or error status: 0.**

## Opdrachten verwijderen
Niet alle installatieopdrachten die zijn vereist voor deze implementaties ondersteunen een opdracht verwijderen. U kunt de AD RMS-client, de toepassing voor delen en de Office-invoegtoepassing verwijderen. Gebruik de volgende opdrachten om deze onderdelen te verwijderen.

### De AD RMS-client en de RMS-toepassing voor delen verwijderen

-   Gebruik de volgende opdrachten:

    -   Voor 64-bits Windows:

        ```
        x64\setup_ipviewer.exe /uninstall /quiet
        ```

    -   Voor de 32 bitsversie van Windows:

        ```
        x86\setup_ipviewer.exe /uninstall /quiet
        ```

### De Office-invoegtoepassing verwijderen

-   Gebruik de volgende opdrachten:

    -   Voor 64-bits versie van Office:

        ```
        msiexec /x \x64\Setup[64].msi /quiet
        ```

    -   Voor de 32 bitsversie van Office:

        ```
        msiexec /x \x86\Setup.msi /quiet
        ```

## Onderdrukken van automatische updates
Standaard krijgen gebruikers een melding als er een nieuwere versie van de RMS-toepassing voor delen is en wordt ze gevraagd om deze te downloaden. U kunt deze melding onderdrukken door de volgende registersleutel te bewerken:

1.  Navigeer naar **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC** en als deze niet al aanwezig is, maakt u een nieuwe sleutel met de naam **RmsSharingApp**.

2.  Selecteer **RmsSharingApp**, maak een nieuwe DWORD-waarde van **AllowUpdatePrompt** en stel de waarde in op **0**.

Omdat de RMS-toepassing voor delen niet wordt ondersteund door WSUS, kunt u de volgende techniek gebruiken om nieuwe versies van de RMS-toepassing voor delen te testen voordat u deze implementeert bij alle gebruikers:

1.  Voer een script uit op alle computers van de gebruikers om automatische updates te onderdrukken. Voer dit script niet uit op computers waar beheerders nieuw versies op testen.

2.  Wanneer een nieuwe versie beschikbaar is, kunnen beheerders het downloaden en testen.

3.  Wanneer het testen is voltooid en eventuele problemen zijn opgelost, implementeert u de nieuwste versie bij alle gebruikers met de automatische implementatie-instructies in deze handleiding.

## Alleen Azure RMS: documenttracking configureren
Als u beschikt over een [abonnement dat ondersteuning biedt voor documenttracking](https://technet.microsoft.com/dn858608), wordt de site voor documenttracking standaard ingeschakeld voor alle gebruikers in uw organisatie.  Documenttracking vermeldt gegevens zoals e-mailadressen van de personen die hebben geprobeerd om toegang te krijgen tot beveiligde documenten die door gebruikers worden gedeeld, wanneer zij hebben geprobeerd om deze te openen en de locatie van deze personen. Als het weergeven van deze informatie niet is toegestaan in uw organisatie vanwege privacyregelgeving, kunt u de toegang tot de site voor documenttracking uitschakelen met de cmdlet [Disable-AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623032). U kunt de toegang tot de site op elk gewenst moment weer inschakelen met de cmdlet [Enable-AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623037) en u kunt controleren of de toegang momenteel is in- of uitgeschakeld met de cmdlet [Get-AadrmDocumentTrackingFeature](http://go.microsoft.com/fwlink/?LinkId=623037).

Als u deze cmdlets wilt uitvoeren, moet u ten minste over versie **2.3.0.0** van de Azure RMS-module voor Windows PowerShell beschikken.  Zie [Windows PowerShell voor Azure Rights Management installeren](../deploy-use/install-powershell.md) voor installatie-instructies.

> [!TIP]
> Als u de module eerder hebt gedownload en geïnstalleerd, controleert u het versienummer door de volgende opdracht uit te voeren: `(Get-Module aadrm –ListAvailable).Version`

De volgende URL's worden gebruikt voor documenttracking en moeten worden toegestaan (voeg ze bijvoorbeeld toe aan uw vertrouwde sites als u Internet Explorer met uitgebreide beveiliging gebruikt):

-   https://&#42;.azurerms.com

-   https://ecn.dev.virtualearth.net

    > [!NOTE]
    > Deze URL is voor Bing-kaarten.

-   https://&#42;.microsoftonline.com

-   https://&#42;.microsoftonline-p.com

## Alleen AD RMS: ondersteuning voor meerdere e-maildomeinen in uw organisatie
Als u AD RMS gebruikt en gebruikers in uw organisatie meerdere e-maildomeinen hebben, moet u als gevolg van een fusie of overname mogelijk de volgende registersleutel bewerken:

1.  Navigeer naar **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC** en als deze niet al aanwezig is, maakt u een nieuwe sleutel met de naam **RmsSharingApp**.

2.  Selecteer **RmsSharingApp**, maak een nieuwe waarde met meerdere tekenreeksen met de naam **FederatedDomains** en voeg de domeinen en alle subdomeinen vervolgens toe die uw organisatie gebruikt. Jokertekens worden niet ondersteund.

    Bijvoorbeeld: het bedrijf Coho Vineyard &amp; Winery heeft een standaarde-maildomein **cohovineyardandwinery.com**, maar als gevolg van fusies gebruiken ze ook de e-maildomeinen **cohowinery.com**, **eastcoast.cohowinery.com** en **cohovineyard**. De beheerder voert als waarde voor **FederatedDomains** het volgende in: **cohowinery.com; eastcoast.cohowinery.com; cohovineyard**

Als u niets in dit register wijzigt, kunnen gebruikers mogelijk geen inhoud gebruiken die beveiligd is door gebruikers in hun organisatie. Deze bewerking van het register is niet nodig als u Azure RMS gebruikt.


## Volgende stappen
Zie [Technisch overzicht voor de Rights Management-toepassing voor delen](sharing-app-admin-guide-technical.md) voor aanvullende technische informatie met uitleg over het verschil tussen de beveiligingsniveaus (systeemeigen en algemeen), de ondersteunde bestandstypen en bestandsextensies, en het wijzigen van het standaardbeveiligingsniveau.




<!--HONumber=Jul16_HO3-->


