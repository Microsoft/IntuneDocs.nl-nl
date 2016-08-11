---
title: Microsoft Passport-instellingen op apparaten beheren | Microsoft Intune
description: Informatie over hoe Intune integreert met Microsoft Passport for Work. Dit is een alternatieve aanmeldingsmethode waarbij Active Directory of een Azure Active Directory-account wordt gebruikt om een wachtwoord, smartcard of virtuele smartcard te vervangen.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 402bc5a1-ada3-4c4c-a0de-292d026b4444
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 822264b7af87c0241e1d345544b8e9892f9e8c51
ms.openlocfilehash: c05929f3c4032bf8e252f4b2087b23dfdecf846b


---

# Microsoft Passport-instellingen beheren op apparaten met Microsoft Intune
Informatie over hoe Microsoft Intune integreert met Microsoft Passport for Work. Dit is een alternatieve aanmeldingsmethode waarbij Active Directory of een Azure Active Directory-account wordt gebruikt om een wachtwoord, smartcard of virtuele smartcard te vervangen.

Met Passport kan de gebruiker zich aanmelden met een *gebaar* in plaats van met een wachtwoord. Een gebaar van de gebruiker kan een eenvoudige pincode zijn, biometrische verificatie zoals Windows Hello of een extern apparaat zoals een vingerafdruklezer.

>[!TIP]
>Microsoft Passport for Work is nu bekend als Windows Hello for Business. Deze wijziging wordt nog niet weergegeven in de Intune-console.

U kunt Intune op twee manieren integreren in Passport for Work:

-   U kunt Intune-beleid gebruiken om te bepalen welke gebaren gebruikers wel en niet kunnen gebruiken om zich aan te melden.

-   U kunt verificatiecertificaten opslaan in de sleutelarchiefprovider (KSP) van Passport for Work. Zie [Toegang tot beveiligde resources met certificaatprofielen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md) voor meer informatie.

## Passport for Work-beleid maken

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Beheer** &gt; **Mobile Device Management** &gt; **Windows** &gt; **Passport for Work** om de pagina Passport for Work weer te geven.

    ![Passport for Work-pagina](../media/passport.png)

2.  Kies een van de volgende instellingen:
    - **Passport for Work uitschakelen op geregistreerde apparaten**. Selecteer deze instelling als u Passport for Work niet wilt gebruiken op Windows 10-apparaten. Alle andere instellingen op het scherm zijn niet beschikbaar.
    - **Passport for Work inschakelen op geregistreerde apparaten**. Selecteer deze instelling als u instellingen voor Passport for Work op alle Windows 10-apparaten wilt configureren.
    - **Niet geconfigureerd**. Selecteer deze instelling als u niet wilt dat Intune de instellingen voor Passport for Work beheert. Alle eventueel bestaande Passport for Work-instellingen voor Windows 10-apparaten worden niet gewijzigd. Alle andere instellingen op het scherm zijn niet beschikbaar.
3.  Als u **Passport for Work op geregistreerde apparaten inschakelen** hebt geselecteerd, configureert u de vereiste instellingen die worden toegepast op alle geregistreerde Windows 10- en Windows 10 Mobile-apparaten.
4.  Als u klaar bent, kiest u **Opslaan**.

## Passport for Work: pincode-instellingen


- **Minimumlengte voor pincode vereisen**/**Maximumlengte voor pincode vereisen**. Hiermee configureert u apparaten om de opgegeven minimum- en maximumlengte van de pincode te gebruiken voor het beveiligen van de aanmelding. De standaardwaarde voor de pincode is 6 tekens, maar u kunt een minimumlengte van 4 tekens afdwingen. De maximumlengte voor de pincode is 127 tekens.
- **Kleine letters voor pincode vereisen**/**Hoofdletters voor pincode vereisen**/**Speciale tekens voor pincode vereisen**. U kunt zorgen voor sterkere pincodes door het gebruik van kleine letters, hoofdletters en speciale tekens voor de pincode af te dwingen. U kunt kiezen uit:
    - **Toegestaan**. Gebruikers kunnen het tekentype gebruiken in hun pincode, maar dit is niet verplicht.
    - **Vereist**. Gebruikers moeten ten minste een van de tekentypen in hun pincode opnemen. Het is bijvoorbeeld gebruikelijk om ten minste één hoofdletter en één speciaal teken verplicht te stellen.
    - **Niet toegestaan** (standaardinstelling). Gebruikers mogen deze tekentypen niet in hun pincode gebruiken. (Dit is ook het gedrag als de instelling niet is geconfigureerd.)
    > [!TIP]
    > Tot de speciale tekens behoren: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**.
- **Verlooptijd pincode (dagen)**. Het is raadzaam om een verloopperiode voor een pincode op te geven, waarna gebruikers deze moeten wijzigen. De standaardwaarde is 41 dagen.
- **Pincodegeschiedenis onthouden**. Beperkt het hergebruik van eerder gebruikte pincodes. Standaard kunnen de laatste 5 gebruikte pincodes niet opnieuw worden gebruikt.


## Passport for Work: overige instellingen

- **Een Trusted Platform Module (TPM) gebruiken**. Een TPM-chip biedt een extra laag gegevensbeveiliging.<br>Kies een van de volgende waarden:
    - **Vereist** (standaard). Alleen apparaten met een toegankelijke TPM kunnen Passport for Work inrichten.
    - **Voorkeur**. Apparaten proberen eerst een TPM te gebruiken. Als deze niet beschikbaar is, kunnen ze softwareversleuteling gebruiken.
- **Biometrische verificatie toestaan**. Hiermee kunt u biometrische verificatie, zoals gezichtsherkenning of een vingerafdruk, inschakelen als alternatief voor een pincode voor Passport for Work. Gebruikers moeten toch een pincode voor Passport for Work configureren voor het geval dat biometrische verificatie mislukt. U kunt kiezen uit:
    - **Ja**. Passport for Work staat biometrische verificatie toe.
    - **Nee**. Passport for Work staat biometrische verificatie niet toe (voor alle typen accounts).
- **Verbeterde anti-adresvervalsing gebruiken, indien beschikbaar**. Hiermee configureert u of de functies voor anti-adresvervalsing van Windows Hello worden gebruikt op apparaten die deze functie ondersteunen (bijvoorbeeld een foto van een gezicht in plaats van een echt gezicht detecteren).<br>Als u deze optie instelt op **Ja**, moeten alle gebruikers anti-adresvervalsing gebruiken voor gezichtskenmerken, indien dat wordt ondersteund.
- **Remote Passport gebruiken**. Als u deze optie instelt op **Ja**, kunnen gebruikers een extern passport gebruiken als draagbaar begeleidingsapparaat voor verificatie op desktopcomputers. De computer moet zijn toegevoegd aan Azure Active Directory en het begeleidingsapparaat moet worden geconfigureerd met een pincode voor Passport for Work.

## Meer informatie
Zie [de gids](https://technet.microsoft.com/library/mt589441.aspx) in de documentatie van Windows 10 voor meer informatie over Microsoft Passport.



<!--HONumber=Aug16_HO1-->


