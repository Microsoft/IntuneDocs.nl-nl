---
title: IOS-of iPadOS-apparaat inschrijven met Intune-bedrijfsportal en Entrust Datacard
description: Registreer een iOS-of iPadOS-apparaat en stel afgeleide referentie verificatie in met Entrust Datacard.
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
ms.collection: M365-identity-device-management
ms.openlocfilehash: bfafa4f35d0b8f1255d66a70c3f7cd0acf01a889
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 11/01/2019
ms.locfileid: "73415760"
---
# <a name="set-up-ios-or-ipados-device-with-company-portal-and-entrust-datacard"></a>IOS-of iPadOS-apparaten instellen met Bedrijfsportal en Entrust Datacard

Registreer uw apparaat met de Intune-bedrijfsportal voor beveiligde, mobiele toegang tot e-mail, bestanden en apps van uw organisatie. Nadat uw apparaat is geregistreerd, wordt het *beheerd*. Uw organisatie kan beleid en apps aan het apparaat toewijzen via een MDM-provider (Mobile Device Management), zoals Intune.  

Tijdens de registratie installeert u ook een afgeleide referentie op het apparaat. Uw organisatie vereist mogelijk dat u de afgeleide referentie gebruikt als verificatie methode bij het openen van bronnen of voor het ondertekenen en versleutelen van e-mail berichten. 

U moet waarschijnlijk een afgeleide referentie instellen als u een Smart Card gebruikt voor het volgende:  

* Meld u aan bij school-of werk-apps, Wi-Fi en virtuele particuliere netwerken (VPN)
* E-mail berichten voor school of werk ondertekenen en versleutelen met S/MIME-certificaten  

In dit artikel gaat u als volgt te werkt:  

   * Registreer een mobiel iOS-of iPadOS-apparaat met Intune-bedrijfsportal.  
   * Een afgeleide referentie ophalen van de afgeleide referentie provider van uw organisatie, [Entrust datacard](https://www.entrustdatacard.com/).  

### <a name="what-are-derived-credentials"></a>Wat zijn afgeleide referenties?  
Een afgeleide referentie is een certificaat dat is afgeleid van uw smartcard referenties en op uw apparaat is geïnstalleerd. Het biedt u externe toegang tot werk resources, waarbij wordt voor komen dat onbevoegde gebruikers toegang krijgen tot gevoelige informatie.  

Afgeleide referenties worden gebruikt voor het volgende: 
* Studenten en mede werkers verifiëren die zich aanmelden bij school-of werk-apps, Wi-Fi en VPN
* E-mail berichten van school of werk ondertekenen en versleutelen met S/MIME-certificaten

Afgeleide referenties zijn een implementatie van de NIST-richtlijnen (National Institute of Standards and Technology) voor afgeleide PIV-referenties (Personal Identity Verification) als onderdeel van Special Publication (SP) 800-157.  

## <a name="prerequisites"></a>Vereisten

 Als u de inschrijving wilt volt ooien, hebt u het volgende nodig:

* De Smart Card van uw school of werk
* Toegang tot een computer of kiosk waar u zich kunt aanmelden met uw Smart Card
* Uw mobiele apparaat
* De Intune-bedrijfsportal-app voor iOS en iPadOS geïnstalleerd op uw apparaat  


## <a name="enroll-device"></a>Een apparaat inschrijven  
1. Open de Bedrijfsportal-app voor iOS-iPadOS op uw mobiele apparaat en meld u aan met uw werk account.  

2. Noteer de code op het scherm.  

    ![Voorbeeld afbeelding van Bedrijfsportal-app met bericht en code op het scherm.](./media/copy-code-intercede.png)   

3. Schakel over naar het apparaat dat geschikt is voor Smart Cards en ga naar https://microsoft.com/devicelogin. 
4. Voer de code in die u eerder hebt geschreven.  

    ![Voor beeld van een scherm opname van de Bedrijfsportal website ' code invoeren '.](./media/enter-code-intercede.png)   

5. Plaats de Smart Card om u aan te melden.   
6. Ga terug naar de Bedrijfsportal-app op uw mobiele apparaat en volg de instructies op het scherm om uw apparaat in te schrijven.  
7. Zodra de inschrijving is voltooid Bedrijfsportal, ontvangt u een melding over het instellen van uw Smart Card. Tik op de melding. Als u geen melding ontvangt, controleert u uw e-mail adres.   

    ![Voor beeld van een scherm opname van de Bedrijfsportal push melding op het Start scherm van het apparaat.](./media/action-required-in-app-intercede.png)  

8. Op het scherm **mobiele-smartcard toegang instellen** :   
    a. Tik op de koppeling naar de installatie-instructies van uw organisatie. Als uw organisatie geen aanvullende instructies verstrekt, wordt u naar dit artikel verzonden.  
    b. Tik op **Start**.  

    ![Voor beeld van een scherm opname van het scherm Bedrijfsportal mobiele smartcard toegang instellen.](./media/smart-card-info-intercede.png)

9. Schakel over naar het apparaat dat geschikt is voor Smart Cards en open IdentityGuard. 
10. Zoek het aanmeldings gebied voor Smart credentials en selecteer de knop aanmelden.  
11. Wanneer u wordt gevraagd om een certificaat te selecteren, kiest u uw referenties voor de Smart Card. Selecteer **OK**. 
12. Voer uw pincode voor de Smart Card in.  
13. U wordt gevraagd om te kiezen uit een lijst met acties. Selecteer het account waarmee u zich kunt inschrijven voor een afgeleide mobiele Smart-referentie. De koppeling of knop kan zeggen dat **Ik wil inschrijven voor een afgeleide mobiele smartcard referentie.**  
14. Selecteer dat u de toepassing met slimme referentie mogelijkheden hebt gedownload en geïnstalleerd. Ga vervolgens naar het volgende scherm.   
15. Voer informatie in over uw afgeleide smartcard referentie.  
    a. Voer voor de identiteits naam een naam in, zoals *afgeleide cred*.  
    b. Selecteer in de vervolg keuzelijst de optie **IdentityGudard Mobile Smart Credential**.  
    c. Ga door naar het volgende scherm. Er wordt een QR-code met een numeriek wacht woord weer geven.  

16. Ga terug naar uw mobiele apparaat. Tik op het scherm Bedrijfsportal > **QR-code ophalen** op **door gaan**. 

    ![Voor beeld scherm afbeelding van het scherm Bedrijfsportal QR-code ophalen.](./media/get-qr-code-intercede.png)  
17. Tik op **camera gebruiken** > **OK**.  

    ![Voor beeld van een scherm opname van een Bedrijfsportal prompt, waarbij toestemming wordt gevraagd om toegang tot de camera toe te staan.](./media/allow-cp-camera-access-intercede.png)  
18. Scan de afbeelding van de QR-code op uw Smart Card-apparaat.  
19. Voer het numerieke wacht woord in dat wordt weer gegeven onder de QR-code.  

    ![Voor beeld scherm opname van het scherm wacht woord Bedrijfsportal vereist, Voer wachtwoord veld in.](./media/enter-password-derived-credentials.png)   

20. Wacht tot Bedrijfsportal uw apparaat hebt ingesteld.  


## <a name="next-steps"></a>Volgende stappen  
Nadat de inschrijving is voltooid, hebt u toegang tot werk resources, zoals e-mail, Wi-Fi en alle apps die uw organisatie beschikbaar maakt. Voor meer informatie over het verkrijgen, zoeken, installeren en verwijderen van apps in de Bedrijfsportal raadpleegt u:

* [Apps beheren via de Bedrijfsportalwebsite](manage-apps-cpweb.md)  
* [Beheerde apps op een apparaat gebruiken](use-managed-apps-on-your-device-ios.md)  

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Controleer of de contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).  
