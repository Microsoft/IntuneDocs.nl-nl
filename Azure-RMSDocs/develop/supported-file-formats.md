---
title: Ondersteunde bestandsindelingen | Azure RMS
description: De huidige versie van de bestands-API ondersteunt systeemeigen beveiliging voor MS Office-bestanden, PDF- en PFile-beveiliging voor alle andere bestandsindelingen.
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: EC831494-7F2C-4C70-9063-B02CDDEA14EE
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 024a29d7c7db2e4c0578a95c93e22f8e7a5b173e
ms.openlocfilehash: e41d8d697d7c35beef84277bc5b9fd497d79cc10


---

# Ondersteunde bestandsindelingen

De bestands-API ondersteunt systeemeigen en Pfile-indelingen.

## Ondersteunde bestandsindelingen

De huidige versie van de bestands-API ondersteunt systeemeigen beveiliging voor Microsoft Office-bestanden, PDF-beveiliging (Portable Document File) en PFile-beveiliging voor alle andere bestandsindelingen. Op PDF-bestanden kan eventueel PFile-beveiliging toegepast zijn.

-   **Systeemeigen beveiliging**. In systeemeigen beveiliging is het bestand versleuteld met een AD RMS-bestandsindeling die is gebaseerd op het MIME-type (bestandsnaamextensie). Bestanden met een systeemeigen beveiliging via bestands-API zijn consistent met de indeling die toepassingen verwachten waarbij AD RMS is ingeschakeld en die systeemeigen beveiliging gebruiken, zoals Office 2013, Office 2010 en FoxIt PDF Reader. Systeemeigen beveiliging wordt alleen ondersteund in Office-bestanden, PDF-bestanden en een beperkt aantal andere bestandstypen. Zie [API-bestandsconfiguratie](file-api-configuration.md) voor meer informatie over de bestandstypen waarop systeemeigen beveiliging wordt ondersteund.
-   **PFile-beveiliging**. Bij PFile-beveiliging worden bestanden versleuteld met de AD RMS PFile-indeling. Het bestand is versleuteld als een bestand met de extensie .pfile. PFile-beveiliging wordt ondersteund voor alle bestandsindelingen, met uitzondering van Office-bestanden.

Beheerders kunnen registersleutels instellen om te configureren of en hoe bestanden moeten worden beveiligd, op basis van hun bestandsnaamextensie. Zie [API-bestandsconfiguratie](file-api-configuration.md) voor meer informatie over het configureren van bestandsbeveiliging bij gebruik van bestands-API.

## Verwante onderwerpen

* [Opmerkingen voor ontwikkelaars](developer-notes.md)
* [Configuratie van bestands-API](file-api-configuration.md)
 

 



<!--HONumber=Aug16_HO4-->


