---
# required metadata

title: Aangepaste sjablonen configureren voor Azure Rights Management | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 06/03/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 1775d8d0-9a59-42c8-914f-ce285b71ac1c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Aangepaste sjablonen configureren voor Azure Rights Management

*Van toepassing op: Azure Rights Management, Office 365*

Nadat u [Azure Rights Management (Azure RMS) hebt geactiveerd](activate-service.md), kunnen gebruikers automatisch twee standaardsjablonen gebruiken om gemakkelijk beleidsregels toe te passen op vertrouwelijke bestanden, zodat de toegang wordt beperkt tot gemachtigde gebruikers uit uw organisatie. Voor deze twee sjablonen gelden de volgende rechtenbeleidsbeperkingen:

-   Alleen-lezen weergave voor de beveiligde inhoud

    -   Weergavenaam: **&lt;Naam van de organisatie&gt;: alleen vertrouwelijke weergave**

    -   Specifieke machtiging: inhoud weergeven

-   Machtigingen voor lezen of wijzigen van de beveiligde inhoud

    -   Weergavenaam: **&lt;Naam van de organisatie&gt;: vertrouwelijk**

    -   Specifieke machtigingen: inhoud weergeven, bestand opslaan, inhoud bewerken, toegewezen rechten weergeven, macro's toestaan, doorsturen, beantwoorden, allen beantwoorden

Bovendien kunnen gebruikers met de [RMS-toepassing voor delen](../rms-client/sharing-app-windows.md) hun eigen set machtigingen definiëren. Voor de Outlook-client en voor Outlook Web Access kunnen gebruikers bovendien de optie [Niet doorsturen](../deploy-use/configure-usage-rights.md#do-not-forward-option-for-emails) selecteren.

Voor veel organisaties zijn de standaardsjablonen voldoende. Maar als u uw eigen, aangepaste rechtenbeleidssjablonen wilt maken, is dat mogelijk. Enkele redenen om een aangepaste sjabloon te maken:

-   U wilt een sjabloon hebben om rechten te verlenen aan een subset gebruikers in de organisatie in plaats van aan alle gebruikers.

-   U wilt dat alleen een subset gebruikers een sjabloon (afdelingssjabloon) vanuit toepassingen kan weergeven en selecteren, in plaats van dat alle gebruikers in de organisatie deze kunnen weergeven en selecteren.

-   U wilt een aangepast recht definiëren voor een sjabloon, zoals weergeven en bewerken, maar niet kopiëren en afdrukken.

-   U wilt in een sjabloon aanvullende opties configureren, zoals een vervaldatum en of de inhoud toegankelijk kan zijn zonder internetverbinding.

Als u wilt dat gebruikers een aangepaste sjabloon met dergelijke instellingen kunnen selecteren, moet u eerst een aangepaste sjabloon maken, deze configureren en ten slotte publiceren. Hoewel u waarschijnlijk slechts een paar sjablonen nodig hebt, kunt u in Azure maximaal 500 aangepaste sjablonen opslaan. 

Raadpleeg de volgende informatie voor hulp bij de configuratie en het gebruik van aangepaste sjablonen:

-   [Een aangepaste sjabloon maken, configureren en publiceren](create-template.md)

-   [Een sjabloon kopiëren](copy-template.md)

-   [Sjablonen verwijderen (archiveren)](remove-template.md)

-   [Sjablonen voor gebruikers vernieuwen](refresh-templates.md)

-   [PowerShell gebruiken om sjablonen te beheren](configure-templates-with-powershell.md)




<!--HONumber=Jun16_HO1-->


