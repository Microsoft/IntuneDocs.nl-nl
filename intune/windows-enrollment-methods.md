---
title: Intune-inschrijvingsmethoden voor Windows-apparaten
titleSuffix: Microsoft Intune
description: Informatie over de verschillende manieren waarop u Windows-apparaten in Intune kunt inschrijven
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: ''
ms.openlocfilehash: eda0d77fc5cdb11fa4bc5b21f48ceb7616ecfb15
ms.sourcegitcommit: a63b9eaa59867ab2b0a6aa415c19d9fff4fda874
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2019
ms.locfileid: "67389249"
---
# <a name="intune-enrollment-methods-for-windows-devices"></a>Intune-inschrijvingsmethoden voor Windows-apparaten

Als u apparaten in Intune wilt beheren, moeten ze eerst worden ingeschreven bij de Intune-service. U kunt zowel persoonlijke als zakelijke apparaten inschrijven voor Intune-beheer. 

U kunt apparaten op twee manieren in Intune inschrijven:
- Gebruikers kunnen hun Windows-pc's zelf inschrijven 
- Beheerders kunnen beleidsregels configureren om automatische inschrijving af te dwingen, zonder tussenkomst van een gebruiker

## <a name="user-self-enrollment-in-intune"></a>Zelfinschrijving voor gebruikers in Intune

Gebruikers kunnen hun eigen Windows-apparaat zelf inschrijven via een van deze methoden:

- [BYOD (Bring Your Own Device)](https://docs.microsoft.com/intune-user-help/enroll-windows-10-device): Gebruikers schrijven hun persoonlijke apparaten in door bij de **instellingen** van het apparaat verbinding te maken met een **werk- en schoolaccount**. Dit gebeurt er tijdens dit proces:
    - Het apparaat wordt bij Azure Active Directory ingeschreven voor toegang tot zakelijke resources, zoals e-mail.
    - Het apparaat wordt als persoonlijk apparaat (BYOD) in Intune ingeschreven.
Als een beheerder Automatische inschrijving heeft geconfigureerd (beschikbaar voor Azure AD Premium-abonnementen), hoeft de gebruiker zijn of haar referenties maar eenmaal in te voeren. Anders moeten ze zich afzonderlijk inschrijven via Alleen MDM-inschrijving en hun referenties opnieuw invoeren.  
- **Alleen MDM-inschrijving**: hiermee kunnen gebruikers een bestaande werkgroep, Active Directory of een aan de Azure Active Directory toegevoegde pc in Intune inschrijven. Gebruikers voeren de inschrijving uit via Instellingen op hun bestaande Windows-pc. Deze methode wordt echter niet aanbevolen, aangezien het apparaat hiermee niet bij Azure Active Directory wordt ingeschreven. Ook kunnen bepaalde functies zoals Voorwaardelijke toegang niet worden gebruikt.
- [Azure Active Directory (Azure AD) Join](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network): hiermee voegt u het apparaat toe aan Azure Active Directory en kunnen gebruikers zich bij Windows aanmelden met hun Azure AD-referenties. Als Automatische inschrijving is ingeschakeld, wordt het apparaat automatisch in Intune ingeschreven. Het voordeel van automatische inschrijving is dat de gebruiker maar één stap hoeft uit te voeren. Anders moeten ze zich afzonderlijk inschrijven via Alleen MDM-inschrijving en hun referenties opnieuw invoeren. Gebruikers kunnen zich ofwel tijdens de initiële Windows OOBE of bij Instellingen op deze manier inschrijven. Het apparaat wordt als een zakelijk apparaat in Intune gemarkeerd.
- [Autopilot](enrollment-autopilot.md): deze functie zorgt ervoor dat gebruikers automatisch aan Azure AD worden toegevoegd en dat nieuwe zakelijke apparaten bij Intune worden ingeschreven. Met deze methode zorgt wordt de out-of-the-boxervaring vereenvoudigd. Bovendien hoeven er geen aangepaste installatiekopieën van het besturingssysteem meer op de apparaten te worden toegepast. Als beheerders Intune gebruiken om Autopilot-apparaten te beheren, kunnen ze beleidsregels, profielen, apps en meer beheren op apparaten nadat ze zijn ingeschreven.  Er zijn twee typen Autopilot-implementatie: [De modus voor zelf implementeren](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying) (voor kiosken, digitale handtekeningen of een gedeeld apparaat) en [Gebruikersmodus](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven) (voor traditionele gebruikers). 

## <a name="administrator-based-enrollment-in-intune"></a>Op beheerders gebaseerde inschrijving in Intune

Beheerders kunnen de volgende inschrijvingsmethoden instellen waarvoor geen gebruikersinteractie is vereist:

- Met [Hybrid Azure AD Join](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy) kunnen beheerders het groepsbeleid voor Active Directory zo instellen dat apparaten die met hybride Azure AD zijn samengevoegd automatisch worden ingeschreven. 
- Met [Co-beheer van Configuration Manager](https://docs.microsoft.com/sccm/comanage/overview) kunnen beheerders hun bestaande via Configuration Manager beheerde apparaten bij Intune inschrijven om te profiteren van zowel de voordelen van Intune als die van Configuration Manager. 
- [Apparaatinschrijvingsmanager](device-enrollment-manager-enroll.md) (Device enrollment manager, DEM) is een speciaal serviceaccount. DEM-accounts beschikken over machtigingen waarmee gemachtigde gebruikers meerdere apparaten in bedrijfseigendom kunnen inschrijven en beheren. Dergelijke apparaten zijn bijvoorbeeld geschikt voor gebruik bij een verkooppunt of met hulpprogramma-apps, maar niet voor gebruikers die toegang nodig hebben tot e-mail of bedrijfsresources. Bij deze methode is het gebruik van functies, zoals Voorwaardelijke toegang, niet toegestaan. 
- Met [Bulksgewijs inschrijven](windows-bulk-enroll.md) kunnen gemachtigde gebruikers grote aantallen nieuwe apparaten in bedrijfseigendom samenvoegen met Azure Active Directory en Intune. U maakt een inrichtingspakket met de app Windows Configuration Designer (WCD). Vervolgens kunt u, met behulp van USB-sticks tijdens de initiële Windows OOBE-ervaring of vanaf een bestaande Windows-pc, het inrichtingspakket installeren zodat de apparaten automatisch in Intune worden ingeschreven. Bij deze methode is het gebruik van Voorwaardelijke toegang niet toegestaan. 
- [Inschrijven van apparaten met Windows IoT Core](https://docs.microsoft.com/en-us/windows/iot-core/manage-your-device/intunedeviceenrollment) is mogelijk met door het apparaat voor te bereiden met behulp van het Windows IoT Core-dashboard en vervolgens Windows Configuration Designer te gebruiken om een inrichtingspakket te maken. Dit inrichtingspakket wordt tijdens het opstarten dan vanaf een SD-kaart uitgevoerd om de apparaten automatisch bij Intune te registreren.

## <a name="next-steps"></a>Volgende stappen

[Meer informatie over de mogelijkheden van de Windows-inschrijvingsmethoden](enrollment-method-capab.md)
