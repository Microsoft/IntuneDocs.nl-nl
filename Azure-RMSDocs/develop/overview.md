---
title: Overzicht | Azure RMS
description: AD RMS en Azure RMS bieden technologie voor gegevensbeveiliging waarmee u digitale gegevens beveiligt tegen onbevoegd gebruik.
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 8A13494E-C1D7-407D-BCD1-A406915EA578
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
ms.sourcegitcommit: f7dd88d90357c99c69fe4fdde67c1544595e02f8
ms.openlocfilehash: 417888c5445d702b1f700a8e717fbb746593efc6


---

# Overzicht


Microsoft Rights Management Services (AD RMS en Azure RMS) is een technologie voor gegevensbeveiliging waarmee u digitale gegevens beveiligt tegen onbevoegd gebruik. Via uw toepassingen met rechten kunnen eigenaren van inhoud definiëren wie hun inhoud kan openen, wijzigen, afdrukken, doorsturen of hiermee andere acties kan uitvoeren.

De Microsoft Rights Management SDK 4.2 is beschikbaar voor verschillende platforms. Deze Software Developer Kit (SDK) (een soort framework) is ontworpen voor clientcomputers en apparaten en heeft als doel toegang tot en gebruik van informatie die in toepassingen wordt gebruikt, te beveiligen met rechten. De SDK's voor deze platforms bieden een eenvoudige API voor toepassingsontwikkelaars, zodat ze digitale inhoud kunnen beveiligen of gebruiken, sjablonen kunnen ophalen en beleid kunnen ophalen van een server. Ze kunnen er ook andere gerelateerde rechtenbeheertaken mee uitvoeren.

Voor meer informatie over de momenteel ondersteunde platforms raadpleegt u de portal voor ontwikkelaarsdocumentatie voor de [Microsoft Rights Management SDK](active-directory-rights-management-services-multi-platform-thin-client-sdk-portal.md).

Hier volgen enkele van de mogelijke scenario's:

-   Een advocatenfirma wil voorkomen dat gevoelige e-mailberichten worden afgedrukt of doorgestuurd op mobiele apparaten.
-   De ontwikkelaars van Computer Aided Design- en productiesoftware willen tekentoegang beperken tot een kleine groep gebruikers binnen de onderzoeksafdeling, zonder dat hiervoor wachtwoorden nodig zijn.
-   De eigenaren van een website voor grafisch ontwerp willen één licentie gebruiken die weergave van afbeeldingen met een lage resolutie gratis toestaat, maar betaling vereist voor toegang tot afbeeldingen met een hoge resolutie.
-   De eigenaren van een online documentbibliotheek willen rechten inschakelen voor het weergeven, afdrukken of bewerken van documenten op basis van de identiteit van de gebruiker wanneer documenten worden gedownload naar een mobiel apparaat.
-   Een bedrijf wil gevoelige gegevens over medewerkers publiceren op een interne website waarvoor de rechten voor weergeven en bewerken zijn beperkt tot bepaalde gebruikers.

De MS RMS SDK 4.2 kan worden gedownload en (na bevestiging van en instemming met de gebruiksrechtovereenkomst) vrijelijk worden gedistribueerd met uw software van derden om op clients toegang te geven tot inhoud waarvan de rechten zijn beveiligd door gebruik en implementatie van AD RMS-servers in uw omgeving of door gebruik van Azure RMS-services. Zie [Aan de slag](get-started.md) voor meer informatie.

## SDK-highlights


De MS RMS SDK 4.2 heeft diverse aantrekkelijke nieuwe kenmerken, zoals:

-   **Opnieuw ontworpen API**: de MS RMS SDK 4.2 API is opnieuw ontworpen voor nog meer eenvoud. Ontwikkelaars kunnen daarom gebruikmaken van een eenvoudige en transparante API voor versleuteling en ontsleuteling, die met een minimale inspanning zorgt voor consistentie in het RMS-gedrag.
-   **Hybride ondersteuning voor AD RMS en Azure RMS**: met één RMS-app kunt u inhoud gebruiken en beveiligen via de AD RMS-server (met de mobiele-apparaatextensie van AD RMS) en via de Azure RMS-service. De MS RMS SDK 4.2 detecteert transparant de relevante eindpunten die IT-beheerders kunnen configureren.
-   **Uw eigen verificatiebibliotheek gebruiken**: als toepassingsontwikkelaar kunt u zelf kiezen welke verificatiebibliotheek er door de MS RMS SDK 4.2 moet worden gebruikt. Of u nu de [Azure AD-verificatiebibliotheek](https://msdn.microsoft.com/library/jj573266.aspx) of de aangepaste bibliotheek van uw organisatie wilt gebruiken, de MS RMS SDK 4.2 scheidt de verificatiestack, zodat u de bibliotheek kunt kiezen die het beste aansluit op uw behoeften.
-   **Uw eigen gebruikersinterface gebruiken**: met de MS RMS SDK 4.2 kunt u nu uw eigen aangepaste gebruikersinterface implementeren. De MS RMS SDK 4.2 forceert geen ingebouwde gebruikersinterface op uw apps, of u nu inhoud beveiligt, sjablonen kiest voor weergave of machtigingen wijzigt tijdens het gebruiken van beveiligde inhoud. Als u wilt, kunt u echter voor alle platforms de Microsoft RMS-gebruikersinterfacebibliotheken gebruiken via ons [GitHub-account](https://github.com/AzureAD/).
-   **Offline toegang tot beveiligde inhoud**: met de MS RMS SDK 4.2 kunnen uw app-gebruikers beveiligde inhoud ook openen als er geen verbinding met internet is. De MS RMS SDK 4.2 plaatst het gebruiksbeleid van de beveiligde inhoud veilig in het cachegeheugen, zodat uw gebruikers offline toegang hebben tot met RMS beveiligde gegevens.

Gebruik de handleiding [Aan de slag](get-started.md) om te beginnen met uw apparaat-app-project voor beveiligde informatie.

## Verwante onderwerpen

* [Microsoft Rights Management SDK](active-directory-rights-management-services-multi-platform-thin-client-sdk-portal.md)
* [Aan de slag](get-started.md)
* [Azure AD-verificatiebibliotheek](https://msdn.microsoft.com/en-us/library/jj573266.aspx)
* [GitHub-account](https://github.com/AzureAD/)
 

 






<!--HONumber=Jun16_HO4-->


