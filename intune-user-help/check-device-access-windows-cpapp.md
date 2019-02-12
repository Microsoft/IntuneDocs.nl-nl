---
title: Apparaattoegang controleren | Microsoft Docs
description: Controleer de apparaattoegang om te ontdekken of uw apparaat voldoet aan de vereisten en er toegang kan worden verkregen tot werk- of schoolresources.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1b4c1575c72e0563c4c55e262756c9b4aa0eddde
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55848199"
---
# <a name="check-access-from-company-portal-app-for-windows"></a>Controleren op toegang vanuit de bedrijfsportal-app voor Windows

Controleer of met uw apparaat toegang kan worden verkregen tot werk- of schoolresources. 

Organisaties leggen eisen&ndash;zoals versleuteling en wachtwoordlimieten&ndash; op om er zeker van te zijn dat alleen veilige en vertrouwde apparaten toegang hebben tot hun gegevens. Beheerde apparaten moeten blijven voldoen aan de vereisten om toegang te verkrijgen tot de resources van de organisatie.

Met de actie **Toegang controleren** worden de instellingen van het apparaat en de toegangsstatus beoordeeld. Op de pagina **Apparaatdetails** staan de instellingen die u moet wijzigen om weer toegang te verkrijgen. 

Voltooi de stappen in dit artikel om toegang via de bedrijfsportal-app voor Windows te controleren.  

## <a name="check-access-from-device-details-page"></a>Toegang controleren vanaf de pagina Apparaatdetails  
1. Open de bedrijfsportal-app voor Windows en ga naar **Mijn apparaten**.  

    ![Voorbeeldschermopname van de bedrijfsportal-app voor Windows: de startpagina met het gedeelte Mijn apparaten gemarkeerd.](./media/1809_CheckAccess_Context_Select_Device.png)  
2. Selecteer een apparaat.  
3. Selecteer op de pagina **Apparaatdetails** de optie **Toegang controleren**. De app synchroniseert de huidige vereisten van de organisatie met uw apparaat en voert een controle uit om er zeker van te zijn dat het apparaat aan de eisen voldoet. Deze controle kan enkele minuten duren.  

    ![Voorbeeldschermopname van de bedrijfsportal-app voor Windows: de pagina Apparaatdetails, met de knop Toegang controleren gemarkeerd.](./media/1809_CheckAccess_Checking_Status.png) 

4. Bekijk de statusupdate. U ziet dat uw apparaat **toegang heeft tot de resources van de organisatie** of dat deze **geen toegang heeft tot de resources van de organisatie**.  

   ![Voorbeeldschermopname van de bedrijfsportal-app voor Windows: de pagina Apparaatdetails, met het gedeelte Status gemarkeerd.](./media/1809_CheckAccess_Device_details_status1.png)  
   
5. Als u met uw apparaat geen toegang hebt tot resources, gaat u naar de waarschuwing boven in de pagina. Klik op **Meer** om de details uit te vouwen. Klik op **Minder** om ze samen te vouwen.  

    ![Voorbeeldschermopname van de bedrijfsportal-app voor Windows: de pagina Apparaatdetails, met de waarschuwing boven in de pagina gemarkeerd.](./media/1809_CheckAccess_Device_details_alert1.png)  

6. Indien van toepassing worden in het bericht koppelingen voor extra hulp en acties voor herstel weergegeven. Selecteer een of meer van deze opties om direct te beginnen met het oplossen van de problemen. De acties voor oplossen, synchroniseren en contact&ndash;die hieronder worden beschreven&ndash;zijn alleen zichtbaar als u de bedrijfsportal op het betreffende apparaat gebruikt.  

     * **Het probleem oplossen** leidt naar een relevant Help-artikel (als er een beschikbaar is).  
     * **Oplossen** leidt u naar de instelling op uw apparaat.  
     * **Synchroniseren** wordt gebruikt om uw apparaat te beoordelen. Er wordt gecontroleerd of het aan de vereisten van de organisatie voldoet.  
     * **Contact opnemen met IT** leidt naar de contactgegevens van het IT-team.   
 
6. Wanneer u de instellingen hebt bijgewerkt, klikt u op **Toegang controleren** om de status van het apparaat te bepalen.  

    ![Voorbeeldschermopname van de bedrijfsportal-app voor Windows: de pagina Apparaatdetails, met het gedeelte Status gemarkeerd.](./media/1809_CheckAccess_Device_details_status1.png)  

## <a name="check-access-from-device-context-menu"></a>Toegang controleren vanuit het contextmenu van het apparaat  
1. Open de bedrijfsportal-app voor Windows en ga naar **Mijn apparaten**.  

    ![Voorbeeldschermopname van de bedrijfsportal-app voor Windows: de startpagina met het gedeelte Mijn apparaten gemarkeerd.](./media/1809_CheckAccess_Context_Select_Device.png)  

2. Klik met de rechtermuisknop op een apparaat of houd het apparaat ingedrukt om het [contextmenu](https://docs.microsoft.com//windows/uwp/design/controls-and-patterns/menus) hiervan te openen.  

    ![Voorbeeldschermopname van de bedrijfsportal-app voor Windows: de startpagina. Het contextmenu van het apparaat kan worden bekeken in het gedeelte **Mijn apparaten** van de pagina. Hier ziet u de acties Naam wijzigen, Verwijderen en Toegang controleren.](./media/1809_DeviceContextMenu_Windows_CP.png)  
3. Selecteer **Toegang controleren**. De app synchroniseert de huidige vereisten van de organisatie met uw apparaat en voert een controle uit om er zeker van te zijn dat het apparaat aan de eisen voldoet. Deze controle kan enkele minuten duren.  
 
4. Er wordt onder het apparaat een bericht weergegeven om u te laten weten dat het apparaat **toegang heeft tot bedrijfsresources** of **geen toegang heeft tot bedrijfsresources**. 

    ![Voorbeeldschermopname van de bedrijfsportal-app voor Windows: de pagina Apparaatdetails, met het gedeelte Status gemarkeerd.](./media/1809_CheckAccess_Context_Menu_Alert2.png) 

5. Als uw apparaat geen toegang heeft tot resources, selecteert u het apparaat.  
6. Op de pagina **Apparaatdetails** gaat u aan de bovenkant van de pagina naar de waarschuwing. Klik op **Meer** om de details uit te vouwen. Klik op **Minder** om ze samen te vouwen.  

    ![Voorbeeldschermopname van de bedrijfsportal-app voor Windows: de pagina Apparaatdetails, met de waarschuwing boven in de pagina gemarkeerd.](./media/1809_CheckAccess_Device_details_alert1.png)  

6. Indien van toepassing worden in het bericht koppelingen voor extra hulp en acties voor herstel weergegeven. Selecteer een of meer van deze opties om direct te beginnen met het oplossen van de problemen. De acties voor oplossen, synchroniseren en contact&ndash;die hieronder worden beschreven&ndash;zijn alleen zichtbaar als u de bedrijfsportal op het betreffende apparaat gebruikt.  

     * **Het probleem oplossen** leidt naar een relevant Help-artikel (als er een beschikbaar is).  
     * **Oplossen** leidt u naar de instelling op uw apparaat.  
     * **Synchroniseren** wordt gebruikt om uw apparaat te beoordelen. Er wordt gecontroleerd of het aan de vereisten van de organisatie voldoet.  
     * **Contact opnemen met IT** leidt naar de contactgegevens van het IT-team.    

7. Wanneer u de instellingen hebt bijgewerkt, klikt u op **Toegang controleren** aan de onderkant van de pagina.  

    ![Voorbeeldschermopname van de bedrijfsportal-app voor Windows: de pagina Apparaatdetails, met de actie Toegang controleren gemarkeerd.](./media/1809_CheckAccess_Device_details_button.png) 


Meer hulp nodig? Ga naar de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980) voor de contactgegevens van het ondersteuningsteam van uw bedrijf.
