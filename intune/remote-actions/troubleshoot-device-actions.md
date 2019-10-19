---
title: Problemen met apparaatacties oplossen in Microsoft Intune - Azure | Microsoft Docs
description: Hulp bij het oplossen van problemen met Apparaatinstellingen.
keywords: ''
author: erikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/02/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ROBOTS: ''
ms.reviewer: coferro
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 96f6dc3d1a8f8589395cf49b3bb934adadf437a4
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72508507"
---
# <a name="troubleshoot-device-actions-in-intune"></a>Problemen met acties in intune oplossen

Microsoft Intune heeft veel acties die u helpen bij het beheren van apparaten. In dit artikel vindt u antwoorden op enkele veelgestelde vragen die u kunnen helpen bij het oplossen van acties op het apparaat.

## <a name="bypass-activation-lock-action"></a>Bypass van activeringsvergrendelingsactie

### <a name="i-clicked-the-bypass-activation-lock-action-in-the-portal-but-nothing-happened-on-the-device"></a>Ik heb op de actie Activeringsslot overs Laan geklikt in de portal, maar er is niets gebeurd op het apparaat.
Dit wordt verwacht. Nadat de actie Activeringsslot overs laan is gestart, vraagt intune een bijgewerkte code op van Apple. U voert de code hand matig in het veld wachtwoord code in nadat het apparaat is ingeschakeld op het Activeringsslot scherm. Deze code is 15 dagen geldig. Zorg er dus voor dat u op de actie klikt en de code kopieert voordat u het wissen uitvoert.

### <a name="why-dont-i-see-the-bypass-activation-lock-code-in-the-hardware-overview-blade-of-my-ios-device"></a>Waarom zie ik de code voor bypass Activeringsslot niet in de Blade hardware overview van mijn iOS-apparaat?
De meest waarschijnlijke oorzaken zijn:
- De code is verlopen en uit de service gewist.
- Het apparaat heeft geen super visie met het restrictie beleid voor apparaten om Activeringsslot toe te staan.

U kunt de code in Graph Explorer controleren met de volgende query:

```GET - https://graph.microsoft.com/beta/deviceManagement/manageddevices('deviceId')?$select=activationLockBypassCode.```

### <a name="why-is-the-bypass-activation-lock-action-greyed-out-for-my-ios-device"></a>Waarom wordt de actie Activeringsslot overs Laan grijs weer gegeven voor mijn iOS-apparaat?
De meest waarschijnlijke oorzaken zijn: 
- De code is verlopen en uit de service gewist.
- Het apparaat heeft geen super visie met het restrictie beleid voor apparaten om Activeringsslot toe te staan.

### <a name="is-the-bypass-activation-lock-code-case-sensitive"></a>Is de bypass-Activeringsslot code hoofdletter gevoelig?
Nee. En u hoeft de streepjes niet in te voeren.

## <a name="remove-devices-action"></a>Actie apparaten verwijderen

### <a name="how-do-i-tell-who-started-a-retirewipe"></a>Hoe kan ik weet wie een buiten gebruik stellen/wissen heeft gestart?
Ga naar **intune** - > **apparaten**  > **apparaat acties** > Controleer de kolom **gestart door** .
Als u geen vermelding ziet, is de meest waarschijnlijke persoon die de actie heeft gestart, de gebruiker van het apparaat. Ze hebben waarschijnlijk de Bedrijfsportal app of portal.manage.microsoft.com gebruikt.

### <a name="why-wasnt-my-application-uninstalled-after-using-retire"></a>Waarom is mijn toepassing niet meer verwijderd na het gebruik van buiten gebruik stellen?
Omdat deze niet wordt beschouwd als een beheerde toepassing. In deze context is een beheerde toepassing een toepassing die is geïnstalleerd met behulp van de intune-service. Dit omvat:
- De app is geïmplementeerd als vereist
- De app is geïmplementeerd als beschikbaar en wordt geïnstalleerd door de eind gebruiker vanuit de Bedrijfsportal-app.

### <a name="why-is-wipe-grayed-out-for-android-enterprise-work-profile-devices"></a>Waarom is wissen grijs weer gegeven voor apparaten van het werk Profiel van een Android-bedrijf?
Dit is normaal. Met Google kan de fabrieks instellingen van het werk profiel niet worden ingesteld op basis van de MDM-provider.

### <a name="why-can-i-sign-back-into-my-office-apps-after-my-device-was-retired"></a>Waarom kan ik me weer aanmelden bij mijn Office-apps nadat mijn apparaat buiten gebruik is gesteld?
Het intrekken van toegangs tokens wordt niet ingetrokken omdat een apparaat buiten gebruik wordt gesteld. U kunt beleid voor voorwaardelijke toegang gebruiken om dit probleem te verhelpen.

### <a name="how-can-i-monitor-a-retirewipe-action-after-it-was-issued"></a>Hoe kan ik een actie buiten gebruik stellen/wissen bewaken nadat deze is uitgegeven?
Ga naar  > **apparaat acties**van **intune**-**apparaten** > .

### <a name="why-do-wipes-sometimes-show-as-pending-indefinitely"></a>Waarom wordt soms voor onbepaalde tijd weer gegeven als in behandeling?
Apparaten rapporteren hun status niet altijd terug naar de intune-service voordat het opnieuw instellen werd gestart. De actie wordt dus weer gegeven als in behandeling. Als u hebt bevestigd dat de actie is geslaagd, verwijdert u het apparaat uit de service.

### <a name="what-happens-if-i-start-a-retirewipe-on-an-offline-device-or-a-device-that-hasnt-communicated-with-the-service-in-a-while"></a>Wat gebeurt er als ik een buiten gebruik stellen/wissen op een offline apparaat of een apparaat dat in een tijdje niet met de service is gecommuniceerd?
Het apparaat blijft in de status **buiten gebruik stellen/wissen in behandeling** totdat het MDM-certificaat verloopt. Het MDM-certificaat duurt één jaar van inschrijving en wordt elk jaar automatisch vernieuwd. Als het apparaat wordt ingecheckt voordat het MDM-certificaat verloopt, wordt het buiten gebruik gesteld/gewist. Als het apparaat niet wordt ingecheckt voordat het MDM-certificaat is verlopen, kan het niet worden ingecheckt bij de service. 180 dagen nadat het MDM-certificaat is verlopen, wordt het apparaat automatisch verwijderd uit de Azure Portal.


## <a name="reset-passcode-action"></a>Wachtwoord code opnieuw instellen

### <a name="why-is-the-reset-passcode-action-greyed-out-on-my-android-device-admin-enrolled-device"></a>Waarom is de actie wachtwoord code opnieuw instellen grijs weer gegeven op de beheerder van het Android-apparaat dat apparaat heeft inge schreven?
Voor het bestrijden van Ransome artikelen heeft Google de functie wachtwoord code opnieuw instellen verwijderd van de API voor Apparaatbeheer (van toepassing op Android-versie 7,0 of hoger).

### <a name="why-do-i-get-a-not-supported-message-when-i-issue-a-passcode-reset-to-my-android-80-or-later-work-profile-enrolled-device"></a>Waarom krijg ik het bericht "niet ondersteund" wanneer ik een wachtwoord code opnieuw ingesteld op mijn Android 8,0 of hoger werk profiel Inge schreven apparaat?
Omdat het token voor opnieuw instellen niet is geactiveerd op het apparaat. Het reset-token activeren:
1. U moet de wachtwoord code van een werk profiel in uw configuratie beleid hebben.
2. De eind gebruiker moet de juiste wachtwoord code voor het werk profiel instellen.
3. De eind gebruiker moet de secundaire prompt accepteren om de wachtwoord code opnieuw in te stellen.
Nadat deze stappen zijn voltooid, kunt u deze niet meer ontvangen.

### <a name="why-am-i-prompted-to-set-a-new-passcode-on-my-ios-device-when-i-issue-the-remove-passcode-action"></a>Waarom wordt u gevraagd om een nieuwe wachtwoord code in te stellen op mijn iOS-apparaat wanneer ik de actie wachtwoord code verwijderen uitgeeft?
Omdat een van uw nalevings beleid een wachtwoord code vereist.

## <a name="next-steps"></a>Volgende stappen

Krijg [ondersteuning van Microsoft](../fundamentals/get-support.md) of gebruik de [communityforums](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
