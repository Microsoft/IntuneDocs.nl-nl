---
title: Voordelen van de Intune App SDK | Microsoft Intune
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b7f62c5ee18d8f69fa174f09a1c46b6925c7517c
ms.openlocfilehash: 3abf566831348de11f718370d6267e3ff4355bfb


---

# Overzicht van de Intune App SDK
De Microsoft Intune App SDK is beschikbaar voor zowel het iOS-platform als het Android-platform en maakt Mobile App Management-functies mogelijk met Microsoft Intune. Daarnaast streven we ernaar het aantal codewijzigingen die van de ontwikkelaar worden vereist, te beperken. U ziet dat u de meeste van de SDK-functies kunt inschakelen zonder het gedrag van uw app te wijzigen. U kunt onze API's gebruiken voor het aanpassen van uw app-gedrag voor functies waarvoor de deelname van uw app is vereist, voor een verbeterde ervaring voor eindgebruikers en IT-beheerders. Nadat u uw app hebt ingeschakeld, kunnen IT-beheerders beleid implementeren voor door Intune beheerde apps en van deze functies profiteren om hun bedrijfsgegevens te beveiligen.

## Reguliere functies

### Bepalen of gebruikers om bedrijfsdocumenten kunnen verplaatsen
IT-beheerders kunnen de herlocatie van bedrijfsbestanden in door Intune beheerde apps bepalen. Ze kunnen bijvoorbeeld een beleid implementeren dat back-up-apps ervan weerhoudt back-apps van bedrijfsgegevens te maken naar de cloud.

### Beperkingen van Klembord configureren
IT-beheerders kunnen het gedrag van Klembord in door Intune beheerde apps configureren. Ze kunnen bijvoorbeeld een beleid implementeren dat bepaalt dat eindgebruikers het Klembord niet kunnen gebruiken om gegevens uit een door Intune beheerde app te knippen/kopiëren en deze gegevens vervolgens naar een niet-beheerde app te plakken.

### Beperkingen voor schermafbeeldingen configureren
IT-beheerders kunnen voorkomen dat gebruikers schermafbeeldingen maken als er een Intune-beheerde app wordt weergegeven. Als u deze beperking toepast, voorkomt u dat het vertrouwelijke zakelijke inhoud kan worden vastgelegd en vrijegegeven. Deze functie is alleen beschikbaar voor Android-apparaten.

### Versleuteling van opgeslagen gegevens afdwingen
IT-beheerders kunnen beleid afdwingen dat ervoor zorgt dat de gegevens die door de app op het apparaat worden opgeslagen, worden versleuteld.

### Bedrijfsgegevens op afstand wissen
IT-beheerders kunnen zakelijke gegevens uit een door Intune beheerde app op afstand wissen wanneer het apparaat wordt uitgeschreven bij Microsoft Intune. Deze functie is op de identiteit gebaseerd en verwijdert alleen bestanden die betrekking hebben op de zakelijke identiteit van de eindgebruiker. Hiertoe vereist de functie deelname van de app. De app aangeven voor welke identiteit het wissen moet plaatsvinden op basis van de instellingen van de gebruiker. Als er dergelijke instellingen niet door de gebruiker in de app zijn opgegeven, is het standaardgedrag om de toepassingsmap te wissen en de eindgebruiker te informeren dat de toegang tot bedrijfsresources is verwijderd.

### Het gebruik van een beheerde browser afdwingen
IT-beheerders kunnen het gebruik van een beheerde browser afdwingen voor het openen van koppelingen binnen door Intune beheerde apps. Met de beheerde browser van Microsoft Intune kunt u ervoor zorgen dat koppelingen die in e-mailberichten (in een door Intune beheerde e-mailclient) worden weergegeven binnen het domein van door Intune beheerde apps blijven.

### Een pincodebeleid afdwingen
IT-beheerders kunnen een pincodebeleid afdwingen wanneer een door Intune beheerde app wordt gestart. Dit beleid helpt controleren of de eindgebruikers die hun apparaat bij Microsoft Intune hebben ingeschreven dezelfde personen zijn die de apps starten. Wanneer eindgebruikers hun pincode configureren, gebruikt Intune App SDK Azure Active Directory om te controleren of de referenties van eindgebruikers overeenkomen met die van de apparaatregistratie.

### Vereisen dat gebruikers referenties invoeren voordat ze apps kunnen starten
IT-beheerders kunnen van gebruikers vereisen dat zijn referenties invoeren voordat ze een door Intune beheerde app kunnen starten. De Intune App SDK gebruikt Azure Active Directory om een single sign-on-ervaring te bieden waar de referenties, nadat deze eenmaal zijn opgegeven, opnieuw worden gebruikt voor toekomstige aanmeldingen. We bieden ook ondersteuning voor verificatie van oplossingen voor identiteitsbeheer [die zijn gefedereerd met Azure Active Directory](https://msdn.microsoft.com/library/azure/jj679342.aspx).

### De status en compatibiliteit van apparaten controleren
IT-beheerders kunnen een status en de compatibiliteit van apparaten met het bedrijfsbeleid controleren voordat eindgebruikers toegang tot door Intune beheerde apps krijgen. Op het iOS-platform controleert dit beleid of het apparaat is gekraakt. Op het Android-platform controleert dit beleid of het apparaat is geroot.

## Preview-functies
De Microsoft Intune App SDK bevat verschillende functies die zich ‘in preview’ zijn. U kunt beginnen met de integratie met preview-API's, maar alleen voor testdoeleinden. Houd er rekening mee dat deze previews functies een toevoeging aan bestaande scenario's zijn in plaats van bestaande scenario's vervangen.

### Ondersteuning voor meerdere identiteiten van Microsoft Intune App SDK
Ondersteuning voor meerdere identiteiten is een functie die co-existentie van door beleid beheerde (zakelijke) accounts en niet-beheerde (privé-)accounts in een enkele app mogelijk maakt.

### Voorbeeld van een scenario met meerdere identiteiten
Veel gebruikers configureren zowel bedrijfs- als persoonlijke e-mailaccounts in de Outlook-app voor iOS en Android. Wanneer een gebruiker zich toegang wil verschaffen tot gegevens in een bedrijfsaccount, moet de IT-beheerder erop kunnen vertrouwen dat het MAM-beleid wordt toegepast. Wanneer een gebruiker zich echter toegang wil verschaffen tot een persoonlijk e-mailaccount, moeten die gegevens buiten de controle van de IT-beheerder blijven. Dit wordt door Microsoft Intune bereikt door het beheerbeleid alleen in de app toe te passen. Deze functie voor het gebruik van meerdere identiteiten helpt bij het oplossen van het gegevensbeveiligingsprobleem waarmee organisaties worden geconfronteerd door apparaten en apps die ondersteuning bieden voor zowel privé- als accounts.

### Hoe u meerdere identiteiten kunt ondersteunen
Met preview-API's kunt u een User Principal Name (UPN) met specifieke gegevensbewerkingen opgeven, zoals klembordbewerkingen en bestandsbewerkingen. De Microsoft Intune App SDK gebruikt de UPN om de aanroep te vergelijken met de UPN die voor het inschrijven van het apparaat bij de Microsoft Intune-service is gebruikt. Als de UPN’s overeenkomen, wordt de aanroep beschouwd als een aanroep van bedrijfsgegevens en worden de gegevens beveiligd; als de UPN’s niet overeenkomen, wordt de oproep beschouwd als een aanroep van privégegevens en worden de gegevens niet beveiligd.

### Appbeheer zonder apparaatinschrijving
Veel gebruikers met privé-apparaten willen bedrijfsgegevens kunnen inzien en gebruiken zonder hun privé-apparaat te moeten inschrijven met Mobile Device Management-product (MDM-product). Omdat MDM-inschrijving algemeen beheer van het apparaat vereist, willen gebruikers de algemene controle over hun eigen privé-apparaat niet altijd aan hun bedrijf geven.

Met appbeheer zonder apparaatinschrijving kan de Microsoft Intune-service MAM-beleid rechtstreeks voor een app implementeren zonder voor de implementatie van het beleid afhankelijk te zijn van een MDM-kanaal. Omdat er geen MDM-kanaal is vereist, is MDM-inschrijving niet vereist.




<!--HONumber=Jun16_HO4-->


