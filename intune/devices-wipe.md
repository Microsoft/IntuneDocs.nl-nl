---
title: Bedrijfsgegevens van apparaten verwijderen met Microsoft Intune - Azure | Microsoft Docs
description: Voor apparaten met Android, een Android-werkprofiel, iOS, macOS of Windows kunt u Microsoft Intune gebruiken om bedrijfsgegevens van een apparaat te verwijderen of de fabrieksinstellingen terug te zetten. Daarnaast kunt u een apparaat uit Azure Active Directory verwijderen.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 326622c324f75e216db69bd850b707e0fc1c0679
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37906053"
---
# <a name="remove-devices-by-using-factory-reset-removing-company-data-or-manually-unenrolling-the-device"></a>Apparaten verwijderen door Fabrieksinstellingen terugzetten te gebruiken, bedrijfsgegevens te verwijderen of de inschrijving van het apparaat handmatig ongedaan te maken

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met de acties **Bedrijfsgegevens verwijderen** of **Fabrieksinstellingen terugzetten** kunt u apparaten uit Intune verwijderen die niet meer nodig zijn, een nieuwe bestemming krijgen of zijn kwijtgeraakt. Gebruikers kunnen ook vanuit de Intune-bedrijfsportal op afstand een opdracht geven voor persoonlijke apparaten die bij Intune zijn ingeschreven.

> [!NOTE]
> Gebruik de actie **Fabrieksinstellingen terugzetten** of **Bedrijfsgegevens verwijderen** voor alle apparaten die aan een gebruiker zijn gekoppeld voordat u een gebruiker verwijdert uit Azure Active Directory (Azure AD). Als u gebruikers met beheerde apparaten uit Azure AD verwijdert, kan Intune geen fabrieksinstellingen meer uitgeven of bedrijfsgegevens van die apparaten verwijderen.

## <a name="factory-reset"></a>Fabrieksinstellingen terugzetten

Met de actie **Fabrieksinstellingen terugzetten** zet u de standaardfabrieksinstellingen terug op het apparaat. De gebruikersgegevens worden bewaard als u het selectievakje **Inschrijvingsstatus en gebruikersaccount behouden** inschakelt. Anders wordt het station veilig gewist.

|Actie Fabrieksinstellingen terugzetten|**Inschrijvingsstatus en gebruikersaccount behouden**|Verwijderd uit Intune-beheer|Description|
|:-------------:|:------------:|:------------:|------------|
|**Fabrieksinstellingen terugzetten**| Niet ingeschakeld | Ja | Alle gebruikersaccounts, gegevens, MDM-beleidsregels en instellingen worden gewist. De standaardtoestand en -instellingen van het besturingssysteem worden teruggezet.|
|**Fabrieksinstellingen terugzetten**| Ingeschakeld | Nee | Alle MDM-beleidsregels worden gewist. Gebruikersaccounts en -gegevens blijven bewaard. Gebruikersinstellingen worden teruggezet op de standaardwaarden. De standaardtoestand en -instellingen van het besturingssysteem worden teruggezet.|

De optie **Inschrijvingsstatus en gebruikersaccount behouden** is alleen beschikbaar voor Windows 10 versie 1709 en hoger.

MDM-beleidsregels worden toegepast wanneer het apparaat de volgende keer verbinding maakt met Intune.

Fabrieksinstellingen terugzetten is nuttig wanneer u een apparaat opnieuw wilt instellen voordat u het aan een nieuwe gebruiker geeft of wanneer een apparaat is verloren of gestolen. Wees voorzichtig bij het selecteren van **Fabrieksinstellingen terugzetten**. De gegevens op het apparaat kunnen niet worden hersteld.

### <a name="factory-reset-a-device"></a>Fabrieksinstellingen terugzetten op een apparaat

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaten** > **Alle apparaten**.
4. Selecteer de naam van het apparaat waarvoor u Fabrieksinstellingen terugzetten wilt gebruiken.
5. Selecteer **Fabrieksinstellingen terugzetten** in het deelvenster waarin de naam van het apparaat wordt weergegeven.
6. Voor Windows 10 versie 1709 of hoger is ook de optie **Inschrijvingsstatus en gebruikersaccount behouden** aanwezig. 
    
    |Behouden tijdens fabrieksinstellingen terugzetten|Niet behouden|
    | -------------|------------|
    |Gebruikersaccounts die zijn gekoppeld aan het apparaat|Gebruikersbestanden|
    |Status van de machine \(lid van domein, lid van Azure AD)| Door de gebruiker geïnstalleerde apps \(Store- en Win32-apps)|
    |MDM-inschrijving (Mobile Device Management)|Niet-standaard apparaatinstellingen|
    |Door OEM geïnstalleerde apps \(Store- en Win32-apps)||
    |Gebruikersprofiel||
    |Gebruikersgegevens buiten gebruikersprofiel||
    |Autologon gebruiker|| 
    
         
7. Selecteer **Ja** om te bevestigen dat u de fabrieksinstellingen wilt terugzetten.

Als het apparaat is ingeschakeld en is verbonden, wordt de actie **Fabrieksinstellingen terugzetten** in minder dan 15 minuten aan alle typen apparaten doorgegeven.

## <a name="remove-company-data"></a>Bedrijfsgegevens verwijderen

Met de actie **Bedrijfsgegevens verwijderen** worden gegevens (indien van toepassing), instellingen en e-mailprofielen van beheerde apps verwijderd die via Intune zijn toegewezen. Het apparaat wordt uit Intune-beheer verwijderd. Dit gebeurt wanneer het apparaat de volgende keer wordt ingecheckt en de actie **Bedrijfsgegevens verwijderen** ontvangt.

Met **Bedrijfsgegevens verwijderen** blijven de persoonlijke gegevens van de gebruiker op het apparaat behouden.  

In de volgende tabel wordt beschreven welke gegevens worden verwijderd en wat het effect van **Bedrijfsgegevens verwijderen** is op de gegevens die achterblijven op het apparaat.

### <a name="ios"></a>iOS

|Gegevenstype|iOS|
|-------------|-------|
|Bedrijfs-apps en de bijbehorende gegevens die door Intune zijn geïnstalleerd|Apps worden verwijderd. Gegevens van bedrijfs-apps worden verwijderd.<br /><br />App-gegevens van Microsoft-apps die gebruikmaken van mobiel appbeheer, worden verwijderd. De app wordt niet verwijderd.|
|Instellingen|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen. Gebruikers kunnen de instellingen wijzigen.|
|Instellingen voor Wi-Fi en VPN-profiel|Verwijderd.|
|Instellingen van certificaatprofiel|Certificaten worden verwijderd en ingetrokken.|
|Beheeragent|Beheerprofiel wordt verwijderd.|
|E-mail|E-mailprofielen die via Intune zijn ingericht, worden verwijderd. In de cache opgeslagen e-mail op het apparaat wordt verwijderd.|
|Outlook|E-mail die wordt ontvangen door de Microsoft Outlook-app voor iOS, wordt verwijderd. Hiervoor moet de mobiele app voor Outlook eerst als een vereiste app voor iOS-gebruikers worden geïmplementeerd.|
|Loskoppelen van Azure AD|Azure AD-record wordt verwijderd.|
|Contactpersonen |Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd. Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden verwijderd. <br /> <br />Op dit moment wordt alleen de Outlook-app ondersteund.

### <a name="android"></a>Android

|Gegevenstype|Android|Android Samsung Knox Standard|
|-------------|-----------|------------------------|
|Webkoppelingen|Verwijderd.|Verwijderd.|
|Niet-beheerde Google Play-apps|Apps en gegevens blijven geïnstalleerd.|Apps en gegevens blijven geïnstalleerd.|
|Niet-beheerde Line-Of-Business-apps|Apps en gegevens blijven geïnstalleerd.|Apps worden verwijderd en lokale app-gegevens worden verwijderd. Er worden geen gegevens buiten de app (bijvoorbeeld op een SD-geheugenkaart) verwijderd.|
|Beheerde Google Play-apps|App-gegevens worden verwijderd. De app wordt niet verwijderd. Gegevens die door MAM-versleuteling (Mobile Application Management) buiten de app worden beveiligd (bijvoorbeeld een SD-geheugenkaart), blijven versleuteld en onbruikbaar, maar worden niet verwijderd.|App-gegevens worden verwijderd. De app wordt niet verwijderd. Gegevens die door MAM-versleuteling buiten de app worden beveiligd (bijvoorbeeld een SD-geheugenkaart), blijven versleuteld, maar worden niet verwijderd.|
|Beheerde Line-Of-Business-apps|App-gegevens worden verwijderd. De app wordt niet verwijderd. Gegevens die door MAM-versleuteling buiten de app worden beveiligd (bijvoorbeeld een SD-geheugenkaart), blijven versleuteld en onbruikbaar, maar worden niet verwijderd.|App-gegevens worden verwijderd. De app wordt niet verwijderd. Gegevens die door MAM-versleuteling buiten de app worden beveiligd (bijvoorbeeld een SD-geheugenkaart), blijven versleuteld en onbruikbaar, maar worden niet verwijderd.|
|Instellingen|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen. Gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen. Gebruikers kunnen de instellingen wijzigen.|
|Instellingen voor Wi-Fi en VPN-profiel|Verwijderd.|Verwijderd.|
|Instellingen van certificaatprofiel|Certificaten worden ingetrokken, maar niet verwijderd.|Certificaten worden verwijderd en ingetrokken.|
|Beheeragent|Administratorbevoegdheden voor apparaat worden ingetrokken.|Administratorbevoegdheden voor apparaat worden ingetrokken.|
|E-mail|N.v.t. (e-mailprofielen worden niet ondersteund door Android-apparaten)|E-mailprofielen die via Intune zijn ingericht, worden verwijderd. In de cache opgeslagen e-mail op het apparaat wordt verwijderd.|
|Outlook|E-mail die door de Outlook-app voor Android is ontvangen, wordt verwijderd. Dit geldt alleen als Outlook wordt beveiligd door MAM-beleid. Anders wordt Outlook niet gewist wanneer het apparaat wordt uitgeschreven.|E-mail die door de Outlook-app voor Android is ontvangen, wordt verwijderd. Dit geldt alleen als Outlook wordt beveiligd door MAM-beleid. Anders wordt Outlook niet gewist wanneer het apparaat wordt uitgeschreven.|
|Loskoppelen van Azure AD|Azure AD-record wordt verwijderd.|Azure AD-record wordt verwijderd.|
|Contactpersonen |Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd. Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden verwijderd. <br /> <br />Op dit moment wordt alleen de Outlook-app ondersteund.|Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd. Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden verwijderd. <br /> <br />Op dit moment wordt alleen de Outlook-app ondersteund.

### <a name="android-work-profile"></a>Android-werkprofiel

Door Bedrijfsgegevens verwijderen uit te voeren op een apparaat met een Android-werkprofiel, verwijdert u alle gegevens, apps en instellingen in het werkprofiel op het apparaat. Het apparaat wordt buiten bedrijf gesteld voor beheer met Intune. Fabrieksinstellingen terugzetten wordt niet ondersteund voor Android-werkprofielen.

### <a name="android-enterprise-kiosk-devices"></a>Kioskapparaten voor Android Enterprise

U kunt alleen de fabrieksinstellingen van Android-kioskapparaten terugzetten. U kunt geen bedrijfsgegevens verwijderen van Android-kioskapparaten.


### <a name="macos"></a>macOS

|Gegevenstype|macOS|
|-------------|-------|
|Instellingen|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen. Gebruikers kunnen de instellingen wijzigen.|
|Instellingen voor Wi-Fi en VPN-profiel|Verwijderd.|
|Instellingen van certificaatprofiel|Certificaten die zijn geïmplementeerd via MDM, worden verwijderd en ingetrokken.|
|Beheeragent|Beheerprofiel wordt verwijderd.|
|Outlook|Als voorwaardelijke toegang is ingeschakeld, ontvangt het apparaat geen nieuwe e-mail.|
|Loskoppelen van Azure AD|Azure AD-record wordt verwijderd.|

### <a name="windows"></a>Windows

|Gegevenstype|Windows 8.1 (MDM) en Windows RT 8.1|Windows RT|Windows Phone 8.1 en Windows Phone 8|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Bedrijfs-apps en de bijbehorende gegevens die door Intune zijn geïnstalleerd|Sleutels worden ingetrokken voor bestanden die zijn beveiligd met EFS. De gebruiker kan de bestanden niet openen.|Bedrijfs-apps worden niet verwijderd.|Apps die oorspronkelijk zijn geïnstalleerd via de bedrijfsportal, worden verwijderd. Gegevens van bedrijfs-apps worden verwijderd.|Apps worden verwijderd. Sideloadsleutels worden verwijderd.<br>Voor Windows 10 versie 1703 (makersupdate) en hoger worden Office 365 ProPlus-apps niet verwijderd.|
|Instellingen|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen. Gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen. Gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen. Gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen. Gebruikers kunnen de instellingen wijzigen.|
|Instellingen voor Wi-Fi en VPN-profiel|Verwijderd.|Verwijderd.|Niet ondersteund.|Verwijderd.|
|Instellingen van certificaatprofiel|Certificaten worden verwijderd en ingetrokken.|Certificaten worden verwijderd en ingetrokken.|Niet ondersteund.|Certificaten worden verwijderd en ingetrokken.|
|E-mail|Hiermee worden e-mails verwijderd waarvoor EFS is ingeschakeld. Dit omvat e-mails en bijlagen in de e-mail-app voor Windows.|Niet ondersteund.|E-mailprofielen die via Intune zijn ingericht, worden verwijderd. In de cache opgeslagen e-mail op het apparaat wordt verwijderd.|Hiermee worden e-mails verwijderd waarvoor EFS is ingeschakeld. Dit omvat e-mails en bijlagen in de e-mail-app voor Windows. Hiermee verwijdert u e-mailaccounts die zijn ingericht door Intune.|
|Loskoppelen van Azure AD|Nee.|Nee.|Azure AD-record wordt verwijderd.|Niet van toepassing. In Windows 10 kunt u geen bedrijfsgegevens verwijderen door apparaten die zijn toegevoegd aan Azure AD.|

### <a name="remove-company-data"></a>Bedrijfsgegevens verwijderen

1. Meld u aan bij [Intune in Azure Portal](https://aka.ms/intuneportal).
2. Selecteer **Alle apparaten** in het deelvenster **Apparaten**.
3. Selecteer de naam van het apparaat waarvan u bedrijfsgegevens wilt verwijderen.
4. Selecteer **Bedrijfsgegevens verwijderen** in het deelvenster waarin de naam van het apparaat wordt weergegeven. Selecteer **Ja** om de opdracht te bevestigen.

Als het apparaat is ingeschakeld en is verbonden, wordt de actie **Bedrijfsgegevens verwijderen** in minder dan 15 minuten aan alle typen apparaten doorgegeven.

## <a name="delete-devices-from-the-intune-portal"></a>Apparaten verwijderen uit de Intune-portal

Als u apparaten wilt verwijderen uit de Intune-portal, kunt u ze verwijderen in het specifieke deelvenster met apparaten. De volgende keer dat het apparaat wordt ingecheckt, worden eventuele bedrijfsgegevens op het apparaat verwijderd.

1. Meld u aan bij [Intune in Azure Portal](https://aka.ms/intuneportal).
2. Kies **Apparaten** > **Alle apparaten** > kies het apparaat dat u wilt verwijderen > **Verwijderen**.

### <a name="automatically-delete-devices-with-cleanup-rules"></a>Apparaten automatisch verwijderen met opschoonregels
U kunt Intune configureren om automatisch apparaten te verwijderen die inactief of verlopen zijn of niet reageren. Deze opschoonregels controleren uw apparaatinventaris continu, zodat uw apparaatrecords up-to-date blijven. Apparaten die op deze manier worden verwijderd, worden verwijderd uit Intune-beheer.
1. Meld u aan bij [Intune in Azure Portal](https://aka.ms/intuneportal).
2. Kies **Apparaten** > **Opschoonregels voor apparaat** > **Ja**.
3. Voer in het vak **Apparaten verwijderen die zo veel dagen niet hebben ingecheckt** een getal tussen 90 en 270 in.
4. Kies **Opslaan**.



## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Apparaten verwijderen van de Azure Active Directory-portal

Vanwege communicatieproblemen of ontbrekende apparaten moet u wellicht apparaten verwijderen van Azure AD. U kunt de actie **Verwijderen** gebruiken voor het verwijderen van apparaatrecords uit Azure Portal die onbereikbaar zijn en vermoedelijk niet opnieuw met Azure gaan communiceren. Met de actie **Verwijderen** wordt het apparaat niet uit beheer verwijderd.

1.  Meld u met uw beheerdersreferenties aan bij [Azure Active Directory in Azure Portal](http://aka.ms/accessaad). U kunt zich ook aanmelden bij de [Office 365-portal](https://portal.office.com). Selecteer **Beheercentrums** > **Azure AD** in het menu.
2.  Maak een Azure-abonnement maken als u er nog geen hebt. U kunt dit zonder creditcard of betaling doen als u beschikt over een betaald account (selecteer de abonnementskoppeling **Uw gratis Azure Active Directory registreren**).
3.  Selecteer **Azure Active Directory** en vervolgens uw organisatie.
4.  Selecteer het tabblad **Gebruikers** .
5. Selecteer de gebruiker die is gekoppeld aan het apparaat dat u wilt verwijderen.
6.  Selecteer **Apparaten**.
7.  Verwijder de gewenste apparaten. U kunt bijvoorbeeld apparaten verwijderen die niet meer in gebruik zijn of die onjuist zijn gedefinieerd.
