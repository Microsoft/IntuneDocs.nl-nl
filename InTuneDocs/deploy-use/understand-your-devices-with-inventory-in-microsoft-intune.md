---
title: Inzicht in uw apparaten met inventarisaties | Microsoft Docs
description: Gebruik Intune voor het weergeven van informatie over de hardware van de apparaten die u beheert.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 3ae5809f8506e2255d9443d3587f2564bc863066


---

# <a name="understand-your-devices-with-inventory-in-microsoft-intune"></a>Inzicht in uw apparaten met inventarisaties in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Met Microsoft Intune kunt u de inventarisatie bekijken van de ingeschreven apparaten en Windows-pc's waarop de Intune-clientsoftware wordt uitgevoerd.
Intune verzamelt inventaris van beheerde apparaten gewoonlijk om de zeven dagen. Hierdoor kan het langer duren voordat de resultaten van recente wijzigingen aan apparaten, bijvoorbeeld een wijziging van de apparaatnaam, of vrije opslagruimte in rapporten worden weergegeven.

## <a name="whats-collected-from-enrolled-devices"></a>Wat wordt er verzameld bij ingeschreven apparaten?
Als u de inventarisatiegegevens wilt bekijken die door mobiele apparaten zijn verzameld, voert u de [Inventarisrapporten voor mobiele apparaten](understand-microsoft-intune-operations-by-using-reports.md) uit. In Intune worden de volgende inventarisgegevens van ingeschreven apparaten verzameld:

|Eigenschap|Verzameld door|
|------------|-----------------------|
|**Naam**|Alle apparaten|
|**Besturingssysteem**|Alle apparaten|
|**Fabrikant**|Alle apparaten|
|**Model**|Alle apparaten|
|**Beheerkanaal**|Alle apparaten|
|**Geregistreerd bij AAD**|Alle apparaten, met uitzondering van Mac OS X|
|**Compatibel**|Alle apparaten|
|**EAS geactiveerd**|Alle apparaten, met uitzondering van Mac OS X|
|**Activerings-id voor EAS**|Alle apparaten, met uitzondering van Mac OS X|
|**Activeringstijd voor EAS**|Alle apparaten, met uitzondering van Mac OS X|
|**Beheerstatus**|Alle apparaten|
|**E-mailadres**|Alle apparaten|
|**Exchange ActiveSync-id**|Alle apparaten|
|**Apparaten waarop jailbreaking of rooting is uitgevoerd**|Alleen iOS- en Android-apparaten|
|**Unieke apparaat-ID**|Alle apparaten, met uitzondering van Exchange Active Sync|
|**Serienummer**|iOS-, Mac OS X-, Android-, Windows 8.1- en Windows 10 Desktop-apparaten|
|**Totale opslagruimte**|iOS-, Mac OS X-, Windows 8.1- en Windows 10 Desktop- en Mobile-apparaten|
|**Beschikbare opslagruimte**|iOS-, Mac OS X-, Windows 8.1- en Windows 10 Desktop-apparaten|
|**Telefoonnummer**<br>Telefoons die zijn aangemerkt als bedrijfseigendom, worden aangeduid met hun volledige telefoonnummer (bijvoorbeeld wanneer u een inventarisrapport voor mobiele apparaten uitvoert). Telefoonnummers voor BYOD-apparaten worden gemaskeerd met &#42;, waarbij alleen de laatste vier cijfers worden weergegeven.|iOS-, Android- en Windows Phone-apparaten|
|**IMEI**|Exchange Active Sync-, iOS-, Android- en Windows Phone-apparaten|
|**MEID**<br>Mobile Equipment Identifier|Alleen iOS-apparaten|
|**MAC-adres Wi-Fi**|Alle apparaten, met uitzondering van Exchange Active Sync|
|**Provider van abonnee**|Alleen iOS- en Android-apparaten|
|**Mobiele telefoontechnologie**|Alleen iOS- en Android-apparaten|
|**Onder supervisie**|Alleen iOS-apparaten|
|**Activeringsstatus van vergrendeling**|Alleen iOS-apparaten|
|**Registratiedatum**|Alle apparaten|
|**Laatst bijgewerkt**|Alle apparaten|
|**Ethernet MAC**|Alleen Mac OS X-apparaten|
|**Activeringsvergrendeling ingeschakeld**|Alleen iOS-apparaten|
|**Versleuteling ingeschakeld**|Alle apparaten|

## <a name="whats-collected-from-windows-pcs"></a>Wat wordt er verzameld voor Windows-pc's?
> [!IMPORTANT]
> Deze sectie geldt alleen voor Windows-computers waarop de Intune Windows- clientsoftware wordt uitgevoerd.

Als u de inventarisatiegegevens wilt weergeven die voor Windows-pc’s worden verzameld, voert u de [Computerinventarisrapporten](understand-microsoft-intune-operations-by-using-reports.md) uit. In Intune worden de volgende inventarisgegevens van Windows-pc's verzameld:

-   **Naam**

-   **Chassistype**

-   **Fabrikant**

-   **Model**

-   **Besturingssysteem**

-   **TPM-versie**

-   **Totale schijfruimte**

-   **Gebruikte schijfruimte**

-   **Vrije schijfruimte**

-   **Naam besturingssysteemschijf**

-   **Ruimte op besturingssysteemschijf**

-   **Vrije ruimte op besturingssysteemschijf**

-   **Fysiek geheugen**

-   **Processornaam**

-   **Processorarchitectuur**

-   **CPU-snelheid**

-   **IP-adres**

-   **Serienummer**

-   **Laatste aangemelde gebruiker**

-   **Toegewezen gebruiker**

-   **Laatst bijgewerkt**

<!-- this section below belongs in the planning journey
### See Also
[Monitoring and reports with Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)
-->



<!--HONumber=Dec16_HO2-->


