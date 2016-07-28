---
title: Certificaatprofielen configureren | Microsoft Intune
description: Informatie over het maken van een certificaatprofiel van Intune.
keywords: 
author: nbigman
manager: Arob98
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: 40ae2ce3ea4393d24770c010bf5292ca1829a7f1


---

# Intune-certificaatprofielen configureren
Nadat de infrastructuur en certificaten zijn geconfigureerd zoals beschreven in [De certificaatinfrastructuur voor SCEP configureren](configure-certificate-infrastructure-for-scep.md) of [De certificaatinfrastructuur voor PFX configureren](configure-certificate-infrastructure-for-pfx.md), kunt u certificaatprofielen configureren:

**Taak 1**: het vertrouwde basis-CA-certificaat exporteren **Taak 2**: profielen voor een vertrouwd CA-certificaat maken **Taak 3**:

SCEP-certificaatprofielen maken, of

PFX-certificaatprofielen maken

### Taak 1: het vertrouwde basis-CA-certificaat exporteren
Exporteer het vertrouwde basis-CA-certificaat als een **.cer** -bestand van de verlenende CA of een apparaat dat uw verlenende CA vertrouwt. U exporteert de persoonlijke sleutel niet.

U importeert dit certificaat wanneer u een profiel voor een vertrouwd certificaat configureert.

### Taak 2: profielen voor een vertrouwd certificaat maken
U moet een **profiel voor een vertrouwd certificaat** maken voordat u een SCEP- of .pfx-certificaatprofiel kunt maken. U hebt een vertrouwd certificaatprofiel en een SCEP- of .pfs-profiel nodig voor elk platform voor mobiele apparaten.

##### Een profiel voor een vertrouwd certificaat maken

1.  Open de [Intune-beheerconsole](https://manage.microsoft.com) en klik op **Beleid** &gt; **Beleid toevoegen**.

2.  Configureer een van de volgende beleidstypen:

    **Android &gt; Profiel voor vertrouwd certificaat (Android 4 en hoger)**

    **iOS &gt; Profiel voor vertrouwd certificaat (iOS 7.1 en hoger)**

    **Mac OS X &gt; Profiel voor vertrouwd certificaat (Mac OS X 10.9 en hoger)**

    **Windows &gt; Profiel voor vertrouwd certificaat (Windows 8.1 en hoger)**

    **Windows &gt; Profiel voor vertrouwd certificaat (Windows Phone 8.1 en hoger)**

    Meer informatie: [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Geef de gevraagde informatie op om de instellingen van het profiel voor een vertrouwd certificaat voor Android, iOS, Mac OS X, Windows 8.1 of Windows Phone 8.1 te configureren. In de instelling van het **certificaatbestand** importeert u het vertrouwde basis-CA-certificaat (**.cer**) dat u vanuit uw verlenende CA hebt geëxporteerd. De instelling van het **doelarchief** geldt alleen voor apparaten met Windows 8.1 en hoger, en alleen als het apparaat meer dan één certificaatarchief heeft.


4.  Wanneer u klaar bent, klikt u op **Beleid opslaan**.

Het nieuwe beleid wordt weergegeven in de werkruimte **Beleid** en kan nu worden geïmplementeerd.

### Taak 3: SCEP- of PFX-certificaatprofielen maken
Nadat u een profiel voor een vertrouwd CA-certificaat hebt gemaakt, maakt u SCEP- of PFX-certificaatprofielen voor elk platform dat u wilt gebruiken. Wanneer u een SCEP-certificaatprofiel maakt, moet u een profiel voor een vertrouwd certificaat voor datzelfde platform opgeven. Hierdoor worden de twee certificaatprofielen gekoppeld. U moet nog wel elk profiel afzonderlijk implementeren.

##### Een SCEP-certificaatprofiel maken

1.  Open de [Intune-beheerconsole](https://manage.microsoft.com) en klik op **Beleid** &gt; **Beleid toevoegen**.

2.  Configureer een van de volgende beleidstypen:

    **Android &gt; SCEP-certificaatprofiel (Android 4 en hoger)**

    **iOS &gt; SCEP-certificaatprofiel (iOS 7.1 en hoger)**

    **Mac OS X &gt; SCEP-certificaatprofiel (Mac OS X 10.9 en hoger)**

    **Windows &gt; SCEP-certificaatprofiel (Windows 8.1 en hoger)**

    **Windows &gt; SCEP-certificaatprofiel (Windows Phone 8.1 en hoger)**

    Meer informatie: [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Volg de instructies op de profielconfiguratiepagina om de instellingen voor het SCEP-certificaatprofiel te configureren.

4.  Wanneer u klaar bent, klikt u op **Beleid opslaan**.

Het nieuwe beleid wordt weergegeven in de werkruimte **Beleid** en kan nu worden geïmplementeerd.

##### Een PFX-certificaatprofiel maken

1.  Open de [Intune-beheerconsole](https://manage.microsoft.com) en klik op **Beleid** &gt; **Beleid toevoegen**.

2.  Configureer een van de volgende beleidstypen:



-   **Android &gt;.pfx-certificaatprofiel (Android 4 en hoger)**

    -   **Windows &gt; PKCS #12 (.pfx)-certificaatprofiel (Windows 10 en hoger)**

    -   **Windows &gt; PKCS #12 (.pfx)-certificaatprofiel (Windows Phone 10 en hoger)**

    -    **iOS > PKCS #12-certificaatprofiel (.pfx) (iOS 7.1 en hoger)**    

    Meer informatie: [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Geef de benodigde informatie op het beleidsformulier op.

4.  Wanneer u klaar bent, klikt u op **Beleid opslaan**.

Het nieuwe beleid wordt weergegeven in de werkruimte **Beleid** en kan nu worden geïmplementeerd.

## Certificaatprofielen implementeren
Wanneer u certificaatprofielen implementeert, wordt het certificaatbestand van het profiel voor het vertrouwde CA-certificaat op apparaten geïnstalleerd en wordt het SCEP- of PFX-certificaatprofiel door het apparaat gebruikt om een certificaataanvraag van het apparaat te maken.

Certificaatprofielen worden alleen op toepasselijke apparaten geïnstalleerd op basis van het platform dat u gebruikt wanneer u het profiel maakt.

-   U kunt certificaatprofielen implementeren voor gebruikersverzamelingen of apparaatverzamelingen.

    > [!TIP]
    > Als u wilt toestaan dat certificaten snel naar apparaten worden gepubliceerd nadat het apparaat is ingeschreven, implementeert u het certificaatprofiel voor een gebruikersgroep (geen apparaatgroep). Als u voor een apparaatgroep implementeert, moet een volledige apparaatinschrijving plaatsvinden voordat het apparaat beleid ontvangt.

-   Hoewel elk profiel afzonderlijk wordt geïmplementeerd, moeten zowel het vertrouwde basisprofiel als het SCEP/PFX-profiel worden geïmplementeerd, omdat het SCEP/PFX-profielbeleid anders mislukt.

U implementeert certificaatprofielen op dezelfde manier als u ander beleid voor Intune implementeert:

1.  Selecteer het beleid dat u wilt implementeren in de werkruimte **Beleid** en klik vervolgens op **Implementatie beheren**.

2.  In het dialoogvenster **Implementatie beheren** :

    -   **Het beleid implementeren**: selecteer een of meer groepen waarvoor u het beleid wilt implementeren en klik vervolgens op **Toevoegen** &gt; **OK**.

    -   **Het dialoogvenster sluiten zonder het beleid te implementeren**: klik op **Annuleren**.

Wanneer u een geïmplementeerde beleid selecteert, kunt u meer informatie over de implementatie weergeven onder in de lijst met beleidsregels.
###  Volgende stappen

U kunt nu certificaten gebruiken om e-mail-, Wi-Fi- en VPN-profielen te beveiligen:

-  [De toegang tot zakelijke e-mail configureren met e-mailprofielen](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Wi-Fi-verbindingen in Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)
-  [VPN-verbindingen in Microsoft Intune](vpn-connections-in-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


