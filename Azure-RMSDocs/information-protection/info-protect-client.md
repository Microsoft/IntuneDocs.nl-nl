---
title: De Azure Information Protection-client installeren | Azure Rights Management
description: 
author: cabailey
manager: mbaldwin
ms.date: 07/29/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 4445adff-4c5a-450f-aff8-88bf5bd4ca78
translationtype: Human Translation
ms.sourcegitcommit: 93444affe94b280db2c9e4e2960c6902e491dec6
ms.openlocfilehash: c8a7c7d7182df7b525b3425ab378126feb389d9f


---

# De Azure Information Protection-client installeren

>*Van toepassing op: Azure Information Protection preview*

**[ Deze informatie is voorlopig en kan worden gewijzigd. ]**

Als u documenten en e-mailberichten wilt classificeren met Azure Information Protection, moet u eerst de Azure Information Protection-client installeren. Met deze installatie wordt een Information Protection-balk aan uw Office-toepassingen (Word, Excel, PowerPoint, Outlook) toegevoegd waarop de classificatielabels voor uw organisatie worden weergegeven naast een nieuwe groep **Beveiliging** op het tabblad **Start** (Word, Excel, PowerPoint) met een knop genaamd **Beveiligen**:

De volgende afbeelding bevat deze Information Protection-balk en de labels van het [standaardbeleid](configure-policy-default.md):

![Azure Information Protection-balk met standaardbeleid](../media/info-protect-bar-default.png)

Download de Azure Information Protection-client vanuit [Microsoft Downloadcentrum](https://www.microsoft.com/en-us/download/details.aspx?id=53018).

Voordat u de client installeert, controleert u of u de vereiste besturingssysteemversies en toepassingen hebt: [Vereisten voor Azure Information Protection](requirements-azure-infoprotect.md).


## De Azure Information Protection-client handmatig installeren

1. Nadat u [de client hebt gedownload](https://www.microsoft.com/en-us/download/details.aspx?id=53018), voert u **AZInfoProtection.exe** uit en volgt u de prompts om de client te installeren. Deze installatie vereist lokale beheerdersmachtigingen.

    Selecteer de optie om een demobeleid te installeren als u geen verbinding kunt maken met Office 365 of Azure Active Directory, maar de clientzijde van Azure Information Protection wilt zien en ervaren door een lokaal beleid voor demonstratiedoeleinden te gebruiken. Wanneer de client verbinding maakt met een Azure Information Protection-service, wordt dit demobeleid vervangen door het Azure Information Protection-beleid van uw organisatie. 

2. Om met het gebruik van de Azure Information Protection-client te beginnen: als de computer werkt met Office 2010, start u de computer opnieuw op. Start voor andere versies van Office alle Office-toepassingen opnieuw.

## De Azure Information Protection-client voor gebruikers installeren

- U kunt scripts voor de installatie van de Azure Information Protection-client gebruiken en de installatie automatiseren door AZInfoProtection.exe te verpakken en standaard[opdrachtregelopties voor Windows Installer (msiexec)](https://technet.microsoft.com/library/cc759262(v=ws.10).aspx) te gebruiken.

    Als de verpakte versie bijvoorbeeld InfoProtect.msi noemt en u de client zonder interactie wilt installeren: `msiexec /qn InfoProtection.msi`


## De Azure Information Protection-client verwijderen

- Een programma verwijderen via het Configuratiescherm: klik op **Microsoft Azure Information Protection** > **Verwijderen**

## De installatie of verbindingsstatus verifiëren of een probleem melden

1. Open een Office-toepassing en klik op het tabblad **Start** in de groep **Beveiliging** op **Beveiligen** en klik vervolgens op **Help en feedback**.

2. In het dialoogvenster **Microsoft Azure Information Protection** ziet u het volgende:

    - De waarde van **Laatste verbinding** waarmee wordt aangegeven wanneer de client voor het laatst verbinding heeft gemaakt met de Azure Information Protection-service van uw organisatie. Wanneer de client verbinding met de service maakt, wordt automatisch het laatste beleid gedownload als er wijzigingen ten opzichte van het huidige beleid worden gevonden. Als u beleidswijzigingen hebt aangebracht na de weergegeven tijd, sluit u de Office-toepassing en opent u deze opnieuw.

    - Uw weergegeven gebruikersnaam waarmee het account wordt aangegeven dat wordt gebruikt om u te verifiëren bij Azure Information Protection. Deze gebruikersnaam moet overeenkomen met een account dat u voor Office 365 of Azure Active Directory gebruikt.

    - De versie van de Azure Information Protection-client.

    - De koppeling **Feedback verzenden** die u kunt gebruiken om automatisch uw clientlogboeken bij een e-mailbericht te voegen dat voor onderzoek naar het Information Protection-team kan worden verzonden.

    - De koppeling **Diagnose uitvoeren**: deze functionaliteit is momenteel niet geïmplementeerd.

## Bestandslocaties

Clientbestanden:   

- Voor 64 bitsbesturingssystemen: **\ProgramFiles (x86)\Microsoft Azure Information Protection**

- Voor 32 bitsbesturingssystemen: **\Program Files\Microsoft Azure Information Protection**

Clientlogboekbestanden en het momenteel geïnstalleerde beveiligingsbestand:

- Voor 64 bits- en 32 bitsbesturingssystemen: **%localappdata%\Microsoft\MSIP**


## Volgende stappen

Als u de labels op de Information Protection-balk wilt wijzigen, moet u het Azure Information Protection-beleid configureren. Zie [Azure Information Protection-beleid configureren](configure-policy.md) voor meer informatie.

Zie [Zelfstudie voor snel starten met Azure Information Protection](infoprotect-quick-start-tutorial.md) voor een voorbeeld van het aanpassen van het standaardbeleid en het resulterende gedrag in een Office-toepassing. 



<!--HONumber=Jul16_HO5-->


