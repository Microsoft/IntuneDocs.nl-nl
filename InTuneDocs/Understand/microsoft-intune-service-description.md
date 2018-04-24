---
title: Beschrijving van de service | Microsoft Intune
description: Intune is een cloudservice waarmee u Windows-pc&quot;s en mobiele iOS-, Mac OS X-, Android- en Windows-apparaten kunt beheren.
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 09/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 40fa5a2e-6c0f-4150-9740-d5ddc0cdbda0
ms.reviewer: cacamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ab9ad1fb42176f2fc2babaa6fa3c91cea40b4ca5
ms.openlocfilehash: 423282fd8dd80358311373862f808cdaa58212bd

<<<<<<< HEAD

---

# Beschrijving van de Microsoft Intune-service

Microsoft Intune is een cloudservice waarmee u Windows-pc's en mobiele iOS-, Mac OS X-, Android- en Windows-apparaten kunt beheren. Met Intune kunt u ook bedrijfsapplicaties en -gegevens beveiligen. U kunt Intune zelfstandig gebruiken of u kunt het integreren met System Center Configuration Manager en zo de beheermogelijkheden uitbreiden. 

Microsoft biedt het Intune Onboarding-voordeel voor services in abonnementen die daarvoor in aanmerking komen. Met het voorbereidingsvoordeel krijgt u externe ondersteuning van Microsoft-specialisten bij het klaarstomen van uw Intune-omgeving. Zie [Beschrijving voorbereidingsvoordeel Microsoft Intune](http://go.microsoft.com/fwlink/?LinkId=619281)voor meer informatie.

U kunt 30 dagen lang een gratis proefversie van Intune met 100 gebruikerslicenties gebruiken. [Klik hier om de registratiepagina van Intune te openen](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/) als u aan de slag wilt gaan met uw gratis proefversie. Als uw organisatie een Enterprise Agreement of equivalente volumelicentieovereenkomst heeft, neemt u contact op met uw Microsoft-vertegenwoordiger om uw gratis proefabonnement in te stellen.

> [!NOTE]
> Als uw organisatie een werk- of schoolaccount voor Microsoft Online Services heeft en u dit Intune-abonnement na de proefperiode mogelijk in uw productieomgeving wilt gebruiken, klikt u op de geopende pagina op de optie **Aanmelden** en voert u de verificatie uit met het account voor de algemeen beheerder voor uw organisatie. Zo zorgt u ervoor dat uw Intune-proefabonnement wordt gekoppeld aan uw bestaande werk- of schoolaccount.

Voor een lijst met instellingen die u op mobiele apparaten kunt configureren, zie:

-   [Beheermogelijkheden voor geregistreerde apparaten in Microsoft Intune](/intune/get-started/mobile-device-management-capabilities-in-microsoft-intune) 

-   [Hybride Mobile Device Management (MDM) met System Center Configuration Manager en Microsoft Intune](https://technet.microsoft.com/library/mt627883.aspx) 

Zie [Documentatiebibliotheek voor System Center Configuration Manager](https://technet.microsoft.com/library/mt346023.aspx)voor informatie over System Center Configuration Manager.

## Het effect van Intune-service-updates op het gebruik van de service
Omdat Intune een onlineservice is, kan de service regelmatig door Microsoft worden bijgewerkt.

In dit onderwerp vindt u informatie over de frequentie van deze service-updates en de voorafgaande melding die u van ons ontvangt wanneer een update van invloed kan zijn op uw gebruik van de service.

Zie [Wat is er nieuw in Microsoft Intune?](/intune/deploy-use/whats-new-in-microsoft-intune) voor meer informatie over wijzigingen in de Intune-service. De wijzigingen in de service worden ook in de [Microsoft Intune-blog](http://blogs.technet.com/b/microsoftintune/) besproken en u vindt in de blog nuttige tips om Intune optimaal te gebruiken. 

Belangrijke updates van de service worden ook aan u doorgegeven in het berichtencentrum van de [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx). Als u de bijbehorende [mobiele Office 365-beheer-app](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a) installeert, kunt u meldingen ontvangen op uw mobiele apparaat.

> [!NOTE]
> U kunt de servicestatus van Intune bewaken in de [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx). Kies **Servicestatus** in het linkerdeelvenster.  

Dit zijn de typen meldingen die Microsoft over de Intune-service biedt:
-   Om te helpen u voor te bereiden op wijzigingen in de service, brengen wij u hiervan ten minste 30 - 90 dagen vóór de service-upgrade op de hoogte, afhankelijk van de gevolgen van de wijziging. Dit vindt plaats via de communicatiekanalen van het product zelf, zoals waarschuwingen op het mededelingenbord. Deze wijzigingen kunnen het volgende omvatten:
* Updates die mogelijk gevolgen hebben voor de beleidsregels of de naleving hiervan
* Wijzigingen in de gebruikerservaring, gebruikersinterface en werkstromen
* Nieuwe of gewijzigde API's. U wordt meegedeeld dat u deze moet testen om ervoor te zorgen dat compatibiliteit met eerdere versies is gewaarborgd
* Wijzigingen in de systeemvereisten, bijvoorbeeld de browserversie die minimaal vereist is
* Updates waarvoor u actie moet ondernemen om de functie in te schakelen of om te voorkomen dat de service voor de functie wordt onderbroken.
-   Informatie over nieuwe functies, nieuwe functionaliteit en verbeteringen in bestaande functies biedt Microsoft in de maandelijkse service-update. Over het algemeen worden de service-updates door Microsoft rond het midden van elke maand geïmplementeerd. Updates worden beschreven in [Wat is er nieuw in Microsoft Intune?](/intune/deploy-use/whats-new-in-microsoft-intune).
-   In het geval van stopzetting van de Intune-service, ontvangt u 12 maanden van tevoren een melding.

## De beheeroplossing kiezen die het beste geschikt is voor u
U kunt Intune op verschillende manieren configureren om de mobiele apparaten en computers (in dit document **apparaten** genoemd) van uw bedrijf te beheren en te beveiligen.

-   **Zelfstandige configuratie van Intune.** Gebruik de webbeheerconsole in Intune om apparaten in uw organisatie te beheren. Intune kan worden gebruikt zonder on-premises IT-infrastructuur, maar als u Intune gebruikt met Active Directory Domain Services, kunt u gebruikmaken van domeingebruikersaccounts die u bij Intune beheert met Domain Services.

-   **Intune met System Center Configuration Manager.** Gebruik de Configuration Manager-beheerconsole om computers en mobiele apparaten in uw bedrijf te beheren. Met deze configuratie kunt u alle apparaten van uw organisatie beheren via één console, de Configuration Manager-beheerconsole. Configuration Manager ondersteunt een zeer groot aantal mobiele apparaten, servers en computers. Zie [Hybride Mobile Device Management (MDM) met System Center Configuration Manager en Microsoft Intune](https://technet.microsoft.com/library/mt627883.aspx) voor meer informatie.  Zie [Kiezen tussen Microsoft Intune standalone en hybride Mobile Device Management met Configuration Manager](https://technet.microsoft.com/en-us/library/mt706478.aspx) voor meer informatie om te bepalen welke benadering geschikt is voor u. 


## Meer informatie over Intune
Voor meer informatie over Intune kunt u de volgende resources raadplegen:

-   [Microsoft Intune Vertrouwenscentrum](http://www.microsoft.com/en-us/server-cloud/products/intune-trust-center/) bevat informatie over de beveiligings-, privacy- en nalevingsprocedures van Intune. Daarnaast wordt er een aantal certificaten van Intune beschreven.

-   [Beheermogelijkheden voor geregistreerde apparaten in Microsoft Intune](/intune/get-started/mobile-device-management-capabilities-in-microsoft-intune) 

### Zie tevens
[Microsoft Intune](https://docs.microsoft.com/intune/)
[Documentatiebibliotheek voor System Center 2012 Configuration Manager](https://technet.microsoft.com/library/gg682041.aspx)

[Wat is er nieuw in Microsoft Intune?](/intune/deploy-use/whats-new-in-microsoft-intune)



<!--HONumber=Sep16_HO4-->

||||||| merged common ancestors

---

# Beschrijving van de Microsoft Intune-service

Microsoft Intune is een cloudservice waarmee u Windows-pc's en mobiele iOS-, Mac OS X-, Android- en Windows-apparaten kunt beheren. Met Intune kunt u ook bedrijfsapplicaties en -gegevens beveiligen. U kunt Intune zelfstandig gebruiken of u kunt het integreren met System Center Configuration Manager en zo de beheermogelijkheden uitbreiden. 

Microsoft biedt het Intune Onboarding-voordeel voor services in abonnementen die daarvoor in aanmerking komen. Met het voorbereidingsvoordeel krijgt u externe ondersteuning van Microsoft-specialisten bij het klaarstomen van uw Intune-omgeving. Zie [Beschrijving voorbereidingsvoordeel Microsoft Intune](http://go.microsoft.com/fwlink/?LinkId=619281)voor meer informatie.

U kunt 30 dagen lang een gratis proefversie van Intune met 100 gebruikerslicenties gebruiken. [Klik hier om de registratiepagina van Intune te openen](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/) als u aan de slag wilt gaan met uw gratis proefversie. Als uw organisatie een Enterprise Agreement of equivalente volumelicentieovereenkomst heeft, neemt u contact op met uw Microsoft-vertegenwoordiger om uw gratis proefabonnement in te stellen.

> [!NOTE]
> Als uw organisatie een werk- of schoolaccount voor Microsoft Online Services heeft en u dit Intune-abonnement na de proefperiode mogelijk in uw productieomgeving wilt gebruiken, klikt u op de geopende pagina op de optie **Aanmelden** en voert u de verificatie uit met het account voor de algemeen beheerder voor uw organisatie. Zo zorgt u ervoor dat uw Intune-proefabonnement wordt gekoppeld aan uw bestaande werk- of schoolaccount.

Voor een lijst met instellingen die u op mobiele apparaten kunt configureren, zie:

-   [Beheermogelijkheden voor geregistreerde apparaten in Microsoft Intune](/intune/get-started/mobile-device-management-capabilities-in-microsoft-intune) 

-   [Hybride Mobile Device Management (MDM) met System Center Configuration Manager en Microsoft Intune](https://technet.microsoft.com/library/mt627883.aspx) 

Zie [Documentatiebibliotheek voor System Center Configuration Manager](https://technet.microsoft.com/library/mt346023.aspx)voor informatie over System Center Configuration Manager.

## Het effect van Intune-service-updates op het gebruik van de service
Omdat Intune een onlineservice is, kan de service regelmatig door Microsoft worden bijgewerkt.

In dit onderwerp vindt u informatie over de frequentie van deze service-updates en de voorafgaande melding die u van ons ontvangt wanneer een update van invloed kan zijn op uw gebruik van de service.

Zie [Wat is er nieuw in Microsoft Intune?](/intune/deploy-use/whats-new-in-microsoft-intune) voor meer informatie over wijzigingen in de Intune-service. De wijzigingen in de service worden ook in de [Microsoft Intune-blog](http://blogs.technet.com/b/microsoftintune/) besproken en u vindt in de blog nuttige tips om Intune optimaal te gebruiken. 

Belangrijke updates van de service worden ook aan u doorgegeven in het berichtencentrum van de [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx). Als u de bijbehorende [mobiele Office 365-beheer-app](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a) installeert, kunt u meldingen ontvangen op uw mobiele apparaat.

> [!NOTE]
> U kunt de servicestatus van Intune bewaken in de [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx). Kies **Servicestatus** in het linkerdeelvenster.  

Dit zijn de typen meldingen die Microsoft over de Intune-service biedt:
-   Om te helpen u voor te bereiden op wijzigingen in de service, brengen wij u hiervan ten minste 30 - 90 dagen vóór de service-upgrade op de hoogte, afhankelijk van de gevolgen van de wijziging. Dit vindt plaats via de communicatiekanalen van het product zelf, zoals waarschuwingen op het mededelingenbord. Deze wijzigingen kunnen het volgende omvatten:
* Updates die mogelijk gevolgen hebben voor de beleidsregels of de naleving hiervan
* Wijzigingen in de gebruikerservaring, gebruikersinterface en werkstromen
* Nieuwe of gewijzigde API's. U wordt meegedeeld dat u deze moet testen om ervoor te zorgen dat compatibiliteit met eerdere versies is gewaarborgd
* Wijzigingen in de systeemvereisten, bijvoorbeeld de browserversie die minimaal vereist is
* Updates waarvoor u actie moet ondernemen om de functie in te schakelen of om te voorkomen dat de service voor de functie wordt onderbroken.
-   Informatie over nieuwe functies, nieuwe functionaliteit en verbeteringen in bestaande functies biedt Microsoft in de maandelijkse service-update. Over het algemeen worden de service-updates door Microsoft rond het midden van elke maand geïmplementeerd. Updates worden beschreven in [Wat is er nieuw in Microsoft Intune?](/intune/deploy-use/whats-new-in-microsoft-intune).
-   In het geval van stopzetting van de Intune-service, ontvangt u 12 maanden van tevoren een melding.

## De beheeroplossing kiezen die het beste geschikt is voor u
U kunt Intune op verschillende manieren configureren om de mobiele apparaten en computers (in dit document **apparaten** genoemd) van uw bedrijf te beheren en te beveiligen.

-   **Zelfstandige configuratie van Intune.** Gebruik de webbeheerconsole in Intune om apparaten in uw organisatie te beheren. Intune kan worden gebruikt zonder on-premises IT-infrastructuur, maar als u Intune gebruikt met Active Directory Domain Services, kunt u gebruikmaken van domeingebruikersaccounts die u bij Intune beheert met Domain Services.

-   **Intune met System Center Configuration Manager.** Gebruik de Configuration Manager-beheerconsole om computers en mobiele apparaten in uw bedrijf te beheren. Met deze configuratie kunt u alle apparaten van uw organisatie beheren via één console, de Configuration Manager-beheerconsole. Configuration Manager ondersteunt een zeer groot aantal mobiele apparaten, servers en computers. Zie [Hybride Mobile Device Management (MDM) met System Center Configuration Manager en Microsoft Intune](https://technet.microsoft.com/library/mt627883.aspx) voor meer informatie.  Zie [Kiezen tussen Microsoft Intune standalone en hybride Mobile Device Management met Configuration Manager](https://technet.microsoft.com/en-us/library/mt706478.aspx) voor meer informatie om te bepalen welke benadering geschikt is voor u. 


## Meer informatie over Intune
Voor meer informatie over Intune kunt u de volgende resources raadplegen:

-   [Microsoft Intune Vertrouwenscentrum](http://www.microsoft.com/en-us/server-cloud/products/intune-trust-center/) bevat informatie over de beveiligings-, privacy- en nalevingsprocedures van Intune. Daarnaast wordt er een aantal certificaten van Intune beschreven.

-   [Beheermogelijkheden voor geregistreerde apparaten in Microsoft Intune](/intune/get-started/mobile-device-management-capabilities-in-microsoft-intune) 

### Zie tevens
[Microsoft Intune](https://docs.microsoft.com/intune/)
[Documentatiebibliotheek voor System Center 2012 Configuration Manager](https://technet.microsoft.com/library/gg682041.aspx)

[Wat is er nieuw in Microsoft Intune?](/intune/deploy-use/whats-new-in-microsoft-intune)



<!--HONumber=Sep16_HO4-->

=======

---

# <a name="microsoft-intune-service-description"></a>Beschrijving van de Microsoft Intune-service

Microsoft Intune is een cloudservice waarmee u Windows-pc's en mobiele iOS-, Mac OS X-, Android- en Windows-apparaten kunt beheren. Met Intune kunt u ook bedrijfsapplicaties en -gegevens beveiligen. U kunt Intune zelfstandig gebruiken of u kunt het integreren met System Center Configuration Manager en zo de beheermogelijkheden uitbreiden. 

Microsoft biedt het Intune Onboarding-voordeel voor services in abonnementen die daarvoor in aanmerking komen. Met het voorbereidingsvoordeel krijgt u externe ondersteuning van Microsoft-specialisten bij het klaarstomen van uw Intune-omgeving. Zie [Beschrijving voorbereidingsvoordeel Microsoft Intune](http://go.microsoft.com/fwlink/?LinkId=619281)voor meer informatie.

U kunt 30 dagen lang een gratis proefversie van Intune met 100 gebruikerslicenties gebruiken. [Klik hier om de registratiepagina van Intune te openen](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/) als u aan de slag wilt gaan met uw gratis proefversie. Als uw organisatie een Enterprise Agreement of equivalente volumelicentieovereenkomst heeft, neemt u contact op met uw Microsoft-vertegenwoordiger om uw gratis proefabonnement in te stellen.

> [!NOTE]
> Als uw organisatie een werk- of schoolaccount voor Microsoft Online Services heeft en u dit Intune-abonnement na de proefperiode mogelijk in uw productieomgeving wilt gebruiken, klikt u op de geopende pagina op de optie **Aanmelden** en voert u de verificatie uit met het account voor de algemeen beheerder voor uw organisatie. Zo zorgt u ervoor dat uw Intune-proefabonnement wordt gekoppeld aan uw bestaande werk- of schoolaccount.

Voor een lijst met instellingen die u op mobiele apparaten kunt configureren, zie:

-   [Beheermogelijkheden voor ingeschreven apparaten in Microsoft Intune](/intune/get-started/mobile-device-management-capabilities-in-microsoft-intune) 

-   [Hybride Mobile Device Management (MDM) met System Center Configuration Manager en Microsoft Intune](https://technet.microsoft.com/library/mt627883.aspx) 

Zie [Documentatiebibliotheek voor System Center Configuration Manager](https://technet.microsoft.com/library/mt346023.aspx)voor informatie over System Center Configuration Manager.

## <a name="understand-how-intune-service-updates-affect-you"></a>Het effect van Intune-service-updates op het gebruik van de service
Omdat Intune een onlineservice is, kan de service regelmatig door Microsoft worden bijgewerkt.

In dit onderwerp vindt u informatie over de frequentie van deze service-updates en de voorafgaande melding die u van ons ontvangt wanneer een update van invloed kan zijn op uw gebruik van de service.

Zie [Wat is er nieuw in Microsoft Intune?](/intune/deploy-use/whats-new-in-microsoft-intune) voor meer informatie over wijzigingen in de Intune-service. De wijzigingen in de service worden ook in de [Microsoft Intune-blog](http://blogs.technet.com/b/microsoftintune/) besproken en u vindt in de blog nuttige tips om Intune optimaal te gebruiken. 

Belangrijke updates van de service worden ook aan u doorgegeven in het berichtencentrum van de [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx). Als u de bijbehorende [mobiele Office 365-beheer-app](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a) installeert, kunt u meldingen ontvangen op uw mobiele apparaat.

> [!NOTE]
> U kunt de servicestatus van Intune bewaken in de [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx). Kies **Servicestatus** in het linkerdeelvenster.  

Dit zijn de typen meldingen die Microsoft over de Intune-service biedt:
-   Om te helpen u voor te bereiden op wijzigingen in de service, brengen wij u hiervan ten minste 30 - 90 dagen vóór de service-upgrade op de hoogte, afhankelijk van de gevolgen van de wijziging. Dit vindt plaats via de communicatiekanalen van het product zelf, zoals waarschuwingen op het mededelingenbord. Deze wijzigingen kunnen het volgende omvatten:
* Updates die mogelijk gevolgen hebben voor de beleidsregels of de naleving hiervan
* Wijzigingen in de gebruikerservaring, gebruikersinterface en werkstromen
* Nieuwe of gewijzigde API's. U wordt meegedeeld dat u deze moet testen om ervoor te zorgen dat compatibiliteit met eerdere versies is gewaarborgd
* Wijzigingen in de systeemvereisten, bijvoorbeeld de browserversie die minimaal vereist is
* Updates waarvoor u actie moet ondernemen om de functie in te schakelen of om te voorkomen dat de service voor de functie wordt onderbroken.
-   Informatie over nieuwe functies, nieuwe functionaliteit en verbeteringen in bestaande functies biedt Microsoft in de maandelijkse service-update. Over het algemeen worden de service-updates door Microsoft rond het midden van elke maand geïmplementeerd. Updates worden beschreven in [Wat is er nieuw in Microsoft Intune?](/intune/deploy-use/whats-new-in-microsoft-intune).
-   In het geval van stopzetting van de Intune-service, ontvangt u 12 maanden van tevoren een melding.

## <a name="choose-the-management-solution-thats-right-for-you"></a>De beheeroplossing kiezen die het beste geschikt is voor u
U kunt Intune op verschillende manieren configureren om de mobiele apparaten en computers (in dit document **apparaten** genoemd) van uw bedrijf te beheren en te beveiligen.

-   **Zelfstandige configuratie van Intune.** Gebruik de webbeheerconsole in Intune om apparaten in uw organisatie te beheren. Intune kan worden gebruikt zonder on-premises IT-infrastructuur, maar als u Intune gebruikt met Active Directory Domain Services, kunt u gebruikmaken van domeingebruikersaccounts die u bij Intune beheert met Domain Services.

-   **Intune met System Center Configuration Manager.** Gebruik de Configuration Manager-beheerconsole om computers en mobiele apparaten in uw bedrijf te beheren. Met deze configuratie kunt u alle apparaten van uw organisatie beheren via één console, de Configuration Manager-beheerconsole. Configuration Manager ondersteunt een zeer groot aantal mobiele apparaten, servers en computers. Zie [Hybride Mobile Device Management (MDM) met System Center Configuration Manager en Microsoft Intune](https://technet.microsoft.com/library/mt627883.aspx) voor meer informatie.  Zie [Kiezen tussen Microsoft Intune standalone en hybride Mobile Device Management met Configuration Manager](https://technet.microsoft.com/en-us/library/mt706478.aspx) voor meer informatie om te bepalen welke benadering geschikt is voor u. 


## <a name="learn-more-about-intune"></a>Meer informatie over Intune
Voor meer informatie over Intune kunt u de volgende resources raadplegen:

-   [Microsoft Intune Vertrouwenscentrum](http://www.microsoft.com/en-us/server-cloud/products/intune-trust-center/) bevat informatie over de beveiligings-, privacy- en nalevingsprocedures van Intune. Daarnaast wordt er een aantal certificaten van Intune beschreven.

-   [Beheermogelijkheden voor ingeschreven apparaten in Microsoft Intune](/intune/get-started/mobile-device-management-capabilities-in-microsoft-intune) 

### <a name="see-also"></a>Zie tevens
[Microsoft Intune](https://docs.microsoft.com/intune/)
[Documentatiebibliotheek voor System Center 2012 Configuration Manager](https://technet.microsoft.com/library/gg682041.aspx)

[Wat is er nieuw in Microsoft Intune?](/intune/deploy-use/whats-new-in-microsoft-intune)



<!--HONumber=Nov16_HO1-->

>>>>>>> 36752dab280937bd95c2ae9719aa3b406dcd9321

