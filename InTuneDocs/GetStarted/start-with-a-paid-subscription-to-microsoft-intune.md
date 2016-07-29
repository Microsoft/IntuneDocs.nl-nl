---
title: Snelstartgids voor Intune | Microsoft Intune
description: Vereisten en voorwaarden om uw Intune-abonnement te gaan gebruiken
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2a192c71b1b82f59b34ea614d09d895174f8112b
ms.openlocfilehash: d10bb6ce48ba000154d117b2481690a198d25e49


---


# Snelstartgids voor Intune
Deze snelstartgids bevat stapsgewijze instructies voor het instellen van een betaald abonnement van Microsoft Intune, zodat u snel en eenvoudig mobiele apparaten en Windows-pc's kunt beheren die door uw organisatie worden gebruikt. U kunt de stappen in volgorde uitvoeren, maar ook stappen overslaan die niet van toepassing zijn op uw specifieke omgeving of bedrijfsbehoeften.

>[!NOTE]
>Dit artikel is gericht op het instellen van Intune als zelfstandige service. Als u momenteel Microsoft System Center Configuration Manager gebruikt voor het beheren van computers en servers, kunt u ook [Configuration Manager uitbreiden voor het beheer van mobiele apparaten](https://technet.microsoft.com/library/jj884158.aspx). U doet dit door Intune te verbinden met Configuration Manager in een hybride Mobile Device Management-implementatie (MDM).

De stappen in deze snelstartgids komen grotendeels overeen met de stappen in de [Intune-evaluatiehandleiding](/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune). Wanneer u de evaluatie hebt voltooid en wanneer u klaar bent om uw mobiele apparaten te gaan beheren, moet u echter aan enkele aanvullende vereisten voldoen:

-   On-premises Active Directory-accounts synchroniseren met Intune en Azure Active Directory.

-   Het openbaar domein en DNS-servicerecords bijwerken bij uw domeinregistrar.

-   Intune-functies aanpassen voor gebruik in productieomgevingen.

>[!TIP]
>Als u ten minste 150 licenties voor Microsoft Intune koopt binnen een abonnement dat in aanmerking komt, kunt u gebruikmaken van de *FastTrack Center Benefit*. Dit is een service waarbij Microsoft-specialisten met u samenwerken om uw omgeving voor te bereiden voor Intune. Zie [Beschrijving van het Microsoft Intune-servicevoordeel](https://technet.microsoft.com/library/mt228265.aspx).


## Voordat u begint
Gebruik deze gids wanneer u een betaald abonnement gaat gebruiken en klaar bent om Intune te implementeren en wijzigingen aan te brengen in uw bestaande netwerkinfrastructuur. Deze taken kunnen variëren van het simpelweg toevoegen of bijwerken van de interne en externe DNS-records tot het synchroniseren van uw bestaande Active Directory-gebruikersaccounts met Azure Active Directory. Ongeacht de combinatie van Intune-functies voor het beheer van mobiele apparaten die u kiest, moet u zorgvuldig plannen hoe Intune op de bestaande netwerkonderdelen en -services aansluit. Houd in het bijzonder rekening met het volgende:

-   **Hoe u gebruikersidentiteiten beheert**: voor de meeste middelgrote tot grote organisaties is het koppelen van de bestaande adreslijstservices aan Intune via Azure Active Directory de beste en gemakkelijkste manier om met Intune gebruikersidentiteiten te beheren. Dit geldt vooral als u andere Microsoft-cloudservices gebruikt, zoals Office 365 of Exchange Online. Het synchroniseren van uw bestaande gebruikersaccounts met behulp van [Microsoft Azure Active Directory Connect](https://www.microsoft.com/download/details.aspx?id=47594) is een snelle en gemakkelijke manier om de on-premises Active Directory te koppelen aan Azure Active Directory en voor gebruikers eenmalige aanmelding te configureren.

-   **Gevolgen voor DNS**: als u uw eigen domeinnaam wilt gebruiken in plaats van het standaarddomein onmicrosoft.com dat u krijgt wanneer u zich de eerste keer bij Intune aanmeldt, dan moeten er enkele openbare DNS-records worden bijgewerkt. De DNS-records moeten worden bijgewerkt, zodat mobiele apparaten de Intune-service kunnen vinden en om ervoor te zorgen dat alle apparaten die door uw organisatie worden gebruikt, correct worden beheerd met de beheerservice voor uw abonnement.

## Zorg ervoor dat u de volgende items bij de hand hebt
Gereed om te beginnen? U hebt de volgende items nodig wanneer u uw betaalde abonnement op Intune wilt gaan gebruiken:

### Een apparaat met een Silverlight-webbrowser
Dit hebt u nodig voor toegang tot de Intune-beheerconsole waarmee u apparaten, apps en beleidsregels gaat beheren. U hebt ook een webbrowser nodig om de webgebaseerde Intune-bedrijfsportal te gebruiken wanneer u de bedrijfsportal-app niet opent op een mobiel apparaat. Het is eenvoudiger om de instelling 'privacymodus' te gebruiken in de browser die u ook gebruikt voor Intune-beheer (in Internet Explorer bijvoorbeeld kunt u klikken op **Extra** &gt; **InPrivate-browsing**).

>[!TIP]
>Vanwege deze vereiste wordt de Microsoft Edge-browser niet ondersteund voor toegang tot de Intune-beheerconsole.


### Certificaten voor mobiele apparaten
Als u met Intune iOS- of Windows Phone-apparaten beheert, hebt u certificaten nodig, evenals accounts om deze certificaten op te halen. U hebt geen extra certificaten nodig om Android-apparaten te beheren.

- Er is geen certificaat nodig voor **Windows Phone 8.1**-gebruikers die de bedrijfsportal-app installeren vanuit de Store. Er is echter wel een [Symantec-certificaat voor codeondertekening](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do) vereist voor **Windows Phone 8.0** of als u Intune wilt gebruiken om de bedrijfsportal-app te implementeren op Windows Phone 8.1-apparaten.

>[!NOTE]
>In deze snelstartgids wordt ervan uitgegaan dat uw gebruikers de bedrijfsportal-app vanuit de Store downloaden op een apparaat met Windows Phone 8.1 of hoger. Zie voor informatie over de ondersteuning van Windows Phone 8.0 [Windows Phone 8.0-beheer met Microsoft Intune instellen](/Intune/deploy-use/set-up-windows-phone-8.0-management-with-microsoft-intune).

- Er zijn geen certificaatvereisten voor **Windows-pc's** of **Windows RT-apparaten** wanneer u Windows-pc's inschrijft als apparaten of de [Windows-pc-client voor Microsoft Intune installeert](/intune/deploy-use/install-the-windows-pc-client-with-microsoft-intune).

- Voor **iOS**- en **Mac OS X**-apparaten moet u een Apple Push Notification servicecertificaat aanvragen bij Apple, zoals wordt beschreven in stap 3 van [iOS- en Mac-beheer met Microsoft Intune instellen](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

## Volgende stappen
U kunt nu aan de slag met de snelstartgids voor Intune.

>[!div class="step-by-step"]
[**Aanmelden bij Intune** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)



<!--HONumber=Jul16_HO4-->


