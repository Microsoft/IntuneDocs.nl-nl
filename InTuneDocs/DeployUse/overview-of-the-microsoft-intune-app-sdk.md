---
# required metadata

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

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Overzicht van de Microsoft Intune App SDK
De Microsoft Intune App SDK is beschikbaar voor zowel het iOS-platform als het Android-platform en maakt Mobile App Management-functies mogelijk met Microsoft Intune. Daarnaast streven we ernaar het aantal codewijzigingen die van de ontwikkelaar worden vereist, te beperken. U ziet dat u de meeste van de SDK-functies kunt inschakelen zonder het gedrag van uw app te wijzigen. U kunt onze API's gebruiken voor het aanpassen van uw app-gedrag voor functies waarvoor de deelname van uw app is vereist, voor een verbeterde ervaring voor eindgebruikers en IT-beheerders. 

Nadat u uw app hebt ingeschakeld, kunnen IT-beheerders beleid implementeren voor door Intune beheerde apps en van deze functies profiteren om hun bedrijfsgegevens te beveiligen.

# Functies
## Bepalen of gebruikers om bedrijfsdocumenten kunnen verplaatsen
IT-beheerders kunnen de herlocatie van bedrijfsbestanden in door Intune beheerde apps bepalen. Ze kunnen bijvoorbeeld een beleid implementeren dat back-up-apps ervan weerhoudt back-apps van bedrijfsgegevens te maken naar de cloud.  

## Beperkingen van Klembord configureren
IT-beheerders kunnen het gedrag van Klembord in door Intune beheerde apps configureren. Ze kunnen bijvoorbeeld een beleid implementeren dat bepaalt dat eindgebruikers het Klembord niet kunnen gebruiken om gegevens uit een door Intune beheerde app te knippen/kopiëren en deze gegevens vervolgens naar een niet-beheerde app te plakken.

## Beperkingen voor schermafbeeldingen configureren
IT-beheerders kunnen voorkomen dat gebruikers schermafbeeldingen maken als er een Intune-beheerde app wordt weergegeven. Als u deze beperking toepast, voorkomt u dat het vertrouwelijke zakelijke inhoud kan worden vastgelegd en vrijegegeven. Deze functie is alleen beschikbaar voor Android-apparaten. 

## Versleuteling van opgeslagen gegevens afdwingen
IT-beheerders kunnen beleid afdwingen dat ervoor zorgt dat de gegevens die door de app op het apparaat worden opgeslagen, worden versleuteld.

## Bedrijfsgegevens op afstand wissen
IT-beheerders kunnen zakelijke gegevens uit een door Intune beheerde app op afstand wissen wanneer het apparaat wordt uitgeschreven bij Microsoft Intune. Deze functie is op de identiteit gebaseerd en verwijdert alleen bestanden die betrekking hebben op de zakelijke identiteit van de eindgebruiker. Hiertoe vereist de functie deelname van de app. De app aangeven voor welke identiteit het wissen moet plaatsvinden op basis van de instellingen van de gebruiker. Als er dergelijke instellingen niet door de gebruiker in de app zijn opgegeven, is het standaardgedrag om de toepassingsmap te wissen en de eindgebruiker te informeren dat de toegang tot bedrijfsresources is verwijderd. 

## Het gebruik van een beheerde browser afdwingen
IT-beheerders kunnen het gebruik van een beheerde browser afdwingen voor het openen van koppelingen binnen door Intune beheerde apps. Met de beheerde browser van Microsoft Intune kunt u ervoor zorgen dat koppelingen die in e-mailberichten (in een door Intune beheerde e-mailclient) worden weergegeven binnen het domein van door Intune beheerde apps blijven.

## Een pincodebeleid afdwingen
IT-beheerders kunnen een pincodebeleid afdwingen wanneer een door Intune beheerde app wordt gestart. Dit beleid helpt controleren of de eindgebruikers die hun apparaat bij Microsoft Intune hebben ingeschreven dezelfde personen zijn die de apps starten. Wanneer eindgebruikers hun pincode configureren, gebruikt Intune App SDK Azure Active Directory om te controleren of de referenties van eindgebruikers overeenkomen met die van de inschrijving van het apparaat. 

## Vereisen dat gebruikers referenties invoeren voordat ze apps kunnen starten
IT-beheerders kunnen van gebruikers vereisen dat zijn referenties invoeren voordat ze een door Intune beheerde app kunnen starten. De Intune App SDK gebruikt Azure Active Directory om een single sign-on-ervaring te bieden waar de referenties, nadat deze eenmaal zijn opgegeven, opnieuw worden gebruikt voor toekomstige aanmeldingen. We bieden ook ondersteuning voor verificatie van oplossingen voor identiteitsbeheer [die zijn gefedereerd met Azure Active Directory](https://msdn.microsoft.com/en-us/library/azure/jj679342.aspx). 

## De status en compatibiliteit van apparaten controleren
IT-beheerders kunnen een status en de compatibiliteit van apparaten met het bedrijfsbeleid controleren voordat eindgebruikers toegang tot door Intune beheerde apps krijgen. Op het iOS-platform controleert dit beleid of het apparaat is gekraakt. Op het Android-platform controleert dit beleid of het apparaat is geroot.  




<!--HONumber=May16_HO1-->


