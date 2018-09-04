---
title: Uw bedrijfsapparaat of macOS-apparaat inschrijven bij beheer | Microsoft Docs
description: Hier wordt beschreven hoe u een macOS-apparaat inschrijft bij Intune dat is aangeschaft en geleverd door uw organisatie.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: japoehlm
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 272a82f7d3d62d117fa5506ccf446b3169ff514f
ms.sourcegitcommit: bb56ada81e6d4950f130415918c4acc455bb52dd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/27/2018
ms.locfileid: "43016224"
---
# <a name="get-your-company-owned-macos-device-managed"></a>Uw macOS-apparaat van het bedrijf laten beheren

Informatie over een nieuw macOS-apparaat automatisch laten beheren in Intune.

Werk- en schoolapparaten zijn vaak vooraf geconfigureerd voordat u ze ontvangt. Uw organisatie verzendt vooraf geconfigureerde instellingen naar uw apparaat wanneer u het inschakelt en u voor de eerste keer aanmeldt. Nadat de installatie op het apparaat is voltooid, krijgt u toegang tot werk- of schoolresources. 

U kunt beheer instellen door uw apparaat in te schakelen en u aan te melden met de referenties van uw werk- of schoolaccount. In de rest van dit artikel worden de stappen en de schermen beschreven die u ziet terwijl u de configuratieassistent uitvoert.   

## <a name="what-is-apple-dep"></a>Wat is Apple DEP?
Als u een bedrijfsapparaat hebt, is dit mogelijk aangeschaft via het Apple Device Enrollment Program (DEP). Sommige organisaties kopen grote hoeveelheden iOS- of macOS-apparaten via Apple DEP. Organisaties kunnen apparaten vervolgens configureren en beheren in hun favoriete provider voor mobiele apparaatbeheer, zoals Intune. Als u beheerder bent en meer informatie wilt over Apple DEP, zie [MacOS-apparaten automatisch inschrijven met Apple Device Enrollment Program](https://docs.microsoft.com/intune/device-enrollment-program-enroll-macos).  

## <a name="set-up-your-macos-device"></a>MacOS-apparaten inschrijven  
Voer de volgende stappen uit om uw macOS-apparaat voor beheer in te schrijven. Als u uw eigen apparaat gebruikt, in plaats van een bedrijfsapparaat, volgt u de stappen voor [persoonlijke en bring-your-own-apparaten](enroll-your-device-in-intune-macos-cp.md).  

1. Schakel uw macOS-apparaat in. 
2. Kies uw **taal** en klik op **Doorgaan**.  

   ![Schermafbeelding van het welkomstscherm van de configuratieassistent op het macOS-apparaat waarop een lijst met selecteerbare talen wordt weergegeven.](./media/macos-dep-welcome-1808.png)   
3. Kies een toetsenbordindeling. De lijst bevat een of meer opties op basis van de geselecteerde taal. Als u alle indelingsopties wilt weergeven, ongeacht de geselecteerde taal, klikt u op **Alles weergeven**. Wanneer u klaar bent, klikt u op **Doorgaan**.  

   ![Schermafbeelding van het scherm voor de toetsenbordindeling van de configuratieassistent op het macOS-apparaat waarop een lijst met selecteerbare toetsenbordtalen wordt weergegeven, een uitgeschakelde optie Alles weergeven en de knoppen Vorige en Doorgaan.](./media/macos-dep-keyboard-1808.png)  
4. Selecteer uw Wi-Fi-netwerk. U moet een internetverbinding hebben om de configuratie voort te zetten. Als u uw netwerk niet ziet of als u verbinding wilt maken via een bekabeld netwerk, klikt u op **Andere netwerkopties**. Wanneer u klaar bent, klikt u op **Doorgaan**.  

   ![Schermafbeelding van het scherm voor Wi-Fi-netwerk selecteren van de configuratieassistent op het macOS-apparaat waarop een lijst met beschikbare netwerken wordt weergegeven die kunnen worden geselecteerd. Ook worden de volgende knoppen weergegeven: Netwerkopties, Vorige en Doorgaan.](./media/macos-dep-wifi-1808.png)  
5. Wanneer u bent verbonden met Wi-Fi, wordt het scherm **Extern beheer** weergegeven. De beheerder van uw organisatie kan met Extern beheer uw apparaat op afstand configureren met accounts, instellingen, apps en netwerken die vereist zijn voor het bedrijf. Voordat u doorgaat, leest u de documentatie om inzicht te krijgen in hoe uw apparaat wordt beheerd. Klik op **Doorgaan**.  

   ![Schermafbeelding van het scherm voor extern beheer van de configuratieassistent op het macOS-apparaat met tekst waarin extern beheer wordt uitgelegd en een koppeling naar documentatie voor meer informatie. Ook worden de knoppen Vorige en Doorgaan weergegeven.](./media/macos-dep-remote-management-1-1808.png)  
6. Meld u aan met een werk- of schoolaccount als dit wordt gevraagd. Nadat u bent geverifieerd, wordt op het apparaat een beheerprofiel geïnstalleerd. Met het profiel wordt uw toegang tot resources van uw organisatie geconfigureerd en ingeschakeld.  
7. Lees meer over het pictogram voor gegevens en privacy van Apple zodat u later kunt bepalen wanneer persoonlijke gegevens worden verzameld. Klik op **Doorgaan**.  

   ![Schermafbeelding van het scherm voor gegevens en privacy van de configuratieassistent op het macOS-apparaat waarop een afbeelding te zien is van twee personen die elkaar de hand schudden en waarop het gebruik van persoonlijke gegevens door Apple wordt beschreven. Ook worden de knoppen Vorige en Doorgaan weergegeven.](./media/macos-dep-apple-data-privacy-1808.png)  
8. Nadat het apparaat is ingeschreven, moet u mogelijk extra stappen uitvoeren om te voltooien. De weergegeven stappen zijn afhankelijk van hoe uw organisatie de installatie-ervaring heeft aangepast. U moet mogelijk:
    * Aanmelden bij een Apple-account
    * Akkoord gaan met de voorwaarden
    * Een computeraccount maken
    * Een snelle installatie doorlopen
    * Uw Mac instellen  
## <a name="get-the-company-portal-app"></a>De Bedrijfsportal-app downloaden      
Ga naar de App Store om de Intune-bedrijfsportal-app te downloaden op uw apparaat. U kunt met de app uw apparaat controleren, synchroniseren, toevoegen aan en verwijderen uit beheer en apps installeren.

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Controleer of de contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](https://portal.manage.microsoft.com#HelpDeskDialog).
