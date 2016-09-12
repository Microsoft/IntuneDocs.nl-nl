---
title: De opties in het dialoogvenster voor de Rights Management-toepassing voor delen | Azure RMS
description: 'Gebruik deze informatie om u te helpen bij de keuze van de opties in de RMS-toepassing voor delen: het dialoogvenster Beveiliging toevoegen of het dialoogvenster Beveiligd delen. U ziet dit dialoogvenster wanneer u een bestand beveiligt om het te delen of wanneer u een bestand in-place beveiligt en u kiest voor aangepaste machtigingen.'
author: cabailey
manager: mbaldwin
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 7b91ab30-6363-4929-bcbd-4dfbd05f644a
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26b043f1f9e7a1e0cd00c2f31c28f7d6685f0232
ms.openlocfilehash: aa0f5456d17564183317e3e693ae63adb8c597c5


---

# De opties in het dialoogvenster voor de Rights Management-toepassing voor delen

>*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management, Windows 10, Windows 7 met SP1, Windows 8, Windows 8.1*

Gebruik deze informatie om u te helpen bij de keuze van de opties in de RMS-toepassing voor delen: het dialoogvenster **Beveiliging toevoegen** of het dialoogvenster **Beveiligd delen**. U ziet dit dialoogvenster wanneer u [een bestand beveiligt om het te delen](sharing-app-protect-by-email.md) of wanneer u [een bestand in-place beveiligt](sharing-app-protect-in-place.md) en u kiest voor aangepaste machtigingen.

> [!IMPORTANT]
> Als de opties die u ziet verschillen van hoe ze hier zijn beschreven, dan hebt u waarschijnlijk niet de meest recente versie van de toepassing voor delen geïnstalleerd. U kunt de nieuwste versie downloaden van de [Microsoft Rights Management](http://go.microsoft.com/fwlink/?LinkId=303970)-pagina.
> 
> Hoe weet u of u de meest recente versie hebt? Zoek naar de **Microsoft Rights Management-toepassing voor delen** die wordt vermeld in Programma’s en onderdelen. Controleer het versienummer. Als u de opties in de tabel wilt zien en gebruiken, moet de versie ten minste **1.0.1770.0** zijn. U kunt het nummer van de meest recente versie op de downloadpagina controleren.

Naast de opties die u kunt kiezen, vraagt u zich mogelijk ook de volgende zaken af:

-   [Wat is het .ppdf-bestand dat automatisch wordt gemaakt?](#what-s-the-ppdf-file-that-s-automatically-created)

-   [Wat is het verschil tussen algemene beveiliging en ingebouwde (systeemeigen) beveiliging?](#what-s-the-difference-between-generic-protection-and-built-in-native-protection)

|Optie|Beschrijving|
|----------|---------------|
|**GEBRUIKERS**|Als u nog geen e-mailadres hebt opgegeven via Outlook, typt u de e-mailadressen van de mensen van wie u wilt dat zij het bestand kunnen openen.<br /><br />Houd er rekening mee dat de RMS-app voor delen niet alle e-mailadressen ondersteunt.<br /><br />Als uw organisatie gebruikmaakt van de on-premises versie van Rights Management (AD RMS), kunt u alleen de e-mailadressen opgeven van mensen uit uw organisatie. Als dit van toepassing is en u probeert om een extern e-mailadres op te geven, krijgt u een bericht te zien waarin staat dat u met uw bedrijfsconfiguratie beveiligde inhoud alleen binnen het bedrijf kunt delen. <br /><br /> Als uw organisatie Azure RMS gebruikt, kunnen de e-mailadressen die u opgeeft, toebehoren aan personen binnen uw organisatie of aan personen in een andere organisatie.<br /><br />Voorbeeld: **janetm@contoso.com; p.dover@fabrikam.com**<br /><br />Persoonlijke e-mailadressen worden momenteel niet ondersteund door de RMS-toepassing voor delen.|
|**Algemene beveiliging**|Als deze optie is geselecteerd, betekent dit dat het geselecteerde bestand niet door het systeem kan worden beveiligd. Zie voor meer informatie [Wat is het verschil tussen algemene beveiliging en ingebouwde (systeemeigen) beveiliging?](#what-s-the-difference-between-generic-protection-and-built-in-native-protection) op deze pagina.|
|**Lezer: alleen weergeven**<br /><br />**Revisor: weergeven en bewerken**<br /><br />**Mede-auteur: weergeven, bewerken, kopiëren en afdrukken**<br /><br />**Mede-eigenaar: alle machtigingen**<br /><br />Opmerking: bij deze opties staat er een rond pictogram voor de naam; dit staat voor een wereldbol. Dit pictogram wordt gebruikt omdat u meestal een van deze opties selecteert wanneer u een bijlage stuurt naar iemand in een andere organisatie.|Selecteer een van deze opties als u de rechten voor het beveiligde document wilt definiëren. Klik op elke optie om een beschrijving weer te geven.<br /><br />Als u voor een van deze opties kiest, hebben alleen de personen die u opgeeft in **GEBRUIKERS**, de rechten die u opgeeft voor het openen en gebruiken van het document. Als ze het document dan bijvoorbeeld naar iemand anders verzenden, kan het niet worden geopend.|
|Beleidssjablonen die de beheerder configureert.<br /><br />Als de naam van uw bedrijf bijvoorbeeld Contoso Ltd is: **Contoso Ltd - alleen vertrouwelijke weergave**<br /><br />Opmerking: bij deze opties staat er een vierkant pictogram voor de naam; dit staat voor een kantoorgebouw. Dit pictogram wordt gebruikt omdat u meestal een van deze opties selecteert wanneer u een bijlage stuurt naar iemand in uw eigen organisatie.|Wanneer u een document deelt met personen die voor uw organisatie werken, ziet u welke beleidssjablonen die de beheerder configureert, er beschikbaar zijn. Selecteer een van deze opties als het document niet buiten uw organisatie mag worden gedeeld.<br /><br />Als u een van deze opties kiest, definieert de beheerder de rechten voor het document en bepaalt deze wie het mag openen.|
|**Deze documenten laten verlopen op**|Selecteer deze optie alleen voor tijdsgebonden bestanden die de gebruikers die u hebt geselecteerd niet kunnen openen na de datum die u opgeeft. U kunt het oorspronkelijke bestand nog wel openen, maar pas na middernacht (in uw huidige tijdzone) op de dag die u hebt opgegeven. Anderen kunnen het bestand niet openen.<br /><br />Deze optie is niet beschikbaar als u een beleidssjabloon selecteert die de beheerder configureert.|
|**Stuur mij een e-mail wanneer iemand dit document probeert te openen**|Opmerking: er is momenteel een preview-versie van de optie beschikbaar.<br /><br />Selecteer deze optie als u e-mailmeldingen wilt ontvangen als iemand het document probeert te openen dat u probeert te beveiligen. Het e-mailbericht geeft aan wie het wanneer heeft geprobeerd te openen en of dit is gelukt.<br /><br />Deze optie is alleen beschikbaar als uw organisatie Azure RMS gebruikt. Als uw organisatie gebruikmaakt van de on-premises versie van Rights Management (AD RMS), ziet u deze optie niet.|
|**Mij toestaan direct toegang tot deze documenten in te trekken**|Selecteer deze optie als u de toegang tot het document later moet intrekken via de site van het documenttrackingsysteem en het intrekken direct moet plaatsvinden. Instellen van deze optie betekent echter dat gebruikers altijd een internetverbinding moeten hebben om het document te lezen op het moment dat het document niet is ingetrokken, telkens wanneer ze het willen openen. Er zijn mogelijk een aantal scenario's waarbij gebruikers geen verbinding kunnen krijgen met internet en gebruikers uw documenten niet kunnen lezen.<br /><br />Als u deze optie niet kiest, kunt u het document nog steeds later intrekken via de site van het documenttrackingsysteem. Omdat gebruikers echter niet altijd een internetverbinding nodig hebben om het document te lezen, weten ze niet direct dat het document is ingetrokken en kunnen ze blijven lezen totdat ze zich aanmelden bij Azure RMS. Het maximumaantal dagen dat iemand een beveiligd document zou kunnen blijven lezen dat u hebt ingetrokken, is standaard 30 dagen, maar een beheerder kan deze waarde wijzigen en meer of minder dagen selecteren.<br /><br />Deze optie is alleen beschikbaar als uw organisatie Azure RMS gebruikt. Als uw organisatie gebruikmaakt van de on-premises versie van Rights Management (AD RMS), ziet u deze optie niet.|

## Wat is het verschil tussen algemene beveiliging en ingebouwde (systeemeigen) beveiliging?

-   Wanneer u een bestand **algemeen beveiligt**, kunnen niet-geautoriseerde personen het bestand niet openen. Maar nadat een geautoriseerd persoon het bestand heeft geopend, kan deze het vervolgens onbeveiligd naar andere mensen doorsturen of het opslaan op een locatie waar anderen bij kunnen. Zij zien echter een bericht waarin wordt uitgelegd welke machtigingen zij hebben voor het bestand en worden gevraagd om zich hieraan te houden. Deze beveiliging kan echter niet worden afgedwongen. Daarnaast kunt u bij de algemene beveiliging van een document de beveiliging niet verder beperken dan autorisatie. U kunt bijvoorbeeld de inhoud niet beperken tot Alleen-lezen of Niet afdrukken:

    > [!NOTE]
    > Een algemeen beveiligd bestand heeft altijd de bestandsnaamextensie **.pfile**.

-   Ter vergelijking: wanneer u de **geïntegreerde (systeemeigen) beveiliging** van Rights Management gebruikt met toepassingen die deze ondersteunen (bijvoorbeeld Office-bestanden), is de beveiliging zelfs op het bestand van toepassing als dit naar iemand anders wordt verzonden of op een andere locatie wordt opgeslagen. En als u deze bestanden beveiligt, dan kunt u beperkte machtigingen gebruiken zoals alleen-lezen, of de machtiging om te bewerken maar niet af te drukken of kopiëren. U kunt bijvoorbeeld **Lezer: alleen weergeven** selecteren, zodat de inhoud niet kan worden bewerkt, afgedrukt of gekopieerd.

Zie het gedeelte [Beveiligingsniveaus: systeemeigen en algemeen](sharing-app-admin-guide-technical.md#levels-of-protection-native-and-generic) in de [Beheerdershandleiding voor de Rights Management-toepassing voor delen](sharing-app-admin-guide.md) voor aanvullende technische informatie.

## Wat is het .ppdf-bestand dat automatisch wordt gemaakt?

-   Wanneer u een beveiligd bestand via e-mail deelt (beveiligd delen), wordt er door de RMS-toepassing voor delen automatisch een **.ppdf**-versie van het bestand gemaakt voor Word, Excel, PowerPoint of PDF. Dit is een alleen-lezen beveiligde versie van het bestand dat alleen daartoe gemachtigde personen kunnen openen en het zorgt ervoor dat de ontvangers de bijlage altijd kunnen lezen, zelfs als ze een mobiel apparaat gebruiken dat geen toepassing heeft die Rights Management ondersteunt. Mits deze mensen een RMS-app voor delen hebben geïnstalleerd, kunnen ze de bijlage lezen.

    In dit scenario wordt gebruikersbeperking afgedwongen, in tegenstelling tot een algemeen beveiligd bestand. De ontvanger kan deze versie van het bestand niet opslaan en als deze bijlage naar iemand anders wordt doorgestuurd, blijven de oorspronkelijke beperkingen op het document. Alleen de personen die gemachtigd zijn voor het beveiligde document kunnen dit openen.

    > [!NOTE]
    > Een .ppdf-bestand wordt automatisch gemaakt wanneer u beveiligd deelt (deelt via e-mail), maar wordt niet gemaakt wanneer u direct beveiligt.

## Voorbeelden en andere instructies
Voor voorbeelden over hoe u de Rights Management-toepassing voor delen kunt gebruiken en praktische instructies, zie de volgende secties van de gebruikershandleiding voor de Rights Management-toepassing voor delen:

-   [Voorbeelden voor het gebruik van de RMS-toepassing voor delen](sharing-app-user-guide.md#examples-for-using-the-rms-sharing-application)

-   [Wat wilt u doen?](sharing-app-user-guide.md#what-do-you-want-to-do)

## Zie ook
[Gebruikershandleiding voor de Rights Management-toepassing voor delen](sharing-app-user-guide.md)




<!--HONumber=Aug16_HO4-->


