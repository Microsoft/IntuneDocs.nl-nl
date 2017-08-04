---
title: Wissen op afstand gebruiken om gegevens te beveiligen
description: Intune biedt mogelijkheden tot selectief wissen en volledig wissen om zo gevoelige bedrijfsgegevens te kunnen verwijderen en om toegang tot veel bedrijfsresources onmogelijk te maken.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8519e411-3d48-44eb-9b41-3e4fd6a93112
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 036899c5e438355cc10da8ab2bd47ec0830c9946
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/03/2017
---
# <a name="help-protect-your-data-with-full-or-selective-wipe-using-microsoft-intune"></a>Uw gegevens beveiligen met volledig wissen of selectief wissen met Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

U kunt apps en gegevens wissen van met Intune beheerde apparaten die niet meer nodig zijn, een nieuwe bestemming krijgen of zijn kwijtgeraakt. Intune biedt hiervoor de mogelijkheid om selectief of volledig te wissen. Gebruikers kunnen ook vanuit de Intune-bedrijfsportal-app op afstand een opdracht tot het wissen van hun apparaat geven, mits dit een eigen apparaat is dat bij Intune is geregistreerd.

  > [!NOTE]
  > Dit onderwerp gaat alleen over het wissen van apparaten die deel uitmaken van Intune-beheer van mobiele apparaten. U kunt [Azure Portal](https://portal.azure.com) ook gebruiken om [bedrijfsgegevens uit apps te wissen](wipe-managed-company-app-data-with-microsoft-intune.md). U kunt ook [computers buiten gebruik stellen die worden beheerd door de Intune-clientsoftware](retire-a-windows-pc-with-microsoft-intune.md).

## <a name="full-wipe"></a>Volledig wissen

Met **Volledig wissen** worden de fabrieksinstellingen van een apparaat hersteld, en worden alle bedrijfs- en gebruikersgegevens en -instellingen verwijderd. Het apparaat wordt uit Intune verwijderd. Volledig wissen is nuttig voor het opnieuw instellen van een apparaat, wanneer het apparaat aan een nieuwe gebruiker wordt gegeven of wanneer het apparaat is verloren of gestolen.  **Wees voorzichtig bij het selecteren van Volledig wissen. De gegevens op het apparaat kunnen niet worden hersteld**.


> [!Warning]
> Windows 10 RTM-apparaten (apparaten ouder dan Windows-10 versie 1511) met minder dan 4 GB aan RAM-geheugen kunnen ontoegankelijk worden als ze worden gewist. Voor toegang tot een Windows 10-apparaat dat niet meer reageert, kunt u het apparaat vanaf een USB-station opstarten.

### <a name="remotely-wipe-a-device-from-the-intune-administrator-console"></a>Een apparaat op afstand wissen via de Intune-beheerconsole

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

3.  Er wordt een bevestigingsbericht weergegeven waarin u wordt gevraagd of u het apparaat buiten gebruik wilt stellen.

    -   Als u **Selectief wissen** wilt uitvoeren, waarbij alleen bedrijfs-apps en -gegevens worden verwijderd, kiest u **Ja**.

    -   Als u **Volledig wissen** wilt uitvoeren, waarbij alle apps en gegevens worden gewist en de standaardinstellingen van het apparaat worden hersteld, kiest u **Het apparaat wissen voordat u het buiten gebruik stelt**. Deze actie is van toepassing op alle platforms met uitzondering van Windows 8.1. **U kunt geen gegevens herstellen die zijn verwijderd met Volledig wissen**.

Als het apparaat is ingeschakeld en verbonden, wordt een wisopdracht in minder dan 15 minuten aan alle typen apparaten doorgegeven.

#### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>U kunt als volgt apparaten verwijderen in de Azure Active Directory-portal:

1.  Blader naar [http://aka.ms/accessaad](http://aka.ms/accessaad) of kies **Beheer** &gt; **Azure AD** op [https://portal.office.com](https://portal.office.com).

2.  Meld u aan met uw organisatie-id via de koppeling aan de linkerkant van de pagina.

3.  Een Azure-abonnement maken als u er nog geen hebt. U kunt dit zonder creditcard of betaling doen als u beschikt over een betaald account (kies de abonnementskoppeling **Uw gratis Azure Active Directory registreren**).

4.  Selecteer **Active Directory** en vervolgens uw organisatie.

5.  Selecteer het tabblad **Gebruikers** .

6.  Selecteer de gebruiker waarvoor u de apparaten wilt verwijderen.

7.  Kies **Apparaten**.

8.  Verwijder waar nodig apparaten, zoals apparaten die niet langer in gebruik zijn of die onjuist zijn gedefinieerd.


## <a name="selective-wipe"></a>Selectief wissen

Met **Selectief wissen** worden bedrijfsgegevens van een apparaat verwijderd, inclusief eventuele MAM-gegevens (Mobile App Management), instellingen en e-mailprofielen. Bij Selectief wissen blijven de persoonlijke gegevens van de gebruiker op het apparaat behouden. Het apparaat wordt uit Intune verwijderd. In de volgende tabel wordt beschreven welke gegevens worden verwijderd en wat het effect van selectief wissen is op de gegevens die achterblijven op het apparaat. (De tabellen zijn ingedeeld op basis van platform.)

**iOS**

|Gegevenstype|iOS|
|-------------|-------|
|Bedrijfs-apps en de bijbehorende gegevens die door Intune zijn geïnstalleerd|Apps worden verwijderd. Gegevens van bedrijfs-apps worden verwijderd.<br /><br />App-gegevens van Microsoft-apps die gebruikmaken van mobiel appbeheer, worden verwijderd. De app wordt niet verwijderd.|
|Instellingen|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|
|Instellingen voor Wi-Fi en VPN-profiel|Verwijderd.|
|Instellingen van certificaatprofiel|Certificaten worden verwijderd en ingetrokken.|
|Beheeragent|Beheerprofiel wordt verwijderd.|
|E-mail|E-mailprofielen die zijn ingericht via Intune, worden verwijderd en in de cache opgeslagen e-mail op het apparaat wordt verwijderd.|
|Outlook|E-mail die wordt ontvangen door de Microsoft Outlook-app voor iOS, wordt verwijderd.|
|Loskoppelen van Azure Active Directory (AAD)|AAD-record wordt verwijderd.|
|Contactpersonen | Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd.  Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. <br /> <br />Op dit moment wordt alleen de Outlook-app ondersteund.

**Android**

|Gegevenstype|Android|Android Samsung KNOX Standard|
|-------------|-----------|------------------------|
|Webkoppelingen|Verwijderd.|Verwijderd.|
|Niet-beheerde Google Play-apps|Apps en gegevens blijven geïnstalleerd.|Apps en gegevens blijven geïnstalleerd.|
|Niet-beheerde Line-Of-Business-apps|Apps en gegevens blijven geïnstalleerd.|Apps worden verwijderd en als gevolg daarvan worden ook lokale app-gegevens verwijderd. Er worden geen gegevens buiten de app (bijvoorbeeld op een SD-geheugenkaart) verwijderd.|
|Beheerde Google Play-apps|App-gegevens worden verwijderd. De app wordt niet verwijderd. Gegevens die door MAM-versleuteling buiten de app worden beveiligd (bijvoorbeeld een SD-geheugenkaart), blijven versleuteld en onbruikbaar, maar worden niet verwijderd.|App-gegevens worden verwijderd. De app wordt niet verwijderd. Gegevens die door MAM-versleuteling buiten de app worden beveiligd (bijvoorbeeld een SD-geheugenkaart), blijven versleuteld, maar worden niet verwijderd.|
|Beheerde Line-Of-Business-apps|App-gegevens worden verwijderd. De app wordt niet verwijderd. Gegevens die door MAM-versleuteling buiten de app worden beveiligd (bijvoorbeeld een SD-geheugenkaart), blijven versleuteld en onbruikbaar, maar worden niet verwijderd.|App-gegevens worden verwijderd. De app wordt niet verwijderd. Gegevens die door MAM-versleuteling buiten de app worden beveiligd (bijvoorbeeld een SD-geheugenkaart), blijven versleuteld en onbruikbaar, maar worden niet verwijderd.|
|Instellingen|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|
|Instellingen voor Wi-Fi en VPN-profiel|Verwijderd.|Verwijderd.|
|Instellingen van certificaatprofiel|Certificaten worden ingetrokken, maar niet verwijderd.|Certificaten worden verwijderd en ingetrokken.|
|Beheeragent|Administratorbevoegdheden voor apparaat worden ingetrokken.|Administratorbevoegdheden voor apparaat worden ingetrokken.|
|E-mail|N.v.t. Zie het Outlook-item.|E-mailprofielen die zijn ingericht via Intune, worden verwijderd en in de cache opgeslagen e-mail op het apparaat wordt verwijderd.|
|Outlook|E-mailberichten die door de Microsoft Outlook-app voor Android zijn ontvangen, worden verwijderd. Dit geldt alleen als Outlook wordt beveiligd door MAM-beleid. Als dit niet het geval is, wordt Outlook niet gewist bij de uitschrijving.|E-mailberichten die door de Microsoft Outlook-app voor Android zijn ontvangen, worden verwijderd. Dit geldt alleen als Outlook wordt beveiligd door MAM-beleid. Als dit niet het geval is, wordt Outlook niet gewist bij de uitschrijving.|
|Loskoppelen van Azure Active Directory (AAD)|AAD-record verwijderd.|AAD-record verwijderd.|
|Contactpersonen | Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd.  Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. <br /> <br />Op dit moment wordt alleen de Outlook-app ondersteund.|Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd.  Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. <br /> <br />Op dit moment wordt alleen de Outlook-app ondersteund.

**Android for Work**

Door selectief wissen uit te voeren op een Android for Work-apparaat, worden alle gegevens, apps en instellingen in het werkprofiel op het apparaat verwijderd. Het apparaat wordt hierdoor uit het beheer met Intune verwijderd. Volledig wissen wordt niet ondersteund voor Android for Work.

**Windows**

|Gegevenstype|Windows 8.1 (MDM) en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Bedrijfs-apps en de bijbehorende gegevens die door Intune zijn geïnstalleerd|Van bestanden die worden beveiligd met EFS, wordt de sleutel ingetrokken en de gebruiker kan de bestanden niet openen.|Bedrijfs-apps worden niet verwijderd.|Apps die oorspronkelijk zijn geïnstalleerd via de bedrijfsportal, worden verwijderd. Gegevens van bedrijfs-apps worden verwijderd.|De installatie van apps wordt ongedaan gemaakt en sideloading-codes worden verwijderd.|
|Instellingen|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|
|Instellingen voor Wi-Fi en VPN-profiel|Verwijderd.|Verwijderd.|Niet ondersteund.|Verwijderd.|
|Instellingen van certificaatprofiel|Certificaten worden verwijderd en ingetrokken.|Certificaten worden verwijderd en ingetrokken.|Niet ondersteund.|Certificaten worden verwijderd en ingetrokken.|
|E-mail|Hiermee verwijdert u e-mail waarvoor EFS is ingeschakeld. Dit omvat de e-mail-app voor Windows-e-mail en -bijlagen.|Niet ondersteund.|E-mailprofielen die zijn ingericht via Intune, worden verwijderd en in de cache opgeslagen e-mail op het apparaat wordt verwijderd.|Hiermee verwijdert u e-mail waarvoor EFS is ingeschakeld. Dit omvat de e-mail-app voor Windows-e-mail en -bijlagen. Hiermee verwijdert u e-mailaccounts die zijn ingericht door Intune.|
|Loskoppelen van Azure Active Directory (AAD)|Nee.|Nee.|AAD-record verwijderd.|Niet van toepassing. Windows 10 biedt geen ondersteuning voor selectief wissen voor apparaten die zijn toegevoegd aan Azure Active Directory.|

## <a name="wipe-encryption-file-system-efs-enabled-content"></a>EFS-inhoud (Encryption File System) wissen
Selectief wissen van EFS-gecodeerde inhoud wordt ondersteund door Windows 8.1 en Windows RT 8.1. De volgende punten zijn van toepassing op selectief wissen van EFS-inhoud:

-   Alleen apps en gegevens die worden beveiligd door EFS met gebruikmaking van hetzelfde internetdomein als het Intune-account, worden selectief gewist. Zie [Windows Selective Wipe for Device Data Management](http://technet.microsoft.com/library/dn486874.aspx) (Selectief wissen in Windows voor beheer van apparaatgegevens) voor meer informatie.

-   Als er wijzigingen zijn aangebracht in het domein dat is gekoppeld aan EFS, kan het 48 uur duren voordat apps en gegevens die gebruikmaken van het nieuwe domein, selectief kunnen worden gewist.

-   Elk domein dat is geregistreerd bij Intune, wordt gewist.

De gegevens en apps die momenteel worden ondersteund door selectief wissen met EFS zijn:

-   E-mail-app voor Windows

-   Werkmappen

-   Bestanden en mappen die zijn gecodeerd met EFS. Zie [Aanbevolen procedures voor het Encrypting File System](http://support.microsoft.com/kb/223316) voor meer informatie.

-   Als uw organisatie zijn identiteit in Active Directory onderhoudt, moet uw organisatie het hulpprogramma Directory-synchronisatie (DirSync) gebruiken om informatie naar AAD te synchroniseren. Anders werkt selectief wissen met EFS niet correct.  Zie [Directory Sync Scenario](http://technet.microsoft.com/library/dn441212.aspx) (Directory-synchronisatiescenario) in de documentatie van Azure Active Directory voor meer informatie over DirSync.

## <a name="monitor-retire-wipe-and-delete-actions"></a>Bewaken van buiten gebruik stellen, wissen en verwijderen
Ga als volgt te werk om een rapport op te halen met informatie over apparaten die buiten gebruik zijn gesteld, gewist of verwijderd:

1.  Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Rapporten** &gt; **Apparaatgeschiedenisrapporten**.

2.  Geef een begin- en einddatum voor het rapport op en kies vervolgens **Rapport weergeven**.

In dit rapport wordt ook aangegeven wie de actie heeft uitgevoerd.

### <a name="see-also"></a>Zie tevens
[Apparaten buiten gebruik stellen](retire-devices-from-microsoft-intune-management.md)

[Selectief wissen in Windows voor beheer van apparaatgegevens](http://technet.microsoft.com/library/dn486874.aspx)
