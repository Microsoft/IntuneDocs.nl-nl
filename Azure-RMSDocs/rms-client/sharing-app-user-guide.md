---
title: Gebruikershandleiding voor de Rights Management-toepassing voor delen | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: eaf6d02c-aa36-4915-856e-49bb71ab1484
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 384a58f32aae8c7d908392e7fd9a1629bc05cdff
ms.openlocfilehash: d3727eb963532e03137aea2140293fa9c5821db2


---

# Gebruikershandleiding voor de Rights Management-toepassing voor delen

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management, Windows 10, Windows 7 met SP1, Windows 8, Windows 8.1*

Met de Microsoft Rights Management (RMS)-toepassing voor delen voor Windows kunt u belangrijke documenten en foto's veilig afschermen van mensen die deze niet hoeven te zien, zelfs als u deze e-mailt of opslaat op een ander apparaat. U kunt deze toepassing ook gebruiken om bestanden te openen en te gebruiken die andere mensen hebben beveiligd met dezelfde Rights Management-technologie.

U hebt alleen een computer nodig met ten minste Windows 7 met Service Pack 1. [Download en installeer](http://go.microsoft.com/fwlink/?LinkId=303970) vervolgens deze gratis toepassing van Microsoft.

Als u vragen hebt die niet worden beantwoord in deze handleiding, raadpleegt u [Veelgestelde vragen over Microsoft Rights Management-toepassing voor delen voor Windows](http://go.microsoft.com/fwlink/?LinkId=303971). Deze pagina bevat ook informatie over probleemoplossing, voor het geval u op problemen stuit.

## Voorbeelden voor het gebruik van de RMS-toepassing voor delen
Hier volgen enkele voorbeelden van hoe u de RMS-toepassing voor delen zou kunnen gebruiken om uw bestanden te beveiligen.

|Ik wil...|Hoe u dit doet|
|----------------|------------------|
|**… financiële gegevens veilig delen met iemand die ik vertrouw en die voor een andere organisatie werkt**<br /><br />U werkt met een partnerbedrijf en wilt ze een Excel-werkblad mailen met geschatte verkoopcijfers. U wilt dat ze de cijfers kunnen zien, maar niet wijzigen.|Gebruik de knop **Beveiligd delen** in het lint in Excel, typ de e-mailadressen van de twee personen met wie u samenwerkt in het partnerbedrijf, selecteer **Lezer: alleen weergeven** en klik op **Verzenden**.<br /><br />Wanneer de e-mail bij het partnerbedrijf aankomt, kunnen alleen de ontvangers in de e-mail het werkblad bekijken en ze kunnen dit niet opslaan, bewerken, afdrukken of doorsturen.<br /><br />Stapsgewijs: [een bestand beveiligen dat u per e-mail deelt met de Rights Management-toepassing voor delen](sharing-app-protect-by-email.md).|
|**… veilig een document per e-mail verzenden aan iemand die gebruikmaakt van een iOS-apparaat**<br /><br />U wilt een uiterst vertrouwelijk Word-document mailen naar een collega waarvan u weet dat deze regelmatig e-mail bekijkt op zijn iOS-apparaat.|Klik in Verkenner met de rechtermuisknop op het bestand en selecteer **Beveiligd delen** om het bestand als bijlage naar uw collega te verzenden.<br /><br />De ontvanger ontvangt de e-mail op zijn iOS-apparaat. Omdat de ontvanger niet beschikt over Office voor iPad en iPhone, klikt hij op de koppeling in de e-mail waarin wordt uitgelegd hoe de toepassing voor delen kan worden gedownload. Nadat de versie voor iOS-apparaten is geïnstalleerd, kan de ontvanger het document bekijken¹.<br /><br />Stapsgewijs: [een bestand beveiligen dat u per e-mail deelt met de Rights Management-toepassing voor delen](sharing-app-protect-by-email.md).|
|**… controleren wie mijn beveiligde documenten wanneer heeft geopend en indien nodig de toegang intrekken**<br /><br />U hebt een vertrouwelijk ontwerpdocument beveiligd gedeeld met potentiële leveranciers en u wilt zien wie het heeft geopend, wanneer en waar. Als een van de leveranciers vervolgens de opdracht heeft gekregen, wilt u de toegang tot het originele document intrekken zodat de mensen waar u dit mee hebt gedeeld dit niet meer kunnen lezen.|Na het delen van een document per e-mail gaat u naar de [site voor documenttracking](http://go.microsoft.com/fwlink/?LinkId=529562) om te controleren wie het document wanneer heeft geopend. Als u wilt stoppen met delen, selecteert u de optie om toegang in te trekken.<br /><br />Stapsgewijs: [uw documenten bijhouden en intrekken met gebruik van de RMS-toepassing voor delen](sharing-app-track-revoke.md).|
|**… een bijlage lezen die ik in een e-mailbericht heb ontvangen en die is beveiligd, maar die ik niet kan lezen omdat mijn bedrijf geen gebruik maakt van Rights Management**<br /><br />De afzender van het e-mailbericht is iemand die u vertrouwt omdat u al eerder zaken met hem hebt gedaan en u vermoedt dat deze persoon u informatie stuurt over een mogelijke nieuwe zakelijke kans.|U volg de instructies in het e-mailbericht en klikt op de koppeling om u aan te melden bij Microsoft Rights Management. U krijgt van Microsoft een bevestiging dat uw organisatie geen abonnement heeft met Azure Rights Management, u krijgt een e-mail waarin u het gratis aanmeldproces kunt voltooien en u meldt zich aan met uw nieuwe account. U klikt u op de tweede koppeling in het e-mailbericht voor het installeren van de Rights Management-app voor delen en vervolgens kunt u de e-mailbijlage openen om te lezen over de nieuwe zakelijke kans.<br /><br />Stapsgewijs: [bestanden weergeven en gebruiken die zijn beveiligd door Rights Management](sharing-app-view-use-files.md).|
|**… vertrouwelijke bestanden op mijn laptop beveiligen zodat ze niet toegankelijk zijn voor mensen buiten mijn bedrijf**<br /><br />Als u veel op reis bent en uw laptop gebruikt voor toegang tot bestanden en ze wil updaten in een map die beveiligd is tegen onbevoegde toegang.|U hebt de RMS-toepassing voor delen op uw laptop geïnstalleerd. U gebruikt Verkenner om bestanden te beveiligen met een sjabloon waarmee u de bestanden snel kunt beveiligen. Als uw laptop wordt gestolen, hebt u zekerheid dat niemand buiten uw bedrijf toegang heeft tot deze documenten.<br /><br />Stapsgewijs: [een bestand beveiligen op een apparaat &#40;direct beveiligen&#41; met behulp van de Rights Management-toepassing voor delen](sharing-app-protect-in-place.md).|
¹ PDF-Rendering mogelijk gemaakt door Foxit. Copyright © 2003-2014 van Foxit Corporation.

## Wat wilt u doen?
> [!NOTE]
> Voor meer technische informatie, zoals [ondersteunde bestandstypen](sharing-app-admin-guide-technical.md#supported-file-types-and-file-name-extensions) en [hoe u deze toepassing kunt installeren op een bedrijfsnetwerk](sharing-app-admin-guide.md#automatic-deployment-for-the-microsoft-rights-management-sharing-application), raadpleegt u de [Beheerdershandleiding voor de Rights Management-toepassing voor delen](sharing-app-admin-guide.md).

- [Download en installeer de toepassing voor delen](install-sharing-app.md)

- [Een bestand op een apparaat beveiligen (in-place beveiligen)](sharing-app-protect-in-place.md)

- [Een bestand beveiligen dat u per e-mail deelt](sharing-app-protect-by-email.md)

- [Machtigingen voor beveiligde bestanden wijzigen](sharing-app-reprotect-files.md)

- [Uw documenten bijhouden en de toegang hiertoe intrekken](sharing-app-track-revoke.md)

- [Weergeven en gebruiken van bestanden die zijn beveiligd](sharing-app-view-use-files.md)

- [Beveiliging van een bestand verwijderen](sharing-app-remove-protection.md)

- [Sneltoetsen gebruiken](sharing-app-keyboard-shortcuts.md)

- [Geef de instellingen op in het dialoogvenster](sharing-app-dialog-box.md)






<!--HONumber=Jul16_HO3-->


