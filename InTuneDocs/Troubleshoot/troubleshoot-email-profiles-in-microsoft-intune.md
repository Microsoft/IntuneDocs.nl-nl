---
title: Problemen met e-mailprofielen oplossen | Microsoft Intune
description: Problemen met e-mailprofielen en hoe u deze kunt oplossen.
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 05/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c1e215320168c659d5f838355f6350111d6979b0
ms.openlocfilehash: c695f39f128cf5ebee14b885b89ebe9833009ae9


---

# Problemen met e-mailprofielen in Microsoft Intune oplossen
Hier vindt u een aantal problemen met e-mailprofielen die zich kunnen voordoen. Ook wordt er beschreven hoe u deze kunt oplossen.

Zie [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md) voor meer manieren om hulp te krijgen als u het probleem niet kunt oplossen met deze informatie.


## Kan geen afbeeldingen verzenden vanuit e-mailaccount
Gebruikers met automatisch geconfigureerde e-mailaccounts kunnen geen afbeeldingen of foto’s verzenden vanaf hun apparaat.
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



<!--HONumber=Jul16_HO3-->


