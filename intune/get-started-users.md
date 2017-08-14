---
title: Aan de slag met gebruikers
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e711f32ebd77a83b17e6db468f8cb23a409c8d31
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/03/2017
---
# <a name="get-started-with-users"></a>Aan de slag met gebruikers

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Azure AD Directory verzorgt het beheer van groepen objecten van uw organisatie, zoals apparaten en apps, evenals groepen gebruikers. U kunt gebruikers of apparaten opnemen in groepen in plaats van elk apparaat afzonderlijk te beheren. Op deze manier kunt u eenvoudig apps en instellingen toewijzen aan grote aantallen gebruikers en apparaten.

## <a name="how-do-i-create-a-user"></a>Hoe maak ik een gebruiker?

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Gebruik **Resources zoeken** om te zoeken naar **Gebruikers en groepen**.
3. Als u de blade **Gebruikers en groepen** hebt geopend, selecteert u **Alle gebruikers** en daarna **+ Nieuwe gebruiker**.
4. Voer gegevens in voor de gebruiker, bijvoorbeeld bij **Naam** en **Gebruikersnaam**. Het domeinnaamgedeelte van de gebruikersnaam moet bestaan uit de naam van het oorspronkelijke standaarddomein 'contoso.onmicrosoft.com' of uit een geverifieerde, niet-gefedereerde domeinnaam zoals 'contoso.com'.
5. Kies onder **Groepen** de testgroep waaraan u de gebruiker wilt toevoegen.
6. Sla het automatisch gegenereerde gebruikerswachtwoord op, zodat u dit kunt gebruiken om u aan te melden bij een testapparaat. U moet dit wachtwoord aan uw gebruikers geven, zodat ze het kunnen wijzigen in een normaal wachtwoord dat ze makkelijk kunnen onthouden.
7. Selecteer **Maken** op de blade **Gebruiker**.

## <a name="assigning-licenses-to-users"></a>Licenties toewijzen aan gebruikers

Nadat u een gebruiker hebt gemaakt, moet u de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) gebruiken om een Intune-licentie toe te wijzen aan die gebruiker. Zonder een licentie kan het apparaat van de gebruiker namelijk niet worden ingeschreven voor beheer.

1. Meld u aan bij de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) met dezelfde referenties die u hebt gebruikt om u aan te melden bij Intune.
2. Selecteer **Gebruikers** > **Actieve gebruikers**, en selecteer vervolgens de gebruiker die u eerder hebt gemaakt.
3. U moet mogelijk even wachten tot alle gegevens van de gebruiker zijn geladen. Als dat is voltooid, selecteert u **Bewerken** bij **Productlicenties** voor de gebruiker.
4. Wijs een**** locatie toe aan de gebruiker en zet Intune op **aan**.

 > [!NOTE]
 > Er wordt nu een van uw licenties gebruikt voor deze gebruiker. Als u de productieomgeving gebruikt, kunt u de toewijzing van deze licentie later uitschakelen om de licentie te gebruiken voor een echte gebruiker.

5. Selecteer **Opslaan**.
