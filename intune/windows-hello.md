---
title: Windows Hello voor Bedrijven integreren in Microsoft Intune | Microsoft Intune
description: In dit onderwerp leest u hoe u een beleid kunt maken om het gebruik van Windows Hello voor Bedrijven op beheerde apparaten te beheren."
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/28/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: shpate
ms.openlocfilehash: 7192c7fa5865a9b9928370d6348218ce0258b659
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57237398"
---
# <a name="integrate-windows-hello-for-business-with-microsoft-intune"></a>Windows Hello voor Bedrijven integreren in Microsoft Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

U kunt Windows Hello voor Bedrijven (voorheen Microsoft Passport for Work) integreren in Microsoft Intune.

 Hello voor Bedrijven biedt een alternatieve aanmeldingsmethode waarbij Active Directory of een Azure Active Directory-account wordt gebruikt om een wachtwoord, smartcard of virtuele smartcard te vervangen. Hiermee kan de gebruiker zich aanmelden met een *gebaar* in plaats van met een wachtwoord. Een gebaar van de gebruiker kan een eenvoudige pincode zijn, biometrische verificatie zoals Windows Hello of een extern apparaat zoals een vingerafdruklezer.

Intune integreert op twee manieren met Hello voor bedrijven:

-   Een Intune-beleid kan worden gemaakt onder **apparaatinschrijving**. Dit beleid is gericht op de hele organisatie (tenant-breed). Het biedt ondersteuning voor het Windows AutoPilot out-of-box-experience (OOBE) en wordt toegepast wanneer een apparaat wordt ingeschreven. 
-  Een profiel voor identiteitsbescherming kan worden gemaakt onder **apparaatconfiguratie**. Dit profiel is gericht op toegewezen gebruikers en apparaten, en wordt toegepast tijdens het inchecken. 

Gebruik dit artikel om een standaard Windows Hello voor Bedrijven-beleid te maken dat is gericht op uw hele organisatie. Zie [Een identiteitsbeschermingprofiel configureren](identity-protection-configure.md) voor het maken van een identiteitsbeschermingprofiel dat is toegepast om gebruikers- en apparaatgroepen te selecteren.  

<!--- -   You can store authentication certificates in the Windows Hello for Business key storage provider (KSP). For more information, see [Secure resource access with certificate profiles in Microsoft Intune](secure-resource-access-with-certificate-profiles.md). --->

> [!IMPORTANT]
> In Windows 10 Desktop en Windows 10 Mobile vóór de jubileumupdate kunt u twee verschillende pincodes instellen voor het verifiëren van resources:
> - U kunt de **pincode van het apparaat** gebruiken om het apparaat te ontgrendelen en verbinding te maken met cloudresources.
> - De **pincode voor werk** werd gebruikt om toegang tot krijgen tot de Azure AD-resources op de persoonlijke apparaten van de gebruiker (BYOD).
> 
> In de jubileumupdate zijn deze twee pincodes samengevoegd tot één pincode voor het apparaat.
> De waarde voor deze nieuwe pincode wordt ingesteld op basis van de Intune-configuratiebeleidsregels die u hebt ingesteld voor het beheer van de pincode van het apparaat, en eventuele Windows Hello-bedrijfsbeleidsregels die u hebt geconfigureerd.
> Als u beide beleidstypen voor het beheren van de pincode hebt ingesteld, wordt het Windows Hello-bedrijfsbeleid toegepast op apparaten met zowel Windows 10 Desktop als apparaten met Windows 10 Mobile.
> Als u ervoor wilt zorgen dat beleidsconflicten worden opgelost en het pincodebeleid correct wordt toegepast, werkt u het Windows Hello-bedrijfsbeleid bij zodat dit overeenkomt met de instellingen in het configuratiebeleid. Vervolgens vraagt u de gebruikers hun apparaten te synchroniseren in de bedrijfsportal-app.



## <a name="create-a-windows-hello-for-business-policy"></a>Een beleid voor Windows Hello voor Bedrijven maken

1. In de [Azure-portal](https://portal.azure.com) kiest u **Alle services** > **Bewaking en beheer** > **Intune**.

2. Kies in het deelvenster Intune de optie **Apparaatinschrijving** en kies vervolgens **Windows-inschrijving** > **Windows Hello voor Bedrijven**.

3. Kies in het deelvenster dat wordt geopend de **standaard**instellingen.

4. Klik in het deelvenster **Alle gebruikers** op **Eigenschappen** en voer een **naam** en desgewenst een **beschrijving** in voor de Windows Hello voor Bedrijven-instellingen.

5. Klik in het deelvenster **Alle gebruikers** op **Instellingen** en kies vervolgens een van de volgende opties voor **Windows Hello voor Bedrijven configureren**:

    - **Uitgeschakeld**. Als u Windows Hello voor Bedrijven niet wilt gebruiken, selecteert u deze instelling. Alle andere instellingen op het scherm zijn niet beschikbaar.
    - **Ingeschakeld**. Selecteer deze instelling als u instellingen voor Windows Hello voor Business wilt configureren.
    - **Niet geconfigureerd**. Selecteer deze instelling als u niet met Intune instellingen voor Windows Hello voor Bedrijven wilt beheren. Alle eventueel bestaande Windows Hello voor Bedrijven-instellingen voor Windows 10-apparaten worden niet gewijzigd. Alle andere instellingen in het deelvenster zijn niet beschikbaar.

6. Als u in de vorige stap **Ingeschakeld** hebt geselecteerd, configureert u de vereiste instellingen die worden toegepast op alle ingeschreven Windows 10- en Windows 10 Mobile-apparaten.

   - **Een Trusted Platform Module (TPM) gebruiken**. Een TPM-chip biedt een extra laag gegevensbeveiliging.<br>Kies een van de volgende waarden:

     - **Vereist** (standaard). Alleen apparaten met een toegankelijke TPM kunnen Windows Hello voor Bedrijven inrichten.
     - **Voorkeur**. Apparaten proberen eerst een TPM te gebruiken. Als deze niet beschikbaar is, kunnen ze softwareversleuteling gebruiken.

   - **Minimumlengte voor pincode**/**Maximumlengte voor pincode**. Hiermee configureert u apparaten om de opgegeven minimum- en maximumlengte van de pincode te gebruiken voor het beveiligen van de aanmelding. De standaardwaarde voor de pincode is zes tekens, maar u kunt een minimumlengte van vier tekens afdwingen. De maximumlengte voor de pincode is 127 tekens.

   - **Kleine letters in pincode**/**Hoofdletters in pincode**/**Speciale tekens in pincode**. U kunt zorgen voor sterkere pincodes door het gebruik van kleine letters, hoofdletters en speciale tekens voor de pincode af te dwingen. U kunt kiezen uit:

     - **Toegestaan**. Gebruikers kunnen het tekentype gebruiken in hun pincode, maar dit is niet verplicht.

     - **Vereist**. Gebruikers moeten ten minste een van de tekentypen in hun pincode opnemen. Het is bijvoorbeeld gebruikelijk om ten minste één hoofdletter en één speciaal teken verplicht te stellen.

     - **Niet toegestaan** (standaardinstelling). Gebruikers mogen deze tekentypen niet in hun pincode gebruiken. (Dit is ook het gedrag als de instelling niet is geconfigureerd.)<br>Tot de speciale tekens behoren: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**

   - **Verlooptijd pincode (dagen)**. Het is raadzaam om een verloopperiode voor een pincode op te geven, waarna gebruikers deze moeten wijzigen. De standaardwaarde is 41 dagen.

   - **Pincodegeschiedenis onthouden**. Beperkt het hergebruik van eerder gebruikte pincodes. Standaard kunnen de laatste 5 gebruikte pincodes niet opnieuw worden gebruikt.

   - **Biometrische verificatie toestaan**. Hiermee kunt u biometrische verificatie, zoals gezichtsherkenning of een vingerafdruk, inschakelen als alternatief voor een pincode voor Windows Hello voor Bedrijven. Gebruikers moeten toch een pincode voor Passport for Work configureren voor het geval dat biometrische verificatie mislukt. U kunt kiezen uit:

     - **Ja**. Windows Hello voor bedrijven staat biometrische verificatie toe.
     - **Nee**. Windows Hello voor Bedrijven staat biometrische verificatie niet toe (voor alle typen accounts).

   - **Verbeterde anti-adresvervalsing gebruiken, indien beschikbaar**. Hiermee configureert u of de functies voor anti-adresvervalsing van Windows Hello worden gebruikt op apparaten die deze functie ondersteunen (bijvoorbeeld een foto van een gezicht in plaats van een echt gezicht detecteren).<br>Als u deze optie instelt op **Ja**, moeten alle gebruikers anti-adresvervalsing gebruiken voor gezichtskenmerken, indien dat wordt ondersteund.

   - **Aanmelding via de telefoon toestaan**. Als u deze optie instelt op **Ja**, kunnen gebruikers een extern passport gebruiken als draagbaar begeleidingsapparaat voor verificatie op desktopcomputers. De computer moet zijn toegevoegd aan Azure Active Directory en het begeleidingsapparaat moet worden geconfigureerd met een pincode voor Windows Hello voor Bedrijven.

## <a name="windows-holographic-for-business-support"></a>Ondersteuning voor Windows Holographic for Business

De volgende instellingen voor Windows Hello for Business worden in Windows Holographic for Business ondersteund:

- Een Trusted Platform Module (TPM) gebruiken
- Minimumlengte voor pincode
- Maximumlengte voor pincode
- Kleine letters in pincode
- Hoofdletters in pincode
- Speciale tekens in pincode
- Verlooptijd pincode (dagen)
- Pincodegeschiedenis onthouden

## <a name="further-information"></a>Meer informatie
Zie [de gids](https://technet.microsoft.com/library/mt589441.aspx) in de documentatie van Windows 10 voor meer informatie over Microsoft Passport.
