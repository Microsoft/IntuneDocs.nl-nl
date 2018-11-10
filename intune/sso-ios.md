---
title: Eenmalige aanmelding toevoegen voor iOS-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: U kunt in Microsoft Intune iOS-apparaten maken, configureren, toestaan of inschakelen, zodat deze eenmalige aanmelding (SSO) kunnen gebruiken in plaats van een wachtwoord voor verificatie voor de resources en de gegevens van uw organisatie. Als u eenmalige aanmelding wilt gebruiken, maakt u een apparaatconfiguratieprofiel en voert u de UPN, apparaat-id, uw apps en een certificaat in om de gebruiker en het apparaat te verifiëren.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d1add113222c2aa7eaea10679c329e877b1a136f
ms.sourcegitcommit: 437eaf364c3b8a38d294397310c770ea4d8a8015
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2018
ms.locfileid: "49992006"
---
# <a name="use-single-sign-on-ios-device-in-microsoft-intune"></a>Eenmalige aanmelding gebruiken voor iOS-apparaten in Microsoft Intune

De meeste LOB-apps (Line-Of-Business) vereisen een zekere mate van gebruikersverificatie om beveiliging te ondersteunen. In veel gevallen moet de gebruiker bij deze verificatie meerdere keren dezelfde referenties invoeren wat vervelend is voor de gebruiker. Ter verbetering van de gebruikerservaring kunnen ontwikkelaars apps maken die gebruikmaken van eenmalige aanmelding (SSO), waardoor een gebruiker minder vaak referenties hoeft in te voeren.

In dit artikel wordt beschreven hoe u eenmalige aanmelding voor iOS-apparaten inschakelt met een apparaatconfiguratieprofiel in Microsoft Intune.

## <a name="before-you-begin"></a>Voordat u begint

Zorg ervoor dat u een app gebruikt die is gecodeerd om naar de gebruikersreferentieopslagplaats te zoeken in de payload voor eenmalige aanmelding op het iOS-apparaat.

## <a name="create-the-sso-profile"></a>Het SSO-profiel maken

1. Selecteer in [Azure Portal](https://portal.azure.com) **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
2. Kies **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende instellingen in:

    - **Naam**: voer een naam in voor het profiel, zoals `ios sso profile`.
    - **Beschrijving**: voer een beschrijving in met sleutelwoorden zodat u het profiel in de lijst kunt vinden.
    - **Platform**: kies **iOS**.
    - **Profieltype**: kies **Apparaatfuncties**.

4. Kies **Eenmalige aanmelding**.

    ![Deelvenster Eenmalige aanmelding](./media/sso-blade.png)

5. Voer de volgende instellingen in: 

    - **Het kenmerk Gebruikersnaam in AAD**: Intune zoekt naar dit kenmerk voor elke gebruiker in Azure AD. Het betreffende veld (zoals UPN) wordt vervolgens door Intune ingevuld vóór het genereren van de XML-payload die op het apparaat wordt geïnstalleerd. Uw opties zijn:
    
        - **User Principal Name**: de UPN wordt op de volgende manier geparseerd:

            ![Kenmerk Gebruikersnaam](media/User-name-attribute.png)

            U kunt de realm ook overschrijven met de tekst die u in het tekstvak **Realm** invoert.

            Contoso kan bijvoorbeeld verschillende subregio's hebben, zoals Europa, Azië en Noord-Amerika. Mogelijk wil het bedrijf dat hun gebruikers in Azië de SSO-payload gebruiken en is voor de app vereist dat de UPN de notatie `username@asia.contoso.com` heeft. Als u in dat geval **User Principal Name** selecteert, wordt de realm voor elke gebruiker standaard uit Azure AD overgenomen, bijvoorbeeld *contoso.com*. Daarom kunt u speciaal voor gebruikers in Azië deze nettolading maken en de realm overschrijven met de waarde *asia.contoso.com*. De UPN van de eindgebruiker is nu username@asia.contoso.com in plaats van username@contoso.com.

        - **Apparaat-id voor Intune**: de apparaat-id voor Intune wordt automatisch door Intune geselecteerd. 

            Apps hoeven standaard alleen de apparaat-id te gebruiken. Als uw app echter gebruikmaakt van de realm *en* de apparaat-id, kunt u de realm in het tekstvak **Realm** invoeren.

            > [!NOTE]
            > Houd de realm standaard leeg als u de apparaat-id gebruikt.

    - **Realm**: het domeingedeelte van de URL.
    
    - **URL-voorvoegsels die gebruikmaken van eenmalige aanmelding**: **voeg** URL's in uw organisatie toe waarvoor gebruikersverificatie met eenmalige aanmelding vereist is. 

        Bijvoorbeeld: wanneer een gebruiker verbinding maakt met een van deze sites, gebruikt het iOS-apparaat de referenties voor eenmalige aanmelding. De gebruiker hoeft geen aanvullende referenties in te voeren. Als u echter meervoudige verificatie hebt ingeschakeld, moeten gebruikers de tweede verificatie invoeren.

        > [!NOTE]
        > Deze URL's moeten de juiste FQDN-indeling hebben. Apple vereist dat de URL's de notatie `http://<yourURL.domain>` hebben.

        De URL-vergelijkingspatronen moeten beginnen met `http://` of `https://`. Er wordt een eenvoudige vergelijking van de tekenreeksen uitgevoerd. Het URL-voorvoegsel `http://www.contoso.com/` komt dus niet overeen met `http://www.contoso.com:80/`. Bij iOS 10.0 of hoger kan echter het jokerteken \* worden gebruikt om alle overeenkomende waarden in te voeren. Bijvoorbeeld: `http://*.contoso.com/` komt overeen met zowel `http://store.contoso.com/` als `http://www.contoso.com`.

        De patronen `http://.com` en `https://.com` komen overeen met respectievelijk alle HTTP- en HTTPS-URL's.
    
    - **Apps die gebruikmaken van eenmalige aanmelding**: **voeg** apps toe op apparaten van eindgebruikers die gebruik kunnen maken van eenmalige aanmelding. 

        De matrix `AppIdentifierMatches` moet tekenreeksen bevatten die overeenkomen met de app-bundel-id's. Deze tekenreeksen kunnen exacte overeenkomsten zijn (bijvoorbeeld: `com.contoso.myapp`) of u kunt identieke begintekens voor de bundel-id invoeren met het jokerteken \*. Het jokerteken moet worden weergegeven na een punt (.) en kan slechts één keer worden weergegeven aan het einde van de tekenreeks (bijvoorbeeld: `com.contoso.*`). Wanneer een jokerteken wordt opgenomen, krijgt elke app waarvan de bundel-id begint met het voorvoegsel toegang tot het account.

        Gebruik **App-naam** om een gebruiksvriendelijke naam in te voeren waarmee u de bundel-id kunt aangeven.
    
    - **Certificaat voor het vernieuwen van de referenties**: als u certificaten voor verificatie (geen wachtwoorden) gebruikt, selecteert u het SCEP- of PFX-certificaat dat voor de gebruiker als verificatiecertificaat is geïmplementeerd. Dit is meestal hetzelfde certificaat dat voor de gebruiker is geïmplementeerd voor andere profielen, bijvoorbeeld voor VPN, Wi-Fi of e-mail.

6. Selecteer **OK** > **OK** > **Maken** om de wijzigingen op te slaan en maak het profiel. Wanneer het profiel is gemaakt, wordt het weergegeven in de lijst **Apparaatconfiguratie: profielen**. 

## <a name="next-steps"></a>Volgende stappen

Zie [Instellingen voor apparaatfuncties configureren in Microsoft Intune](device-features-configure.md) voor aanvullende informatie over de configuratie van apparaatfuncties.

[Wijs dit profiel toe](device-profile-assign.md) aan uw iOS-apparaten.
