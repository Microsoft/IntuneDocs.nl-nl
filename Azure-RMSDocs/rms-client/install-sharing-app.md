---
title: De Rights Management-toepassing voor delen downloaden en installeren | Azure RMS
description: U hoeft geen lokale beheerder te zijn om de RMS-toepassing voor delen te installeren Als u echter geen beheerder bent en u Office 2010 gebruikt, zijn er enkele beperkingen. Zie het gedeelte Als u geen lokale beheerder bent en Office 2010 gebruikt op deze pagina voor meer informatie.
author: cabailey
manager: mbaldwin
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 2bf09690-9dba-43b7-9e0a-0110915d4081
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26b043f1f9e7a1e0cd00c2f31c28f7d6685f0232
ms.openlocfilehash: bda09df1ff51565a4bbf501161c7a4f8cdbbfe22


---

# De Rights Management-toepassing voor delen downloaden en installeren

>*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management, Windows 10, Windows 7 met SP1, Windows 8, Windows 8.1*

U hoeft geen lokale beheerder te zijn om de RMS-toepassing voor delen te installeren Als u echter geen beheerder bent en u Office 2010 gebruikt, zijn er enkele beperkingen. Zie voor meer informatie het gedeelte [Als u geen lokale beheerder bent en Office 2010 gebruikt](#if-you-are-not-a-local-administrator-and-use-office-2010) op deze pagina.

## Downloaden en installeren van de Rights Management-toepassing voor delen

1.  Ga naar de [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970)-pagina op de website van Microsoft.

2.  Klik in het gedeelte **Computers** op het pictogram voor de **RMS-app voor Windows** en sla het **setup.exe**-bestand op om de Microsoft Rights Management-toepassing voor delen te installeren.

3.  Dubbelklik op het bestand Setup.exe dat is gedownload. Als u wordt gevraagd om door te gaan, klikt u op **Ja**.

4.  Op de pagina **Microsoft RMS installeren** klikt u op **Volgende** en wacht u totdat de installatie is voltooid.

    > [!NOTE]
    > Voor de RMS-toepassing voor delen is minimaal Microsoft .NET Framework 4.0 vereist. Setup controleert of deze is geïnstalleerd en als dit niet het geval is, ziet u een bericht met een koppeling om deze te installeren.

5.  Wanneer de installatie is voltooid, klikt u op **Opnieuw opstarten** om uw computer opnieuw op te starten en de installatie te voltooien. U kunt ook op **Sluiten** klikken en uw computer later opnieuw opstarten om de installatie te voltooien.

U kunt nu uw bestanden beveiligen of bestanden lezen die anderen hebben beveiligd.

## Als u geen lokale beheerder bent en Office 2010 gebruikt
Als u zich aanmeldt bij uw computer, geen lokale beheerdersrechten hebt en er wordt gedetecteerd dat u Office 2010 hebt geïnstalleerd, dan krijgt u een waarschuwing dat bepaalde scenario's met deze configuratie niet werken. De scenario's:

-   Als uw organisatie Azure RMS in plaats van een lokale versie van RMS gebruikt:

    -   De Information Rights Management (IRM)-functies van Office zijn niet beschikbaar. Bijvoorbeeld de optie **Niet doorsturen** voor e-mailberichten en de machtiging **Beperkte toegang** die u kunt instellen via het menu **Bestand** in Word en Excel. U kunt de optie Beveiligd delen op het lint gebruiken, evenals de snelmenuopties via de Verkenner.

-   Als uw organisatie gebruikmaakt van een on-premises versie van RMS in plaats van Azure RMS:

    -   U kunt geen beveiligd document lezen dat is verzonden door iemand van een andere organisatie die van Azure RMS gebruikmaakt.

Als u geen lokale beheerder bent en u Office 365 of Office 2013 gebruikt, wordt dit bericht niet weergegeven en worden deze scenario's gewoon ondersteund.

U kunt doorgaan met de installatie met deze bekende beperkingen. U kunt ook de installatie stoppen en deze opnieuw uitvoeren met de optie **Als beheerder uitvoeren** wanneer u Setup.exe in stap 3 uitvoert, of u vraagt een beheerder om het programma voor u te installeren. Beheerders kunnen [een script maken voor deze installatie](sharing-app-admin-guide.md#automatic-deployment-for-the-microsoft-rights-management-sharing-application), zodat deze automatisch wordt uitgevoerd.

## Voorbeelden en andere instructies
Voor voorbeelden over hoe u de Rights Management-toepassing voor delen kunt gebruiken en praktische instructies, zie de volgende secties van de gebruikershandleiding voor de Rights Management-toepassing voor delen:

-   [Voorbeelden voor het gebruik van de RMS-toepassing voor delen](sharing-app-user-guide.md#examples-for-using-the-rms-sharing-application)

-   [Wat wilt u doen?](sharing-app-user-guide.md#what-do-you-want-to-do)

## Zie ook
[Gebruikershandleiding voor de Rights Management-toepassing voor delen](sharing-app-user-guide.md)




<!--HONumber=Aug16_HO4-->


