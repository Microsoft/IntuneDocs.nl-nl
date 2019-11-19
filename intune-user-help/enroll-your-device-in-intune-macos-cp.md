---
title: Uw Mac registreren bij Intune-bedrijfsportal | Microsoft Docs
description: Meer informatie over het registreren van uw Mac in intune met de app Bedrijfsportal.
keywords: Mac OS X, Mac OS, OS X
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/14/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: kakyker
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: ba285fc9de58b3fb739a16722e0e05e36e840e87
ms.sourcegitcommit: 76ae5aea5deee7a590e24c3b2bb52f88125943e5
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 11/15/2019
ms.locfileid: "74098127"
---
# <a name="enroll-your-macos-device-using-the-company-portal-app"></a>Uw macOS-apparaat inschrijven met behulp van de app Bedrijfsportal  

Registreer uw macOS-apparaat met de bedrijfsportal-app van Intune voor beveiligde toegang tot e-mail, bestanden en apps van uw werk of school.

Organisaties vereisen doorgaans dat u uw apparaat registreert voordat u toegang krijgt tot bedrijfs eigen gegevens. Nadat uw apparaat is geregistreerd, wordt het *beheerd*. Uw organisatie kan beleid en apps aan het apparaat toewijzen via een MDM-provider (Mobile Device Management), zoals Intune. Voor continue toegang tot werk- of schoolgegevens op uw apparaat moet u uw apparaat zo configureren dat het overeenkomt met de beleidsinstellingen van uw organisatie.  

In dit artikel wordt beschreven hoe u met behulp van de bedrijfsportal-app voor macOS uw apparaat zo kunt registreren, configureren en onderhouden dat dit voldoet aan de vereisten van uw organisatie.  


## <a name="what-to-expect-from-the-company-portal-app"></a>Wat u kunt verwachten van de bedrijfsportal-app

Tijdens de eerste installatie moet u zich bij de Bedrijfsportal-app aanmelden en uzelf verifiëren met uw organisatie. Bedrijfsportal wordt u vervolgens geïnformeerd over alle Apparaatinstellingen die u moet configureren om te voldoen aan de vereisten van uw organisatie. Organisaties stellen bijvoorbeeld vaak wachtwoordvereisten van een minimum- of maximumaantal tekens waaraan u moet voldoen.    

Nadat u uw apparaat hebt Inge schreven, controleert Bedrijfsportal altijd of uw apparaat is beveiligd volgens de vereisten van uw organisatie. Als u bijvoorbeeld een app van een niet-vertrouwde bron installeert, wordt Bedrijfsportal u gewaarschuwd en kan de toegang tot de resources van uw organisatie worden beperkt. Het beveiligings beleid voor apps zoals dit is een veelvoorkomende versie. Om weer toegang te krijgen, moet u de niet-vertrouwde app waarschijnlijk verwijderen. 

Als uw organisatie na de registratie een nieuwe beveiligingsvereiste oplegt, zoals meervoudige verificatie, wordt u via de bedrijfsportal op de hoogte gebracht. U hebt de mogelijkheid om uw instellingen aan te passen, zodat u op uw apparaat kunt blijven werken.  

Zie [Wat gebeurt er wanneer ik de bedrijfsportal-app installeer en mijn apparaat inschrijf?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md) voor meer informatie over inschrijving.  

## <a name="get-your-macos-device-managed"></a>Uw macOS-apparaat laten beheren  
Gebruik de volgende stappen om uw macOS-apparaat bij uw organisatie in te schrijven. Op uw apparaat moet macOS 10,12 of hoger worden uitgevoerd.   

> [!NOTE]
> Tijdens dit proces wordt u mogelijk gevraagd Bedrijfsportal toe te staan vertrouwelijke informatie te gebruiken die is opgeslagen in uw sleutel hanger. Deze instructies maken deel uit van Apple Security. Wanneer u de prompt krijgt, typt u het wacht woord voor de aanmeldings sleutel en selecteert u **altijd toestaan**. Als u op **Enter** of **return** op het toetsen bord drukt, selecteert u in plaats daarvan **toestaan**, wat kan leiden tot extra prompts.  

### <a name="install-company-portal-app"></a>De bedrijfsportal-app installeren  
1. Ga naar [mijn Mac registreren](https://go.microsoft.com/fwlink/?linkid=853070).  
2. Het bestand met de Bedrijfsportal Installer. pak wordt gedownload. Open het installatie programma en ga door met de stappen. 
3. Ga akkoord met de gebruiksrecht overeenkomst van de software. 
4. Voer het wacht woord of de geregistreerde vinger afdruk van het apparaat in om de software te installeren.  
5. Open Bedrijfsportal. 

> [!IMPORTANT]
> Micro soft auto update kan worden geopend om uw micro soft-software bij te werken. Nadat alle updates zijn geïnstalleerd, opent u de Bedrijfsportal-app. Installeer de meest recente versies van micro soft auto update en Bedrijfsportal voor de beste installatie-ervaring.  


### <a name="enroll-your-mac"></a>Uw Mac registreren  


1. Meld u aan bij de bedrijfsportal met het account van uw werk of school.  
2. Wanneer de app wordt geopend, selecteert u **beginnen**.  
3. Bekijk [wat uw organisatie wel en niet kan zien](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md) op het Inge schreven apparaat. Selecteer vervolgens **Doorgaan**.  
4. Selecteer **profiel downloaden**in het scherm **beheer profiel installeren** .   

    ![Voor beeld van een scherm opname van Bedrijfsportal, het scherm beheer profiel installeren en de knop ' profiel downloaden ' selecteren.](./media/install-mgmt-profile-mac-1911.PNG)   
5. De systeem voorkeuren van uw apparaat worden geopend. Selecteer **installeren** en selecteer vervolgens opnieuw **installeren** . Als u wordt gevraagd, voert u het wacht woord van uw apparaat in.  

    ![Voor beeld van een scherm opname van macOS-systeem voorkeuren, installatie prompt, markeren van de knop installeren.](./media/system-preference-install-1911.PNG)  
6. Zodra het profiel is geïnstalleerd, wordt het weer gegeven in de lijst profielen onder **beheer profiel.**  

   ![Voor beeld van een scherm opname van macOS System Preferences, Profiles screen, markeren van het geïnstalleerde beheer profiel.](./media/system-preference-verify-1911.PNG)   
7. Ga terug naar Bedrijfsportal.   
8. Uw organisatie vereist mogelijk dat u de apparaatinstellingen bijwerkt. Wanneer u klaar bent met het bijwerken van de instellingen, selecteert u **instellingen controleren**.  

    ![Voor beeld van een scherm opname van Bedrijfsportal, het scherm Apparaatinstellingen bijwerken, de knop instellingen controleren markeren.](./media/update-settings-mac-1911.PNG)  
9. Wanneer het installatie programma is voltooid, selecteert u **gereed**.  


 ## <a name="troubleshooting-and-feedback"></a>Problemen oplossen en feedback   

Als u tijdens de registratie problemen ondervindt, gaat u naar **Help** > **diagnostische rapport verzenden** om het probleem te melden aan micro soft app-ontwikkel aars. Deze informatie wordt gebruikt om de app te verbeteren. Ze gebruiken deze informatie ook om het probleem op te lossen als uw IT-ondersteunings medewerker om hulp te bereiken.  

Nadat u het probleem hebt gerapporteerd aan micro soft, kunt u de details van uw ervaring naar uw IT-ondersteunings medewerker sturen. Selecteer de **e-mail gegevens**. Typ in wat u in de hoofd tekst van het e-mail bericht hebt ondervonden. Als u het e-mail adres van uw ondersteunings medewerker wilt vinden, gaat u naar de Bedrijfsportal-app > **contact persoon**. Of Controleer de [bedrijfsportal-website](https://go.microsoft.com/fwlink/?linkid=2010980).  
 

Daarnaast zou de Microsoft Intune Bedrijfsportal team graag uw feedback horen. Ga naar **Help** > **Feedback verzenden** om uw ideeën en ideeën te delen.  

## <a name="unverified-profiles"></a>Niet-geverifieerde profielen  
Wanneer u de geïnstalleerde MDM-profielen (Mobile Device Management) in **Systeemvoorkeuren** > **Profielen** weergeeft, hebben sommige profielen mogelijk de status Niet geverifieerd. Zolang het beheerprofiel de status Geverifieerd heeft, hoeft u zich geen zorgen te maken.  

Het beheerprofiel definieert de MDM-kanaalverbinding. Zolang het beheerprofiel is geverifieerd, nemen alle andere profielen die via dat kanaal aan de machine worden geleverd, de beveiligingseigenschappen van het beheerprofiel over.  

## <a name="updating-the-company-portal-app"></a>De bedrijfsportal-app bijwerken

U kunt de bedrijfsportal-app net als alle andere Office-apps bijwerken via Microsoft AutoUpdate voor macOS. U vindt hier meer informatie over het [bijwerken van Microsoft-apps voor macOS](https://support.office.com/article/Check-for-Office-for-Mac-updates-automatically-bfd1e497-c24d-4754-92ab-910a4074d7c1).  

## <a name="next-steps"></a>Volgende stappen  
Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Controleer of de contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).  


