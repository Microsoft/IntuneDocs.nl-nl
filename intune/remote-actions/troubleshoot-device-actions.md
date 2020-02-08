---
title: Problemen met apparaatacties oplossen in Microsoft Intune - Azure | Microsoft Docs
description: Hulp verkrijgen bij het oplossen van problemen met apparaatacties.
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
ms.openlocfilehash: 7d4517d89e3b7365834e904c815b30a362540906
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755592"
---
# <a name="troubleshoot-device-actions-in-intune"></a>Problemen met acties oplossen in Intune

Microsoft Intune biedt veel acties die u helpen bij het beheren van apparaten. In dit artikel vindt u antwoorden op enkele veelgestelde vragen die u kunnen helpen bij het oplossen van acties op het apparaat.

## <a name="disable-activation-lock-action"></a>De actie Activeringsslot uitschakelen

### <a name="i-clicked-the-disable-activation-lock-action-in-the-portal-but-nothing-happened-on-the-device"></a>Ik heb geklikt op de actie Activeringsslot uitschakelen in de portal, maar er is niets gebeurd op het apparaat.
Dit is normaal. Na het starten van de actie Activeringsslot uitschakelen, wordt Intune om een bijgewerkte code van Apple gevraagd. U voert de code handmatig in het wachtwoordcodeveld in als uw apparaat op het scherm Activeringsslot wordt weergegeven. Deze code is slechts 15 dagen geldig. Zorg er dus voor dat u op de actie klikt en de code kopieert voordat u Wissen gebruikt.

### <a name="why-dont-i-see-the-disable-activation-lock-code-in-the-hardware-overview-blade-of-my-ios-device"></a>Waarom zie ik de code voor het uitschakelen van het activeringsslot niet in de blade Hardwareoverzicht van mijn iOS-apparaat?
De waarschijnlijke oorzaken zijn:
- De code is verlopen en is uit de service gewist.
- Het apparaat staat niet onder supervisie van het restrictiebeleid voor apparaten om Activeringsslot toe te staan.

U kunt de code in Grafiekverkenner controleren met de volgende query:

```GET - https://graph.microsoft.com/beta/deviceManagement/manageddevices('deviceId')?$select=activationLockBypassCode.```

### <a name="why-is-the-disable-activation-lock-action-greyed-out-for-my-ios-device"></a>Waarom wordt de actie Activeringsslot uitschakelen grijs weergegeven voor mijn iOS-apparaat?
De waarschijnlijke oorzaken zijn: 
- De code is verlopen en is uit de service gewist.
- Het apparaat staat niet onder supervisie van het restrictiebeleid voor apparaten om Activeringsslot toe te staan.

### <a name="is-the-disable-activation-lock-code-case-sensitive"></a>Is de code voor Activeringsslot uitschakelen hoofdlettergevoelig?
Nee. En u hoeft de streepjes niet in te voeren.

## <a name="remove-devices-action"></a>De actie Apparaten verwijderen

### <a name="how-do-i-tell-who-started-a-retirewipe"></a>Hoe kan ik nagaan wie een actie Buiten gebruik stellen/wissen heeft gestart?
Ga in het [Beheercentrum voor Microsoft Eindpuntbeheer](https://go.microsoft.com/fwlink/?linkid=2109431) naar **Tenantbeheer** > **Auditlogboeken** en controleer de kolom **Gestart door**.
Als u geen vermelding ziet, is de kans groot dat de gebruiker van het apparaat de actie heeft gestart. Deze heeft waarschijnlijk de Bedrijfsportal-app of portal.manage.microsoft.com gebruikt.

### <a name="why-wasnt-my-application-uninstalled-after-using-retire"></a>Waarom is mijn toepassing niet verwijderd na gebruik van Buiten gebruik stellen?
Omdat deze niet wordt beschouwd als een beheerde toepassing. In deze context is een beheerde toepassing een toepassing die is geïnstalleerd met behulp van de Intune-service. Dit omvat:
- De app is geïmplementeerd als Vereist
- De app is geïmplementeerd als Beschikbaar en is vervolgens geïnstalleerd door de eindgebruiker vanuit de Bedrijfsportal-app.

### <a name="why-is-wipe-grayed-out-for-android-enterprise-work-profile-devices"></a>Waarom wordt Wissen grijs weergegeven voor apparaten met een Android Enterprise-werkprofiel?
Dit is normaal. Google staat geen herstel van de fabrieksinstellingen van werkprofielapparaten van de MDM-provider toe.

### <a name="why-can-i-sign-back-into-my-office-apps-after-my-device-was-retired"></a>Waarom kan ik me weer aanmelden bij mijn Office-apps nadat mijn apparaat buiten gebruik is gesteld?
Omdat met het buiten gebruik stellen van een apparaat geen toegangstokens worden ingetrokken. U kunt beleid voor voorwaardelijke toegang gebruiken om dit probleem te verhelpen.

### <a name="how-can-i-monitor-a-retirewipe-action-after-it-was-issued"></a>Hoe kan ik een actie Buiten gebruik stellen/wissen bewaken nadat deze is uitgevoerd?
Ga in het [Beheercentrum voor Microsoft Eindpuntbeheer](https://go.microsoft.com/fwlink/?linkid=2109431) naar **Tenantbeheer** > **Auditlogboeken**.

### <a name="why-do-wipes-sometimes-show-as-pending-indefinitely"></a>Waarom worden wisacties soms voor onbepaalde tijd weergegeven als In behandeling?
De status van apparaten wordt niet altijd gemeld aan de Intune-service voordat Opnieuw instellen is gestart. Daarom wordt de actie weergegeven als In behandeling. Als u hebt bevestigd dat de actie is geslaagd, verwijdert u het apparaat uit de service.

### <a name="what-happens-if-i-start-a-retirewipe-on-an-offline-device-or-a-device-that-hasnt-communicated-with-the-service-in-a-while"></a>Wat gebeurt er als ik Buiten gebruik stellen/wissen start op een apparaat dat offline is of een tijdje niet met de service heeft gecommuniceerd?
Het apparaat blijft in de status **Buiten gebruik stellen/wissen in behandeling** tot het MDM-certificaat verloopt. Het MDM-certificaat blijft geldig tot één jaar na inschrijving en wordt elk jaar automatisch vernieuwd. Als het apparaat wordt ingecheckt voordat het MDM-certificaat verloopt, wordt het buiten gebruik gesteld/gewist. Als het apparaat niet wordt ingecheckt voordat het MDM-certificaat is verlopen, kan het niet worden ingecheckt bij de service. 180 dagen nadat het MDM-certificaat is verlopen, wordt het apparaat automatisch verwijderd uit Azure Portal.


## <a name="reset-passcode-action"></a>De actie Wachtwoordcode opnieuw instellen

### <a name="why-is-the-reset-passcode-action-greyed-out-on-my-android-device-admin-enrolled-device"></a>Waarom wordt de actie Wachtwoordcode opnieuw instellen grijs weergegeven op mijn apparaat dat is ingeschreven bij Android-apparaatbeheer?
Voor het bestrijden van ransomeware heeft Google de functie voor het opnieuw instellen van de wachtwoordcode verwijderd uit de Apparaatbeheer-API (van toepassing op apparaten met Android-versie 7.0 of hoger).

### <a name="why-do-i-get-a-not-supported-message-when-i-issue-a-passcode-reset-to-my-android-80-or-later-work-profile-enrolled-device"></a>Waarom krijg ik het bericht 'Niet ondersteund' wanneer ik Wachtwoordcode herstellen uitvoer voor mijn ingeschreven apparaat met het werkprofiel Android 8.0 of later?
Omdat het token voor opnieuw instellen niet is geactiveerd op het apparaat. Het token voor opnieuw instellen activeren:
1. U moet de wachtwoordcode voor een werkprofiel vereisen in uw Configuratiebeleid.
2. De eindgebruiker moet een juiste wachtwoordcode voor een werkprofiel instellen.
3. De eindgebruiker moet de secundaire prompt accepteren om opnieuw instellen van de wachtwoordcode mogelijk te maken.
Na voltooiing van deze stappen ontvangt u dit antwoord niet meer.

### <a name="why-am-i-prompted-to-set-a-new-passcode-on-my-ios-device-when-i-issue-the-remove-passcode-action"></a>Waarom krijg ik het verzoek een nieuwe wachtwoordcode in te stellen op mijn iOS-apparaat wanneer ik de actie Wachtwoordcode verwijderen uitvoer?
Omdat volgens een van uw nalevingsbeleidsregels een wachtwoordcode vereist is.

## <a name="next-steps"></a>Volgende stappen

Krijg [ondersteuning van Microsoft](../fundamentals/get-support.md) of gebruik de [communityforums](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
