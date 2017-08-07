---
title: ARTIKELTITEL | SERVICENAAM
description: 
keywords: 
author: GITHUB USERNAME
manager: ALIAS
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: GET ONE FROM guidgenerator.com
ms.openlocfilehash: 68090a038cec49009b6bd0ce0515a075f62483b8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="metadata-and-markdown-template"></a>Metagegevens en markdown-sjabloon

Deze docs.ms-sjabloon bevat voorbeelden van markdown-syntaxis, evenals richtlijnen voor het instellen van de metagegevens. De sjabloon is beschikbaar in de hoofdmap van elke EM-testopslagplaats (bijvoorbeeld ~/Azure-RMSDocs-pr/template.md) en is bedoeld om te lezen als markdown-bestand, maar u kunt [de gepubliceerde versie](https://stage.docs.microsoft.com/en-us/rights-management/template) raadplegen om te zien hoe de markdown-voorbeelden worden weergegeven.

Wanneer u een markdown-bestand maakt, moet u de sjabloon naar een nieuw bestand kopiëren, de metagegevens invullen zoals hieronder aangegeven, de H1-kop boven aan de titel van het artikel instellen en de inhoud verwijderen. 


## <a name="metadata"></a>Metagegevens 

Het volledige metagegevensblok staat hierboven, onderverdeeld in verplichte en optionele velden. Zie het [OPS-referentieoverzicht voor metagegevens](https://ppe.msdn.microsoft.com/en-us/ce-csi-docs/ops/ops-onboarding/managing-content/content-meta-data) voor meer informatie. Een aantal belangrijke opmerkingen:

- Voor een metagegevenselement **moet** er een spatie staan tussen de dubbele punt (:) en de waarde.
- Als een optioneel metagegevenselement geen waarde heeft, markeert u het element als commentaar met een # (laat het element niet leeg en gebruik niet 'n.v.t.'). Als u een waarde toevoegt aan een element dat is gemarkeerd als commentaar , moet u # verwijderen.
- Door dubbele punten in een waarde (bijvoorbeeld een titel) wordt de metagegevensparser verbroken. Gebruik in plaats daarvan de HTML-codering van &#58; (bijvoorbeeld 'titel: Azure Rights Management &#58; de basisbeginselen | Azure RMS').
- **titel**: deze titel wordt weergegeven in zoekmachineresultaten. De titel moet eindigen met een sluisteken (|), gevolgd door de naam van de service (zoals hierboven). De titel hoeft niet gelijk te zijn (waarschijnlijk is dit ook geen goed idee) aan de titel in de H1-kop. De titel moet ongeveer 65 tekens bevatten (inclusief | SERVICENAAM).
- **auteur**, **manager**, **revisor**: het veld 'auteur' moet de **Github-gebruikersnaam** van de auteur bevatten, niet zijn alias.  De velden manager en reviewer moeten daarentegen wel een alias bevatten. ms.reviewer geeft de naam aan van de projectmanager die is gekoppeld aan het artikel of de service.
- **MS.AssetID**: dit is de GUID van het artikel van CAPS. Haal bij het maken van een nieuw markdown-bestand een GUID op van [https://www.guidgenerator.com](https://www.guidgenerator.com). 
- **MS.prod**, **ms.service**, **ms.technology**, **ms.devlang**, **ms.topic**, **ms.tgt_pltfrm**: mogelijke waarden voor deze elementen vindt u [hier](https://microsoft.sharepoint.com/teams/STBCSI/Insights/_layouts/15/WopiFrame.aspx?sourcedoc=%7b7A321BF1-0611-4184-84DA-A0E964C435FA%7d&file=WEDCS_MasterList_CSIValues.xlsx&action=default).

## <a name="basic-markdown-and-gfm"></a>Basis-markdown en markdown met een vleugje GitHub

Alle basis-markdown en markdown met een vleugje GitHub worden ondersteund. Zie voor meer informatie hierover:

- [Baseline markdown syntax](https://daringfireball.net/projects/markdown/syntax) (Engelstalig)
- [Engelstalige documentatie over Github-flavored markdown (GFM)](https://guides.github.com/features/mastering-markdown)

## <a name="headings"></a>Koppen

Voorbeelden van koppen op het eerste en tweede niveau staan hierboven. 

Er mag **slechts één kop** van het eerste niveau in uw onderwerp staan. Deze wordt weergegeven als de titel op de pagina.  

Koppen op het tweede niveau genereren de inhoudsopgave op de pagina die wordt weergegeven in de sectie 'In dit artikel' onder de titel op de pagina.

### <a name="third-level-heading"></a>Kop op derde niveau
#### <a name="fourth-level-heading"></a>Kop op vierde niveau
##### <a name="fifth-level-heading"></a>Kop op vijfde niveau
###### <a name="sixth-level-heading"></a>Kop op zesde niveau

## <a name="text-styling"></a>Tekstopmaak

*Cursief* 

**Vet** 

~~Doorhalen~~



## <a name="links"></a>Links

Als u een koppeling wilt maken naar een bestand in dezelfde repo, gebruikt u [relatieve koppelingen](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2). 

- Voorbeeld: [Wat is Azure Rights Management?](./understand-explore/what-is-azure-rights-management.md)

Als u een koppeling wilt maken naar een kop in hetzelfde markdown-bestand, bekijkt u de bron van het gepubliceerde artikel en zoekt u de id van de kop op (bijvoorbeeld `id="blockquote"`, en maakt u een koppeling met # + id (bijvoorbeeld `#blockquote`)).

- Voorbeeld: [Blockquotes](#blockquote)

Als u een koppeling wilt maken naar een kop in een markdown-bestand in dezelfde repo, gebruikt u een relatieve koppeling + hashtagkoppeling.

- Voorbeeld: [technisch overzicht van het aanmeldingsproces](./understand-explore/rms-for-individuals-user-signup.md#technical-overview-of-the-sign-up-process)

Als u een koppeling wilt maken naar een extern bestand, gebruikt u de volledige URL als koppeling.

- Voorbeeld: [Github](http://www.github.com)

Als een URL wordt weergegeven in een markdown-bestand, wordt deze omgezet in een aanklikbare koppeling.

- Voorbeeld: http://www.github.com

## <a name="lists"></a>Lijsten

### <a name="ordered-lists"></a>Geordende lijsten

1. Deze 
1. Is
1. Een
1. Geordende
1. Lijst  


#### <a name="ordered-list-with-an-embedded-list"></a>Geordende lijst met een ingesloten lijst

1. Hier
1. komt
1. een
1. ingesloten
    1. Mevr. Scarlett
    1. Professor Plum
1. geordende
1. lijst


### <a name="unordered-lists"></a>Niet-geordende lijsten

- Deze
- is
- a
- met opsommingstekens
- lijst


##### <a name="unordered-list-with-an-embedded-lists"></a>Niet-geordende lijst met een ingesloten lijst

- Deze 
- met opsommingstekens 
- lijst
    - Mevr. Peacock
    - Dhr. Green
- bevat  
- andere
    1. Kolonel Mustard
    1. Mevr. White
- lijsten


## <a name="horizontal-rule"></a>Horizontale lijn

---

## <a name="tables"></a>Tabellen

| Tabellen        | Zijn           | Leuk  |
| ------------- |:-------------:| -----:|
| kol. 3 is      | rechts uitgelijnd | $ 1600 |
| kol. 2 is      | gecentreerd      |   $ 12 |
| kol. 1 is standaard | links uitgelijnd     |    $ 1 |


## <a name="code"></a>Code

### <a name="codeblock"></a>Codeblock

    function fancyAlert(arg) {
      if(arg) {
        $.docs({div:'#foo'})
      }
    }

### <a name="in-line-code"></a>Inline code

Dit is een voorbeeld van `in-line code`.

## <a name="blockquotes"></a>Blockquotes

> De droogte had nu tien miljoen jaar geduurd en aan de heerschappij van de verschrikkelijke hagedissen was allang een einde gekomen. Hier op de evenaar, op het continent dat op een dag bekend zou staan als Afrika, had de strijd om het bestaan een nieuw hoogtepunt van wreedheid bereikt. Wie de overwinning zou behalen, was nog niet bekend. In dit barre en dorre land konden alleen kleine, snelle of dappere wezens overleven of gedijen.

## <a name="images"></a>Installatiekopieën

### <a name="static-image"></a>Statische afbeelding

![dit is de alt-tekst](./media/AzRMS_elements.png)

### <a name="linked-image"></a>Gekoppelde afbeelding

[![alt-tekst voor gekoppelde afbeelding](./media/AzRMS_elements.png)](https://azure.microsoft.com) 

### <a name="animated-gif"></a>GIF-animatie

![GIF-animatie](./media/hololens.gif)

## <a name="alerts"></a>Waarschuwingen

### <a name="note"></a>Opmerking

> [!NOTE]
> Dit is een OPMERKING

### <a name="warning"></a>Waarschuwing

> [!WARNING]
> Dit is een WAARSCHUWING

### <a name="tip"></a>Tip

> [!TIP]
> Dit is een TIP

### <a name="important"></a>Belangrijk

> [!IMPORTANT]
> Dit is BELANGRIJK

## <a name="videos"></a>Video 's

### <a name="channel-9"></a>Kanaal 9

<iframe src="http://channel9.msdn.com/Series/Azure-Active-Directory-Videos-Demos/Azure-Active-Directory-Connect-Express-Settings/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>


### <a name="youtube"></a>YouTube

<iframe width="420" height="315" src="https://www.youtube.com/embed/R6_eWWfNB54" frameborder="0" allowfullscreen></iframe>

## <a name="docsms-extentions"></a>docs.ms-uitbreidingen

### <a name="button"></a>Knop

> [!div class="button"]
[knop voor koppelingen](/rights-management)

### <a name="selector"></a>Kiezer

> [!div class="op_single_selector"]
- [foo](/rights-management/template.md)
- [bar](/rights-management/scratch.md)

### <a name="step-by-step"></a>Stapsgewijs

>[!div class="step-by-step"]
[Vorige](https://www.example.com)
[Volgende](https://www.example.com)