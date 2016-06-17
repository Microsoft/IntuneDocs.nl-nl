---
# required metadata

title: Problemen met e-mailprofielen oplossen | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 05/26/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Problemen met e-mailprofielen in Microsoft Intune oplossen
Hier vindt u een aantal mogelijke problemen met e-mailprofielen en wordt beschreven hoe u deze kunt oplossen.

Zie [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md) voor meer manieren om hulp te krijgen als u het probleem niet kunt oplossen met deze informatie.


## Kan geen afbeeldingen verzenden vanuit e-mailaccount
Gebruikers met automatisch geconfigureerde e-mailaccounts kunnen geen afbeeldingen of foto's verzenden vanaf hun apparaten.
Dit is het geval als de optie **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden** niet is ingeschakeld.

### Intune-oplossing

1.  Open de Microsoft Intune-beheerconsole, selecteer de workload **Beleid** &gt; **Configuratiebeleid**.

2.  Selecteer het e-mailprofiel en kies **Bewerken**.

3.  Selecteer **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden**.

### Configuration Manager geïntegreerd met Intune-oplossing

1.  Open de Configuration Manager-console &gt; **Activa en naleving**.

2.  Vouw **Overzicht** -&gt; **Instellingen voor naleving** -&gt; **Toegang tot bedrijfsbronnen** uit en selecteer **E-mailprofielen**.

3.  Klik met de rechtermuisknop op het e-mailprofiel en open **Eigenschappen**.

4.  Selecteer op het tabblad **Synchronisatie-instellingen** de optie **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden**.

## Volgende stappen
Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).


<!--HONumber=Jun16_HO1-->


