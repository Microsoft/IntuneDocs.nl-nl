---
title: Een Apple MDM-pushcertificaat ophalen
titlesuffix: Microsoft Intune
description: In dit onderwerp leest u welke stappen u moet uitvoeren om een Apple MDM-pushcertificaat op te halen voor het beheren van iOS-apparaten met Intune.
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 504f2431754aa88ddf79bef4a201cbf7aa032834
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/12/2018
---
# <a name="get-an-apple-mdm-push-certificate"></a>Een Apple MDM-pushcertificaat ophalen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Intune maakt Mobile Device Management (MDM) mogelijk voor iPads, iPhones en Mac-computers en geeft gebruikers toegang tot zakelijke e-mail en apps. Een MDM-pushcertificaat is vereist zodat Intune iOS- en Mac-apparaten kan beheren. Nadat u het certificaat aan Intune hebt toegevoegd, kunnen uw gebruikers de bedrijfsportal-app installeren om hun apparaten in te schrijven. U kunt bijvoorbeeld ook beheer voor iOS-apparaten in bedrijfseigendom instellen met het Apple Device Enrollment Program of apparaten inschrijven met Apple Configurator. Raadpleeg [Kiezen hoe u iOS-apparaten registreert](enrollment-method-choose-ios.md) voor meer informatie over inschrijvingsopties.

## <a name="steps-to-get-your-certificate"></a>Stappen voor het ophalen van het certificaat
Kies in de [Azure Portal](https://portal.azure.com) **Apparaatinschrijving** > **Apple-inschrijving** > **Apple MDM-pushcertificaat** en volg deze stappen in de [Azure Portal](https://portal.azure.com).

**Stap 1. De aanvraag voor Intune-certificaatondertekening downloaden die is vereist voor het maken van een Apple MDM-pushcertificaat.**<br>
Selecteer **Uw CSR downloaden** om het aanvraagbestand te downloaden en lokaal op te slaan. Het bestand wordt gebruikt voor het aanvragen van een vertrouwensrelatiecertificaat uit de Apple Push Certificates Portal.

  ![Het scherm MDM-pushcertificaat configureren waarbij MDM-push niet is ingesteld.](./media/create-mdm-push-certificate.png)

**Stap 2. Een Apple MDM-pushcertificaat maken.**<br>
Selecteer **Uw MDM-pushcertificaat maken** om naar de portal voor Apple-pushcertificaten te gaan. Meld u aan met de Apple-id van uw bedrijf en klik op **Een certificaat maken**. Klik op **Bestand selecteren**, blader naar het bestand met de certificaatondertekeningsaanvraag en kies vervolgens **Uploaden**. Kies **Downloaden** op de bevestigingspagina om het certificaatbestand (.pem) te downloaden, en sla het bestand lokaal op.

> [!NOTE]
> Het certificaat wordt gekoppeld aan de Apple-id waarmee het wordt gemaakt. Als best practice kunt u een zakelijke Apple-id gebruiken voor beheertaken. Zorg ervoor dat het postvak wordt bewaakt door meer dan één persoon, zoals bij een distributielijst. Gebruik nooit een persoonlijke Apple-id.

**Stap 3. De Apple ID invoeren die is gebruikt om uw Apple MDM-pushcertificaat te maken.**<br>
Bewaar deze id voor wanneer u dit certificaat moet verlengen.

**Stap 4. Bladeren naar het Apple MDM-pushcertificaat om dit te uploaden.**<br>
Ga naar het certificaatbestand (.pem), kies **Openen** en kies vervolgens **Uploaden**. Met het pushcertificaat kan Intune Apple-apparaten inschrijven en beheren.

## <a name="renew-apple-mdm-push-certificate"></a>Een Apple MDM-pushcertificaat verlengen
Het Apple MDM-pushcertificaat is één jaar geldig en moet elk jaar worden verlengd om het iOS- en macOS-apparaatbeheer te kunnen handhaven. Als het certificaat verloopt, kan er geen contact worden opgenomen met ingeschreven Apple-apparaten.

Het certificaat wordt gekoppeld aan de Apple-id waarmee het wordt gemaakt. Verlengt het MDM-pushcertificaat met dezelfde Apple-id waarmee u het hebt gemaakt.

1. Kies in [Azure Portal](https://portal.azure.com) achtereenvolgens **Apparaatinschrijving** > **Apple-inschrijving** en kies vervolgens de tegel **Apple MDM-pushcertificaat** in het gedeelte met details.
2. Kies **Uw CSR downloaden** om het aanvraagbestand te downloaden en lokaal op te slaan. Het bestand wordt gebruikt voor het aanvragen van een vertrouwensrelatiecertificaat uit de Apple Push Certificates Portal.
3. Selecteer **Uw MDM-pushcertificaat maken** om naar de portal voor Apple-pushcertificaten te gaan. Zoek het certificaat dat u wilt verlengen en selecteer **Verlengen**.
4. Via het scherm **Push-certificaat vernieuwen** voegt u notities toe om het certificaat later te kunnen identificeren. Selecteer **Bestand kiezen** om naar het gedownloade aanvraagbestand te bladeren en kiest u **Uploaden**.
   > [!TIP]
   > Een certificaat kan worden geïdentificeerd aan de hand van de bijbehorende UID. Bekijk de **onderwerp-id** in de certificaatgegevens om het GUID-gedeelte van de UID te vinden. U kunt ook op een ingeschreven iOS-apparaat naar **Instellingen** > **Algemeen** > **Apparaat** **Beheer** > **Beheerprofiel** > **Meer details** > **Beheerprofiel** gaan. Het tweede regelitem **Onderwerp** bevat de unieke GUID die u met het certificaat in het portal voor Apple-pushcertificaten kunt vergelijken.
 
6. Selecteer in het scherm **Bevestiging** de optie **Downloaden** en sla het PEM-bestand lokaal op.
7. Selecteer in de [Azure-portal](https://portal.azure.com) het bladerpictogram **Apple MDM-pushcertificaat**, selecteer het in Apple gedownloade PEM-bestand en kies **Uploaden**.

Uw Apple MDM-pushcertificaat blijkt **actief** en verloopt over 365 dagen.
