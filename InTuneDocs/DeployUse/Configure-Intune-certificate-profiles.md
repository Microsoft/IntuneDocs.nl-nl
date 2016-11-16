---
title: Certificaatprofielen configureren | Microsoft Intune
description: Informatie over het maken van een certificaatprofiel van Intune.
keywords: 
author: nbigman
ms.author: nbigman
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7b4acce1b1861ca2c2d1432b0258ad1e95e46d2a
ms.openlocfilehash: d4fd80ad7819911b6bf47ccd51e62bebdec24f04


---

# Intune-certificaatprofielen configureren
Nadat u de infrastructuur en certificaten hebt geconfigureerd zoals beschreven in [De certificaatinfrastructuur voor SCEP configureren](configure-certificate-infrastructure-for-scep.md) of [De certificaatinfrastructuur voor PFX configureren](configure-certificate-infrastructure-for-pfx.md), kunt u certificaatprofielen maken. Dit is het proces:

- **Taak 1**: het vertrouwde basis-CA-certificaat exporteren
- **Taak 2**: vertrouwde certificaatprofielen maken
- **Taak 3**: een van de twee certificaatprofieltypen maken:
  - SCEP-certificaatprofielen
  - PFX-certificaatprofielen

## **Taak 1**: het vertrouwde basis-CA-certificaat exporteren
Exporteer het certificaat van vertrouwde basiscertificeringsinstanties (CA) als een **.cer** -bestand van de verlenende CA of van een apparaat dat uw verlenende CA vertrouwt. Exporteer de persoonlijke sleutel niet.

U importeert dit certificaat wanneer u een vertrouwd certificaatprofiel configureert.

## **Taak 2**: vertrouwde certificaatprofielen maken
U moet een vertrouwd certificaatprofiel maken voordat u een Simple Certificate Enrollment Protocol- (SCEP) of een PKCS #12-certificaatprofiel (.PFX) kunt maken. U hebt een vertrouwd certificaatprofiel en een SCEP- of PFX-profiel nodig voor elk platform voor mobiele apparaten.

### Een vertrouwd certificaatprofiel maken

1.  Ga naar de [Intune-beheerconsole](https://manage.microsoft.com), kies **Beleid** &gt; **Beleid toevoegen** en kies vervolgens een platform voor apparaten. U kunt een vertrouwd certificaatprofiel maken voor deze apparaten:

-  Android 4 en hoger

-  Android for Work

-  iOS 7.1 en hoger

-  Mac OS X 10.9 en hoger

-  Windows 8.1 en hoger

-  Windows Phone 8.1 en hoger


2.  Een beleid voor een **vertrouwd certificaatprofiel** toevoegen.

    Meer informatie: [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Geef de gevraagde informatie op om de instellingen van het vertrouwde certificaatprofiel voor Android, iOS, Mac OS X, Windows 8.1 of Windows Phone 8.1 te configureren. 
4.  Importeer in de instelling van het **certificaatbestand** het vertrouwde basis-CA-certificaat (CER-bestand) dat u vanuit uw verlenende CA hebt geëxporteerd. De instelling van het **doelarchief** geldt alleen voor apparaten met Windows 8.1 en hoger, en alleen als het apparaat meer dan één certificaatarchief heeft.
    
4.  Kies **Beleid opslaan**.

Het nieuwe beleid wordt weergegeven in de werkruimte **Beleid**. U kunt het nu implementeren.

> [!NOTE]
>
> Android- en Android for Work-apparaten geven een melding weer dat een derde partij een vertrouwd certificaat heeft geïnstalleerd.
    

## **Taak 3**: SCEP- of PFX-certificaatprofielen maken
Nadat u een vertrouwd CA-certificaatprofiel hebt gemaakt, maakt u SCEP- of PFX-certificaatprofielen voor elk platform dat u wilt gebruiken. Wanneer u een SCEP-certificaatprofiel maakt, moet u een vertrouwd certificaatprofiel voor datzelfde platform opgeven. Hierdoor worden de twee certificaatprofielen gekoppeld. U moet nog wel elk profiel afzonderlijk implementeren.

### Een SCEP-certificaatprofiel maken

1.  Kies in de [Intune-beheerconsole](https://manage.microsoft.com) de optie **Beleid** &gt; **Beleid toevoegen** en kies vervolgens een platform voor apparaten.  U kunt een SCEP-certificaatprofiel maken voor deze apparaten:

-  Android 4 en hoger

-  Android for Work

-  iOS 7.1 en hoger

-  Mac OS X 10.9 en hoger

-  Windows 8.1 en hoger

-  Windows Phone 8.1 en hoger

2.  Een beleid voor een **SCEP-certificaatprofiel** toevoegen
    
    Meer informatie: [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Volg de instructies op de profielconfiguratiepagina om de instellingen voor het SCEP-certificaatprofiel te configureren.
    > [!NOTE]
    >
    > Selecteer onder **Indeling van onderwerpnaam** de optie **Aangepast** om een aangepaste indeling voor de naam van de certificaathouder op te geven (alleen in iOS-profielen).
    >
    > De twee variabelen die momenteel worden ondersteund voor de aangepaste indeling zijn `Common Name (CN)` en `Email (E)`. Door een combinatie van deze twee variabelen met statische tekenreeksen te gebruiken, kunt u een aangepaste indeling voor de naam van een certificaathouder maken, bijvoorbeeld:

    >     CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US

    > In dit voorbeeld heeft de beheerder een indeling voor de naam van een certificaathouder gemaakt, waarin naast de variabelen `CN` en `E` gebruik wordt gemaakt van tekenreeksen voor de waarden Organisatie-eenheid, Organisatie, Locatie, Regio en Land. De [functie CertStrToName](https://msdn.microsoft.com/en-us/library/windows/desktop/aa377160.aspx) geeft een lijst met ondersteunde tekenreeksen.

4.  Kies **Beleid opslaan**.

Het nieuwe beleid wordt weergegeven in de werkruimte **Beleid**. U kunt het nu implementeren.

### Een PFX-certificaatprofiel maken

1.  Ga naar de [Intune-beheerconsole](https://manage.microsoft.com), kies **Beleid** &gt; **Beleid toevoegen** en kies vervolgens een platform voor apparaten. PFX-certificaten worden ondersteund voor:
  - Android 4 en hoger
  - Android for Work
  - Windows 10 en hoger
  - Windows Phone 10 en hoger
  - iOS 8.0 en hoger    

    
2.  Een beleid voor een **PFX-certificaatprofiel** toevoegen. 
      Meer informatie: [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).
3.  Geef de benodigde informatie op het beleidsformulier op.
4.  Kies **Beleid opslaan**.

Het nieuwe beleid wordt weergegeven in de werkruimte **Beleid**. U kunt het nu implementeren.

## Certificaatprofielen implementeren
Wanneer u certificaatprofielen implementeert, wordt het certificaatbestand van het vertrouwde CA-certificaatprofiel op het apparaat geïnstalleerd. Het apparaat gebruikt het SCEP- of PFX-certificaatprofiel om een certificaataanvraag te maken.

Certificaatprofielen worden alleen geïnstalleerd op apparaten met het platform dat u gebruikt wanneer u het profiel maakt.

-   U kunt certificaatprofielen implementeren voor gebruikersverzamelingen of voor apparaatverzamelingen.

    > [!TIP]
    > Als u een certificaat snel naar een apparaat wilt publiceren nadat het apparaat is geregistreerd, implementeert u het certificaatprofiel voor een gebruikersgroep en niet voor een apparaatgroep. Als u voor een apparaatgroep implementeert, is een volledige apparaatregistratie vereist voordat het apparaat beleid ontvangt.

-   Hoewel u elk profiel afzonderlijk implementeert, moet u ook het vertrouwde basis-CA- en het SCEP- of PFX-profiel implementeren. Anders mislukt het SCEP- of PFX-certificaatbeleid.

U implementeert certificaatprofielen op dezelfde manier als ander beleid voor Intune:

1.  Selecteer in de werkruimte **Beleid** het beleid dat u wilt implementeren en kies vervolgens **Implementatie beheren**.
2.  In het dialoogvenster **Implementatie beheren** :
    -   **Als u het beleid wilt implementeren**, selecteert u een of meer groepen waarvoor u het beleid wilt implementeren en kiest u **Toevoegen** &gt; **OK**.
    -   **Als u het dialoogvenster wilt sluiten zonder het beleid te implementeren**, kiest u **Annuleren**.

Wanneer u een geïmplementeerd beleid selecteert, kunt u onder aan de lijst met beleidsregels meer informatie over de implementatie bekijken.

### Volgende stappen

Ontdek nu hoe u certificaten kunt gebruiken om e-mail-, Wi-Fi- en VPN-profielen te beveiligen.

-  [De toegang tot zakelijke e-mail configureren met e-mailprofielen](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Wi-Fi-verbindingen in Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)
-  [VPN-verbindingen in Microsoft Intune](vpn-connections-in-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


