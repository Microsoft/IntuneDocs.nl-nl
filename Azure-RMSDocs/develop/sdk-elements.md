---
title: Ontwikkelomgevingsbestanden | Azure RMS
description: "Dit onderwerp bevat informatie over de ontwikkelomgevingsbestanden en de locaties waar deze op uw computer zijn geïnstalleerd."
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: B57AC6F3-733C-42A8-AF83-0E15FBF27C99
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 024a29d7c7db2e4c0578a95c93e22f8e7a5b173e
ms.openlocfilehash: a3f1e913c92dbee3b889a3d3c0bd6c97317112c9


---

# Ontwikkelomgevingsbestanden

Dit onderwerp bevat informatie over de ontwikkelomgevingsbestanden en de locaties waar deze op uw computer zijn geïnstalleerd.

De Rights Management Services SDK 2.1 bevat de volgende bestanden, die op uw computer worden geïnstalleerd op de standaardlocatie of op de locatie die u hebt opgegeven: %MsipcSDKDir%.

|Bestand|Pad|Beschrijving|
|----|----|-----------|
|ReadMe.htm| \ | Bevat een koppeling naar de RMS Help en de [Opmerkingen bij de release](release-notes-rtm.md).|
|Isvtier5appsigningprivkey.dat|\Bin|Bevat de privésleutel die wordt gebruikt om een manifest te genereren tijdens de ontwikkeling van een RMS-toepassing.|
|Isvtier5appsigningpubkey.dat|\Bin|Bevat de openbare sleutel die wordt gebruikt om een manifest te genereren tijdens de ontwikkeling van een RMS-toepassing.|
|Isvtier5appsignsdk_client.xml|\Bin|Wordt gebruikt om een manifest te genereren voor gebruik tijdens de ontwikkeling van een RMS-toepassing.|
|YourAppName.isv.mcf|\Bin|Een manifestconfiguratiebestand met standaardtekst dat u kunt gebruiken om een manifest te maken tijdens het ontwikkelen van een toepassing met RMS-beveiliging.|
|Ipcsecproc_isv.dll|\bin\x86|DLL-bestand dat intern wordt gebruikt voor x86-toepassingen door de Active Directory Rights Management Services Client 2.1 wanneer het wordt uitgevoerd in de ISV-hiërarchie.|
|Ipcsecproc_ssp_isv.dll|\bin\x86|DLL-bestand dat intern wordt gebruikt voor x86-toepassingen door de AD RMS 2.1 als het wordt uitgevoerd in de ISV-hiërarchie.|
|Ipcsecproc_isv.dll|\bin\x64|DLL-bestand dat intern wordt gebruikt voor x64-toepassingen door de AD RMS Client 2.1 als het wordt uitgevoerd in de ISV-hiërarchie.|
|Ipcsecproc_ssp_isv.dll|\bin\x64|DLL-bestand dat intern wordt gebruikt voor x64-toepassingen door de AD RMS Client 2.1 als het wordt uitgevoerd in de ISV-hiërarchie.|
|Msipc.h|\inc|Bevat het bestand voor de RMS SDK 2.1.|
|Ipcprot.h|\inc|Bevat de openbare interface die is geëxporteerd door de RMS SDK 2.1.|
|Ipcbase.h|\inc|Bevat algemene typen en hulpfuncties die zijn geëxporteerd door de RMS SDK 2.1.|
|Ipcerror.h|\inc|Bevat openbare foutcodes die zijn geëxporteerd door de RMS SDK 2.1.|
|Ipcfile.h|\inc|Bevat de bestands-API-interfaces die zijn geëxporteerd door de RMS SDK 2.1|
|Msipc.lib|\lib|Bibliotheek om aan te koppelen als u de RMS SDK 2.1 gebruikt voor het bouwen van x86-toepassingen.|
|Msipc_s.lib|\lib|Biedt een invoerpunt voor [<strong>IpcInitialize</strong>](/rights-management/sdk/2.1/api/win/functions#msipc_ipcinitialize) voor x86-toepassingen.|
|Msipc.lib|\lib\x64|Bibliotheek om aan te koppelen als u de RMS SDK 2.1 gebruikt voor het bouwen van x64-toepassingen.|
|Msipc_s.lib|\lib\x64|Biedt een invoerpunt voor [<strong>IpcInitialize</strong>](/rights-management/sdk/2.1/api/win/functions#msipc_ipcinitialize) voor x64-toepassingen.|
|Genmanifest.exe|\tools|Wordt gebruikt om een manifest te genereren voor gebruik tijdens de ontwikkeling van een RMS-toepassing.|
 

 

 



<!--HONumber=Aug16_HO4-->


