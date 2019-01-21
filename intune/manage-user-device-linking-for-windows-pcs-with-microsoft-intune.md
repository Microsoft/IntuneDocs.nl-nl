---
title: Koppeling tussen gebruiker en apparaat voor Windows-pc's beheren
titlesuffix: Microsoft Intune
description: Een gebruiker aan een Windows-pc koppelen die wordt beheerd door Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 53c99d63-c312-442a-8a71-de1b10fcd39b
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.openlocfilehash: 9d6c894e30b050ec6e824e1e77d0c476d4dc15bc
ms.sourcegitcommit: 2ff19c09a43c63556d082966727674120b516d10
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149624"
---
# <a name="manage-user-device-linking-for-windows-pcs"></a>Koppeling tussen gebruiker en apparaat voor Windows-pc's beheren

[!INCLUDE [classic-portal](includes/classic-portal.md)]

De informatie in dit onderwerp geldt alleen voor Windows-desktops die u als pc's beheert met behulp van de Intune-softwareclient. 

Voordat u software voor een gebruiker kunt implementeren, moet u de gebruiker aan een pc koppelen. U kunt een gebruiker aan meerdere pc's koppelen, maar elke pc kan aan slechts één gebruiker worden gekoppeld. Gebruikers worden automatisch gekoppeld aan pc's die ze registreren bij Intune met behulp van de bedrijfsportal.

Een gebruiker aan een pc koppelen:

1. Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) de optie **Groepen**&gt;**Alle apparaten** (of een andere groep die de pc bevat die u aan een gebruiker wilt koppelen).

2. Selecteer de pc die u aan een gebruiker wilt koppelen en kies **Gebruiker koppelen**.

   In het dialoogvenster **Gebruiker koppelen** wordt een lijst met beschikbare gebruikers weergegeven met hun weergavenaam, gebruikers-id en het aantal pc's waaraan elke gebruiker momenteel is gekoppeld. Als een gebruiker al aan de geselecteerde pc is gekoppeld, worden de naam van die gebruiker en de gebruikers-id weergegeven onder **Huidige gebruiker**. Als de pc niet aan een gebruiker is gekoppeld, wordt **Geen gebruiker** weergegeven onder **Huidige gebruiker**.

3. Voer een van de volgende handelingen uit:

   - Als u de pc gekoppeld wilt laten aan de huidige gebruiker (als er een is), kiest u **Annuleren**.

   - Als u de koppeling met de huidige gebruiker (als er een is) wilt verwijderen, kiest u <strong>Koppeling verwijderen**&gt;** OK</strong>.

   - Als u de pc aan een nieuwe gebruiker wilt koppelen, selecteert u een gebruiker in de lijst **Alle gebruikers**. Controleer of de gebruikersgegevens juist zijn en kies vervolgens **OK**.

> [!TIP]
> Als u de mogelijkheden van eindgebruikers om zichzelf aan pc's te koppelen wilt beperken, schakelt u de optie **Koppelingen tussen gebruikers en computers beperken** in het beleid voor **Instellingen Microsoft Intune-agent** in.

### <a name="see-also"></a>Zie tevens

[Algemene beheertaken voor Windows-pc's met de Intune-softwareclient](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
