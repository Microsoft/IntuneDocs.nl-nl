---
# required metadata

title: Informatie over gebruiksbeperkingen | Azure RMS
description: In alle toepassingen waarin RMS is ingeschakeld, moeten gebruiksbeperkingen worden afgedwongen.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: E388B16C-ECDA-4696-A040-D457D3C96766
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

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

* [Concepten voor ontwikkelaars](ad-rms-concepts-nav.md)
* [**IpcAccessCheck**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcaccesscheck)
* [Overzicht van gebruiksbeperkingen](usage-restriction-reference.md)
 

 





<!--HONumber=May16_HO2-->


