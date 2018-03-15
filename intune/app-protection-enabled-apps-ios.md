---
title: iOS-apps met beveiligingsbeleid voor apps
titlesuffix: Microsoft Intune
description: Informatie over wat u kunt verwachten van een iOS-app met beveiligingsbeleid.
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 13833d41603e24e4471f0bb5fdda40d000f29a34
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Meer informatie over de gebruikerservaring voor iOS-apps met app-beveiligingsbeleid. App-beveiligingsbeleid wordt alleen toegepast wanneer apps in de context van het werk worden gebruikt. Wanneer u bijvoorbeeld een app met een werkaccount opent, of wanneer u bestanden opent die zijn opgeslagen in de OneDrive-locatie van uw bedrijf.
##  <a name="accessing-apps"></a>Apps openen

Als het apparaat **niet is ingeschreven bij Intune**, wordt de gebruiker gevraagd de app opnieuw te starten wanneer die de eerste keer wordt gebruikt.  Er moet opnieuw worden opgestart zodat het app-beveiligingsbeleid kan worden toegepast op de app. In de volgende schermafbeelding wordt dit weergegeven met de Skype-app:


![schermafbeelding van iOS-apparaat met pincodeprompt](./media/ios-pin-prompt.png)

Op apparaten die zijn **ingeschreven voor beheer in Intune** krijgt de gebruiker een bericht te zien dat de app nu wordt beheerd:

![schermafbeelding van iOS-apparaat met het bericht dat het wordt beheerd door het bedrijf en een pincodeprompt](./media/ios-managed-devices-pin-prompt.png)

##  <a name="using-apps-with-multi-identity-support"></a>Apps met ondersteuning voor meerdere identiteiten gebruiken

App-beveiligingsbeleid wordt pas van kracht wanneer een gebruiker probeert toegang te krijgen tot werkgerelateerde gegevens.  Mogelijk ziet u ander gedrag als de gebruiker de app voor persoonlijk gebruik opent. 

Voor apps die ondersteuning bieden voor meerdere identiteiten, past Intune alleen app-beveiligingsbeleid toe als een gebruiker zakelijke gegevens benadert.  Een gebruiker kan bijvoorbeeld om een pincode worden gevraagd.  In de **Outlook-app** wordt een prompt weergegeven wanneer een gebruiker de app start. In de **OneDrive-app** wordt een prompt weergegeven wanneer een gebruiker het werkaccount invoert.  In Microsoft **Word**, **PowerPoint** en **Excel** wordt een prompt weergegeven wanneer een gebruiker OneDrive-bedrijfsdocumenten opent.
##  <a name="managing-user-accounts-on-the-device"></a>Gebruikersaccounts op het apparaat beheren

Intune biedt alleen ondersteuning voor het implementeren van app-beveiligingsbeleid naar slechts één gebruikersaccount per apparaat.

* Afhankelijk van de app die u gebruikt, kan het zijn dat de tweede gebruiker op het apparaat wordt geblokkeerd. In alle gevallen wordt echter alleen de eerste gebruiker die het app-beveiligingsbeleid ontvangt door het beleid beïnvloed.
  * **Microsoft Word**, **Excel** en **PowerPoint** blokkeren toegang tot een extra gebruikersaccount niet. Het gebruikersaccount wordt echter niet beïnvloed door het app-beveiligingsbeleid.

  * Voor de **OneDrive-app en Outlook-app** kunt u slechts één werkaccount gebruiken.  Het toevoegen van meerdere werkaccounts is op deze apps geblokkeerd.  U kunt een gebruiker echter van een apparaat verwijderen en vervolgens een andere gebruiker toevoegen aan het apparaat.

* Een apparaat kan meerdere bestaande gebruikersaccounts hebben voordat het app-beveiligingsbeleid wordt geïmplementeerd. In dit geval wordt het eerste account waarop het app-beveiligingsbeleid wordt geïmplementeerd, beheerd door het app-beveiligingsbeleid van Intune.


Lees het volgende voorbeeldscenario voor meer informatie over hoe Intune omgaat met meerdere gebruikersaccounts.

Gebruiker A werkt voor twee bedrijven: **bedrijf X** en **bedrijf Y**. Gebruiker A heeft voor elk bedrijf een werkaccount en voor beide accounts wordt gebruikgemaakt van Intune om app-beveiligingsbeleid te implementeren. **Bedrijf X** implementeert app-beveiligingsbeleid **voordat** **bedrijf Y** dat doet. Het app-beveiligingsbeleid wordt toegepast op het account dat is gekoppeld aan **bedrijf X**, niet op het account dat is gekoppeld aan bedrijf Y. Als u wilt dat het gebruikersaccount van bedrijf Y door het app-beveiligingsbeleid wordt beheerd, moet gebruiker A het gebruikersaccount van bedrijf X verwijderen.
### <a name="adding-a-second-account"></a>Een tweede account toevoegen

Als u een iOS-apparaat gebruikt en probeert op hetzelfde apparaat een tweede werkaccount toe te voegen, ziet u mogelijk een blokkeringsbericht.  De accounts worden weergegeven en u kunt kiezen welk account u wilt verwijderen.

![Schermafbeelding van het dialoogvenster met het blokkeringsbericht en de opties Ja en Nee](./media/ios-switch-user.PNG)

## <a name="next-steps"></a>Volgende stappen
[Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-apps-android.md)
### <a name="see-also"></a>Zie tevens
[App-beveiligingsbeleid maken en implementeren met Microsoft Intune](app-protection-policies.md)
