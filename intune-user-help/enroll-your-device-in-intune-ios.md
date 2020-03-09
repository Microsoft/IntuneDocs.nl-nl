---
title: Toegang tot uw bedrijfsbronnen instellen voor uw iOS-apparaat | Microsoft Docs
description: Hier wordt beschreven hoe u uw iOS-apparaat kunt laten beheren door Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/18/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: tisilv
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: 92d1ca850d8bb542f0b7fe027ab7af8c12089ef8
ms.sourcegitcommit: 9ee2401a2f01373a962749b0728c22385dbcba6d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/29/2020
ms.locfileid: "78181752"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Toegang tot uw bedrijfsbronnen instellen voor uw iOS-apparaat  

Uw iOS-apparaat registreren met de bedrijfsportal-app van Intune voor beveiligde toegang tot e-mail, bestanden en apps van uw organisatie.

Nadat uw apparaat is geregistreerd, wordt het *beheerd*. Uw organisatie kan beleid en apps aan het apparaat toewijzen via een MDM-provider (Mobile Device Management), zoals Intune.  

> [!NOTE]
> We verkopen gegevens die door onze service worden verzameld om geen enkele reden aan externe partijen.  

Als u toegang wilt houden tot uw werk- of schoolgegevens op het apparaat, moet u de instellingen van uw apparaat aanpassen aan de voorkeursinstellingen van uw organisatie. In dit artikel wordt beschreven hoe u Bedrijfsportal gebruikt om uw apparaat te registreren en de vereiste instellingen van uw organisatie aan te houden.  
</br>
> [!VIDEO https://www.youtube.com/embed/mJyv6YcHi7c?rel=0]

> [!NOTE]
> Als u hebt geprobeerd toegang te krijgen tot zakelijke e-mail in de Mail-app en een prompt ontving om uw apparaat te laten beheren, bent u op de juiste plek. Volg de onderstaande instructies om op uw iOS-apparaat toegang te krijgen tot uw e-mail en andere bedrijfsbronnen.  


## <a name="what-to-expect-from-the-company-portal-app"></a>Wat u kunt verwachten van de bedrijfsportal-app  

### <a name="security"></a>Beveiliging  
Tijdens de eerste configuratie verplicht de app u om uzelf te verifiëren bij uw organisatie. Vervolgens krijgt u instructies over de bij te werken apparaatinstellingen. Organisaties stellen bijvoorbeeld vaak wachtwoordvereisten van een minimum- of maximumaantal tekens waaraan u moet voldoen.

### <a name="protection"></a>Protection  
Nadat het apparaat is geregistreerd, zorgt de bedrijfsportal-app ervoor dat uw apparaat beveiligd blijft. Als u bijvoorbeeld een app installeert vanaf een niet-vertrouwde bron, geeft de app een waarschuwing en wordt soms de toegang tot bedrijfsgegevens ontzegd. Dit type beleid is gebruikelijk binnen organisaties en verplicht u vaak om niet-vertrouwde apps te verwijderen voordat u weer toegang kunt krijgen.  

### <a name="setting-notifications"></a>Meldingen instellen  
Als uw organisatie na de registratie een nieuwe beveiligingsvereiste oplegt, zoals meervoudige verificatie, wordt u via de bedrijfsportal-app op de hoogte gebracht. U hebt de mogelijkheid om uw instellingen aan te passen, zodat u op uw apparaat kunt blijven werken.  

Zie [Wat gebeurt er wanneer ik de bedrijfsportal-app installeer en mijn apparaat inschrijf?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios) voor meer informatie over inschrijving.  

## <a name="enroll-your-ios-device"></a>Uw iOS-apparaten inschrijven  

Ga naar de App Store om de [Intune-bedrijfsportal-app](install-and-sign-in-to-the-intune-company-portal-app-ios.md) te downloaden en op uw apparaat te installeren. U hebt ook een continue wifiverbinding en toegang tot Safari nodig tijdens de inschrijving. 

Als u uw inschrijving langer dan een paar minuten onderbreekt, kan de app worden gesloten of de installatie worden beëindigd. Als dit het geval is, opent u de bedrijfsportal-app en probeert u het opnieuw.  

1. Open Bedrijfsportal en meld u aan met uw werk- of schoolaccount.  

2. Wanneer u wordt gevraagd of u Bedrijfsportal-meldingen wilt ontvangen, tikt u op **Toestaan.** De bedrijfsportal-app maakt gebruik van meldingen om u te waarschuwen, bijvoorbeeld als uw apparaatinstellingen moeten worden bijgewerkt.  

3. Selecteer op het scherm **Toegang instellen** de optie **Beginnen.**   

    ![Voorbeeldschermopname van Bedrijfsportal, het scherm Toegang instellen.](./media/ios-enrollment-checklist-1909.PNG)  

4. Het scherm **Apparaat- en inschrijvingstype selecteren** wordt weergegeven en u wordt gevraagd om het apparaattype.  
    * Tik op **(Organisatie) is eigenaar van dit apparaat** als u uw apparaat hebt ontvangen van uw organisatie. Ga vervolgens naar [Volledige apparaat beveiligen](#secure-entire-device) in dit artikel om de installatie te voltooien.  
    * Tik op **Ik ben eigenaar van dit apparaat** als u een privé-apparaat gebruikt dat u van huis hebt meegenomen. Ga dan door naar de volgende stap.  

    Als dit scherm niet wordt weergegeven, gaat u naar [Volledig apparaat beveiligen](#secure-entire-device) om de installatie te voltooien.  
    
    ![Voorbeeld van een schermopname van Bedrijfsportal, het scherm Apparaat- en inschrijvingstype selecteren, opties voor apparaattype.](./media/ios-device-type-1909.PNG)  


5. Kies hoe u de gegevens op uw apparaat wilt beveiligen zodra deze is ingeschreven.  
    * Tik op **Volledig apparaat beveiligen** om alle apps en gegevens op het apparaat te beveiligen. Ga vervolgens naar [Volledig apparaat beveiligen](enroll-your-device-in-intune-ios.md#secure-entire-device) om de installatie te voltooien.
    * Tik op **Alleen werkgerelateerde apps en gegevens beveiligen** om alleen de apps en gegevens te beveiligen die u met uw werkaccount opent. Ga vervolgens naar [Werkgerelateerde apps en gegevens beveiligen](enroll-your-device-in-intune-ios.md#secure-work-related-apps-and-data).  

    ![Voorbeeld van een schermopname van Bedrijfsportal, het scherm Apparaat- en inschrijvingstype selecteren, opties voor inschrijvingstype.](./media/ios-enrollment-type-1909.PNG)  


### <a name="secure-entire-device"></a>Volledig apparaat beveiligen  

1. Lees in het scherm **Apparaatbeheer en privacy** welke apparaatgegevens uw organisatie wel en niet kan zien. Tik op **Doorgaan**.  


 > [!IMPORTANT]
> De volgende stappen en schermen variëren afhankelijk van uw iOS-versie. Volg de stappen voor uw iOS-versie. 

2. In Safari wordt de bedrijfsportalwebsite geopend op uw apparaat. Wanneer u wordt gevraagd om het configuratieprofiel te downloaden, tikt u op **Toestaan**. Als u werkt op een apparaat met:  
    * iOS 12.2 en hoger: Wanneer het downloaden is voltooid, tikt u op **Sluiten**. Ga vervolgens door naar stap 3.  
    * iOS 12.1 en eerder: Wanneer het downloaden is voltooid, wordt u automatisch omgeleid naar de Instellingen-app. Ga verder met stap 4.  
 
    Als u per ongeluk op **Negeren** tikt, vernieuwt u de pagina. U wordt vervolgens gevraagd om de bedrijfsportal-app te openen. Tik op **Nogmaals downloaden** als u daar bent.

  > [!NOTE]
  > U moet het beheerprofiel binnen acht minuten na het downloaden installeren zoals beschreven in de volgende stappen. Als u dit niet doet, wordt het profiel verwijderd en moet u de inschrijving opnieuw starten.  

3. Wanneer u wordt gevraagd om Bedrijfsportal te openen, tikt u op **Openen**. Lees de informatie in het scherm **Het beheerprofiel installeren**.  

4. Ga naar de app Instellingen en tik op **Inschrijven in < organisatienaam >** of **Gedownload profiel**.  

    ![Voorbeeld van een schermopname van de Instellingen-app, optie Inschrijven bij organisatie.](./media/enroll-in-organization-ios-1909.PNG)  

   Als geen van beide opties wordt weergegeven, gaat u naar **Algemeen** > **Profielen en apparaatbeheer**> **Beheerprofiel**. Als u het beheerprofiel nog niet ziet, moet u het mogelijk opnieuw downloaden.  

5. Tik op **INSTALLEREN**.  
    
6. Voor uw apparaatwachtwoord in. Tik vervolgens op **Installeren**.    

7. Het volgende scherm bevat een standaardsysteemwaarschuwing over apparaatbeheer. Als u wilt doorgaan met de installatie, tikt u op **Installeren**. Als u wordt gevraagd om extern beheer te vertrouwen, tikt u op **Vertrouwen**.  

8. Wanneer de installatie is voltooid, klikt u op **Gereed**. U kunt controleren of het profiel is geïnstalleerd door naar de instellingen **Profielen en apparaatbeheer** te gaan. Het profiel moet worden weergegeven onder **Mobile Device Management**.   

    ![Voorbeeldschermopname van de app Instellingen, de instellingen Profielen en Apparaatbeheer met het beheerprofiel.](./media/ios-12-cp-enroll-1904.PNG)  

9. Ga terug naar de bedrijfsportal-app. In de bedrijfsportal-app gaat de synchronisatie en setup van uw apparaat van start. In Bedrijfsportal kunt u mogelijk worden gevraagd aanvullende apparaatinstellingen bij te werken. Als dit het geval is, tikt u op **Doorgaan**.  

10. U weet dat de installatie is voltooid wanneer alle items in de lijst met een groen vinkje worden weergegeven. Tik op **Gereed**.   

> [!Note]
> Als uw organisatie bel- en datalimieten hanteert, of u een apparaat geeft dat bedrijfseigendom is, moet u mogelijk nog enkele andere stappen uitvoeren. Zie [Uw app registreren bij Telecom Expense Management](enroll-your-device-with-telecom-expense-management-ios.md) als u wordt gevraagd om de app **Datalert** te installeren. Ontdek [hoe u uw bedrijfsapparaat registreert](enroll-your-device-dep-ios.md) als uw organisatie meedoet aan het Device Enrollment Program van Apple.  

### <a name="secure-work-related-apps-and-data"></a>Werkgerelateerde apps en gegevens beveiligen  
1. Het scherm **Microsoft Authenticator downloaden** wordt weergegeven (als u al een Authenticator hebt, ziet u dit scherm niet en kunt u door naar stap 2).  
    1. Tik op **Downloaden uit de App Store**.
    2. Wanneer de App Store wordt geopend, installeert u de app. 
    3. Keer terug naar Bedrijfsportal en tik op **Doorgaan**.    
    
   Nadat u Microsoft Authenticator hebt geïnstalleerd, hoeft u verder niets te doen met de app. Deze hoeft alleen maar aanwezig te zijn op uw apparaat. 

   ![Voorbeeld van een schermopname van Bedrijfsportal, scherm Microsoft Authenticator downloaden.](./media/download-ms-authenticator-1909.PNG)  

2. Lees in het scherm **Apparaatbeheer en privacy** welke apparaatgegevens uw organisatie wel en niet kan zien. Tik op **Doorgaan**.  


 > [!IMPORTANT]
> De volgende stappen en schermen variëren afhankelijk van uw iOS-versie. Volg de stappen voor uw iOS-versie. 

3. In Safari wordt de bedrijfsportalwebsite geopend op uw apparaat. Wanneer u wordt gevraagd om het configuratieprofiel te downloaden, tikt u op **Toestaan**. Als u werkt op een apparaat met:  
    * iOS 12.2 en hoger: Wanneer het downloaden is voltooid, tikt u op **Sluiten**. Ga vervolgens door naar stap 4.  
    * iOS 12.1 en eerder: Wanneer het downloaden is voltooid, wordt u automatisch omgeleid naar de Instellingen-app. Ga verder met stap 5.  
 
    Als u per ongeluk op **Negeren** tikt, vernieuwt u de pagina. U wordt vervolgens gevraagd om de bedrijfsportal-app te openen. Vanuit de app tikt u op **Opnieuw downloaden**.

  > [!NOTE]
  > U moet het beheerprofiel binnen acht minuten na het downloaden installeren zoals beschreven in de volgende stappen. Als u dit niet doet, wordt het profiel verwijderd en moet u de inschrijving opnieuw starten.  

4. Wanneer u wordt gevraagd om Bedrijfsportal te openen, tikt u op **Openen**. Lees de informatie in het scherm **Het beheerprofiel installeren**. 

5. Ga naar de app Instellingen en tik op **Inschrijven in < organisatienaam >** of **Gedownload profiel**.  

    ![Voorbeeld van een schermopname van de Instellingen-app, optie Inschrijven bij organisatie.](./media/enroll-in-organization-ios-1909.PNG)  

   Als geen van beide opties wordt weergegeven, gaat u naar **Algemeen** > **Profielen en apparaatbeheer**> **Beheerprofiel**. Als u het beheerprofiel nog niet ziet, moet u het mogelijk opnieuw downloaden.   


6. Tik op het scherm **Gebruikersregistratie** op **Mijn iPhone inschrijven**.  

    ![Voorbeeld van een schermopname van de app Instellingen, scherm Gebruikersregistratie waarbij de registratieknop is gemarkeerd.](./media/user-enrollment-information-1909.PNG)  

7. Voer het apparaatwachtwoord in. Tik vervolgens op **Installeren**.  

8. Voer het wachtwoord voor uw beheerde Apple-id in op het scherm **Aanmelden**. In de meeste gevallen zijn deze referenties dezelfde die u ook gebruikt om u aan te melden bij uw werk- of schoolaccount, tenzij uw organisatie u een andere set referenties heeft gegeven. 
9. Tik op **Aanmelden**.  
10. Er wordt een succesbericht weergegeven op het scherm kort nadat het profiel is geïnstalleerd. U kunt controleren of het profiel is geïnstalleerd door naar de instellingen  **Profielen en apparaatbeheer**  te gaan. Het profiel moet worden weergegeven onder  **Mobile Device Management**.  

    ![Voorbeeldschermopname van de app Instellingen, de instellingen Profielen en Apparaatbeheer met het beheerprofiel.](./media/ios-12-cp-enroll-1904.PNG)  

11. Ga terug naar de bedrijfsportal-app. In de bedrijfsportal-app gaat de synchronisatie en setup van uw apparaat van start. In Bedrijfsportal kunt u mogelijk worden gevraagd aanvullende apparaatinstellingen bij te werken. Als dit het geval is, tikt u op **Doorgaan**.    

12. U weet dat de installatie is voltooid wanneer alle items in de lijst met een groen vinkje worden weergegeven. Tik op  **Gereed**.  

## <a name="it-administrator-support"></a>Ondersteuning IT-beheerder  
Als u een IT-beheerder bent en in de problemen raakt tijdens het inschrijven van apparaten, kunt u [Troubleshooting iOS device enrollment problems in Microsoft Intune (Problemen oplossen met de inschrijving van iOS-apparaten in Microsoft Intune)](https://support.microsoft.com/en-us/help/4039809) raadplegen. Dit artikel bevat algemene fouten, de oorzaken en de stappen om deze op te lossen.  

## <a name="next-steps"></a>Volgende stappen  
Zoek nuttige apps voor op uw werk of op school. Informatie over [hoe apps beschikbaar worden gesteld](use-managed-apps-on-your-device-ios.md) aan u via Bedrijfsportal.  

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. U vindt de contactgegevens van uw beheerder op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).  
