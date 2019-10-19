---
title: Android-apparaat versleutelen voor intune | Microsoft Docs
description: Stappen voor het inschakelen van de versleuteling van Android-apparaten wanneer dit vereist is door intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: d4430e92-04cc-48e9-a77a-81b95a90b6b3
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: d2965d6a017d92bd4535a29a2257c0cac5e6deaf
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506361"
---
# <a name="encrypting-your-android-device"></a>Uw Android-apparaat versleutelen

Met apparaatversleuteling worden uw bestanden en mappen beschermd tegen onbevoegde toegang als uw apparaat is vermist of gestolen. Nadat u apparaatversleuteling hebt ingeschakeld, kunnen alleen personen met het juiste wacht woord of de pincode zich aanmelden bij uw apparaat. 

Voordat u toegang krijgt tot school-of werk resources, moet u mogelijk uw Android-apparaat versleutelen met uw organisatie. Sommige nieuwere Android-apparaten worden standaard versleuteld.  

## <a name="turn-on-encryption"></a>Versleuteling inschakelen

Als Bedrijfsportal of de Microsoft Intune app u vraagt om uw apparaat te versleutelen, voert u de volgende stappen uit. 

> [!Note]
> Bepaalde Android-apparaten van Huawei, vivo en OPPO kunnen niet worden versleuteld. Zie [hier](your-device-appears-encrypted-but-cp-says-otherwise-android.md) voor meer informatie.  

1. Stel een scherm vergrendeling voor het apparaat in.  
    a. Ga naar **Instelling** > **Vergrendelscherm en beveiliging** > **Type schermvergrendeling**.  
    b. Selecteer **pincode**, **wacht woord**of **patroon**.  
    c. Volg de instructies op het scherm voor het configureren van de beeldscherm vergrendeling.  

2. Ga terug naar het **vergrendelings scherm en de beveiliging** en selecteer **beveiligd opstarten**.
3. Kies **pincode vereisen wanneer het apparaat** wordt ingeschakeld  > **OK**.
4. Voer uw pincode in om uw apparaat te bevestigen en te versleutelen.
5. Open de app Bedrijfsportal of Microsoft Intune.
    * Gebruikers van de bedrijfsportal: selecteer uw apparaat en tik op **Apparaatinstellingen controleren**. 
    * Microsoft Intune gebruikers: u moet wachten tot de pagina wordt bijgewerkt, maar als dit wel het geval is, wordt de versleutelings status gewijzigd in compatibel.  

Op apparaten met Android 4,4 en eerder wordt mogelijk niet de optie voor **beveiligd opstarten** gebruikt. In dat geval voert u de volgende stappen uit om uw apparaat te versleutelen.

1. Ga naar **instellingen**  > **beveiliging**  > **apparaat versleutelen**. Labels op het scherm zijn afhankelijk van Android-apparaten. Als u de optie **apparaat versleutelen** niet ziet, controleert u het volgende:
    * **Opslag**  > **opslag versleuteling**
    * **Opslag**  > **vergrendelings scherm en beveiligings**  > **andere beveiligings instellingen** 

2. Volg de instructies op het scherm. Tijdens het versleutelen wordt het apparaat mogelijk meerdere keren opnieuw opgestart.
3. Open de app Bedrijfsportal of Microsoft Intune.
    * Gebruikers van de bedrijfsportal: selecteer uw apparaat en tik op **Apparaatinstellingen controleren**.  
    * Microsoft Intune gebruikers: u moet wachten tot de pagina wordt bijgewerkt, maar als dit wel het geval is, wordt de versleutelings status gewijzigd in compatibel.

## <a name="troubleshoot"></a>Problemen oplossen  
**Probleem**: u hebt uw apparaat al versleuteld en

- De versleutelingsknop is uitgeschakeld.
- Er wordt een bericht weergegeven dat u nog moet versleutelen.
- U krijgt fouten bij het gebruik van de Bedrijfsportal-of Microsoft Intune-app.

**Wat u kunt doen**

- Zorg dat het apparaat is geladen en aangesloten.  
- Zorg ervoor dat u een pincode of wachtwoord hebt ingesteld op het apparaat.  

Nog hulp nodig? Neem contact op met het ondersteuningsteam van het bedrijf (zie de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980) voor contactgegevens) of stuur een e-mail naar het <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with encryption on my Android device&body=Describe the issue you're experiencing here.">Microsoft Android-team</a>.  
