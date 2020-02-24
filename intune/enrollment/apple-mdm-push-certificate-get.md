---
title: Een Apple MDM-pushcertificaat voor Intune ophalen
titleSuffix: ''
description: Lees hoe u een Apple MDM-pushcertificaat kunt ophalen voor het beheren van iOS-/iPadOS-apparaten met Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 673f63194b46ca7e4dbf1206d363cbe70c6e6098
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77414431"
---
# <a name="get-an-apple-mdm-push-certificate"></a>Een Apple MDM-pushcertificaat ophalen

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Een Apple MDM-pushcertificaat is vereist zodat Intune iOS-/iPadOS- en macOS-apparaten kan beheren. Nadat u het certificaat aan Intune hebt toegevoegd, kunnen uw gebruikers hun apparaten inschrijven met:

- De bedrijfsportal-app.

- De massaregistratiemethoden van Apple zoals het Apple-apparaatinschrijvingsprogramma, Apple School Manager of Apple Configurator.

Raadpleeg [Kiezen hoe u iOS-/iPadOS-apparaten inschrijft](ios-enroll.md) voor meer informatie over inschrijvingsopties.

Wanneer een pushcertificaat is verlopen, moet u dit vernieuwen. Zorg er tijdens de vernieuwing voor dat u dezelfde Apple ID gebruikt als toen u het pushcertificaat hebt gemaakt.


## <a name="steps-to-get-your-certificate"></a>Stappen voor het ophalen van het certificaat
Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431), kies **Apparaten** > **Apparaten inschrijven** > **Apple-inschrijving** > **Apple MDM-pushcertificaat** en volg deze stappen.

### <a name="step-1-grant-microsoft-permission-to-send-user-and-device-information-to-apple"></a>Stap 1. Microsoft toestemming geven om gebruikers en apparaatgegevens naar Apple te verzenden
Selecteer **Ik ga akkoord.** om Microsoft toestemming te geven om gegevens te verzenden naar Apple.

![Het scherm MDM-pushcertificaat configureren waarbij MDM-push niet is ingesteld.](./media/apple-mdm-push-certificate-get/create-mdm-push-certificate.png)

### <a name="step-2-download-the-intune-certificate-signing-request-required-to-create-an-apple-mdm-push-certificate"></a>Stap 2. De aanvraag voor Intune-certificaatondertekening downloaden die is vereist voor het maken van een Apple MDM-pushcertificaat
Selecteer **Uw CSR downloaden** om het aanvraagbestand te downloaden en lokaal op te slaan. Het bestand wordt gebruikt voor het aanvragen van een vertrouwensrelatiecertificaat uit de Apple Push Certificates Portal.

### <a name="step-3-create-an-apple-mdm-push-certificate"></a>Stap 3. Een Apple MDM-pushcertificaat maken
Selecteer **Uw MDM-pushcertificaat maken** om naar de portal voor Apple-pushcertificaten te gaan. Meld u aan met de Apple-id van uw bedrijf en klik op **Een certificaat maken**. Klik op **Bestand selecteren**, blader naar het bestand met de certificaatondertekeningsaanvraag en kies vervolgens **Uploaden**. Kies **Downloaden** op de bevestigingspagina om het certificaatbestand (.pem) te downloaden, en sla het bestand lokaal op.

> [!NOTE]
> Het certificaat wordt gekoppeld aan de Apple-id waarmee het wordt gemaakt. Als best practice kunt u een zakelijke Apple-id gebruiken voor beheertaken. Zorg ervoor dat het postvak wordt bewaakt door meer dan één persoon, zoals bij een distributielijst. Gebruik nooit een persoonlijke Apple-id.

### <a name="step-4-enter-the-apple-id-used-to-create-your-apple-mdm-push-certificate"></a>Stap 4. De Apple ID invoeren die is gebruikt om uw Apple MDM-pushcertificaat te maken
Bewaar deze id voor wanneer u dit certificaat moet verlengen.

### <a name="step-5-browse-to-your-apple-mdm-push-certificate-to-upload"></a>Stap 5. Bladeren naar het Apple MDM-pushcertificaat om dit te uploaden
Ga naar het certificaatbestand (.pem), kies **Openen** en kies vervolgens **Uploaden**. Met het pushcertificaat kan Intune Apple-apparaten inschrijven en beheren.

## <a name="renew-apple-mdm-push-certificate"></a>Een Apple MDM-pushcertificaat verlengen
Het Apple MDM-pushcertificaat is één jaar geldig en moet elk jaar worden verlengd om het iOS-/iPadOS- en macOS-apparaatbeheer te kunnen handhaven. Als het certificaat verloopt, kan er geen contact worden opgenomen met ingeschreven Apple-apparaten.

Het certificaat wordt gekoppeld aan de Apple-id waarmee het wordt gemaakt. Verlengt het MDM-pushcertificaat met dezelfde Apple-id waarmee u het hebt gemaakt.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431), kies **Apparaten** > **Apparaten inschrijven** > **Apple-inschrijving** > **Apple MDM-pushcertificaat**.
2. Kies **Uw CSR downloaden** om het aanvraagbestand te downloaden en lokaal op te slaan. Het bestand wordt gebruikt voor het aanvragen van een vertrouwensrelatiecertificaat uit de Apple Push Certificates Portal.
3. Selecteer **Uw MDM-pushcertificaat maken** om naar de portal voor Apple-pushcertificaten te gaan. Zoek het certificaat dat u wilt verlengen en selecteer **Verlengen**.
4. Via het scherm **Push-certificaat vernieuwen** voegt u notities toe om het certificaat later te kunnen identificeren. Selecteer **Bestand kiezen** om naar het gedownloade aanvraagbestand te bladeren en kiest u **Uploaden**.
   > [!TIP]
   > Een certificaat kan worden geïdentificeerd aan de hand van de bijbehorende UID. Bekijk de **onderwerp-id** in de certificaatgegevens om het GUID-gedeelte van de UID te vinden. U kunt ook op een ingeschreven iOS-/iPadOS-apparaat naar **Instellingen** > **Algemeen** > **Apparaat** **Beheer** > **Beheerprofiel** > **Meer details** > **Beheerprofiel** gaan. Het tweede regelitem **Onderwerp** bevat de unieke GUID die u met het certificaat in het portal voor Apple-pushcertificaten kunt vergelijken.
 
6. Selecteer in het scherm **Bevestiging** de optie **Downloaden** en sla het PEM-bestand lokaal op.
7. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), selecteer het bladerpictogram **Apple MDM-pushcertificaat**, selecteer het in Apple gedownloade PEM-bestand en kies **Uploaden**.

Uw Apple MDM-pushcertificaat blijkt **actief** en verloopt over 365 dagen.
