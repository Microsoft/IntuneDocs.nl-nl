---
title: Mobile Device Management evalueren in Microsoft Intune | Microsoft Docs
description: Evalueer MDM in uw gratis proefversie van Intune.
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 4133c64d283682f0be37cd6ac69164ef872a5026
ms.lasthandoff: 01/05/2017


---

# <a name="evaluate-mobile-device-management-in-microsoft-intune"></a>Mobile Device Management evalueren in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In deze evaluatiehandleiding wordt uitgelegd hoe Mobiel Device Management werkt in Intune. U gaat als volgt te werk:
- Registreer een apparaat dat moet worden beheerd door Intune.
- Maak groepen om gebruikers en apparaten in te delen.
- Maak enkele beleidsregels voor apparaatbeheer en implementeer deze naar uw groepen.
- Publiceer een app zodat gebruikers met geregistreerde apparaten deze op hun apparaat kunnen installeren.
<!--- - Monitor the device? View a report of compliant devices?--->
<!--- - Remove the device from management--->

## <a name="assumptions"></a>Aannames
In deze handleiding wordt verondersteld dat u de evaluatieversie uitsluitend voor evaluatiedoeleinden gebruikt en u met een schone omgeving wilt beginnen wanneer u zich abonneert.

We zorgen ervoor dat u snel aan de slag kunt met de proefversie door een zeer eenvoudige omgeving in te stellen die alleen gebruikmaakt van Intune en ervan uitgaat dat dit uw instantie voor het beheren van mobiele apparaten is. De handleiding bevat echter ook verwijzingen naar diepere technische inhoud voor verdere exploratie.

De proefversie biedt dezelfde mogelijkheden als de abonnementsversie. Het enige verschil is dat de proefversie is beperkt tot maximaal 100 gebruikersaccounts.

## <a name="whats-not-covered"></a>Wat er niet wordt behandeld
|Als u geïnteresseerd bent in |Leest u |
|------------------------|----------|
|MDM in een niet-testomgeving | [Aan de slag](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune) |
|MDM met Intune en System Center Configuration Manager | [Hybride MDM](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management) |

Aangezien de bovenstaande handleidingen u helpen Intune in te stellen in een productieomgeving, zijn ze langer en bevatten ze meer beslissingspunten dan de evaluatiehandleiding.

U kunt het beste met de evaluatiehandleiding beginnen om snel vertrouwd te raken met Intune. Vervolgens kunt u de andere handleidingen gebruiken.

## <a name="prerequisites-for-this-evaluation"></a>Vereisten voor deze evaluatie
- Internet Explorer 10 of hoger
- Een apparaat met een webbrowser. Hiermee test u hoe Intune-gebruikers hun apparaten via de bedrijfsportal registreren en beheren. We gebruiken een iPad en een Android-telefoon voor deze handleiding.
- Als u de iPad of een ander iOS-apparaat wilt beheren, hebt u een [Apple Push Notification Service-certificaat](https://docs.microsoft.com/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) nodig.
- Een [Intune-proefabonnement](sign-up-for-30-day-trial-microsoft-intune.md)

## <a name="set-your-mdm-authority"></a>Uw MDM-instantie instellen
Als u uw mobiele apparaten wilt beheren met Intune, moet u eerst uw **MDM-instantie (Mobile Device Management)** instellen.

Als u Intune geheel zelfstandig gebruikt, waarvan wordt uitgegaan, of als u Intune gebruikt als onderdeel van een EMS-abonnement (Enterprise Mobility + Security), moet u Intune instellen als uw MDM-instantie. Dat wil zeggen dat u Intune aanwijst als de service waarmee mobiele apparaten in uw organisatie worden beheerd.

Klanten die Intune in combinatie met System Center Configuration Manager willen gebruiken om mobiele apparaten te beheren, moeten besluiten of ze Intune of Configuration Manager als MDM-instantie willen gebruiken. Dit is een belangrijke beslissing in een productieomgeving omdat het momenteel zeer moeilijk is om de instelling achteraf te wijzigen. Dit valt echter buiten het kader van deze evaluatiehandleiding. Zie [Choose between standalone Intune and hybrid mobile device management](https://docs.microsoft.com/en-us/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management) (Kiezen tussen zelfstandige versie van Intune en hybride Mobile Device Management) voor meer informatie over de implicaties van de keuze voor Intune of Configuration Manager als uw MDM-instantie.

Voor de proefversie wordt Intune ingesteld als MDM-instantie. Dit heeft geen gevolgen voor uw productieomgeving, tenzij u besluit uw proefversie voor uw productieomgeving te gebruiken.

1. Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Beheer** &gt; **Mobile Device Management**.
2. Kies in de lijst **Taken** de optie **MDM-instantie instellen**. Het dialoogvenster **Instantie voor beheer van mobiele apparaten instellen** wordt geopend. <!---screen shot--->
3. Intune vraagt u te bevestigen dat u Intune wilt gebruiken als uw MDM-instantie. Schakel het selectievakje in en kies vervolgens **Ja** als u mobiele apparaten wilt beheren met Intune.

## <a name="enroll-your-test-devices-into-intune"></a>Uw testapparaten registreren bij Intune

In het kader van deze handleiding worden er een Android-telefoon en een Apple iPad geregistreerd. Daarnaast vindt u aan het eind van deze sectie koppelingen naar [meer informatie over het registreren van apparaten in Intune](#Learn-more-about-device-enrollment).
### <a name="android"></a>Android
Installeer de app **Intune-bedrijfsportal** van Microsoft Corporation via [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) en meld u aan met de Intune-[gebruikersreferenties die u hebt gemaakt](sign-up-for-30-day-trial-microsoft-intune.md#add-users) toe u zich hebt aangemeld voor de gratis proefversie.

### <a name="ios"></a>iOS
Voordat gebruikers hun iOS-apparaten kunnen registreren, moet u Intune instellen om deze apparaten te beheren.

1. **Een aanvraag voor certificaatondertekening ophalen**<br/>
Meld u met uw beheerdersaccount aan bij Intune en ga naar **Beheer** > **Mobile Device Management** > **iOS en Mac OS X** > **Een APNs-certificaat uploaden** en kies vervolgens **De APNs-certificaataanvraag downloaden**. Sla het bestand met de aanvraag voor certificaatondertekening (.csr) lokaal op. Het CSR-bestand wordt gebruikt voor het aanvragen van een vertrouwensrelatiecertificaat uit de Apple Push Certificates Portal. <!--- screen shot--->
2.    **Certificaat van Apple Push Notification Service ophalen**<BR/>
Ga naar de [Apple Push Certificates-portal](https://idmsa.apple.com/IDMSWebAuth/login?appIdKey=3fbfc9ad8dfedeb78be1d37f6458e72adc3160d1ad5b323a9e5c5eb2f8e7e3e2&rv=2) en meld u aan met de Apple-id van uw bedrijf om het APNs-certificaat te maken met het .csr-bestand. Nadat u in de Apple Push Certificates-portal **Uploaden** hebt gekozen, ontvangt u een JSON-bestand dat niet kan worden gebruikt voor APN's. Voltooi het downloaden en keer terug naar de Apple Push Certificates-portal voor certificaten voor servers van derden. Kies **Downloaden**.<br/>
Download het APNs-certificaat (.pem) en sla het bestand lokaal op. Deze Apple-id moet later worden gebruikt om uw APNs-certificaat te vernieuwen.
3.    **Het APNs-certificaat toevoegen aan Intune**<BR/>
In de Microsoft Intune-beheerconsole gaat u naar **Beheer** > **Mobiele apparaten beheren** > **iOS en Mac OS X** > **Een APNs-certificaat uploaden** en kiest u **Het APNs-certificaat uploaden**. Ga naar het certificaatbestand (.pem), klik op **Openen** en voer uw Apple-id in. Met Het APNs-certificaat kan Intune iOS-apparaten registreren en beheren door beleid naar geregistreerde mobiele apparaten te pushen.
4.    **Laat uw gebruikers weten hoe ze hun apparaten moeten registreren om toegang te krijgen tot bedrijfsbronnen.**<br/>
Zie [Uw iOS-apparaat registreren bij Intune](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-ios) of [Uw Mac OS X-apparaat registreren bij Intune](https://docs.microsoft.com/en-us/Intune/enduser/enroll-your-device-in-intune-mac-os-x) voor inschrijvingsinstructies voor eindgebruikers. Het inschrijvingsproces laat gebruikers weten wat ze kunnen verwachten, en wat IT-beheerders wel en niet kunnen zien op hun apparaten.


### <a name="learn-more-about-device-enrollment"></a>Meer informatie over apparaatregistratiemanagers

Intune ondersteunt de volgende apparaatplatformen:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

De vereisten voor het inschakelen van apparaatbeheer zijn afhankelijk van de platformen die u wilt beheren.
- Op mobiele apparaten met **Android** kunnen gebruikers zich [registreren via de bedrijfsportal-app](/intune/deploy-use/set-up-android-management-with-microsoft-intune), die beschikbaar is via Google Play. Er is geen aanvullende configuratie in Intune vereist.
- [Vereisten voor **iOS en Mac OS X**](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) instellen
- [Vereisten voor**Windows Phone**](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) instellen

<!--- ## Verify enrollment--->
<!--- START HERE

### iOS and Mac OS X
Install the **Microsoft Intune Company Portal** app from Microsoft Corporation available in the App Store and sign in with Intune user credentials added above. View **Enrolled devices** to add your device.



### Windows Phone 8.1
Users install the **Company Portal** app from Microsoft Corporation, available in the Windows Phone store, and sign in with the Intune user credentials added above.  View **Enrolled devices** to add your device.

## Install the previously deployed app
Open the Company Portal on the mobile device, choose **Apps**, and then install **Microsoft Skype**.--->



## <a name="next-steps"></a>Volgende stappen
[Groepen maken om gebruikers en apparaten in te delen](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)

