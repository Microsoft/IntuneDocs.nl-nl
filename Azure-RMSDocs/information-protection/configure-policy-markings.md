---
title: Een label configureren voor visuele markeringen voor Azure Information Protection | Azure Rights Management
description: 
author: cabailey
manager: mbaldwin
ms.date: 08/10/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: df2676eeb062-f25a-4cf8-a782-e59664427d54
translationtype: Human Translation
ms.sourcegitcommit: b2263c212a1b869b778767493645f10ad821828f
ms.openlocfilehash: 78b68c7a502776c6492437e9b8a5c3f1ebf27f95


---

# Een label configureren voor visuele markeringen voor Azure Information Protection

>*Van toepassing op: Azure Information Protection preview*

**[ Deze informatie is voorlopig en kan worden gewijzigd. ]**

Wanneer u een label aan een document of e-mailbericht toewijst, kunt u verschillende opties selecteren om de gekozen classificatie gemakkelijk zichtbaar te maken. Deze visuele markeringen zijn een koptekst, een voettekst en een watermerk:

De visuele markeringen worden toegepast op documenten in Word, Excel en PowerPoint als het label wordt toegepast, en wanneer de documenten worden opgeslagen. Bij e-mailberichten worden de visuele markeringen toegepast wanneer het e-mailbericht wordt verzonden.

Aanvullende informatie over deze visuele markeringen:

- Kopteksten en voetteksten zijn van toepassing op Word, Excel, PowerPoint en Outlook.

- Watermerken zijn van toepassing op Word, Excel en PowerPoint:

    - Excel: watermerken zijn alleen zichtbaar in de modus voor de pagina-indeling en de afdrukvoorbeeldmodus en wanneer het document wordt afgedrukt.

    - PowerPoint: watermerken worden toegepast op het diamodel als achtergrondafbeelding.

- U kunt alleen een tekenreeks opgeven of [variabelen](#using-variables-in-the-text-string) gebruiken om dynamisch een tekenreeks te maken als de kop- of voettekst of het watermerk wordt toegepast. 

Gebruik de volgende instructies voor het configureren van visuele markeringen voor een label.

1. Als u zich nog niet bij [Azure Portal](https://portal.azure.com) hebt aangemeld, meldt u zich nu aan en navigeert u vervolgens naar de blade **Azure Information Protection**. 
    
    Klik bijvoorbeeld in het hub-menu op **Bladeren** en begin met het typen van **Information** in het filtervak. Selecteer **Azure Information Protection**.

2. Selecteer op de blade **Azure Information Protection** het label dat u wilt configureren voor visuele markeringen.

3. Configureer op de blade **Label** in de sectie **Visuele markering instellen (zoals koptekst of voettekst)** de gewenste instellingen voor de visuele markering en klik vervolgens op **Opslaan**:

    - Een koptekst configureren: selecteer voor **Documenten met dit label hebben een koptekst** de optie **Aan** als u een koptekst wilt en **Uit** als u er geen wilt. Als u **Aan** selecteert, geeft u de tekst, grootte, kleur en uitlijning voor de koptekst op.
    
    - Een voettekst configureren: selecteer voor **Documenten met dit label hebben een voettekst** de optie **Aan** als u een koptekst wilt en **Uit** als u er geen wilt. Als u **Aan** selecteert, geeft u de tekst, grootte, kleur en uitlijning voor de voettekst op.
    
    - Een watermerk configureren: selecteer voor **Documenten met dit label hebben een watermerk** de optie **Aan** als u een watermerk wilt en **Uit** als u er geen wilt. Als u **Aan** selecteert, geeft u de tekst, grootte, kleur en indeling voor het watermerk op. 

4. Maak de wijzigingen beschikbaar voor gebruikers door op de blade **Azure Information Protection** op **Publiceren** te klikken.

## Variabelen gebruiken in de tekenreeks

U kunt de volgende variabelen gebruiken in de tekenreeks voor uw koptekst, voettekst of watermerk:

- `${Item.Label}` voor het geselecteerde label

- `${Item.Name}` voor de bestandsnaam of het e-mailonderwerp

- `${Item.Location}` voor het bestandspad

- `${User.Name}` voor de eigenaar van het document of e-mailbericht

- `${Event.DateTime}` voor de datum en tijd waarop het geselecteerde label is ingesteld 
    
Voorbeeld: als u de tekenreeks `Document: ${item.name} Sensitivity: ${item.label}` voor het voettekstlabel Geheim opgeeft, wordt **Document: project.docx Gevoeligheid: Geheim** de voettekst die wordt toegepast op een document genaamd project.docx.

## Volgende stappen

Gebruik de koppelingen in de sectie [Het beleid van uw organisatie configureren](configure-policy.md#configuring-your-organization-s-policy) voor meer informatie over het configureren van uw Azure Information Protection-beleid.  





<!--HONumber=Aug16_HO2-->


