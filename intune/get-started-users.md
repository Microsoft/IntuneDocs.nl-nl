---
title: Aan de slag met het beheren van gebruikers
titlesuffix: Microsoft Intune
description: Voeg een gebruiker toe aan Intune en wijs hem/haar een licentie toe zodat hij/zij op mobiele apparaten toegang heeft tot bedrijfsresources.
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4e06b335c03caee0bd997748f9c48ed78d7d379b
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
# <a name="get-started-managing-users"></a>Aan de slag met het beheren van gebruikers

Denk aan alle andere personen in uw organisatie. Iedereen die zakelijke gegevens gebruikt, heeft een gebruiker nodig om toegang ertoe in Intune te beheren.

## <a name="how-do-i-create-a-user"></a>Hoe maak ik een gebruiker?

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Gebruik **Resources zoeken** om te zoeken naar **Intune**.
3. Selecteer nadat u de blade **Microsoft Intune** hebt geopend de optie **Gebruikers**. Selecteer op de pagina **Alle gebruikers** de optie **+ Nieuwe gebruiker**.
4. Voer gegevens in voor de gebruiker, bijvoorbeeld bij **Naam** en **Gebruikersnaam**. Het domeinnaamgedeelte van de gebruikersnaam moet bestaan uit de naam van het oorspronkelijke standaarddomein 'contoso.onmicrosoft.com' of uit een geverifieerde, niet-gefedereerde domeinnaam zoals 'contoso.com'.
5. Kies onder **Groepen** de testgroep waaraan u de gebruiker wilt toevoegen.
6. Sla het automatisch gegenereerde gebruikerswachtwoord op, zodat u dit kunt gebruiken om u aan te melden bij een testapparaat. U moet dit wachtwoord aan uw gebruikers geven, zodat ze het kunnen wijzigen in een normaal wachtwoord dat ze makkelijk kunnen onthouden.
7. Selecteer **Maken** op de blade **Gebruiker**.

## <a name="assigning-licenses-to-users"></a>Licenties toewijzen aan gebruikers

Nadat u een gebruiker hebt gemaakt, moet u de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) gebruiken om een Intune-licentie toe te wijzen aan die gebruiker. Zonder een licentie kan het apparaat van de gebruiker namelijk niet worden ingeschreven voor beheer.

1. Meld u aan bij de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) met dezelfde referenties die u hebt gebruikt om u aan te melden bij Intune.
2. Selecteer **Gebruikers** > **Actieve gebruikers**, en selecteer vervolgens de gebruiker die u eerder hebt gemaakt.
3. U moet mogelijk even wachten tot alle gegevens van de gebruiker zijn geladen. Als dat is voltooid, selecteert u **Bewerken** bij **Productlicenties** voor de gebruiker.
4. Wijs een **locatie** toe aan de gebruiker en zet Intune op **aan**.

 > [!NOTE]
 > Er wordt nu een van uw licenties gebruikt voor deze gebruiker. Als u de productieomgeving gebruikt, kunt u de toewijzing van deze licentie later uitschakelen om de licentie te gebruiken voor een echte gebruiker.

5. Selecteer **Opslaan**.

## <a name="next-steps"></a>Volgende stappen

[Aan de slag met groepen](get-started-groups.md) - Deel gebruikers in groepen in om het beleid en de apps waar ze toegang toe hebben gemakkelijker te beheren.
