---
title: Gegevensoverdracht tussen iOS-apps beheren
titleSuffix: Microsoft Intune
description: Begrijpen hoe u Mobile Application Management-beleid in Microsoft Intune gebruikt om gegevensoverdracht tussen apps te beheren.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/08/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d10b2d64-8c72-4e9b-bd06-ab9d9486ba5e
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: eaf381d6d7b6bf8e9508eac4ccfc5431aa008658
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724942"
---
# <a name="how-to-manage-data-transfer-between-ios-apps-in-microsoft-intune"></a>Gegevensoverdracht beheren tussen iOS-apps met Microsoft Intune

Beperk bestandsoverdrachten ter beveiliging van bedrijfsgegevens tot alleen de apps die u beheert. U kunt iOS-apps op de volgende manieren beheren:

- Beveilig organisatiegegevens voor werk-of schoolaccounts door een app-beveiligingsbeleid te configureren voor de apps. Dit noemen we *door beleid beheerde apps*.  Bekijk [alle door Intune beheerde apps die u met app-beveiligingsbeleid kunt beheren](https://www.microsoft.com/cloud-platform/microsoft-intune-apps)

- Implementeer en beheer apps via iOS-apparaatbeheer. Hiervoor moeten apparaten worden ingeschreven in een MDM-oplossing (Mobile Device Management). De apps die u implementeert, kunnen *door beleid beheerde apps* of andere door iOS beheerde apps zijn.

De functie **Open-in management** voor ingeschreven iOS-apparaten beperkt de bestandsoverdracht tussen door iOS beheerde apps. Stel bij de configuratie-instellingen de beperkingen in voor de beheerde *Open-in-functie* van iOS en implementeer de apparaten met uw MDM-oplossing.  Wanneer een gebruiker de geïmplementeerde app installeert, worden de door u ingestelde beperkingen toegepast.

## <a name="use-app-protection-with-ios-apps"></a>App-beveiliging gebruiken met iOS-apps
Gebruik een app-beveiligingsbeleid met de beheerde **Open-in-functie** van iOS om bedrijfsgegevens op de volgende manieren te beveiligen:

- **Apparaten die niet worden beheerd door een MDM-oplossing:** U kunt de instellingen voor het beveiligingsbeleid voor apps instellen om het delen van gegevens met andere toepassingen te beheren via *Open-in* of *share-extensies*.  Als u dit wilt doen, moet u **Organisatiegegevens naar andere apps verzenden** instellen op de waarde **Door beleid beheerde apps met filteren op 'Openen in/delen'** .  Het gedrag *Openen in/delen* in de *door beleid beheerde app* presenteert alleen andere *door beleid beheerde apps* als opties voor delen. 

- **Apparaten die worden beheerd door MDM-oplossingen**: Voor apparaten die zijn ingeschreven bij Intune of externe MDM-oplossingen, wordt het delen van gegevens tussen apps met app-beveiligingsbeleid en andere beheerde iOS-apps die via MDM zijn geïmplementeerd, beheerd door Intune App-beleid en de iOS-functie **Openen in management**. Als u ervoor wilt zorgen dat apps die u implementeert met behulp van een MDM-oplossing, ook onderhevig zijn aan het app-beveiligingsbeleid in Intune, configureert u de UPN-gebruikersinstelling zoals beschreven in het volgende gedeelte: [UPN-gebruikersinstelling configureren](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm). Als u wilt opgeven hoe u gegevensoverdracht naar andere apps wilt toestaan, schakelt u **Organisatiegegevens naar andere apps verzenden** in en kiest u vervolgens het gewenste deelniveau. Als u wilt opgeven hoe u apps wilt toestaan om gegevens te ontvangen van andere apps, schakelt u **Organisatiegegevens naar andere apps verzenden** in en kiest u vervolgens het gewenste niveau voor het ontvangen van gegevens. Zie [Instellingen voor herlocatie van gegevens](app-protection-policy-settings-ios.md#data-protection) voor meer informatie over het ontvangen en delen van app-gegevens.

## <a name="configure-user-upn-setting-for-microsoft-intune-or-third-party-emm"></a>UPN-gebruikersinstelling configureren voor Microsoft Intune of EMM van derden
Deze configuratie van de UPN-gebruikersinstelling is **vereist** voor apparaten die worden beheerd door Intune of een EMM-oplossing van derden om het geregistreerde gebruikersaccount vast te stellen. De UPN-configuratie werkt met het app-beveiligingsbeleid dat u via Intune implementeert. De volgende procedure is een algemene werkstroom voor het configureren van de UPN-instelling en de daaruit voortvloeiende gebruikerservaring:

1. In [Azure Portal](https://portal.azure.com) [maakt u beveiligingsbeleid voor apps en wijst u dit toe](app-protection-policies.md) voor iOS. Configureer beleidsinstellingen via de bedrijfsvereisten en selecteer de iOS-apps waarop dit beleid van toepassing moet zijn.

2. Implementeer de apps en het e-mailprofiel die u wilt laten beheren via Intune of de MDM-oplossing van derden met behulp van de volgende algemene stappen. Deze ervaring wordt ook getoond in *voorbeeld 1*.

3. Implementeer de app met de volgende app-configuratie-instellingen naar het beheerde apparaat:

      **sleutel** = IntuneMAMUPN, **waarde** = <username@company.com>

      Voorbeeld: [‘IntuneMAMUPN’, ‘janellecraig@contoso.com’]
      
     > [!NOTE]
     > In Intune moet het inschrijvingstype van het App Configuration-beleid zijn ingesteld op **Beheerde apparaten**.
     > Verder moet de app worden geïnstalleerd vanuit de Intune-bedrijfsportal (als deze als beschikbaar is ingesteld) of naar het apparaat worden gepusht. 

4. Implementeer het beleid **Openen in beheer** met Intune of de MDM-provider van derden op ingeschreven apparaten.


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
   |Beheer van Citrix-eindpunt | IntuneMAMUPN | Tekenreeks | ${user.userprincipalname} |
   |ManageEngine Mobile Device Manager | IntuneMAMUPN | Tekenreeks | %upn% |

> [!NOTE]  
> Als u voor de Outlook-app in iOS een App Configuration-beleid implementeert met de optie 'Configuratiedesigner gebruiken', wordt de configuratiesleutel IntuneMAMUPN op de achtergrond automatisch geconfigureerd voor het beleid. Raadpleeg voor meer informatie het gedeelte met veelgestelde vragen in [New Outlook for iOS and Android App Configuration Policy Experience – General App Configuration](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Outlook-for-iOS-and-Android-App-Configuration-Policy/ba-p/370481) (Nieuwe App Configuration-beleidservaring voor Outlook voor iOS en Android: algemene appconfiguratie). 


### <a name="example-2-end-user-experience"></a>Voorbeeld 2: De ervaring voor de eindgebruiker

*Delen vanuit een* door beleid beheerde app *naar andere toepassingen met delen van het besturingssysteem*

1. Een gebruiker opent de app Microsoft OneDrive op een geregistreerd iOS-apparaat en meldt zich aan met zijn of haar werkaccount.  Het account dat de gebruiker invoert, moet overeenkomen met de UPN van het account dat u hebt opgegeven in de configuratie-instellingen voor de app Microsoft OneDrive.

2. Nadat u zich hebt aangemeld, zijn de door de beheerder geconfigureerde app-instellingen van toepassing op het gebruikersaccount in Microsoft OneDrive.  Dit omvat het instellen van **Organisatiegegevens naar andere apps verzenden** op de waarde **Door beleid beheerde apps met delen van het besturingssysteem**.

3. De gebruiker bekijkt een werkbestand en probeert het te delen via Open-in voor door iOS beheerde apps.  

4. De gegevensoverdracht wordt voltooid en de gegevens worden nu beveiligd door **Open-in management** in de door iOS beheerde app.  De Intune-app is niet van toepassing op toepassingen die geen *door beleid beheerde apps* zijn.

*Delen vanuit een* door iOS beheerde app *naar een* door beleid beheerde app *met inkomende organisatiegegevens*

1. Een gebruiker opent systeemeigen e-mail op een geregistreerd iOS-apparaat met een beheerd e-mailprofiel.  

1. De gebruiker opent een werkdocumentbijlage vanuit systeemeigen e-mail in Microsoft Word.

1. Wanneer de app Word wordt gestart, gebeurt er het volgende:
   1. De gegevens worden in de volgende gevallen beveiligd door de Intune-app:
      - De gebruiker wordt aangemeld bij het werkaccount dat overeenkomt met de UPN van het account dat u hebt opgegeven in de configuratie-instellingen voor de app Microsoft Word. 
      - De door de beheerder geconfigureerde app-instellingen zijn van toepassing op het gebruikersaccount in Microsoft Word.  Dit omvat het instellen van **Gegevens ontvangen van andere apps** op de waarde **Alle apps met inkomende organisatiegegevens**.
      - De gegevensoverdracht wordt voltooid en het document wordt in de app getagd als werkdocument.  De gebruikersacties voor het document worden beveiligd met de Intune-app.
   1. De gegevens worden in de volgende gevallen **niet** beveiligd door de Intune-app:
      - De gebruiker wordt **niet** aangemeld bij zijn of haar werkaccount.
      - De door de beheerder geconfigureerde instellingen worden **niet** toegepast op Microsoft Word omdat de gebruiker niet is aangemeld.
      - De gegevensoverdracht wordt voltooid en het document wordt **niet** in de app getagd als werkdocument.  De Intune-app beveiligt **niet** de gebruikersacties voor het document omdat deze niet actief is.

    > [!NOTE]
    > De gebruiker kan het persoonlijke account toevoegen en gebruiken met Word. App-beveiligingsbeleid is niet van toepassing wanneer de gebruiker Word in een andere context dan werk gebruikt. 

### <a name="validate-user-upn-setting-for-third-party-emm"></a>UPN-gebruikersinstelling voor EMM van derden valideren

Na het configureren van de UPN-gebruikersinstelling valideert u de mogelijkheid van de iOS-app om te voldoen aan het beveiligingsbeleid voor apps van Intune en dit te ontvangen.

De beleidsinstelling **Require app PIN** (Een app-pincode vereisen ) is bijvoorbeeld eenvoudig te testen. Als de beleidsinstelling is ingesteld op **Require** (vereisen), ziet de gebruiker een prompt om een pincode in te voeren of in te stellen voordat er toegang tot bedrijfsgegevens kan worden verkregen.

[Maak allereerst een app-beveiligingsbeleid en wijs dit toe](app-protection-policies.md) aan de iOS-app. Zie [App-beveiligingsbeleid valideren](app-protection-policies-validate.md) voor meer informatie over het testen van beveiligingsbeleid voor apps.


## <a name="see-also"></a>Zie tevens
[Wat is een app-beveiligingsbeleid in Intune?](app-protection-policy.md)
