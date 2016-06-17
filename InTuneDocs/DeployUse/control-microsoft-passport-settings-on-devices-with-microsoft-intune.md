---
# required metadata

title: Microsoft Passport-instellingen op apparaten beheren | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 402bc5a1-ada3-4c4c-a0de-292d026b4444

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Microsoft Passport-instellingen beheren op apparaten met Microsoft Intune
Microsoft Intune biedt de mogelijkheid van integratie in **Microsoft Passport for Work**. Dit is een alternatieve aanmeldingsmethode waarbij Active Directory of een Azure Active Directory-account wordt gebruikt om een wachtwoord, smartcard of virtuele smartcard te vervangen.

Met Passport kan de gebruiker zich aanmelden met een **gebaar** in plaats van met een wachtwoord. Een gebaar van de gebruiker kan een eenvoudige pincode zijn, biometrische verificatie zoals Windows Hello of een extern apparaat zoals een vingerafdruklezer.

U kunt Intune op twee manieren integreren in Passport for Work:

-   U kunt Intune-beleid gebruiken om te bepalen welke gebaren gebruikers wel en niet kunnen gebruiken om zich aan te melden.

-   U kunt verificatiecertificaten opslaan in de sleutelarchiefprovider (KSP) van Passport for Work. Zie [Toegang tot beveiligde resources met certificaatprofielen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md) voor meer informatie.

## Passport for Work-beleid maken

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Beheer** &gt; **Mobile Device Management** &gt; **Windows** &gt; **Passport for Work** om, zoals hieronder, de pagina Passport for Work weer te geven.

    ![Passport for Work-pagina](../media/passport.png)

2.  Kies een van de volgende instellingen:
    - **Passport for Work op geregistreerde apparaten uitschakelen**: selecteer deze instelling als u Passport for Work niet wilt gebruiken op Windows 10-apparaten. Alle andere instellingen op het scherm worden uitgeschakeld.
    - **Passport for Work op geregistreerde apparaten inschakelen**: selecteer deze instelling als u instellingen voor Passport for Work op alle Windows 10-apparaten wilt configureren.
    - **Niet geconfigureerd**: selecteer deze instelling als u niet wilt dat Intune de instellingen voor Passport for Work beheert. Alle eventueel bestaande Passport for Work-instellingen voor Windows 10-apparaten worden niet gewijzigd. Alle andere instellingen op het scherm worden uitgeschakeld.
3.  Als u **Passport for Work op geregistreerde apparaten inschakelen** hebt geselecteerd, configureert u de vereiste instellingen die worden toegepast op alle geregistreerde Windows 10- en Windows 10 Mobile-apparaten.
3.  Klik op **Opslaan** als u klaar bent.

## Passport for Work: pincode-instellingen

  
- **Minimumlengte voor pincode vereisen**/**Maximumlengte voor pincode vereisen**: hiermee configureert u apparaten zodanig dat deze de minimum- en maximumlengte die u voor de pincode opgeeft, gebruiken om voor veilige aanmelding te zorgen. De standaardwaarde voor de pincode is 6 tekens, maar u kunt een minimumlengte van 4 tekens afdwingen. De maximumlengte voor de pincode is 127 tekens.
- **Kleine letters in pincode vereisen**/**Hoofdletters in pincode vereisen**/**Speciale tekens in pincode vereisen**: ook kunt u een sterkere pincode afdwingen door het gebruik van hoofdletters, kleine letters en speciale tekens in de pincode af te dwingen. U kunt kiezen uit:
    - **Toegestaan**: gebruikers kunnen het tekentype gebruiken in hun pincode, maar dit is niet verplicht.
    - **Vereist**: gebruikers moeten ten minste een van de tekentypen in hun pincode opnemen. Het is bijvoorbeeld gebruikelijk om ten minste één hoofdletter en één speciaal teken verplicht te stellen.
    - **Niet toegestaan** (standaard): gebruikers mogen deze speciale tekens niet in hun pincode gebruiken (dit is ook het gedrag als de instelling niet is geconfigureerd).
    > [!TIP] Tot de speciale tekens behoren: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**.
- **Vervaldagen pincode**: het is raadzaam om een vervalperiode voor een pincode op te geven, waarna eindgebruikers deze moeten wijzigen. De standaardwaarde is 41 dagen. 
- **Pincodegeschiedenis onthouden**: gebruik deze instelling om het hergebruik van eerder gebruikte pincodes te beperken. De standaardwaarde is dat de laatste 5 gebruikte pincodes niet opnieuw kunnen worden gebruikt.


## Passport for Work: overige instellingen

- **Een Trusted Platform Module (TPM) gebruiken**: een TPM-chip (Trusted Platform Module) biedt een extra laag voor de beveiliging van gegevens.<br>Kies een van de volgende waarden:
    - **Vereist** (standaard): alleen apparaten met een toegankelijke TPM kunnen Passport for Work inrichten.
    - **Voorkeur**: apparaten proberen eerst een TPM te gebruiken. Als deze niet beschikbaar is, kunnen ze softwareversleuteling gebruiken
- **Biometrische verificatie toestaan**: hiermee kunt u biometrische verificatie, zoals gezichtsherkenning of een vingerafdruk, inschakelen als alternatief voor een pincode voor Passport for Work. Gebruikers moeten toch een pincode voor Passport for Work configureren voor het geval dat biometrische verificatie mislukt. U kunt kiezen uit:
    - **Ja**: Passport for Work staat biometrische verificatie toe.
    - **Nee**: Passport for Work verhindert biometrische verificatie (voor alle typen accounts).
- **Verbeterde anti-adresvervalsing gebruiken, indien beschikbaar**: hiermee configureert u of de functies voor anti-adresvervalsing van Windows Hello worden gebruikt op apparaten die deze functie ondersteunen (bijvoorbeeld een foto van een gezicht in plaats van een echt gezicht detecteren).<br>Als u deze optie instelt op **Ja**, moeten alle gebruikers anti-adresvervalsing gebruiken voor gezichtskenmerken, indien ondersteund.
- **Remote Passport gebruiken**: als u deze optie instelt op **Ja**, kunnen gebruikers een extern paspoort gebruiken als draagbaar begeleidingsapparaat voor verificatie op desktopcomputers. De computer moet zijn toegevoegd aan Azure Active Directory en het begeleidingsapparaat moet worden geconfigureerd met een pincode voor Passport for Work.

## Meer informatie
Zie [de gids](https://technet.microsoft.com/library/mt589441.aspx) in de documentatie van Windows 10 voor meer informatie over Microsoft Passport.




<!--HONumber=May16_HO2-->


