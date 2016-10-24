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
ms.sourcegitcommit: c4d05b9ba7249e4068d21480b1c9db342277757e
ms.openlocfilehash: 687a102ccb34cb7acfaab1e8a1d4b67cb54b9e92


---

# Lookout for Work-apps configureren en implementeren
In dit artikel wordt uitgelegd hoe u de Lookout for Work-app configureert en implementeert voor ingeschreven apparaten met Android 4.1 of later.

* **Stap 1:** ga in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) naar **Apps** en kies **Apps toevoegen**.   
* **Stap 2:** kies **Externe koppeling** op de pagina **Setup van software** van de uitgever en geef de volgende URL op:  https://play.google.com/store/apps/details?id=com.lookout.enterprise
>[!NOTE]
>Klik niet op het vak voor het vereisen van een beheerde browser.

* **Stap 3:** vul op de pagina **Beschrijving van software** de volgende informatie in:
  * **Uitgever:** Lookout Mobile Security
  * **Naam:** Lookout for Work
  * **Beschrijving:** Lookout biedt de beste beveiliging tegen mobiele bedreigingen om uw apparaat te beschermen. Wanneer de Lookout-app op het apparaat is geïnstalleerd, wordt uw apparaat met de app beschermd tegen bedreigingen en worden u en uw bedrijfsbeheerder gewaarschuwd als er een bedreiging wordt aangetroffen.
  * **Categorie:** computerbeheer
* **Stap 4:** wanneer de installatie is voltooid, wordt het bericht **Het uploaden van gegevens naar Microsoft Intune is voltooid** weergegeven.

Wanneer u nu in de Intune-beheerconsole op **Apps** klikt, wordt de Lookout for Work-app weergegeven in de lijst. ![schermopname van de pagina Apps van de Intune-beheerconsole waarop de Lookout for Work-app wordt weergegeven](../media/mtp/lookout-app-listed-intune-console.png)

U kunt **de app bij gebruikers implementeren** door de Lookout for Work-app te selecteren die op het scherm hierboven wordt weergegeven en vervolgens **Implementatie beheren** te selecteren.

U moet dezelfde gebruikers selecteren die zijn toegevoegd aan de optie Registratiebeheer in de Lookout MTP-console.  Zie stap 3 in de sectie [Uw abonnement configureren met Lookout MTP](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp) voor informatie over het toevoegen van gebruikersgroepen aan Lookout MTP.
>[!IMPORTANT]
> De implementatiewizard van Intune app is niet op de hoogte van de Azure AD-gebruikersgroepen en maakt in plaats daarvan gebruik van de Intune-gebruikersgroepen. Daarom moet u een Intune-gebruikersgroep maken op basis van de Azure AD-gebruikersgroep die is geregistreerd in de Lookout MTP-console, zoals beschreven in [dit](plan-your-user-and-device-groups.md) onderwerp.

Kies de optie **Vereiste installatie** om te vereisen dat de Lookout-app op het apparaat van de gebruiker wordt geïnstalleerd.


Als de optie **Vereiste installatie** is geselecteerd voor implementatie, wordt de Lookout for Work-toepassing met Intune naar het apparaat gepusht.   

Wanneer de gebruiker de Lookout for Work-app opent op het apparaat, wordt de gebruiker gevraagd de app te activeren en de optie Aanmelden bij Azure Active Directory te kiezen. Een gedetailleerd overzicht van de eindgebruikersstroom vindt u in de volgende onderwerpen:

* [U wordt gevraagd Lookout for Work te installeren op uw Android-apparaat](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [U moet een bedreiging oplossen die met Lookout for Work op een Android-apparaat is gevonden](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## Volgende stappen
* [De regel Device Threat Protection inschakelen in het nalevingsbeleid](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Sep16_HO3-->


