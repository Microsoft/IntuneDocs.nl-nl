---
title: Sjablonen vernieuwen | Azure RMS
description: Als u Azure RMS gebruikt, worden sjablonen automatisch gedownload naar clientcomputers, zodat gebruikers deze in hun toepassingen kunnen selecteren. U moet mogelijk echter extra stappen uitvoeren als u de sjablonen wilt wijzigen.
author: cabailey
manager: mbaldwin
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 8c2064f0-dd71-4ca5-9040-1740ab8876fb
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 024a29d7c7db2e4c0578a95c93e22f8e7a5b173e
ms.openlocfilehash: 2339643120b9e9ee24d046bf5620f68fee88b7c9


---


# Sjablonen voor gebruikers vernieuwen

>*Van toepassing op: Azure Rights Management, Office 365*

Als u Azure RMS gebruikt, worden sjablonen automatisch gedownload naar clientcomputers, zodat gebruikers deze in hun toepassingen kunnen selecteren. U moet mogelijk echter extra stappen uitvoeren als u de sjablonen wilt wijzigen:

|Toepassing of service|Hoe sjablonen na wijziging worden vernieuwd|
|--------------------------|---------------------------------------------|
|Exchange Online|Handmatige configuratie is vereist om sjablonen te vernieuwen.<br /><br />Bekijk het volgende gedeelte voor de configuratiestappen: [Alleen Exchange Online: Exchange configureren om gewijzigde, aangepaste sjablonen te downloaden](#exchange-online-only-how-to-configure-exchange-to-download-changed-custom-templates).|
|Office 365|Automatisch vernieuwd - geen extra stappen vereist.|
|Office 2016 en Office 2013<br /><br />RMS-toepassing voor delen voor Windows|Automatisch vernieuwd - volgens een schema:<br /><br />Voor deze latere versies van Office: de standaardvernieuwingsinterval is elke zeven dagen.<br /><br />Voor de RMS-toepassing voor delen voor Windows: vanaf versie 1.0.1784.0 is de standaardvernieuwingsinterval om de dag. Eerdere versies hebben een standaardvernieuwingsinterval van zeven dagen.<br /><br />Als u sneller wilt vernieuwen dan gepland, raadpleegt u dit gedeelte: [Office 2016, Office 2013 en RMS-toepassing voor delen voor Windows: een gewijzigde, aangepaste sjabloon geforceerd vernieuwen](#office-2016-office-2013-and-rms-sharing-application-for-windows-how-to-force-a-refresh-for-a-changed-custom-template).|
|Office 2010|Vernieuwd wanneer gebruikers zich aanmelden.<br /><br />Als u een vernieuwing wilt forceren, moet u gebruikers vragen of dwingen zich af te melden en zich opnieuw aan te melden. Of raadpleeg het volgende gedeelte [Alleen Office 2010: een gewijzigde, aangepaste sjabloon geforceerd vernieuwen](#office-2010-only-how-to-force-a-refresh-for-a-changed-custom-template).|
Op mobiele apparaten waarop de RMS-toepassing voor delen wordt gebruikt, worden sjablonen automatisch gedownload (en zo nodig vernieuwd) zonder dat aanvullende configuratie vereist is.

## Alleen Exchange Online: Exchange configureren om gewijzigde, aangepaste sjablonen te downloaden
Als u Information Rights Management (IRM) voor Exchange Online al hebt geconfigureerd, worden aangepaste sjablonen pas naar gebruikers gedownload wanneer u de volgende wijzigingen aanbrengt met Windows PowerShell Exchange Online.

> [!NOTE]
> Zie voor meer informatie over het gebruik van Windows PowerShell in Exchange Online [PowerShell gebruiken in combinatie met Exchange Online](https://technet.microsoft.com/library/jj200677%28v=exchg.160%29.aspx).

U moet deze procedure uitvoeren telkens wanneer u een sjabloon wijzigt.

### Sjablonen voor Exchange Online bijwerken

1.  Maak verbinding met de service via Windows PowerShell in Exchange Online:

    1.  Geef uw gebruikersnaam en wachtwoord voor Office 365 op:

        ```
        $Cred = Get-Credential
        ```

    2.  Maak verbinding met de Exchange Online-service door de volgende twee opdrachten uit te voeren:

        ```
        $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell/ -Credential $Cred -Authentication Basic –AllowRedirection
        ```

        ```
        Import-PSSession $Session
        ```

2.  Gebruik de cmdlet [Import-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/jj200724%28v=exchg.160%29.aspx) om uw Trusted Publishing Domain (TPD) opnieuw te importeren uit Azure RMS:

    ```
    Import-RMSTrustedPublishingDomain -Name "<TPD name>" -RefreshTemplates -RMSOnline
    ```
    Als bijvoorbeeld uw TPD-naam **RMS Online RMS - 1** is (een gebruikelijke naam voor veel organisaties), dan geeft u het volgende op: **Import-RMSTrustedPublishingDomain -Name "RMS Online - 1" -RefreshTemplates -RMSOnline**

    > [!NOTE]
    > U kunt uw TPD-naam controleren met de cmdlet [Get-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/jj200707%28v=exchg.160%29.aspx).

3.  Als u wilt controleren of de sjablonen zijn geïmporteerd, wacht u een paar minuten, voert u de cmdlet [Get-RMSTemplate](http://technet.microsoft.com/library/dd297960%28v=exchg.160%29.aspx) uit en stelt u het type in op Alle. Bijvoorbeeld:

    ```
    Get-RMSTemplate -TrustedPublishingDomain "RMS Online - 1" -Type All
    ```
    > [!TIP]
    > Het is nuttig een kopie van de uitvoer te bewaren, zodat u eenvoudig de sjabloonnamen of GUID's kunt kopiëren als u een sjabloon later archiveert.

4.  Voor elke geïmporteerde sjabloon die u beschikbaar wilt hebben in de Outlook Web App, moet u de cmdlet [Set RMSTemplate](http://technet.microsoft.com/library/hh529923%28v=exchg.160%29.aspx) gebruiken en het type instellen op Gedistribueerd:

    ```
    Set-RMSTemplate -Identity "<name  or GUID of the template>" -Type Distributed
    ```
    Omdat Outlook Web Access de UI 24 uur in het cachegeheugen opslaat, zien gebruikers de nieuwe sjabloon mogelijk pas een dag later.

Als u een sjabloon (aangepast of standaard) archiveert en Exchange Online gebruikt in combinatie met Office 365, blijven gebruikers bovendien de gearchiveerde sjablonen zien als ze werken met de Outlook Web App of met mobiele apparaten die gebruikmaken van het Exchange ActiveSync-protocol.

Om ervoor te zorgen dat gebruikers deze sjablonen niet meer zien, maakt u verbinding met de service via Windows PowerShell in Exchange Online en gebruikt u vervolgens de cmdlet [Set-RMSTemplate](http://technet.microsoft.com/library/hh529923%28v=exchg.160%29.aspx) door de volgende opdracht uit te voeren:

```
Set-RMSTemplate -Identity "<name or GUID of the template>" -Type Archived
```

## Office 2016, Office 2013 en RMS-toepassing voor delen voor Windows: een vernieuwing voor een aangepaste, gewijzigde sjabloon forceren
Door het register op de computers met Office 2016, Office 2013 of de Rights Management-toepassing (RMS) voor delen voor Windows te bewerken, kunt u de automatische planning wijzigen, zodat gewijzigde sjablonen vaker dan de standaardwaarde op computers worden vernieuwd. U kunt ook een onmiddellijke vernieuwing forceren door de bestaande gegevens in een registerwaarde te verwijderen.

> [!WARNING]
> Als u de Registry Editor onjuist gebruikt, kunt u ernstige problemen veroorzaken waardoor u mogelijk het besturingssysteem opnieuw zult moeten installeren. Microsoft biedt geen garantie dat u problemen kunt oplossen die veroorzaakt worden door onjuist gebruik van de Registry Editor. Gebruik de Registry Editor op eigen risico.

### De automatische planning wijzigen

1.  Gebruik een registereditor om een van de volgende registerwaarden te maken en in te stellen:

    - Een updatefrequentie in dagen instellen (minimaal één dag): maak een nieuwe registerwaarde met de naam **TemplateUpdateFrequency** en definieer een integerwaarde voor de gegevens waarmee de frequentie in dagen voor het downloaden van wijzigingen naar een gedownloade sjabloon wordt vastgelegd. Gebruik de volgende informatie om het registerpad voor het maken van deze nieuwe registerwaarde te vinden.

        **Registerpad:** HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC

        **Type:** REG_DWORD

        **Waarde:** TemplateUpdateFrequency

    - Een updatefrequentie in seconden instellen (minimaal één seconde): maak een nieuwe registerwaarde met de naam **TemplateUpdateFrequencyInSeconds** en definieer een integerwaarde voor de gegevens waarmee de frequentie in seconden voor het downloaden van wijzigingen naar een gedownloade sjabloon wordt vastgelegd. Gebruik de volgende informatie om het registerpad voor het maken van deze nieuwe registerwaarde te vinden.

        **Registerpad:** HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC

        **Type:** REG_DWORD

        **Waarde:** TemplateUpdateFrequencyInSeconds

    Zorg ervoor dat u slechts één van deze registerwaarden maakt en instelt, niet beide. Als beide waarden aanwezig zijn, wordt **TemplateUpdateFrequency** genegeerd.

2.  Als u een onmiddellijke vernieuwing van de sjablonen wilt forceren, gaat u naar de volgende procedure. Anders moet u uw Office-toepassingen en instanties van de Bestandenverkenner opnieuw starten.

### Onmiddellijk vernieuwen forceren

1.  Verwijder met een registereditor de gegevens voor de waarde **LastUpdatedTime**. De gegevens geven bijvoorbeeld **2015-04-20T15:52** weer. Verwijder dan 2015-04-20T15:52, zodat er geen gegevens worden weergegeven. Gebruik de volgende informatie om het registerpad te vinden voor het verwijderen van deze registerwaardgegevens.

    **Registerpad:** HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC\\<*MicrosoftRMS_FQDN*>\Template

    **Type:** REG_SZ

    **Waarde:** LastUpdatedTime

    > [!TIP]
        > In het registerpad verwijst <*MicrosoftRMS_FQDN*> naar de FQDN-naam van uw Microsoft RMS-service. Als u deze waarde wilt controleren, doet u het volgende:

    > 1.  Voer de cmdlet [Get-AadrmConfiguration](https://msdn.microsoft.com/library/windowsazure/dn629410.aspx) voor Azure RMS uit. Zie [Windows PowerShell voor Azure Rights Management installeren](install-powershell.md) als u de Windows PowerShell-module voor Azure RMS nog niet hebt geïnstalleerd.
    > 2.  Identificeer op grond van de uitvoer de waarde van **LicensingIntranetDistributionPointUrl**.
    > 
    >     Bijvoorbeeld: **LicensingIntranetDistributionPointUrl : https://5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com/_wmcs/licensing**
    > 3.  Verwijder **https://** uit de waarde en **/_wmcs/licensing** uit deze tekenreeks. De resterende waarde is de FQDN van uw Microsoft RMS-service. In het voorbeeld zou de FQDN van de Microsoft RMS-service de volgende waarde hebben:
    > 
    >     **5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com**

2.  Verwijder de volgende map en alle bestanden die de map bevat: **%localappdata%\Microsoft\MSIPC\Templates**

3.  Start uw Office-toepassingen en instanties van de Bestandenverkenner opnieuw op.

## Alleen Office 2010: een gewijzigde, aangepaste sjabloon geforceerd vernieuwen
Door het register op de computers met Office 2010 te bewerken, kunt u een waarde instellen zodat gewijzigde sjablonen op computers worden vernieuwd zonder erop te hoeven wachten dat gebruikers zich afmelden en opnieuw aanmelden. U kunt ook een onmiddellijke vernieuwing forceren door de bestaande gegevens in een registerwaarde te verwijderen.

> [!WARNING]
> Als u de Registry Editor onjuist gebruikt, kunt u ernstige problemen veroorzaken waardoor u mogelijk het besturingssysteem opnieuw zult moeten installeren. Microsoft biedt geen garantie dat u problemen kunt oplossen die veroorzaakt worden door onjuist gebruik van de Registry Editor. Gebruik de Registry Editor op eigen risico.

### De updatefrequentie wijzigen

1.  Maak met een registereditor een nieuwe registerwaarde met de naam **UpdateFrequency** en definieer een integerwaarde voor de gegevens die de frequentie in dagen aangeeft voor het downloaden van wijzigingen in een gedownloade sjabloon. Gebruik de volgende tabel om het registerpad voor het maken van deze nieuwe registerwaarde te vinden.

    **Registerpad:** HKEY_CURRENT_USER\Software\Microsoft\MSDRM\TemplateManagement

    **Type:** REG_DWORD

    **Waarde:** UpdateFrequency

2.  Als u een onmiddellijke vernieuwing van de sjablonen wilt forceren, gaat u naar de volgende procedure. Start anders uw Office-toepassingen nu opnieuw op.

### Onmiddellijk vernieuwen forceren

1.  Verwijder met een registereditor de gegevens voor de waarde **LastUpdatedTime**. De gegevens geven bijvoorbeeld **2015-04-20T15:52** weer. Verwijder dan 2015-04-20T15:52, zodat er geen gegevens worden weergegeven. Gebruik de volgende tabel om het registerpad te vinden voor het verwijderen van deze registerwaardegegevens.

    **Registerpad:** HKEY_CURRENT_USER\Software\Microsoft\MSDRM\TemplateManagement

    **Type:** REG_SZ

    **Waarde:** lastUpdatedTime


2.  Verwijder de volgende map en alle bestanden die de map bevat: **%localappdata%\Microsoft\MSIPC\Templates**

3.  Start uw Office-toepassingen opnieuw op.

## Zie ook
[Aangepaste sjablonen configureren voor Azure Rights Management](configure-custom-templates.md)


<!--HONumber=Aug16_HO4-->


