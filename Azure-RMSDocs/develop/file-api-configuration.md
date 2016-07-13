---
title: Configuratie van de bestands-API| Azure RMS
description: Het gedrag van de bestands-API's kan worden geconfigureerd via instellingen in het register.
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 06/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 930878C2-D2B4-45F1-885F-64927CEBAC1D
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 56d0538243af49580f24c701ad5097b30f3059b0
ms.openlocfilehash: 46b1fe5a0c4f138db65072d14489a5d588015df7


---

# API-bestandsconfiguratie


Het gedrag van de bestands-API's kan worden geconfigureerd via instellingen in het register.

De bestands-API bevat twee soorten beveiliging: systeemeigen beveiliging en PFile-beveiliging.

-   **Systeemeigen beveiliging**: het bestand wordt beveiligd door een AD RMS-indeling op basis van het MIME-type (bestandsnaamextensie).
-   **PFile-beveiliging**: het bestand wordt beveiligd met de PFile-indeling (AD RMS Protected File).

Zie voor meer informatie over ondersteunde indelingen **Bestands-API - Details van bestandsondersteuning** in dit onderwerp.

## Typen en beschrijvingen van sleutel/sleutelwaarde

In de volgende secties worden de sleutels en sleutelwaarden beschreven waarmee versleuteling wordt ingesteld.

### HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\FileProtection

**Type**: sleutel

**Beschrijving**: bevat de algemene configuratie voor de bestands-API.

### HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\FileProtection\&lt;EXT&gt;

**Type**: sleutel

**Beschrijving**: bevat configuratie-informatie voor een specifieke bestandsextensie; bijvoorbeeld, txt, jpg, enzovoort.

- Het jokerteken, ' *', is toegestaan. Een instelling voor een bepaalde extensie heeft echter voorrang op de instelling van het jokerteken. Het jokerteken heeft geen invloed op de instellingen voor Microsoft Office-bestanden. Deze moeten expliciet worden uitgeschakeld door het bestandstype.
- Gebruik '.' voor het opgeven van bestanden die geen extensie hebben.
- Geef het teken '.' niet op bij het opgeven van de sleutel voor een specifieke bestandsextensie. Gebruik bijvoorbeeld `HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\FileProtection\TXT` om instellingen op te geven voor txt-bestanden. (Gebruik `HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\FileProtection\.TXT` niet.)

Stel de waarde **Versleuteling** in de sleutel in om het beveiligingsgedrag op te geven. Als de waarde **Versleuteling** niet is ingesteld, wordt het standaardgedrag voor het bestandstype toegepast.


### HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\FileProtection\&lt;EXT&gt;\Encryption*

**Type**: REG_SZ

**Beschrijving**: bevat een van drie waarden:

- **Uit**: versleuteling is uitgeschakeld.

> [!Note] 
> Deze instelling heeft geen gevolgen voor ontsleuteling. Een versleuteld bestand, ongeacht of het is versleuteld met systeemeigen beveiliging of Pfile-beveiliging, kan worden ontsleuteld mits de gebruiker beschikt over uitpakrechten (**EXTRACT**).

- **Systeemeigen**: systeemeigen versleuteling wordt gebruikt. Bij Office-bestanden heeft het versleutelde bestand dezelfde extensie als het oorspronkelijke bestand. Een bestand met de bestandsnaamextensie .docx wordt bijvoorbeeld versleuteld als een bestand met de extensie .docx. Voor andere bestanden waarop systeemeigen beveiliging kan worden toegepast, wordt het bestand versleuteld als een bestand met de extensie in de indeling p*zzz*, waarbij *zzz* de oorspronkelijke bestandsextensie is. Txt-bestanden worden bijvoorbeeld versleuteld als een bestand met de extensie .ptxt. Hieronder vindt u een lijst met bestandsextensies waarop systeemeigen beveiliging kan worden toegepast.

- **Pfile**: PFile-versleuteling wordt gebruikt. Aan het versleutelde bestand wordt .pfile toegevoegd aan de originele extensie. Na versleuteling heeft een txt-bestand bijvoorbeeld de extensie .txt.pfile.


> [!Note] 
> Deze instelling heeft geen invloed op de Office-bestandsindelingen. Als de waarde van `HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\FileProtection\DOCX\Encryption` bijvoorbeeld is ingesteld op &quot;Pfile, worden docx-bestanden nog steeds versleuteld met systeemeigen beveiliging en heeft het versleutelde bestand nog steeds de bestandsextensie .docx.

Als u een andere waarde of geen waarde instelt, wordt het standaardgedrag toegepast.

## Standaardgedrag voor verschillende bestandsindelingen

-   **Office-bestanden** Systeemeigen versleuteling is ingeschakeld.
-   **Txt-, xml-, jpg-, jpeg-, pdf-, png-, tiff-,bmp-, gif-, giff-, jpe-, jfif-, jif-bestanden** Systeemeigen versleuteling is ingeschakeld (xxx wordt pxxx)
-   **Alle andere bestanden** Versleuteling met Pfile (Protected File) (xxx wordr xxx.pfile)

Als versleuteling wordt toegepast op een geblokkeerd bestandstype, treedt de fout [**IPCERROR\_FILE\_ENCRYPT\_BLOCKED**](/rights-management/sdk/2.1/api/win/error%20codes) op.

### Bestands-API - Details van bestandsondersteuning

Systeemeigen ondersteuning kan worden toegevoegd voor elk bestandstype (extensie). Zo wordt voor elke extensie &lt;ext&gt; (niet-Office-bestanden), \*.p&lt;ext&gt; gebruikt als de beheerconfiguratie voor de extensie SYSTEEMEIGEN is.

**Office-bestanden**

-   Bestandsextensies: doc, dot, xla, xls, xlt, pps, ppt, docm, docx, dotm, dotx, xlam, xlsb, xlsm, xlsx, xltm, xltx, xps, potm, potx, ppsx, ppsm, pptm, pptx, thmx.
-   Beveiligingstype = systeemeigen (standaard): sample.docx wordt versleuteld als sample.docx
-   Beveiligingstype = Pfile: heeft voor Office-bestanden hetzelfde resultaat als systeemeigen beveiliging.
-   Uit: versleuteling uitschakelen.

**PDF-bestanden**

-   Beveiligingstype = systeemeigen: sample.pdf heeft na versleuteling de naam sample.ppdf
-   Beveiligingstype = Pfile: sample.pdf heeft na versleuteling de naam sample.pdf.pfile.
-   Uit: versleuteling uitschakelen.

**Alle andere bestandsindelingen**

-   Beveiligingstype = Pfile: sample.*zzz* heeft na versleuteling de naam sample.*zzz*.pfile, waarbij *zzz* de oorspronkelijke bestandsextensie is.
-   Uit: versleuteling uitschakelen.

### Voorbeelden

Met de volgende instellingen past u PFile-versleuteling toe op txt-bestanden. Op Office-bestanden wordt systeemeigen beveiliging toegepast (standaard), op txt-bestanden wordt PFile-beveiliging toegepast, en alle andere bestanden zijn geblokkeerd tegen beveiliging (standaard).

```
HKEY_LOCAL_MACHINE
   Software
      Microsoft
         MSIPC
            FileProtection
               txt
                  Encryption = Pfile
```

Met de volgende instellingen past u PFile-versleuteling toe op alle niet-Office-bestanden, behalve txt-bestanden. Op Office-bestanden wordt systeemeigen beveiliging toegepast (standaard), txt-bestanden zijn geblokkeerd tegen beveiliging en op alle andere bestanden wordt PFile-beveiliging toegepast.

```
HKEY_LOCAL_MACHINE
   Software
      Microsoft
         MSIPC
            FileProtection
               *
                  Encryption = Pfile
               txt
                  Encryption = Off
```

Met de volgende instellingen schakelt u systeemeigen versleuteling uit voor docx-bestanden. Op Office-bestanden, met uitzondering van docx-bestanden wordt systeemeigen beveiliging toegepast (standaard) en alle andere bestanden zijn geblokkeerd tegen beveiliging (standaard).

```
HKEY_LOCAL_MACHINE
   Software
      Microsoft
         MSIPC
            FileProtection
               docx
                  Encryption = Off
```

## Verwante onderwerpen

* [Opmerkingen voor ontwikkelaars](developer-notes.md)
* [**IPCERROR\_FILE\_ENCRYPT\_BLOCKED**](/rights-management/sdk/2.1/api/win/error%20codes)
 

 



<!--HONumber=Jun16_HO4-->


