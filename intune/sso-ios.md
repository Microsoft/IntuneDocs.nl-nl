---
title: Intune configureren voor eenmalige aanmelding vanaf iOS-apparaten
titlesuffix: Azure portal
description: Meer informatie over het configureren van Intune voor eenmalige aanmelding vanaf iOS-apparaten."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 12/7/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 07ac355232c1e4ac290c87191d3764e3df45327e
ms.sourcegitcommit: 4509039cbfd4d450324a3475fb5841906720baa1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2018
---
# <a name="configure-intune-for-ios-device-single-sign-on"></a>Intune configureren voor eenmalige aanmelding vanaf iOS-apparaten

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

De meeste LOB-apps (Line-Of-Business) vereisen een zekere mate van gebruikersverificatie om beveiliging te ondersteunen. In veel gevallen moet de gebruiker daarom meerdere keren dezelfde referenties typen wat als vervelend kan worden ervaren. Ter verbetering van de gebruikerservaring kunnen ontwikkelaars apps maken die gebruikmaken van eenmalige aanmelding, waardoor een gebruiker minder vaak referenties hoeft te typen.

Om eenmalige aanmelding voor iOS-apparaten te kunnen gebruiken moet aan de volgende voorwaarden worden voldaan:

- Een app die is gecodeerd om te zoeken naar de gebruikersreferentieopslagplaats in de ene nettolading voor eenmalige aanmelding op het iOS-apparaat.
- Intune geconfigureerd voor eenmalige aanmelding vanaf iOS-apparaten.

## <a name="to-configure-intune-for-ios-device-single-sign-on"></a>Intune configureren voor eenmalige aanmelding vanaf iOS-apparaten


1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies op de blade **Intune** de optie **Apparaatconfiguratie**.
2. Kies op de blade **Apparaatconfiguratie** de optie **Profielen**.
3. Kies op de blade voor profielen de optie **Profiel maken**, geef een naam en beschrijving op en configureer de volgende instellingen:
   - **Platform**: kies **iOS**. 
   - **Profieltype**: kies **Apparaatfuncties**.
4. Kies op de blade **Apparaatfuncties** de optie **Eenmalige aanmelding**.

   ![Blade Eenmalige aanmelding](./media/sso-blade.png)

2. Gebruik de volgende samenvattingstabel om de velden op de blade **Eenmalige aanmelding** in te vullen. Zie de secties na de tabel voor meer informatie.
   
   |Veld  |Opmerkingen|
   |---------|---------|
   |**Het kenmerk Gebruikersnaam van AAD**|Het kenmerk dat door Intune wordt gecontroleerd voor elke gebruiker in AAD en waarmee het betreffende veld (zoals UPN) wordt ingevuld vóór het genereren van de XML-nettolading die op het apparaat wordt geïnstalleerd.|
   |**Realm**|Het domeingedeelte van de URL.|
   |**URL-voorvoegsels die gebruikmaken van eenmalige aanmelding**|Alle URL's in uw organisatie die gebruikersverificatie met eenmalige aanmelding vereisen|
   |**Apps die gebruikmaken van eenmalige aanmelding**|Apps op apparaten van eindgebruikers die gebruikmaken van de nettolading voor eenmalige aanmelding.|
   |**Referentievernieuwingscertificaat**|Als u certificaten voor verificatie gebruikt, selecteert u het SCEP- of PFX-certificaat dat voor de gebruiker als verificatiecertificaat is geïmplementeerd.|

In de volgende secties vindt u meer informatie over deze velden voor eenmalige aanmelding.

### <a name="username-attribute-from-aad-and-realm"></a>Het kenmerk Gebruikersnaam van AAD en Realm

- Als **Principal-naam gebruiker** voor dit veld is geselecteerd, wordt deze op de volgende manier geparseerd:

   ![Kenmerk Gebruikersnaam](media/User-name-attribute.png)

   U kunt de realm ook overschrijven met de tekst die u typt in het tekstvak **Realm**.

   Contoso kan bijvoorbeeld verschillende subregio's hebben, zoals Europa, Azië en Noord-Amerika. Mogelijk wil het bedrijf dat hun gebruikers in Azië de nettolading voor eenmalige aanmelding gebruiken en vereist de app dat de UPN de indeling *username@asia.contoso.com* heeft. Als u in dat geval **Principal-naam gebruiker** selecteert, is de realm voor elke gebruiker, die standaard afkomstig is van AAD, misschien gewoon *contoso.com*. Daarom kunt u speciaal voor gebruikers in Azië deze nettolading maken en de realm overschrijven met de waarde *asia.contoso.com*. De UPN van de eindgebruiker is nu *username@asia.contoso.com* en niet *username@contoso.com*.

- Als u **Apparaat-id** selecteert, selecteert Intune automatisch de Intune apparaat-id.

   Apps hoeven standaard alleen de apparaat-id te gebruiken. Maar als uw app gebruikmaakt van de realm naast de apparaat-id, kunt u de realm in het tekstvak **Realm** typen.

   > [!NOTE]
   > Houd de realm standaard leeg als u de apparaat-id gebruikt.

### <a name="url-prefixes-that-will-use-single-sign-on"></a>URL-voorvoegsels die gebruikmaken van eenmalige aanmelding

Typ hier alle URL's in uw organisatie die gebruikersverificatie vereisen.

Bijvoorbeeld: wanneer een gebruiker verbinding maakt met een van deze sites, gebruikt het iOS-apparaat de referenties voor eenmalige aanmelding en hoeft de gebruiker geen aanvullende referenties in te voeren. Als u echter meervoudige verificatie hebt ingeschakeld, moeten gebruikers de tweede verificatie invoeren.

> [!NOTE]
> Deze URL's moeten de juiste FQDN-indeling hebben. Apple vereist dat deze de volgende indeling hebben: `http://<yourURL.domain>`

De URL-vergelijkingspatronen moeten beginnen met `http://` of `https://`. Er wordt een eenvoudige vergelijking van de tekenreeksen uitgevoerd. Het URL-voorvoegsel `http://www.contoso.com/` komt dus niet overeen met `http://www.contoso.com:80/`. Bij iOS 9.0 of hoger kan echter één jokerteken * worden gebruikt om alle overeenkomende waarden op te geven. Bijvoorbeeld: `http://*.contoso.com/` komt overeen met zowel `http://store.contoso.com/` als `http://www.contoso.com`.
De patronen `http://.com` en `https://.com` komen overeen met respectievelijk alle HTTP- en HTTPS-URL's.

### <a name="apps-that-will-use-single-sign-on"></a>Apps die gebruikmaken van eenmalige aanmelding

Geef aan welke apps op apparaten van eindgebruikers gebruik kunnen maken van de nettolading voor eenmalige aanmelding.

De matrix `AppIdentifierMatches` moet tekenreeksen bevatten die overeenkomen met de app-bundel-id's. Deze tekenreeksen kunnen exacte overeenkomsten zijn (bijvoorbeeld: `com.contoso.myapp`) of er kan hiermee een overeenkomend voorvoegsel voor de bundel-id worden opgegeven door het jokerteken *\ te gebruiken. Het jokerteken moet worden weergegeven na een punt (.) en kan slechts één keer worden weergegeven aan het einde van de tekenreeks (bijvoorbeeld: `com.contoso.*`). Wanneer een jokerteken wordt opgenomen, krijgt elke app waarvan de bundel-id begint met het voorvoegsel toegang tot het account.

Het veld **App-naam** wordt gebruikt voor het toevoegen van een gebruiksvriendelijke naam om u te helpen de bundel-id te identificeren.

### <a name="credential-renewal-certificate"></a>Referentievernieuwingscertificaat

Als u uw eindgebruikers met certificaten (dus niet met wachtwoorden) verifieert, gebruikt u dit veld om het SCEP- of PFX-certificaat te selecteren dat voor de gebruiker als verificatiecertificaat is geïmplementeerd. Dit is meestal hetzelfde certificaat dat voor de gebruiker is geïmplementeerd voor andere profielen, zoals VPN, Wi-Fi of E-mail.

## <a name="next-steps"></a>Volgende stappen

Zie [Instellingen voor apparaatfuncties configureren in Microsoft Intune](device-features-configure.md) voor aanvullende informatie over de configuratie van apparaatfuncties.
