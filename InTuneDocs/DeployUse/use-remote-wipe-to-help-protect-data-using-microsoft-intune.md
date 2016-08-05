---
title: Wissen op afstand gebruiken om gegevens te beveiligen | Microsoft Intune
description: Intune biedt mogelijkheden tot selectief wissen en volledig wissen om zo gevoelige bedrijfsgegevens te kunnen verwijderen en om toegang tot veel bedrijfsresources onmogelijk te maken.
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8519e411-3d48-44eb-9b41-3e4fd6a93112
ms.reviewer: lancecra
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e9cbf5858cc4e860b540f421b6d463b8e7a429cf
ms.openlocfilehash: c61fd1070f84f359ac6abe9ff48e51d2787c4eb4


---

# Uw gegevens beveiligen met volledig wissen of selectief wissen met Microsoft Intune
Net zoals u apparaten afschrijft, moet of wilt u op een bepaald moment ook op pc's en mobiele apparaten geïmplementeerde [apps buiten gebruik stellen](retire-apps-using-microsoft-intune.md) omdat u deze niet langer nodig hebt. Het kan ook voorkomen dat u bedrijfsgegevens van een apparaat wilt verwijderen. Intune biedt hiervoor de mogelijkheid om selectief of volledig te wissen. Omdat mobiele apparaten gevoelige bedrijfsgegevens kunnen bevatten en toegang bieden tot veel bedrijfsbronnen, kunt u vanuit Intune een opdracht geven tot op afstand wissen van een apparaat dat wordt vermist of is gestolen. Ook gebruikers kunnen vanuit Intune een opdracht tot wissen van hun apparaat geven, mits dit een eigen apparaat is dat in Intune is ingeschreven.

  > [!NOTE]
  > Dit onderwerp gaat alleen over het wissen van apparaten die worden beheerd door Intune. U kunt ook [Azure Preview Portal](https://portal.azure.com) gebruiken om [bedrijfsgegevens uit apps te wissen](wipe-managed-company-app-data-with-microsoft-intune.md).

## Volledig wissen


Met **Volledig wissen** worden de fabrieksinstellingen van een apparaat hersteld, en worden alle bedrijfs- en gebruikersgegevens en -instellingen verwijderd. Het apparaat wordt uit Intune verwijderd. Volledig wissen is nuttig voor het opnieuw instellen van een apparaat, wanneer het apparaat aan een nieuwe gebruiker wordt gegeven of wanneer het apparaat is verloren of gestolen.  **Wees voorzichtig bij het selecteren van Volledig wissen. De gegevens op het apparaat kunnen niet worden hersteld**.

> [!Warning]
> Windows 10 RTM-apparaten (dat wil zeggen; ouder dan Windows-10 versie 1511) met minder dan 4 GB aan RAM-geheugen, kunnen ontoegankelijk worden als ze worden gewist. Voor toegang tot een Windows 10-apparaat dat niet meer reageert, kunt u het apparaat vanaf een USB-station opstarten of een vergelijkbare tijdelijke oplossing toepassen.

## Selectief wissen

Met **Selectief wissen** worden bedrijfsgegevens van een apparaat verwijderd, inclusief MAM-gegevens (Mobile App Management-gegevens), indien van toepassing, instellingen en e-mailprofielen. Bij Selectief wissen blijven de persoonlijke gegevens van de gebruiker op het apparaat behouden. Het apparaat wordt uit Intune verwijderd. In de volgende tabel wordt per platform beschreven welke gegevens worden verwijderd en wat het effect van selectief wissen is op de gegevens die achterblijven op het apparaat.

**iOS**

|Gegevenstype|iOS|
|-------------|-------|
|Bedrijfs-apps en de bijbehorende gegevens die door Intune zijn geïnstalleerd.|Apps worden verwijderd. Gegevens van bedrijfs-apps worden verwijderd.<br /><br />App-gegevens van Microsoft-apps die gebruikmaken van mobiel appbeheer, worden verwijderd. De app wordt niet verwijderd.|
|Instellingen|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|
|Instellingen voor Wi-Fi en VPN-profiel|Verwijderd|
|Instellingen van certificaatprofiel|Certificaten worden verwijderd en ingetrokken.|
|Beheeragent|Beheerprofiel wordt verwijderd.|
|E-mail|E-mailprofielen die zijn ingericht via Intune, worden verwijderd en in de cache opgeslagen e-mail op het apparaat wordt verwijderd.|
|Loskoppelen van Azure Active Directory (AAD)|AAD-record verwijderd|
|Contactpersonen | Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd.  Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. <br /> <br />Op dit moment wordt alleen de Outlook-app ondersteund.

**Android**

|Gegevenstype|Android|Android Samsung KNOX|
|-------------|-----------|------------------------|
|Webkoppelingen|Verwijderd.|Verwijderd|
|Niet-beheerde Google Play-apps|Apps en gegevens blijven geïnstalleerd|Apps en gegevens blijven geïnstalleerd|
|Niet-beheerde Line-Of-Business-apps|Apps en gegevens blijven geïnstalleerd|Apps worden verwijderd en als gevolg daarvan worden ook lokale app-gegevens verwijderd. Er worden geen gegevens buiten de app (SD-geheugenkaart enzovoort) verwijderd.|
|Beheerde Google Play-apps|App-gegevens worden verwijderd. De app wordt niet verwijderd. Gegevens die door MAM-versleuteling buiten de app worden beveiligd (SD-geheugenkaart enzovoort) blijven versleuteld en onbruikbaar, maar worden niet verwijderd.|App-gegevens worden verwijderd. De app wordt niet verwijderd. Gegevens die door MAM-versleuteling buiten de app worden beveiligd (SD-geheugenkaart enzovoort), blijven versleuteld, maar worden niet verwijderd.|
|Beheerde Line-Of-Business-apps|App-gegevens worden verwijderd. De app wordt niet verwijderd. Gegevens die door MAM-versleuteling buiten de app worden beveiligd (SD-geheugenkaart enzovoort) blijven versleuteld en onbruikbaar, maar worden niet verwijderd.|App-gegevens worden verwijderd. De app wordt niet verwijderd. Gegevens die door MAM-versleuteling buiten de app worden beveiligd (SD-geheugenkaart enzovoort) blijven versleuteld en onbruikbaar, maar worden niet verwijderd.|
|Instellingen|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|
|Instellingen voor Wi-Fi en VPN-profiel|Verwijderd|Verwijderd|
|Instellingen van certificaatprofiel|Certificaten worden ingetrokken, maar niet verwijderd.|Certificaten worden verwijderd en ingetrokken.|
|Beheeragent|Administratorbevoegdheden voor apparaat worden ingetrokken.|Administratorbevoegdheden voor apparaat worden ingetrokken.|
|E-mail|E-mail die wordt ontvangen door de Microsoft Outlook-app voor Android-app wordt verwijderd.|E-mailprofielen die zijn ingericht via Intune, worden verwijderd en in de cache opgeslagen e-mail op het apparaat wordt verwijderd.|
|Loskoppelen van Azure Active Directory (AAD)|AAD-record verwijderd|AAD-record verwijderd|
|Contactpersonen | Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd.  Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. <br /> <br />Op dit moment wordt alleen de Outlook-app ondersteund.|Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd.  Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. <br /> <br />Op dit moment wordt alleen de Outlook-app ondersteund.

**Windows**

|Gegevenstype|Windows 8.1 (MDM) en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Bedrijfs-apps en de bijbehorende gegevens die door Intune zijn geïnstalleerd.|Van bestanden die worden beveiligd met EFS, wordt de sleutel ingetrokken en de gebruiker kan de bestanden niet openen.|Bedrijfs-apps worden niet verwijderd.|Apps die oorspronkelijk zijn geïnstalleerd via de bedrijfsportal, worden verwijderd. Gegevens van bedrijfs-apps worden verwijderd.|De installatie van apps wordt ongedaan gemaakt en sideloading-codes worden verwijderd.|
|Instellingen|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|
|Instellingen voor Wi-Fi en VPN-profiel|Verwijderd|Verwijderd|Niet ondersteund|Verwijderd|
|Instellingen van certificaatprofiel|Certificaten worden verwijderd en ingetrokken.|Certificaten worden verwijderd en ingetrokken.|Niet ondersteund|Certificaten worden verwijderd en ingetrokken.|
|E-mail|Hiermee verwijdert u e-mail waarvoor EFS is ingeschakeld. Dit omvat de e-mailapp voor Windows-e-mail en bijlagen.|Niet ondersteund|E-mailprofielen die zijn ingericht via Intune, worden verwijderd en in de cache opgeslagen e-mail op het apparaat wordt verwijderd.|Hiermee verwijdert u e-mail waarvoor EFS is ingeschakeld. Dit omvat de e-mailapp voor Windows-e-mail en bijlagen. Hiermee verwijdert u e-mailaccounts die zijn ingericht door Intune.|
|Loskoppelen van Azure Active Directory (AAD)|Nee|Nee|AAD-record verwijderd|Niet van toepassing. Windows 10 biedt geen ondersteuning voor selectief wissen voor apparaten die zijn toegevoegd aan Azure Active Directory|

### Een apparaat op afstand wissen via de Intune-beheerconsole

1.  Selecteer de te wissen apparaten. U vindt deze op basis van gebruiker of apparaat.

    -   **Op gebruiker:**

        1.  Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Groepen** &gt; **Alle gebruikers**.

        2.  Kies de naam van de gebruiker van wie u het mobiele apparaat wilt wissen. Kies **Eigenschappen weergeven**.

        3.  Kies op de pagina **Eigenschappen** van de gebruiker **Apparaten** en kies vervolgens de naam van het mobiele apparaat dat u wilt wissen. Gebruik Ctrl+klikken om meerdere apparaten te selecteren.

    -   **Op apparaat:**

        1.  Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Groepen** &gt; **Alle mobiele apparaten**.

      ![Een bewerking voor buiten gebruik stellen of wissen starten](../media/dev-sa-wipe.png)

        2.  Kies **Apparaten** en vervolgens de naam van het mobiele apparaat dat u wilt wissen. Gebruik Ctrl+klikken om meerdere apparaten te selecteren.

2.  Kies **Buiten gebruik stellen/Wissen**.

3.  Er wordt een bericht weergegeven waarin u wordt gevraagd om te bevestigen of u het apparaat buiten gebruik wilt stellen.

    -   Als u **Selectief wissen** wilt uitvoeren, waarbij alleen bedrijfs-apps en -gegevens worden verwijderd, kiest u **Ja**.

    -   Als u **Volledig wissen** wilt uitvoeren, waarbij alle apps en gegevens worden gewist en de standaardinstellingen van het apparaat worden hersteld, selecteert u **Het apparaat wissen voordat u het buiten gebruik stelt**. Deze actie is van toepassing op alle platforms met uitzondering van Windows 8.1. **U kunt geen gegevens herstellen die zijn verwijderd met Volledig wissen**.

Het duurt minder dan 15 minuten voordat een wisactie naar alle typen apparaten is doorgegeven.

## EFS-inhoud (Encryption File System) wissen
Selectief wissen van EFS-gecodeerde inhoud wordt ondersteund door Windows 8.1 en Windows RT 8.1. Het volgende is van toepassing op selectief wissen van EFS-inhoud:

-   Alleen apps en gegevens die worden beveiligd door EFS met gebruikmaking van hetzelfde internetdomein als het Intune-account, worden selectief gewist. Zie [Windows Selective Wipe for Device Data Management](http://technet.microsoft.com/library/dn486874.aspx) (Selectief wissen in Windows voor beheer van apparaatgegevens) voor meer informatie.

-   Als er wijzigingen zijn aangebracht in het domein dat is gekoppeld aan EFS, kan het 48 uur duren voordat apps en gegevens die gebruikmaken van het nieuwe domein, selectief kunnen worden gewist.

-   Elk domein dat is geregistreerd bij Intune, wordt gewist.

De gegevens en apps die momenteel worden ondersteund door selectief wissen met EFS zijn:

-   E-mail-app voor Windows

-   Werkmappen

-   Bestanden en mappen die zijn gecodeerd met EFS. Zie [Aanbevolen procedures voor het Encrypting File System](http://support.microsoft.com/kb/223316) voor meer informatie.

-   Als uw organisatie zijn identiteit in Active Directory onderhoudt, moet uw organisatie het hulpprogramma Directory-synchronisatie (DirSync) gebruiken om informatie naar AAD te synchroniseren. Anders werkt selectief wissen met EFS niet correct.  Zie [Directory Sync Scenario](http://technet.microsoft.com/library/dn441212.aspx) (Directory-synchronisatiescenario) in de documentatie van Azure Active Directory voor meer informatie over DirSync.

## Bewaken van buiten gebruik stellen, wissen en verwijderen
Ga als volgt te werk om een rapport op te halen met informatie over de apparaten die buiten gebruik zijn gesteld, gewist of verwijderd, en door wie deze actie is uitgevoerd:

1.  Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Rapporten** &gt; **Apparaatgeschiedenisrapporten**.

2.  Geef een begin- en einddatum voor het rapport op en kies vervolgens **Rapport weergeven**.


### Zie ook
[Apparaten buiten gebruik stellen](retire-devices-from-microsoft-intune-management.md)

[Windows Selective Wipe fof Device Data Management](http://technet.microsoft.com/library/dn486874.aspx)



<!--HONumber=Jul16_HO4-->


