---
title: Bedrijfsapparaat inschrijven met de Microsoft Intune-app| Microsoft Docs
description: Hierin wordt beschreven hoe u een zakelijk Android-apparaat bij Intune kunt inschrijven
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/07/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: ef7ec650c65206eeab69d8f666dc4fb39052bbdb
ms.sourcegitcommit: 549352bdea93cc2809e3e0010bfcc10bd44dc728
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 08/09/2019
ms.locfileid: "68862243"
---
# <a name="enroll-your-corporate-device-with-the-microsoft-intune-app"></a>Uw bedrijfsapparaat inschrijven met de Microsoft Intune-app

Schrijf uw zakelijke Android-apparaat in voor veilige toegang tot uw zakelijke e-mail, apps en andere gegevens die uw bedrijf beschikbaar stelt. De Microsoft Intune-app biedt ondersteuning voor apparaten in bedrijfseigendom met Android 6.0 en hoger. De app wordt automatisch geïnstalleerd op nieuwe apparaten en op apparaten waarop de fabrieksinstellingen zijn hersteld tijdens de inschrijving. 

U kunt uw apparaat op vier verschillende manieren inschrijven. Uw bedrijf informeert u over de juiste manier.
 
* Near Field Communication (NFC)  
* Token  
* QR-code   
* Google Zero Touch  

## <a name="enroll-device"></a>Een apparaat inschrijven 
Voltooi deze stappen voor het instellen en inschrijven van uw apparaat.  

> [!NOTE]
> Het is mogelijk dat u vanwege uw Android-versie of de fabrikant van het apparaat extra stappen moet uitvoeren die hier niet worden beschreven. De kleuren en de tekst in de schermopnamen zien er mogelijk anders uit dan op uw apparaat.  

1. Schakel uw nieuwe apparaat of het apparaat waarop de fabrieksinstellingen zijn hersteld in.  
2. Selecteer uw taal in het scherm **Welkom**.   Als u het apparaat moet inschrijven met een QR-code of via NFC, volgt u de bijbehorende stappen.  
     * NFC: Houd het apparaat dat NFC ondersteunt tegen een programmeerapparaat om verbinding te maken met het bedrijfsnetwerk. Volg de instructies op het scherm. Wanneer het scherm met de servicevoorwaarden van Chrome wordt weergegeven, kunt u verder met stap 5.  

     * QR-code: Volg de stappen in [Inschrijven met behulp van QR-code](#qr-code-enrollment).  

     Als u een andere methode moet volgen, gaat u verder naar stap 3.    

3. Maak verbinding met Wi-Fi en tik op **VOLGENDE**. Volg de stap die overeenkomt met uw inschrijvingsmethode. 

    * Token: Wanneer het aanmeldscherm van Google wordt weergegeven, voert u de stappen uit die worden beschreven in [Tokeninschrijving](#token-enrollment).  
    * Google Zero Touch: Nadat u verbinding met Wi-Fi hebt gemaakt, wordt uw apparaat herkend door uw bedrijf. Ga verder met stap 4 en volg de instructies op het scherm totdat de installatie is voltooid.    
 
       ![Voorbeeldafbeelding van het scherm met de voorwaarden van Google dat verschijnt als u Google Zero Touch gebruikt, waarin de knop Accept & Continue is gemarkeerd.](./media/google-zero-touch-intune-app-01.png)   
   
4. Lees de voorwaarden van Google. Tik vervolgens op **ACCEPT & CONTINUE**.  

      ![Voorbeeldafbeelding van het scherm met de voorwaarden van Google, waarin de knop Accept & Continue is gemarkeerd.](./media/fully-managed-intune-app-04.png)   

6. Lees de servicevoorwaarden van Chrome. Tik vervolgens op **ACCEPT & CONTINUE**.  

   ![Voorbeeldafbeelding van het scherm met de servicevoorwaarden van Chrome, waarin de knop Accept & Continue is gemarkeerd.](./media/fully-managed-intune-app-06.png)   

7. Meld u in de aanmeldschermen aan met een werk- of schoolaccount.   

    a. Voer uw e-mailadres in en tik op **Volgende**.      
    b. Voer uw wachtwoord in en tik op **Aanmelden**.  

8. Afhankelijk van de vereisten van uw bedrijf, moet u mogelijk instellingen bijwerken, zoals schermvergrendeling of versleuteling. Als u hierom wordt gevraagd, tikt u op **INSTELLEN** en volgt u de instructies op het scherm.  

   ![Voorbeeldafbeelding van het instellen van uw zakelijke telefoon, waarin de knop Instellen is gemarkeerd.](./media/fully-managed-intune-app-10.png)   

9. Tik op **INSTALLEREN** om de bedrijfsapps op uw apparaat te installeren. Wanneer de installatie is voltooid, tikt u op **VOLGENDE**.  

   ![Voorbeeldafbeelding van het instellen van uw zakelijke telefoon, waarin de knop Installeren is gemarkeerd.](./media/fully-managed-intune-app-11.png)   

10. Tik **op** start om de Microsoft intune-app te openen en uw apparaat te registreren. 

    ![Voorbeeldafbeelding van het instellen van uw zakelijke telefoon, waarin de knop Starten is gemarkeerd.](./media/fully-managed-intune-app-17.png)   

11. Tik op **aanmelden** en tik vervolgens op **volgende** om te beginnen met de registratie. Wanneer u het bericht ziet dat de registratie is voltooid, **tikt**u op gereed.  

    ![Voorbeeld afbeelding van het instellen van de toegang, het scherm van het apparaat registreren, de knop gereed markeren.](./media/fully-managed-intune-app-19.png)   

10. Wanneer u het bericht ziet dat uw apparaat gereed is, tikt u op **GEREED**.  

    ![Voorbeeldafbeelding van het instellen van uw zakelijke telefoon, waarin de knop Gereed is gemarkeerd.](./media/fully-managed-intune-app-18.png)   

Als u problemen hebt met het verkrijgen van toegang tot de resources van uw organisatie, moet u mogelijk aanvullende instellingen op uw apparaat bijwerken. Meld u aan bij de app van Microsoft Intune om te controleren op vereiste updates.   


## <a name="qr-code-enrollment"></a>Inschrijven met behulp van QR-code  
In deze sectie gaat u de QR-code scannen die u van uw bedrijf hebt ontvangen.  Wanneer u klaar bent, wordt u teruggeleid naar de stappen voor de registratie van het apparaat.     
  
1. Tik in het scherm **Welkom** vijf maal op het scherm om de installatie van de QR-code te starten.  

   ![Voorbeeldafbeelding van het scherm Welkom waarin de instructies voor tikken op het scherm zijn gemarkeerd.](./media/qr-code-intune-app-01.png)  

2. Volg de instructies op het scherm om verbinding te maken met Wi-Fi.  
3. Als uw apparaat geen QC-codescanner heeft, wordt in de installatieschermen de voortgang weergegeven als er een scanner is geïnstalleerd. Wacht tot de installatie is voltooid.  
4. Wanneer u hierom wordt gevraagd, scant u de QR-code van het inschrijvingsprofiel die u van uw bedrijf hebt ontvangen.  
5. Ga terug naar [Apparaat inschrijven](#enroll-device), stap 4, om door te gaan met de installatie.  

## <a name="token-enrollment"></a>Tokeninschrijving  
In deze sectie gaat u het token invoeren dat u van uw bedrijf hebt ontvangen. Wanneer u klaar bent, wordt u teruggeleid naar de stappen voor de registratie van het apparaat.  

1. Typ in het aanmeldscherm van Google **afw #setup** in het vak **E-mailadres of telefoonnummer**. Tik op **Volgende**. 

   ![Voorbeeldafbeelding van het aanmeldscherm van Google waarin afw#setup in het veld is getypt.](./media/token-intune-app-01.png)   

2. Kies **Installeren** voor de app **Beleid voor Android-apparaat**. Ga verder met de installatie. Afhankelijk van uw apparaat moet u mogelijk aanvullende voorwaarden lezen en accepteren.    

3. Selecteer **Volgende** in het scherm **Dit apparaat inschrijven**.  

4. Selecteer **Code invoeren**.  

5. Typ in het scherm **Code scannen of invoeren** de code die u van uw bedrijf hebt ontvangen.  Klik op **Volgende**.  

   ![Voorbeeldafbeelding van het scherm Code scannen of invoeren, waarin de knop Volgende is gemarkeerd.](./media/token-intune-app-04.png)  

6. Ga terug naar [Apparaat inschrijven](#enroll-device), stap 4, om door te gaan met de installatie.  



## <a name="next-steps"></a>Volgende stappen   
Nog hulp nodig? Neem contact op met het ondersteuningsteam van het bedrijf (zie de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980) voor contactgegevens) of stuur een e-mail naar het <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android-team</a>.  
