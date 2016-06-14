---
# required metadata

title: Inzicht in uw apparaten met inventarisaties in Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Inzicht in uw apparaten met inventarisaties in Microsoft Intune
Met Microsoft Intune kunt u de inventarisatie bekijken van de ingeschreven apparaten en Windows-pc's waarop de Intune-clientsoftware wordt uitgevoerd.

## Wat wordt er verzameld bij ingeschreven apparaten?
Als u de inventaris wilt bekijken die voor mobiele apparaten is verzameld, voert u de [rapporten voor de inventaris van mobiele apparaten](understand-microsoft-intune-operations-by-using-reports.md) uit. De volgende inventarisgegevens van ingeschreven apparaten worden door Intune verzameld:

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
|**Gekraakt of geroot**|Alleen iOS- en Android-apparaten|
|**Unieke apparaat-ID**|Alle apparaten, met uitzondering van Exchange ActiveSync|
|**Serienummer**|iOS-, Mac OS X-, Android-, Windows 8.1- en Windows 10-apparaten|
|**Totale opslagruimte**|iOS-, Mac OS X-, Windows 8.1- en Windows 10-apparaten|
|**Beschikbare opslagruimte**|iOS-, Mac OS X-, Windows 8.1- en Windows 10-apparaten|
|**Telefoonnummer**<br>Telefoons die zijn aangemerkt als bedrijfseigendom, worden aangeduid met hun volledige telefoonnummer, bijvoorbeeld wanneer u een inventarisrapport voor mobiele apparaten uitvoert. Telefoonnummers voor BYOD-apparaten worden gemaskeerd met &#42;, waarbij alleen de laatste 4 cijfers worden weergegeven.|iOS-, Android- en Windows Phone-apparaten|
|**IMEI**|Exchange ActiveSync-, iOS-, Android- en Windows Phone-apparaten|
|**MEID**<br>Mobile Equipment Identifier|Alleen iOS-apparaten|
|**MAC-adres Wi-Fi**|Alle apparaten, met uitzondering van Exchange ActiveSync|
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

Als u de inventaris wilt weergeven die voor Windows-pc’s is verzameld, voert u de [rapporten voor de inventaris van computers](understand-microsoft-intune-operations-by-using-reports.md) uit. De volgende inventarisgegevens van Windows-pc’s worden door Intune verzameld:

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

### Zie ook
[Bewaking en rapporten voor Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=May16_HO1-->


