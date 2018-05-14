---
title: App-toewijzingen opnemen en uitsluiten in Microsoft Intune
titlesuffix: ''
description: Lees meer over de manier waarop u Microsoft Intune kunt gebruiken om app-toewijzingen op te nemen en uit te sluiten.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: aa0b7396c22bd8bc832a6d845d4f40603013608a
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/28/2018
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>App-toewijzingen opnemen en uitsluiten in Microsoft Intune

In Intune kunt u bepalen wie toegang heeft tot een app door groepen gebruikers toe te wijzen die moeten worden opgenomen en uitgesloten. Voordat u groepen aan de app toewijst, moet u het toewijzingstype voor een app instellen. Het toewijzingstype maakt de app beschikbaar, vereist of verwijdert de app. 

Als u de beschikbaarheid van een app wilt instellen, kunt u app-toewijzingen opnemen en uitsluiten voor een groep gebruikers of apparaten door een combinatie te gebruiken van op te nemen en uit te sluiten groepstoewijzingen. Dit kan een handige mogelijkheid zijn wanneer u de app beschikbaar stelt door een grote groep op te nemen en vervolgens de geselecteerde gebruikers te beperken door ook een kleinere groep uit te sluiten. De kleinere groep kan als testgroep of uitvoerende groep fungeren. 

Wanneer u groepen uitsluit in een app-toewijzing, moet u alleen gebruikersgroepen of alleen apparaatgroepen uitsluiten. U kunt geen combinatie van gebruikersgroepen en apparaatgroepen uitsluiten. 

Intune houdt geen rekening met koppelingen van gebruikers aan apparaten bij het uitsluiten van groepen. Als u gebruikersgroepen opneemt en tegelijkertijd apparaatgroepen uitsluit, is het onwaarschijnlijk dat dit de gewenste resultaten oplevert. Opnemen heeft voorrang boven uitsluiten. Als u bijvoorbeeld een iOS-app op **Alle gebruikers** richt en **Alle iPads** uitsluit, is het nettoresultaat dat elke gebruiker die een iPad gebruikt, nog steeds toegang heeft tot de app. Als u de iOS-app echter op **Alle apparaten** richt en **Alle iPads** uitsluit, lukt de implementatie wel.  

> [!NOTE]
> Als u een groepstoewijzing voor een app instelt, wordt het type **Niet van toepassing** afgeschaft en vervangen door een functionaliteit voor het uitsluiten van groepen. 
>
> Intune biedt in de console de vooraf gemaakte groepen **Alle gebruikers** en **Alle apparaten**. De groepen hebben ingebouwde optimalisaties voor uw gemak. We raden u ten zeerste aan deze groepen te gebruiken om u op alle gebruikers en alle apparaten te richten in plaats van groepen Alle gebruikers en Alle apparaten die u mogelijk zelf hebt gemaakt.  
>
> Android Enterprise (voorheen bekend als Android for Work) biedt ondersteuning voor het opnemen en uitsluiten van groepen. U kunt de ingebouwde groepen **Alle gebruikers** en **Alle apparaten** gebruiken voor de Android Enterprise-app-toewijzing. 


## <a name="include-and-exclude-groups-when-assigning-apps"></a>Groepen opnemen en uitsluiten bij het toewijzen van apps 
U kunt een app toewijzen aan groepen met behulp van de toewijzing voor opnemen en uitsluiten:
1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer **Mobiele apps** in het menu **Intune**.
4. Selecteer **Apps** in het deelvenster **Mobiele apps**. De lijst met toegevoegde apps wordt weergegeven.
5. Selecteer de app die u wilt beheren. In een dashboard worden gegevens over de app weergegeven. 
6. Selecteer **Toewijzingen** in de sectie **Beheren** van het menu. 

    ![App-toewijzingen van Intune](./media/apps-inc-exl-01.png)
7. Selecteer **Groep toevoegen** om de groepen van gebruikers aan wie de app is toegewezen toe te voegen. 
8. Selecteer een **Toewijzingstype** uit de beschikbare toewijzingstypen in het deelvenster **Groep toevoegen**.
9. Selecteer **Beschikbaar met of zonder inschrijving** als het toewijzingstype.

    ![App-toewijzingen van Intune - Groep toevoegen](./media/apps-inc-exl-02.png)
10. Selecteer **Opgenomen groepen** om de groep gebruikers te selecteren voor wie u deze app beschikbaar wilt maken.

    > [!NOTE]
    > Wanneer u een groep toevoegt terwijl er al een andere groep is opgenomen voor een gegeven toewijzingstype, wordt deze groep vooraf geselecteerd. Dit kan niet worden gewijzigd voor andere toewijzingstypen voor opnemen. De groep die is gebruikt, kan niet worden gebruikt als een opgenomen groep.

11. Selecteer **Ja** om deze app beschikbaar maken voor alle gebruikers.

    ![App-toewijzingen van Intune - Groepen opnemen](./media/apps-inc-exl-03.png)
12. Selecteer **OK** om de groep op te nemen die moet worden ingesteld.
13. Selecteer **Uitgesloten groepen** om de groep gebruikers te selecteren voor wie u deze app niet beschikbaar wilt maken. 
14. Selecteer de groepen die moeten worden uitgesloten. Hierdoor is deze app niet meer beschikbaar voor deze groepen.

    ![App-toewijzingen van Intune - Groepen uitsluiten](./media/apps-inc-exl-04.png)
15. Selecteer **Selecteren** om de selectie van groepen te voltooien.
16. Selecteer **OK** in het deelvenster **Groep toevoegen**. De app-lijst **Toewijzingen** wordt weergegeven.
17. Klik op **Opslaan** om uw groepstoewijzingen te activeren voor de app.

Als u groepstoewijzingen maakt, kunnen groepen die al zijn toegewezen, niet worden gewijzigd. Als u een groep wilt selecteren die momenteel niet beschikbaar is, verwijdert u eerst de app uit de lijst met toegewezen apps. 

Als u toewijzingen wilt bewerken, selecteert u in de lijst **Toewijzingen** in de app de rij met de specifieke toewijzing die u wilt wijzigen. U kunt een toewijzing ook verwijderen door aan het eind van een rij op het weglatingsteken (**...**) te klikken en **Verwijderen** te selecteren. Groepeer op **Toewijzingstype** of op **Opgenomen/uitgesloten** om de weergave van de lijst **Toewijzingen** te wijzigen.

![App-toewijzingen van Intune - Voltooid](./media/apps-inc-exl-05.png)

## <a name="next-steps"></a>Volgende stappen

- Zie de [Microsoft Intune-blog](https://aka.ms/new_app_assignment_process) voor meer informatie over het opnemen en uitsluiten van groepstoewijzingen voor apps.
- Meer informatie over hoe u [app-gegevens en -toewijzingen kunt controleren](apps-monitor.md).
