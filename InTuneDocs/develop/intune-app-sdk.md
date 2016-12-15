---
title: Voordelen van de Intune App SDK | Microsoft Docs
description: 
keywords: 
author: mtillman
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 613e293d9bd853d6de7cdc0d753cc8473afc180b
ms.openlocfilehash: e8f96499f006af590b6e7da295503696110dad4e


---

# <a name="intune-app-sdk-overview"></a>Overzicht van de Intune App SDK
De Microsoft Intune App SDK is beschikbaar voor zowel het iOS-platform als het Android-platform en maakt Mobile App Management-functies mogelijk met Microsoft Intune. Deze streeft ernaar om het aantal door de app-ontwikkelaar vereiste codewijzigingen zo klein mogelijk te maken. U ziet dat u de meeste van de SDK-functies kunt inschakelen zonder het gedrag van uw app te wijzigen. U kunt onze API's gebruiken voor het aanpassen van uw app-gedrag voor functies waarvoor de deelname van uw app is vereist, voor een verbeterde ervaring voor eindgebruikers en IT-beheerders. 

Nadat u uw app hebt ingeschakeld, kunnen IT-beheerders beleid implementeren voor door Intune beheerde apps en van deze functies profiteren om hun bedrijfsgegevens te beveiligen.

## <a name="regular-features"></a>Reguliere functies

### <a name="control-users-ability-to-move-corporate-documents"></a>Bepalen of gebruikers om bedrijfsdocumenten kunnen verplaatsen
IT-beheerders kunnen de herlocatie van bedrijfsbestanden in door Intune beheerde apps bepalen. Ze kunnen bijvoorbeeld een beleid implementeren dat back-up-apps ervan weerhoudt back-apps van bedrijfsgegevens te maken naar de cloud.

### <a name="configure-clipboard-restrictions"></a>Beperkingen van Klembord configureren
IT-beheerders kunnen het gedrag van het Klembord in door Intune beheerde apps configureren. Ze kunnen bijvoorbeeld een beleid implementeren dat bepaalt dat eindgebruikers het Klembord niet kunnen gebruiken om gegevens uit een door Intune beheerde app te knippen/kopiëren en deze gegevens vervolgens naar een niet-beheerde, persoonlijke app te plakken.

### <a name="enforce-encryption-on-saved-data"></a>Versleuteling van opgeslagen gegevens afdwingen
IT-beheerders kunnen beleid afdwingen dat ervoor zorgt dat de gegevens die door de app op het apparaat worden opgeslagen, worden versleuteld.

### <a name="remotely-wipe-corporate-data"></a>Bedrijfsgegevens op afstand wissen
IT-beheerders kunnen op afstand bedrijfsgegevens wissen uit een met Intune beheerde app. Deze functie is op de identiteit gebaseerd en verwijdert alleen bestanden die betrekking hebben op de zakelijke identiteit van de eindgebruiker. Hiertoe vereist de functie deelname van de app. De app aangeven voor welke identiteit het wissen moet plaatsvinden op basis van de instellingen van de gebruiker. Als dergelijke instellingen niet door de gebruiker in de app zijn opgegeven, is het standaardgedrag om de toepassingsmap te wissen en de eindgebruiker te informeren dat de toegang is verwijderd.

### <a name="enforce-the-use-of-a-managed-browser"></a>Het gebruik van een beheerde browser afdwingen
IT-beheerders kunnen het gebruik van de Intune Managed Browser-app afdwingen voor het openen van koppelingen in door Intune beheerde apps. Dit zorgt ervoor dat de koppelingen die worden weergegeven in een bedrijfsomgeving, binnen het domein van door Intune beheerde apps worden gehouden.

### <a name="enforce-a-pin-policy"></a>Een pincodebeleid afdwingen
IT-beheerders kunnen een pincodebeleid afdwingen wanneer een door Intune beheerde app wordt gestart. Dit zorgt ervoor dat de gebruiker die de app start dezelfde gebruiker is die zich in het begin heeft aangemeld met een ingeschreven werk- of schoolaccount. Wanneer eindgebruikers hun pincode configureren, gebruikt Intune App SDK Azure Active Directory om te controleren of de referenties van eindgebruikers overeenkomen met het ingeschreven Intune account.

### <a name="require-users-to-enter-credentials-before-they-can-start-apps"></a>Vereisen dat gebruikers referenties invoeren voordat ze apps kunnen starten
IT-beheerders kunnen van gebruikers vereisen dat zijn referenties invoeren voordat ze een door Intune beheerde app kunnen starten. De Intune App SDK gebruikt Azure Active Directory om een single sign-on-ervaring te bieden waar de referenties, nadat deze eenmaal zijn opgegeven, opnieuw worden gebruikt voor toekomstige aanmeldingen. We bieden ook ondersteuning voor verificatie van oplossingen voor identiteitsbeheer [die zijn gefedereerd met Azure Active Directory](https://msdn.microsoft.com/library/azure/jj679342.aspx).

### <a name="check-device-health-and-compliance"></a>De status en compatibiliteit van apparaten controleren
IT-beheerders kunnen een status en de compatibiliteit van apparaten met het bedrijfsbeleid controleren voordat eindgebruikers toegang tot door Intune beheerde apps krijgen. Op het iOS-platform controleert dit beleid of het apparaat is gekraakt. Op het Android-platform controleert dit beleid of het apparaat is geroot.

### <a name="sdk-multi-identity-support"></a>SDK voor ondersteuning voor meerdere identiteiten
Ondersteuning voor meerdere identiteiten is een functie die co-existentie van door beleid beheerde (zakelijke) accounts en niet-beheerde (privé-)accounts in een enkele app mogelijk maakt.

Zo configureren veel gebruikers bijvoorbeeld zowel bedrijfs- als persoonlijke e‑mailaccounts in de Outlook-app voor iOS en Android. Wanneer een gebruiker zich toegang wil verschaffen tot gegevens in een bedrijfsaccount, moet de IT-beheerder erop kunnen vertrouwen dat het MAM-beleid wordt toegepast. Wanneer een gebruiker zich echter toegang wil verschaffen tot een persoonlijk e-mailaccount, moeten die gegevens buiten de controle van de IT-beheerder blijven. Dit wordt door Microsoft Intune bereikt door het beheerbeleid alleen in de app toe te passen. Deze functie voor het gebruik van meerdere identiteiten helpt bij het oplossen van het gegevensbeveiligingsprobleem waarmee organisaties worden geconfronteerd door apparaten en apps die ondersteuning bieden voor zowel privé- als accounts.

* **Hoe u meerdere identiteiten kunt ondersteunen**: met de Microsoft Intune App SDK-API's kunt u een User Principal Name (UPN) met specifieke gegevensbewerkingen opgeven, zoals klembordbewerkingen en bestandsbewerkingen. De SDK gebruikt de UPN om de aanroep te vergelijken met de UPN die voor het inschrijven van het apparaat bij de Microsoft Intune-service is gebruikt. Als de UPN’s overeenkomen, wordt de aanroep beschouwd als een aanroep van bedrijfsgegevens en worden de gegevens beveiligd; als de UPN’s niet overeenkomen, wordt de oproep beschouwd als een aanroep van privégegevens en worden de gegevens niet beveiligd.

### <a name="app-management-without-device-enrollment"></a>Appbeheer zonder apparaatinschrijving

>[!IMPORTANT]
>Het beheren van mobiele apps door Intune zonder dat een apparaat is ingeschreven, kan alleen met de Intune App SDK voor iOS. 


Veel gebruikers met privé-apparaten willen bedrijfsgegevens kunnen inzien en gebruiken zonder hun privé-apparaat te moeten inschrijven met Mobile Device Management-product (MDM-product). Omdat MDM-inschrijving algemeen beheer van het apparaat vereist, willen gebruikers de algemene controle over hun eigen privé-apparaat niet altijd aan hun bedrijf geven.

Met appbeheer zonder apparaatinschrijving kan de Microsoft Intune-service MAM-beleid rechtstreeks voor een app implementeren zonder voor de implementatie van het beleid afhankelijk te zijn van een MDM-kanaal. Omdat er geen MDM-kanaal is vereist, is MDM-inschrijving niet vereist.



<!--HONumber=Dec16_HO2-->


