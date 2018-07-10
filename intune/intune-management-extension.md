---
title: PowerShell-scripts in Microsoft Intune toevoegen voor Windows 10-apparaten - Azure | Microsoft Docs
description: Voeg PowerShell-scripts toe, wijs het scriptbeleid toe aan Azure Active Directory-groepen, gebruik rapporten om de scripts te controleren en zie de stappen om scripts te verwijderen die u toevoegt op Windows 10-apparaten in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: eb7d8b35cb88223a3fbfa45e0ad8e2f8d2852a96
ms.sourcegitcommit: ab801d715aa26f6d97f1a0c42a07e55146a14e6f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2018
ms.locfileid: "35289020"
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>PowerShell-scripts in Intune beheren voor Windows 10-apparaten
Met de Intune-beheeruitbreiding kunt u PowerShell-scripts uploaden in Intune om deze uit te voeren op Windows 10-apparaten. De beheeruitbreiding is een aanvulling op de Windows 10 MDM-functionaliteit en maakt het eenvoudiger voor u om uw beheer te moderniseren.

## <a name="moving-to-modern-management"></a>Uw beheer moderniseren
Computergebruik door de eindgebruiker ondergaat een digitale transformatie. Klassieke, traditionele IT richt zich op een platform voor een enkel apparaat, apparaten in bedrijfseigendom, gebruikers die vanuit hun kantoor werken en tal van handmatige, reactieve IT-processen. De moderne werkplek maakt echter platformen mogelijk voor meerdere apparaten die in eigendom zijn van de gebruiker en het bedrijf, waarmee gebruikers vanuit elke locatie kunnen werken en die voorzien in geautomatiseerde en proactieve IT-processen. 

Met MDM-services, zoals Microsoft Intune, kunt u Windows 10-apparaten beheren met behulp van het MDM-protocol. De ingebouwde Windows 10-beheerclient kan met Intune communiceren voor de uitvoering van bedrijfsbeheertaken. Hiermee komt modern beheer op Windows 10-apparaten een stap dichterbij. Er is echter bepaalde functionaliteit die u misschien nodig hebt, zoals geavanceerde apparaatconfiguratie, het oplossen van problemen en het beheer van verouderde Win32-apps die momenteel niet beschikbaar is in Windows 10-MDM. U kunt voor deze functionaliteit de Intune-softwareclient uitvoeren op uw Windows 10-apparaten. Als gevolg hiervan kunt u niet nieuwe functionaliteit gebruiken waarin Windows 10-MDM voorziet. [Vergelijk de verschillen tussen de Intune-softwareclient en Windows 10-MDM](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison).

De extensie van de Intune-management is een aanvulling op de meegeleverde Windows 10-MDM-functionaliteit. U kunt PowerShell-scripts maken die u kunt uitvoeren op de Windows 10-apparaten die de functionaliteit bieden die u nodig hebt. U kunt bijvoorbeeld een PowerShell-script maken dat een verouderde Win32-app op uw Windows 10-apparaten installeert, het script uploadt naar Intune, het script toewijst aan een Azure Active Directory (AD) en het script uitvoert op Windows 10-apparaten. U kunt vervolgens de uitvoeringsstatus van het script op Windows 10-apparaten van begin tot eind controleren.

## <a name="prerequisites"></a>Vereisten
De Intune-beheeruitbreiding heeft de volgende vereisten:
- Apparaten moeten zijn gekoppeld aan Azure AD. Dit omvat geen apparaten die aan Hybrid AD zijn toegevoegd.
- Op apparaten moet Windows 10 versie 1607 of hoger worden uitgevoerd.
- Automatische MDM-inschrijving moet zijn [ingeschakeld in Azure AD](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment) en apparaten moeten automatisch worden geregistreerd bij Intune.

## <a name="create-a-powershell-script-policy"></a>Een PowerShell-scriptbeleid maken 
1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaatconfiguratie** > **PowerShell-scripts** > **Toevoegen**.
4. Voer een **naam** en **beschrijving** in voor het PowerShell-abonnement. Blader voor de **Scriptlocatie** naar het PowerShell-script. Het script moet kleiner zijn dan 200 kB (ASCII) of 100 kB (Unicode).
5. Kies **Configureren**. Kies vervolgens of het script wel of niet met de referenties van de gebruiker op het apparaat moet worden uitgevoerd (**Ja**) of systeemcontext (**Nee**). Het script wordt standaard uitgevoerd in de systeemcontext. Selecteer **Ja** tenzij het noodzakelijk is dat het script wordt uitgevoerd in de systeemcontext. 
  ![Het deelvenster PowerShell-script toevoegen](./media/mgmt-extension-add-script.png)
6. Kies of het script moet worden ondertekend door een vertrouwde uitgever (**Ja**). Standaard hoeft het script niet te worden ondertekend. 
7. Selecteer **OK** en vervolgens **Maken** om het script op te slaan.

## <a name="assign-a-powershell-script-policy"></a>Een PowerShell-scriptbeleid toewijzen
1. Selecteer in **PowerShell-scripts** het script dat u wilt toewijzen, en kies vervolgens **Beheren** > **Toewijzingen**.
  ![Het deelvenster PowerShell-script toevoegen](./media/mgmt-extension-assignments.png)
 
2. Kies **Groepen selecteren** beschikbare Microsoft Azure Active Directory-groepen in een lijst op te nemen. 
3. Selecteer een of meer groepen die de gebruikers bevatten wiens apparaten het script ontvangen. Kies **Selecteren** om het beleid aan de geselecteerde groepen toe te wijzen.

> [!NOTE]
> - PowerShell-scripts kunnen niet worden toegepast op computergroepen.
> - PowerShell-scripts worden alleen uitgevoerd op apparaten als een AD-gebruiker (Azure Active Directory) is aangemeld op het apparaat.

De Intune-beheeruitbreiding wordt eenmaal per uur met Intune gesynchroniseerd. Wanneer u het beleid aan de Microsoft Azure Active Directory-groepen toewijst, wordt het PowerShell-script uitgevoerd en worden de resultaten van de uitvoering gerapporteerd. 
 
## <a name="monitor-run-status-for-powershell-scripts"></a>Uitvoeringsstatus van de PowerShell-scripts controleren
U kunt de uitvoeringsstatus van PowerShell-scripts voor gebruikers en apparaten in Azure Portal controleren.

Selecteer in **PowerShell-scripts** het script dat u wilt controleren, kies **Controleren** en kies vervolgens een van de volgende rapporten:
   - **Apparaatstatus**
   - **Gebruikersstatus**

## <a name="delete-a-powershell-script"></a>Een PowerShell-script verwijderen
Klik in **PowerShell-scripts** met de rechtermuisknop op het script en selecteer **Verwijderen**.
