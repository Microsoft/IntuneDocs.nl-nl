---
title: Een Windows-pc buiten gebruik stellen | Microsoft Docs
description: Een Windows-pc buiten gebruik stellen die wordt beheerd door Intune.
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c916182-d99c-44c5-a779-3f596f261c40
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 10dd2caa9ce1b96424f55e373e904a778390eb15
ms.openlocfilehash: fbf188be16ca4a47ee369e3fdde8c0a7f799beab


---

# <a name="retire-a-windows-pc"></a>Een Windows-pc buiten gebruik stellen
Gebruik de volgende stappen voor het buiten gebruik stellen van desktops die u als pc's beheert door er de Intune-softwareclient op uit te voeren. Wanneer u een pc buiten gebruik stelt, wordt deze uit Intune-beheer verwijderd. U kunt een pc niet vanuit Intune terugzetten naar de oorspronkelijke fabrieksinstellingen.

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) de optie **Groepen**&gt;**Alle apparaten** (of een andere groep die de pc bevat die u buiten gebruik wilt stellen).

2.  Selecteer de apparaten die u buiten gebruik wilt stellen en kies vervolgens **Buiten gebruik stellen/wissen**.

Als u een pc opnieuw wilt registreren bij Intune, installeert u de softwareclient opnieuw op de pc met behulp van de informatie in [De Windows-pc-client installeren met Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

Als een pc geen verbinding kan maken met Intune, wordt een bericht weergegeven in de werkruimte **Dashboard**.

Wanneer u een pc buiten gebruik stelt:

-   Wordt deze verwijderd uit het Intune-beheer en de Intune-inventarisatie en wordt de licentie die aan de pc is gekoppeld, beschikbaar gesteld voor hergebruik. Met Buiten gebruik stellen/wissen wordt alleen de Intune-softwareclient van de pc verwijderd, en geen apps of gegevens. Met Buiten gebruik stellen wordt de pc niet volledig gewist.

-   Wordt de status ervan niet meer weergegeven de Intune-console.

-   De clientsoftware wordt met Intune van de pc verwijderd. Als de pc niet met de Intune-service is verbonden, wordt de softwareclient de volgende keer dat de computer verbinding maakt, verwijderd.

-   Microsoft Intune Endpoint Protection wordt verwijderd van de pc. Als op de pc een andere eindpunttoepassing is geïnstalleerd en deze is uitgeschakeld, kan die toepassing opnieuw worden ingeschakeld nadat Microsoft Intune Endpoint Protection is verwijderd om ervoor te zorgen dat uw pc is beveiligd.

-   Eventuele beleidsregels worden verwijderd van de pc en de waarden die zijn ingesteld door het beleid, worden gewijzigd.

-   De pc ontvangt geen software-updates of updates voor definities van schadelijke software meer van de Intune-service.

-   Afhankelijk van de configuratie kunnen pc's die buiten gebruik zijn gesteld, nog steeds updates ontvangen via Windows Server Update Services, Windows Update of Microsoft Update.

    > [!IMPORTANT]
    > Als de clientsoftware is geïnstalleerd met behulp van een groepsbeleidsobject (GPO), moet u het groepsbeleidsobject verwijderen voordat u de clientsoftware kunt verwijderen om te voorkomen dat de software wordt geïnstalleerd.

    Als de Endpoint Protection-client niet kan worden verwijderd, leest u [Problemen met Endpoint Protection oplossen](/intune/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune) voor meer informatie.

### <a name="see-also"></a>Zie tevens

[Algemene beheertaken voor Windows-pc's met de Intune-softwareclient](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)


<!--HONumber=Dec16_HO3-->


