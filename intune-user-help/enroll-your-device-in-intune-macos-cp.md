---
title: Uw macOS-apparaat registreren bij Intune met bedrijfsportal | Microsoft Docs
description: Informatie over hoe u een macOS-apparaat bij Intune kunt registreren met de bedrijfsportal-app
keywords: Mac OS X, Mac OS, OS X
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2c9ea11cd19fee8f491329020753501996b47f40
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55834718"
---
# <a name="enroll-your-macos-device-in-intune-with-the-company-portal-app"></a>Uw macOS-apparaten registreren bij Intune met de bedrijfsportal-app

Registreer uw macOS-apparaat met de bedrijfsportal-app van Intune voor beveiligde toegang tot e-mail, bestanden en apps van uw organisatie.

Organisaties verplichten u vaak om uw apparaat te laten beheren voordat u toegang krijgt tot de vertrouwelijke gegevens van de organisatie. Nadat een apparaat wordt beheerd, kunnen organisaties beleid en apps pushen naar het apparaat via hun provider voor het beheer van mobiele apparaten. Voor continue toegang tot werk- of schoolgegevens op uw apparaat moet u uw apparaat zo configureren dat deze overeenkomt met de beleidsinstellingen.  

In dit artikel wordt beschreven hoe u met behulp van de Intune-bedrijfsportal-app voor macOS uw apparaat zo kunt registreren, configureren en onderhouden dat dit voldoet aan de vereisten van uw organisatie.

## <a name="what-to-expect-from-the-company-portal-app"></a>Wat u kunt verwachten van de bedrijfsportal-app

Tijdens de eerste configuratie verplicht de app u om uzelf te verifiëren bij uw organisatie. Vervolgens krijgt u instructies over de te maken apparaatinstellingen. Organisaties stellen bijvoorbeeld vaak wachtwoordvereisten van een minimum- of maximumaantal tekens waaraan u moet voldoen.    

Nadat het apparaat is geregistreerd, zorgt de bedrijfsportal-app ervoor dat uw apparaat beveiligd blijft. Als u bijvoorbeeld een app installeert vanaf een niet-vertrouwde bron, geeft de app een waarschuwing en wordt soms de toegang tot bedrijfsgegevens ontzegd. Dergelijk app-beveiligingsbeleid is gebruikelijk binnen organisaties en verplicht u vaak om niet-vertrouwde apps te verwijderen voordat u weer toegang kunt krijgen.

Als uw organisatie na de registratie een nieuwe beveiligingsvereiste oplegt, zoals meervoudige verificatie, wordt u via de bedrijfsportal-app op de hoogte gebracht. U hebt de mogelijkheid om uw instellingen aan te passen, zodat u op uw apparaat kunt blijven werken.  

Zie [Wat gebeurt er wanneer ik de bedrijfsportal-app installeer en mijn apparaat inschrijf?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md) voor meer informatie over de registratie.  

## <a name="get-your-device-managed"></a>Uw apparaat laten beheren  
Gebruik de volgende stappen om macOS-apparaten met OS X El Capitan 10.11 en hoger te registreren.   


1. Open een nieuw venster in __Safari__ en ga naar https://portal.manage.microsoft.com voor toegang tot de bedrijfsportalwebsite.  

2. Meld u aan bij de bedrijfsportalwebsite met uw werk- of schoolaccount.

   [!INCLUDE [wit_nextref](includes/end-user-password-guidance.md)]


3. Ga naar de linkerbovenhoek van de pagina en klik op **Menu** > **Apparaten**.  

4. Op de pagina __Apparaten__ ziet u een lijst met beheerde apparaten of een banner. Wat u ziet, is afhankelijk van of u al over een beheerd apparaat beschikt. 
    * Als u een niet-vermeld apparaat wilt toevoegen, selecteert u de banner met de tekst **Tik hier om ons te laten weten welk apparaat u gebruikt of om een nieuw apparaat toe te voegen.**
    * Als u geen apparaten hebt, ziet u het volgende op de banner: **U hebt geen beheerde apparaten. Voeg dit apparaat toe door hier te tikken.** Klik op de banner als u uw apparaat wilt toevoegen.  

     ![Een schermafbeelding van de pagina Apparaten met een rood vierkant rond de banner-optie om aan te geven waar u moet klikken.](./media/CP-enroll-MACOS-1808.png)  
5.  Voer onderstaande stap uit in overeenstemming met het bericht u momenteel in de bedrijfsportal ziet.  
    * Als u voor de eerste keer een apparaat toevoegt, wordt u gevraagd om de bedrijfsportal-app te downloaden naar uw apparaat. Klik op **Downloaden** om door te gaan.  

         ![Voorbeeldschermafbeelding van het scherm met de prompt om de bedrijfsportal-app voor macOS te downloaden. De gebruiker kan de volgende opties selecteren: klikken op de blauwe knop Downloaden linksonder de prompt, of op de grijze knop Annuleren rechtsonder.](./media/CP-enroll-download-macOS-1808.png)  

    * Als u al een beheerd macOS-apparaat hebt, ontvangt u een opdrachtprompt met een lijst van de momenteel beheerde macOS-apparaten. Selecteer **Mijn apparaat wordt hier niet vermeld** > **Downloaden** om de bedrijfsportal-app te downloaden op het apparaat dat u wilt toevoegen.  

         ![Voorbeeldschermafbeelding van het scherm met de prompt om de bedrijfsportal-app voor macOS te downloaden. De gebruiker heeft de optie om *Mijn apparaat wordt hier niet vermeld* of een specifiek apparaat in het midden van de pagina te selecteren. De blauwe knop voor downloaden wordt linksonder de opdrachtprompt weergegeven, en een grijze knop voor annuleren in rechtsonder](./media/cp-mac-os-device-isnt-here-1808.png)  

6. Uw apparaat controleert of het installatiebestand **CompanyPortal.pkg** veilig kan worden geopend. Open, nadat dit is voltooid, het installatieprogramma en voltooi de installatie.  

7. Als het installatieprogramma is voltooid, gaat u naar de **Launchpad** en opent u **Bedrijfsportal**.  

8. U wordt door uw macOS-apparaat gevraagd om te bevestigen dat u de bedrijfsportal-app wilt openen. Klik op **Openen**.  

   > [!TIP]
   > Intune heeft toegang nodig tot uw computer om te controleren of dit apparaat voldoende is beveiligd om toegang te verkrijgen tot de bronnen van uw organisatie. Als u de bedrijfsportal-app niet kunt openen op uw computer, [schakelt u Gatekeeper uit](https://support.apple.com/HT202491). Open vervolgens de app.

9. Op het eerste scherm dat u in de bedrijfsportal-app ziet, wordt u gevraagd om u **aan te melden**. Gebruik hetzelfde werk- of schoolaccount dat u hebt gebruikt om u aan te melden bij de bedrijfsportalwebsite.

10. De bedrijfsportal bevestigt uw accountgegevens en geeft de status van de **apparaatregistratie** en **apparaatcompatibiliteit** weer. Gele driehoeken markeren de acties die u moet uitvoeren om uw macOS-apparaat te beveiligen voor school of werk. Klik op **Beginnen** om de registratie te starten. 

11. Typ de aanmeldgegevens van uw computer in wanneer u daarom wordt gevraagd.  

Het duurt mogelijk enkele minuten om uw apparaat in beheer te registreren. Gedurende deze tijd kunt u andere dingen doen op uw apparaat. U krijgt een bericht zodra het instellen van de bedrijfstoegang is voltooid, zodat u weet dat u klaar bent.  

## <a name="unverified-profiles"></a>Niet-geverifieerde profielen
Wanneer u de geïnstalleerde MDM-profielen (Mobile Device Management) voor uw macOS-apparaat weergeeft, tonen sommige profielen mogelijk de status **Niet geverifieerd**. Zolang het **Beheerprofiel** de status **Geverifieerd** weergeeft, hoeft u zich geen zorgen te maken.  

Het beheerprofiel definieert de MDM-kanaalverbinding. Zolang het beheerprofiel is geverifieerd, nemen alle andere profielen die via dat kanaal aan de machine worden geleverd de beveiligingseigenschappen van het beheerprofiel over.

Omdat voor de andere profielen geen afzonderlijke verificatie is vereist, worden ze bovendien sneller gegenereerd en naar apparaten gestuurd. 

## <a name="updating-the-company-portal-app"></a>De bedrijfsportal-app bijwerken

U kunt de bedrijfsportal-app net als alle andere Office-apps bijwerken via Microsoft AutoUpdate voor de Mac. U vindt [hier meer informatie over het bijwerken van Microsoft-apps voor macOS](https://support.office.com/article/Check-for-Office-for-Mac-updates-automatically-bfd1e497-c24d-4754-92ab-910a4074d7c1).  

## <a name="next-steps"></a>Volgende stappen  
Hebt u meer hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. U vindt de contactgegevens van uw beheerder op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).  


