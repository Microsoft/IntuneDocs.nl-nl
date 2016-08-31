---
title: Informatie over gebruiksbeperkingen | Azure RMS
description: In alle toepassingen waarin RMS is ingeschakeld, moeten gebruiksbeperkingen worden afgedwongen.
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: E388B16C-ECDA-4696-A040-D457D3C96766
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 024a29d7c7db2e4c0578a95c93e22f8e7a5b173e
ms.openlocfilehash: df210bd7aff33fda41a278e6aed1108574fe68eb


---

# Gebruiksbeperkingen begrijpen

In alle toepassingen waarin RMS is ingeschakeld, moeten gebruiksbeperkingen worden afgedwongen. Een gebruiksbeperking is een situatie die zich voordoet wanneer een gebruiker probeert een actie (bijvoorbeeld een document afdrukken) uit te voeren, maar de gebruiker in het RMS-beleid voor het document geen machtiging of rechten heeft om die actie uit te voeren (bijvoorbeeld het recht PRINT).

De gebruikersmachtigingen voor een document kunnen worden opgevraagd met behulp van de functie [**IpcAccessCheck**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcaccesscheck).

## Gebruiksbeperkingen begrijpen

-   Maak uzelf bekend met standaardrechten van RMS

    Zie [Overzicht van gebruiksbeperkingen](usage-restriction-reference.md) voor de volledige set RMS-rechten die uw toepassing kan afdwingen.

    Houd er rekening mee dat er voor de toepassing gedefinieerde rechten kunnen worden gemaakt die specifiek zijn voor uw situatie en die verder gaan dan de standaardrechten van RMS.

-   Identificeer afdwingingspunten voor gebruiksbeperking

    Een *Afdwingingspunt voor gebruiksbeperking* is een plaats in de beheerstroom van uw toepassing waar u een gebruiksbeperking afdwingt. Het onderwerp [Overzicht van gebruiksbeperkingen](usage-restriction-reference.md) bevat enkele voorbeelden van algemene afdwingingspunten.

    Evalueer uw eigen toepassing om te bepalen welke afdwingingspunten voor gebruiksbeperking van toepassing zijn.

    De toepassing heeft mogelijk niet alle afdwingingspunten nodig die zijn beschreven in [Overzicht van gebruiksbeperkingen](usage-restriction-reference.md). Als het in uw toepassing bijvoorbeeld niet is toegestaan dat gebruikers inhoud afdrukken, hoeft deze niet te controleren op het recht **IPC\_GENERIC\_PRINT**.

-   Werk uw code bij om een toegangscontrole uit te voeren op elk afdwingingspunt

    Zie [Overzicht van gebruiksbeperkingen](usage-restriction-reference.md) voor instructies over het afdwingen van specifieke rechten.

## Verwante onderwerpen

* [**IpcAccessCheck**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcaccesscheck)
* [Overzicht van gebruiksbeperkingen](usage-restriction-reference.md)
 

 



<!--HONumber=Aug16_HO4-->


