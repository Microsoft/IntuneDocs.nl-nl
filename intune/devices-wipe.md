---
title: Apparaten buiten gebruik stellen of wissen met Microsoft Intune - Azure | Microsoft Docs
description: Een apparaat met Android, een Android-werkprofiel, iOS, macOS of Windows-apparaat buiten gebruik of wissen met Microsoft Intune. Daarnaast kunt u een apparaat uit Azure Active Directory verwijderen.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 896008594e17c3773831edede263c8c47cde3c48
ms.sourcegitcommit: 601327125ac8ae912d8159422de8aac7dbdc25f6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59570543"
---
# <a name="remove-devices-by-using-wipe-retire-or-manually-unenrolling-the-device"></a>Apparaten verwijderen via wissen of buiten gebruik stellen, of de registratie van het apparaat handmatig ongedaan maken

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met de acties **Buiten gebruik stellen** of **Wissen** kunt u apparaten uit Intune verwijderen die niet meer nodig zijn, een nieuwe bestemming krijgen of zijn kwijtgeraakt. Gebruikers kunnen ook vanuit de Intune-bedrijfsportal op afstand een opdracht geven voor apparaten die zijn ingeschreven bij Intune.

> [!NOTE]
> Gebruik de actie **Buiten gebruik stellen** of **Wissen** voor alle apparaten die aan een gebruiker zijn gekoppeld voordat u een gebruiker verwijdert uit Azure Active Directory (Azure AD). Als u gebruikers met beheerde apparaten uit Azure AD verwijdert, kan Intune die apparaten niet meer buiten gebruik stellen of wissen.

## <a name="wipe"></a>Wissen

Met de actie **Wissen** herstelt u de fabrieksinstellingen van het apparaat. De gebruikersgegevens worden bewaard als u het selectievakje **Inschrijvingsstatus en gebruikersaccount behouden** inschakelt. Anders wordt het station veilig gewist.

|Actie Wissen|**Inschrijvingsstatus en gebruikersaccount behouden**|Verwijderd uit Intune-beheer|Beschrijving|
|:-------------:|:------------:|:------------:|------------|
|**Wissen**| Niet ingeschakeld | Ja | Alle gebruikersaccounts, gegevens, MDM-beleidsregels en instellingen worden gewist. De standaardtoestand en -instellingen van het besturingssysteem worden teruggezet.|
|**Wissen**| Ingeschakeld | Nee | Alle MDM-beleidsregels worden gewist. Gebruikersaccounts en -gegevens blijven bewaard. Gebruikersinstellingen worden teruggezet op de standaardwaarden. De standaardtoestand en -instellingen van het besturingssysteem worden teruggezet.|

De optie **Inschrijvingsstatus en gebruikersaccount behouden** is alleen beschikbaar voor Windows 10 versie 1709 en hoger.

MDM-beleidsregels worden toegepast wanneer het apparaat de volgende keer verbinding maakt met Intune.

Wissen is nuttig wanneer u een apparaat opnieuw wilt instellen voordat u het aan een nieuwe gebruiker geeft of wanneer een apparaat is verloren of gestolen. Wees voorzichtig bij het selecteren van **Wissen**. De gegevens op het apparaat kunnen niet worden hersteld.

### <a name="wiping-a-device"></a>Een apparaat wissen

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaten** > **Alle apparaten**.
4. Selecteer de naam van het apparaat dat u wilt wissen.
5. Selecteer **Wissen** in het deelvenster waarin de naam van het apparaat wordt weergegeven.
6. Voor Windows 10 versie 1709 of hoger is ook de optie **Inschrijvingsstatus en gebruikersaccount behouden** aanwezig. 
    
    |Behouden tijdens wissen |Niet behouden|
    | -------------|------------|
    |Gebruikersaccounts die zijn gekoppeld aan het apparaat|Gebruikersbestanden|
    |Status van de machine \(lid van domein, lid van Azure AD)| Door de gebruiker geïnstalleerde apps \(Store- en Win32-apps)|
    |MDM-inschrijving (Mobile Device Management)|Niet-standaard apparaatinstellingen|
    |Door OEM geïnstalleerde apps \(Store- en Win32-apps)||
    |Gebruikersprofiel||
    |Gebruikersgegevens buiten gebruikersprofiel||
    |Autologon gebruiker|| 
    
         
7. Selecteer **Ja** om wissen te bevestigen.

Als het apparaat is ingeschakeld en is verbonden, wordt de actie **Wissen** in minder dan 15 minuten aan alle typen apparaten doorgegeven.

## <a name="retire"></a>Buiten gebruik stellen

Met de actie **Buiten gebruik stellen** worden gegevens (indien van toepassing), instellingen en e-mailprofielen van beheerde apps verwijderd die via Intune zijn toegewezen. Het apparaat wordt uit Intune-beheer verwijderd. Dit gebeurt wanneer het apparaat de volgende keer wordt ingecheckt en de actie **Buiten gebruik stellen** ontvangt.

Bij de actie **Buiten gebruik stellen** blijven de persoonlijke gegevens van de gebruiker op het apparaat behouden.  

In de volgende tabellen wordt beschreven welke gegevens worden verwijderd en wat het effect is van de actie **Buiten gebruik stellen** op de gegevens die achterblijven op het apparaat nadat de bedrijfsgegevens zijn verwijderd.

### <a name="ios"></a>iOS

|Gegevenstype|iOS|
|-------------|-------|
|Bedrijfs-apps en de bijbehorende gegevens die door Intune zijn geïnstalleerd|**Apps die zijn geïnstalleerd met de bedrijfsportal-app:** Voor apps die zijn vastgemaakt aan het beheerprofiel, worden alle app-gegevens en de app zelf verwijderd. Hiertoe behoren ook de apps die oorspronkelijk zijn geïnstalleerd vanuit de App Store en later worden beheerd als bedrijfs-apps. <br /><br /> **Microsoft-apps die gebruikmaken van MAM en zijn die geïnstalleerd vanuit de App Store:** Voor apps die niet worden beheerd door de bedrijfsportal, worden de gegevens verwijderd van bedrijfs-apps die in de lokale opslagruimte van de app worden beveiligd met MAM-versleuteling (Mobile Application Management). Gegevens die door MAM-versleuteling buiten de app worden beveiligd, blijven versleuteld en onbruikbaar, maar worden niet verwijderd. Gegevens van persoonlijke apps en de apps worden niet verwijderd.|
|Instellingen|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen. Gebruikers kunnen de instellingen wijzigen.|
|Instellingen voor Wi-Fi en VPN-profiel|Verwijderd.|
|Instellingen van certificaatprofiel|Certificaten worden verwijderd en ingetrokken.|
|Beheeragent|Beheerprofiel wordt verwijderd.|
|E-mail|E-mailprofielen die via Intune zijn ingericht, worden verwijderd. In de cache opgeslagen e-mail op het apparaat wordt verwijderd.|
|Loskoppelen van Azure AD|Azure AD-record wordt verwijderd.|

### <a name="android"></a>Android

|Gegevenstype|Android|Android Samsung Knox Standard|
|-------------|-----------|------------------------|
|Webkoppelingen|Verwijderd.|Verwijderd.|
|Niet-beheerde Google Play-apps|Apps en gegevens blijven geïnstalleerd. <br /> <br />De gegevens van bedrijfs-apps die in de lokale opslagruimte van de app worden beveiligd met MAM-versleuteling (Mobile Application Management) worden verwijderd. Gegevens die door MAM-versleuteling buiten de app worden beveiligd, blijven versleuteld en onbruikbaar, maar worden niet verwijderd. |Apps en gegevens blijven geïnstalleerd. <br /> <br />De gegevens van bedrijfs-apps die in de lokale opslagruimte van de app worden beveiligd met MAM-versleuteling (Mobile Application Management) worden verwijderd. Gegevens die door MAM-versleuteling buiten de app worden beveiligd, blijven versleuteld en onbruikbaar, maar worden niet verwijderd.|
|Niet-beheerde Line-Of-Business-apps|Apps en gegevens blijven geïnstalleerd.|Apps worden verwijderd en lokale app-gegevens worden verwijderd. Er worden geen gegevens buiten de app (bijvoorbeeld op een SD-geheugenkaart) verwijderd.|
|Beheerde Google Play-apps|App-gegevens worden verwijderd. De app wordt niet verwijderd. Gegevens die door MAM-versleuteling (Mobile Application Management) buiten de app worden beveiligd (bijvoorbeeld een SD-geheugenkaart), blijven versleuteld en onbruikbaar, maar worden niet verwijderd.|App-gegevens worden verwijderd. De app wordt niet verwijderd. Gegevens die door MAM-versleuteling buiten de app worden beveiligd (bijvoorbeeld een SD-geheugenkaart), blijven versleuteld, maar worden niet verwijderd.|
|Beheerde Line-Of-Business-apps|App-gegevens worden verwijderd. De app wordt niet verwijderd. Gegevens die door MAM-versleuteling buiten de app worden beveiligd (bijvoorbeeld een SD-geheugenkaart), blijven versleuteld en onbruikbaar, maar worden niet verwijderd.|App-gegevens worden verwijderd. De app wordt niet verwijderd. Gegevens die door MAM-versleuteling buiten de app worden beveiligd (bijvoorbeeld een SD-geheugenkaart), blijven versleuteld en onbruikbaar, maar worden niet verwijderd.|
|Instellingen|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen. Gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen. Gebruikers kunnen de instellingen wijzigen.|
|Instellingen voor Wi-Fi en VPN-profiel|Verwijderd.|Verwijderd.|
|Instellingen van certificaatprofiel|Certificaten worden ingetrokken, maar niet verwijderd.|Certificaten worden verwijderd en ingetrokken.|
|Beheeragent|Administratorbevoegdheden voor apparaat worden ingetrokken.|Administratorbevoegdheden voor apparaat worden ingetrokken.|
|E-mail|N.v.t. (e-mailprofielen worden niet ondersteund door Android-apparaten)|E-mailprofielen die via Intune zijn ingericht, worden verwijderd. In de cache opgeslagen e-mail op het apparaat wordt verwijderd.|
|Loskoppelen van Azure AD|Azure AD-record wordt verwijderd.|Azure AD-record wordt verwijderd.|

### <a name="android-work-profile"></a>Android-werkprofiel

Door Bedrijfsgegevens verwijderen uit te voeren op een apparaat met een Android-werkprofiel, verwijdert u alle gegevens, apps en instellingen in het werkprofiel op het apparaat. Het apparaat wordt buiten bedrijf gesteld voor beheer met Intune. Wissen wordt niet ondersteund voor Android-werkprofielen.

### <a name="android-enterprise-kiosk-devices"></a>Kioskapparaten voor Android Enterprise

U kunt apparaten in de kioskmodus alleen wissen. U kunt Android-apparaten in de kioskmodus niet buiten gebruik stellen.


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

|Gegevenstype|Windows 8.1 (MDM) en Windows RT 8.1|Windows RT|Windows Phone 8.1 en Windows Phone 8|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Bedrijfs-apps en de bijbehorende gegevens die door Intune zijn geïnstalleerd|Sleutels worden ingetrokken voor bestanden die zijn beveiligd met EFS. De gebruiker kan de bestanden niet openen.|Bedrijfs-apps worden niet verwijderd.|Apps die oorspronkelijk zijn geïnstalleerd via de bedrijfsportal, worden verwijderd. Gegevens van bedrijfs-apps worden verwijderd.|Apps worden verwijderd. Sideloadsleutels worden verwijderd.<br>Voor Windows 10 versie 1703 (makersupdate) en hoger worden Office 365 ProPlus-apps niet verwijderd. Win32-apps waarvoor de Intune-beheerextensie is geïnstalleerd, worden niet verwijderd van apparaten die niet meer ingeschreven zijn. Beheerders kunnen gebruikmaken van uitsluiting van opdrachten, zodat Win32-apps niet worden aangeboden op BYOD-apparaten.|
|Instellingen|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen. Gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen. Gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen. Gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen. Gebruikers kunnen de instellingen wijzigen.|
|Instellingen voor Wi-Fi en VPN-profiel|Verwijderd.|Verwijderd.|Niet ondersteund.|Verwijderd.|
|Instellingen van certificaatprofiel|Certificaten worden verwijderd en ingetrokken.|Certificaten worden verwijderd en ingetrokken.|Niet ondersteund.|Certificaten worden verwijderd en ingetrokken.|
|E-mail|Hiermee worden e-mails verwijderd waarvoor EFS is ingeschakeld. Dit omvat e-mails en bijlagen in de e-mail-app voor Windows.|Niet ondersteund.|E-mailprofielen die via Intune zijn ingericht, worden verwijderd. In de cache opgeslagen e-mail op het apparaat wordt verwijderd.|Hiermee worden e-mails verwijderd waarvoor EFS is ingeschakeld. Dit omvat e-mails en bijlagen in de e-mail-app voor Windows. Hiermee verwijdert u e-mailaccounts die zijn ingericht door Intune.|
|Loskoppelen van Azure AD|Nee.|Nee.|Azure AD-record wordt verwijderd.|Niet van toepassing. In Windows 10 kunt u geen apparaten buiten gebruik stellen die zijn toegevoegd aan Azure AD.|

### <a name="retire"></a>Buiten gebruik stellen

1. Meld u aan bij [Intune in Azure Portal](https://aka.ms/intuneportal).
2. Selecteer **Alle apparaten** in het deelvenster **Apparaten**.
3. Selecteer de naam van het apparaat dat u buiten gebruik wilt stellen.
4. Selecteer **Buiten gebruik stellen** in het deelvenster waarin de naam van het apparaat wordt weergegeven. Selecteer **Ja** om de opdracht te bevestigen.

Als het apparaat is ingeschakeld en is verbonden, wordt de actie **Buiten gebruik stellen** in minder dan 15 minuten aan alle typen apparaten doorgegeven.

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

1.  Meld u met uw beheerdersreferenties aan bij [Azure Active Directory in Azure Portal](http://aka.ms/accessaad). U kunt u ook aanmelden bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com). Selecteer **Beheercentrums** > **Azure AD** in het menu.
2.  Maak een Azure-abonnement maken als u er nog geen hebt. U kunt dit zonder creditcard of betaling doen als u beschikt over een betaald account (selecteer de abonnementskoppeling **Uw gratis Azure Active Directory registreren**).
3.  Selecteer **Azure Active Directory** en vervolgens uw organisatie.
4.  Selecteer het tabblad **Gebruikers** .
5. Selecteer de gebruiker die is gekoppeld aan het apparaat dat u wilt verwijderen.
6.  Selecteer **Apparaten**.
7.  Verwijder de gewenste apparaten. U kunt bijvoorbeeld apparaten verwijderen die niet meer in gebruik zijn of die onjuist zijn gedefinieerd.

## <a name="retire-an-apple-dep-device-from-intune"></a>Een Apple DEP-apparaat in Intune buiten gebruik stellen

Als u een Apple DEP-apparaat volledig wilt verwijderen uit het beheer door Intune, voert u de volgende stappen:

1. Meld u aan bij [Intune in Azure Portal](https://aka.ms/intuneportal).
2. Kies **Apparaten** > **Alle apparaten** > kies het apparaat > **Buiten gebruik stellen**.
![Schermafbeelding van buiten gebruik stellen](./media/devices-wipe/retire.png)
3. Kies **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor het inschrijvingsprogramma** > kies het token > **Apparaten** > schakel het selectievakje voor het apparaat in > **Verwijderen** > **Ja**.
![Schermafbeelding voor het verwijderen van een apparaat](./media/devices-wipe/delete-device.png)
4. Ga naar [deploy.apple.com](http://deploy.apple.com) en zoek het apparaat met behulp van het serienummer.
5. Kies in het menu **Toegewezen aan** de optie **Niet toegewezen**.

6. Kies **Opnieuw toewijzen**.

    ![Schermafbeelding voor opnieuw toewijzen bij Apple](./media/devices-wipe/apple-reassign.png)

## <a name="fresh-start"></a>Nieuwe start

Beschikbaar voor apparaten met Windows 10. Meer informatie over [Nieuwe start](https://docs.microsoft.com/intune/device-fresh-start).

## <a name="next-steps"></a>Volgende stappen

Zie [Inschrijvingsopties](enrollment-options.md) als u een verwijderd apparaat opnieuw wilt registreren.

