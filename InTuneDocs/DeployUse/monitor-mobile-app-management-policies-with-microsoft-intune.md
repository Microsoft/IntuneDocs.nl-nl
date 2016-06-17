---
# required metadata

title: Mobile App Management-beleid bewaken met Microsoft Intune | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Mobile App Management-beleid bewaken met Microsoft Intune
Nadat u MAM-beleid hebt geconfigureerd en toegepast op de gebruikers, kunt u de nalevingsstatus bewaken in de [Azure-portal](https://portal.azure.com). De Azure-portal bevat informatie over de gebruikers die door het beleid worden beïnvloed, de nalevingsstatus en eventuele problemen die uw eindgebruikers ondervinden.
## Samenvattingsweergave
Op de blade **Intune Mobile Application Management** ziet u een samenvatting van de nalevingsstatus, zoals hieronder wordt beschreven:


![De tegel Samenvatting op de blade Intune Mobile Application Management](../media/mam-azure-portal-user-status-summary.png)

-   **GEBRUIKERS:** het totale aantal gebruikers in uw bedrijf dat gebruikmaakt van de apps die zijn gekoppeld aan het beleid.

-   **BEHEERD DOOR BELEID**: het aantal gebruikers dat ten minste één van de apps in een werkcontext heeft gebruikt.

-   **GEEN BELEID:** het aantal gebruikers dat gebruikmaakt van de apps die zijn gekoppeld aan het beleid, maar op wie het beleid niet is gericht.  U kunt overwegen deze gebruikers toe te voegen aan uw beleid.

- **Gemarkeerde gebruikers:** het aantal gebruikers dat problemen ondervindt. Momenteel worden onder **Gemarkeerde gebruikers** alleen gebruikers met apparaten waarop jailbreaking is uitgevoerd, gerapporteerd.


## Detailweergave
U kunt de gedetailleerde weergave van de samenvatting openen door te klikken op de tegel **Gebruikersstatus** en de tegel **Gemarkeerde gebruikers**.

### Gebruikersstatus
U kunt zoeken naar een afzonderlijke gebruiker en de nalevingsstatus voor deze gebruiker bekijken. De blade **App-rapportage** bevat de volgende informatie voor de geselecteerde gebruiker:
- Appara(a)t(en) die zijn gekoppeld aan het gebruikersaccount
- App(s) met MAM-beleid op het apparaat
- Status:

  **Ingecheckt:** dit betekent dat het beleid is geïmplementeerd voor de gebruiker en de app minstens eenmaal in een werkcontext is gebruikt.

  **Niet ingecheckt**: geeft aan dat het beleid is geïmplementeerd voor de gebruiker, maar dat de app sindsdien niet is gebruikt in een werkcontext.

Ga als volgt te werk om de rapportage voor een gebruiker te bekijken:

**Stap 1:** selecteer de gewenste gebruiker. Klik hiertoe op de tegel Samenvatting of kies de optie **APP-RAPPORTAGE DOOR GEBRUIKER** op de blade **Instellingen**, zoals hieronder wordt weergegeven:

![De optie App-rapportage op de blade Instellingen](../media/mam-azure-portal-app-reporting-by-user-settings-blade.png)

**Stap 2:** de blade **App-rapportage** wordt nu geopend. Kies **Gebruiker selecteren** om een Azure Active Directory-gebruiker te zoeken.

![De optie Gebruiker selecteren op de blade App-rapportage](../media/mam-azure-portal-app-reporting-select-user.png)

**Stap 3:** nadat u een gebruiker in de lijst hebt geselecteerd, ziet u de details van de nalevingsstatus voor die gebruiker.

![Details van app-rapportage](../media/mam-azure-portal-app-reporting-by-user.png)
### Gemarkeerde gebruikers
De gedetailleerde weergave bevat het foutbericht, de app die werd geopend toen de fout is opgetreden, het platform van het apparaat en een tijdstempel.  

### Zie ook
[Gegevensoverdracht tussen iOS-apps beheren](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

[Ervaring van eindgebruikers voor apps die geschikt zijn voor MAM](end-user-experience-for-mam-enabled-apps-with-microsoft-intune.md)


<!--HONumber=May16_HO3-->


