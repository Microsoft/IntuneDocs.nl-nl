---
title: App-configuratiebeleidsregels toevoegen voor beheerde Android Enterprise-apparaten
titleSuffix: Microsoft Intune
description: Gebruik app-configuratiebeleidsregels in Microsoft Intune om instellingen te leveren wanneer gebruikers een beheerde Google Play-app uitvoeren.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 59d93bed7bae2b757a4bd1e7b1dffc814629f6a1
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71725735"
---
# <a name="add-app-configuration-policies-for-managed-android-enterprise-devices"></a>App-configuratiebeleidsregels toevoegen voor beheerde Android Enterprise-apparaten

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

App-configuratiebeleidsregels in Microsoft Intune leveren instellingen voor beheerde Google Play apps op beheerde Android Enterprise-apparaten. De app-ontwikkelaar maakt configuratie-instellingen voor door Android beheerde apps beschikbaar. Deze beschikbare instelling worden door Intune gebruikt om de beheerder functies voor de app te laten configureren. Het app-configuratiebeleid wordt toegewezen aan uw gebruikersgroepen. De beleidsinstellingen worden gebruikt wanneer de app deze controleert, doorgaans bij de eerste keer dat de app wordt uitgevoerd.

> [!NOTE]  
> Niet elke app ondersteunt app-configuratie. Vraag aan de app-ontwikkelaar of de app app-configuratiebeleidsregels ondersteunt.

1. Selecteer in [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) **Client-apps** > **App-configuratiebeleid** >  **Toevoegen**.
2. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het beleid. Geef uw beleid een naam zodat u het later eenvoudig kunt identificeren. Een goede beleidsnaam is bijvoorbeeld **Android Enterprise Nine Work-app-beleid voor het hele bedrijf**.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Type apparaatinschrijving**: Selecteer **Beheerde apparaten**.
    - **Platform**: Selecteer **Android**.

3. Selecteer **Gekoppelde app**. Kies de app waarvoor u een app-configuratiebeleid wilt definiëren. Selecteer in de lijst met beheerde Google Play-apps de apps die u hebt goedgekeurd en die zijn gesynchroniseerd met Intune.
4. Selecteer **Machtigingen**. U kunt configuraties instellen door gebruik te maken van:

    - [Configuration Designer](#use-the-configuration-designer)
    - [JSON-editor](#enter-the-json-editor)

5. Selecteer **OK** > **Toevoegen**.

## <a name="use-the-configuration-designer"></a>Configuration Designer gebruiken

U kunt Configuration Designer gebruiken voor beheerde Google Play-apps wanneer de app is ontworpen om configuratie-instellingen te ondersteunen. De configuratie is van toepassing op apparaten die zijn ingeschreven bij Intune. Met Configuration Designer kunt u specifieke configuratiewaarden configureren voor de instellingen die voor een app beschikbaar zijn.

1. Selecteer **Toevoegen**. Kies de lijst met configuratie-instellingen die u wilt invoeren voor de app.

    Als u GMail of Nine Work voor uw e-mail-app gebruikt, raadpleegt u [Android Enterprise-apparaatinstellingen voor het configureren van e-mail](../email-settings-android-enterprise.md) voor meer informatie over deze instellingen.

2. Stel voor elke sleutel en waarde in de configuratie het volgende in:

    - **Waardetype**: Het gegevenstype van de configuratiewaarde. Voor het waardetype Tekenreeks kunt u een variabel profiel of een certificaatprofiel als waardetype kiezen (optioneel).
    - **Configuratiewaarde**: De waarde voor de configuratie. Als u Variabele of Certificaat als **waardetype** selecteert, kunt u kiezen uit een lijst met variabelen of certificaatprofielen. Als u een certificaat kiest, wordt de alias van het certificaat dat is geïmplementeerd op het apparaat tijdens runtime ingevuld.

### <a name="supported-variables-for-configuration-values"></a>Ondersteunde variabelen voor configuratiewaarden

U kunt de volgende opties kiezen als u Variabele als het waardetype kiest:

| Optie | Voorbeeld |
|----|----|
| Mail | john@contoso.com |
| User Principal Name | john@contoso.com |
| Partial UPN | jan |
| Domein | contoso.com |
| Gebruikersnaam | Jan de Vries |
| Account-id | fc0dc142-71d8-4b12-bbea-bae2a8514c81 |
| Gebruikers-id | 3ec2c00f-b125-4519-acf0-302ac3761822 |
| Apparaat-id | b9841cd9-9843-405f-be28-b2265c59ef97 |

### <a name="allow-only-configured-organization-accounts-in-multi-identity-apps"></a>Alleen geconfigureerde organisatieaccounts toestaan in apps met meerdere identiteiten 

Gebruik voor Android-apparaten de volgende sleutel-/waardeparen:

| **Sleutel** | com.microsoft.intune.mam.AllowedAccountUPNs |
|---|---|
| **Waarden** | <ul><li>Een of meer door <code>;</code> gescheiden UPN’s.</li><li>Alleen beheerde gebruikersaccounts die met deze sleutel zijn gedefinieerd, zijn toegestaan.</li><li> Voor apparaten die zijn ingeschreven bij Intune, kan het <code>{{userprincipalname}}</code>-token worden gebruikt voor het ingeschreven gebruikersaccount.</li></ul> |

   > [!NOTE]
   > U moet Outlook voor Android 2.2.222 of hoger gebruiken wanneer u alleen geconfigureerde organisatieaccounts met meerdere identiteiten toestaat.<p></p>
   > Als Microsoft Intune-beheerder kunt u bepalen welke gebruikersaccounts worden toegevoegd aan Microsoft Office-toepassingen op beheerde apparaten. U kunt de toegang beperken tot uitsluitend toegestane gebruikersaccounts van de organisatie, en persoonlijke accounts blokkeren op ingeschreven apparaten. De app-configuratie wordt verwerkt op de ondersteunende toepassingen, en niet-goedgekeurde accounts worden verwijderd en geblokkeerd.<p></p>
   > Voor Microsoft Word, Microsoft Excel en Microsoft PowerPoint moet u app-versie 16.0.9327.1000 of hoger gebruiken. 

## <a name="enter-the-json-editor"></a>De JSON-editor invoeren

Bepaalde configuratie-instellingen voor apps (zoals apps met bundeltypen) kunnen niet worden geconfigureerd met Configuration Designer. Gebruik de JSON-editor voor deze waarden. Instellingen worden automatisch aan apps geleverd wanneer de app wordt geïnstalleerd.

1. Voor **Indeling configuratie-instellingen** selecteert u **JSON-editor invoeren**.
2. U kunt in de editor JSON-waarden definiëren voor configuratie-instellingen. U kunt **JSON-sjabloon downloaden** kiezen om een voorbeeldbestand te downloaden dat u vervolgens kunt configureren.
3. Kies **OK** en kies vervolgens **Toevoegen**.

Het beleid wordt gemaakt en in de lijst weergegeven.

Wanneer de toegewezen app op een apparaat wordt uitgevoerd, worden de instellingen uitgevoerd die u in het configuratiebeleid voor de app hebt geconfigureerd.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>De status van de machtigingen voor apps vooraf configureren

U kunt machtigingen voor apps ook vooraf configureren voor toegang tot Android-apparaatfuncties. Android-apps die apparaatmachtigingen vereisen, zoals voor toegang tot uw locatie of de apparaatcamera, vragen gebruikers de machtiging te accepteren of te weigeren.

Een app maakt bijvoorbeeld gebruik van de microfoon van het apparaat. De gebruiker wordt gevraagd de app toestemming te verlenen voor het gebruik van de microfoon.

1. Selecteer in [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) **Client-apps** > **App-configuratiebeleid** >  **Toevoegen**.
2. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het beleid. Geef uw beleid een naam zodat u het later eenvoudig kunt identificeren. Een goede beleidsnaam is bijvoorbeeld **Android Enterprise-toestemmingsprompt-app-beleid voor het hele bedrijf**.
    - **Beschrijving**. Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Type apparaatinschrijving**: Selecteer **Beheerde apparaten**.
    - **Platform**: Selecteer **Android**.

3. Selecteer **Gekoppelde app**. Kies de app waarvoor u een configuratiebeleid wilt definiëren. Selecteer in de lijst met Android-werkprofiel-apps de apps die u hebt goedgekeurd en die zijn gesynchroniseerd met Intune.
4. Selecteer **Machtigingen** > **Toevoegen**. Selecteer in de lijst de beschikbare app-machtigingen > **OK**.
5. Selecteer een optie voor elke machtiging die aan dit beleid moet worden verleend:
    - **Vragen**. De gebruiker vragen om de machtiging te accepteren of te weigeren.
    - **Automatisch verlenen**. Automatisch goedkeuren zonder de gebruiker hiervan op de hoogte te stellen.
    - **Automatisch weigeren**. Automatisch weigeren zonder de gebruiker hiervan op de hoogte te stellen.
6. Als u het configuratiebeleid voor apps wilt toewijzen, selecteert u het beleid > **Toewijzing** > **Groepen selecteren**. Kies de gebruikersgroepen die u wilt toewijzen > **Selecteren**.
7. Kies **Opslaan** om het beleid toe te wijzen.

## <a name="additional-information"></a>Aanvullende informatie

- [Een beheerde Google Play-app toewijzen aan Android Enterprise-apparaten](apps-add-android-for-work.md#assigning-a-managed-google-play-app-to-android-enterprise-work-profile-devices)
- [Configuratie-instellingen voor de Outlook-app voor iOS en Android implementeren](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune)

## <a name="next-steps"></a>Volgende stappen

Ga verder met het [toewijzen](apps-deploy.md) en [controleren](apps-monitor.md) van de app.
