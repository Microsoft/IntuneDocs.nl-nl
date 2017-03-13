---
title: Een Apple DEP-certificaat voor Intune ophalen
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp vindt u instructies voor het configureren en uploaden van een MDM-pushcertificaat, een vereiste voor het beheren van Apple-apparaten in Intune. '
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e5c79c5-2883-4841-9be6-74cba16ee447
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 8edc42bb86e3856ac6568cc3c1acc5d757978e79
ms.lasthandoff: 02/18/2017

---

# <a name="get-an-apple-dep-certificate"></a>Een Apple DEP-certificaat ophalen

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Voordat u iOS-apparaten van het bedrijf met het Apple Device Enrollment Program (DEP) kunt inschrijven, moet u een DEP-token van Apple ontvangen. Intune kan met dit token informatie synchroniseren over apparaten binnen uw bedrijf die aan DEP deelnemen. Ook kan Intune hiermee inschrijvingsprofielen naar Apple uploaden en apparaten toewijzen aan die profielen.

Voor het beheren van iOS-apparaten in bedrijfseigendom met het DEP van Apple moet uw organisatie lid worden van DEP en apparaten verwerven via dat programma. Details van dit proces kunt u vinden op: https://deploy.apple.com. Voordelen van het programma zijn onder andere handsfree instellen, dus zonder dat elk apparaat via een USB-verbinding op een computer moet worden aangesloten.

> [!NOTE]
> Deze opmerking is alleen van toepassing op klanten die vanuit de Intune-beheerconsole zijn gemigreerd naar de Azure Portal. Als u een Apple DEP-token van de Intune-beheerconsole hebt verwijderd tijdens de migratieperiode, merkt u dat het DEP-token in uw Intune-account is hersteld. Als dit gebeurt, moet u alleen het DEP-token uit Azure Portal verwijderen.

## <a name="steps-to-get-the-apple-dep-certificate"></a>Stappen voor het ophalen van het Apple DEP-certificaat
Kies in Azure-portal **Meer services** > **Bewaking en beheer** > **Intune**. Kies op de blade Intune **Apparaten inschrijven** > **Apple DEP-token** en volg de genummerde stappen in Azure Portal. Deze stappen worden hieronder weergegeven.

**Stap 1. Download een openbare-sleutelcertificaat van Intune dat is vereist voor het maken van een Apple DEP-token.**<br>
Selecteer **Uw openbare-sleutelcertificaat downloaden** en sla het bestand met de versleutelingssleutel (.pem) lokaal op. Het .pem-bestand wordt gebruikt om een vertrouwensrelatiecertificaat bij de portal Apple Device Enrollment Program aan te vragen.

**Stap 2. Download een Apple DEP-token vanaf de betreffende Apple-website.**<br>
Selecteer [Een DEP-token via Apple Deployment Programs maken](https://deploy.apple.com) (https://deploy.apple.com) en meld u aan met de Apple ID van uw bedrijf. Deze Apple ID moet u later gebruiken om uw DEP-token te verlengen.

   a.  Ga in de [portal Device Enrollment Program](https://deploy.apple.com) naar **Programma apparaatinschrijving** &gt; **Servers beheren** en kies **MDM-server toevoegen**.

   b.  Voer de **MDM-servernaam** in en kies **Volgende**. De servernaam is voor eigen referentie en dient om de MDM-server te identificeren. Het is niet de naam of URL van de Microsoft Intune-server.

   c.  Het dialoogvenster **&lt;Servernaam&gt; toevoegen** wordt geopend. Kies **Bestand selecteren...** om het .pem-bestand te uploaden en kies **Volgende**.

   d.  In het dialoogvenster **&lt;Servernaam&gt; toevoegen** wordt een koppeling met **Uw servertoken** weergegeven. Download het servertokenbestand (.p7m) naar uw computer en kies **Gereed**.

    This certificate (.p7m) file is used to establish a trust relationship between Intune and Apple’s Device Enrollment Program servers.

**Stap 3. Voer de Apple ID in die u hebt gebruikt om uw Apple DEP-token te maken. Deze ID kan worden gebruikt om uw Apple DEP-token te verlengen.**

**Stap 4. Blader naar het Apple DEP-token dat u wilt uploaden. Intune voert automatisch een synchronisatie met uw DEP-account uit.**<br>
Ga naar het certificaatbestand (.pem), kies **Openen** en kies vervolgens **Uploaden**. Met het pushcertificaat kan Intune iOS-apparaten inschrijven en beheren door beleid naar geregistreerde mobiele apparaten te pushen.

