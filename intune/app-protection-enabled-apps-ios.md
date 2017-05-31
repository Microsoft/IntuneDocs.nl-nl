---
title: iOS-apps met beveiligingsbeleid voor apps| Intune Azure Preview
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp wordt beschreven wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid.'
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 5e172b940dfae32213c870b29f05f56573192704
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid
[!INCLUDE[azure_preview](./includes/azure_preview.md)] In dit onderwerp wordt de gebruikerservaring voor apps met app-beveiligingsbeleid beschreven. App-beveiligingsbeleid wordt alleen toegepast wanneer apps worden gebruikt in een werkcontext, dus wanneer u apps gebruikt met uw werkaccount of bestanden opent die zijn opgeslagen in de OneDrive voor Bedrijven-locatie van uw bedrijf.
##  <a name="accessing-apps"></a>Apps openen

Als het apparaat **niet is ingeschreven bij Intune**, wordt de eindgebruiker gevraagd de app opnieuw te starten wanneer die de eerste keer wordt gebruikt.  Er moet opnieuw worden opgestart zodat het app-beveiligingsbeleid kan worden toegepast op de app. In de volgende schermafbeelding wordt dit weergegeven met de Skype-app:


![schermafbeelding van iOS-apparaat met pincodeprompt](./media/ios-pin-prompt.png)

Op apparaten die zijn **ingeschreven voor beheer in Intune** krijgt de eindgebruiker een bericht te zien dat de app nu wordt beheerd:

![schermafbeelding van iOS-apparaat met het bericht dat het wordt beheerd door het bedrijf en een pincodeprompt](./media/ios-managed-devices-pin-prompt.png)

##  <a name="using-apps-with-multi-identity-support"></a>Apps met ondersteuning voor meerdere identiteiten gebruiken

App-beveiligingsbeleid wordt alleen toegepast wanneer de app wordt gebruikt in een werkcontext, dus de app werkt mogelijk anders afhankelijk van de context waarin u die gebruikt (werk of persoonlijk).  

Voor apps die meerdere identiteiten ondersteunen past Intune het app-beveiligingsbeleid alleen toe wanneer de eindgebruiker de app gebruikt in de werkcontext.  De gebruiker moet bijvoorbeeld een pincode invoeren bij het openen van bedrijfsgegevens.  Bij de **Outlook-app** wordt de gebruiker gevraagd een pincode in te voeren bij het starten van de app. Bij de **OneDrive-app** gebeurt dit wanneer de eindgebruiker het werkaccount invoert.  Bij **Microsoft Word**, **PowerPoint* en **Excel** gebeurt dit wanneer de eindgebruiker documenten opent die zijn opgeslagen in de OneDrive voor Bedrijven-locatie van uw bedrijf.
##  <a name="managing-user-accounts-on-the-device"></a>Gebruikersaccounts op het apparaat beheren

Intune biedt alleen ondersteuning voor het implementeren van app-beveiligingsbeleid naar slechts één gebruikersaccount per apparaat.

* Afhankelijk van de app die u gebruikt, kan het zijn dat de tweede gebruiker op het apparaat wordt geblokkeerd. In alle gevallen wordt echter alleen de eerste gebruiker die het app-beveiligingsbeleid ontvangt, door het beleid beïnvloed.
  * **Microsoft Word**, **Excel** en **PowerPoint** blokkeren een tweede gebruikersaccount niet, maar het tweede gebruikersaccount wordt niet beïnvloed door het app-beveiligingsbeleid.  

  * Voor de **OneDrive-app en Outlook-app** kunt u slechts één werkaccount gebruiken.  Het toevoegen van meerdere werkaccounts is op deze apps geblokkeerd.  U kunt wel een gebruiker verwijderen en een andere gebruiker op het apparaat toevoegen.

* Als een apparaat meerdere gebruikersaccounts heeft voordat het app-beveiligingsbeleid wordt geïmplementeerd, wordt het account waarop het app-beveiligingsbeleid als eerste wordt geïmplementeerd, door het app-beveiligingsbeleid van Intune beheerd.


Lees het voorbeeldscenario hieronder om meer inzicht te krijgen in hoe meerdere gebruikersaccounts worden behandeld.

Gebruiker A werkt voor twee bedrijven: **bedrijf X** en **bedrijf Y**. Gebruiker A heeft voor elk bedrijf een werkaccount en voor beide accounts wordt gebruikgemaakt van Intune om app-beveiligingsbeleid te implementeren. **Bedrijf X** implementeert app-beveiligingsbeleid **voordat** **bedrijf Y** dat doet. Het app-beveiligingsbeleid wordt toegepast op het account dat is gekoppeld aan **bedrijf X**, niet op het account dat is gekoppeld aan bedrijf Y. Als u wilt dat het gebruikersaccount dat is gekoppeld aan bedrijf Y, door het app-beveiligingsbeleid wordt beheerd, moet u het gebruikersaccount dat is gekoppeld aan bedrijf X, verwijderen.
### <a name="adding-a-second-account"></a>Een tweede account toevoegen

Als u een iOS-apparaat gebruikt en probeert op hetzelfde apparaat een tweede werkaccount toe te voegen, ziet u mogelijk een blokkeringsbericht.  De accounts worden weergegeven en u kunt kiezen welk account u wilt verwijderen.

![Schermafbeelding van het dialoogvenster met het blokkeringsbericht en de opties Ja en Nee](./media/ios-switch-user.PNG)

## <a name="next-steps"></a>Volgende stappen
[Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-apps-android.md)
### <a name="see-also"></a>Zie tevens
[App-beveiligingsbeleid maken en implementeren met Microsoft Intune](app-protection-policies.md)

