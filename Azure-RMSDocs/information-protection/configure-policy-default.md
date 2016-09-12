---
title: Het Azure Information Protection-standaardbeleid | Azure Rights Management
description: Gebruik de volgende informatie om te begrijpen hoe het standaardbeleid voor Azure Information Protection wordt geconfigureerd. Als u het standaardbeleid wijzigt, kunt u naar deze waarden verwijzen om het beleid opnieuw op de standaardinstellingen in te stellen.
manager: mbaldwin
ms.date: 08/08/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 671281c8-f0d1-42b6-aae3-681d1821e2cf
translationtype: Human Translation
ms.sourcegitcommit: c9f9211e7c1dcf293caf81475515114b5433d6a7
ms.openlocfilehash: 89b7a8cb0ca893d4ce29540ef054e19409bd75eb


---

# Het Azure Information Protection-standaardbeleid

>*Van toepassing op: Azure Information Protection preview*

**[ Deze informatie is voorlopig en kan worden gewijzigd. ]**

Gebruik de volgende informatie om te begrijpen hoe het standaardbeleid voor Azure Information Protection wordt geconfigureerd. Als u het standaardbeleid wijzigt, kunt u naar deze waarden verwijzen om het beleid opnieuw op de standaardinstellingen in te stellen.

## Information Protection-balk

|Instelling|Waarde|
|-------------------------------|---------------------------|
|Titel|Gevoeligheid|
|Knopinfo|Gevoeligheid van informatie bestaat uit vier verschillende niveaus (Openbaar, Intern, Vertrouwelijk en Geheim), zodat de gebruiker kan aangeven wat het risico is wanneer de gegevens voor onbevoegde gebruikers binnen of buiten het bedrijf beschikbaar komen.|

## Labels

|Label|Knopinfo|Instellingen|
|-------------------------------|---------------------------|-----------------|
|Persoonlijk|Alleen voor persoonlijk gebruik. Deze gegevens worden niet bewaakt door de organisatie. Persoonlijke informatie mag geen bedrijfsgerelateerde gegevens bevatten.|**Ingeschakeld**: Aan <br /><br />**Kleur**: Lichtgroen<br /><br />**Visuele markeringen**: Uit <br /><br />**Voorwaarden**: Geen<br /><br />**Beveiliging**: Nee|
|Openbaar|Dit is interne informatie die door iedereen binnen of buiten het bedrijf kan worden gebruikt.|**Ingeschakeld**: Aan <br /><br />**Kleur**: Groen<br /><br />**Visuele markeringen**: Uit<br /><br />**Voorwaarden**: Geen<br /><br />**Beveiliging**: Nee|
|Intern|Deze informatie omvat een breed scala aan interne zakelijke gegevens die kunnen worden gebruikt door alle werknemers en kunnen worden gedeeld met geautoriseerde klanten en zakenpartners. Voorbeelden voor interne informatie zijn het bedrijfsbeleid en de meeste interne communicatie.|**Ingeschakeld**: Aan <br /><br />**Kleur**: Blauw <br /><br />**Visuele markeringen**: Voettekst (document en e-mailbericht)<br /><br />**Voorwaarden**: Geen<br /><br />**Beveiliging**: Nee|
|Vertrouwelijk|Deze gegevens bevatten gevoelige bedrijfsgegevens. Als deze gegevens beschikbaar komen voor onbevoegde gebruikers, kan dit schade aan de organisatie toebrengen. Voorbeelden van vertrouwelijke informatie zijn werknemersgegevens, individuele klantprojecten of contracten en gegevens van verkoopaccounts.|**Ingeschakeld**: Aan <br /><br />**Kleur**: Oranje<br /><br />**Visuele markeringen**: Voettekst (document en e-mailbericht)<br /><br />**Voorwaarden**: Geen<br /><br />**Beveiliging**: Nee|
|Geheim|Deze gegevens omvatten uiterst gevoelige informatie voor het bedrijf die moet worden beveiligd. Als deze geheime gegevens beschikbaar komen voor onbevoegde gebruikers, kan dit grote schade aan de organisatie toebrengen. Voorbeelden van geheime informatie zijn persoonlijke identiteitsgegevens, klantrecords, broncode en vooraf aangekondigde financiële rapporten.|**Ingeschakeld**: Aan <br /><br />**Kleur**: Rood<br /><br />**Visuele markeringen**: Voettekst (document en e-mailbericht)<br /><br />**Voorwaarden**: Geen<br /><br />**Beveiliging**: Nee|

## Sublabels

|Label|Knopinfo|Instellingen|
|-------------------------------|---------------------------|-----------------|
|*Geheim* > Hele bedrijf|Deze gegevens omvatten gevoelige bedrijfsinformatie: toegestaan voor alle werknemers van het bedrijf.|**Ingeschakeld**: Aan <br /><br />**Visuele markeringen**: Uit<br /><br />**Voorwaarden**: Geen<br /><br />**Beveiliging**: Nee|
|*Geheim* > Mijn groep|Deze gegevens omvatten gevoelige bedrijfsinformatie: alleen toegestaan voor werknemersgroepen.|**Ingeschakeld**: Aan <br /><br />**Visuele markeringen**: Uit<br /><br />**Voorwaarden**: Geen<br /><br />**Beveiliging**: Nee|

## Globale instellingen

|Instelling|Waarde|
|-------------------------------|---------------------------|
|Alle documenten en e-mailberichten moeten een label hebben (automatisch of door gebruikers toegepast)|Uit|
|Het standaardlabel selecteren|Geen|
|Gebruikers moeten een reden opgeven wanneer ze het vertrouwelijkheidsniveau verlagen (bijvoorbeeld van Vertrouwelijk naar Openbaar)|Uit|


## Volgende stappen

Gebruik de koppelingen in de sectie [Het beleid van uw organisatie configureren](configure-policy.md#configuring-your-organization-s-policy) voor meer informatie over het configureren van uw Azure Information Protection-beleid. 



<!--HONumber=Aug16_HO4-->


