---
title: Gegevensoverdracht tussen iOS-apps beheren | Microsoft Intune
description: Begrijpen hoe u Mobile Application Management-beleid in Microsoft Intune gebruikt om gegevensoverdracht tussen apps te beheren.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 8e223301b15a408c5f5a444a1904fca9826929ac
ms.sourcegitcommit: 0142020a7cd75348c6367facf072ed94238e667f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2019
ms.locfileid: "55229896"
---
# <a name="how-to-manage-data-transfer-between-ios-apps-in-microsoft-intune"></a>Gegevensoverdracht beheren tussen iOS-apps met Microsoft Intune

Beperk bestandsoverdrachten ter beveiliging van bedrijfsgegevens tot alleen de apps die u beheert. U kunt iOS-apps op de volgende manieren beheren:

-   Voorkom het verlies van bedrijfsgegevens door voor apps een app-beveiligingsbeleid te configureren. Dergelijke apps worden aangeduid als **door beleid beheerde** apps. Bekijk [alle door Intune beheerde apps die u met app-beveiligingsbeleid kunt beheren](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)

-   Implementeer en beheer apps via het **MDM-kanaal**. Hiermee wordt vereist dat apparaten worden ingeschreven in een MDM-oplossing (Mobile Device Management). De apps die u implementeert, kunnen **door beleid beheerde** apps of andere beheerde apps zijn.

De functie **Openen in beheer** voor iOS-apparaten beperkt de bestandsoverdracht tussen apps die zijn geïmplementeerd via het **MDM-kanaal**. Stel bij de configuratie-instellingen de beperkingen in voor de beheerde *Open in-functie* van iOS en implementeer de apparaten met uw MDM-oplossing.  Wanneer een gebruiker de geïmplementeerde app installeert, worden de door u ingestelde beperkingen toegepast.

##  <a name="use-app-protection-with-ios-apps"></a>App-beveiliging gebruiken met iOS-apps
Gebruik een app-beveiligingsbeleid met de beheerde **Open in-functie** van iOS om bedrijfsgegevens op de volgende manieren te beveiligen:

-   **Apparaten die eigendom zijn van werknemers en die niet worden beheerd met een MDM-oplossing:** u kunt de app-beveiligingsbeleidsinstellingen instellen op **App toestaan om alleen gegevens over te dragen naar door beleid beheerde apps**. Het gedrag *Open-In* in een door beleid beheerde app presenteert alleen andere door beleid beheerde apps als opties voor delen. Als een gebruiker een met beleid beveiligd bestand als bijlage van OneDrive via de systeemeigen e-mail-app probeert te verzenden, is dat bestand onleesbaar.

-   **Apparaten die worden beheerd met Intune:** voor apparaten die zijn ingeschreven in Intune, wordt gegevensoverdracht automatisch toegestaan tussen apps met een app-beveiligingsbeleid en andere beheerde iOS-apps die via Intune zijn geïmplementeerd. Als u wilt opgeven hoe u gegevensoverdracht naar andere apps wilt toestaan, schakelt u **App mag gegevens overdragen naar andere apps** in en kiest u vervolgens het gewenste deelniveau. Als u wilt opgeven hoe u apps wilt toestaan om gegevens te ontvangen van andere apps, schakelt u **App mag gegevens ontvangen van andere apps** in en kiest u vervolgens het gewenste niveau voor het ontvangen van gegevens. U kunt de functie **Openen in beheer** gebruiken om gegevensoverdracht te beheren tussen apps die via Intune zijn geïmplementeerd. Zie [Instellingen voor herlocatie van gegevens](app-protection-policy-settings-ios.md#data-protection) voor meer informatie over het ontvangen en delen van app-gegevens.   

-   **Apparaten die worden beheerd door een externe MDM-oplossing:** met de beheerde functie **Open in** van iOS kunt u de gegevensoverdracht beperken tot alleen beheerde apps.
Als u ervoor wilt zorgen dat apps die u implementeert met behulp van een MDM-oplossing van derden ook onderhevig zijn aan het app-beveiligingsbeleid in Intune, configureert u de UPN-gebruikersinstelling zoals beschreven in de volgende sectie [UPN-gebruikersinstelling configureren](#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm). Wanneer apps zijn geïmplementeerd met de UPN-gebruikersinstelling, wordt het app-beveiligingsbeleid toegepast op de app wanneer de gebruiker zich aanmeldt met zijn/haar werkaccount.

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>UPN-gebruikersinstelling configureren voor Microsoft Intune of EMM van derden
Deze configuratie van de UPN-gebruikersinstelling is **vereist** voor apparaten die worden beheerd door Intune of een EMM-oplossing van derden. De UPN-configuratie werkt met het app-beveiligingsbeleid dat u via Intune implementeert. De volgende procedure is een algemene werkstroom voor het configureren van de UPN-instelling en de daaruit voortvloeiende gebruikerservaring:

1.  In [Azure Portal](https://portal.azure.com) [maakt u beveiligingsbeleid voor apps en wijst u dit toe](app-protection-policies.md) voor iOS. Configureer beleidsinstellingen via de bedrijfsvereisten en selecteer de iOS-apps waarop dit beleid van toepassing moet zijn.

2.  Implementeer de apps en het e-mailprofiel die u wilt laten beheren via Intune of de MDM-oplossing van derden met behulp van de volgende algemene stappen. Deze ervaring wordt ook getoond in *voorbeeld 1*.

3.  Implementeer de app met de volgende app-configuratie-instellingen:

      **sleutel** = IntuneMAMUPN, **waarde** = <username@company.com>

      Voorbeeld: [‘IntuneMAMUPN’, ‘jondoe@microsoft.com’]

4.  Implementeer het beleid **Openen in beheer** met Intune of de MDM-provider van derden op ingeschreven apparaten.


### <a name="example-1-admin-experience-in-intune-or-third-party-mdm-console"></a>Voorbeeld 1: beheerervaring in Intune of MDM-console van derden

1. Ga naar de beheerconsole van Intune of uw MDM-provider van derden. Ga naar de sectie van de console waarin u configuratie-instellingen van toepassingen implementeert op ingeschreven iOS-apparaten.

2. Voer in de sectie Toepassingsconfiguratie de volgende instelling in:

   **sleutel** = IntuneMAMUPN, **waarde** = <username@company.com>

   De juiste syntaxis van het sleutel/waarde-paar kan verschillen op basis van uw MDM-provider van derden. De volgende tabel bevat voorbeelden van externe MDM-providers en de exacte waarden die u voor het sleutel-waardepaar moet invoeren.

   |MDM-provider van derden| Configuratiesleutel | Waardetype | Configuratiewaarde|
   | ------- | ---- | ---- | ---- |
   |Microsoft Intune| IntuneMAMUPN | Tekenreeks | {{UserPrincipalName}}|
   |VMware AirWatch| IntuneMAMUPN | Tekenreeks | {UserPrincipalName}|
   |MobileIron | IntuneMAMUPN | Tekenreeks | ${userUPN} **of** ${userEmailAddress} |
   |ManageEngine Mobile Device Manager | IntuneMAMUPN | Tekenreeks | %upn% |


### <a name="example-2-end-user-experience"></a>Voorbeeld 2: De ervaring voor de eindgebruiker

1.  Een gebruiker installeert de Microsoft Word-app op een apparaat.

2.  De gebruiker start de beheerde systeemeigen e-mail-app om toegang te krijgen tot zijn/haar e-mail.

3.  De gebruiker probeert een document te openen via de systeemeigen e-mail-app in Microsoft Word.

4.  Wanneer de Word-app wordt gestart, wordt de gebruiker gevraagd zich aan te melden met het werkaccount. Het account dat de gebruiker invoert, moet overeenkomen met het account dat u hebt opgegeven in de instellingen voor app-configuratie voor de Microsoft Word-app.

    > [!NOTE]
    > De gebruiker kan het persoonlijke account toevoegen en gebruiken met Word. App-beveiligingsbeleid is niet van toepassing wanneer de gebruiker Word in een andere context dan werk gebruikt. 

5.  Na het aanmelden gelden de instellingen voor het app-beveiligingsbeleid voor de Word-app.

6.  Nu wordt de gegevensoverdracht voltooid en het document in de app getagd als zakelijk document.  De gegevens worden behandeld in een werkcontext en de beleidsinstellingen zijn van toepassing. 

### <a name="validate-user-upn-setting-for-third-party-emm"></a>UPN-gebruikersinstelling voor EMM van derden valideren

Na het configureren van de UPN-gebruikersinstelling valideert u de mogelijkheid van de iOS-app om te voldoen aan het beveiligingsbeleid voor apps van Intune en dit te ontvangen.

De beleidsinstelling **Require app PIN** (Een app-pincode vereisen ) is bijvoorbeeld eenvoudig te testen. Als de beleidsinstelling is ingesteld op **Ja**, ziet de gebruiker een prompt om een pincode in te voeren of in te stellen voordat er toegang tot bedrijfsgegevens kan worden verkregen.

[Maak allereerst een app-beveiligingsbeleid en wijs dit toe](app-protection-policies.md) aan de iOS-app. Zie [App-beveiligingsbeleid valideren](app-protection-policies-validate.md) voor meer informatie over het testen van beveiligingsbeleid voor apps.


### <a name="see-also"></a>Zie tevens
[Wat is een app-beveiligingsbeleid in Intune?](app-protection-policy.md)