---
title: App-configuratiebeleidsregels toevoegen voor beheerde Android Enterprise-apparaten
titleSuffix: Microsoft Intune
description: Gebruik app-configuratiebeleidsregels in Microsoft Intune om instellingen te leveren wanneer gebruikers een beheerde Google Play-app uitvoeren.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b30da567d1a25028c51cf8268eab9613a7c3b8af
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755452"
---
# <a name="add-app-configuration-policies-for-managed-android-enterprise-devices"></a>App-configuratiebeleidsregels toevoegen voor beheerde Android Enterprise-apparaten

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

App-configuratiebeleidsregels in Microsoft Intune leveren instellingen voor beheerde Google Play apps op beheerde Android Enterprise-apparaten. De app-ontwikkelaar maakt configuratie-instellingen voor door Android beheerde apps beschikbaar. Deze beschikbare instelling worden door Intune gebruikt om de beheerder functies voor de app te laten configureren. Het app-configuratiebeleid wordt toegewezen aan uw gebruikersgroepen. De beleidsinstellingen worden gebruikt wanneer de app deze controleert, doorgaans bij de eerste keer dat de app wordt uitgevoerd.

> [!NOTE]  
> Niet elke app ondersteunt app-configuratie. Vraag aan de app-ontwikkelaar of app-configuratiebeleidsregels worden ondersteund in de app.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Kies de opties **Apps** > **App-configuratiebeleid** > **Toevoegen** > **Beheerde apparaten**. U kunt kiezen tussen **Beheerde apparaten** en **Beheerde apps**. Zie [Apps die app-configuratie ondersteunen](~/apps/app-configuration-policies-overview.md#apps-that-support-app-configuration) voor meer informatie.
3. Stel op de pagina **Basisinformatie** de volgende gegevens in:
    - **Naam**: de naam van het profiel zoals deze in Azure Portal wordt weergegeven.
    - **Beschrijving**: de beschrijving van het profiel dat wordt weergegeven in Azure Portal.
    - **Type apparaatinschrijving** - deze instelling is ingesteld op **Beheerde apparaten**.
4. Selecteer **Android Enterprise** als het **Platform**.
5. Klik op **App selecteren** naast **Beoogde app**. Het deelvenster **Gekoppelde app** wordt weergegeven. 
6. Kies in het deelvenster **Gekoppelde app** de beheerde app die u wilt koppelen aan het configuratiebeleid en klik op **OK**.
7. Klik op **Volgende** om de pagina **Instelling** weer te geven.
8. Klik op **Toevoegen** om het deelvenster **Machtigingen toevoegen** weer te geven.
9. Klik op de machtigingen die u wilt overschrijven. De verleende machtigingen overschrijven het beleid Standaardapp-machtigingen voor de geselecteerde apps.
10. Stel de **Machtigingsstatus** in voor elke machtiging. U kunt kiezen uit **Vragen**, **Automatisch verlenen** of **Automatisch weigeren**. Zie [Android Enterprise-instellingen om te markeren of apparaten wel of niet conform zijn met behulp van Intune](~/protect/compliance-policy-create-android-for-work.md) voor meer informatie over machtigingen.
11. Selecteer in de vervolgkeuzelijst de **Indeling van de configuratie-instellingen**. Selecteer een van de volgende methoden om configuratiegegevens toe te voegen:
    - **Configuration Designer gebruiken**
    - **JSON-gegevens invoeren**<br><br>
    Zie [Configuration Designer gebruiken](#use-the-configuration-designer) voor meer informatie over het gebruik van Configuration Designer. Zie [JSON-gegevens invoeren](#enter-json-data) voor meer informatie over het invoeren van XML-gegevens. 
12. Klik op **Volgende** om de pagina **Toewijzingen** weer te geven.
13. Selecteer in de vervolgkeuzelijst naast **Toewijzen aan** de optie **Geselecteerde groepen**, **Alle gebruikers**, **Alle apparaten** of **Alle gebruikers en alle apparaten** om het app-configuratiebeleid aan toe te wijzen.

    ![Schermafbeelding van Beleidstoewijzingen op het tabblad Opnemen](./media/app-configuration-policies-use-ios/app-config-policy01.png)

14. Selecteer **Alle gebruikers** in de vervolgkeuzelijst.

    ![Schermafbeelding van Beleidstoewijzingen met de vervolgkeuzemenu-optie Alle gebruikers](./media/app-configuration-policies-use-ios/app-config-policy02.png)

15. Klik op **Groepen voor uitsluiten selecteren** om het gerelateerde deelvenster weer te geven.

    ![Schermopname van Beleidstoewijzingen - het deelvenster Groepen selecteren die moeten worden uitgesloten](./media/app-configuration-policies-use-ios/app-config-policy03.png)

16. Kies de groepen die u wilt uitsluiten en klik vervolgens op **Selecteren**.

    >[!NOTE]
    >Wanneer u een groep toevoegt en als er al een andere groep is opgenomen voor een gegeven toewijzingstype, wordt deze groep vooraf geselecteerd. Dit kan niet worden gewijzigd voor andere toewijzingstypen voor opnemen. De groep die is gebruikt, kan daarom niet als een uitgesloten groep worden gebruikt.

17. Klik op **Volgende** om naar de pagina **Controleren en maken** weer te geven.
18. Klik op **Maken** om het configuratiebeleid toe te voegen aan Intune.

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
| AAD-apparaat-id | dc0dc142-11d8-4b12-bfea-cae2a8514c82 |
| Account-id | fc0dc142-71d8-4b12-bbea-bae2a8514c81 |
| Intune-apparaat-id | b9841cd9-9843-405f-be28-b2265c59ef97 |
| Domein | contoso.com |
| Mail | john@contoso.com |
| Partial UPN | jan |
| Gebruikers-id | 3ec2c00f-b125-4519-acf0-302ac3761822 |
| Gebruikersnaam | Jan de Vries |
| User Principal Name | john@contoso.com |


### <a name="allow-only-configured-organization-accounts-in-multi-identity-apps"></a>Alleen geconfigureerde organisatieaccounts toestaan in apps met meerdere identiteiten 

Gebruik voor Android-apparaten de volgende sleutel-/waardeparen:

| **Sleutel** | com.microsoft.intune.mam.AllowedAccountUPNs |
|---|---|
| **Waarden** | <ul><li>Een of meer door <code>;</code> gescheiden UPN’s.</li><li>Alleen beheerde gebruikersaccounts die met deze sleutel zijn gedefinieerd, zijn toegestaan.</li><li> Voor apparaten die zijn ingeschreven bij Intune, kan het <code>{{userprincipalname}}</code>-token worden gebruikt voor het ingeschreven gebruikersaccount.</li></ul> |

   > [!NOTE]
   > U moet Outlook voor Android 2.2.222 en hoger, Word, Excel, PowerPoint voor Android 16.0.9327.1000 en hoger, of OneDrive voor Android 5.28 en hoger gebruiken, wanneer alleen organisatieaccounts met meerdere identiteiten zijn toegestaan.<p></p>
   > Als Microsoft Intune-beheerder kunt u bepalen welke gebruikersaccounts worden toegevoegd aan Microsoft Office-toepassingen op beheerde apparaten. U kunt de toegang beperken tot uitsluitend toegestane gebruikersaccounts van de organisatie, en persoonlijke accounts blokkeren op ingeschreven apparaten. De app-configuratie wordt verwerkt op de ondersteunende toepassingen, en niet-goedgekeurde accounts worden verwijderd en geblokkeerd.<p></p>

## <a name="enter-json-data"></a>JSON-gegevens invoeren

Bepaalde configuratie-instellingen voor apps (zoals apps met bundeltypen) kunnen niet worden geconfigureerd met Configuration Designer. Gebruik de JSON-editor voor deze waarden. Instellingen worden automatisch aan apps geleverd wanneer de app wordt geïnstalleerd.

1. Voor **Indeling configuratie-instellingen** selecteert u **JSON-editor invoeren**.
2. U kunt in de editor JSON-waarden definiëren voor configuratie-instellingen. U kunt **JSON-sjabloon downloaden** kiezen om een voorbeeldbestand te downloaden dat u vervolgens kunt configureren.
3. Kies **OK** en kies vervolgens **Toevoegen**.

Het beleid wordt gemaakt en in de lijst weergegeven.

Wanneer de toegewezen app op een apparaat wordt uitgevoerd, worden de instellingen uitgevoerd die u in het configuratiebeleid voor de app hebt geconfigureerd.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>De status van de machtigingen voor apps vooraf configureren

U kunt machtigingen voor apps ook vooraf configureren voor toegang tot Android-apparaatfuncties. Android-apps die apparaatmachtigingen vereisen, zoals voor toegang tot uw locatie of de camera van uw apparaat, vragen gebruikers de machtiging te accepteren of te weigeren.

Een app maakt bijvoorbeeld gebruik van de microfoon van het apparaat. De gebruiker wordt gevraagd de app toestemming te verlenen voor het gebruik van de microfoon.

1. Selecteer in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de optie **Apps** > **App-configuratiebeleid** >  **Toevoegen** > **Beheerde apparaten**.
2. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het beleid. Geef uw beleid een naam zodat u het later eenvoudig kunt identificeren. Een goede beleidsnaam is bijvoorbeeld **Android Enterprise-toestemmingsprompt-app-beleid voor het hele bedrijf**.
    - **Beschrijving**. Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Type apparaatinschrijving**: Deze instelling is ingesteld op **Beheerde apparaten**.
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
