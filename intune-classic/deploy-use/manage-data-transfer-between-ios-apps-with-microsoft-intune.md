---
title: Gegevensoverdracht beheren tussen iOS-apps | Microsoft Docs
description: Lees dit onderwerp om te begrijpen hoe u de functie iOS openen in en beleidsregels voor het beheren van mobiele apps kunt gebruiken voor het beheren van de gegevensoverdracht tussen apps.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a4515c1-b325-4ac1-9f0a-45ac27e00681
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: c66226b7fc31f91669c4f4f0693ccbd7c679189f
ms.openlocfilehash: e71ebacec9d7b890b41e7650c8c50f42952c6326
ms.lasthandoff: 03/29/2017


---

# <a name="manage-data-transfer-between-ios-apps-with-microsoft-intune"></a>Gegevensoverdracht beheren tussen iOS-apps met Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="manage-ios-apps"></a>iOS-apps beheren
Tot het beveiligen van uw bedrijfsgegevens behoort ook het beperken van bestandsoverdracht tot apps die door u worden beheerd.  U kunt iOS-apps op de volgende manieren beheren:

-   Voorkom het verlies van bedrijfsgegevens door voor apps een app-beveiligingsbeleid te configureren. Naar deze apps wordt verwezen als **door beleid beheerde** apps.

-   U kunt apps ook implementeren en beheren via het **MDM-kanaal**.  Hiervoor is vereist dat apparaten zijn ingeschreven in de MDM-oplossing. Dit kunnen **door beleid beheerde** apps of andere beheerde apps zijn.

Met de functie **Openen in beheer** voor iOS-apparaten kan de bestandsoverdracht worden beperkt tussen apps die zijn geïmplementeerd via het **MDM-kanaal**. Beperkingen voor Openen in beheer worden ingesteld in de configuratie-instellingen en geïmplementeerd met behulp van uw MDM-oplossing.  Wanneer de gebruiker de geïmplementeerde app installeert, worden de door u ingestelde beperkingen toegepast.

##  <a name="manage-data-transfer-between-ios-apps"></a>Gegevensoverdracht tussen iOS-apps beheren
Een beveiligingsbeleid voor apps kan worden gebruikt met de iOS-functie **Openen in beheer** om bedrijfsgegevens op de volgende manieren te beveiligen:

-   **Apparaten die eigendom zijn van werknemers en die niet worden beheerd met een MDM-oplossing:** u kunt de [app-beveiligingsbeleidsinstellingen](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) instellen op **App toestaan om alleen gegevens over te dragen naar beheerde apps**. Wanneer de eindgebruiker een beveiligd bestand opent in een app die niet door beleid wordt beheerd, is het bestand onleesbaar.

-   **Apparaten die worden beheerd met Intune:** voor apparaten die zijn ingeschreven bij Intune wordt de gegevensoverdracht tussen apps met een beveiligingsbeleid voor apps en andere beheerde iOS-apps die via Intune zijn geïmplementeerd automatisch toegestaan. Schakel de instelling **Toestaan dat app gegevens overdraagt naar andere apps: Door beleid beheerde apps** in om gegevensoverdracht toe te staan tussen apps met een app-beveiligingsbeleid. U kunt de functie **Openen in beheer** gebruiken om gegevensoverdracht te beheren tussen apps die via Intune zijn geïmplementeerd.   

-   **Apparaten die worden beheerd met een MDM-oplossing van derden:** met behulp van de iOS-functie **Openen in beheer** kunt u de gegevensoverdracht beperken tot alleen beheerde apps.
Als u ervoor wilt zorgen dat apps die u implementeert met behulp van de MDM-oplossing van derden ook onderhevig zijn aan het app-beveiligingsbeleid dat u in Intune hebt geconfigureerd, configureert u de UPN-gebruikersinstelling zoals beschreven in het overzicht [UPN-gebruikersinstelling configureren](#configure-user-upn-setting-for-third-party-emm).  Wanneer apps zijn geïmplementeerd met de UPN-gebruikersinstelling, wordt het app-beveiligingsbeleid toegepast op de app wanneer de eindgebruiker zich aanmeldt met zijn of haar werkaccount.

> [!IMPORTANT]
> De UPN-gebruikersinstelling is alleen vereist voor apps die zijn geïmplementeerd op apparaten die worden beheerd door een MDM-oplossing van derden.  Deze instelling is niet vereist voor apparaten die worden beheerd met Intune.

## <a name="configure-user-upn-setting-for-third-party-emm"></a>UPN-gebruikersinstelling voor EMM van derden configureren
Deze configuratie van de UPN-gebruikersinstelling is **vereist** voor apparaten die worden beheerd door een EMM-oplossing van derden. De procedure die hieronder wordt beschreven, is een algemene werkstroom voor het configureren van de UPN-instelling en de daaruit voortvloeiende eindgebruikerservaring:


1.  In Azure Portal [configureert u beveiligingsbeleid voor apps](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) voor het iOS-platform. Configureer beleidsinstellingen via de bedrijfsvereisten en selecteer de apps waarop dit beleid van toepassing moet zijn.

2.  Implementeer de apps en e-mailprofielen die u wilt laten beheren **via de MDM-oplossing van derden** met behulp van de algemene stappen hieronder. Deze ervaring wordt ook getoond in voorbeeld 1.

  1.  Implementeer de app met de volgende app-configuratie-instellingen:

      **sleutel** = IntuneMAMUPN, **waarde** = <username@company.com>

      Voorbeeld: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

  2.  Implementeer het beleid Openen in beheer met de MDM-provider van derden op ingeschreven apparaten.


### <a name="example-1-admin-experience-in-third-party-mdm-console"></a>Voorbeeld 1: beheerervaring in MDM-console van derden

1. Ga naar de beheerconsole van uw MDM-provider van derden. Ga naar de sectie van de console waarin u configuratie-instellingen van toepassingen implementeert op ingeschreven iOS-apparaten.

2. Voer in de sectie Toepassingsconfiguratie de volgende instelling in:

  **sleutel** = IntuneMAMUPN, **waarde** = <username@company.com>

  De juiste syntaxis van het sleutel/waarde-paar kan verschillen op basis van uw MDM-provider van derden. De volgende tabel bevat voorbeelden van MDM-providers van derden en de exacte waarden die u voor het sleutel/waarde-paar moet invoeren.

|MDM-provider van derden| Configuratiesleutel | Waardetype | Configuratiewaarde|
| ------- | ---- | ---- | ---- |
| VMware AirWatch | IntuneMAMUPN | Tekenreeks | {UserPrincipalName}|
| MobileIron Core | IntuneMAMUPN | Tekenreeks | $EMAIL$ **of** $USER_UPN$ |
| MobileIron Cloud | IntuneMAMUPN | Tekenreeks | ${userUPN} **of** ${userEmailAddress} |

### <a name="example-2-end-user-experience"></a>Voorbeeld 2: eindgebruikerservaring

1.  De eindgebruiker installeert de Microsoft Word-app op het apparaat.

2.  De eindgebruiker start de beheerde systeemeigen e-mail-app om toegang te krijgen tot zijn e-mail.

3.  De eindgebruiker probeert een document te openen via de systeemeigen e-mail-app in Microsoft Word.

4.  Wanneer de Word-app wordt gestart, wordt de eindgebruiker gevraagd zich aan te melden met zijn werkaccount.  Het werkaccount dat de eindgebruiker invoert, moet overeenkomen met het account dat u hebt opgegeven in de configuratie-instellingen van de Microsoft Word-app.

    > [!NOTE]
    > De eindgebruiker kan voor privéwerkzaamheden persoonlijke accounts aan Word toevoegen. Wanneer de Word-app wordt gebruikt in een persoonlijke context, heeft het app-beveiligingsbeleid hier geen invloed op.

5.  Als de aanmelding is geslaagd, worden de beleidsinstellingen toegepast op de Word-app.

6.  De bestandsoverdracht is voltooid en het document is als bedrijfsidentiteit getagd in de app. Daarnaast wordt het bestand beschouwd als onderdeel van een zakelijke context en de beleidsinstellingen worden dienovereenkomstig toegepast.

### <a name="validate-user-upn-setting-for-third-party-emm"></a>UPN-gebruikersinstelling voor EMM van derden valideren

Na het configureren van de UPN-gebruikersinstelling moet u de mogelijkheid valideren van de iOS-app om te voldoen aan het beveiligingsbeleid voor apps van Intune en dit te ontvangen.

De beleidsinstelling **Vereist app-pincode** is bijvoorbeeld eenvoudig visueel te testen op een apparaat. Als de beleidsinstelling is ingesteld op **Ja**, ziet de gebruiker een prompt om een pincode in te voeren of in te stellen wanneer die toegang probeert te krijgen tot bedrijfsgegevens.

[Creëer allereerst een app-beveiligingsbeleid en implementeer](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) dat op de iOS-app. Zie [App-beveiligingsbeleid valideren](validate-mobile-application-management.md) voor meer informatie over het testen van beveiligingsbeleid voor apps.



### <a name="see-also"></a>Zie tevens
[Bescherm app-gegevens met beveiligingsbeleid voor apps met Micorsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

