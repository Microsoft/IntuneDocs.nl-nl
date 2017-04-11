---
title: Volledig of selectief wissen op apparaten met Intune
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: meer informatie over het selectief wissen van bedrijfsgegevens op een apparaat of het apparaat volledig wissen om de fabriekswaarden te herstellen.'
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 1ba0dab35e0da6cfe744314a4935221a206fcea7
ms.openlocfilehash: 6b723069108ff2cbe85951f7d65ef803323eceb9
ms.lasthandoff: 03/13/2017


---

# <a name="use-full-or-selective-wipe"></a>Volledig of selectief wissen gebruiken

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

U kunt apps en gegevens wissen van met Intune beheerde apparaten die niet meer nodig zijn, een nieuwe bestemming krijgen of zijn kwijtgeraakt. Intune biedt hiervoor de mogelijkheid om selectief of volledig te wissen. Gebruikers kunnen ook vanuit de Intune-bedrijfsportal-app op afstand een opdracht tot het wissen van hun apparaat geven, mits dit een eigen apparaat is dat bij Intune is geregistreerd.

  > [!NOTE]
  > Dit onderwerp gaat alleen over het wissen van apparaten die deel uitmaken van Intune-beheer van mobiele apparaten. U kunt [Azure Portal](https://portal.azure.com) ook gebruiken om [bedrijfsgegevens uit apps te wissen](https://docs.microsoft.com/intune/deploy-use/wipe-managed-company-app-data-with-microsoft-intune). U kunt ook [computers buiten gebruik stellen die worden beheerd door de Intune-clientsoftware](https://docs.microsoft.com/intune/deploy-use/retire-a-windows-pc-with-microsoft-intune).

## <a name="full-wipe"></a>Volledig wissen

Met **Volledig wissen** worden de fabrieksinstellingen van een apparaat hersteld, en worden alle bedrijfs- en gebruikersgegevens en -instellingen verwijderd. Het apparaat wordt uit Intune verwijderd. Volledig wissen is nuttig voor het opnieuw instellen van een apparaat, wanneer het apparaat aan een nieuwe gebruiker wordt gegeven of wanneer het apparaat is verloren of gestolen.  **Wees voorzichtig bij het selecteren van Volledig wissen. De gegevens op het apparaat kunnen niet worden hersteld**.


> [!Warning]
> Windows 10 RTM-apparaten (apparaten ouder dan Windows-10 versie 1511) met minder dan 4 GB aan RAM-geheugen kunnen ontoegankelijk worden als ze worden gewist. Voor toegang tot een Windows 10-apparaat dat niet meer reageert, kunt u het apparaat vanaf een USB-station opstarten.


**Een apparaat volledig wissen (fabriekswaarden herstellen)**:

1.  Kies op de blade **Apparaten en groepen** de optie **Alle apparaten**.

2.  Kies de naam van het apparaat dat u wilt wissen.

3.  Kies op de blade met de naam van het apparaat **Fabrieksinstellingen** en kies vervolgens **Ja** om het wissen te bevestigen.

Als het apparaat is ingeschakeld en verbonden, wordt een wisopdracht in minder dan 15 minuten aan alle typen apparaten doorgegeven.

### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>U kunt als volgt apparaten verwijderen in de Azure Active Directory-portal:

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
|E-mail|E-mailprofielen die zijn ingericht via Intune, worden verwijderd en in de cache opgeslagen e-mail op het apparaat wordt verwijderd. Als Microsoft Exchange on-premises wordt gehost, worden e-mailprofielen en in cache opgeslagen e-mailberichten niet verwijderd.|
|Outlook|E-mail die wordt ontvangen door de Microsoft Outlook-app voor iOS, wordt verwijderd.</br>Uitzondering: als Exchange on-premises wordt gehost, wordt e-mail niet verwijderd.|
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
|E-mail|E-mail die wordt ontvangen door de Microsoft Outlook-app voor Android wordt verwijderd.|E-mailprofielen die zijn ingericht via Intune, worden verwijderd en in de cache opgeslagen e-mail op het apparaat wordt verwijderd.|
|Outlook|E-mail die wordt ontvangen door de Microsoft Outlook-app voor iOS, wordt verwijderd.</br>Uitzondering: als Exchange on-premises wordt gehost, wordt e-mail niet verwijderd.|E-mail die wordt ontvangen door de Microsoft Outlook-app voor iOS, wordt verwijderd.</br>Uitzondering: als Exchange on-premises wordt gehost, wordt e-mail niet verwijderd.|
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
|E-mail|Hiermee verwijdert u e-mail waarvoor EFS is ingeschakeld. Dit omvat de e-mail-app voor Windows-e-mail en -bijlagen.|Niet ondersteund.|E-mailprofielen die zijn ingericht via Intune, worden verwijderd en in de cache opgeslagen e-mail op het apparaat wordt verwijderd.|Hiermee verwijdert u e-mail waarvoor EFS is ingeschakeld. Dit omvat de e-mail-app voor Windows-e-mail en -bijlagen. Hiermee verwijdert u e-mailaccounts die zijn ingericht door Intune.</br>**Uitzondering**: als Microsoft Exchange on-premises wordt gehost, worden e-mailaccounts niet verwijderd.|
|Loskoppelen van Azure Active Directory (AAD)|Nee.|Nee.|AAD-record verwijderd.|Niet van toepassing. Windows 10 biedt geen ondersteuning voor selectief wissen voor apparaten die zijn toegevoegd aan Azure Active Directory.|

**Selectief wissen**:

1.  Kies op de blade **Apparaten en groepen** de optie **Alle apparaten**.

2.  Kies de naam van het apparaat dat u wilt wissen.

3.  Kies op de blade met de naam van het apparaat **Remove comp...** (Bedrijfsgeg...), wat staat voor Bedrijfsgegevens verwijderen, en kies vervolgens **Ja** om het wissen te bevestigen.

Als het apparaat is ingeschakeld en verbonden, wordt een wisopdracht in minder dan 15 minuten aan alle typen apparaten doorgegeven.

