---
title: IOS-of iPadOS-apparaat inschrijven met Intune-bedrijfsportal en DISA Purebred
description: Meer informatie over het registreren van een iOS-of iPadOS-apparaat en het instellen van afgeleide referentie verificatie met DISA Purebred.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: tisilver
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5c484b98466c1418016f4ebc6cc805e412d7891e
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "73415786"
---
# <a name="set-up-ios-or-ipados-device-with-company-portal-and-disa-purebred"></a>IOS-of iPadOS-apparaten instellen met Bedrijfsportal en DISA Purebred  

Registreer uw apparaat met de Intune-bedrijfsportal voor beveiligde, mobiele toegang tot e-mail, bestanden en apps van uw organisatie. Nadat uw apparaat is geregistreerd, wordt het *beheerd*. Uw organisatie kan beleid en apps aan het apparaat toewijzen via een MDM-provider (Mobile Device Management), zoals Intune.  

Tijdens de registratie installeert u ook een afgeleide referentie op het apparaat. Uw organisatie vereist mogelijk dat u de afgeleide referentie gebruikt als verificatie methode bij het openen van bronnen of voor het ondertekenen en versleutelen van e-mail berichten. 

U moet waarschijnlijk een afgeleide referentie instellen als u een Smart Card gebruikt voor het volgende:

* Meld u aan bij school-of werk-apps, Wi-Fi en virtuele particuliere netwerken (VPN)
* E-mail berichten voor school of werk ondertekenen en versleutelen met S/MIME-certificaten  

In dit artikel gaat u als volgt te werkt:  

   * Registreer een mobiel iOS-of iPadOS-apparaat met Intune-bedrijfsportal.  
   * Haal een afgeleide referentie op uit de afgeleide referentie provider van uw organisatie, [Disa Purebred](https://cyber.mil/pki-pke/purebred/).  

## <a name="what-are-derived-credentials"></a>Wat zijn afgeleide referenties?  
Een afgeleide referentie is een certificaat dat is afgeleid van uw smartcard referenties en op uw apparaat is geïnstalleerd. Het biedt u externe toegang tot werk resources, waarbij wordt voor komen dat onbevoegde gebruikers toegang krijgen tot gevoelige informatie.  

Afgeleide referenties worden gebruikt voor het volgende: 
* Studenten en mede werkers verifiëren die zich aanmelden bij school-of werk-apps, Wi-Fi en VPN
* E-mail berichten van school of werk ondertekenen en versleutelen met S/MIME-certificaten

Afgeleide referenties zijn een implementatie van de NIST-richtlijnen (National Institute of Standards and Technology) voor afgeleide PIV-referenties (Personal Identity Verification) als onderdeel van Special Publication (SP) 800-157.  

## <a name="prerequisites"></a>Vereisten

 Als u de inschrijving wilt volt ooien, hebt u het volgende nodig:

* De Smart Card van uw school of werk
* Toegang tot een computer of kiosk waar u zich kunt aanmelden met uw Smart Card
* Uw mobiele apparaat
* De Intune-bedrijfsportal-app voor iOS en iPadOS geïnstalleerd op uw apparaat   

U moet ook contact opnemen met een Purebred-agent of-vertegenwoordiger tijdens de installatie.      

## <a name="enroll-device"></a>Een apparaat inschrijven  
1. Open de Bedrijfsportal-app voor iOS-iPadOS op uw mobiele apparaat en meld u aan met uw werk account.  

2. Noteer de code op het scherm.  

    ![Voorbeeld afbeelding van Bedrijfsportal-app met bericht en code op het scherm.](./media/copy-code-intercede.png)  
3. Schakel over naar het apparaat dat geschikt is voor Smart Cards en ga naar https://microsoft.com/devicelogin. 
4. Voer de code in die u eerder hebt geschreven.  

    ![Voor beeld van een scherm opname van de Bedrijfsportal website ' code invoeren '.](./media/enter-code-intercede.png)   

5. Plaats de Smart Card om u aan te melden.  
6. Ga terug naar de Bedrijfsportal-app op uw mobiele apparaat en volg de instructies op het scherm om uw apparaat in te schrijven.  
7. Zodra de inschrijving is voltooid Bedrijfsportal, ontvangt u een melding over het instellen van uw Smart Card. Tik op de melding. Als u geen melding ontvangt, controleert u uw e-mail adres.   

    ![Voor beeld van een scherm opname van de Bedrijfsportal push melding op het Start scherm van het apparaat.](./media/action-required-in-app-intercede.png)  
8. Op het scherm **mobiele-smartcard toegang instellen** :  
    a. Tik op de koppeling naar de instructies voor het instellen van uw organisatie. Als uw organisatie geen aanvullende instructies verstrekt, wordt u naar dit artikel verzonden.  
    b. Klik op **openen** om de Purebred-app te openen.  

    ![Voor beeld van een scherm opname van het scherm Bedrijfsportal mobiele smartcard toegang instellen.](./media/smart-card-open-disa-purebred.png)  
9. Als u wordt gevraagd Bedrijfsportal de Purebred-registratie-app te openen, selecteert u **openen**.   

    ![Voor beeld van een scherm opname van de Bedrijfsportal vragen om DISA Purebred-app te openen.](./media/open-app-prompt-disa-purbred.png)  
10. Wanneer de app werkt, moet u samen werken met de Purebred-agent van uw organisatie om het Purebred-configuratie profiel voor voor registratie te configureren en downloaden.   
11. Ga naar de instellingen-app > **algemene** > **profielen & Apparaatbeheer** > **profiel installeren** en tik op **installeren**.  
12. Voer uw apparaatwachtwoord in.  
13. Installeer het profiel. Mogelijk moet **u meer dan** één keer tikken om de installatie te starten. 
14. Ga terug naar de Purebred-registratie-app. Volg de instructies van uw Purebred-agent om door te gaan.  
 
15. Nadat u het configuratie profiel hebt gedownload, gaat u naar de instellingen app > **algemene** > **profielen & Apparaatbeheer** > **profiel installeren** en tikt u op **installeren**.   
16.  Voer uw apparaatwachtwoord in.
17. Installeer het profiel. Mogelijk moet **u meer dan** één keer tikken om de installatie te starten. 
18. Nadat de installatie is voltooid, keert u terug naar de app Bedrijfsportal.  
19.  Tik in het scherm **Mobile Smart Card-toegang instellen** op **door gaan**.  

20. In het scherm **certificaten importeren** kunt u de afgeleide referentie ophalen en importeren die u hebt ontvangen van DISA Purebred.  

    a. Tik op **Doorgaan**.   

    ![voorbeeld scherm afbeelding van het scherm Bedrijfsportal instellen voor het importeren van certificaten.](./media/import-certificate-disa-purebred.png)  
    b. Ga naar iCloud drive **browse** > **locaties** en tik op **meer locaties**.  

    ![voorbeeld scherm afbeelding van iCloud Drive, bladeren menu meer locaties markeren.](./media/icloud-drive-more-locations.png)  
    c. Tik op de switch om de **Purebred-sleutel keten**in te scha kelen.  

    ![Voor beeld van een scherm opname van een iCloud-station, een Blader weergave, waarmee wordt aangegeven dat de switch van de Purebred-sleutel keten is ingeschakeld.](./media/icloud-drive-enable-purebred-keychain.png)   

    d. Tik op **Purebred-referentie pakket**.  

    ![voorbeeld scherm afbeelding van een iOS-scherm met een selecteerbaar Purebred-referentie pakket optie.](./media/purebred-credential-package.png)  
    f. Er wordt een lijst met certificaten weer gegeven. Selecteer één en tik vervolgens op **sleutel importeren**.  

    ![Een voor beeld van een scherm opname van een lijst met selecteerbaar certificaten, waarbij er al een is geselecteerd.](./media/import-purebred-keychain.png) 
21. Ga terug naar de app Bedrijfsportal en wacht tot Bedrijfsportal uw apparaat hebt ingesteld.   

## <a name="next-steps"></a>Volgende stappen  
Nadat de inschrijving is voltooid, hebt u toegang tot werk resources, zoals e-mail, Wi-Fi en alle apps die uw organisatie beschikbaar maakt. Voor meer informatie over het verkrijgen, zoeken, installeren en verwijderen van apps in de Bedrijfsportal raadpleegt u:

* [Apps beheren via de Bedrijfsportalwebsite](manage-apps-cpweb.md)  
* [Beheerde apps op een apparaat gebruiken](use-managed-apps-on-your-device-ios.md)  

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Controleer of de contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).
