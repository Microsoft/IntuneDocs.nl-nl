---
title: PowerShell-scripts in Intune beheren voor Windows 10-apparaten
titlesuffix: Azure portal
description: Informatie over het uploaden van PowerShell-scripts in Intune om deze uit te voeren op Windows 10-apparaten.
keywords: 
author: dougeby
manager: dougeby
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e8c959ca3df62cbda17e5a659d0703cbc37f3249
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>PowerShell-scripts in Intune beheren voor Windows 10-apparaten
Met de Intune-beheeruitbreiding kunt u PowerShell-scripts uploaden in Intune om deze uit te voeren op Windows 10-apparaten. De beheeruitbreiding is een aanvulling op de Windows 10 MDM-functionaliteit en maakt het eenvoudiger voor u om uw beheer te moderniseren.

## <a name="moving-to-modern-management"></a>Uw beheer moderniseren
Computergebruik door de eindgebruiker ondergaat een digitale transformatie. Klassieke, traditionele IT richt zich op een platform voor een enkel apparaat, apparaten in bedrijfseigendom, gebruikers die vanuit hun kantoor werken en tal van handmatige, reactieve IT-processen. De moderne werkplek maakt echter platformen mogelijk voor meerdere apparaten die in eigendom zijn van de gebruiker en het bedrijf, waarmee gebruikers vanuit elke locatie kunnen werken en die voorzien in geautomatiseerde en proactieve IT-processen. 

Met MDM-services, zoals Microsoft Intune, kunt u Windows 10-apparaten beheren met behulp van het MDM-protocol. De ingebouwde Windows 10-beheerclient kan met Intune communiceren voor de uitvoering van bedrijfsbeheertaken. Hiermee komt modern beheer op Windows 10-apparaten een stap dichterbij. Er is echter bepaalde functionaliteit die u misschien nodig hebt, zoals geavanceerde apparaatconfiguratie, het oplossen van problemen en het beheer van verouderde Win32-apps die momenteel niet beschikbaar is in Windows 10-MDM. U kunt voor deze functionaliteit de Intune-softwareclient uitvoeren op uw Windows 10-apparaten. Als gevolg hiervan kunt u niet nieuwe functionaliteit gebruiken waarin Windows 10-MDM voorziet. [Vergelijk de verschillen tussen de Intune-softwareclient en Windows 10-MDM](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison).

De extensie van de Intune-management is een aanvulling op de meegeleverde Windows 10-MDM-functionaliteit. U kunt PowerShell-scripts maken die u kunt uitvoeren op de Windows 10-apparaten die de functionaliteit bieden die u nodig hebt. U kunt bijvoorbeeld een PowerShell-script maken dat een verouderde Win32-app op uw Windows 10-apparaten installeert, het script uploadt naar Intune, het script toewijst aan een Azure Active Directory (AD) en het script uitvoert op Windows 10-apparaten. U kunt vervolgens de uitvoeringsstatus van het script op Windows 10-apparaten van begin tot eind controleren.

## <a name="prerequisites"></a>Vereisten
De Intune-beheeruitbreiding heeft de volgende vereisten:
- Apparaten moeten gekoppeld zijn aan Microsoft Azure Active Directory
- Op apparaten moet Windows 10 versie 1607 of hoger worden uitgevoerd

## <a name="create-a-powershell-script-policy"></a>Een PowerShell-scriptbeleid maken 
1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies op de blade **Intune** de optie **Apparaatconfiguratie**.
4. Kies **Beheren** > **PowerShell-scripts** op de blade **Apparaatconfiguratie**.
5. Kies op de blade **PowerShell-scripts** **Script toevoegen**.
6. Voer op de blade **PowerShell-script toevoegen** een **naam** en **beschrijving** in voor het PowerShell-script.
7. Blader voor de **Scriptlocatie** naar het PowerShell-script. Het script moet kleiner zijn dan 10 KB (ASCII) of 5 KB (Unicode).
8. Kies **Configureren**, en kies vervolgens of het script wel of niet met de referenties van de gebruiker op het apparaat moet worden uitgevoerd (**Ja**) of systeemcontext (**Nee**). Het script wordt standaard uitgevoerd in de systeemcontext. Selecteer **Ja** tenzij het noodzakelijk is dat het script wordt uitgevoerd in de systeemcontext. 
  ![Het PowerShell-script toevoegen](./media/mgmt-extension-add-script.png)
9. Kies of het script wel of niet moet worden ondertekend door een vertrouwde uitgever (**Ja**). Standaard hoeft het script niet te worden ondertekend. 
10. Klik op **OK** en klik vervolgens op **Maken** om het script op te slaan.

## <a name="assign-a-powershell-script-policy"></a>Een PowerShell-scriptbeleid toewijzen
1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies op de blade **Intune** de optie **Apparaatconfiguratie**.
4. Kies **Beheren** > **PowerShell-scripts** op de blade **Apparaatconfiguratie**.
5. Selecteer op de blade **PowerShell-scripts** het script dat u wilt toewijzen, en kies vervolgens **Beheren** > **Toewijzingen**.
  ![De blade PowerShell-script toevoegen](./media/mgmt-extension-assignments.png)
 
6. Kies **Groepen selecteren** beschikbare Microsoft Azure Active Directory-groepen in een lijst op te nemen. 
7. Selecteer een of meer groepen met daarin de gebruikers van wie de apparaten het script ontvangen en klik vervolgens op **Selecteren** om het beleid toe te wijzen aan de geselecteerde groepen.

De Intune-beheeruitbreiding wordt eenmaal per uur met Intune gesynchroniseerd. Wanneer u het beleid aan de Microsoft Azure Active Directory-groepen toewijst, wordt het PowerShell-script uitgevoerd en worden de resultaten van de uitvoering gerapporteerd. 
 
## <a name="monitor-run-status-for-powershell-scripts"></a>Uitvoeringsstatus van de PowerShell-scripts controleren
U kunt de uitvoeringsstatus van PowerShell-scripts voor gebruikers en apparaten in Azure Portal controleren.
1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies op de blade **Intune** de optie **Apparaatconfiguratie**.
4. Kies **Beheren** > **PowerShell-scripts** op de blade **Apparaatconfiguratie**.
5. Selecteer op de blade **PowerShell-scripts** het script dat u wilt controleren en kies daarna **Controleren**, en vervolgens een van de volgende rapporten:
   - **Apparaatstatus**
   - **Gebruikersstatus**
