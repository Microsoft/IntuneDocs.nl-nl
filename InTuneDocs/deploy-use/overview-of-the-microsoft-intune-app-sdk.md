---
title: Overzicht van de Microsoft Intune App SDK | Microsoft Intune
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ef1751bb-3a2f-4662-a922-38c076869eb3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 4cb153c601b83b113a22b2acf3da5200cdb70472


---

# <a name="overview-of-the-microsoft-intune-app-sdk"></a>Overzicht van de Microsoft Intune App SDK
De Microsoft Intune App SDK is beschikbaar voor zowel het iOS-platform als het Android-platform en maakt Mobile App Management-functies mogelijk met Microsoft Intune. Daarnaast wordt ernaar gestreefd het aantal codewijzigingen die de ontwikkelaar moet aanbrengen, te beperken.

U ziet dat u de meeste van de SDK-functies kunt inschakelen zonder het gedrag van uw app te wijzigen. U kunt onze API's gebruiken voor het aanpassen van uw app-gedrag voor functies waarvoor de deelname van uw app is vereist, voor een verbeterde ervaring voor eindgebruikers en IT-beheerders.

Nadat u uw app hebt ingeschakeld, kunnen IT-beheerders beleid implementeren voor door Intune beheerde apps en van deze functies profiteren om hun bedrijfsgegevens te beveiligen.

# <a name="features"></a>Functies
## <a name="control-users-ability-to-move-corporate-documents"></a>Bepalen of gebruikers bedrijfsdocumenten kunnen verplaatsen
IT-beheerders kunnen de herlocatie van bedrijfsbestanden in door Intune beheerde apps bepalen. Ze kunnen bijvoorbeeld een beleid implementeren dat back-up-apps ervan weerhoudt back-apps van bedrijfsgegevens te maken naar de cloud.  

## <a name="configure-clipboard-restrictions"></a>Beperkingen van Klembord configureren
IT-beheerders kunnen het gedrag van Klembord in door Intune beheerde apps configureren. Ze kunnen bijvoorbeeld een beleid implementeren dat bepaalt dat eindgebruikers het Klembord niet kunnen gebruiken om gegevens uit een door Intune beheerde app te knippen/kopiëren en deze gegevens vervolgens in een niet-beheerde app te plakken.

## <a name="enforce-encryption-on-saved-data"></a>Versleuteling van opgeslagen gegevens afdwingen
IT-beheerders kunnen beleid afdwingen dat ervoor zorgt dat de gegevens die door de app op het apparaat worden opgeslagen, worden versleuteld.

## <a name="remotely-wipe-corporate-data"></a>Bedrijfsgegevens op afstand wissen
IT-beheerders kunnen zakelijke gegevens uit een door Intune beheerde app op afstand wissen wanneer het apparaat wordt uitgeschreven bij Microsoft Intune. Deze functie is op de identiteit gebaseerd en verwijdert alleen bestanden die betrekking hebben op de zakelijke identiteit van de eindgebruiker. Hiertoe vereist de functie deelname van de app. De app aangeven voor welke identiteit het wissen moet plaatsvinden op basis van de instellingen van de gebruiker. Als er dergelijke instellingen niet door de gebruiker in de app zijn opgegeven, is het standaardgedrag om de toepassingsmap te wissen en de eindgebruiker te informeren dat de toegang tot bedrijfsresources is verwijderd.

## <a name="enforce-the-use-of-a-managed-browser"></a>Het gebruik van een beheerde browser afdwingen
IT-beheerders kunnen het gebruik van een beheerde browser afdwingen wanneer gebruikers koppelingen binnen door Intune beheerde apps openen. Wanneer eindgebruikers de beheerde browser van Microsoft Intune gebruiken, kunt u ervoor zorgen dat koppelingen in e-mailberichten in een door Intune beheerde e-mailclient worden weergegeven binnen het domein van door Intune beheerde apps blijven.

## <a name="enforce-a-pin-policy"></a>Een pincodebeleid afdwingen
IT-beheerders kunnen een pincodebeleid afdwingen wanneer een door Intune beheerde app wordt gestart. Dit beleid helpt controleren of de eindgebruikers die hun apparaat bij Microsoft Intune hebben ingeschreven dezelfde personen zijn die de apps starten. Wanneer eindgebruikers hun pincode configureren, gebruikt de Intune App SDK Azure Active Directory om te controleren of hun referenties overeenkomen met die van de apparaatregistratie.

## <a name="require-users-to-enter-credentials-before-they-can-start-apps"></a>Vereisen dat gebruikers referenties invoeren voordat ze apps kunnen starten
IT-beheerders kunnen van eindgebruikers vereisen dat zij referenties invoeren voordat ze een door Intune beheerde app kunnen starten. De Intune App SDK gebruikt Azure Active Directory om ervoor te zorgen dat gebruikers zich slechts één keer hoeven aan te melden. Dit betekent dat zodra de referenties zijn ingevoerd, ze voor volgende aanmeldingen opnieuw worden gebruikt. De SDK biedt ook ondersteuning voor de verificatie van oplossingen voor identiteitsbeheer [die zijn gefedereerd met Azure Active Directory](/active-directory/active-directory-aadconnect-federation-compatibility).

## <a name="check-device-health-and-compliance"></a>De status en compatibiliteit van apparaten controleren
IT-beheerders kunnen de status en compatibiliteit van apparaten met het bedrijfsbeleid controleren voordat eindgebruikers toegang tot door Intune beheerde apps krijgen. Op het iOS-platform controleert dit beleid of het apparaat is gekraakt. Op het Android-platform controleert dit beleid of het apparaat is geroot.  



<!--HONumber=Nov16_HO5-->


