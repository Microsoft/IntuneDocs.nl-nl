---
title: E-mailinstellingen configureren in Intune
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u Intune kunt configureren voor het maken van verbindingen met zakelijke e-mail op de apparaten die u beheert.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 484bd9b0-fbf1-4f4f-940c-6b12fa07e228
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: a9748a0ad6b9bbe10e36ba133ba74edb6aa6e09a
ms.openlocfilehash: faacf9a71deed1b9597ee42849d426a76e81d831
ms.contentlocale: nl-nl
ms.lasthandoff: 05/05/2017


---

# <a name="how-to-configure-email-settings-in-microsoft-intune"></a>E-mailinstellingen configureren in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Met e-mailprofielen kunt u de apparaten die u beheert, configureren met de instellingen die nodig zijn om verbinding te maken en synchronisaties uit te voeren met zakelijke e-mail. Op deze manier zorgt u ervoor dat op alle apparaten standaardinstellingen worden gebruikt en er minder ondersteuningsaanvragen worden ingediend van eindgebruikers die de juiste e-mailinstellingen niet weten.

De ingebouwde e-mailclient wordt voor de meeste platformen ondersteund. De meeste e-mail-apps van derden worden momenteel niet ondersteund.

U kunt e-mailprofielen gebruiken om de systeemeigen e-mailclient te configureren op de volgende apparaattypen:

- Android Samsung KNOX Standard 4.0 en hoger
- Android for Work
- iOS 8.0 en hoger
- Windows Phone 8.1 en hoger
- Windows 10 (Desktop) en Windows 10 Mobile

Gebruik de informatie in dit onderwerp voor meer informatie over de basisbeginselen voor het configureren van een e-mailprofiel en lees vervolgens de aanvullende onderwerpen voor elk platform voor meer apparaatspecifieke informatie.

## <a name="create-a-device-profile-containing-email-settings"></a>Een apparaatprofiel met e-mailinstellingen maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies op de blade **Intune** de optie **Apparaatconfiguratie**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
3. Kies **Profiel maken** op de blade Profielen.
4. Voer op de blade **Profiel maken** een **naam** en een **beschrijving** in voor het e-mailprofiel.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de e-mailinstellingen wilt toepassen. Op dit moment kunt u een van de volgende platformen kiezen voor e-mailapparaatinstellingen:
    - **Android**
    - **iOS**
    - **Windows Phone 8.1**
    - **Windows 10 en hoger**
6. Kies **E-mail** in de vervolgkeuzelijst **Profieltype**.
7. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u hebt gekozen. Raadpleeg een van de volgende onderwerpen voor gedetailleerde instellingen voor elk platform:
    - [Android-instellingen](email-profile-settings-for-android.md)
    - [iOS-instellingen](email-profile-settings-for-ios.md)
    - [Windows Phone 8.1-instellingen](email-profile-settings-for-windows-phone-8-1.md)
    - [Windows 10-instellingen](email-profile-settings-for-windows-10.md)
8. Als u klaar bent, gaat u terug naar de blade **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.
Zie [How to assign device profiles](how-to-assign-device-profiles.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.

## <a name="further-information"></a>Meer informatie

### <a name="remove-an-email-profile"></a>Een e-mailprofiel verwijderen

Als u een e-mailprofiel van een apparaat wilt verwijderen, bewerkt u de toewijzing en verwijdert u de groepen waarvan het apparaat lid is. U kunt een e-mailprofiel niet op deze manier verwijderen als dit het enige e-mailprofiel op een apparaat is.

### <a name="securing-email-access"></a>Toegang tot e-mail beveiligen

U kunt e-mailprofielen op twee manieren beveiligen:

1. **Certificaten**: wanneer u het e-mailprofiel maakt, kiest u een certificaatprofiel dat u eerder hebt gemaakt in Intune. Dit wordt het identiteitscertificaat genoemd en wordt gebruikt voor verificatie aan de hand van een vertrouwd-certificaatprofiel (of basiscertificaat) om te bepalen of het apparaat van de gebruiker verbinding mag maken. Het vertrouwde certificaat wordt toegewezen aan de computer die de e-mailverbinding verifieert. Dit is meestal de systeemeigen e-mailserver.
Zie [How to configure certificates with Intune](/intune-azure/configure-devices/how-to-configure-certificates) (Certificaten configureren met Intune) voor meer informatie over het gebruiken en maken van certificaatprofielen in Intune.
2. **Gebruikersnaam en wachtwoord**: de gebruiker wordt geverifieerd op de systeemeigen e-mailserver door de gebruikersnaam en het wachtwoord op te geven.
Het wachtwoord is niet opgenomen in het e-mailprofiel, dus de gebruiker moet dit opgeven wanneer deze de e-mailverbinding tot stand brengt.


### <a name="how-intune-handles-existing-email-accounts"></a>Hoe Intune omgaat met bestaande e-mailaccounts

Als de gebruiker al een e-mailaccount heeft geconfigureerd, hangt het resultaat van de e-mailprofieltoewijzing in Intune af van het apparaatplatform:

- **iOS**: een bestaand, dubbel e-mailprofiel wordt gedetecteerd op basis van hostnaam en het e-mailadres. De toewijzing van een Intune-profiel wordt geblokkeerd op basis van het dubbele e-mailprofiel. In dit geval deelt de bedrijfsportal de gebruiker mee dat deze niet voldoet aan de eisen en wordt de gebruiker gevraagd dit profiel handmatig te verwijderen. Als u dit probleem wilt voorkomen, vertelt u gebruikers dat ze het apparaat eerst moeten inschrijven voordat ze een e-mailprofiel installeren, zodat Intune het profiel kan instellen.
- **Windows**: een bestaand, dubbel e-mailprofiel wordt gedetecteerd op basis van de hostnaam en het e-mailadres. Intune overschrijft het bestaande e-mailprofiel dat is gemaakt door de gebruiker.
- **Android**: een bestaand, dubbel e-mailprofiel wordt gedetecteerd op basis van het e-mailadres. Het bestaande e-mailprofiel wordt overschreven door het Intune-profiel.
Omdat Android geen hostnaam gebruikt om een profiel te identificeren, wordt afgeraden om voor hetzelfde e-mailadres meerdere e-mailprofielen te maken op verschillende hosts, aangezien deze profielen elkaar overschrijven.

### <a name="update-an-email-profile"></a>Een e-mailprofiel bijwerken

Als u wijzigingen aanbrengt aan een e-mailprofiel dat u eerder had toegewezen, zien eindgebruikers mogelijk een bericht waarin ze wordt gevraagd de herconfiguratie van hun e-mailinstellingen goed te keuren.

