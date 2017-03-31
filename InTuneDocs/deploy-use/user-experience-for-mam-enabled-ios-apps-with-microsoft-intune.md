---
title: iOS-apps met app-beveiligingsbeleid | Microsoft Docs
description: In dit onderwerp wordt beschreven wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 665d3347636d5ec0c698ffb93b768028c9d59ce3
ms.openlocfilehash: fba18027039a0e49c5301f9d1a16947e97408034
ms.lasthandoff: 03/07/2017


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

 In dit onderwerp wordt de gebruikerservaring voor apps met app-beveiligingsbeleid beschreven. App-beveiligingsbeleid wordt alleen toegepast wanneer apps worden gebruikt in een werkcontext, bijvoorbeeld wanneer de gebruiker apps gebruikt met een werkaccount of bestanden opent die zijn opgeslagen in de OneDrive voor Bedrijven-locatie van uw bedrijf.

##  <a name="access-apps"></a>Toegang tot apps

Als het apparaat **niet is geregistreerd bij Intune**, wordt de gebruiker gevraagd de app opnieuw te starten wanneer deze voor het eerst wordt gebruikt.  Er moet opnieuw worden opgestart zodat het app-beveiligingsbeleid kan worden toegepast op de app. 

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

Op apparaten die zijn **ingeschreven voor beheer in Intune**, wordt een bericht aan de gebruiker weergegeven dat de app nu wordt beheerd.

##  <a name="use-apps-with-multi-identity-support"></a>Apps met ondersteuning voor meerdere identiteiten gebruiken

App-beveiligingsbeleid wordt alleen toegepast in een werkcontext. Daarom is het mogelijk dat de app zich anders gedraagt, afhankelijk of het om een persoonlijke of werkcontext gaat.

 De gebruiker moet bijvoorbeeld een pincode invoeren bij het openen van werkgegevens. Voor de **Outlook-app** wordt de gebruiker gevraagd een pincode in te voeren bij het starten van de app. Voor de **OneDrive app** wordt de gebruiker om een pincode gevraagd wanneer deze het werkaccount typt.  Bij Microsoft **Word**, **PowerPoint** en **Excel** wordt de gebruiker om een pincode gevraagd wanneer deze documenten opent die zijn opgeslagen op de OneDrive voor Bedrijven-locatie van het bedrijf.

##  <a name="manage-user-accounts-on-the-device"></a>Gebruikersaccounts op het apparaat beheren

Intune biedt ondersteuning voor de implementatie van app-beveiligingsbeleid voor slechts één gebruikersaccount per apparaat.

* Afhankelijk van de app die u gebruikt, kan het zijn dat de tweede gebruiker op het apparaat wordt geblokkeerd. In alle gevallen wordt echter alleen de eerste gebruiker die het app-beveiligingsbeleid ontvangt, door het beleid beïnvloed.
  * **Microsoft Word**, **Excel** en **PowerPoint** blokkeren een tweede gebruikersaccount niet, maar het tweede gebruikersaccount wordt niet beïnvloed door het app-beveiligingsbeleid.  

  * Voor de apps **OneDrive** en **Outlook** kunt u slechts één werkaccount gebruiken. Het is niet mogelijk om meerdere werkaccounts voor deze apps toe te voegen. U kunt wel een gebruiker verwijderen en een andere gebruiker op het apparaat toevoegen.

* Als een apparaat meerdere gebruikersaccounts heeft voordat het app-beveiligingsbeleid wordt geïmplementeerd, wordt het account waarop het app-beveiligingsbeleid als eerste wordt geïmplementeerd, door het app-beveiligingsbeleid van Intune beheerd.


Lees het volgende voorbeeldscenario om meer inzicht te krijgen in hoe meerdere gebruikersaccounts worden behandeld.

Gebruiker A werkt voor twee bedrijven: **bedrijf X** en **bedrijf Y**. Gebruiker A heeft voor elk bedrijf een werkaccount en voor beide accounts wordt gebruikgemaakt van Intune om app-beveiligingsbeleid te implementeren. **Bedrijf X** implementeert app-beveiligingsbeleid **voordat** **bedrijf Y** dat doet. Het app-beveiligingsbeleid wordt toegepast op het account dat is gekoppeld aan **bedrijf X**, niet op het account dat is gekoppeld aan bedrijf Y. Als u wilt dat het gebruikersaccount dat is gekoppeld aan bedrijf Y, door het app-beveiligingsbeleid wordt beheerd, moet u het gebruikersaccount dat is gekoppeld aan bedrijf X, verwijderen.

### <a name="add-a-second-account"></a>Een tweede account toevoegen

Als u een iOS-apparaat gebruikt en u een tweede werkaccount op dat apparaat probeert toe te voegen, ziet u mogelijk een blokkeringsbericht. De accounts worden weergegeven en vervolgens u kunt kiezen welk account u wilt verwijderen.

## <a name="next-steps"></a>Volgende stappen
[Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### <a name="see-also"></a>Zie tevens
[Beleid voor Mobile App Management maken en implementeren met Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)

