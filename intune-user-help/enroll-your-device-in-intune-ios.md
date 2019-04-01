---
title: Toegang tot uw bedrijfsbronnen instellen voor uw iOS-apparaat | Microsoft Docs
description: Hier wordt beschreven hoe u uw iOS-apparaat kunt laten beheren door Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/26/2019
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
ms.openlocfilehash: ee0f438d929abd6b5b90acbaeeddc41e3ce11f98
ms.sourcegitcommit: 44095bbd1502b02201a01604531f4105401fbb92
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/27/2019
ms.locfileid: "58490639"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Toegang tot uw bedrijfsbronnen instellen voor uw iOS-apparaat  

Uw iOS-apparaat registreren met de bedrijfsportal-app van Intune voor beveiligde toegang tot e-mail, bestanden en apps van uw organisatie.

Voordat u toegang krijgt tot vertrouwelijke gegevens op een zakelijk of persoonlijk apparaat, moet u uw apparaat laten beheren. Wanneer uw apparaat wordt beheerd, kan uw organisatie beleid en apps aan het apparaat toewijzen via een MDM-provider (Mobile Device Management), zoals Intune. 

Voor continue toegang tot werk- of schoolgegevens op uw apparaat moet u uw apparaat zo configureren dat deze overeenkomt met de voorkeursinstellingen van uw organisatie. In dit artikel wordt beschreven hoe u bedrijfsportal gebruiken om u te registreren u apparaten en vereisten van de instelling van uw organisatie beheren. 

> [!NOTE]
> Als u hebt geprobeerd toegang te krijgen tot zakelijke e-mail in de Mail-app en een prompt ontving om uw apparaat te laten beheren, bent u op de juiste plek. Volg de onderstaande instructies om op uw iOS-apparaat toegang te krijgen tot uw e-mail en andere bedrijfsbronnen.  

## <a name="what-to-expect-from-the-company-portal-app"></a>Wat u kunt verwachten van de bedrijfsportal-app  

### <a name="security"></a>Beveiliging  
Tijdens de eerste configuratie verplicht de app u om uzelf te verifiëren bij uw organisatie. Vervolgens krijgt u instructies over de bij te werken apparaatinstellingen. Organisaties stellen bijvoorbeeld vaak wachtwoordvereisten van een minimum- of maximumaantal tekens waaraan u moet voldoen.     

### <a name="protection"></a>Protection  
Nadat het apparaat is geregistreerd, zorgt de bedrijfsportal-app ervoor dat uw apparaat beveiligd blijft. Als u bijvoorbeeld een app installeert vanaf een niet-vertrouwde bron, geeft de app een waarschuwing en wordt soms de toegang tot bedrijfsgegevens ontzegd. Een beleid zoals dit wordt vaak gebruikt in organisaties en vaak, moet u de niet-vertrouwde app verwijderen voordat u weer toegang kan krijgen.  

### <a name="setting-notifications"></a>Meldingen instellen  
Als uw organisatie na de registratie een nieuwe beveiligingsvereiste oplegt, zoals meervoudige verificatie, wordt u via de bedrijfsportal-app op de hoogte gebracht. U hebt de mogelijkheid om uw instellingen aan te passen, zodat u op uw apparaat kunt blijven werken.  

Zie [Wat gebeurt er wanneer ik de bedrijfsportal-app installeer en mijn apparaat inschrijf?](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios) voor meer informatie over inschrijving.  

## <a name="enroll-your-ios-device"></a>Uw iOS-apparaten inschrijven   

> [!IMPORTANT]
> De schermafbeeldingen in deze sectie laten zien dat de ervaring voor apparaten met iOS-versie 12.1 en eerdere versies. Indien van toepassing, hebben we opgenomen instructies die specifiek zijn voor iOS-versie 12.2 en hoger. Als u merkt dat uw ervaring af van de schermafbeeldingen wordt weergegeven wijkt, raadpleegt u de 12.2 instructies.      

Ga naar de appstore downloaden en installeren de [Intune-bedrijfsportal-app](install-and-sign-in-to-the-intune-company-portal-app-ios.md) op uw apparaat. Tijdens de inschrijving, hebt u ook een Wi-Fi-verbinding en de toegang tot Safari nodig. 

Als u meer dan een paar minuten tijdens de inschrijving onderbroken, kan de app sluit of beëindigen van setup. Als dit het geval is, open de bedrijfsportal-app en probeer het opnieuw.  

1. Open Bedrijfsportal en meld u aan met uw werk- of schoolaccount. 

    ![Schermopname van de bedrijfsportal-app aanmelden.](./media/ios-01-cp-enroll-1903.PNG)  

2. Wanneer u hierom wordt gevraagd voor het ontvangen van meldingen van de bedrijfsportal-App, tikt u op **toestaan.** Bedrijfsportal-App maakt gebruik van meldingen om u te waarschuwen als bijvoorbeeld uw instellingen voor apparaten moeten worden bijgewerkt. 

    ![Schermopname van de bedrijfsportal-App-startpagina, 'Meldingen' prompt van.](./media/ios-04-cp-enroll-1903.PNG)  

3. Op de **toegang instellen** scherm, selecteer **beginnen.**  

     ![Schermopname van de bedrijfsportal gaan, scherm 'Toegang instellen'.](./media/ios-05-cp-enroll-1903.PNG)  

4. Lees de lijst met informatie over apparaten van uw organisatie wel en niet zien. [Meer informatie over dit onderwerp](what-info-can-your-company-see-when-you-enroll-your-device-in-Intune.md) vindt u de **meer** koppeling. Wanneer u klaar bent, tikt u op **doorgaan**.  

    ![Schermopname van de bedrijfsportal-app, 'Wat kan mijn bedrijf zien', met de knop Doorgaan.](./media/ios-06-cp-enroll-1903.PNG)  
 
5. De **wat volgt?** scherm bevat een overzicht van de resterende stappen. Deze stappen kunnen afwijken, afhankelijk van uw iOS-versie. 
    * **iOS 12.2 en hoger**: uw ervaring in plaats daarvan moet u mogelijk:  

        a. **Toestaan van downloaden van het beheerprofiel**: uw browser wordt open de bedrijfsportal-website en vraagt u om te downloaden. De download wordt opgeslagen in uw app instellingen.  

        b. **Open de app instellingen en installatie van het profiel**: U moet gaat u naar de instellingen-app en het beheerprofiel installeren.  

        c. **Ga terug naar de bedrijfsportal-app**: U moet om terug te keren naar de bedrijfsportal-app en de installatie voltooien.  

    Wanneer u klaar bent om het beheerprofiel te downloaden, tikt u op **doorgaan**.  

6. Safari wordt geopend de bedrijfsportal-website. Wanneer u hierom wordt gevraagd om te downloaden van het configuratieprofiel, tikt u op **toestaan**.  
    * **iOS 12.2 en hoger**: wachten op het profiel dat u wilt downloaden in Safari en tikt u op Voltooien **gedaan**. Open vervolgens de app **Instellingen** op uw apparaat.  

    > [!IMPORTANT]
    > Gaat u naar de **instellingen** app en installeert u dit profiel binnen 8 minuten na het downloaden. Als u dit niet doet, wordt het profiel wordt verwijderd en hebt u de inschrijving opnieuw starten. 

7. In de **instellingen** app, tik **gedownload profiel installeren** > **installeren**. Als **gedownload profiel installeren** niet weergegeven als een optie, gaat u naar **algemene** > **profielen**. Als u het profiel niet ziet, moet u mogelijk opnieuw downloaden.  

    ![Schermopname van de instellingen-app-instelling gedownload profiel installeren, met een rode badge die aangeeft van een onlangs gedownloade profiel.](./media/ios-10-cp-enroll-1903.PNG)  
    
8. Als u wordt gevraagd, voert u het wachtwoord van uw apparaat. Tik op **installeren**.      

9. Het volgende scherm is een waarschuwing standaard-systeem voor Apparaatbeheer. Zie voor meer informatie over wat uw organisatie wel en niet kan zien op uw apparaat, de relevante [Intune docs-artikel](what-info-can-your-company-see-when-you-enroll-your-device-in-Intune.md). Als u wilt doorgaan met installatie, tikt u op **installeren**. Als u wordt gevraagd of u extern beheer vertrouwen, tikt u op **vertrouwensrelatie**.  

    ![Schermopname van de app instellingen, standaard-systeem waarschuwing scherm voor het basiscertificaat en beheer van mobiele apparaten.](./media/ios-15-cp-enroll-1903.PNG)  

10. Nadat de installatie is voltooid, tikt u op **gedaan**. Om te controleren dat het profiel is geïnstalleerd, gaat u naar de **profiel- en Apparaatbeheer** instellingen. U ziet nu het profiel dat wordt vermeld onder **Mobile Device Management**.   

    ![Schermopname van de app instellingen, profiel- en Apparaatbeheer-instellingen, het beheerprofiel weergegeven.](./media/ios-00-cp-enroll-1903.PNG)  


11. Ga terug naar de app **Bedrijfsportal**. Bedrijfsportal-App begint te synchroniseren en instellen van uw apparaat. Bedrijfsportal vraagt u mogelijk aanvullende apparaatinstellingen bijwerken. Als dit het geval is, tikt u op **doorgaan**.

    ![Schermopname van de bedrijfsportal-App, 'Toegang instellen' scherm, met een gele driehoek naast de vereiste instellen.](./media/ios-12-cp-enroll-1903.PNG)  

12. Weet u dat de installatie is voltooid wanneer alle items in de lijst met een groene cirkel weergegeven. Tik op **Gereed**.  
    
    ![Schermopname van de bedrijfsportal-App, 'u bent nu klaar!" scherm, met alle groene cirkels.](./media/ios-13-cp-enroll-1903.PNG)  

> [!Note]
> Als uw organisatie bewaakt de spraak- en limieten, of u met een apparaat Bedrijfseigendom kunt, wellicht u enkele extra stappen uitvoeren. Als u wordt gevraagd voor het installeren van de **Datalert** app, Zie [registreren van uw apparaat bij telecom expense management](enroll-your-device-with-telecom-expense-management-ios.md). Als uw organisatie deel uit van het Apple Device Enrollment Program maakt, ontdek [over het registreren van uw apparaat Bedrijfseigendom](enroll-your-device-dep-ios.md).  

## <a name="next-steps"></a>Volgende stappen  
Zoeken naar apps waarmee u op het werk of school. Informatie over [hoe apps beschikbaar zijn gesteld](use-managed-apps-on-your-device-ios.md) via de bedrijfsportal-App.  

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. U vindt de contactgegevens van uw beheerder op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).  
