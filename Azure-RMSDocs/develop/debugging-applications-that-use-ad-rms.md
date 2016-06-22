---
# required metadata

title: Fouten opsporen in een toepassing met rechtenbescherming | Azure RMS
description: In het volgende onderwerp staat hoe u fouten kunt opsporen in uw toepassing en hoe u het Windows-gebeurtenislogboek gebruikt.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 6F6C7651-6A6E-45DD-A0C5-F036F803249B
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Instructies: fouten opsporen in een toepassing met rechten

In het volgende onderwerp staat hoe u fouten kunt opsporen in uw toepassing en hoe u het Windows-gebeurtenislogboek gebruikt.

## Fouten opsporen in uw toepassing

In de Rights Management Services SDK 2.1 zijn de anti-foutopsporingscontroles in de ontwikkelaarsversie van onze runtime uitgeschakeld.

U kunt foutopsporingstracering inschakelen met behulp van de volgende registersleutel. (Als u foutopsporingstracering wilt uitschakelen, wijzigt u de waarde in 0.) Voor het opsporen van fouten is in deze release verder niets vereist.


```
HKEY_LOCAL_MACHINE
   SOFTWARE
      Microsoft
         MSIPC
            "Trace" = 00000001
            Data type
            dword
```

### Logboekregistratie van toepassingen met behulp van het Windows-gebeurtenislogboek

De naam van het gebeurtenislogboek is 'Microsoft-RMS-MSIPC/Debug'. Dit betekent dat in de functie Logboeken van Windows uw logboek wordt weergegeven als Logboeken voor toepassingen en services \\Microsoft\\RMS\\MSIPC\\Debug.

**Opmerking**: het logboek is standaard ingeschakeld en ingesteld op uitgebreidheidsniveau 3.

 

Voor het wijzigen van de instellingen van de functie voor logboekregistratie kunt u ofwel de gebruikersinterface voor Windows Logboeken gebruiken ofwel Wevtutil, een opdrachtregelprogramma dat is geïntegreerd in Windows.

U kunt de mate van uitgebreidheid van het logboek beheren via de Wevtutil-interface.

Op dit moment ondersteunen we 3 niveaus van logboekregistratie:

-   Niveau 2: fout
-   Niveau 3: waarschuwing
-   Niveau 4: informatie

Met de volgende opdracht wordt bijvoorbeeld het gebeurtenislogboek MSIPC ingeschakeld en het uitgebreidheidsniveau ingesteld op 'Informatie'.

**wevtutil sl Microsoft-RMS-MSIPC/Debug /e:true /l:4**

**Opmerking**: selecteer in Windows Logboeken in het menu **Weergave** de optie **Logboeken voor analyseren en foutopsporing weergeven** om het MSIPC-foutopsporingslogboek zichtbaar te maken.

 

## Verwante onderwerpen

 

 


<!--HONumber=Jun16_HO2-->


