---
title: Android-apparaat versleutelt voor Intune | Microsoft Docs
description: Stappen voor het Android-apparaat-versleuteling indien nodig door Intune inschakelen
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: cfc17c60412a1cfe90693216caa69ada3d2d2c9a
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2019
ms.locfileid: "67545247"
---
# <a name="encrypting-your-android-device"></a>Uw Android-apparaat versleutelen

Apparaatversleuteling beschermt uw bestanden en mappen tegen onbevoegde toegang als uw apparaat is zoekgeraakt of gestolen. Nadat u apparaatversleuteling inschakelen, zich alleen de personen met het juiste wachtwoord of pincode aanmelden bij uw apparaat. 

Voordat u toegang hebt school of werk resources, uw organisatie moet u mogelijk voor het versleutelen van uw Android-apparaat. Sommige nieuwere Android-apparaten worden versleuteld standaard out-of-the-box.  

## <a name="turn-on-encryption"></a>Versleuteling inschakelen

Als de bedrijfsportal of de Microsoft Intune-app u uw apparaat versleutelt vraagt, kunt u de volgende stappen. 

> [!Note]
> Bepaalde Android-apparaten van Huawei, Vivo en OPPO, kunnen niet worden versleuteld. Zie [hier](your-device-appears-encrypted-but-cp-says-otherwise-android.md) voor meer informatie.  

1. Stel een apparaat voor het vergrendelde scherm.  
    a. Ga naar **Instelling** > **Vergrendelscherm en beveiliging** > **Type schermvergrendeling**.  
    b. Selecteer een **PINCODE**, **wachtwoord**, of **patroon**.  
    c. Volg de instructies op het scherm uw schermvergrendeling configureren.  

2. Ga terug naar **scherm vergrendelen en beveiliging** en selecteer **beveiligd opstarten**.
3. Kies **PINCODE vereisen wanneer het apparaat wordt ingeschakeld** > **OK**.
4. Voer uw PINCODE in om te bevestigen en uw apparaat versleutelen.
5. Open de bedrijfsportal of de Microsoft Intune-app.
    * Gebruikers van de bedrijfsportal: selecteer uw apparaat en tik op **Apparaatinstellingen controleren**. 
    * Microsoft Intune-gebruikers: U hoeft te wachten tot de pagina-updates, maar als dit wel gebeurt, de versleutelingsstatus van uw te voldoen aan het beleid moet wijzigen.  

Apparaten met Android 4.4 en eerder niet mogelijk de **beveiligd opstarten** optie. In dat geval wordt de volgende stappen voor het versleutelen van uw apparaat.

1. Ga naar **instellingen** > **Security** >  **-apparaat versleutelt**. Op het scherm labels verschillen tussen de Android-apparaten. Als er geen de **apparaat versleutelen** optie, controleert u:
    * **Opslag** > **versleuteling van opslag**
    * **Opslag** > **scherm vergrendelen en beveiliging** > **overige beveiligingsinstellingen** 

2. Volg de instructies op het scherm. Tijdens het versleutelen wordt het apparaat mogelijk meerdere keren opnieuw opgestart.
3. Open de bedrijfsportal of de Microsoft Intune-app.
    * Gebruikers van de bedrijfsportal: selecteer uw apparaat en tik op **Apparaatinstellingen controleren**.  
    * Microsoft Intune-gebruikers: U hoeft te wachten tot de pagina-updates, maar als dit wel gebeurt, de versleutelingsstatus van uw te voldoen aan het beleid moet wijzigen.

## <a name="troubleshoot"></a>Problemen oplossen  
**Probleem**: U hebt uw apparaat al versleuteld en

- De versleutelingsknop is uitgeschakeld.
- Er wordt een bericht weergegeven dat u nog moet versleutelen.
- Er treden fouten op bij het gebruik van de bedrijfsportal of de Microsoft Intune-app.

**Wat u kunt doen**

- Zorg dat het apparaat is geladen en aangesloten.  
- Zorg ervoor dat u een pincode of wachtwoord hebt ingesteld op het apparaat.  

Nog hulp nodig? Neem contact op met het ondersteuningsteam van het bedrijf (zie de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980) voor contactgegevens) of stuur een e-mail naar het <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with encryption on my Android device&body=Describe the issue you're experiencing here.">Microsoft Android-team</a>.  
