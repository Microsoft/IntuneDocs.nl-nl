---
title: Termen | Azure RMS
description: Een overzicht van termen die specifiek zijn voor Rights Management Services.
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: adb1f868-0da7-431b-83d1-86f41c2da4ae
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 024a29d7c7db2e4c0578a95c93e22f8e7a5b173e
ms.openlocfilehash: 5340673beb2a6f2dd4acd96fd599c0b90b9991dd


---

# Termen

Een overzicht van termen die specifiek zijn voor Rights Management Services.

**Afgeschaft algoritme**  
Een modale instelling waarmee een ouder inhoudbeveiligingsschema wordt geïmplementeerd dat specifiek verwijst naar de ECB-cijfermodus (Electronic Cookbook). In deze SDK stelt deze instelling u in staat licenties te genereren die compatibel zijn met de MSDRM-bibliotheek die wordt gebruikt door [AD Rights Management Services SDK](https://msdn.microsoft.com/library/windows/desktop/cc530379.aspx).

Selectie van deze instelling kan ertoe leiden dat uw toepassing inhoud beveiligt op een manier die niet voldoet aan de standaarden van uw klanten voor de beveiliging van inhoud.

Als u deze instelling gebruikt, profiteert uw toepassing niet van cryptografische verbeteringen die zijn toegevoegd aan Microsoft Rights Management SDK 3.0 of hoger.

**Door Microsoft beveiligde bestandsindeling**

Dit is de standaardbestandsindeling voor AD RMS. Deze indeling fungeert als standaard voor RMS-toepassingen. Wordt ook wel aangeduid als PFile-indeling.

De PFile-indeling is transparant voor ontwikkelaars van toepassingen omdat deze is ingebed in de manier waarop de Microsoft Rights Management SDK 4.2 is ontworpen.

 

 






<!--HONumber=Aug16_HO4-->


