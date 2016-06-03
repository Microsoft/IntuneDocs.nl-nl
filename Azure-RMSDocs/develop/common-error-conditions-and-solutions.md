---
# required metadata

title: Algemene fouten en oplossingen | Azure RMS
description: Dit onderwerp bevat de meestvoorkomende foutberichten die u kunt tegenkomen wanneer u de ontwikkelhulpprogramma's van de RMS SDK 2.1 gebruikt.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: A5B95EB8-3528-4CFF-86FC-166613A5F4A3
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Algemene fouten en oplossingen
Dit onderwerp bevat de meestvoorkomende foutberichten die u kunt tegenkomen wanneer u de ontwikkelhulpprogramma's van de Rights Management Services SDK 2.1 gebruikt. Indien van toepassing vindt u hier ook een aanbevolen actie om de fout te verhelpen.

**Belangrijk**: gebruik voor foutafhandeling altijd een aanroep aan [IpcGetErrorMessageText](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgeterrormessagetext) direct nadat een SDK API-aanroep is mislukt, zodat u uitgebreide informatie over de aard van de fout krijgt.

 

## Fout en actie ##
Onderstaande lijst geeft een overzicht van veelvoorkomende fouten, de bijbehorende beschrijving en een voorgestelde actie om de fout te verhelpen.

**FOUT**: *IPCERROR_DEBUGGER_DETECTED*: de RMS SDK 2.1 heeft een foutopsporingsprogramma gedetecteerd

**ACTIE**: de ontwikkelaarsversie van de RMS SDK 2.1 controleert niet op de aanwezigheid van een foutopsporingsprogramma. Spoor indien mogelijk fouten in uw toepassing op met behulp van deze versie van de RMS SDK 2.1.
Als u fouten moet opsporen in de productieversie van de RMS SDK 2.1, gebruikt u de volgende richtlijnen.

Sommige functies van de RMS SDK 2.1 zijn zo ontworpen dat ze mislukken wanneer er een debugger wordt uitgevoerd:
- [IpcGetKey</strong>](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgetkey)
- [IpcGetTemplateList](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgettemplatelist)
- [IpcGetTemplateIssuerList](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgettemplateissuerlist)

Om fouten op te sporen in code volgend op deze functieaanroepen, moet u het proces opsplitsen en een foutopsporingsprogramma koppelen nadat de functieaanroepen zijn voltooid. U kunt dit bijvoorbeeld doen door een assert-instructie te gebruiken om in het foutopsporingsprogramma te komen. De macro ASSERTE is opgenomen in de *Crtdbg.h*-kop.
Zie [\_ASSERT, \_ASSERTE-macro's](https://msdn.microsoft.com/en-us/library/ezb1wyez.aspx) voor meer informatie over \_ASSERTE.

**FOUT**: *IPCERROR_BROKEN_CERT_CHAIN*: certificaatketen komt niet overeen.

**ACTIE**: zorg ervoor dat de hiërarchiesleutel de juiste waarde bevat op basis van de sleutel die u gebruikt voor het ondertekenen van uw AD RMS-toepassingsmanifest.
Dit zijn de ondertekeningssleutels en de gekoppelde waarden ervan (hiërarchie **DWORD**):
- ISV: 1
- Productie: 0 of niet aanwezig

**FOUT**: *IPCERROR_MACHINE_CERT_NOT_TRUSTED*: u gebruikt een toepassing die is ondertekend met de ISV-ondertekeningssleutel, maar deze probeert te communiceren met een AD RMS-productieserver of vice versa.

- Als u de ontwikkelaarsversie van AD RMS Server gebruikt, zorgt u ervoor dat u de ISV-ondertekeningssleutel gebruikt om uw toepassing te ondertekenen.
- Als u de productieversie van AD RMS Server gebruikt, zorgt u ervoor dat u de ISV-productieondertekeningssleutel gebruikt om uw toepassing te ondertekenen.

**FOUT**: *IPCERROR_APPLICATION_AUTH_ERROR_MANIFEST*: het manifest voor de toepassing is niet geldig. Dit kan gebeuren wanneer het binaire onderdeel (de toepassing) opnieuw is opgebouwd en het manifest niet opnieuw is gegenereerd.

**ACTIE**: zorg ervoor dat u uw toepassingsmanifest opnieuw genereert telkens wanneer u uw toepassing opnieuw bouwt.

## Verwante onderwerpen ##
* [Opmerkingen voor ontwikkelaars](developer-notes.md)
* [IpcGetKey](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgetkey)
* [IpcGetTemplateList](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgettemplatelist)
* [IpcGetTemplateIssuerList](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgettemplateissuerlist)
* [\_ASSERT, \_ASSERTE-macro's](https://msdn.microsoft.com/en-us/library/ezb1wyez.aspx)
 

 


<!--HONumber=Apr16_HO4-->


