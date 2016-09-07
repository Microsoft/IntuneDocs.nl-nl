---
title: Apparaten categoriseren met apparaatgroeptoewijzing | Microsoft Intune
description: "Gebruik apparaatgroeptoewijzing van Microsoft Intune om apparaten te groeperen in categorieën die u definieert, zodat het voor u eenvoudiger wordt om die apparaten te beheren."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e
ms.reviewer: sumitp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 727d28cff074124b5401f6c2931f87df3a9d2d23
ms.openlocfilehash: 7b1c6f0e380c03d048686462682fc1cee85b7cfa


---

# Apparaten categoriseren met apparaatgroeptoewijzing in Microsoft Intune
Gebruik **apparaatgroeptoewijzing** van Microsoft Intune om apparaten te groeperen in categorieën (die u definieert), zodat het voor u eenvoudiger wordt om die apparaten te beheren. 

Voor apparaatgroeptoewijzing wordt gebruikgemaakt van de volgende werkstroom:
1. U maakt Intune-apparaatgroepen voor elke categorie die u wilt gebruiken.
2. U configureert regels voor apparaatgroeptoewijzing waarmee de categorie die u kiest, wordt toegewezen aan de gemaakte apparaatgroep.
3. Wanneer eindgebruikers hun apparaat inschrijven, moeten ze een categorie kiezen uit de categorieën die u hebt geconfigureerd. Wanneer ze een keuze hebben gemaakt, wordt hun apparaat automatisch toegevoegd aan de bijbehorende apparaatgroep die u hebt gemaakt.
4. U kunt deze apparaatgroepen vervolgens ook gebruiken bij het implementeren van beleid en apps.

Voorbeelden van categorieën kunnen zijn:
* Persoonlijk
* Verkooppuntapparaat
* Demonstratieapparaat
* Sales
* Boekhouding
* Manager

U kunt echter alle categorieën configureren die u wilt.

## Apparaatgroeptoewijzing configureren
1. Maak een Intune-apparaatgroep voor elke apparaatcategorie die u wilt gebruiken. Zie [Groepen gebruiken voor het beheren van gebruikers en apparaten met Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md) voor informatie over het maken van groepen.
2. Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Beheer**.
3. In de werkruimte **Beheer** vouwt u **Mobile Device Management** uit en kiest u vervolgens **Apparaatgroeptoewijzing**.
4. Op de pagina **Apparaatgroeptoewijzing** schakelt u apparaatgroeptoewijzing in.
5. Kies **Toevoegen** om een nieuwe toewijzingsregel te maken.
6. In het dialoogvenster **Regel voor apparaatgroeptoewijzing toevoegen** voert u de naam in van de categorie die u wilt maken. Kies daarna uit de vervolgkeuzelijst de apparaatverzameling waar u deze categorie aan wilt toewijzen. Kies **Toevoegen** wanneer u klaar bent.
7. Wanneer u de categorieën en groepen hebt toegevoegd, kiest u **Opslaan**.

Wanneer gebruikers nu hun apparaat inschrijven, krijgen ze een lijst te zien van de categorieën die u hebt geconfigureerd. Wanneer ze een categorie hebben gekozen en het inschrijven voltooien, wordt hun apparaat toegevoegd aan de apparaatgroep die overeenkomt met de gekozen categorie.

### Zie tevens
[Groepen gebruiken voor het beheren van gebruikers en apparaten met Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)


<!--HONumber=Aug16_HO5-->


