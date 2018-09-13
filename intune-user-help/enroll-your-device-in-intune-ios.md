---
title: Toegang tot uw bedrijfsbronnen instellen | Microsoft Docs
description: Hier wordt beschreven hoe u uw iOS-apparaat kunt laten beheren door Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 51492c1a8d7e32ab7dbdd5d896e7726c877d62d5
ms.sourcegitcommit: 490365fb8b5405f323b4358fb1ec9dfdd9ff2d58
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2018
ms.locfileid: "43149580"
---
# <a name="set-up-access-to-your-company-resources"></a>Toegang tot uw bedrijfsbronnen instellen

Uw iOS-apparaat registreren met de bedrijfsportal-app van Intune voor beveiligde toegang tot e-mail, bestanden en apps van uw organisatie.

Organisaties verplichten u vaak om uw apparaat te laten beheren voordat u toegang krijgt tot de vertrouwelijke gegevens van de organisatie. Nadat een apparaat wordt beheerd, kunnen organisaties beleid en apps pushen naar het apparaat via hun provider voor het beheer van mobiele apparaten. 

Voor continue toegang tot uw werk- of schoolgegevens op uw apparaat moet u uw apparaat zo configureren dat dit overeenkomt met de beleidsinstellingen. In dit artikel wordt beschreven hoe u met behulp van de Intune-bedrijfsportal-app voor iOS uw apparaat zo kunt registreren, configureren en onderhouden dat dit voldoet aan de vereisten van de organisatie.

> [!NOTE]
> Als u in de Mail-app toegang probeert te krijgen tot zakelijke e-mail, ziet u waarschijnlijk een prompt waarin u wordt gevraagd uw apparaat te beheren om het veilig te houden. Volg de onderstaande instructies om op uw iOS-apparaat toegang te krijgen tot uw e-mail en andere bedrijfsbronnen.

## <a name="what-to-expect-from-the-company-portal-app"></a>Wat u kunt verwachten van de bedrijfsportal-app

### <a name="security"></a>Beveiliging
Tijdens de eerste configuratie verplicht de app u om uzelf te verifiëren bij uw organisatie. Vervolgens krijgt u instructies over de te maken apparaatinstellingen. Organisaties stellen bijvoorbeeld vaak wachtwoordvereisten van een minimum- of maximumaantal tekens waaraan u moet voldoen.    

### <a name="protection"></a>Protection
Nadat het apparaat is geregistreerd, zorgt de bedrijfsportal-app ervoor dat uw apparaat beveiligd blijft. Als u bijvoorbeeld een app installeert vanaf een niet-vertrouwde bron, geeft de app een waarschuwing en wordt soms de toegang tot bedrijfsgegevens ontzegd. Dergelijk app-beveiligingsbeleid is gebruikelijk binnen organisaties en verplicht u vaak om niet-vertrouwde apps te verwijderen voordat u weer toegang kunt krijgen.

### <a name="setting-notifications"></a>Meldingen instellen
Als uw organisatie na de registratie een nieuwe beveiligingsvereiste oplegt, zoals meervoudige verificatie, wordt u via de bedrijfsportal-app op de hoogte gebracht. U hebt de mogelijkheid om uw instellingen aan te passen, zodat u op uw apparaat kunt blijven werken.  

Zie [Wat gebeurt er wanneer ik de bedrijfsportal-app installeer en mijn apparaat inschrijf?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md) voor meer informatie over inschrijving. 

## <a name="before-you-start"></a>Voordat u begint

- Zodra u begint, dient u ervoor te zorgen dat u het hele proces voltooit. Als u meer dan een paar minuten pauzeert, kan de installatie eindigen en moet u opnieuw beginnen.  
    - Als dit proces mislukt, moet u terugkeren naar de bedrijfsportal-app en het opnieuw proberen.  
- Controleer of uw Wi-Fi werkt en of Safari op uw apparaat werkt.
- Download en installeer de [Intune-bedrijfsportal-app](install-and-sign-in-to-the-intune-company-portal-app-ios.md).


## <a name="using-the-company-portal-app-to-set-up-access-to-company-resources"></a>De bedrijfsportal-app gebruiken om toegang tot bedrijfsbronnen in te stellen

|Wat u ziet|Uitleg|
|---|---|
|![Aanmeldingsscherm bedrijfsportal met de knop 'Aanmelden' onderaan.](./media/ios-01-cp-enroll-1802.png)|Open de bedrijfsportal-app en tik op **Aanmelden**.|
|![Prompt voor aanmelden bij Azure AD.](./media/ios-02-cp-enroll-1802.png)|Voer uw gebruikersnaam van uw bedrijf in en tik op **Volgende**.|
|![Prompt voor Azure AD-wachtwoord.](./media/ios-03-cp-enroll-1802.png)|Voer uw wachtwoord in en tik op **Aanmelden**.|
|![Beginscherm voor laden van bedrijfsbronnen.](./media/ios-04-cp-enroll-1802.png)|Wacht totdat het scherm is geladen.|
|![Pagina met voorwaarden.](./media/ios-05-cp-enroll-1802.png)|Lees en **ga akkoord met alle** voorwaarden.|
|![Scherm voor instellen van bedrijfstoegang. Zowel het beheer als de instellingen moeten nog worden gedefinieerd.](./media/ios-06-cp-enroll-1802.png)|Tik op **Starten** om ervoor te zorgen dat uw apparaat toegang kan krijgen tot bedrijfsbronnen. Als u dit nu nog niet kunt doen, kunt u het proces **Uitstellen**, maar dit betekent wel dat u geen e-mail, documenten en dergelijke kunt ophalen.|
|![Scherm Wat kan mijn bedrijf zien.](./media/ios-07-cp-enroll-1802.png)|Lees **meer informatie** over wat uw bedrijf kan zien door op de koppeling onderaan te tikken. Tik anders op **Doorgaan**.|
|![Scherm De volgende stap.](./media/ios-08-cp-enroll-1802.png)|In dit scherm kunt u zien wat er allemaal tijdens de installatie gebeurt. U gaat aan het werk in Safari, de app Instellingen en de bedrijfsportal-app om dit proces te voltooien. Tik op **Doorgaan**.|
|![Laden van het scherm na tikken op Volgende in De volgende stap.](./media/ios-09-cp-enroll-1802.png)|Wacht totdat het scherm is geladen.|
|![Overgeschakeld naar Safari om in te schrijven.](./media/ios-7-cp-enroll-1711.png)|U bent doorgestuurd naar Safari om beheerinformatie voor uw apparaat op te halen.|
|![Systeemprompt om de app Instellingen te openen.](./media/ios-8-cp-enroll-1711.png)|Tik op **Toestaan** om de app Instellingen te openen en het configuratieprofiel te downloaden. U installeert dit profiel zodat uw bedrijf zakelijke gegevens op uw apparaat kan beheren.|
|![Met het profiel worden apparaatinstellingen geopend.](./media/ios-9-cp-enroll-1711.png)|Tik op **INSTALLEREN**.|
|![Profiel modaal dialoogvenster installeren vanaf de onderkant van het scherm.](./media/ios-10-cp-enroll-1711.png)|Tik op **INSTALLEREN**.|
|![Profiel installeert het laadscherm.](./media/ios-11-cp-enroll-1711.png)|Wacht totdat het scherm is geladen.|
|![Waarschuwingsscherm voor profielbeheer.](./media/ios-12-cp-enroll-1711.png)|Deze door Apple geschreven waarschuwing geeft meer informatie over welke typen acties kunnen worden uitgevoerd op een apparaat dat onder beheer staat. Meer informatie over [welke informatie uw bedrijf kan zien](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).|
|![Systeemprompt met vraag over vertrouwen in extern beheer.](./media/ios-13-cp-enroll-1711.png)|Tik op **Vertrouwen** zodat uw bedrijf zakelijke gegevens en instellingen op uw apparaat kan beheren.|
|![Profiel voor voltooien installatie laadscherm.](./media/ios-14-cp-enroll-1711.png)|Wacht totdat het scherm is geladen.|
|![Scherm Profiel geïnstalleerd.](./media/ios-15-cp-enroll-1711.png)|Uw profiel is geïnstalleerd en de zakelijke gegevens en instellingen van uw apparaat zijn nu veel beter geschikt om te worden beheerd.|
|![Overgeschakeld naar Safari om in te schrijven.](./media/ios-16-cp-enroll-1711.png)|U wordt teruggestuurd naar Safari om het ophalen van beheerinformatie voor uw apparaat af te ronden. |
|![Systeemprompt om de bedrijfsportal te openen.](./media/ios-17-cp-enroll-1711.png)|Tik op **Openen**.|
|![Scherm voor laden van bedrijfsbronnen.](./media/ios-21-cp-enroll-1802.png)|Wacht totdat het scherm is geladen.|
|![Selecteer de apparaatcategorie in de bedrijfsportal-app.](./media/ios-22-cp-enroll-1802.png)|Selecteer de beste categorie voor uw apparaat. Dit heeft meestal betrekking op wie de eigenaar van het apparaat is of waar het apparaat zich meestal bevindt.|
|![Categorie geselecteerd.](./media/ios-23-cp-enroll-1802.png)||
|![Apparaatbeheer is geslaagd. Nu moeten de instellingen nog worden bijgewerkt.](./media/ios-24-cp-enroll-1802.png)|U hebt nu het beheer van uw apparaat verkregen. Er zijn waarschijnlijk nog instellingen, zoals de lengte van uw wachtwoord, die voor uw bedrijf moeten worden aangepast. Tik op **Doorgaan** om verder te gaan.|
|![Apparaatinstellingen bevestigen.](./media/ios-25-cp-enroll-1802.png)|Bedrijfsportal controleert of er instellingen zijn die moeten worden bijgewerkt.|
|![Controle van instellingen voltooid, met een onjuiste versie van het besturingssysteem](./media/ios-26-cp-enroll-1802.png)|Bedrijfsportal geeft instructies over hoe u problemen met uw instellingen kunt oplossen. Nadat de problemen zijn opgelost, tikt u op **Instellingen controleren**.|
|![Laadscherm apparaatinstellingen bevestigen](./media/ios-27-cp-enroll-1802.png)|Uw apparaat controleert of uw instellingen veilig genoeg zijn voor toegang tot bedrijfsbronnen.|
|![Instellingen ingeschreven en bijgewerkt](./media/ios-28-cp-enroll-1802.png)|Gefeliciteerd. Uw apparaat is nu ingeschreven bij Intune.|

> [!Note]
> U moet wellicht nog enkele andere stappen uitvoeren voordat het apparaat volledig is beheerd. Meer informatie over het [registreren van uw apparaat met Telecom-onkostenbeheer](enroll-your-device-with-telecom-expense-management-ios.md). Als uw organisatie Apple Device Enrollment Program gebruikt, meer, vindt u [hier](enroll-your-device-dep-ios.md) meer informatie.

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Controleer of de contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).
