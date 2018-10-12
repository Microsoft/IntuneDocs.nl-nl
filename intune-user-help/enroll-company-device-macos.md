---
title: Een door uw organisatie verstrekt macOS-apparaat inschrijven voor beheer | Microsoft Docs
description: Hier wordt beschreven hoe u een macOS-apparaat inschrijft bij Intune dat is aangeschaft en geleverd door uw organisatie.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/29/2018
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
ms.openlocfilehash: 603a501ff8b8b3ebc6b142a823b1c5bea4e48b98
ms.sourcegitcommit: 77540295381a59918eb638ce9c1870209cf8af02
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/20/2018
ms.locfileid: "46505747"
---
# <a name="enroll-your-organization-provided-macos-device-in-management"></a>Het door uw organisatie verstrekte iOS-apparaat voor beheer inschrijven

Ontdek hoe u uw nieuwe macOS-apparaat kunt laten beheren in Intune.  

Apparaten die aan u worden verstrekt door uw werk of school zijn vaak geconfigureerd voordat u ze hebt ontvangen. Uw organisatie verzendt vooraf geconfigureerde instellingen naar uw apparaat wanneer u het inschakelt en u zich voor de eerste keer aanmeldt. Nadat de installatie op het apparaat is voltooid, krijgt u toegang tot uw werk- of schoolresources. 

U kunt beheer instellen door uw apparaat in te schakelen en u aan te melden met de referenties van uw werk- of schoolaccount. In de rest van dit artikel worden de stappen en de schermen beschreven die u ziet terwijl u de configuratieassistent uitvoert.   

## <a name="what-is-apple-dep"></a>Wat is Apple DEP?
Uw organisatie heeft mogelijk hun apparaten aangeschaft via een programma met de naam *Apple Device Enrollment Program* (DEP). Organisaties kopen grote hoeveelheden iOS- of macOS-apparaten via Apple DEP. Organisaties kunnen die apparaten vervolgens configureren en beheren in hun favoriete provider voor mobiele apparaatbeheer, zoals Intune. Zie [macOS-apparaten automatisch inschrijven met Apple Device Enrollment Program](https://docs.microsoft.com/intune/device-enrollment-program-enroll-macos) als u beheerder bent en informatie wilt over Apple DEP.  

## <a name="get-your-device-managed"></a>Uw apparaat laten beheren 
Voer de volgende stappen uit om uw macOS-apparaat voor beheer in te schrijven. Als u uw eigen apparaat gebruikt in plaats van een door de organisatie verstrekt apparaat, volgt u de stappen voor [persoonlijke en bring-your-own-apparaten](enroll-your-device-in-intune-macos-cp.md).  

1. Schakel uw macOS-apparaat in. 
2. Kies uw land en klik op **Doorgaan**.  

   ![Schermafbeelding van het welkomstscherm van de configuratieassistent op het macOS-apparaat waarop een lijst met selecteerbare talen wordt weergegeven.](./media/macos-dep-welcome-1808.png)   
3. Kies een toetsenbordindeling. De lijst bevat een of meer opties op basis van het geselecteerde land. Als u alle indelingsopties wilt weergeven, ongeacht het geselecteerde land, klikt u op **Alles weergeven**. Wanneer u klaar bent, klikt u op **Doorgaan**.  

   ![Schermafbeelding van het scherm voor de toetsenbordindeling van de configuratieassistent op het macOS-apparaat waarop een lijst met selecteerbare toetsenbordtalen wordt weergegeven, een uitgeschakelde optie Alles weergeven en de knoppen Vorige en Doorgaan.](./media/macos-dep-keyboard-1808.png)  
4. Selecteer uw Wi-Fi-netwerk. U moet een internetverbinding hebben om de configuratie voort te zetten. Als u uw netwerk niet ziet of als u verbinding wilt maken via een bekabeld netwerk, klikt u op **Andere netwerkopties**. Wanneer u klaar bent, klikt u op **Doorgaan**.  

   ![Schermafbeelding van het scherm voor Wi-Fi-netwerk selecteren van de configuratieassistent op het macOS-apparaat waarop een lijst met beschikbare netwerken wordt weergegeven die kunnen worden geselecteerd. Ook worden de volgende knoppen weergegeven: Netwerkopties, Vorige en Doorgaan.](./media/macos-dep-wifi-1808.png)  
5. Wanneer u bent verbonden met Wi-Fi, wordt het scherm **Extern beheer** weergegeven. De beheerder van uw organisatie kan met Extern beheer uw apparaat op afstand configureren met accounts, instellingen, apps en netwerken die vereist zijn voor het bedrijf. Lees de uitleg over extern beheer om te leren hoe uw apparaat wordt beheerd. Klik op **Doorgaan**.  

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
Download de Intune-bedrijfsportal-app voor macOS op uw apparaat. U kunt met de app uw apparaat controleren, synchroniseren, toevoegen aan en verwijderen uit beheer en apps installeren. In deze stappen wordt ook beschreven hoe u uw apparaat bij de bedrijfsportal registreert.  
1. Ga op uw macOS-apparaat naar http://portal.manage.microsoft.com/EnrollmentRedirect.aspx.
2. Meld u aan bij de bedrijfsportalwebsite met uw werk- of schoolaccount. 
3. Klik op **De app downloaden** om het installatieprogramma voor de bedrijfsportal voor macOS te downloaden.
4. Wanneer u hierom wordt gevraagd, opent u het .pkg-bestand en voltooit u de installatiestappen.
4. Open de bedrijfsportal-app en meld u aan met het account van uw werk of school.
5. Zoek uw apparaat en klik op **Registreren**.
6. Klik op **Doorgaan** > **Gereed**. Uw apparaat moet nu worden weergegeven in de bedrijfsportal-app als een zakelijk apparaat dat aan de vereisten voldoet.

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Controleer of de contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).
