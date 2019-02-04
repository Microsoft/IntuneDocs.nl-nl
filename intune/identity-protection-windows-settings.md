---
title: Instellingen voor Windows Hello voor Bedrijven in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een lijst met alle pincodes, biometrische instellingen, en instellingen voor anti-adresvervalsing in een Identity Protection-profiel om Windows Hello voor Bedrijven te gebruiken op Windows 10-apparaten in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b5eb25c48e3724fdc9277a790d01908e976c75be
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54832133"
---
# <a name="windows-10-and-newer-device-settings-to-enable-windows-hello-for-business-in-intune"></a>Instellingen voor Windows 10-apparaten (en nieuwer) om Windows Hello voor Bedrijven in te schakelen

Dit artikel bevat een overzicht en beschrijving van de instellingen voor Windows Hello voor Bedrijven die u kunt beheren op Windows 10-apparaten in Intune. Gebruik deze instellingen als onderdeel van de MDM-oplossing (Mobile Device Management) om een pincode of vingerafdruk te gebruiken voor aanmelden, en meer.

Als Intune-beheerder kunt u deze instellingen maken en toewijzen aan Windows 10-apparaten (en hoger).

Zie [Identity Protection configureren](identity-protection-configure.md) voor meer informatie over Windows Hello voor Bedrijven-profielen in Intune.

## <a name="before-you-begin"></a>Voordat u begint

[Een configuratieprofiel maken](identity-protection-configure.md#create-the-device-profile).

## <a name="windows-hello-for-business"></a>Windows Hello voor Bedrijven

- **Windows Hello voor Bedrijven configureren**: Kies **Inschakelen** om deze functie te gebruiken en de bijbehorende instellingen te configureren.
- **Minimale lengte pincode**: Voer de minimale lengte voor de pincode in die u wilt toestaan op de apparaten. De standaardlengte voor pincodes is zes tekens. De minimale lengte is vier (4) tekens.
- **Maximale lengte voor pincode**: Voer de maximale lengte voor de pincode in die u wilt toestaan op de apparaten. De standaardlengte voor pincodes is zes (6) tekens. De maximumlengte voor de pincode is 127 tekens.  
- **Kleine letters in pincode**: U kunt een sterkere pincode afdwingen door te vereisen dat eindgebruikers kleine letters opnemen. Uw opties zijn:

  - **Niet toegestaan** (standaardinstelling): Blokkeren dat gebruikers kleine letters gebruiken in de pincode. Dit gedrag treedt ook op als de instelling niet is geconfigureerd.
  - **Toegestaan**: Toestaan dat gebruikers kleine letters gebruiken in de pincode. Dit is echter niet vereist.
  - **Vereist**: Gebruikers moeten minstens één kleine letter opnemen in hun pincode. Het is bijvoorbeeld gebruikelijk om ten minste één hoofdletter en één speciaal teken verplicht te stellen.

- **Hoofdletters in pincode**: U kunt een sterkere pincode afdwingen door te vereisen dat eindgebruikers hoofdletters opnemen. Uw opties zijn:

  - **Niet toegestaan** (standaardinstelling): Blokkeren dat gebruikers hoofdletters gebruiken in de pincode. Dit gedrag treedt ook op als de instelling niet is geconfigureerd.
  - **Toegestaan**: Toestaan dat gebruikers hoofdletters gebruiken in de pincode. Dit is echter niet vereist.
  - **Vereist**: Gebruikers moeten minstens één hoofdletter opnemen in hun pincode. Het is bijvoorbeeld gebruikelijk om ten minste één hoofdletter en één speciaal teken verplicht te stellen.

- **Speciale tekens in pincode**: U kunt een sterkere pincode afdwingen door te vereisen dat eindgebruikers speciale tekens opnemen. Uw opties zijn:

  - **Niet toegestaan** (standaardinstelling): Blokkeren dat gebruikers speciale tekens gebruiken in de pincode. Dit gedrag treedt ook op als de instelling niet is geconfigureerd.
    Tot de speciale tekens behoren: `! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~`
  - **Toegestaan**: Toestaan dat gebruikers hoofdletters gebruiken in de pincode. Dit is echter niet vereist.
  - **Vereist**: Gebruikers moeten minstens één hoofdletter opnemen in hun pincode. Het is bijvoorbeeld gebruikelijk om ten minste één hoofdletter en één speciaal teken verplicht te stellen.

- **Verlooptijd pincode (dagen)**: Het is raadzaam om een verloopperiode voor een pincode op te geven, waarna gebruikers deze moeten wijzigen. De standaardwaarde is 41 dagen.

- **Pincodegeschiedenis onthouden**: Beperkt het hergebruik van eerder gebruikte pincodes. Standaard kunnen de laatste 5 gebruikte pincodes niet opnieuw worden gebruikt.  
- **Herstel van pincode inschakelen**: Hiermee kan de gebruiker de pincode wijzigen met behulp van de pincodeherstelservice van Windows Hello voor Bedrijven.

       - **Enable**: The cloud service encrypts a PIN recovery secret to store on the device. The user can change their PIN if needed.  
       - **Not configured** (default): A PIN recovery secret is not created or stored. If the user's PIN is forgotten, the only way to get a new PIN is by deleting the existing PIN and creating a new one. The user will need to re-register with any services the old PIN provided access to.  

- **Een TPM (Trusted Platform Module) gebruiken**: Een TPM-chip biedt een extra laag gegevensbeveiliging. Kies een van de volgende waarden:  
  - **Inschakelen**: Alleen apparaten met een toegankelijke TPM kunnen Windows Hello voor Bedrijven inrichten.
  - **Niet geconfigureerd**: Alle apparaten kunnen Windows Hello voor Bedrijven inrichten, zelfs als er geen bruikbare TPM is. Apparaten proberen eerst gebruik te maken van een TPM, maar als er geen beschikbaar is, kunnen apparaten gebruik maken van softwareversleuteling.  

- **Biometrische verificatie toestaan**: Hiermee kunt u biometrische verificatie, zoals gezichtsherkenning of een vingerafdruk, inschakelen als alternatief voor een pincode voor Windows Hello voor Bedrijven. Gebruikers moeten toch een pincode voor Passport for Work configureren voor het geval dat biometrische verificatie mislukt. U kunt kiezen uit:

  - **Inschakelen**: Windows Hello voor bedrijven staat biometrische verificatie toe.
  - **Niet geconfigureerd** (standaard): Windows Hello voor Bedrijven staat biometrische verificatie niet toe (voor alle typen accounts).

- **Verbeterde anti-adresvervalsing gebruiken, indien beschikbaar**: Kies deze optie als de anti-adresvervalsingsfuncties van Windows Hello worden gebruikt op apparaten die hier ondersteuning voor bieden. Detecteer bijvoorbeeld een foto van een gezicht in plaats van een echt gezicht.

  - **Inschakelen**: Windows verplicht alle gebruikers om een anti-adresvervalsing te gebruiken voor gezichtskenmerken, indien dit wordt ondersteund.  
  - **Niet geconfigureerd** (standaard): Windows houdt zich aan de anti-adresvervalsingsconfiguraties van het apparaat.

- **Certificaat voor on-premises resources**: 

  - **Inschakelen**: Hiermee staat u Windows Hello voor Bedrijven toe certificaten te gebruiken voor verificatie bij on-premises resources.
  - **Niet geconfigureerd** (standaard): Hiermee voorkomt u dat Windows Hello voor Bedrijven certificaten gebruikt voor verificatie bij on-premises resources.  

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).