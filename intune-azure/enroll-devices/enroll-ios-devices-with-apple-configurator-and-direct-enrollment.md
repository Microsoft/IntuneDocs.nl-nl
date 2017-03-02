---
title: iOS-apparaten registreren met Apple Configurator en directe inschrijving
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u Apple Configurator kunt gebruiken om iOS-apparaten die bedrijfseigendom zijn in te schrijven met directe inschrijving.'
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: d335572ae2bc5ce74532de281658d06903f995ee
ms.lasthandoff: 02/18/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-direct-enrollment"></a>iOS-apparaten registreren met Apple Configurator en directe inschrijving 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune ondersteunt het inschrijven van iOS-apparaten die bedrijfseigendom zijn, met behulp van het hulpprogramma [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) dat wordt uitgevoerd op een Mac-computer. Met dit proces wordt het apparaat niet teruggezet op de fabrieksinstellingen en wordt het apparaat met een vooraf gedefinieerd beleid geregistreerd. Deze methode is bedoeld voor apparaten waarop **geen relatie met gebruiker** is ingesteld. Voor deze methode is vereist dat u met het iOS-apparaat een USB-verbinding met een Mac-computer maakt om bedrijfsinschrijving in te stellen.

>[!NOTE]
>Deze inschrijvingsmethode kan niet worden gebruikt met de methode [Apparaatinschrijvingsmanager](enroll-devices-using-device-enrollment-manager.md).

Wanneer u iOS-apparaten rechtstreeks inschrijft, kunt u een apparaat inschrijven zonder het serienummer van het apparaat in te voeren. U kunt ook het apparaat een naam geven voor identificatiedoeleinden voordat Intune de naam van het apparaat vastlegt tijdens de inschrijving. De bedrijfsportal-app wordt niet ondersteund voor rechtstreeks ingeschreven apparaten. In deze richtlijnen wordt ervan uitgegaan dat u Apple Configurator 2.0 gebruikt op een Mac-computer.

Andere methoden voor het registreren van iOS-apparaten worden beschreven in [Choose how to enroll iOS devices in Intune](choose-ios-enrollment-method.md) (Kiezen hoe iOS-apparaten worden geregistreerd in Intune).


## <a name="prerequisites"></a>Vereisten

Voer de volgende vereisten uit voordat u inschrijving van iOS-apparaten instelt:

- [Domeinen configureren](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [MDM-instantie instellen](set-mdm-authority.md)
- [Groepen maken](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [De bedrijfsportal configureren](/intune-azure/manage-apps/company-portal-app.md)
- Gebruikerslicenties toewijzen in de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Een Apple MDM-pushcertificaat ophalen](get-an-apple-mdm-push-certificate.md)
- Fysieke toegang tot de iOS-apparaten
- Serienummers van apparaten (zie [Een iOS-serienummer opvragen](https://support.apple.com//HT204308))
- USB-verbindingskabels
- Een Mac-computer waarop [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) is geïnstalleerd

## <a name="create-an-apple-configurator-profile-for-devices"></a>Een Apple Configurator-profiel maken voor apparaten

Met een inschrijvingsprofiel voor apparaten worden de instellingen gedefinieerd die worden toegepast op een groep apparaten. De volgende stappen laten zien hoe u een inschrijvingsprofiel kunt maken voor iOS-apparaten die worden ingeschreven met Apple Configurator.

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Apple-inschrijving**.

3. Selecteer **AC-profielen** onder **Instellingen van de inschrijving van Apple Configurator beheren**.

4. Selecteer **Maken** op de blade **Apple Configurator-inschrijvingsprofielen**.

5. Voer op de blade **Inschrijvingsprofiel maken** een naam en een beschrijving in voor het profiel.

6. Kies voor **Gebruikersaffiniteit** de optie **Inschrijven zonder gebruikersaffiniteit** om ervoor te zorgen dat het apparaat niet aan een gebruiker is gekoppeld. Gebruik deze relatie voor apparaten waarmee taken worden uitgevoerd zonder toegang tot lokale gebruikersgegevens. Apps waarvoor een gebruikersrelatie is vereist, zoals de bedrijfsportal-app die wordt gebruikt voor het installeren van LOB-apps, zullen niet werken.

7. Selecteer **Maken** om het profiel op te slaan.

## <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Het profiel als .mobileconfig exporteren naar iOS-apparaten

1. Download het inschrijvingsprofiel op de blade **Profiel exporteren** naar [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) om dit direct als een beheerprofiel te pushen naar een aangesloten iOS-apparaat. De fabrieksinstellingen hoeven niet te worden teruggezet.

2. Bereid het apparaat met behulp van de volgende stappen voor met Apple Configurator.

   a. Open Apple Configurator 2.0 op een Mac-computer.

   b. Verbind het iOS-apparaat met de Mac-computer met behulp van een USB-kabel. Sluit Foto's, iTunes en andere apps die voor het apparaat worden geopend wanneer het apparaat wordt gedetecteerd.

   c. Kies in Apple Configurator het verbonden iOS-apparaat en kies vervolgens de knop **Toevoegen**. Opties die kunnen worden toegevoegd aan het apparaat, worden weergegeven in de vervolgkeuzelijst. Kies **Profielen**.

   d. Gebruik de bestandskiezer om het .mobileconfig-bestand te selecteren dat u uit Intune hebt geëxporteerd. Kies vervolgens **Toevoegen**. Het profiel wordt toegevoegd aan het apparaat. Als het apparaat niet onder supervisie is, vereist de installatie acceptatie op het apparaat.

3. Voer de volgende stappen uit om het profiel op het iOS-apparaat te installeren. Het apparaat moet de Configuratieassistent al hebben uitgevoerd en gereed zijn voor gebruik. Als inschrijving app-implementaties omvat, moet op het apparaat een Apple ID zijn ingesteld, omdat de app-implementaties vereisen dat u met een Apple ID bent aangemeld voor de App Store.

   a. Ontgrendel het iOS-apparaat.

   b. Kies in het dialoogvenster **Profiel installeren** voor **Beheerprofiel** de optie **Installeren**.

   c. Geef zo nodig een wachtwoordcode of Apple ID op.

   d. Accepteer de **Waarschuwing** en kies **Installeren**.

   e. Accepteer de **Externe waarschuwing** en kies **Vertrouwen**.

   f. Wanneer in het vak **Profiel geïnstalleerd** wordt bevestigd dat het profiel is geïnstalleerd, kiest u **Gereed**.

4. Open **Instellingen** op het iOS-apparaat en ga naar **Algemeen** > **Apparaatbeheer** > **Beheerprofiel**. Controleer of de profielinstallatie wordt weergegeven en controleer vervolgens de iOS-beleidsbeperkingen en geïnstalleerde apps. Het kan 10 minuten duren voordat beleidsbeperkingen en apps worden weergegeven op het apparaat.

5. Apparaten distribueren. Het iOS-apparaat is nu ingeschreven bij Intune en wordt beheerd.

