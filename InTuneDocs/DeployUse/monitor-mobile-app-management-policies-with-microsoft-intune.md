<<<<<<< HEAD
---
title: MAM-beleid bewaken met Microsoft Intune | Microsoft Intune
description: U kunt bekijken hoeveel gebruikers het beleid hebben en hier op inzoomen om meer inzicht te verkrijgen.
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 07/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: bc68a13b8d5694908cd00e5e615f81f6e15cfe22

||||||| merged common ancestors
---
title: MAM-beleid bewaken met Microsoft Intune | Microsoft Intune
description: U kunt bekijken hoeveel gebruikers het beleid hebben en hier op inzoomen om meer inzicht te verkrijgen.
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 07/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: bc68a13b8d5694908cd00e5e615f81f6e15cfe22

=======
---
title: MAM-beleid bewaken met Microsoft Intune | Microsoft Intune
description: U kunt bekijken hoeveel gebruikers het beleid hebben en hier op inzoomen om meer inzicht te verkrijgen.
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: aec3b198ef6246cfc148eee09796f264e8bd037a
ms.openlocfilehash: 05250ba1165b0dfc13757bb2a5ebe3562f8bea63

>>>>>>> 0aaa8317d010412c0781f3e79ff4b889d024dce5

---
<<<<<<< HEAD

# Mobile App Management-beleid bewaken met Microsoft Intune
Nadat u een MAM-beleid hebt geconfigureerd en toegepast op de gebruikers, kunt u de nalevingsstatus in [Azure Portal](https://portal.azure.com) bewaken. De Azure-portal bevat informatie over de gebruikers die door het beleid worden beïnvloed, de nalevingsstatus en eventuele problemen die uw eindgebruikers ondervinden.
## Samenvattingsweergave
Op het tabblad **Intune Mobile Application Management** ziet u een samenvatting van de nalevingsstatus, zoals hieronder wordt beschreven:
||||||| merged common ancestors

# Mobile App Management-beleid bewaken met Microsoft Intune
Nadat u een MAM-beleid hebt geconfigureerd en toegepast op de gebruikers, kunt u de nalevingsstatus in [Azure Portal](https://portal.azure.com) bewaken. De Azure-portal bevat informatie over de gebruikers die door het beleid worden beïnvloed, de nalevingsstatus en eventuele problemen die uw eindgebruikers ondervinden.
## Samenvattingsweergave
Op het tabblad **Intune Mobile Application Management** ziet u een samenvatting van de nalevingsstatus, zoals hieronder wordt beschreven:
=======

# <a name="monitor-mobile-app-management-policies-with-microsoft-intune"></a>Mobile App Management-beleid bewaken met Microsoft Intune
Nadat u een MAM-beleid (Mobile App Management) hebt ingesteld en toegepast op de gebruikers, kunt u de nalevingsstatus in [Azure Portal](https://portal.azure.com) bewaken. Azure Portal bevat informatie over de gebruikers die door het beleid worden beïnvloed, de nalevingsstatus en eventuele problemen die uw gebruikers ondervinden.
## <a name="summary-view"></a>Samenvattingsweergave
Op de blade **Intune Mobile Application Management** ziet u een samenvatting van de nalevingsstatus:
>>>>>>> 0aaa8317d010412c0781f3e79ff4b889d024dce5


![De tegel Samenvatting op het tabblad Intune Mobile Application Management](../media/mam-azure-portal-user-status-summary.png)

-   **Gebruikers:** het totale aantal gebruikers in uw bedrijf dat gebruikmaakt van de apps die zijn gekoppeld aan het beleid.

-   **BEHEERD DOOR BELEID**: het aantal gebruikers dat ten minste een van de apps in de werkcontext heeft gebruikt.

-   **GEEN BELEID:** het aantal gebruikers dat gebruikmaakt van de apps die zijn gekoppeld aan het beleid, maar op wie het beleid niet is gericht. U kunt overwegen deze gebruikers toe te voegen aan het beleid.

- **Gemarkeerde gebruikers:** het aantal gebruikers dat problemen ondervindt. Momenteel worden onder **Gemarkeerde gebruikers** alleen gebruikers met gekraakte apparaten gerapporteerd.


## <a name="detailed-view"></a>Detailweergave
U kunt de gedetailleerde weergave van de samenvatting openen door de tegel **Gebruikersstatus** en de tegel **Gemarkeerde gebruikers** te kiezen.

### <a name="user-status"></a>Gebruikersstatus
U kunt zoeken naar een afzonderlijke gebruiker en de nalevingsstatus voor deze gebruiker controleren. De blade **App-rapportage** bevat de volgende informatie voor de geselecteerde gebruiker:
- Apparaten die zijn gekoppeld aan het gebruikersaccount

- Apps met een MAM-beleid op het apparaat

- Status:

  - **Ingeschakeld**: het beleid is geïmplementeerd voor de gebruiker en de app is minstens eenmaal in de werkcontext gebruikt.

  - **Niet ingeschakeld**: het beleid is geïmplementeerd voor de gebruiker, maar de app is sindsdien niet gebruikt in de werkcontext.

>[!NOTE]
> Als het MAM-beleid niet op de gebruiker waarnaar u hebt gezocht is toegepast, wordt in een bericht gemeld dat de gebruiker niet in aanmerking komt voor een app-beleid.

Ga als volgt te werk om de rapportage voor een gebruiker te bekijken:

1.  Als u een gebruiker wilt selecteren, kiest u de tegel **Samenvatting** of kiest u de optie **APP-RAPPORTAGE DOOR DE GEBRUIKER** op de blade **Instellingen**:

    ![De optie App-rapportage op de blade Instellingen](../media/mam-azure-portal-app-reporting-by-user-settings-blade.png)

2. Kies op de geopende blade **App-rapportage** de optie **Gebruiker selecteren** om een Azure Active Directory-gebruiker te zoeken.

    ![De gebruikersoptie op de blade App-rapportage selecteren](../media/mam-azure-portal-app-reporting-select-user.png)

3. Selecteer de gebruiker uit de lijst. U ziet de details van de nalevingsstatus voor die gebruiker.

    ![Details van app-rapportage](../media/mam-azure-portal-app-reporting-by-user.png)

### <a name="flagged-users"></a>Gemarkeerde gebruikers
De gedetailleerde weergave bevat het foutbericht, de app die werd geopend toen de fout is opgetreden, het platform van het apparaat en een tijdstempel.  

### <a name="see-also"></a>Zie tevens
[Gegevensoverdracht tussen iOS-apps beheren](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door MAM-beleid](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door MAM-beleid](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)



<!--HONumber=Oct16_HO5-->


