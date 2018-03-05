---
title: App-toewijzingen opnemen en uitsluiten
titlesuffix: Microsoft Intune
description: Lees meer over de manier waarop u Intune kunt gebruiken om app-toewijzingen op te nemen en uit te sluiten.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/29/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ca1f45c3203645dc474fcb6411a8ad598ff83714
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/03/2018
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>App-toewijzingen opnemen en uitsluiten in Microsoft Intune

Met Intune kunt u bepalen wie toegang heeft tot een app door de groepen die moeten worden opgenomen en uitgesloten toe te wijzen. U kunt app-toewijzingen opnemen en uitsluiten voor een groep gebruikers of apparaten door een combinatie te gebruiken van op te nemen en uit te sluiten groepstoewijzingen. Na het selecteren van een app kunt u kiezen hoe de app wordt toegewezen. Dit kan een handige mogelijkheid zijn wanneer u de app beschikbaar stelt door een grote groep op te nemen en vervolgens de geselecteerde gebruikers te beperken door ook een kleinere groep uit te sluiten. De kleinere groep kan als testgroep of uitvoerende groep fungeren. 

Wanneer u groepen uitsluit van een toewijzing, moet u alleen groepen gebruikers of alleen groepen apparaten uitsluiten, niet een combinatie van groepen. Intune houdt geen rekening met eventuele koppelingen van gebruikers aan apparaten bij het uitsluiten van groepen. Als u gebruikersgroepen opneemt en tegelijkertijd apparaatgroepen uitsluit, is het onwaarschijnlijk dat dit de gewenste resultaten oplevert omdat insluiting een hogere prioriteit heeft dan uitsluiting. Als u bijvoorbeeld een iOS-app op **Alle gebruikers** richt en **Alle iPads** uitsluit, is het nettoresultaat dat elke gebruiker met een iPad nog steeds toegang tot de app heeft. Als u de iOS-app echter op **Alle apparaten** richt en **Alle iPads** uitsluit, is de implementatie wel succesvol.  

>[!NOTE]
>Bij het instellen van de groepstoewijzing voor een app wordt het type **Niet van toepassing** afgeschaft en vervangen door een functionaliteit voor het uitsluiten van groepen. 
>
>Intune biedt vooraf gemaakte de groepen **Alle gebruikers** en **Alle apparaten** in de console met handige, ingebouwde optimalisaties. We raden u ten zeerste aan deze groepen te gebruiken om u op alle gebruikers en alle apparaten te richten in plaats van de groepen ‘Alle gebruikers’ en ‘Alle apparaten’ die u mogelijk zelf hebt gemaakt.  

## <a name="including-and-excluding-groups-when-assigning-apps"></a>Groepen opnemen en uitsluiten bij het toewijzen van apps 
U kunt als volgt een app aan groepen toewijzen met behulp van de toewijzing voor opnemen en uitsluiten:
1. Op de blade Microsoft Intune selecteert u **Mobiele apps**.
2. Op de blade **Mobiele apps** selecteert u **Apps**. De lijst met toegevoegde apps wordt weergegeven.
3. Selecteer de app die u wilt beheren. Er wordt een dashboard weergegeven die betrekking heeft op de app. 
4. Selecteer **Toewijzingen** onder de sectie **Beheren**. 

    ![App-toewijzingen van Intune](./media/apps-inc-exl-01.png)
5. Selecteer **Groep toevoegen** om de groepen van gebruikers aan wie de app is toegewezen toe te voegen. 
6. Selecteer een **Toewijzingstype** uit de beschikbare toewijzingstypen op de blade **Groep toevoegen**.
7. Selecteer **Beschikbaar met of zonder inschrijving** als het toewijzingstype.

    ![App-toewijzingen van Intune - Groep toevoegen](./media/apps-inc-exl-02.png)
8. Selecteer **Opgenomen groepen** om de groep gebruikers voor wie u deze app beschikbaar wilt maken te selecteren.

    >[!NOTE]
    >Wanneer u een groep toevoegt en als er al een andere groep is opgenomen voor een gegeven toewijzingstype, wordt deze groep vooraf geselecteerd. Dit kan niet worden gewijzigd voor andere toewijzingstypen voor opnemen. De groep die is gebruikt, kan daarom niet als een opgenomen groep worden gebruikt.

9. Selecteer **Ja** om deze app beschikbaar maken voor alle gebruikers.

    ![App-toewijzingen van Intune - Groepen opnemen](./media/apps-inc-exl-03.png)
10. Klik op **OK** om de op te nemen groep in te stellen.
11. Selecteer **Uitgesloten groepen** om de groep gebruikers voor wie u deze app niet beschikbaar wilt maken te selecteren. 
12. Selecteer de groepen die moeten worden uitgesloten. Hierdoor wordt de app niet beschikbaar.

    ![App-toewijzingen van Intune - Groepen uitsluiten](./media/apps-inc-exl-04.png)
13. Klik op **Selecteren** om de selectie van groepen te voltooien.
14. Klik op **OK** op de blade **Groep toevoegen**. De lijst **Toewijzingen** van de app wordt weergegeven.
15. Klik op **Opslaan** om uw groepstoewijzingen te activeren voor de app.

Wanneer u groepstoewijzingen maakt, worden groepen die al zijn toegewezen of geselecteerd, uitgeschakeld. Als u een momenteel uitgeschakelde groep wilt selecteren, moet u deze verwijderen uit de lijst Toegewezen van de app. U kunt toewijzingen uit de lijst **Toewijzingen** van de app bewerken door de rij met de specifieke toewijzing die u wilt wijzigen te selecteren. Daarnaast kunt u een toewijzing verwijderen door aan het eind van een rij op het weglatingsteken (...) te klikken en **Verwijderen** te selecteren. Bovendien kunt u de weergave van de lijst **Toewijzingen** wijzigen door te groeperen op **Toewijzingstype** of op **Opgenomen/uitgesloten**.

![App-toewijzingen van Intune - Voltooid](./media/apps-inc-exl-05.png)

## <a name="next-steps"></a>Volgende stappen

* Zie de [blog van Microsoft Intune](https://aka.ms/new_app_assignment_process) voor meer informatie over het opnemen en uitsluiten van groepstoewijzingen voor apps.
