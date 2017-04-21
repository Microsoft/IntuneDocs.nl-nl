---
title: Veelgestelde vragen over MAM en app-beveiliging
description: In dit artikel vindt u antwoorden op enkele veelgestelde vragen over Intune Mobile Application Management (MAM) en de bescherming van apps met Intune.
keywords: 
author: oydang
ms.author: oydang
manager: mtillman
ms.date: 01/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 149def73-9d08-494b-97b7-4ba1572f0623
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: aea41c86e1fe784d6234f4ff90e299632b2a6d5f
ms.lasthandoff: 04/14/2017


---

# <a name="frequently-asked-questions-about-mam-and-app-protection"></a>Veelgestelde vragen over MAM en app-beveiliging

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In dit artikel vindt u antwoorden op enkele veelgestelde vragen over Intune Mobile Application Management (MAM) en de bescherming van apps met Intune.

## <a name="mam-basics"></a>Basisinformatie over MAM


**Wat is MAM?** [Intune Mobile Application Management](../deploy-use/overview-of-app-lifecycle-in-microsoft-intune.md) verwijst naar de suite met Intune-beheerfuncties waarmee u mobiele apps voor uw gebruikers kunt publiceren, pushen, configureren, beveiligen, controleren en bijwerken.

**Wat zijn de voordelen van het beveiligen van apps met MAM?** Met MAM worden de gegevens van een organisatie in een toepassing beveiligd. Met MAM-WE kunt u op bijna elk apparaat, inclusief persoonlijke apparaten in BYOD-scenario's (Bring-Your-Own-Device), een werk- of schoolgerelateerde app beheren die gevoelige gegevens bevat. Veel productiviteits-apps, zoals Microsoft Office-apps, kunnen worden beheerd met Intune MAM. Zie de officiële lijst met [apps met Intune-functionaliteit](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) die beschikbaar zijn voor openbaar gebruik.

**Welke apparaatconfiguraties ondersteunt MAM?** Intune MAM ondersteunt twee configuraties:
  1. **Intune MDM + MAM**: dit is de eerste configuratie die door MAM wordt ondersteund wanneer de app voor het eerst wordt gestart. IT-beheerders kunnen apps alleen met MAM en beleidsregels voor de beveiliging van apps beheren op apparaten die zijn geregistreerd bij Intune Mobile Device Management (MDM). Voor het beheren van apps met MDM + MAM moeten klanten de zelfstandige Intune-console op http://manage.microsoft.com gebruiken.

  2. **MAM zonder apparaatregistratie**: MAM zonder apparaatregistratie, of MAM-WE, biedt IT-beheerders de mogelijkheid apps te beheren met MAM en beleidsregels voor de beveiliging van apps op apparaten die niet zijn geregistreerd bij Intune MDM. Dit betekent dat apps door Intune kunnen worden beheerd op apparaten die zijn geregistreerd bij externe EMM providers. Voor het beheren van apps met MAM-WE moeten klanten de Intune-console Azure Portal op http://portal.azure.com gebruiken.


## <a name="app-protection-policies"></a>Beleidsregels voor de beveiliging van apps

**Wat zijn beleidsregels voor de beveiliging van apps**? Beleidsregels voor de beveiliging van apps zijn regels die ervoor zorgen dat de bedrijfsgegevens die zijn opgenomen in een app, veilig of binnen de app blijven. Een beleidsregel kan een regel zijn die wordt afgedwongen wanneer de gebruiker bedrijfsgegevens probeert te openen of te verplaatsen, of een reeks acties die zijn verboden of worden gecontroleerd wanneer de gebruiker zich in de app bevindt.

**Wat zijn voorbeelden van beleidsregels voor de beveiliging van apps?** Zie de [beleidsinstellingen voor de beveiliging van Android-apps](../deploy-use/android-mam-policy-settings.md) en de [beleidsinstellingen voor de beveiliging van iOS-apps](../deploy-use/ios-mam-policy-settings.md) voor gedetailleerde informatie over elke beleidsinstelling voor de beveiliging van apps.

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Apps die u kunt beheren met beleidsregels voor de beveiliging van apps

**Welke apps kunnen worden beheerd door beleidsregels voor de beveiliging van apps?** Alle apps met de functionaliteit van de [Intune App SDK](../develop/intune-app-sdk.md) of die zijn ingepakt met de [Intune App Wrapping Tool](../deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) kunnen worden beheerd met Intune-beleidsregels voor de beveiliging van apps. Zie de officiële lijst met [apps met Intune-functionaliteit](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) die beschikbaar zijn voor openbaar gebruik.

**Wat zijn de basisvereisten voor het gebruik van beleidsregels voor de beveiliging van apps die geschikt zijn voor Intune?**
  1. De eindgebruiker moet een AAD-account (Azure Active Directory) hebben. Zie [Gebruikers toevoegen en beheerdersmachtigingen aan Intune toekennen](../get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3.md) voor informatie over het maken van Intune-gebruikers in Azure Active Directory.

  2. Er moet een licentie voor Microsoft Intune Azure aan het Azure Active Directory-account van de eindgebruiker zijn toegewezen. Zie [Intune-licenties beheren](../get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4.md) voor informatie over het toewijzen van Intune-licenties aan eindgebruikers.

  3. De eindgebruiker moet behoren tot een beveiligingsgroep waarop een beleidsregel voor de beveiliging van apps is gericht. Dezelfde beleidsregel voor de beveiliging van apps moet ook zijn gericht op de specifieke app die wordt gebruikt. Beleidsregels voor de beveiliging van apps kunnen worden gemaakt en geïmplementeerd in de Intune-console in [Azure Portal](http://portal.azure.com). Beveiligingsgroepen kunnen op dit moment worden gemaakt in de [Office-portal](http://portal.office.com).

  4. De eindgebruiker moet zich aanmelden bij de app met zijn of haar AAD-account.

**Wat zijn de aanvullende vereisten voor het gebruik van de [mobiele app van Outlook](https://www.microsoft.com/outlook-com/mobile/)?**

  1. Eindgebruikers moeten de mobiele app van Outlook op hun apparaat hebben geïnstalleerd.

  2. De eindgebruiker moet een [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online)-postvak en -licentie aan het Azure Active Directory-account hebben gekoppeld.

  >[!NOTE]
  > De mobiele app van Outlook ondersteunt momenteel alleen Microsoft Exchange Online en biedt geen ondersteuning voor Exchange On-Premises of Exchange in Office 365 Dedicated.

**Wat zijn de aanvullende vereisten voor het gebruik van de apps [Word, Excel en PowerPoint](https://products.office.com/business/office)?**

  1. Eindgebruikers moeten een licentie voor [Office 365 Business of Enterprise](https://products.office.com/business/compare-more-office-365-for-business-plans) aan hun Azure Active Directory-account hebben gekoppeld. Het abonnement moet de Office-apps voor mobiele apparaten en een cloudopslagaccount met [OneDrive voor Bedrijven](https://onedrive.live.com/about/business/) omvatten. Office 365-licenties kunnen aan de hand van de volgende [instructies](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc) worden toegewezen in de [Office-portal](http://portal.office.com).

  2. Eindgebruikers moeten de app [OneDrive](https://onedrive.live.com/about/) op hun apparaat hebben geïnstalleerd en zijn aangemeld met hun AAD-account.

  3. De app OneDrive app moet het doel zijn van het app-beveiligingsbeleid dat voor de eindgebruiker is geïmplementeerd.

  >[!NOTE]
  > De mobiele Office-apps bieden momenteel alleen ondersteuning voor SharePoint Online en niet voor SharePoint On-Premises.

**Waarom is OneDrive nodig voor Office?** Intune markeert alle gegevens in de app als 'zakelijk' of 'persoonlijk'. Gegevens worden als 'zakelijk' beschouwd wanneer ze afkomstig zijn van een bedrijfslocatie. Voor Office-apps worden de volgende locaties door Intune beschouwd als bedrijfslocaties: e-mail (Exchange) of cloudopslag (OneDrive-app met een OneDrive voor Bedrijven-account).

**Wat zijn de aanvullende vereisten voor het gebruik van Skype voor Bedrijven?** Zie de licentievereisten voor [Skype voor Bedrijven](https://products.office.com/skype-for-business/it-pros).
  >[!NOTE]
  > De mobiel app van Skype voor Bedrijven biedt momenteel alleen ondersteuning voor Skype voor Bedrijven Online.

## <a name="app-protection-features"></a>Functies voor app-beveiliging

**Wat is ondersteuning voor meerdere identiteiten?** Via ondersteuning voor meerdere identiteiten kan de Intune App SDK beleidsregels voor de beveiliging van apps toepassen op alleen het werk- of schoolaccount dat is aangemeld bij de app. Als een persoonlijk account is aangemeld bij de app, blijven de gegevens ongewijzigd.

**Wat is het doel van ondersteuning voor meerdere identiteiten?** Dankzij ondersteuning voor meerdere identiteiten kunnen apps met zowel een zakelijke als particuliere doelgroep (oftewel de Office-apps) openbaar worden vrijgegeven met app-beveiligingsfuncties van Intune voor de 'zakelijke' accounts.

**Wanneer wordt het pincodescherm weergegeven?** Het pincodescherm van Intune wordt alleen weergegeven wanneer de gebruiker 'zakelijke gegevens' in de app probeert te openen. In de apps Word/Excel/PowerPoint wordt het pincodescherm bijvoorbeeld weergegeven wanneer de eindgebruiker een document in OneDrive voor Bedrijven probeert te openen (ervan uitgaand dat u een app-beveiligingsbeleid hebt geïmplementeerd waarmee de pincode wordt afgedwongen).

**Outlook en meerdere identiteiten** Aangezien Outlook een gecombineerde e-mailweergave heeft met zowel persoonlijke als 'zakelijke' e-mails, wordt er naar de Intune-pincode gevraagd zodra Outlook wordt gestart.

**Wat is de pincode voor de Intune-app?** De pincode is een wachtwoordcode die wordt gebruikt om te verifiëren of de juiste gebruiker de bedrijfsgegevens in een app benadert.

  1. **Wanneer wordt de gebruiker gevraagd een pincode op te geven?** Intune vraagt alleen naar de pincode van de gebruiker wanneer de gebruiker 'zakelijke' gegevens benadert. In apps met functionaliteit voor meerdere identiteiten, zoals Word/Excel/PowerPoint, wordt de gebruiker naar een de pincode gevraagd wanneer ze een 'zakelijk' document of bestand willen openen. In apps waarvoor maar één identiteit kan worden gebruikt, zoals Line-Of-Business-apps met de Intune App Wrapping Tool-functionaliteit, wordt gelijk bij het starten van de app om de pincode gevraagd, omdat de Intune App SDK weet dat de gebruik de app uitsluitend 'zakelijk' gebruikt.

  2. **Is de pincode veilig?** De pincode zorgt ervoor dat alleen de juiste gebruiker toegang heeft tot de gegevens van de organisatie in de app. Daarom moet een eindgebruikers zich aanmelden met een werk- of schoolaccount voordat de pincode voor de Intune-app kan worden ingesteld of hersteld. Deze verificatie wordt verwerkt door Azure Active Directory via uitwisseling van een beveiligde token en is niet transparant voor de Intune App SDK. Vanuit het oogpunt van veiligheid kunt u werk- of schoolgerelateerde gegevens het beste versleutelen. Versleuteling is niet gerelateerd aan de pincode van de app, maar is een eigen app-beveiligingsbeleid.

  3. **Hoe beschermt Intune de pincode tegen beveiligingsaanvallen?** Als onderdeel van het app-pincodebeleid kan de IT-beheerder een maximumaantal verificatiepogingen voor gebruikers instellen voordat de app wordt vergrendeld. Na het toegestane aantal aanmeldingspogingen kan de Intune App SDK de 'zakelijke' gegevens in de app wissen.

**Versleuteling** IT-beheerders kunnen een app-beveiligingsbeleid instellen dat vereist dat de gegevens in de app worden versleuteld. De IT-beheerder kan als onderdeel van het beleid ook opgeven wanneer de inhoud wordt versleuteld.

  1. **Hoe worden gegevens versleuteld met Intune?** Zie de [beleidsinstellingen voor de beveiliging van Android-apps](../deploy-use/android-mam-policy-settings.md) en de [beleidsinstellingen voor de beveiliging van iOS-apps](../deploy-use/ios-mam-policy-settings.md) voor gedetailleerde informatie over elke beleidsinstelling voor de beveiliging van apps.

  2. **Wat wordt versleuteld?** Alleen gegevens die zijn gemarkeerd als 'zakelijk' worden versleuteld overeenkomstig het app-beveiligingsbeleid van de IT-beheerder. Gegevens worden als 'zakelijk' beschouwd wanneer ze afkomstig zijn van een bedrijfslocatie. Voor Office-apps worden de volgende locaties door Intune beschouwd als bedrijfslocaties: e-mail (Exchange) of cloudopslag (OneDrive-app met een OneDrive voor Bedrijven-account). Alle app-gegevens in Line-Of-Business-apps met Intune App Wrapping Tool-functionaliteit worden beschouwd als 'zakelijk'.

**Hoe worden gegevens extern gewist met Intune?** In Intune kunnen app-gegevens op drie verschillende manieren worden gewist: volledig apparaat wissen, selectief wissen voor MDM en selectief wissen voor MAM. Zie [Uw gegevens beveiligen met volledig wissen of selectief wissen met Microsoft Intune](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) voor meer informatie over wissen op afstand voor MDM. Zie [Bedrijfsgegevens van beheerde apps wissen met Microsoft Intune](../deploy-use/wipe-managed-company-app-data-with-microsoft-intune.md) voor meer informatie over selectief wissen met MAM.

  1. **Wat is volledig wissen?** Met [Volledig wissen](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe) verwijdert u alle gebruikersgegevens en instellingen van **het apparaat** door het apparaat terug te zetten op de standaardfabrieksinstellingen. Het apparaat wordt uit Intune verwijderd.
  >[!NOTE]
  > Alleen apparaten die zijn geregistreerd bij Intune Mobile Device Management (MDM) kunnen volledig worden gewist.

  2. **Wat is selectief wissen voor MDM?** Zie [Uw gegevens beveiligen met volledig wissen of selectief wissen met Microsoft Intune](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) voor meer informatie over selectief wissen.

  3. **Wat is selectief wissen voor MAM?** Bij selectief wissen voor MAM worden gegevens van bedrijfs-apps gewoon gewist uit een app. De aanvraag wordt gestart via de Intune Azure-portal. Zie [Bedrijfsgegevens van beheerde apps wissen met Microsoft Intune](../deploy-use/wipe-managed-company-app-data-with-microsoft-intune.md) voor meer informatie over het initiëren van een wisaanvraag.

  4. **Hoe snel wordt selectief wissen voor MAM uitgevoerd?** Als de gebruiker de app gebruikt wanneer selectief wissen wordt gestart, controleert de Intune App SDK om de 30 minuten op aanvragen van de MAM-service voor selectief wissen. Daarnaast wordt er gecontroleerd of er een aanvraag voor selectief wissen is verzonden wanneer de gebruiker de app voor de eerste keer start en zich aanmeldt met een werk- of schoolaccount.

**Waarom kunnen er geen on-premises services (on-prem) worden gebruikt in combinatie met apps die zijn beveiligd met Intune?** Voor de app-beveiliging van Intune moet de identiteit van de gebruiker voor de toepassing en Intune App SDK consistent zijn. Dit kan alleen worden gegarandeerd via moderne verificatie. Er zijn scenario's waarin apps met een on-premisses configuratie werken, maar deze zijn niet consistent en kunnen ook niet worden gegarandeerd.

**Is er een veilige manier om webkoppelingen te openen vanuit beheerde apps?** Ja. De IT-beheerder kan een app-beveiligingsbeleid implementeren en instellen voor de [Intune Managed Browser-app](../deploy-use/manage-internet-access-using-managed-browser-policies.md), een webbrowser die is ontwikkeld door Microsoft Intune en eenvoudig kan worden beheerd met Intune. De IT-beheerder kan ervoor zorgen dat alle webkoppelingen in apps met de Intune-functionaliteit moeten worden geopend met de Managed Browser-app.


## <a name="app-experience-on-android"></a>Apps op Android gebruiken

**Waarom is de bedrijfsportal-app op Android-apparaten nodig voor app-beveiliging met Intune?** Veel van de functies voor het beveiligen van apps zijn ingebouwd in de bedrijfsportal-app. Hoewel de bedrijfsportal-app altijd vereist is, hoeft een apparaat _niet te worden geregistreerd_. Voor MAM-WE moet de eindgebruiker de bedrijfsportal-app op het apparaat hebben geïnstalleerd.

## <a name="app-experience-on-ios"></a>Apps op iOS gebruiken

**Ik kan de iOS-extensie voor delen gebruiken om werk- of schoolgegevens te openen in niet-beheerde apps, zelfs wanneer het beleid voor het overdragen van gegevens is ingesteld op 'alleen voor beheerde apps' of 'geen apps'. Ontstaat hierdoor geen gegevenslek?** De iOS-extensie voor delen kan alleen met het app-beveiligingsbeleid worden beheerd als ook het apparaat wordt beheerd. Daarom worden _**'zakelijke' gegevens door Intune versleuteld voordat ze buiten de app worden gedeeld**_. U kunt dit controleren door een 'zakelijk' bestand te openen buiten de beheerde app. Het bestand moet zijn versleuteld en kan niet worden geopend bijten de beheerde app.

### <a name="see-also"></a>Zie tevens
- [Mobile Application Management-beleidsinstellingen voor Android in Microsoft Intune](../deploy-use/android-mam-policy-settings.md)
- [Mobile Application Management-beleidsinstellingen voor iOS](../deploy-use/ios-mam-policy-settings.md)
- [De Mobile Application Management-configuratie valideren](../deploy-use/validate-mobile-application-management.md)
- [Voorbereidingen voor het configureren van beleid voor het beheer van mobiele apps (Mobile App Management) met Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
- [Ondersteuning voor Microsoft Intune krijgen](../troubleshoot/how-to-get-support-for-microsoft-intune.md)

