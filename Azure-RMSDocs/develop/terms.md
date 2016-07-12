---
title: Termen | Azure RMS
description: Een overzicht van termen die specifiek zijn voor Rights Management Services.
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: adb1f868-0da7-431b-83d1-86f41c2da4ae
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
ms.sourcegitcommit: f7dd88d90357c99c69fe4fdde67c1544595e02f8
ms.openlocfilehash: 5779cc10503ad7afe997e031a467021b513fc510


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

 

 






<!--HONumber=Jun16_HO4-->


