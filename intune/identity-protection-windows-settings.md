---
title: Instellingen voor Windows Hello voor Bedrijven in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een lijst met alle pincodes, biometrische instellingen, en instellingen voor anti-adresvervalsing in een Identity Protection-profiel om Windows Hello voor Bedrijven te gebruiken op Windows 10-apparaten in Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/20/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: shpate
ms.openlocfilehash: 5a8111d2542269441c7305aad0aad0b7c2162037
ms.sourcegitcommit: 1dc9d4e1d906fab3fc46b291c67545cfa2231660
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2019
ms.locfileid: "67735609"
---
# <a name="windows-10-device-settings-to-enable-windows-hello-for-business-in-intune"></a>Windows 10 device settings to enable Windows Hello for Business in Intune (Instellingen voor Windows 10-apparaten om Windows Hello voor Bedrijven in Intune in te schakelen)

Dit artikel bevat een overzicht en beschrijving van de instellingen voor Windows Hello voor Bedrijven die u kunt beheren op Windows 10-apparaten in Intune. Als Intune-beheerder kunt u deze instellingen configureren en toewijzen aan Windows 10-apparaten als onderdeel van uw MDM-oplossing (Mobile Device Management). 

U kunt meer informatie over deze instellingen vinden in [Beleidsinstellingen configureren voor Windows Hello voor Bedrijven](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings) in de Windows Hello-documentatie.


Zie [Identity Protection configureren](identity-protection-configure.md) voor meer informatie over Windows Hello voor Bedrijven-profielen in Intune.

## <a name="before-you-begin"></a>Voordat u begint

[Een configuratieprofiel maken](identity-protection-configure.md#create-the-device-profile).

## <a name="windows-hello-for-business"></a>Windows Hello voor Bedrijven
- **Windows Hello voor Bedrijven configureren**:
  - **Niet geconfigureerd**: selecteer deze instelling als u niet met Intune instellingen voor Windows Hello voor Bedrijven wilt beheren. Alle eventueel bestaande Windows Hello voor Bedrijven-instellingen voor Windows 10-apparaten worden niet gewijzigd. Alle andere instellingen in het deelvenster zijn niet beschikbaar.

  - **Uitgeschakeld**: als u Windows Hello voor Bedrijven niet wilt gebruiken, selecteert u deze instelling. Alle andere instellingen op het scherm zijn niet beschikbaar.
  - **Ingeschakeld**: selecteer deze instelling als u instellingen voor Windows Hello voor Business wilt configureren.  
  
  **Standaard**: niet geconfigureerd

  Als deze instelling is *ingeschakeld*, zijn de volgende instellingen beschikbaar:

  - **Minimale lengte pincode**  
    Geef een minimale lengte voor de pincode voor apparaten op om het aanmelden te helpen beveiligen. De standaard waarden van Windows-apparaten zijn zes tekens, maar deze instelling kan ten minste vier tot 127 tekens afdwingen. 

    **Standaard**: *niet geconfigureerd*

  - **Maximale lengte pincode**  
  Geef een maximale lengte voor de pincode voor apparaten op om het aanmelden te helpen beveiligen. De standaard waarden van Windows-apparaten zijn zes tekens, maar deze instelling kan ten minste vier tot 127 tekens afdwingen.  

    **Standaard**: *niet geconfigureerd*  

  - **Kleine letters in pincode**  
    U kunt een sterkere pincode afdwingen door te vereisen dat eindgebruikers kleine letters opnemen. Uw opties zijn:

    - **Niet toegestaan**: blokkeren dat gebruikers kleine letters gebruiken in de pincode. Dit gedrag treedt ook op als de instelling niet is geconfigureerd.
    - **Toegestaan**: toestaan dat gebruikers kleine letters gebruiken in de pincode. Dit is echter niet vereist.
    - **Vereist**: gebruikers moeten minstens één kleine letter opnemen in hun pincode. Het is bijvoorbeeld gebruikelijk om ten minste één hoofdletter en één speciaal teken verplicht te stellen.

  - **Hoofdletters in pincode**  
    U kunt een sterkere pincode afdwingen door te vereisen dat eindgebruikers hoofdletters opnemen. Uw opties zijn:

    - **Niet toegestaan**: blokkeren dat gebruikers hoofdletters gebruiken in de pincode. Dit gedrag treedt ook op als de instelling niet is geconfigureerd.
    - **Toegestaan**: toestaan dat gebruikers hoofdletters gebruiken in de pincode. Dit is echter niet vereist.
    - **Vereist**: gebruikers moeten minstens één hoofdletter opnemen in hun pincode. Het is bijvoorbeeld gebruikelijk om ten minste één hoofdletter en één speciaal teken verplicht te stellen.

  - **Speciale tekens in pincode**  
    U kunt een sterkere pincode afdwingen door te vereisen dat eindgebruikers speciale tekens opnemen. Tot de speciale tekens behoren: `! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~`  

    Uw opties zijn:
    - **Niet toegestaan**: blokkeren dat gebruikers speciale tekens gebruiken in de pincode. Dit gedrag treedt ook op als de instelling niet is geconfigureerd.
    - **Toegestaan**: toestaan dat gebruikers hoofdletters gebruiken in de pincode. Dit is echter niet vereist.
    - **Vereist**: gebruikers moeten minstens één hoofdletter opnemen in hun pincode. Het is bijvoorbeeld gebruikelijk om ten minste één hoofdletter en één speciaal teken verplicht te stellen.

    **Standaard**: niet toegestaan

  - **Verlooptijd pincode (dagen)**  
    Het is raadzaam om een verloopperiode voor een pincode op te geven, waarna gebruikers deze moeten wijzigen. Standaard waarden voor Windows-apparaten zijn 41 dagen.

    **Standaardinstelling**: niet geconfigureerd

  - **Pincodegeschiedenis onthouden**  
    Beperkt het hergebruik van eerder gebruikte pincodes. Windows-apparaten standaard om het hergebruik van de laatste vijf pincodes te voor komen.  

    **Standaardinstelling**: niet geconfigureerd  

  - **Herstel van pincode inschakelen**   
    Hiermee kan de gebruiker de Windows hello voor bedrijven-pincode herstel service gebruiken. 
    
    - **Ingeschakeld** : het geheim voor pincode herstel wordt opgeslagen op het apparaat en de gebruiker kan de pincode zo nodig wijzigen.  
    - **Uitgeschakeld** : het herstel geheim is niet gemaakt of opgeslagen.

    **Standaard**: niet geconfigureerd

  - **Een TPM (Trusted Platform Module) gebruiken**   
    Een TPM-chip biedt een extra laag gegevensbeveiliging.  

    - **Ingeschakeld**: alleen apparaten met een toegankelijke TPM kunnen Windows Hello voor Bedrijven inrichten.
    - **Niet geconfigureerd**: apparaten proberen eerst een TPM te gebruiken. Als deze niet beschikbaar is, kunnen ze softwareversleuteling gebruiken.
    
    **Standaard**: niet geconfigureerd

  - **Biometrische verificatie toestaan**  
     Hiermee kunt u biometrische verificatie, zoals gezichtsherkenning of een vingerafdruk, inschakelen als alternatief voor een pincode voor Windows Hello voor Bedrijven. Gebruikers moeten toch een pincode voor Passport for Work configureren voor het geval dat biometrische verificatie mislukt. U kunt kiezen uit:

    - **Inschakelen**: Windows Hello voor bedrijven staat biometrische verificatie toe.
    - **Niet geconfigureerd**: het gebruik van biometrische verificatie (voor alle accounttypen) is niet toegestaan in Windows Hello voor Bedrijven.

    **Standaard**: niet geconfigureerd

  - **Verbeterde anti-adresvervalsing gebruiken, indien beschikbaar**  
    Hiermee configureert u of de functies voor anti-adresvervalsing van Windows Hello worden gebruikt op apparaten die deze functie ondersteunen (bijvoorbeeld een foto van een gezicht in plaats van een echt gezicht detecteren).  
    - **Inschakelen**: Windows verplicht alle gebruikers om anti-adresvervalsing te gebruiken voor gezichtskenmerken, indien dit wordt ondersteund.
    - **Niet geconfigureerd**: Windows houdt zich aan de anti-adresvervalsingsconfiguraties van het apparaat.

    **Standaard**: niet geconfigureerd

  - **Certificaat voor on-premises resources**  

    - **Inschakelen**: hiermee staat u Windows Hello voor Bedrijven toe certificaten te gebruiken voor verificatie bij on-premises resources.
    - **Niet geconfigureerd**: hiermee voorkomt u dat Windows Hello voor Bedrijven certificaten gebruikt voor verificatie bij on-premises resources. In plaats daarvan maken apparaten gebruik van het standaardgedrag van *On-premises verificatie met sleutelvertrouwen*. Zie [Gebruikerscertificaat voor on-premises verificatie](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-cert-trust-policy-settings#use-certificate-for-on-premises-authentication) in de Windows Hello-documentatie voor meer informatie.  

  **Standaard**: niet geconfigureerd

- **Beveiligings sleutels gebruiken voor aanmelden**  
  Deze instelling is beschikbaar voor apparaten waarop Windows 10 versie 1903 of hoger wordt uitgevoerd. Gebruik het om ondersteuning voor het gebruik van Windows hello-beveiligings sleutels voor aanmelden te beheren.  

  - **Ingeschakeld** : gebruikers kunnen een Windows hello-beveiligings sleutel gebruiken als aanmeldings referentie voor pc's waarop dit beleid is gericht. 
  - **Uitgeschakeld** : beveiligings sleutels zijn uitgeschakeld en gebruikers kunnen ze niet gebruiken om zich aan te melden bij pc's.   

  **Standaard**: niet geconfigureerd

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
