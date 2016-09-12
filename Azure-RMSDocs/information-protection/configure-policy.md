---
title: Azure Information Protection-beleid configureren | Azure RMS
description: Als u classificatie, labels en beveiliging wilt configureren, moet u het Azure Information Protection-beleid configureren.
author: cabailey
manager: mbaldwin
ms.date: 08/25/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: ba0e8119-886c-4830-bd26-f98fb14b2933
ms.reviewer: eymanor
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: da0145444a7d0abb6407ed2ccbb581d4dcdd10d6
ms.openlocfilehash: e5b8054b3b5cb38adf2f5ae1d2f4f399d98f6e23


---

# Azure Information Protection-beleid configureren

>*Van toepassing op: Azure Information Protection preview*

**[ Deze informatie is voorlopig en kan worden gewijzigd. ]**

Als u classificatie, labels en beveiliging wilt configureren, moet u het Azure Information Protection-beleid configureren. Dit beleid wordt vervolgens gedownload naar computers waarop de [Azure Information Protection-client](https://www.microsoft.com/en-us/download/details.aspx?id=53018) is geïnstalleerd.

Het Azure Information Protection-beleid configureren tijdens de evaluatierelease van Azure Information Protection:

1. Meld u aan bij [Azure Portal](https://portal.azure.com).

2. Ga naar de blade **Azure Information Protection**: klik bijvoorbeeld in het hub-menu op **Bladeren** en begin met het typen van **Information Protection** in het filtervak. Selecteer in de resultaten **Azure Information Protection**. 

    Vervolgens ziet u de blade **Azure Information Protection** waar u het Azure Information Protection-beleid configureert dat de volgende elementen bevat:

    - Titel en knopinfo voor de Information Protection-balk die voor gebruikers wordt weergegeven in hun Office-toepassingen.

    - Labels waarmee u en gebruikers documenten en e-mailberichten kunnen classificeren.

    - De optie om classificatie af te dwingen wanneer gebruikers documenten opslaan en e-mailberichten verzenden.

    - De optie om een standaardlabel als beginpunt voor het classificeren van documenten en e-mailberichten in te stellen.

    - De optie om gebruikers te vragen een reden op te geven wanneer ze een label selecteren dat een lager gevoeligheidsniveau heeft dan het oorspronkelijke label.


Azure Information Protection wordt geleverd met een [standaardbeleid](configure-policy-default.md) dat de labels **Persoonlijk**, **Openbaar**, **Intern**, **Vertrouwelijk** en **Geheim** bevat. U kunt de standaardlabels zonder wijzigingen gebruiken, of u kunt deze aanpassen of verwijderen of nieuwe labels maken.

Wanneer u wijzigingen op een blade van Azure Information Protection aanbrengt, klikt u op **Opslaan** om de wijzigingen op te slaan of klikt u op **Negeren** om terug te keren naar de laatst opgeslagen instellingen. 

Wanneer u de gewenste wijzigingen hebt aangebracht, klikt u op **Publiceren**. 

Met de Azure Information Protection-client wordt op wijzigingen gecontroleerd wanneer een ondersteunde Office-toepassing wordt gestart en worden de wijzigingen gedownload als Azure Information Protection-beleid.

## Het beleid van uw organisatie configureren

Gebruik de volgende informatie om uw Azure Information Protection-beleid te configureren:

- [Het Information Protection-standaardbeleid](configure-policy-default.md)

- [De globale beleidsinstellingen configureren](configure-policy-settings.md)

- [Een nieuw label maken](configure-policy-new-label.md)

- [Een label verwijderen of opnieuw rangschikken](configure-policy-delete-reorder.md)

- [Een bestaand label wijzigen of aanpassen](configure-policy-change-label.md)

- [Een label configureren om beveiliging toe te passen](configure-policy-protection.md)

- [Een label configureren om visuele markeringen toe te passen](configure-policy-markings.md)

- [Voorwaarden voor automatische en aanbevolen classificatie configureren](configure-policy-classification.md)

## Volgende stappen

Zie [Zelfstudie voor snel starten met Azure Information Protection](infoprotect-quick-start-tutorial.md) voor een voorbeeld van het aanpassen van het standaardbeleid en het resulterende gedrag in een Office-toepassing.




<!--HONumber=Aug16_HO4-->


