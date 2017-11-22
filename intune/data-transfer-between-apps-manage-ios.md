---
title: Gegevensoverdracht tussen iOS-apps beheren
titlesuffix: Azure portal
description: Lees dit onderwerp om te begrijpen hoe u de functie iOS openen in en beleidsregels voor het beheren van mobiele apps kunt gebruiken voor het beheren van de gegevensoverdracht tussen apps.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3e4dcd7767620d6d3939686f69ad9d72f6a2d8e2
ms.sourcegitcommit: e692be57ec7044dfc224b70941affbfd7efba421
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/08/2017
---
# <a name="how-to-manage-data-transfer-between-ios-apps"></a>Gegevensoverdracht tussen iOS-apps beheren
## <a name="manage-ios-apps"></a>iOS-apps beheren
Tot het beveiligen van uw bedrijfsgegevens behoort ook het beperken van bestandsoverdracht tot apps die door u worden beheerd.  U kunt iOS-apps op de volgende manieren beheren:

-   Voorkom het verlies van bedrijfsgegevens door voor apps een app-beveiligingsbeleid te configureren. Naar deze apps wordt verwezen als **door beleid beheerde** apps. Zie [alle apps met Intune-functionaliteit die u kunt beheren met app-beveiligingsbeleid](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)

-   U kunt apps ook implementeren en beheren via het **MDM-kanaal**.  Hiervoor is vereist dat apparaten zijn ingeschreven in de MDM-oplossing. Dit kunnen **door beleid beheerde** apps of andere beheerde apps zijn.

De functie **Openen in beheer** voor iOS-apparaten beperkt de bestandsoverdracht tussen apps die zijn geïmplementeerd via het **MDM-kanaal**. Beperkingen voor Openen in beheer worden ingesteld in de configuratie-instellingen en geïmplementeerd met behulp van uw MDM-oplossing.  Wanneer de gebruiker de geïmplementeerde app installeert, worden de door u ingestelde beperkingen toegepast.

##  <a name="using-app-protection-with-ios-apps"></a>App-beveiliging gebruiken met iOS-apps
Een app-beveiligingsbeleid kan worden gebruikt met de iOS-functie **Openen in beheer** om bedrijfsgegevens op de volgende manieren te beveiligen:

-   **Apparaten die eigendom zijn van werknemers en die niet worden beheerd met een MDM-oplossing:** u kunt de app-beveiligingsbeleidsinstellingen instellen op **App toestaan om alleen gegevens over te dragen naar door beleid beheerde apps**. Het gedrag Open-In in een door beleid beheerde app presenteert alleen andere door beleid beheerde apps als een optie voor delen. Als een gebruiker een met beleid beveiligd bestand als bijlage van OneDrive via de systeemeigen e-mail probeert te verzenden, is dat bestand onleesbaar.

-   **Apparaten die worden beheerd met Intune:** voor apparaten die zijn ingeschreven in Intune, wordt de gegevensoverdracht tussen apps met een app-beveiligingsbeleid en andere beheerde iOS-apps die via Intune zijn geïmplementeerd, automatisch toegestaan. Schakel de instelling **Toestaan dat app gegevens overdraagt naar andere apps: Door beleid beheerde apps** in om gegevensoverdracht toe te staan tussen apps met een app-beveiligingsbeleid. U kunt de functie **Openen in beheer** gebruiken om gegevensoverdracht te beheren tussen apps die via Intune zijn geïmplementeerd.   

-   **Apparaten die worden beheerd met een MDM-oplossing van derden:** met behulp van de iOS-functie **Openen in beheer** kunt u de gegevensoverdracht beperken tot alleen beheerde apps.
Als u ervoor wilt zorgen dat apps die u implementeert met behulp van de MDM-oplossing van derden ook onderhevig zijn aan het app-beveiligingsbeleid dat u in Intune hebt geconfigureerd, configureert u de UPN-gebruikersinstelling zoals beschreven in het overzicht [UPN-gebruikersinstelling configureren](#configure-user-upn-setting-for-third-party-emm).  Wanneer apps zijn geïmplementeerd met de UPN-gebruikersinstelling, wordt het app-beveiligingsbeleid toegepast op de app wanneer de eindgebruiker zich aanmeldt met zijn of haar werkaccount.

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>UPN-gebruikersinstelling configureren voor Microsoft Intune of EMM van derden
Deze configuratie van de UPN-gebruikersinstelling is **vereist** voor apparaten die worden beheerd door Intune of een EMM-oplossing van derden. De procedure die hieronder wordt beschreven, is een algemene werkstroom voor het configureren van de UPN-instelling en de daaruit voortvloeiende eindgebruikerservaring:

1.  In [Azure Portal](https://portal.azure.com) [maakt u beveiligingsbeleid voor apps en wijst u dit toe](app-protection-policies.md) voor iOS. Configureer beleidsinstellingen via de bedrijfsvereisten en selecteer de iOS-apps waarop dit beleid van toepassing moet zijn.

2.  Implementeer de apps en e-mailprofielen die u wilt laten beheren via Intune of de MDM-oplossing van derden met behulp van de algemene stappen hieronder. Deze ervaring wordt ook getoond in voorbeeld 1.

3.  Implementeer de app met de volgende app-configuratie-instellingen:

      **sleutel** = IntuneMAMUPN, **waarde** = <username@company.com>

      Voorbeeld: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Implementeer het beleid **Openen in beheer** met Intune of de MDM-provider van derden op ingeschreven apparaten.


### <a name="example-1-admin-experience-in-intune-or-third-party-mdm-console"></a>Voorbeeld 1: beheerervaring in Intune of MDM-console van derden

1. Ga naar de beheerconsole van Intune of uw MDM-provider van derden. Ga naar de sectie van de console waarin u configuratie-instellingen van toepassingen implementeert op ingeschreven iOS-apparaten.

2. Voer in de sectie Toepassingsconfiguratie de volgende instelling in:

  **sleutel** = IntuneMAMUPN, **waarde** = <username@company.com>

  De juiste syntaxis van het sleutel/waarde-paar kan verschillen op basis van uw MDM-provider van derden. De volgende tabel bevat voorbeelden van MDM-providers van derden en de exacte waarden die u voor het sleutel/waarde-paar moet invoeren.

|MDM-provider van derden| Configuratiesleutel | Waardetype | Configuratiewaarde|
| ------- | ---- | ---- | ---- |
|Microsoft Intune| IntuneMAMUPN | Tekenreeks | {UserPrincipalName}|
|VMware AirWatch| IntuneMAMUPN | Tekenreeks | {UserPrincipalName}|
|MobileIron | IntuneMAMUPN | Tekenreeks | ${userUPN} **of** ${userEmailAddress} |


### <a name="example-2-end-user-experience"></a>Voorbeeld 2: eindgebruikerservaring

1.  De eindgebruiker installeert de Microsoft Word-app op het apparaat.

2.  De eindgebruiker start de beheerde systeemeigen e-mail-app om toegang te krijgen tot zijn e-mail.

3.  De eindgebruiker probeert een document te openen via de systeemeigen e-mail-app in Microsoft Word.

4.  Wanneer de Word-app wordt gestart, wordt de eindgebruiker gevraagd zich aan te melden met zijn werkaccount.  Het werkaccount dat de eindgebruiker invoert, moet overeenkomen met het account dat u hebt opgegeven in de configuratie-instellingen van de Microsoft Word-app.

    > [!NOTE]
    > De eindgebruiker kan voor privéwerkzaamheden persoonlijke accounts aan Word toevoegen. Wanneer de Word-app wordt gebruikt in een persoonlijke context, heeft het app-beveiligingsbeleid hier geen invloed op.

5.  Als de aanmelding is geslaagd, worden de beleidsinstellingen toegepast op de Word-app.

6.  Nu wordt de gegevensoverdracht voltooid en het document in de app getagd als zakelijk document. De gegevens worden vervolgens beschouwd als behorende bij een zakelijke context en de beleidsinstellingen worden dienovereenkomstig toegepast.

### <a name="validate-user-upn-setting-for-third-party-emm"></a>UPN-gebruikersinstelling voor EMM van derden valideren

Na het configureren van de UPN-gebruikersinstelling moet u de mogelijkheid valideren van de iOS-app om te voldoen aan het beveiligingsbeleid voor apps van Intune en dit te ontvangen.

De beleidsinstelling **Vereist app-pincode** is bijvoorbeeld eenvoudig visueel te testen op een apparaat. Als de beleidsinstelling is ingesteld op **Ja**, ziet de eindgebruiker een prompt om een pincode in te voeren of in te stellen wanneer die toegang probeert te krijgen tot bedrijfsgegevens.

[Maak allereerst een app-beveiligingsbeleid en wijs dit toe](app-protection-policies.md) aan de iOS-app. Zie [App-beveiligingsbeleid valideren](app-protection-policies-validate.md) voor meer informatie over het testen van beveiligingsbeleid voor apps.


### <a name="see-also"></a>Zie tevens
[Wat is een app-beveiligingsbeleid in Intune?](app-protection-policy.md)
