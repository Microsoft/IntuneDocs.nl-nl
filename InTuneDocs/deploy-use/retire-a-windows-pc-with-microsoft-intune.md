---
title: Een Windows-pc buiten gebruik stellen | Microsoft Intune
description: Een Windows-pc buiten gebruik stellen die wordt beheerd door Intune.
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c916182-d99c-44c5-a779-3f596f261c40
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 19e8e2b6a7eaa3cf02e4296a6fd147baa1472b61


---

# <a name="retire-a-windows-pc"></a>Een Windows-pc buiten gebruik stellen
Gebruik de volgende stappen om pc's die worden beheerd door Intune, buiten gebruik te stellen.

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) de optie **Groepen**&gt;**Alle apparaten** (of een andere groep die de computer bevat die u buiten gebruik wilt stellen).

2.  Selecteer de apparaten die u buiten gebruik wilt stellen en kies vervolgens **Buiten gebruik stellen/wissen**.

Als u een computer opnieuw wilt registreren bij Intune, installeert u de softwareclient opnieuw op de pc met behulp van de informatie in [De Windows-pc-client installeren met Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

Als een computer geen verbinding kan maken met Intune, wordt een bericht weergegeven in de werkruimte **Dashboard**.

Wanneer u een computer buiten gebruik stelt:

-   Wordt deze verwijderd uit het Intune-beheer en de Intune-inventarisatie en wordt de licentie die aan de computer is gekoppeld, beschikbaar gesteld voor hergebruik. Met Buiten gebruik stellen/wissen wordt alleen de Intune-softwareclient van de computer verwijderd, niet apps of gegevens. Met Buiten gebruik stellen wordt de computer niet volledig gewist.

-   Wordt de status ervan niet meer weergegeven de Intune-console.

-   De clientsoftware wordt met Intune van de computer verwijderd. Als de computer niet met de Intune-service is verbonden, wordt de softwareclient de volgende keer dat de computer verbinding maakt, verwijderd.

-   Microsoft Intune Endpoint Protection wordt verwijderd van de computer. Als op de computer een andere eindpunttoepassing is geïnstalleerd en deze is uitgeschakeld, kan die toepassing opnieuw worden ingeschakeld nadat Microsoft Intune Endpoint Protection is verwijderd om ervoor te zorgen dat uw computers zijn beveiligd.

-   Eventuele beleidsregels worden verwijderd van de computer en de waarden die zijn ingesteld door het beleid, worden gewijzigd.

-   De computer ontvangt geen software-updates of updates voor definities van schadelijke software meer van de Intune-service.

-   Afhankelijk van de configuratie kunnen computers die buiten gebruik zijn gesteld, nog steeds updates ontvangen via Windows Server Update Services, Windows Update of Microsoft Update.

    > [!IMPORTANT]
    > Als de clientsoftware is geïnstalleerd met behulp van een groepsbeleidsobject (GPO), moet u het groepsbeleidsobject verwijderen voordat u de clientsoftware kunt verwijderen om te voorkomen dat de software wordt geïnstalleerd.

    Als de client niet kan worden verwijderd, leest u [Problemen met Endpoint Protection oplossen](/intune/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune) voor meer informatie.

### <a name="see-also"></a>Zie ook

[Algemene beheertaken voor Windows-pc's met de Intune-softwareclient](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)


<!--HONumber=Nov16_HO4-->


