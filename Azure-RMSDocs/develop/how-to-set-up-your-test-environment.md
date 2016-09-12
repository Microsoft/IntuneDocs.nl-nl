---
title: Uw toepassing testen | Azure RMS
description: Instructies voor het instellen van uw toepassing voor testen.
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: E480D8D6-F070-43D1-B2B0-6921459C3437
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 024a29d7c7db2e4c0578a95c93e22f8e7a5b173e
ms.openlocfilehash: 9cc96c7f4d75969ec75b1372a4a49499709b0d32


---

# Uw toepassing testen

Dit onderwerp bevat instructies voor het instellen van uw toepassingstest.

## Instructies

### Stap 1: configureren voor testen

U kunt testen met Azure RMS of een RMS-server die wordt uitgevoerd op Windows Server. Het wordt aangeraden te beginnen met het testen op Azure RMS en daarna, als dit vereist is voor uw implementatie, met RMS-server.

1. Zie voor tests met Azure RMS het onderwerp [Instructies: ADAL-verificatie gebruiken](how-to-use-adal-authentication.md).
2. Zie voor tests met RMS-Server het onderwerp [Instructies: een RMS-server installeren en configureren](how-to-install-and-configure-an-rms-server.md).
3. In de volgende stappen wordt beschreven hoe u de runtime voor ontwikkelaars installeert.

   De Rights Management Service Client 2.1 moet op de computer zijn geïnstalleerd waarop u uw toepassing gaat testen.
   - Als u uw toepassing gaat testen op een andere computer dan uw ontwikkelcomputer, kunt u de RMS-client 2.1 op die computer installeren via de [downloadpagina voor de RMS-client](http://www.microsoft.com/en-us/download/details.aspx?id=38396).
   - Als u de toepassing gaat testen op uw ontwikkelingscomputer, zou u de Rights Management Services SDK 2.1 al geïnstalleerd moeten hebben. De RMS-client 2.1 is dan op de achtergrond ook geïnstalleerd.

    Zie [De SDK installeren](install-the-rms-sdk.md) voor meer informatie over het installeren van de RMS SDK 2.1.

## Opmerkingen

De instructies in dit onderwerp zijn niet uitgebreid. Voor gedetailleerde informatie over het configureren van RMS-client 2.1 raadpleegt u [Opmerkingen bij de implementatie van de RMS-client 2.1](https://technet.microsoft.com/en-us/library/jj159267(WS.10).aspx).

### Verwante onderwerpen

* [Instructies voor het installeren en configureren van een RMS-server](how-to-install-and-configure-an-rms-server.md)
* [Instructies: ADAL-verificatie gebruiken](how-to-use-adal-authentication.md)
* [De SDK installeren](install-the-rms-sdk.md)
* [Opmerkingen bij de implementatie van de RMS-client 2.1](https://technet.microsoft.com/en-us/library/jj159267(WS.10).aspx)
 

 



<!--HONumber=Aug16_HO4-->


