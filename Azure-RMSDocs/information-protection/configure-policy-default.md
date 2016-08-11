---
title: Het Azure Information Protection-standaardbeleid | Azure Rights Management
description: 
author: cabailey
manager: mbaldwin
ms.date: 07/21/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 671281c8-f0d1-42b6-aae3-681d1821e2cf
translationtype: Human Translation
ms.sourcegitcommit: 93444affe94b280db2c9e4e2960c6902e491dec6
ms.openlocfilehash: 977cbf2f45cab75aaca9c2a16dd1564c2af2fe4a


---

# Het Azure Information Protection-standaardbeleid

>*Van toepassing op: Azure Information Protection preview*

**[ Deze informatie is voorlopig en kan worden gewijzigd. ]**

Gebruik de volgende informatie om te begrijpen hoe het standaardbeleid voor Azure Information Protection wordt geconfigureerd. Als u het standaardbeleid wijzigt, kunt u naar deze waarden verwijzen om het beleid opnieuw op de standaardinstellingen in te stellen.

## Information Protection-balk

Titel: **Gevoeligheid**

Knopinfo: **Gevoeligheid van informatie bestaat uit vier verschillende niveaus (Openbaar, Intern, Vertrouwelijk en Geheim), zodat de gebruiker kan aangeven wat het risico is wanneer de gegevens voor onbevoegde gebruikers binnen of buiten het bedrijf beschikbaar komen.**


## Labels

Er zijn vijf standaardlabels die de volgende instellingen hebben:

### **Persoonlijk**

Knopinfo: **Alleen voor persoonlijk gebruik. Deze gegevens worden niet bewaakt door de organisatie. Persoonlijke informatie mag geen bedrijfsgerelateerde gegevens bevatten.**

Kleur: lichtgroen

Visuele markeringen: geen

Voorwaarden: geen

Beveiliging: nee

----


### **Openbaar**

Knopinfo: **Dit is interne informatie die door iedereen binnen of buiten het bedrijf kan worden gebruikt.**

Kleur: groen

Visuele markeringen: geen

Voorwaarden: geen

Beveiliging: nee

----

### **Intern**

Knopinfo: **Deze informatie omvat een breed scala aan interne zakelijke gegevens die kunnen worden gebruikt door alle werknemers en kunnen worden gedeeld met geautoriseerde klanten en zakenpartners. Voorbeelden voor interne informatie zijn het bedrijfsbeleid en de meeste interne communicatie.**

Kleur: blauw

Visuele markeringen: voettekst (document en e-mailbericht)

Voorwaarden: geen

Beveiliging: nee

----

### **Vertrouwelijk**

Knopinfo: **Deze gegevens bevatten gevoelige bedrijfsgegevens. Als deze gegevens beschikbaar komen voor onbevoegde gebruikers, kan dit schade aan de organisatie toebrengen. Voorbeelden voor vertrouwelijke informatie zijn werknemersgegevens, individuele klantprojecten of contracten en gegevens van verkoopaccounts.**

Kleur: oranje

Visuele markeringen: voettekst (document en e-mailbericht)

Voorwaarden: geen

Beveiliging: nee

----

### **Geheim**

Knopinfo: **Deze gegevens omvatten uiterst gevoelige informatie voor het bedrijf die moet worden beveiligd. Als deze geheime gegevens beschikbaar komen voor onbevoegde gebruikers, kan dit grote schade aan de organisatie toebrengen. Voorbeelden van geheime informatie zijn persoonlijke identiteitsgegevens, klantrecords, broncode en vooraf aangekondigde financiële rapporten.**

Kleur: rood

Visuele markeringen: voettekst (document en e-mailbericht)

Voorwaarden: geen

Beveiliging: nee

----


## Sublabels

Er zijn twee standaardsublabels die de volgende instellingen hebben:

### Geheim > **Hele bedrijf**

Knopinfo: **Deze gegevens omvatten gevoelige bedrijfsinformatie - toegestaan voor alle werknemers van het bedrijf.**

Visuele markeringen: geen

Voorwaarden: geen

Beveiliging: nee

----

### Geheim > **Mijn groep**

Knopinfo: **Deze gegevens omvatten gevoelige bedrijfsinformatie - alleen toegestaan voor werknemersgroepen.**

Visuele markeringen: geen

Voorwaarden: geen

Beveiliging: nee

## Globale instellingen

**Alle documenten en e-mailberichten moeten een label hebben (automatisch of door gebruikers toegepast)**: Uit

**Het standaardlabel selecteren**: Geen

**Users must provide justification when lowering the sensitivity level (Gebruikers moeten een reden opgeven wanneer ze het gevoeligheidsniveau verlagen)** (bijvoorbeeld van Vertrouwelijk naar Openbaar): Off

## Volgende stappen

Gebruik de koppelingen in de sectie [Het beleid van uw organisatie configureren](configure-policy.md#configuring-your-organization-s-policy) voor meer informatie over het configureren van uw Azure Information Protection-beleid. 



<!--HONumber=Jul16_HO5-->


