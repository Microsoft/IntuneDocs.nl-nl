---
# required metadata

title: Visual Studio configureren | Azure RMS
description: Instructies over het configureren van een Visual Studio-project voor het gebruik van de RMS SDK 2.1.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 396A2C19-3A00-4E9A-9088-198A48B15289
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Visual Studio configureren

Dit onderwerp bevat instructies over het configureren van een Visual Studio-project voor het gebruik van de Rights Management Services SDK 2.1.

## Vereisten

-   [De SDK installeren](create-your-first-rights-aware-application.md)

**Instructies**

### Stap 1: configureer een Visual Studio-project voor het gebruik van de RMS SDK 2.1

Deze instructies zijn specifiek bedoeld voor Microsoft Visual Studio 2010. Als u een andere versie van Microsoft Visual Studio gebruikt, zien de dialoogvensters met instellingen er mogelijk anders uit.

Deze instructies gelden voor het bouwen van een systeemeigen 32-bits toepassing.

1.  Voeg de RMS SDK 2.1-includemap toe aan uw Visual Studio 2010-project.

    Onder **Configuratie-eigenschappen** selecteert u **VC++ mappen**. Voer de RMS SDK 2.1-includemap **$(MSIPCSDKDIR)\\inc** in in het veld **Includemappen**.

    ![Veld voor configuratie-eigenschappen van includemappen](../media/include_directories.png)

2.  Voeg de RMS SDK 2.1-bibliotheekmap toe aan uw Visual Studio 2010-project.

    Onder **Configuratie-eigenschappen** selecteert u **VC++ mappen**. Voer de RMS SDK 2.1-bibliotheekmap in in het veld **Bibliotheekmappen** van uw platform.

    -   Voor Win32 gebruikt u **$(MSIPCSDKDIR)\\lib**
    -   Voor x64 gebruikt u **$(MSIPCSDKDIR)\\lib\\64**

    ![Veld voor configuratie-eigenschappen van bibliotheekmappen](../media/library_directories.png)

3.  Voeg de RMS SDK 2.1-bibliotheekbestanden toe als Visual Studio 2010-afhankelijkheden.

    Onder **Linker** selecteert u **Invoer** en voegt u de RMS SDK 2.1-bibliotheekbestanden **Msipc.lib** en **Msipc\_s.lib** toe aan het veld **Extra afhankelijkheden**.

    ![Veld voor bibliotheekafhankelijkheden voor de Linker](../media/additional_dependencies.png)

4.  Voeg de RMS SDK 2.1 Dynamic Link Library (DLL) toe als een vertraagd geladen dll-bestand.

    Onder **Linker** selecteert u **Invoer** en voegt u het RMS SDK 2.1 DLL-bestand **Msipc.dll** toe aan het veld **Vertraagd geladen dll-bestanden**.

    ![Veld voor vertraagd geladen bibliotheken voor de Linker](../media/delay_loaded.png)

5.  Maak versie-informatie voor uw resulterende binaire bestand.

    Onder **Solution Explorer** selecteert u **Resourcebestanden** en voegt u de binaire naam toe aan het veld **OriginalFileName**.

    ![Veld voor resourcebestanden voor Solution Explorer](../media/original_file_name.png)

## Verwante onderwerpen

* [Gebruik](how-to-use-msipc.md)
* [De SDK installeren](create-your-first-rights-aware-application.md)
 

 





<!--HONumber=Apr16_HO4-->


