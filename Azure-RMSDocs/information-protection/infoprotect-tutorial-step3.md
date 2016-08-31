---
title: Zelfstudie voor snel starten met Azure Information Protection - Stap 3 | Azure Rights Management
description: Stap 3 in de introductiezelfstudie om Microsoft Azure Information Protection snel uit te proberen voor uw organisatie, met slechts 4 stappen die minder dan 15 minuten duren.
author: cabailey
manager: mbaldwin
ms.date: 08/10/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 209815b9-81c9-430c-a82f-32cac991449b
translationtype: Human Translation
ms.sourcegitcommit: c9f9211e7c1dcf293caf81475515114b5433d6a7
ms.openlocfilehash: 320cd688ba5aabcb966009907d568033149953e3


---

# Stap 3: De Azure Information Protection-client installeren 

>*Van toepassing op: Azure Information Protection preview*

**[ Deze informatie is voorlopig en kan worden gewijzigd. ]**

In deze stap installeert u de Azure Information Protection-client, zodat het beleid dat u zojuist hebt geconfigureerd naar een Windows-pc wordt gedownload en de labels in Office-toepassingen worden weergegeven. 

1. [Download de Azure Information Protection-client](https://www.microsoft.com/en-us/download/details.aspx?id=53018) op een pc waarop Office is geïnstalleerd (maar Word momenteel niet is geopend) via het Microsoft Downloadcentrum. 

2. Voer **AZInfoProtection.exe** uit en volg de prompts om de client te installeren.

    Voor deze zelfstudie maakt het niet uit of u de optie selecteert voor het installeren van een demobeleid, omdat het beleid dat we zojuist hebben geconfigureerd wordt gedownload van Azure en het demobeleid (indien geïnstalleerd) vervangt. U kunt het demobeleid echter gebruiken als u de standaardlabels wilt zien zonder dat u verbinding maakt met Azure Information Protection. 

3. Controleer of de client is geïnstalleerd door in Word een nieuw, leeg document te openen (sla dit document nog niet op). Als u wordt gevraagd om uw gebruikersnaam en wachtwoord in te voeren, voert u de details in voor het account van de hoofdbeheerder. Wanneer het document wordt geladen, ziet u twee nieuwe dingen:

    - Op het tabblad **Start** staat een nieuwe **beveiliging**sgroep met een knop met de naam **Beveiligen**.

        Klik op **Beveiligen** > **Help en feedback** en bevestig de clientstatus in het dialoogvenster **Microsoft Azure Information Protection**. Als het goed is, ziet u **Information Protection-beleid wordt geïnstalleerd** en wordt een recente verbindingstijd weergegeven. Controleer of de weergegeven gebruikersnaam juist is voor uw tenant.

    - Er wordt een nieuwe balk weergegeven onder het lint, de balk Information Protection. Hierin wordt de titel **Gevoeligheid** weergegeven en het standaardlabel dat we hebben geconfigureerd voor **Intern**. 
    
        ![Zelfstudie voor snel starten met Azure Information Protection Stap 3- client geïnstalleerd](../media/word2013-callouts2.png)

U bent klaar voor de laatste stap om de classificatie, labels en beveiliging in actie te zien.

|Als u meer informatie wilt|Aanvullende informatie|
|--------------------------------|--------------------------|
|Over het installeren van de client|[De Azure Information Protection-client installeren](info-protect-client.md)|


>[!div class="step-by-step"]
[&#171; Stap 2](infoprotect-tutorial-step2.md)
[Stap 4 &#187;](infoprotect-tutorial-step4.md)


<!--HONumber=Aug16_HO4-->


