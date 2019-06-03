---
title: Instellingen voor Windows Hello voor Bedrijven in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een lijst met alle pincodes, biometrische instellingen, en instellingen voor anti-adresvervalsing in een Identity Protection-profiel om Windows Hello voor Bedrijven te gebruiken op Windows 10-apparaten in Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/14/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: shpate
ms.openlocfilehash: 158840a73784516d13defa04785ca5990a9874cf
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66041829"
---
# <a name="windows-10-device-settings-to-enable-windows-hello-for-business-in-intune"></a>Windows 10 device settings to enable Windows Hello for Business in Intune (Instellingen voor Windows 10-apparaten om Windows Hello voor Bedrijven in Intune in te schakelen)

Dit artikel bevat een overzicht en beschrijving van de instellingen voor Windows Hello voor Bedrijven die u kunt beheren op Windows 10-apparaten in Intune. Als Intune-beheerder kunt u deze instellingen configureren en toewijzen aan Windows 10-apparaten als onderdeel van uw MDM-oplossing (Mobile Device Management). 

U kunt meer informatie over deze instellingen vinden in [Beleidsinstellingen configureren voor Windows Hello voor Bedrijven](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings) in de Windows Hello-documentatie.


Zie [Identity Protection configureren](identity-protection-configure.md) voor meer informatie over Windows Hello voor Bedrijven-profielen in Intune.

## <a name="before-you-begin"></a>Voordat u begint

[Een configuratieprofiel maken](identity-protection-configure.md#create-the-device-profile).

## <a name="windows-hello-for-business"></a>Windows Hello voor Bedrijven

- **Windows Hello voor Bedrijven configureren**: Kies **Inschakelen** om deze functie te gebruiken en de bijbehorende instellingen te configureren.
- **Minimumlengte voor pincode**: voer de minimale lengte voor de pincode in die u wilt toestaan op de apparaten. De standaardlengte voor pincodes is zes tekens. De minimale lengte is vier (4) tekens.
- **Maximumlengte voor pincode**: voer de maximale lengte voor de pincode in die u wilt toestaan op de apparaten. De standaardlengte voor pincodes is zes (6) tekens. De maximumlengte voor de pincode is 127 tekens.  
- **Kleine letters in pincode**: u kunt een sterkere pincode afdwingen door te vereisen dat eindgebruikers kleine letters opnemen. Uw opties zijn:

  - **Niet toegestaan** (standaard): Blokkeren dat gebruikers kleine letters gebruiken in de pincode. Dit gedrag treedt ook op als de instelling niet is geconfigureerd.
  - **Toegestaan**: toestaan dat gebruikers kleine letters gebruiken in de pincode. Dit is echter niet vereist.
  - **Vereist**: gebruikers moeten minstens één kleine letter opnemen in hun pincode. Het is bijvoorbeeld gebruikelijk om ten minste één hoofdletter en één speciaal teken verplicht te stellen.

- **Hoofdletters in pincode**: u kunt een sterkere pincode afdwingen door te vereisen dat eindgebruikers hoofdletters opnemen. Uw opties zijn:

  - **Niet toegestaan** (standaard): Blokkeren dat gebruikers hoofdletters gebruiken in de pincode. Dit gedrag treedt ook op als de instelling niet is geconfigureerd.
  - **Toegestaan**: toestaan dat gebruikers hoofdletters gebruiken in de pincode. Dit is echter niet vereist.
  - **Vereist**: gebruikers moeten minstens één hoofdletter opnemen in hun pincode. Het is bijvoorbeeld gebruikelijk om ten minste één hoofdletter en één speciaal teken verplicht te stellen.

- **Speciale tekens in pincode**: u kunt een sterkere pincode afdwingen door te vereisen dat eindgebruikers speciale tekens opnemen. Uw opties zijn:

  - **Niet toegestaan** (standaard): Blokkeren dat gebruikers speciale tekens gebruiken in de pincode. Dit gedrag treedt ook op als de instelling niet is geconfigureerd.
    Tot de speciale tekens behoren: `! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~`
  - **Toegestaan**: toestaan dat gebruikers hoofdletters gebruiken in de pincode. Dit is echter niet vereist.
  - **Vereist**: gebruikers moeten minstens één hoofdletter opnemen in hun pincode. Het is bijvoorbeeld gebruikelijk om ten minste één hoofdletter en één speciaal teken verplicht te stellen.

- **Vervaldagen pincode**: Het is raadzaam om een vervalperiode voor een pincode op te geven, waarna gebruikers deze moeten wijzigen. De standaardwaarde is 41 dagen.

- **Pincodegeschiedenis onthouden**: beperkt het hergebruik van eerder gebruikte pincodes. Standaard kunnen de laatste 5 gebruikte pincodes niet opnieuw worden gebruikt.  
- **Herstel van de pincode inschakelen**: hiermee kan de gebruiker de pincode wijzigen met behulp van de pincodeherstelservice van Windows Hello voor Bedrijven.

       - **Enable**: The cloud service encrypts a PIN recovery secret to store on the device. The user can change their PIN if needed.  
       - **Not configured** (default): A PIN recovery secret is not created or stored. If the user's PIN is forgotten, the only way to get a new PIN is by deleting the existing PIN and creating a new one. The user will need to re-register with any services the old PIN provided access to.  

- **Een Trusted Platform Module (TPM) gebruiken**: een TPM-chip biedt een extra laag voor gegevensbeveiliging. Kies een van de volgende waarden:  
  - **Inschakelen**: alleen apparaten met een toegankelijke TPM kunnen Windows Hello voor Bedrijven inrichten.
  - **Niet geconfigureerd**: alle apparaten kunnen Windows Hello voor Bedrijven inrichten, zelfs als er geen bruikbare TPM is. Apparaten proberen eerst gebruik te maken van een TPM, maar als er geen beschikbaar is, kunnen apparaten gebruik maken van softwareversleuteling.  

- **Biometrische verificatie toestaan**: hiermee kunt u biometrische verificatie, zoals gezichtsherkenning of een vingerafdruk, inschakelen als alternatief voor een pincode voor Windows Hello voor Bedrijven. Gebruikers moeten toch een pincode voor Passport for Work configureren voor het geval dat biometrische verificatie mislukt. U kunt kiezen uit:

  - **Inschakelen**: Windows Hello voor bedrijven staat biometrische verificatie toe.
  - **Niet geconfigureerd** (standaard): het gebruik van biometrische verificatie (voor alle accounttypen) is niet toegestaan in Windows Hello voor Bedrijven.

- **Uitgebreide anti-spoofing gebruiken, indien beschikbaar**: kies deze optie als de anti-adresvervalsingsfuncties van Windows Hello worden gebruikt op apparaten die hier ondersteuning voor bieden. Detecteer bijvoorbeeld een foto van een gezicht in plaats van een echt gezicht.

  - **Inschakelen**: Windows verplicht alle gebruikers om anti-adresvervalsing te gebruiken voor gezichtskenmerken, indien dit wordt ondersteund.  
  - **Niet geconfigureerd** (standaard): Windows houdt zich aan de anti-adresvervalsingsconfiguraties van het apparaat.

- **Certificaat voor on-premises resources**: 

  - **Inschakelen**: hiermee staat u Windows Hello voor Bedrijven toe certificaten te gebruiken voor verificatie bij on-premises resources.
  - **Niet geconfigureerd** (standaard): hiermee voorkomt u dat Windows Hello voor Bedrijven certificaten gebruikt voor verificatie bij on-premises resources. In plaats daarvan maken apparaten gebruik van het standaardgedrag van *On-premises verificatie met sleutelvertrouwen*. Zie [Gebruikerscertificaat voor on-premises verificatie](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings#use-certificate-for-on-premises-authentication) in de Windows Hello-documentatie voor meer informatie.  
## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
