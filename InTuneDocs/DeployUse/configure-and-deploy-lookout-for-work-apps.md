---
title: Lookout for Work-app implementeren | Microsoft Intune
description: Lookout for Work-apps voor Android configureren en implementeren.
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9c2ffb5fe497d56d8250fe3dec7db606c2067a1c
ms.openlocfilehash: c43104ff199e1800bfded35154d2be0cfd0c40f3


---

# Lookout for Work-apps configureren en implementeren
In deze release wordt de Lookout for Work-app op apparaten met Android 4.1 en hoger ondersteund.
## Android
In deze sectie wordt beschreven hoe u de Lookout for Work-toepassing kunt configureren en implementeren voor Android-apparaten die in Intune zijn geregistreerd.  
* Stap 1: ga in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) naar **Apps** en kies **Apps toevoegen**.   
* Stap 2: kies **Externe koppeling** op de pagina **Setup van software** van de uitgever en geef de volgende URL op:  https://play.google.com/store/apps/details?id=com.lookout.enterprise
>[!NOTE]
>Klik niet op het vak voor het vereisen van een beheerde browser.

* Stap 3: vul op de pagina **Beschrijving van software** de volgende informatie in:
  * **Uitgever:** Lookout Mobile Security
  * **Naam:** Lookout for Work
  * **Beschrijving:** Lookout biedt de beste beveiliging tegen mobiele bedreigingen om uw apparaat te beschermen. Wanneer de Lookout-app op het apparaat is geïnstalleerd, wordt uw apparaat met de app beschermd tegen bedreigingen en worden u en uw bedrijfsbeheerder gewaarschuwd als een bedreiging wordt aangetroffen.
  * **Categorie:** computerbeheer
* Stap 4: wanneer de installatie is voltooid, wordt het bericht **Het uploaden van gegevens naar Microsoft Intune is voltooid** weergegeven.

Wanneer u in de Intune-console op **Apps** klikt, wordt de the Lookout for Work-app weergegeven in de lijst. ![schermopname van de pagina Apps van de Intune-beheerconsole waarop de Lookout for Work-app wordt weergegeven](../media/mtp/lookout-app-listed-intune-console.png)

Stap 5: nu is duidelijk hoe de Lookout for Work-app voor Android met Intune moet worden geïmplementeerd.   U kunt de app bij gebruikers implementeren door de Lookout for Work-app te selecteren die op het scherm hierboven wordt weergegeven en vervolgens **Implementatie beheren** te selecteren.

U moet dezelfde gebruikers selecteren als die zijn toegevoegd aan de optie Registratiebeheer in de Lookout MTP-console.  Zie stap 3 in de sectie [Uw abonnement configureren met Lookout MTP](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp) voor informatie over het toevoegen van gebruikersgroepen aan Lookout MTP.
>[!IMPORTANT]
> De Intune-wizard voor implementatie van apps is onbekend met de Azure AD-gebruikersgroepen en in plaats daarvan worden de Intune-gebruikersgroepen gebruikt. U moet daarom een Intune-gebruikersgroep maken op basis van de Azure AD-gebruikersgroep die in de Lookout MTP-console is geregistreerd, zoals beschreven in [dit](plan-your-user-and-device-groups.md) onderwerp.

Stap 6: kies de optie **Vereiste installatie** om te vereisen dat de Lookout-app op het apparaat van de gebruiker wordt geïnstalleerd.

### Apparaatactivering
Als de optie **Vereiste installatie** is geselecteerd voor implementatie, wordt de Lookout for Work-toepassing met Intune naar het apparaat gepusht.   

Wanneer de gebruiker de Lookout for Work-app opent op het apparaat, wordt de gebruiker gevraagd de app te activeren en de optie Aanmelden bij Azure Active Directory te kiezen. Een gedetailleerd overzicht van de eindgebruikersstroom vindt u in de volgende onderwerpen:

* [U wordt gevraagd Lookout for Work te installeren op uw Android-apparaat](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [U moet een bedreiging oplossen die met Lookout for Work op een Android-apparaat is gevonden](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## Volgende stappen
* [De regel Device Threat Protection inschakelen in het nalevingsbeleid](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Sep16_HO2-->


