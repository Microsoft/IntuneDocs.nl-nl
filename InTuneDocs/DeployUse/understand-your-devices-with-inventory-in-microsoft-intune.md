---
title: Inzicht in uw apparaten met inventarisaties | Microsoft Intune
description: Intune gebruiken voor het weergeven van informatie over de hardware van de apparaten die u beheert.
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 669e096735ae7123123873dad8982abf2c4c38d6


---

# Inzicht in uw apparaten met inventarisaties in Microsoft Intune
Met Microsoft Intune kunt u de inventarisatie bekijken van de ingeschreven apparaten en Windows-pc's waarop de Intune-clientsoftware wordt uitgevoerd.

## Wat wordt er verzameld bij ingeschreven apparaten?
Als u de inventaris wilt bekijken die voor mobiele apparaten is verzameld, voert u de [rapporten voor de inventaris van mobiele apparaten](understand-microsoft-intune-operations-by-using-reports.md) uit. In Intune worden de volgende inventarisgegevens van ingeschreven apparaten verzameld:

|Eigenschap|Verzameld door|
|------------|-----------------------|
|**Naam**|Alle apparaten|
|**Besturingssysteem**|Alle apparaten|
|**Fabrikant**|Alle apparaten|
|**Model**|Alle apparaten|
|**Beheerkanaal**|Alle apparaten|
|**AAD-geregistreerd**|Alle apparaten, met uitzondering van Mac OS X|
|**Compliant**|Alle apparaten|
|**EAS geactiveerd**|Alle apparaten, met uitzondering van Mac OS X|
|**Activerings-id voor EAS**|Alle apparaten, met uitzondering van Mac OS X|
|**Activeringstijd voor EAS**|Alle apparaten, met uitzondering van Mac OS X|
|**Beheerstatus**|Alle apparaten|
|**E-mailadres**|Alle apparaten|
|**Exchange ActiveSync-id**|Alle apparaten|
|**Apparaten waarop jailbreaking of rooting is uitgevoerd**|Alleen iOS- en Android-apparaten|
|**Unieke apparaat-ID**|Alle apparaten, met uitzondering van Exchange Active Sync|
|**Serienummer**|iOS-, Mac OS X-, Android-, Windows 8.1- en Windows 10-apparaten|
|**Totale opslagruimte**|iOS-, Mac OS X-, Windows 8.1- en Windows 10-apparaten|
|**Beschikbare opslagruimte**|iOS-, Mac OS X-, Windows 8.1- en Windows 10-apparaten|
|**Telefoonnummer**<br>Telefoons die zijn aangemerkt als bedrijfseigendom, worden aangeduid met hun volledige telefoonnummer, bijvoorbeeld wanneer u een inventarisrapport voor mobiele apparaten uitvoert. Telefoonnummers voor BYOD-apparaten worden gemaskeerd met &#42;, waarbij alleen de laatste 4 cijfers worden weergegeven.|iOS-, Android- en Windows Phone-apparaten|
|**IMEI**|Exchange Active Sync-, iOS-, Android- en Windows Phone-apparaten|
|**MEID**<br>Mobile Equipment Identifier|Alleen iOS-apparaten|
|**MAC-adres Wi-Fi**|Alle apparaten, met uitzondering van Exchange Active Sync|
|**Provider van abonnee**|Alleen iOS- en Android-apparaten|
|**Mobiele telefoontechnologie**|Alleen iOS- en Android-apparaten|
|**Onder supervisie**|Alleen iOS-apparaten|
|**Status van activeringsvergrendeling**|Alleen iOS-apparaten|
|**Registratiedatum**|Alle apparaten|
|**Laatst bijgewerkt**|Alle apparaten|
|**Ethernet MAC**|Alleen Mac OS X-apparaten|
|**Activeringsvergrendeling ingeschakeld**|Alleen iOS-apparaten|
|**Versleuteling ingeschakeld**|Alle apparaten|

## Wat wordt er verzameld voor Windows-pc's?
> [!IMPORTANT]
> Deze sectie geldt alleen voor Windows-computers waarop de Intune Windows- clientsoftware wordt uitgevoerd.

Als u de inventaris wilt weergeven die voor Windows-pc’s is verzameld, voert u de [rapporten voor de inventaris van computers](understand-microsoft-intune-operations-by-using-reports.md) uit. In Intune worden de volgende inventarisgegevens van Windows-pc's verzameld:

-   **Naam**

-   **Chassistype**

-   **Fabrikant**

-   **Model**

-   **Besturingssysteem**

-   **TPM-versie**

-   **Totale schijfruimte**

-   **Gebruikte schijfruimte**

-   **Beschikbare schijfruimte**

-   **Naam besturingssysteemschijf**

-   **Ruimte op besturingssysteemschijf**

-   **Beschikbare ruimte op besturingssysteemschijf**

-   **Fysiek geheugen**

-   **Processornaam**

-   **Processorarchitectuur**

-   **CPU-snelheid**

-   **IP-adres**

-   **Serienummer**

-   **Laatst aangemelde gebruiker**

-   **Toegewezen gebruiker**

-   **Laatst bijgewerkt**

<!-- this section below belongs in the planning journey
### See Also
[Monitoring and reports with Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)
-->



<!--HONumber=Jul16_HO3-->


