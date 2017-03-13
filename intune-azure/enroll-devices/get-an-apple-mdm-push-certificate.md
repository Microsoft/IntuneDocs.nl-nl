---
title: Een Apple MDM-pushcertificaat ophalen
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp leest u welke stappen u moet uitvoeren om een Apple MDM-pushcertificaat op te halen voor het beheren van iOS-apparaten met Intune.'
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 26991bd0c7632d04b75ecbec023d96c1045f337a
ms.lasthandoff: 02/18/2017


---

# <a name="get-an-apple-mdm-push-certificate"></a>Een Apple MDM-pushcertificaat ophalen 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune maakt beheer van mobiele apparaten (MDM) mogelijk voor iPads, iPhones, en Mac OS X-apparaten en geeft gebruikers toegang tot zakelijke e-mail en apps. Een APNs-certificaat (Apple Push Notification-service) is vereist zodat Intune iOS- en Mac-apparaten kan beheren. Nadat u het certificaat aan Intune hebt toegevoegd, kunnen uw gebruikers de bedrijfsportal-app installeren om hun apparaten in te schrijven, of kunt u beheer voor iOS-apparaten in bedrijfseigendom instellen.

## <a name="steps-to-get-your-certificate"></a>Stappen voor het ophalen van het certificaat
Kies in Azure-portal **Meer services** > **Bewaking en beheer** > **Intune**. Kies op de blade Intune **Apparaten inschrijven** > **Apple MDM-pushcertificaat** en volg de genummerde stappen in Azure Portal. Deze stappen worden hieronder weergegeven.

**Stap 1. De aanvraag voor Intune-certificaatondertekening downloaden die is vereist voor het maken van een Apple MDM-pushcertificaat.**<br>
Selecteer **Uw CSR downloaden** om het CSR-bestand te downloaden en lokaal op te slaan. Het CSR-bestand wordt gebruikt voor het aanvragen van een vertrouwensrelatiecertificaat uit de Apple Push Certificates Portal.

**Stap 2. Een Apple MDM-pushcertificaat maken.**<br>
Selecteer **Uw MDM-pushcertificaat maken** om naar de portal voor Apple-pushcertificaten te gaan. Meld u aan met de Apple ID van uw bedrijf om het pushcertificaat te maken met behulp van het CSR-bestand. Nadat u in de portal voor Apple-pushcertificaten **Uploaden** hebt gekozen, ontvangt u een JSON-bestand. Gebruik dit bestand voor het pushcertificaat. Voltooi het downloaden en keer terug naar de Apple Push Certificates-portal voor certificaten voor servers van derden. Kies **Downloaden**. Download het pushcertificaat (PEM-bestand) en sla het bestand lokaal op.
Opmerking

**Stap 3. De Apple ID invoeren die is gebruikt om uw Apple MDM-pushcertificaat te maken.**

**Stap 4. Bladeren naar het Apple MDM-pushcertificaat om dit te uploaden.**<br>
Ga naar het certificaatbestand (.pem), kies **Openen** en kies vervolgens **Uploaden**. Met het pushcertificaat kan Intune iOS-apparaten inschrijven en beheren door beleid naar geregistreerde mobiele apparaten te pushen.

