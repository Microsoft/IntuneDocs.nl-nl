---
title: Koppeling tussen gebruiker en apparaat voor Windows-pc&quot;s beheren | Microsoft Intune
description: Een gebruiker aan een Windows-pc koppelen die wordt beheerd door Intune.
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c99d63-c312-442a-8a71-de1b10fcd39b
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 39fec6a2ea8d8c0f4b6ea1460c76a8a6c652d614


---

# <a name="manage-user-device-linking-for-windows-pcs"></a>Koppeling tussen gebruiker en apparaat voor Windows-pc's beheren
Voordat u software voor een gebruiker kunt implementeren, moet u de gebruiker aan een computer koppelen. U kunt een gebruiker aan meerdere computers koppelen, maar elke computer kan aan slechts één gebruiker worden gekoppeld. Gebruikers worden automatisch gekoppeld aan computers die ze registreren bij Intune met behulp van de bedrijfsportal.

Een gebruiker aan een computer koppelen:

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) de optie **Groepen**&gt;**Alle apparaten** (of een andere groep die de computer bevat die u aan een gebruiker wilt koppelen).

2.  Selecteer de computer die u aan een gebruiker wilt koppelen en kies vervolgens **Gebruiker koppelen**.

    In het dialoogvenster **Gebruiker koppelen** wordt een lijst met beschikbare gebruikers weergegeven met hun weergavenaam, gebruikers-id en het aantal computers waaraan elke gebruiker momenteel is gekoppeld. Als een gebruiker al aan de geselecteerde computer is gekoppeld, worden de naam van die gebruiker en de gebruikers-id weergegeven onder **Huidige gebruiker**. Als de computer niet aan een gebruiker is gekoppeld, wordt **Geen gebruiker** weergegeven onder **Huidige gebruiker**.

3.  Voer een van de volgende handelingen uit:

    -   Als u de computer gekoppeld wilt laten aan de huidige gebruiker, indien aanwezig, kiest u **Annuleren**.

    -   Als u de koppeling met de huidige gebruiker, indien aanwezig, wilt verwijderen, kiest u **Koppeling verwijderen**&gt;**OK**.

    -   Als u de computer aan een nieuwe gebruiker wilt koppelen, selecteert u een gebruiker in de lijst **Alle gebruikers** . Controleer of de gebruikersgegevens juist zijn en kies vervolgens **OK**.

> [!TIP]
> Als u de mogelijkheden van eindgebruikers om zichzelf aan computers te koppelen wilt beperken, schakelt u de optie **Koppelingen tussen gebruikers en computers beperken** in het beleid voor **Instellingen Microsoft Intune-agent** in.

### <a name="see-also"></a>Zie ook

[Algemene beheertaken voor Windows-pc's met de Intune-softwareclient](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)


<!--HONumber=Nov16_HO4-->


