---
title: IOS-of iPadOS-apparaat inschrijven met Intune-bedrijfsportal en intermijnen
description: Meer informatie over het registreren van een iOS-of iPadOS-apparaat en het instellen van afgeleide referentie verificatie met inter.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: tisilver
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: 2a2c3264b2894ad81a64e7aaa7d3697f069dbfbb
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 01/10/2020
ms.locfileid: "75856284"
---
# <a name="set-up-ios-or-ipados-device-with-company-portal-and-intercede"></a>IOS-of iPadOS-apparaten instellen met Bedrijfsportal en intermijnen

Registreer uw apparaat met de Intune-bedrijfsportal voor beveiligde, mobiele toegang tot e-mail, bestanden en apps van uw organisatie.  Nadat uw apparaat is geregistreerd, wordt het *beheerd*. Uw organisatie kan beleid en apps aan het apparaat toewijzen via een MDM-provider (Mobile Device Management), zoals Intune.  

Tijdens de registratie installeert u ook een afgeleide referentie op het apparaat. Uw organisatie vereist mogelijk dat u de afgeleide referentie gebruikt als verificatie methode bij het openen van bronnen of voor het ondertekenen en versleutelen van e-mail berichten. 

U moet waarschijnlijk een afgeleide referentie instellen als u een Smart Card gebruikt voor het volgende:

* Meld u aan bij school-of werk-apps, Wi-Fi en virtuele particuliere netwerken (VPN)
* E-mail berichten voor school of werk ondertekenen en versleutelen met S/MIME-certificaten  

In dit artikel gaat u het volgende doen:  

* Registreer een mobiel iOS-of iPadOS-apparaat met Intune-bedrijfsportal.  
* Haal een afgeleide referentie op van de afgeleide referentie provider van uw organisatie, voor [rang](https://www.intercede.com/).   


## <a name="what-are-derived-credentials"></a>Wat zijn afgeleide referenties?  
Een afgeleide referentie is een certificaat dat is afgeleid van uw smartcard referenties en op uw apparaat is geïnstalleerd. Het biedt u externe toegang tot werk resources, waarbij wordt voor komen dat onbevoegde gebruikers toegang krijgen tot gevoelige informatie.  

Afgeleide referenties worden gebruikt voor het volgende: 
* Studenten en mede werkers verifiëren die zich aanmelden bij school-of werk-apps, Wi-Fi en VPN
* E-mail berichten van school of werk ondertekenen en versleutelen met S/MIME-certificaten  

Afgeleide referenties zijn een implementatie van de NIST-richtlijnen (National Institute of Standards and Technology) voor afgeleide PIV-referenties (Personal Identity Verification) als onderdeel van Special Publication (SP) 800-157.  

## <a name="prerequisites"></a>Vereisten

 Als u de inschrijving wilt volt ooien, hebt u het volgende nodig:

* De Smart Card van uw school of werk
* Toegang tot een computer of self-service kiosk waarbij u zich kunt aanmelden met uw Smart Card
* Uw mobiele apparaat
* De Intune-bedrijfsportal-app voor iOS en iPadOS geïnstalleerd op uw apparaat


## <a name="enroll-device"></a>Een apparaat inschrijven  
1. Open de Bedrijfsportal-app voor iOS-iPadOS op uw mobiele apparaat en meld u aan met uw werk account.  
2. Noteer de code die op het scherm wordt weer gegeven.  

    ![Voorbeeld afbeelding van Bedrijfsportal-app met bericht en code op het scherm.](./media/copy-code-intercede.png)  
1. Schakel over naar het apparaat dat geschikt is voor Smart Cards en ga naar https://microsoft.com/devicelogin. 

1. Voer de code in die u eerder hebt geschreven.
 
2. Plaats de Smart Card om u aan te melden.   

3. Ga terug naar de Bedrijfsportal-app op uw mobiele apparaat en volg de instructies op het scherm om uw apparaat in te schrijven.  
4. Zodra de inschrijving is voltooid Bedrijfsportal, ontvangt u een melding over het instellen van uw Smart Card. Tik op de melding. Als u geen melding ontvangt, controleert u uw e-mail adres.   

    ![Voor beeld van een scherm opname van de Bedrijfsportal push melding op het Start scherm van het apparaat.](./media/action-required-in-app-intercede.png)  

5. Op het scherm **mobiele-smartcard toegang instellen** :  
    a. Tik op de koppeling naar de installatie-instructies van uw organisatie. Als uw organisatie geen aanvullende instructies verstrekt, wordt u naar dit artikel verzonden.  
    b. Tik op **Start**.  

    ![Voor beeld van een scherm opname van het scherm Bedrijfsportal mobiele smartcard toegang instellen.](./media/smart-card-info-intercede.png)  

6. Schakel over naar het apparaat met Smart Cards of de self-service kiosk en open de MyID-app. Meld u aan met uw werk referenties.  
7. Selecteer de optie om uw ID aan te vragen. 
8. Wanneer u wordt gevraagd welk profiel u wilt gebruiken, selecteert u de optie om te activeren met een mobiele referentie. Er wordt een QR-code weer gegeven.  
9. Ga terug naar uw mobiele apparaat. Tik op het scherm Bedrijfsportal > **QR-code ophalen** op **door gaan**.  

    ![Voor beeld scherm afbeelding van het scherm Bedrijfsportal QR-code ophalen.](./media/get-qr-code-intercede.png) 
 
10. Tik op **camera gebruiken** > **OK**.  

    ![Voor beeld van een scherm opname van een Bedrijfsportal prompt, waarbij toestemming wordt gevraagd om toegang tot de camera toe te staan.](./media/allow-cp-camera-access-intercede.png)  

11. Scan de afbeelding van de QR-code op uw Smart Card-apparaat. 
12. Wacht tot Bedrijfsportal uw apparaat hebt ingesteld.  

## <a name="next-steps"></a>Volgende stappen  
Nadat de inschrijving is voltooid, hebt u toegang tot werk resources, zoals e-mail, Wi-Fi en alle apps die uw organisatie beschikbaar maakt. Voor meer informatie over het verkrijgen, zoeken, installeren en verwijderen van apps in de Bedrijfsportal raadpleegt u:

* [Apps beheren via de Bedrijfsportalwebsite](manage-apps-cpweb.md)  
* [Beheerde apps op een apparaat gebruiken](use-managed-apps-on-your-device-ios.md)  

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Controleer of de contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).
