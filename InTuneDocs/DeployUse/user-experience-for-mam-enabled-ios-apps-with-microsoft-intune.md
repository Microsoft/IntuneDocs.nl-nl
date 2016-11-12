---
title: iOS-apps met MAM-beleid | Microsoft Intune
description: In dit onderwerp wordt beschreven wat u kunt verwachten wanneer uw iOS-app wordt beheerd door beleidsregels voor beheer van mobiele apps.
keywords: 
author: karthikaraman
ms.author: karaman
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
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: 3f9d9c7cafcdac0db21e5ba35f713fe630c65b99


---

# Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door MAM-beleid
 Dit onderwerp beschrijft de gebruikerservaring voor apps met MAM-beleid. Beleid voor het beheer van mobiele toepassingen (MAM) wordt alleen toegepast wanneer apps worden gebruikt in een werkcontext, dus wanneer u apps gebruikt met uw werkaccount of bestanden opent die zijn opgeslagen in de OneDrive voor Bedrijven-locatie van uw bedrijf.
##  Apps openen

Als het apparaat **niet is ingeschreven bij Intune**, wordt de eindgebruiker gevraagd de app opnieuw te starten wanneer die de eerste keer wordt gebruikt.  Dit opnieuw starten is nodig voor het toepassen van het MAM-beleid op de app. In de volgende schermafbeelding wordt dit weergegeven met de Skype-app:


![schermafbeelding van iOS-apparaat met pincodeprompt](../media/appmanagement/iOS_AppPINPrompt.png)

Op apparaten die zijn **ingeschreven voor beheer in Intune** krijgt de eindgebruiker een bericht te zien dat de app nu wordt beheerd:

![schermafbeelding van iOS-apparaat met het bericht dat het wordt beheerd door het bedrijf en een pincodeprompt](../media/appmanagement/ios-managed-devices-pin-prompt.png)

##  Apps met ondersteuning voor meerdere identiteiten gebruiken

Het MAM-beleid wordt alleen toegepast wanneer de app wordt gebruikt in een werkcontext, dus de app werkt mogelijk anders afhankelijk van de context waarin u die gebruikt (werk of persoonlijk).  

Voor apps die meerdere identiteiten ondersteunen past Intune het MAM-beleid alleen toe wanneer de eindgebruiker de app gebruikt in de werkcontext.  De gebruiker moet bijvoorbeeld een pincode invoeren bij het openen van bedrijfsgegevens.  Bij de **Outlook-app** wordt de gebruiker gevraagd een pincode in te voeren bij het starten van de app. Bij de **OneDrive-app** gebeurt dit wanneer de eindgebruiker het werkaccount invoert.  Bij Microsoft **Word**, **PowerPoint* en **Excel** gebeurt dit wanneer de eindgebruiker documenten opent die zijn opgeslagen in de OneDrive voor Bedrijven-locatie van uw bedrijf.
##  Gebruikersaccounts op het apparaat beheren

Intune biedt alleen ondersteuning voor het implementeren van MAM-beleid naar slechts één gebruikersaccount per apparaat.

* Afhankelijk van de app die u gebruikt, kan het zijn dat de tweede gebruiker op het apparaat wordt geblokkeerd. In alle gevallen wordt echter alleen de eerste gebruiker die het MAM-beleid ontvangt, door het beleid beïnvloed.
  * **Microsoft Word**, **Excel** en **PowerPoint** blokkeren een tweede gebruikersaccount niet, maar de tweede gebruikersaccount wordt niet beïnvloed door het MAM-beleid.  

  * Voor de **OneDrive-app en Outlook-app** kunt u slechts één werkaccount gebruiken.  Het toevoegen van meerdere werkaccounts is op deze apps geblokkeerd.  U kunt wel een gebruiker verwijderen en een andere gebruiker op het apparaat toevoegen.

* Als een apparaat meerdere gebruikersaccounts heeft voordat het MAM-beleid wordt geïmplementeerd, wordt het account waarop het MAM-beleid als eerste wordt geïmplementeerd, door het Intune MAM-beleid beheerd.


Lees het voorbeeldscenario hieronder om meer inzicht te krijgen in hoe meerdere gebruikersaccounts worden behandeld.

Gebruiker A werkt voor twee bedrijven: **bedrijf X** en **bedrijf Y**. Gebruiker A heeft voor elk bedrijf een werkaccount en voor beide accounts wordt gebruikgemaakt van Intune om MAM-beleid te implementeren. **Bedrijf X** implementeert MAM-beleid **voordat** **bedrijf Y** dat doet. Het MAM-beleid wordt toegepast op het account dat is gekoppeld aan **bedrijf X**, niet op het account dat is gekoppeld aan bedrijf Y. Als u wilt dat het gebruikersaccount dat is gekoppeld aan bedrijf Y, door het MAM-beleid wordt beheerd, moet u het gebruikersaccount dat is gekoppeld aan bedrijf X, verwijderen.
### Een tweede account toevoegen

Als u een iOS-apparaat gebruikt en probeert op hetzelfde apparaat een tweede werkaccount toe te voegen, ziet u mogelijk een blokkeringsbericht.  De accounts worden weergegeven en u kunt kiezen welk account u wilt verwijderen.

![Schermafbeelding van het dialoogvenster met het blokkeringsbericht en de opties Ja en Nee](../media/AppManagement/iOS_SwitchUser.PNG)
## Volgende stappen
[Wat u kunt verwachten wanneer uw Android-app wordt beheerd door MAM-beleid](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
### Zie tevens
[Beleid voor Mobile App Management maken en implementeren met Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


