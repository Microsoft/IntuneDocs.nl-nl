---
title: Gegevensoverdracht tussen iOS-apps beheren | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: lees dit onderwerp om te begrijpen hoe u de functie iOS openen in en beleidsregels voor het beheren van mobiele apps kunt gebruiken voor het beheren van de gegevensoverdracht tussen apps.'
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: 8846417efd34db32d5a5c872ef438f5a0bc57e36


---

# <a name="how-to-manage-data-transfer-between-ios-apps"></a>Gegevensoverdracht tussen iOS-apps beheren 
## <a name="manage-ios-apps"></a>iOS-apps beheren
Tot het beveiligen van uw bedrijfsgegevens behoort ook het beperken van bestandsoverdracht tot apps die door u worden beheerd.  U kunt iOS-apps op de volgende manieren beheren:

-   Voorkom het verlies van bedrijfsgegevens door voor apps een app-beveiligingsbeleid te configureren. Naar deze apps wordt verwezen als **door beleid beheerde** apps.

-   U kunt apps ook implementeren en beheren via het **MDM-kanaal**.  Hiervoor is vereist dat apparaten zijn ingeschreven in de MDM-oplossing. Dit kunnen **door beleid beheerde** apps of andere beheerde apps zijn.

De functie **Openen in beheer** voor iOS-apparaten beperkt de bestandsoverdracht tussen apps die zijn geïmplementeerd via het **MDM-kanaal**. Beperkingen voor Openen in beheer worden ingesteld in de configuratie-instellingen en geïmplementeerd met behulp van uw MDM-oplossing.  Wanneer de gebruiker de geïmplementeerde app installeert, worden de door u ingestelde beperkingen toegepast.
##  <a name="using-app-protection-with-ios-apps"></a>App-beveiliging gebruiken met iOS-apps
Een app-beveiligingsbeleid kan worden gebruikt met de iOS-functie **Openen in beheer** om bedrijfsgegevens op de volgende manieren te beveiligen:

-   **Apparaten die eigendom zijn van werknemers en die niet worden beheerd met een MDM-oplossing:** u kunt de app-beveiligingsbeleidsinstellingen instellen op **App toestaan om alleen gegevens over te dragen naar beheerde apps**. Wanneer de eindgebruiker een beveiligd bestand opent in een app die niet door beleid wordt beheerd, is het bestand onleesbaar.

-   **Apparaten die worden beheerd met Intune:** voor apparaten die zijn ingeschreven in Intune, wordt de gegevensoverdracht tussen apps met een app-beveiligingsbeleid en andere beheerde iOS-apps die via Intune zijn geïmplementeerd, automatisch toegestaan. Schakel de instelling **Toestaan dat app gegevens overdraagt naar andere apps: Door beleid beheerde apps** in om gegevensoverdracht toe te staan tussen apps met een app-beveiligingsbeleid. U kunt de functie **Openen in beheer** gebruiken om gegevensoverdracht te beheren tussen apps die via Intune zijn geïmplementeerd.   

-   **Apparaten die worden beheerd met een MDM-oplossing van derden:** met behulp van de iOS-functie **Openen in beheer** kunt u de gegevensoverdracht beperken tot alleen beheerde apps.
Als u ervoor wilt zorgen dat apps die u implementeert met behulp van de MDM-oplossing van derden ook onderhevig zijn aan het app-beveiligingsbeleid dat u in Intune hebt geconfigureerd, configureert u de UPN-gebruikersinstelling zoals beschreven in het overzicht [UPN-gebruikersinstelling configureren](#configure-user-upn-setting).  Wanneer apps zijn geïmplementeerd met de UPN-gebruikersinstelling, wordt het app-beveiligingsbeleid toegepast op de app wanneer de eindgebruiker zich aanmeldt met zijn of haar werkaccount.

> [!IMPORTANT]
> De UPN-gebruikersinstelling is alleen vereist voor apps die zijn geïmplementeerd op apparaten die worden beheerd door een MDM-oplossing van derden.  Deze instelling is niet vereist voor apparaten die worden beheerd met Intune.

## <a name="configure-user-upn-setting"></a>UPN-gebruikersinstelling configureren
Deze configuratie is vereist voor apparaten die worden beheerd door een MDM-oplossing van derden. De procedure die hieronder wordt beschreven, toont een algemene werkstroom voor het implementeren van de UPN-instelling en laat het resultaat voor eindgebruikers zien:


1.  In Azure Portal [configureert u MAM-beleid](app-protection-policies.md) voor het iOS-platform. Configureer beleidsinstellingen via de bedrijfsvereisten en selecteer de apps waarop dit beleid van toepassing moet zijn.

2.  Implementeer de apps en het e-mailprofiel die u wilt beheren **via de MDM-oplossing van derden** met behulp van de instelling die wordt beschreven in stap 3 en stap 4.

3.  Implementeer de app met de volgende app-configuratie-instellingen: key=IntuneMAMUPN, Value=<username@company.com> [voorbeeld: ‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Implementeer het beleid Openen in beheer op ingeschreven apparaten.

### <a name="example-end-user-experience"></a>Voorbeeld van resultaat voor eindgebruikers

1.  De eindgebruiker installeert de Microsoft Word-app op het apparaat.

2.  De eindgebruiker start de beheerde systeemeigen e-mail-app om toegang te krijgen tot zijn e-mail.

3.  De eindgebruiker probeert een document te openen via de systeemeigen e-mail-app in Microsoft Word.

4.  Wanneer de Word-app wordt gestart, wordt de eindgebruiker gevraagd zich aan te melden met zijn werkaccount.  Het werkaccount dat de eindgebruiker invoert, moet overeenkomen met het account dat u hebt opgegeven in de configuratie-instellingen van de Microsoft Word-app.

    > [!NOTE]
    > De eindgebruiker kan voor privéwerkzaamheden persoonlijke accounts aan Word toevoegen. Wanneer de Word-app wordt gebruikt in een persoonlijke context, heeft het app-beveiligingsbeleid hier geen invloed op.

5.  Als de aanmelding is geslaagd, worden de beleidsinstellingen toegepast op de Word-app.

6.  Nu wordt de gegevensoverdracht voltooid en het document in de app getagd als zakelijk document. De gegevens worden vervolgens beschouwd als behorende bij een zakelijke context en de beleidsinstellingen worden dienovereenkomstig toegepast.

### <a name="see-also"></a>Zie tevens
[Wat is een app-beveiligingsbeleid in Intune?](what-is-app-protection-policy.md)



<!--HONumber=Feb17_HO1-->


