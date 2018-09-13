---
title: De wachtwoordcode opnieuw instellen op de website van de bedrijfsportal | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 8ce71a14f9bb7e877fb31e78afdf64d5e492f4a8
ms.sourcegitcommit: 490365fb8b5405f323b4358fb1ec9dfdd9ff2d58
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2018
ms.locfileid: "43146686"
---
# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>De wachtwoordcode van uw apparaat opnieuw instellen op de website van de bedrijfsportal

Als u de pincode of het wachtwoord van uw apparaat bent vergeten, kunt u de [bedrijfsportalwebsite](https://portal.manage.microsoft.com) gebruiken om de pincode of het wachtwoord opnieuw in te stellen.  

Als u een apparaat in bedrijfseigendom gebruikt, ziet u misschien niet de optie voor het opnieuw instellen van de wachtwoordcode van uw apparaat. Neem contact op met het ondersteuningsteam van het bedrijf om de wachtwoordcode opnieuw in te stellen.

   > [!NOTE]
   > Het is niet mogelijk om wachtwoordcodes voor apparaten met Android 7.0 en hoger opnieuw in te stellen. U moet het apparaat naar de fabrieksinstellingen terugzetten als u de wachtwoordcode bent vergeten. 

## <a name="reset-your-passcode"></a>Uw wachtwoordcode opnieuw instellen

1.  Open de [bedrijfsportalwebsite](https://portal.manage.microsoft.com) en selecteer de knop __Menu__ > __Apparaten__.  

2. Selecteer het apparaat waarvoor de wachtwoordcode opnieuw moet worden ingesteld.  

    ![Een schermafbeelding van de pagina Apparaten, met 2 tegels met niet-geïdentificeerde apparaten met een algemene naam. Direct onder de apparaten wordt een grijze banner weergegeven. Er wordt gevraagd welk apparaat de gebruiker gebruikt of dat de gebruiker een nieuw apparaat wil toevoegen.](./media/rename-reset-device-step2-1808.png) 

3. Selecteer **Wachtwoordcode opnieuw instellen**. Als de optie wachtwoordcode niet worden weergegeven aan de bovenkant van de pagina, selecteert u **Meer (...)**   >  **Wachtwoordcode opnieuw instellen**.   

   ![De pagina met apparaatgegevens van een geselecteerd apparaat op de bedrijfsportalwebsite, met een lijst met bovenaan koppelingen als Naam wijzigen, Verwijderen, Apparaat opnieuw instellen, Wachtwoordcode opnieuw instellen en Extern vergrendelen. ](./media/rename-reset-device-1808.png)   

    ![Weergave door in te zoomen op het pictogram Meer, gemarkeerd met een rode pijl.](./media/rename-reset-device-step3-more-1808.png)  

4. Klik desgevraagd op **Afmelden**. Wanneer u opnieuw wordt gevraagd, meldt u zich weer aan. U moet zich binnen vijf minuten opnieuw aanmelden bij de bedrijfsportalwebsite, anders wordt de wachtwoordcode niet opnieuw ingesteld door de bedrijfsportal-app.  

   > [!NOTE]
   > U moet zich opnieuw aanmelden om uw identiteit te bevestigen. Hiermee worden pogingen van kwaadwillenden voorkomen om de wachtwoordcode van uw apparaat opnieuw in te stellen.

   ![Voorbeeldschermafbeeldingen van een prompt om zich af te melden bij de bedrijfsportal-app. De knoppen voor invoer van de gebruiker zijn Afmelden en Annuleren.](./media/iwp-reset-passcode-popup-1808.png)

5. Er wordt een bericht weergegeven om u te waarschuwen dat de bestaande wachtwoordcode wordt verwijderd. Klik op **Wachtwoordcode opnieuw instellen** om te bevestigen.  
    > [!WARNING]
    > Nadat u uw wachtwoordcode opnieuw hebt ingesteld, krijgt iedereen die fysieke toegang tot het apparaat heeft toegang tot de meest persoonlijke en zakelijke gegevens op dit apparaat. Stel de wachtwoordcode niet opnieuw in als u het apparaat op dit moment niet in uw bezit hebt.  

   ![Voorbeeld-schermafbeelding van het tweede bericht voor het opnieuw instellen van wachtwoordcode. Bevat de koppeling voor meer informatie over het instellen van een nieuwe wachtwoordcode in de documentatie, en de afzonderlijke knoppen voor het opnieuw instellen van de wachtwoordcode en voor annuleren.](./media/iwp-reset-passcode-popup2-1808.png) 

6. Als u de wachtwoordcode voor een iOS-apparaat opnieuw instelt, wordt de bestaande wachtwoordcode verwijderd. Voor Windows- of Android-apparaten krijgt u een tijdelijke wachtwoordcode voor het ontgrendelen van het apparaat en het instellen van een nieuwe wachtwoordcode. 

   > [!NOTE]
   > Het tijdelijke wachtwoord voor Windows- en Android-apparaten is te vinden in de bedrijfsportal-app, onder de pagina met apparaatgegevens. Zie de sectie [Een nieuwe wachtwoordcode instellen](reset-your-passcode-cpwebsite.md#set-up-a-new-passcode) voor wachtwoordcodebeschrijvingen die meer specifiek zijn voor besturingssystemen.  
   
7. Ga op uw apparaat naar **Instellingen** en wijzig de tijdelijke wachtwoordcode. 

8. Er wordt een vlag weergegeven in de rechterbovenhoek van de bedrijfsportalwebsite. Klik erop om de melding te lezen en te bevestigen dat het wachtwoord opnieuw is ingesteld.  

## <a name="set-up-a-new-passcode"></a>Een nieuwe wachtwoordcode instellen  

Deze sectie beschrijft het opnieuw instellen van de wachtwoordcode en het gedrag van het tijdelijke wachtwoord voor elk apparaatplatform.  

**Android**: de bestaande wachtwoordcode wordt verwijderd en er wordt een tijdelijke wachtwoordcode gemaakt die bestaat uit letters en cijfers.

**iOS**: de bestaande wachtwoordcode wordt verwijderd en er wordt geen tijdelijke wachtwoordcode gemaakt. Als u de Touch ID-vingerafdrukscanner gebruikt voor het openen van uw apparaat of om aankopen te doen, moet u deze opnieuw instellen.  

**Windows 10 Mobile**: de bestaande wachtwoordcode wordt verwijderd en er wordt een tijdelijke wachtwoordcode gemaakt die bestaat uit letters en cijfers. Als deze is ingesteld, zal Windows Hello-gezichtsherkenning nog steeds met het apparaat werken.
    
**Windows Phone 8.1**: de bestaande wachtwoordcode wordt verwijderd en er wordt een tijdelijke wachtwoordcode gemaakt die bestaat uit cijfers.  

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Controleer of de contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).  
