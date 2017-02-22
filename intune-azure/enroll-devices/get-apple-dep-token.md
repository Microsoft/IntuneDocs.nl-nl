---
title: Een Apple DEP-certificaat voor Intune ophalen | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp vindt u instructies voor het configureren en uploaden van een MDM-pushcertificaat, een vereiste voor het beheren van Apple-apparaten in Intune. '
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e5c79c5-2883-4841-9be6-74cba16ee447
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 65a6b2e22359bdcb9b0c15a84c6b3586dafe4d6c
ms.openlocfilehash: c740dedebdc4afd909a8c38447f698c2724de5a1

---

# <a name="get-an-apple-dep-certificate"></a>Een Apple DEP-certificaat ophalen 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Voordat u iOS-apparaten van het bedrijf met DEP kunt inschrijven, moet u een DEP-token van Apple ontvangen. Intune kan met dit token informatie synchroniseren over apparaten binnen uw bedrijf die aan DEP deelnemen. Ook kan Intune hiermee inschrijvingsprofielen naar Apple uploaden en apparaten toewijzen aan die profielen.

Voor het beheren van iOS-apparaten in bedrijfseigendom met het Device Enrollment Program (DEP) van Apple moet uw organisatie lid worden van DEP en apparaten verwerven via dat programma. Details van dit proces kunt u vinden op: https://deploy.apple.com. Voordelen van het programma zijn onder andere handsfree instellen, dus zonder dat elk apparaat via een USB-verbinding op een computer moet worden aangesloten.

> [!NOTE]
> Lees deze opmerking alleen als u een klant bent die vanuit de Intune-beheerconsole is gemigreerd naar Azure Portal. Als u een Apple DEP-token van de Intune-beheerconsole hebt verwijderd tijdens de migratieperiode, merkt u dat het DEP-token in uw Intune-account is hersteld. Als dit gebeurt, moet u alleen het DEP-token uit Azure Portal verwijderen. 

**Het Apple DEP-certificaat ophalen**</br>
Kies in Azure Portal **Meer services**, voer **Intune** in het tekstvak in en kies **Overige** > **Intune**. Kies op de blade Intune **Apparaten inschrijven** > **Apple DEP-token** en volg de genummerde stappen in Azure Portal. Deze stappen worden hieronder weergegeven.

**Stap 1. Download een openbare-sleutelcertificaat van Intune dat is vereist voor het maken van een Apple DEP-token.**<br>
Selecteer **Uw openbare-sleutelcertificaat downloaden** en sla het bestand met de versleutelingssleutel (.pem) lokaal op. Het .pem-bestand wordt gebruikt om een vertrouwensrelatiecertificaat bij de portal Apple Device Enrollment Program aan te vragen.

**Stap 2. Download een Apple DEP-token vanaf de betreffende Apple-website.**<br>
Selecteer [Een DEP-token via Apple Deployment Programs maken](https://deploy.apple.com) (https://deploy.apple.com) en meld u aan met de Apple ID van uw bedrijf. Deze Apple ID moet u later gebruiken om uw DEP-token te verlengen.

   1.  Ga in de [portal Device Enrollment Program](https://deploy.apple.com) naar **Programma apparaatinschrijving** &gt; **Servers beheren** en kies **MDM-server toevoegen**.

   2.  Voer de **MDM-servernaam** in en kies **Volgende**. De servernaam is voor eigen referentie en dient om de MDM-server te identificeren. Het is niet de naam of URL van de Microsoft Intune-server.

   3.  Het dialoogvenster **&lt;Servernaam&gt; toevoegen** wordt geopend. Kies **Bestand selecteren...** om het .pem-bestand te uploaden en kies **Volgende**.

   4.  In het dialoogvenster **&lt;Servernaam&gt; toevoegen** wordt een koppeling met **Uw servertoken** weergegeven. Download het servertokenbestand (.p7m) naar uw computer en kies **Gereed**.

    Dit certificaatbestand (.p7m) wordt gebruikt om een vertrouwensrelatie tussen Intune en de Device Enrollment Program-servers van Apple tot stand te brengen.

**Stap 3. Voer de Apple ID in die u hebt gebruikt om uw Apple DEP-token te maken. Deze ID kan worden gebruikt om uw Apple DEP-token te verlengen.**

**Stap 4. Blader naar het Apple DEP-token dat u wilt uploaden. Intune voert automatisch een synchronisatie met uw DEP-account uit.**<br>
Ga naar het certificaatbestand (.pem), kies **Openen** en kies vervolgens **Uploaden**. Met het pushcertificaat kan Intune iOS-apparaten inschrijven en beheren door beleid naar geregistreerde mobiele apparaten te pushen.



<!--HONumber=Feb17_HO1-->


