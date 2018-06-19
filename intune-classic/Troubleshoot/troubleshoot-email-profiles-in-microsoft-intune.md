---
title: Problemen met e-mailprofielen oplossen
description: Problemen met e-mailprofielen en hoe u deze kunt oplossen.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e001d1df510ac249687be9f5690c16f0a738c3e2
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31013735"
---
# <a name="troubleshoot-email-profiles-in-microsoft-intune"></a>Problemen met e-mailprofielen in Microsoft Intune oplossen

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Hier vindt u een aantal problemen met e-mailprofielen die zich kunnen voordoen. Ook wordt er beschreven hoe u deze kunt oplossen.

Zie [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md) voor meer manieren om hulp te krijgen als u het probleem niet kunt oplossen met deze informatie.


## <a name="unable-to-send-images-from--email-account"></a>Kan geen afbeeldingen verzenden vanuit e-mailaccount
Gebruikers met automatisch geconfigureerde e-mailaccounts kunnen geen afbeeldingen of foto’s verzenden vanaf hun apparaat.
Dit is het geval als de optie **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden** niet is ingeschakeld.

### <a name="intune-solution"></a>Intune-oplossing

1.  Open de Microsoft Intune-beheerconsole, selecteer de workload **Beleid** &gt; **Configuratiebeleid**.

2.  Selecteer het e-mailprofiel en kies **Bewerken**.

3.  Selecteer **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden**.

### <a name="configuration-manager-integrated-with-intune-solution"></a>Configuration Manager geïntegreerd met Intune-oplossing

1.  Open de Configuration Manager-console &gt; **Activa en naleving**.

2.  Vouw **Overzicht** -&gt; **Instellingen voor naleving** -&gt; **Toegang tot bedrijfsbronnen** uit en selecteer **E-mailprofielen**.

3.  Klik met de rechtermuisknop op het e-mailprofiel en open **Eigenschappen**.

4.  Selecteer op het tabblad **Synchronisatie-instellingen** de optie **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden**.


## <a name="device-already-has-an-email-profile-installed"></a>Er is al een e-mailprofiel geïnstalleerd op het apparaat

Als de gebruiker een e-mailprofiel heeft geïnstalleerd voorafgaand aan het inrichten van een profiel door Intune, is het resultaat van de implementatie van het Intune-e-mailprofiel afhankelijk van het apparaatplatform:

-**iOS**: Intune detecteert een bestaand, dubbel e-mailprofiel op basis van hostnaam en e-mailadres. Het dubbele e-mailprofiel dat is gemaakt door de gebruiker blokkeert de implementatie van een Intune-profiel dat door een beheerder is gemaakt. Dit is een veelvoorkomend probleem omdat iOS-gebruikers vaak zelf een e-mailprofiel maken en zich vervolgens inschrijven. In de bedrijfsportal ziet de gebruiker dat deze niet voldoet aan de voorwaarden wegens het handmatig geconfigureerde e-mailprofiel. De gebruiker wordt gevraagd dat profiel te verwijderen. Het e-mailprofiel moet worden verwijderd zodat het Intune-profiel kan worden geïmplementeerd. Als u dit probleem wilt voorkomen, vertelt u gebruikers dat zij moeten registreren voordat ze een e-mailprofiel installeren, zodat Intune het profiel kan implementeren.

-**Windows**: Intune detecteert een bestaand, dubbel e-mailprofiel op basis van hostnaam en e-mailadres. Intune overschrijft het bestaande e-mailprofiel dat is gemaakt door de gebruiker.

-**Samsung KNOX**: Intune identificeert een dubbele e-mailaccount op basis van het e-mailadres, en overschrijft het met het Intune-profiel. Als de gebruiker dat account configureert, wordt het opnieuw overschreven door het Intune-profiel. Dit kan leiden tot enige verwarring bij de gebruiker waarvan de accountconfiguratie word overschreven.

Omdat Samsung KNOX niet de hostnaam gebruikt om het profiel te identificeren, wordt geadviseerd om niet meerdere e-mailprofielen te implementeren naar hetzelfde e-mailadres op verschillende hosts, aangezien die elkaar zullen overschrijven.

## <a name="error--0x87d1fde8-for-knox-standard-device"></a>Fout 0x87D1FDE8 voor KNOX Standard-apparaat
**Probleem**: na het maken en implementeren van een Exchange Active Sync-e-mailprofiel voor Samsung KNOX Standard voor verschillende Android-apparaten wordt door de apparaten de fout **0x87D1FDE8** of de fout **Doorvoeren is mislukt** gemeld op het tabblad &gt;-beleid van de eigenschappen van het apparaat.

Controleer de configuratie van uw EAS-profiel voor Samsung KNOX en het bronbeleid. De synchronisatieoptie voor Samsung Notes wordt niet meer ondersteund en deze optie moet niet worden geselecteerd in uw profiel. Gun de apparaten voldoende tijd (maximaal 24 uur) om het beleid te verwerken.

## <a name="next-steps"></a>Volgende stappen
Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).
