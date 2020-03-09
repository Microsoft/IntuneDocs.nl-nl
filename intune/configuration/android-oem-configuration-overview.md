---
title: OEMConfig gebruiken op Android Enterprise-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik Microsoft Intune om apparaten met Android Enterprise te beheren en te gebruiken met OEMConfig. Bekijk alle stappen, inclusief een overzicht, bekijk de vereisten, maak het configuratieprofiel in Intune en bekijk een lijst met ondersteunde OEMConfig-apps.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/02/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1bc811bcac80f8321284ece8d3860efc7164a270
ms.sourcegitcommit: a25f556aa9df4fcd9fdacccd12c9029bc6c5fe20
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2020
ms.locfileid: "78256319"
---
# <a name="use-and-manage-android-enterprise-devices-with-oemconfig-in-microsoft-intune"></a>Android Enterprise-apparaten met OEMConfig gebruiken en beheren in Microsoft Intune

In Microsoft Intune kunt u OEMConfig gebruiken om OEM-specifieke instellingen voor Android Enterprise-apparaten toe te voegen, te maken en te wijzigen. OEMConfig wordt doorgaans gebruikt om instellingen te configureren die niet zijn ingebouwd Intune. Andere OEM's (Original Equipment Manufacturers) bieden andere instellingen. De beschikbare instellingen zijn afhankelijk van wat de OEM in de OEMConfig-app opneemt.

Deze functie is van toepassing op:  

- Android Enterprise

In dit artikel wordt OEMConfig beschreven, worden de vereisten weergegeven, wordt aangegeven hoe u een configuratieprofiel maakt en worden de ondersteunde OEMConfig-apps in Intune weergegeven.

## <a name="overview"></a>Overzicht

OEMConfig-beleid is een speciaal type configuratiebeleid voor apparaten en is te vergelijken met [app-configuratiebeleid](../apps/app-configuration-policies-overview.md). OEMConfig is een standaard die is gedefinieerd door Google en gebruikmaakt van app-configuratie in Android om apparaatinstellingen te verzenden naar apps die zijn geschreven door OEM's (Original Equipment Manufacturers). Op basis van deze standaard kunnen OEM's en EMMs (Enterprise Mobility Management) op een gestandaardiseerde manier OEM-specifieke functies bouwen en ondersteunen. [Meer informatie over OEMConfig](https://blog.google/products/android-enterprise/oemconfig-supports-enterprise-device-features/).

EMM's, zoals Intune, bouwen handmatig ondersteuning in voor OEM-specifieke functies nadat deze door de OEM zijn geïntroduceerd. Deze aanpak leidt tot dubbele inspanningen en trage ingebruikname.

Met OEMConfig maakt een OEM een schema waarin OEM-specifieke beheerfuncties zijn gedefinieerd. De OEM sluit het schema in een app in en plaatst deze app vervolgens in Google Play. De EMM leest het schema van de app en maakt het schema beschikbaar in de EMM-beheerdersconsole. Via de console kunnen Intune-beheerders de instellingen in het schema configureren.

Wanneer de OEMConfig-app op een apparaat wordt geïnstalleerd, worden de instellingen die zijn geconfigureerd in de EMM-beheerdersconsole gebruikt om het apparaat te beheren. Apparaatinstellingen worden uitgevoerd door de OEMConfig-app in plaats van een MDM-agent die is gebouwd door de EMM.

Wanneer de OEM beheerfuncties toevoegt en verbetert, werkt de OEM ook de app bij in Google Play. Als beheerder beschikt u over deze nieuwe functies en updates (inclusief fixes) zonder dat u hoeft te wachten tot EMMs deze updates opnemen.

> [!TIP]
> U kunt OEMConfig alleen gebruiken met apparaten die deze functie ondersteunen en een bijbehorende OEMConfig-app hebben. Neem contact op met uw OEM voor specifieke informatie.

## <a name="before-you-begin"></a>Voordat u begint

Houd bij het gebruik van OEMConfig rekening met de volgende informatie:

- In Intune wordt het schema van de OEMConfig-app weergegeven, zodat u het kunt configureren. Het schema dat door de app wordt geleverd, wordt niet gevalideerd of gewijzigd door Intune. Als het schema onjuist is of onjuiste gegevens bevat, worden deze gegevens dus toch naar apparaten verzonden. Als u op een probleem stuit dat afkomstig is van het schema, neemt u contact op met de OEM voor hulp.
- De inhoud van het appschema wordt niet beïnvloed of beheerd door Intune. Intune heeft bijvoorbeeld geen controle over tekenreeksen, taal, toegestane acties enzovoort. Het is raadzaam contact op te nemen met de OEM voor meer informatie over het beheren van hun apparaten met OEMConfig.
- OEM's kunnen op elk gewenst moment hun ondersteunde functies en schema's bijwerken en een nieuwe app uploaden naar Google Play. Door Intune wordt altijd de nieuwste versie van de OEMConfig-app van Google Play gesynchroniseerd. Intune behoudt geen oudere versies van het schema of de app. Als u versieconflicten ondervindt, wordt u aangeraden contact op te nemen met de OEM voor meer informatie.
- Wijs één OEMConfig-profiel toe aan een apparaat. Als er meerdere profielen aan hetzelfde apparaat worden toegewezen, kan er inconsistent gedrag optreden. Het OEMConfig-model ondersteunt slechts één beleid per apparaat.

## <a name="prerequisites"></a>Vereisten

Zorg dat u aan de volgende vereisten voldoet als u OEMConfig op uw apparaten wilt gebruiken:

- Een Android Enterprise-apparaat dat is ingeschreven bij Intune.
- Een OEMConfig-app die is gebouwd door de OEM en is geüpload naar Google Play. Als deze zich niet in Google Play bevindt, neemt u contact op met de OEM voor meer informatie.
- De Intune-beheerder heeft machtigingen voor op rollen gebaseerde toegangsbeheer (RBAC) voor **Mobiele apps**, **Apparaatconfiguraties** en de machtiging 'lezen' onder **Android for Work**. Deze machtigingen zijn vereist omdat OEMConfig-profielen gebruikmaken van configuraties van beheerde apps om apparaatconfiguraties te beheren.

## <a name="prepare-the-oemconfig-app"></a>De OEMConfig-app voorbereiden

Zorg ervoor dat het apparaat OEMConfig ondersteunt, dat de juiste OEMConfig-app is toegevoegd aan Intune en dat de app op het apparaat is geïnstalleerd. Neem contact op met de OEM voor deze informatie.

> [!TIP] 
> OEMConfig-apps zijn specifiek voor de OEM. In een Sony OEMConfig-app die is geïnstalleerd op een Zebra Technologies-apparaat gebeurt er bijvoorbeeld niets.

1. Haal de OEMConfig-app op uit de Beheerde Google Play Store. De stappen worden beschreven in [Add Managed Google Play apps to Android enterprise devices](../apps/apps-add-android-for-work.md) (Beheerde Google Play-apps toevoegen aan Android Enterprise-apparaten).
2. Sommige OEM's kunnen apparaten verzenden waarop de OEMConfig-app vooraf is geïnstalleerd. Als de app niet vooraf is geïnstalleerd, gebruikt u Intune om [de app toe te voegen aan en te implementeren op apparaten](../apps/apps-deploy.md).

## <a name="create-an-oemconfig-profile"></a>Een OEMConfig-profiel maken

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Configuratieprofielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

    - **Platform**: Selecteer **Android Enterprise**.
    - **Profieltype**: Selecteer **OEMConfig**.

4. Selecteer **Maken**.
5. Voer in **Basisinformatie** de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het nieuwe profiel.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **OEMConfig-app**: Kies **Een OEMConfig-app selecteren**.

6. In **Gekoppelde app**selecteert u een bestaande OEMConfig-app die u eerder hebt toegevoegd > **Selecteren**. Zorg ervoor dat u de juiste OEMConfig-app kiest voor de apparaten waaraan u het beleid toewijst.

    Als er geen apps worden weergegeven, kunt u Beheerde Google Play instellen en apps uit de Beheerde Google Play Store ophalen. De stappen worden beschreven in [Beheerde Google Play-apps toevoegen aan Android Enterprise-apparaten](../apps/apps-add-android-for-work.md).

    > [!IMPORTANT]
    > Als u een OEMConfig-app hebt toegevoegd en deze hebt gesynchroniseerd met Google Play, maar deze niet wordt vermeld als een **Gekoppelde app**, moet u mogelijk contact opnemen met Intune om de app te onboarden. Zie [Een nieuwe app toevoegen](#supported-oemconfig-apps) (in dit artikel).

7. Selecteer **Volgende**.
8. Selecteer in **Instellingen configureren** de optie **Configuration Designer** of **JSON-editor**:

    > [!TIP]
    > Lees de OEM-documentatie om ervoor te zorgen dat u de eigenschappen juist configureert. Deze app-eigenschappen worden toegevoegd door de OEM, niet door Intune. Door Intune wordt een minimale validatie uitgevoerd van de eigenschappen of van wat u invoert. Als u bijvoorbeeld `abcd` opgeeft als een poortnummer, wordt het profiel zodanig opgeslagen en wordt het op uw apparaten geïmplementeerd met de waarden die u configureert. Zorg dat u de juiste informatie invoert.

    - **Configuratie-ontwerper**: Wanneer u deze optie selecteert, worden de eigenschappen die beschikbaar zijn in het appschema weergegeven zodat u deze kunt configureren.

      - Contextmenu's in Configuration Designer geven aan dat er meer opties beschikbaar zijn. Via het contextmenu kunt u bijvoorbeeld instellingen toevoegen, verwijderen en de volgorde ervan wijzigen. Deze opties worden toegevoegd door de OEM. Lees de documentatie over de OEM-app voor meer informatie over het gebruik van deze opties voor het maken van profielen.

      - Veel instellingen hebben standaardwaarden die zijn opgegeven door de OEM. Als u wilt zien of er een standaardwaarde is, wijst u het pictogram Info naast de instelling aan. Bij de Knopinfo vindt u de standaardwaarden voor die instelling (indien van toepassing) en meer informatie die door de OEM is verstrekt.

      - Als u op **Wissen** klikt, wordt een instelling uit het profiel verwijderd. Als een instelling zich niet in het profiel bevindt, wordt de waarde ervan op het apparaat niet gewijzigd wanneer het profiel wordt toegepast.

      - Als u in Configuration Designer een lege (niet-geconfigureerde) bundel maakt, wordt deze verwijderd wanneer u schakelt naar de JSON-editor.

    - **JSON-editor**: Wanneer u deze optie selecteert, wordt er een JSON-editor geopend met een sjabloon voor het volledige configuratieschema dat in de app is ingesloten. In de editor kunt u de sjabloon aanpassen met waarden voor de verschillende instellingen. Als u de **Configuration Designer** gebruikt om uw waarden te wijzigen, wordt de sjabloon in de JSON-editor overschreven met waarden van Configuration Designer.

      - Als u een bestaand profiel bijwerkt, worden in de JSON-editor de instellingen weergegeven die voor het laatst zijn opgeslagen voor het profiel.

      - OEMConfig-schema's kunnen groot en complex zijn. Als u deze instellingen liever met behulp van een andere editor wilt bijwerken, selecteert u de knop **JSON-sjabloon downloaden**. Gebruik een editor van uw keuze om uw configuratiewaarden toe te voegen aan de sjabloon. Kopieer en plak vervolgens uw bijgewerkte JSON in de eigenschap **JSON-editor**.

      - U kunt de JSON-editor gebruiken om een back-up van uw configuratie te maken. Nadat u uw instellingen hebt geconfigureerd, gebruikt u deze functie om de JSON-instellingen met uw waarden op te halen. Kopieer en plak de JSON in een bestand en sla het op. U hebt nu een back-upbestand.

    Wijzigingen die zijn aangebracht in configuratie Designer worden ook automatisch aangebracht in de JSON-editor. Net zo worden wijzigingen die in de JSON-editor zijn aangebracht, automatisch aangebracht in Configuration Designer. Als uw invoer ongeldige waarden bevat, kunt u pas schakelen tussen Configuration Designer en de JSON-editor als u de problemen hebt opgelost.

9. Selecteer **Volgende**.
10. Wijs in **Bereiktags** (optioneel) een tag toe om het profiel te filteren op specifieke IT-groepen, zoals `US-NC IT Team` of `JohnGlenn_ITDepartment`. Zie [RBAC en bereiktags gebruiken voor gedistribueerde IT](../fundamentals/scope-tags.md) voor meer informatie over bereiktags.

    Selecteer **Volgende**.

11. Selecteer in **Toewijzingen** de gebruikers of groepen die uw profiel zullen ontvangen. Wijs één profiel toe aan elk apparaat. Het OEMConfig-model ondersteunt slechts één beleid per apparaat.

    Zie [Gebruikers- en apparaatprofielen toewijzen](device-profile-assign.md) voor meer informatie over het toewijzen van profielen.

    Selecteer **Volgende**.

12. Controleer uw instellingen in **Beoordelen en maken**. Wanneer u **Maken**selecteert, worden uw wijzigingen opgeslagen en wordt het profiel toegewezen. Het beleid wordt ook weergegeven in de lijst met profielen.

De volgende keer dat het apparaat controleert op configuratie-updates, worden de OEM-specifieke instellingen die u hebt geconfigureerd, toegepast op de OEMConfig-app.

> [!NOTE]
> De OEMConfig-standaard bevat momenteel geen statusrapportage. Profielen hebben daarom standaard de status **In behandeling**.

## <a name="supported-oemconfig-apps"></a>Ondersteunde OEMConfig-apps

Vergeleken met standaard-apps bieden OEMConfig-apps meer bevoegdheden voor beheerde configuraties die door Google worden verleend om complexere schema's te ondersteunen. Intune ondersteunt momenteel de volgende OEMConfig-apps:

-----------------

| OEM | Bundel-id | OEM-documentatie (indien beschikbaar) |
| --- | --- | ---|
| Samsung | com.samsung.android.knox.kpu | [Beheerdershandleiding voor de KNOX-service-invoegtoepassing](https://docs.samsungknox.com/knox-service-plugin/admin-guide/index.htm) |
| Zebra Technologies | com.zebra.oemconfig.common | [Overzicht van OEMConfig van Zebra](http://techdocs.zebra.com/oemconfig ) |
| Datalogic | com.datalogic.oemconfig | [Gebruikersdocumentatie voor OEMConfig van Datalogic](https://datalogic.github.io/oemconfig/) |
| Honeywell | com.honeywell.oemconfig |  |
| Kyocera | jp.kyocera.enterprisedeviceconfig |  |
| Spectralink: streepjescodes | com.spectralink.barcode.service |  |
| Spectralink: knoppen | com.spectralink.buttons |  |
| Spectralink: apparaat | com.spectralink.slnkdevicesettings  |  |
| Spectralink: logboekregistratie | com.spectralink.slnklogger |  |
| Spectralink: VQO | com.spectralink.slnkvqo |  |
| Seuic | com.seuic.seuicoemconfig | |
| Unitech Electronics | com.unitech.oemconfig | |

-----------------

Als er een OEMConfig-toepassing voor uw apparaat bestaat, maar deze niet in de bovenstaande tabel staat of niet wordt weergegeven in de Intune-console, mailt u naar `IntuneOEMConfig@microsoft.com`.

> [!NOTE]
> OEMConfig-apps moeten door Intune worden onboarded voordat ze kunnen worden geconfigureerd met OEMConfig-profielen. Zodra een app wordt ondersteund, hoeft u geen contact op te nemen met Microsoft over het instellen ervan in uw tenant. U kunt gewoon de instructies op deze pagina volgen.
>
> Als u merkt dat een OEMConfig-app niet op de juiste manier werkt, kunt u contact opnemen met de ontwikkelaars van de OEMConfig-app. Het Intune-team is niet verantwoordelijk voor technische problemen met de afzonderlijke OEMConfig-apps.

## <a name="next-steps"></a>Volgende stappen

[De profielstatus bewaken](device-profile-monitor.md).
