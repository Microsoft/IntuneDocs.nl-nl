---
title: iOS-apps met MAM-beleid | Microsoft Intune
description: In dit onderwerp wordt beschreven wat u kunt verwachten wanneer uw iOS-app wordt beheerd door beleidsregels voor beheer van mobiele apps.
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 3aa6728036ff66ea489176063af2d136bef4c7cc


---

# <a name="what-to-expect-when-your-ios-app-is-managed-by-mam-policies"></a>Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door MAM-beleid
 In dit onderwerp wordt de gebruikerservaring voor apps met MAM-beleid (Mobile Access Management) beschreven. MAM-beleidsregels worden alleen toegepast wanneer apps worden gebruikt in een werkcontext, bijvoorbeeld wanneer de gebruiker apps gebruikt met een werkaccount of bestanden opent die zijn opgeslagen in de OneDrive voor Bedrijven-locatie van uw bedrijf.

##  <a name="access-apps"></a>Toegang tot apps

Als het apparaat **niet is geregistreerd bij Intune**, wordt de gebruiker gevraagd de app opnieuw te starten wanneer deze voor het eerst wordt gebruikt.  Er moet opnieuw worden opgestart zodat het MAM-beleid kan worden toegepast op de app. Dit opstartverzoek wordt geïllustreerd in de volgende schermafbeelding van de Skype-app:


![Schermafbeelding van het iOS-apparaat met pincodeprompt](../media/appmanagement/iOS_AppPINPrompt.png)

Op apparaten die zijn **geregistreerd voor beheer in Intune**, wordt een bericht aan de gebruiker weergegeven dat de app nu wordt beheerd:

![Schermafbeelding van het iOS-apparaat met het bericht dat het wordt beheerd door het bedrijf en een pincodeprompt](../media/appmanagement/ios-managed-devices-pin-prompt.png)

##  <a name="use-apps-with-multi-identity-support"></a>Apps met ondersteuning voor meerdere identiteiten gebruiken

MAM-beleidsregels worden alleen toegepast in de context van het werk. Daarom is het mogelijk dat de app zich anders gedraagt, afhankelijk of het om een persoonlijke of werkcontext gaat.

 De gebruiker moet bijvoorbeeld een pincode invoeren bij het openen van werkgegevens. Voor de **Outlook-app** wordt de gebruiker gevraagd een pincode in te voeren bij het starten van de app. Voor de **OneDrive app** wordt de gebruiker om een pincode gevraagd wanneer deze het werkaccount typt.  Bij Microsoft **Word**, **PowerPoint** en **Excel** wordt de gebruiker om een pincode gevraagd wanneer deze documenten opent die zijn opgeslagen op de OneDrive voor Bedrijven-locatie van het bedrijf.

##  <a name="manage-user-accounts-on-the-device"></a>Gebruikersaccounts op het apparaat beheren

Intune biedt alleen ondersteuning voor de implementatie van MAM-beleid naar slechts één gebruikersaccount per apparaat.

* Afhankelijk van de app die u gebruikt, kan het zijn dat de tweede gebruiker op het apparaat wordt geblokkeerd. In alle gevallen wordt echter alleen de eerste gebruiker die het MAM-beleid ontvangt, door het beleid beïnvloed.
  * **Microsoft Word**, **Excel** en **PowerPoint** blokkeren een tweede gebruikersaccount niet, maar de tweede gebruikersaccount wordt niet beïnvloed door het MAM-beleid.  

  * Voor de apps **OneDrive** en **Outlook** kunt u slechts één werkaccount gebruiken. Het is niet mogelijk om meerdere werkaccounts voor deze apps toe te voegen. U kunt wel een gebruiker verwijderen en een andere gebruiker op het apparaat toevoegen.

* Als een apparaat meerdere gebruikersaccounts heeft voordat het MAM-beleid wordt geïmplementeerd, wordt het account waarop het MAM-beleid als eerste wordt geïmplementeerd, door het Intune MAM-beleid beheerd.


Lees het volgende voorbeeldscenario om meer inzicht te krijgen in hoe meerdere gebruikersaccounts worden behandeld.

Gebruiker A werkt voor twee bedrijven: **bedrijf X** en **bedrijf Y**. Gebruiker A heeft voor elk bedrijf een werkaccount en voor beide accounts wordt gebruikgemaakt van Intune om MAM-beleid te implementeren. **Bedrijf X** implementeert MAM-beleid **voordat** **bedrijf Y** dat doet. Het MAM-beleid wordt toegepast op het account dat is gekoppeld aan **bedrijf X**, niet op het account dat is gekoppeld aan bedrijf Y. Als u wilt dat het gebruikersaccount dat is gekoppeld aan bedrijf Y, door het MAM-beleid wordt beheerd, moet u het gebruikersaccount dat is gekoppeld aan bedrijf X, verwijderen.

### <a name="add-a-second-account"></a>Een tweede account toevoegen

Als u een iOS-apparaat gebruikt en u een tweede werkaccount op dat apparaat probeert toe te voegen, ziet u mogelijk een blokkeringsbericht. De accounts worden weergegeven en vervolgens u kunt kiezen welk account u wilt verwijderen.

![Schermafbeelding van het dialoogvenster met het blokkeringsbericht en de opties Ja en Nee](../media/AppManagement/iOS_SwitchUser.PNG)
## <a name="next-steps"></a>Volgende stappen
[Wat u kunt verwachten wanneer uw Android-app wordt beheerd door MAM-beleid](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### <a name="see-also"></a>Zie tevens
[Beleid voor Mobile App Management maken en implementeren met Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


