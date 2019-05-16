---
title: Toegang tot uw bedrijfsbronnen instellen voor uw iOS-apparaat | Microsoft Docs
description: Hier wordt beschreven hoe u uw iOS-apparaat kunt laten beheren door Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: tisilv
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: d0c7ac239a67a51ba7165771206883f3c46f5f55
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59292421"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Toegang tot uw bedrijfsbronnen instellen voor uw iOS-apparaat  

Uw iOS-apparaat registreren met de bedrijfsportal-app van Intune voor beveiligde toegang tot e-mail, bestanden en apps van uw organisatie.

Nadat uw apparaat is geregistreerd, wordt het *beheerd*. Uw organisatie kan beleid en apps aan het apparaat toewijzen via een MDM-provider (Mobile Device Management), zoals Intune.  

Als u toegang wilt houden tot uw werk- of schoolgegevens op het apparaat, moet u de instellingen van uw apparaat aanpassen aan de voorkeursinstellingen van uw organisatie. In dit artikel wordt beschreven hoe u Bedrijfsportal gebruikt om uw apparaat te registreren en de vereiste instellingen van uw organisatie aan te houden. 

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

    ![Voorbeeldschermopname van de bedrijfsportal-app, aanmelden.](./media/ios-01-cp-enroll-1903.PNG)  

2. Wanneer u wordt gevraagd of u Bedrijfsportal-meldingen wilt ontvangen, tikt u op **Toestaan.** De bedrijfsportal-app maakt gebruik van meldingen om u te waarschuwen, bijvoorbeeld als uw apparaatinstellingen moeten worden bijgewerkt. 

    ![Voorbeeldschermopname van de startpagina van Bedrijfsportal, de Meldingen-vraag.](./media/ios-04-cp-enroll-1903.PNG)  

3. Selecteer op het scherm **Toegang instellen** de optie **Beginnen.**  

     ![Voorbeeldschermopname van Bedrijfsportal, het scherm Toegang instellen.](./media/ios-05-cp-enroll-1903.PNG)  

4. Lees welke apparaatgegevens uw organisatie wel en niet kan zien. Tik op **Doorgaan**.  

5. Lees de instructies op het scherm **De volgende stap**. Als u het beheerprofiel wilt downloaden en installeren, tikt u op **Doorgaan**.  

 > [!IMPORTANT]
> De volgende stappen en schermen variëren afhankelijk van uw iOS-versie. Volg de stappen voor uw iOS-versie. 

6. In Safari wordt de bedrijfsportalwebsite geopend op uw apparaat. Wanneer u wordt gevraagd om het configuratieprofiel te downloaden, tikt u op **Toestaan**. Als u werkt op een apparaat met:  
    * iOS 12.2 en later: Wanneer het downloaden is voltooid, tikt u op **Gereed.** Ga verder met stap 7 in dit artikel.
    * iOS 12.1 en eerder: U wordt automatisch omgeleid naar de app Instellingen. Ga verder met stap 8 in dit artikel.  
 
    Als u per ongeluk op **Negeren** tikt, vernieuwt u de pagina. U wordt vervolgens gevraagd om de bedrijfsportal-app te openen. Vanuit de app tikt u op **Opnieuw downloaden**.

  > [!NOTE]
  > U moet het beheerprofiel binnen acht minuten na het downloaden installeren zoals beschreven in de volgende stappen. Als u dit niet doet, wordt het profiel verwijderd en moet u de inschrijving opnieuw starten.  

7. Uitsluitend iOS 12.2 en later: wanneer u wordt gevraagd om Bedrijfsportal te openen, tikt u op **Openen**. Op het scherm **Beheerprofiel installeren** worden de stappen voor het installeren van het profiel weergegeven.

    ![Voorbeeldschermopname van Bedrijfsportal, het scherm Beheerprofiel installeren.](./media/ios-1904-settings-icon.PNG)  

8. Ga naar de app Instellingen en tik op **Profiel gedownload**.  

    Als **Profiel gedownload** niet als optie wordt weergegeven, gaat u naar **Algemeen** > **Profielen**. Als u het profiel nog niet ziet, moet u het mogelijk opnieuw downloaden.  

    ![Voorbeeldschermopname van de app Instellingen, de instelling Profiel gedownload.](./media/ios-1904-settings-badge.PNG)  

9. Tik op **INSTALLEREN**.  
    
10. Voor uw apparaatwachtwoord in. Tik vervolgens op **Installeren**.    

    ![Voorbeeldschermopname van de app Instellingen, het scherm Profiel installeren met de cursor op de knop ** Installeren **.](./media/ios-1904-password-install.PNG)  


11. Het volgende scherm bevat een standaardsysteemwaarschuwing voor apparaatbeheer. Als u wilt doorgaan met de installatie, tikt u op **Installeren**. Als u wordt gevraagd om extern beheer te vertrouwen, tikt u op **Vertrouwen**.  

    ![Voorbeeldschermopname van de app Instellingen, het scherm met de standaardsysteemwaarschuwing voor basiscertificaat en Mobile Device Management.](./media/ios-15-cp-enroll-1903.PNG)  

12. Wanneer de installatie is voltooid, klikt u op **Gereed**. U kunt controleren of het profiel is geïnstalleerd door naar de instellingen **Profielen en apparaatbeheer** te gaan. Het profiel moet worden weergegeven onder **Mobile Device Management**.   

    ![Voorbeeldschermopname van de app Instellingen, de instellingen Profielen en Apparaatbeheer met het beheerprofiel.](./media/ios-00-cp-enroll-1903.PNG)  

13. Ga terug naar de bedrijfsportal-app. In de bedrijfsportal-app gaat de synchronisatie en setup van uw apparaat van start. In Bedrijfsportal kunt u mogelijk worden gevraagd aanvullende apparaatinstellingen bij te werken. Als dit het geval is, tikt u op **Doorgaan**.  

    ![Voorbeeldschermopname van de bedrijfsportal-app, het scherm Toegang instellen met een gele driehoek naast de instellingsvereiste.](./media/ios-12-cp-enroll-1903.PNG)  

14. U weet dat de installatie is voltooid wanneer alle items in de lijst met een groene cirkel worden weergegeven. Tik op **Gereed**.   
    
    ![Voorbeeldschermopname van Bedrijfsportal, het scherm U bent klaar, met allemaal groene cirkels.](./media/ios-13-cp-enroll-1903.PNG)  

> [!Note]
> Als uw organisatie bel- en datalimieten hanteert, of u een apparaat geeft dat bedrijfseigendom is, moet u mogelijk nog enkele andere stappen uitvoeren. Zie [Uw app registreren bij Telecom Expense Management](enroll-your-device-with-telecom-expense-management-ios.md) als u wordt gevraagd om de app **Datalert** te installeren. Ontdek [hoe u uw bedrijfsapparaat registreert](enroll-your-device-dep-ios.md) als uw organisatie meedoet aan het Device Enrollment Program van Apple.  

## <a name="next-steps"></a>Volgende stappen  
Zoek nuttige apps voor op uw werk of op school. Informatie over [hoe apps beschikbaar worden gesteld](use-managed-apps-on-your-device-ios.md) aan u via Bedrijfsportal.  

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. U vindt de contactgegevens van uw beheerder op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).  
