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

Nadat het apparaat is geregistreerd, wordt deze *beheerd*. Uw organisatie kan beleid en apps toewijzen aan het apparaat via een provider van een mobile device management (MDM), zoals Intune.  

Voor continue toegang tot werk- of schoolgegevens op uw apparaat moet u uw apparaat zo configureren dat deze overeenkomt met de voorkeursinstellingen van uw organisatie. In dit artikel wordt beschreven hoe u bedrijfsportal gebruiken om u te registreren u apparaten en vereisten van de instelling van uw organisatie beheren. 

> [!NOTE]
> Als u hebt geprobeerd toegang te krijgen tot zakelijke e-mail in de Mail-app en een prompt ontving om uw apparaat te laten beheren, bent u op de juiste plek. Volg de onderstaande instructies om op uw iOS-apparaat toegang te krijgen tot uw e-mail en andere bedrijfsbronnen.  

## <a name="what-to-expect-from-the-company-portal-app"></a>Wat u kunt verwachten van de bedrijfsportal-app  

### <a name="security"></a>Beveiliging  
Tijdens de eerste configuratie verplicht de app u om uzelf te verifiëren bij uw organisatie. Vervolgens krijgt u instructies over de bij te werken apparaatinstellingen. Organisaties stellen bijvoorbeeld vaak wachtwoordvereisten van een minimum- of maximumaantal tekens waaraan u moet voldoen.     

### <a name="protection"></a>Protection  
Nadat het apparaat is geregistreerd, zorgt de bedrijfsportal-app ervoor dat uw apparaat beveiligd blijft. Als u bijvoorbeeld een app installeert vanaf een niet-vertrouwde bron, geeft de app een waarschuwing en wordt soms de toegang tot bedrijfsgegevens ontzegd. Dit soort beleid is gebruikelijk in organisaties en vaak, moet u de niet-vertrouwde app verwijderen voordat u weer toegang kan krijgen.  

### <a name="setting-notifications"></a>Meldingen instellen  
Als uw organisatie na de registratie een nieuwe beveiligingsvereiste oplegt, zoals meervoudige verificatie, wordt u via de bedrijfsportal-app op de hoogte gebracht. U hebt de mogelijkheid om uw instellingen aan te passen, zodat u op uw apparaat kunt blijven werken.  

Zie [Wat gebeurt er wanneer ik de bedrijfsportal-app installeer en mijn apparaat inschrijf?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios) voor meer informatie over inschrijving.  

## <a name="enroll-your-ios-device"></a>Uw iOS-apparaten inschrijven  

Ga naar de appstore downloaden en installeren de [Intune-bedrijfsportal-app](install-and-sign-in-to-the-intune-company-portal-app-ios.md) op uw apparaat. U moet ook voor het onderhouden van een Wi-Fi-verbinding en hebben toegang tot Safari tijdens de inschrijving. 

Meer dan een paar minuten tijdens de inschrijving wordt onderbroken, is het mogelijk dat de app te sluiten of beëindigen van setup. Als dit het geval is, open de bedrijfsportal-app en probeer het opnieuw.  

1. Open Bedrijfsportal en meld u aan met uw werk- of schoolaccount. 

    ![Schermopname van de bedrijfsportal-app aanmelden.](./media/ios-01-cp-enroll-1903.PNG)  

2. Wanneer u hierom wordt gevraagd voor het ontvangen van meldingen van de bedrijfsportal-App, tikt u op **toestaan.** Bedrijfsportal-App maakt gebruik van meldingen om u te waarschuwen als bijvoorbeeld uw instellingen voor apparaten moeten worden bijgewerkt. 

    ![Schermopname van de bedrijfsportal-App-startpagina, 'Meldingen' prompt van.](./media/ios-04-cp-enroll-1903.PNG)  

3. Op de **toegang instellen** scherm, selecteer **beginnen.**  

     ![Schermopname van de bedrijfsportal gaan, scherm 'Toegang instellen'.](./media/ios-05-cp-enroll-1903.PNG)  

4. Lees de lijst met informatie over apparaten van uw organisatie wel en niet zien. Tik op **doorgaan**.  

5. Lees de instructies op de **wat volgt?** scherm. Wanneer u bent klaar om te downloaden en installeren van het beheerprofiel, tikt u op **doorgaan**.  

 > [!IMPORTANT]
> Deze volgende stappen en schermen wordt variëren, afhankelijk van uw iOS-versie. Volg de stappen voor uw iOS-versie. 

6. Safari wordt geopend de bedrijfsportal-website op uw apparaat. Wanneer u hierom wordt gevraagd om te downloaden van het configuratieprofiel, tikt u op **toestaan**. Als u op een apparaat met:  
    * iOS 12.2 en hoger: wanneer het downloaden voltooid is, tikt u op **gedaan.** Ga verder met stap 7 in dit artikel.
    * iOS 12.1 en eerder: U automatisch omgeleid naar de app instellingen. Ga naar stap 8 in dit artikel.  
 
    Als u per ongeluk op **negeren**, vernieuw de pagina. U wordt gevraagd om de bedrijfsportal-app te openen. Vanuit de app, tikt u op **opnieuw downloaden**.

  > [!NOTE]
  > U moet het beheerprofiel zoals beschreven in de volgende stappen binnen 8 minuten van het downloaden van het installeren. Als u dit niet doet, wordt het profiel wordt verwijderd en hebt u de inschrijving opnieuw starten.  

7. iOS 12.2 en nieuwere versies: wanneer u hierom wordt gevraagd om bedrijfsportal te openen, tikt u op **Open**. De **beheerprofiel installeren** scherm worden de stappen voor het installeren van het profiel.

    ![Schermopname van de bedrijfsportal gaan, beheerprofiel installeren scherm.](./media/ios-1904-settings-icon.PNG)  

8. Ga naar de instellingen-app en tik op **profiel gedownload**.  

    Als **profiel gedownload** niet weergegeven als een optie, gaat u naar **algemene** > **profielen**. Als u het profiel niet ziet, moet u mogelijk opnieuw downloaden.  

    ![Schermopname van de app instellingen, gedownload profiel instellen.](./media/ios-1904-settings-badge.PNG)  

9. Tik op **INSTALLEREN**.  
    
10. Het apparaatwachtwoord wijzigen Tik op **installeren**.    

    ![Schermopname van de instellingen-app, het scherm profiel installeren met een cursor op de ** installeren ** knop.](./media/ios-1904-password-install.PNG)  


11. Het volgende scherm is een waarschuwing standaard-systeem voor Apparaatbeheer. Als u wilt doorgaan met installatie, tikt u op **installeren**. Als u hierom wordt gevraagd naar extern beheer vertrouwen, tikt u op **vertrouwensrelatie**.  

    ![Schermopname van de app instellingen, standaard-systeem waarschuwing scherm voor het basiscertificaat en beheer van mobiele apparaten.](./media/ios-15-cp-enroll-1903.PNG)  

12. Nadat de installatie is voltooid, tikt u op **gedaan**. Om te controleren dat het profiel is geïnstalleerd, gaat u naar de **profiel- en Apparaatbeheer** instellingen. U ziet nu het profiel dat wordt vermeld onder **Mobile Device Management**.   

    ![Schermopname van de app instellingen, profiel- en Apparaatbeheer-instellingen, het beheerprofiel weergegeven.](./media/ios-00-cp-enroll-1903.PNG)  

13. Ga terug naar de app Bedrijfsportal. Bedrijfsportal-App begint te synchroniseren en instellen van uw apparaat. Bedrijfsportal vraagt u mogelijk aanvullende apparaatinstellingen bijwerken. Als dit het geval is, tikt u op **doorgaan**.  

    ![Schermopname van de bedrijfsportal-App, 'Toegang instellen' scherm, met een gele driehoek naast de vereiste instellen.](./media/ios-12-cp-enroll-1903.PNG)  

14. Weet u dat de installatie is voltooid wanneer alle items in de lijst met een groene cirkel weergegeven. Tik op **Gereed**.   
    
    ![Schermopname van de bedrijfsportal-App, 'u bent nu klaar!" scherm, met alle groene cirkels.](./media/ios-13-cp-enroll-1903.PNG)  

> [!Note]
> Als uw organisatie bewaakt de spraak- en limieten, of u met een apparaat Bedrijfseigendom kunt, wellicht u enkele extra stappen uitvoeren. Als u wordt gevraagd voor het installeren van de **Datalert** app, Zie [registreren van uw apparaat bij telecom expense management](enroll-your-device-with-telecom-expense-management-ios.md). Als uw organisatie deel uit van het Apple Device Enrollment Program maakt, ontdek [over het registreren van uw apparaat Bedrijfseigendom](enroll-your-device-dep-ios.md).  

## <a name="next-steps"></a>Volgende stappen  
Zoeken naar apps waarmee u op het werk of school. Informatie over [hoe apps beschikbaar zijn gesteld](use-managed-apps-on-your-device-ios.md) via de bedrijfsportal-App.  

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. U vindt de contactgegevens van uw beheerder op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).  
