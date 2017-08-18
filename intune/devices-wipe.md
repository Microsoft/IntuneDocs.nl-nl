---
title: Fabrieksinstellingen terugzetten gebruiken of bedrijfsgegevens verwijderen met behulp van Intune
titleSuffix: Intune on Azure
description: Informatie over het verwijderen van bedrijfsgegevens op een apparaat of het terugzetten naar de fabrieksinstellingen.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 331ced93f0697f7c76d1356aae32b955602d17a3
ms.sourcegitcommit: 2ed8d1c39d4b3e3282111f1d758afb3a50f19f8f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2017
---
# <a name="remove-devices-by-using-factory-reset-or-remove-company-data"></a>Apparaten verwijderen door Fabrieksinstellingen terugzetten te gebruiken of bedrijfsgegevens te verwijderen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

U kunt apparaten van Intune verwijderen die niet meer nodig zijn, een nieuwe bestemming krijgen of zijn kwijtgeraakt. U kunt dit doen met de opdracht **Bedrijfsgegevens verwijderen** of **Fabrieksinstellingen terugzetten**. Gebruikers kunnen ook vanuit de Intune-bedrijfsportal op afstand een opdracht geven voor persoonlijke apparaten die bij Intune zijn ingeschreven.

> [!NOTE]
> Voer de opdracht **Fabrieksinstellingen terugzetten** of **Bedrijfsgegevens verwijderen** uit voor alle apparaten die aan een gebruiker zijn gekoppeld voordat u een gebruiker verwijderd van Azure Active Directory. Als u gebruikers met beheerde apparaten van Azure Active Directory verwijdert, kan Intune niet langer fabrieksinstellingen uitgeven of bedrijfsgegevens van die apparaten verwijderen.

## <a name="factory-reset"></a>Fabrieksinstellingen terugzetten

Met **Fabrieksinstellingen terugzetten** worden de fabrieksinstellingen van een apparaat hersteld, en worden alle bedrijfs- en gebruikersgegevens en -instellingen verwijderd. Het apparaat wordt uit Intune-beheer verwijderd. Fabrieksinstellingen terugzetten is nuttig voor het opnieuw instellen van een apparaat, wanneer het apparaat aan een nieuwe gebruiker wordt gegeven of wanneer het apparaat is verloren of gestolen. Wees voorzichtig bij het selecteren van Fabrieksinstellingen terugzetten. De gegevens op het apparaat kunnen niet worden hersteld.

### <a name="to-factory-reset-a-device"></a>Fabrieksinstellingen terugzetten op een apparaat gebruiken

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies op de blade **Apparaten en groepen** de optie **Alle apparaten**.
4. Kies de naam van het apparaat waarvoor u Fabrieksinstellingen terugzetten wilt gebruiken.
5. Kies op de blade met de naam van het apparaat **Fabrieksinstellingen** en kies vervolgens **Ja** om te bevestigen.

Als het apparaat is ingeschakeld en verbonden, wordt Fabrieksinstellingen terugzetten in minder dan 15 minuten aan alle typen apparaten doorgegeven.

## <a name="remove-company-data"></a>Bedrijfsgegevens verwijderen

Met de opdracht **Bedrijfsgegevens verwijderen** worden gegevens (indien van toepassing), instellingen en e-mailprofielen van beheerde apps die door het gebruik van Intune zijn toegewezen, verwijderd. Met Bedrijfsgegevens verwijderen blijven de persoonlijke gegevens van de gebruiker op het apparaat behouden. Het apparaat wordt uit Intune-beheer verwijderd. In de volgende tabel wordt beschreven welke gegevens worden verwijderd en wat het effect van Bedrijfsgegevens verwijderen is op de gegevens die achterblijven op het apparaat.

### <a name="ios"></a>iOS

|Gegevenstype|iOS|
|-------------|-------|
|Bedrijfs-apps en de bijbehorende gegevens die door Intune zijn geïnstalleerd|Apps worden verwijderd. Gegevens van bedrijfs-apps worden verwijderd.<br /><br />App-gegevens van Microsoft-apps die gebruikmaken van mobiel appbeheer, worden verwijderd. De app wordt niet verwijderd.|
|Instellingen|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|
|Instellingen voor Wi-Fi en VPN-profiel|Verwijderd.|
|Instellingen van certificaatprofiel|Certificaten worden verwijderd en ingetrokken.|
|Beheeragent|Beheerprofiel wordt verwijderd.|
|E-mail|E-mailprofielen die zijn ingericht via Intune, worden verwijderd en in de cache opgeslagen e-mail op het apparaat wordt verwijderd.|
|Outlook|E-mail die wordt ontvangen door de Microsoft Outlook-app voor iOS, wordt verwijderd.|
|Loskoppelen van Azure Active Directory (AD)|Azure AD-record wordt verwijderd.|
|Contactpersonen | Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd.  Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden verwijderd. <br /> <br />Op dit moment wordt alleen de Outlook-app ondersteund.

### <a name="android"></a>Android

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
|E-mail|n.v.t. (e-mailprofielen worden niet ondersteund door Android-apparaten)|E-mailprofielen die zijn ingericht via Intune, worden verwijderd en in de cache opgeslagen e-mail op het apparaat wordt verwijderd.|
|Outlook|E-mail die wordt ontvangen door de Microsoft Outlook-app voor Android wordt verwijderd.|E-mail die wordt ontvangen door de Microsoft Outlook-app voor Android wordt verwijderd.|
|Loskoppelen van Azure Active Directory (AD)|Azure AD-record wordt verwijderd.|Azure AD-record wordt verwijderd.|
|Contactpersonen | Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd.  Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden verwijderd. <br /> <br />Op dit moment wordt alleen de Outlook-app ondersteund.|Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd.  Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden verwijderd. <br /> <br />Op dit moment wordt alleen de Outlook-app ondersteund.

### <a name="android-for-work"></a>Android for Work

Door Bedrijfsgegevens verwijderen uit te voeren op een Android for Work-apparaat, worden alle gegevens, apps en instellingen in het werkprofiel op het apparaat verwijderd. Het apparaat wordt hierdoor uit het beheer met Intune verwijderd. Fabrieksinstellingen terugzetten wordt niet ondersteund voor Android for Work.

### <a name="windows"></a>Windows

|Gegevenstype|Windows 8.1 (MDM) en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Bedrijfs-apps en de bijbehorende gegevens die door Intune zijn geïnstalleerd|Van bestanden die worden beveiligd met EFS, wordt de sleutel ingetrokken en de gebruiker kan de bestanden niet openen.|Bedrijfs-apps worden niet verwijderd.|Apps die oorspronkelijk zijn geïnstalleerd via de bedrijfsportal, worden verwijderd. Gegevens van bedrijfs-apps worden verwijderd.|De installatie van apps wordt ongedaan gemaakt en sideloading-codes worden verwijderd.<br>Voor Windows 10 versie 1703 (Creators Update) en hoger, worden Office 365 ProPlus-apps niet verwijderd.|
|Instellingen|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|Configuraties die zijn ingesteld door Intune-beleid, worden niet meer afgedwongen en gebruikers kunnen de instellingen wijzigen.|
|Instellingen voor Wi-Fi en VPN-profiel|Verwijderd.|Verwijderd.|Niet ondersteund.|Verwijderd.|
|Instellingen van certificaatprofiel|Certificaten worden verwijderd en ingetrokken.|Certificaten worden verwijderd en ingetrokken.|Niet ondersteund.|Certificaten worden verwijderd en ingetrokken.|
|E-mail|Hiermee verwijdert u e-mail waarvoor EFS is ingeschakeld. Dit omvat de e-mail-app voor Windows-e-mail en -bijlagen.|Niet ondersteund.|E-mailprofielen die zijn ingericht via Intune, worden verwijderd en in de cache opgeslagen e-mail op het apparaat wordt verwijderd.|Hiermee verwijdert u e-mail waarvoor EFS is ingeschakeld. Dit omvat de e-mail-app voor Windows-e-mail en -bijlagen. Hiermee verwijdert u e-mailaccounts die zijn ingericht door Intune.|
|Loskoppelen van Azure Active Directory (AD)|Nee.|Nee.|Azure AD-record wordt verwijderd.|Niet van toepassing. Windows 10 biedt geen ondersteuning voor het verwijderen van bedrijfsgegevens voor apparaten die zijn toegevoegd aan Azure Active Directory.|

### <a name="to-remove-company-data"></a>Bedrijfsgegevens verwijderen

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies op de blade **Apparaten en groepen** de optie **Alle apparaten**.
4. Kies de naam van het apparaat waarvan u bedrijfsgegevens wilt verwijderen.
5. Kies op de blade met de naam van het apparaat **Bedrijfsgegevens verwijderen** en kies vervolgens **Ja** om te bevestigen.

Als het apparaat is ingeschakeld en verbonden, wordt de opdracht Bedrijfsgegevens verwijderen in minder dan 15 minuten aan alle typen apparaten doorgegeven.

## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Apparaten verwijderen van de Azure Active Directory-portal

Vanwege communicatieproblemen of ontbrekende apparaten moet u wellicht apparaten verwijderen van Azure Active Directory (AD). Met de opdracht Verwijderen wordt een apparaat niet uit het beheer verwijderd, maar u kunt **Verwijderen** wel gebruiken voor het verwijderen van apparaatrecords uit de Azure-console die onbereikbaar zijn en vermoedelijk niet opnieuw met Azure gaan communiceren.

1.  Meld u met uw referenties aan bij [Azure Active Directory in Azure Portal](http://aka.ms/accessaad). U kunt u ook aanmelden bij de [Office 365-portal](https://portal.office.com) en vervolgens **Beheerder** &gt; **Azure AD** kiezen met behulp van de koppeling aan de linkerkant van de pagina.
3.  Maak een Azure-abonnement maken als u er nog geen hebt. U kunt dit zonder creditcard of betaling doen als u beschikt over een betaald account (kies de abonnementskoppeling **Uw gratis Azure Active Directory registreren**).
4.  Selecteer **Active Directory** en vervolgens uw organisatie.
5.  Selecteer het tabblad **Gebruikers** .
6.  Selecteer de gebruiker waarvoor u de apparaten wilt verwijderen.
7.  Kies **Apparaten**.
8.  Verwijder waar nodig apparaten, zoals apparaten die niet langer in gebruik zijn of die onjuist zijn gedefinieerd.
