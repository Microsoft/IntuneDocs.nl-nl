---
title: Aan de slag met het beheren van gebruikers
titlesuffix: Microsoft Intune
description: Voeg een gebruiker toe aan Intune en wijs hem/haar een licentie toe zodat hij/zij op mobiele apparaten toegang heeft tot bedrijfsresources.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4c401110799202bd0c8aafc62bfda6d8827247be
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57234750"
---
# <a name="get-started-managing-users"></a>Aan de slag met het beheren van gebruikers

Denk aan alle andere personen in uw organisatie. Iedereen die zakelijke gegevens gebruikt, heeft een gebruiker nodig om toegang ertoe in Intune te beheren.

## <a name="how-do-i-create-a-user"></a>Hoe maak ik een gebruiker?

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer **Gebruikers** nadat u het deelvenster **Microsoft Intune** hebt geopend. Selecteer op de pagina **Alle gebruikers** de optie **+ Nieuwe gebruiker**.
4. Voer gegevens in voor de gebruiker, bijvoorbeeld bij **Naam** en **Gebruikersnaam**. Het domeinnaamgedeelte van de gebruikersnaam moet een van de volgende domeinen zijn:
    - de oorspronkelijke standaarddomeinnaam contoso.onmicrosoft.com of
    - een geverifieerde, niet-gefedereerde domeinnaam zoals contoso.com.
5. Kies onder **Groepen** de [groep](get-started-groups.md) waaraan u de gebruiker wilt toevoegen.
6. Sla het automatisch gegenereerde gebruikerswachtwoord op, zodat u dit kunt gebruiken om u aan te melden bij een testapparaat. U moet dit wachtwoord aan uw gebruikers geven, zodat ze het kunnen wijzigen in een normaal wachtwoord dat ze makkelijk kunnen onthouden.
7. In het deelvenster **Gebruiker** selecteert u **Maken**.

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
