---
title: OEMConfig gebruiken op Android Enterprise-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik Microsoft Intune voor het beheren en gebruiken van apparaten met Android Enter prise met OEMConfig. Bekijk alle stappen, inclusief een overzicht, zie de vereisten, maak het configuratie profiel in intune en Bekijk een lijst met ondersteunde OEMConfig-apps.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/18/2019
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
ms.openlocfilehash: eb992747765ea087d5ef536c2da7c444bfa2d987
ms.sourcegitcommit: 4f979ba7030e72d820113fe23ac8521ddb2433bd
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/25/2019
ms.locfileid: "72915731"
---
# <a name="use-and-manage-android-enterprise-devices-with-oemconfig-in-microsoft-intune"></a>Android Enter prise-apparaten gebruiken en beheren met OEMConfig in Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

In Microsoft Intune kunt u OEMConfig gebruiken om OEM-specifieke instellingen voor Android Enter prise-apparaten toe te voegen, te maken en aan te passen. OEMConfig wordt doorgaans gebruikt voor het configureren van instellingen die niet zijn ingebouwd in intune. Andere OEM'S (Original Equipment Manufacturers) bevatten verschillende instellingen. De beschik bare instellingen zijn afhankelijk van wat de OEM in hun OEMConfig-app opneemt.

Deze functie is van toepassing op:  

- Android Enterprise

In dit artikel worden OEMConfig beschreven, worden de vereisten weer gegeven, ziet u hoe u een configuratie profiel maakt en een lijst met ondersteunde OEMConfig-apps in intune.

## <a name="overview"></a>Overzicht

OEMConfig-beleid is een speciaal type configuratie beleid voor apparaten, vergelijkbaar met het [app-configuratie beleid](../apps/app-configuration-policies-overview.md). OEMConfig is een standaard die is gedefinieerd door Google en die gebruikmaakt van app-configuratie in Android voor het verzenden van Apparaatinstellingen naar apps die zijn geschreven door Oem's (Original Equipment Manufacturers). Deze standaard staat Oem's en EMMs (Enter prise Mobility Management) toe om OEM-specifieke functies op een gestandaardiseerde manier te bouwen en te ondersteunen. Meer [informatie over OEMConfig](https://blog.google/products/android-enterprise/oemconfig-supports-enterprise-device-features/).

EMMs, zoals intune, hand matig ondersteuning bouwen voor OEM-specifieke functies nadat deze door de OEM zijn geïntroduceerd. Deze aanpak leidt tot dubbele inspanningen en een trage goed keuring.

Met OEMConfig maakt een OEM een schema dat OEM-specifieke beheer functies definieert. De OEM sluit het schema in een app in en zet deze app vervolgens op Google Play. De EMM leest het schema van de app en toont het schema in de EMM-beheerders console. Met de-console kunnen intune-beheerders de instellingen in het schema configureren.

Wanneer de OEMConfig-app op een apparaat wordt geïnstalleerd, worden de instellingen gebruikt die zijn geconfigureerd in de console van de EMM-beheerder om het apparaat te beheren. Instellingen op het apparaat worden uitgevoerd door de OEMConfig-app in plaats van een MDM-agent die is gebouwd door de EMM.

Wanneer de OEM beheer functies toevoegt en verbetert, werkt de OEM ook de app bij in Google Play. Als beheerder beschikt u over deze nieuwe functies en updates (inclusief oplossingen) zonder te hoeven wachten tot EMMs deze updates bevatten.

> [!TIP]
> U kunt OEMConfig alleen gebruiken met apparaten die deze functie ondersteunen en een bijbehorende OEMConfig-app hebben. Neem contact op met uw OEM voor specifieke informatie.

## <a name="before-you-begin"></a>Voordat u begint

Wanneer u OEMConfig gebruikt, moet u rekening houden met de volgende informatie:

- In intune wordt het schema van de OEMConfig-app weer gegeven, zodat u het kunt configureren. InTune valideert of wijzigt het schema dat wordt meegeleverd met de app niet. Dus als het schema onjuist is of onjuiste gegevens bevat, worden deze gegevens nog steeds naar apparaten verzonden. Als u een probleem vindt dat afkomstig is uit het schema, neemt u contact op met de OEM voor hulp.
- InTune heeft geen invloed op de inhoud van het app-schema of om deze te beheren. InTune heeft bijvoorbeeld geen controle over teken reeksen, taal, de toegestane acties, enzovoort. Het is raadzaam contact op te nemen met de OEM voor meer informatie en aanbevolen procedures voor het beheren van hun apparaten met OEMConfig.
- Oem's kunnen op elk gewenst moment hun ondersteunde functies en schema's bijwerken en een nieuwe app uploaden naar Google Play. InTune synchroniseert altijd de nieuwste versie van de OEMConfig-app van Google Play. InTune behoudt geen oudere versies van het schema of de app. Als u versie conflicten ondervindt, wordt u aangeraden contact op te nemen met de OEM voor meer informatie.
- Wijs één OEMConfig-profiel toe aan een apparaat. Als er meerdere profielen aan hetzelfde apparaat zijn toegewezen, ziet u mogelijk inconsistent gedrag. Het OEMConfig-model ondersteunt slechts één beleid per apparaat.

## <a name="prerequisites"></a>Vereisten

Als u OEMConfig op uw apparaten wilt gebruiken, zorg er dan voor dat u de volgende vereisten hebt:

- Een Android Enter prise-apparaat dat is inge schreven bij intune.
- Een OEMConfig-app die is gebouwd door de OEM en is geüpload naar Google Play. Als dit niet het geval is Google Play, neemt u contact op met de OEM voor meer informatie.
- De intune-beheerder heeft machtigingen voor op rollen gebaseerde toegangs beheer (RBAC) voor **mobiele apps**, **configuraties van apparaten**en de machtiging lezen onder **Android for work**. Deze machtigingen zijn vereist omdat OEMConfig-profielen beheerde app-configuraties gebruiken voor het beheren van de configuraties van apparaten.

## <a name="prepare-the-oemconfig-app"></a>De OEMConfig-app voorbereiden

Zorg ervoor dat het apparaat OEMConfig ondersteunt, de juiste OEMConfig-app wordt toegevoegd aan intune en de app op het apparaat is geïnstalleerd. Neem contact op met de OEM voor deze informatie.

> [!TIP] 
> OEMConfig-apps zijn specifiek voor de OEM. Zo kan een Sony OEMConfig-app die is geïnstalleerd op een Zebra-technologie apparaat niets doen.

1. Haal de OEMConfig-app op uit de beheerde Google Play Store. De stappen worden beschreven in [Add Managed Google Play apps to Android enterprise devices](../apps/apps-add-android-for-work.md) (Beheerde Google Play-apps toevoegen aan Android Enterprise-apparaten).
2. Sommige Oem's kunnen apparaten verzenden met de OEMConfig-app vooraf geïnstalleerd. Als de app niet vooraf is geïnstalleerd, gebruikt u intune om [de app toe te voegen aan en te implementeren op apparaten](../apps/apps-deploy.md).

## <a name="create-an-oemconfig-profile"></a>Een OEMConfig-profiel maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

    - **Naam**: voer een beschrijvende naam in voor het nieuwe profiel.
    - **Beschrijving:** voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: selecteer **Android-onderneming**.
    - **Profiel type**: Selecteer **OEMConfig**.

4. Selecteer **gekoppelde app**, selecteer een bestaande OEMConfig-app die u eerder > **OK**hebt toegevoegd. Zorg ervoor dat u de juiste OEMConfig-app kiest voor de apparaten waaraan u het beleid toewijst.

    Als er geen apps worden weer gegeven, kunt u beheerde Google Play instellen en apps uit de beheerde Google Play Store ophalen. De stappen worden beschreven in [Add Managed Google Play apps to Android enterprise devices](../apps/apps-add-android-for-work.md) (Beheerde Google Play-apps toevoegen aan Android Enterprise-apparaten).

    > [!IMPORTANT]
    > Als u een OEMConfig-app hebt toegevoegd en deze hebt gesynchroniseerd met Google Play, maar deze niet wordt vermeld als een **gekoppelde app**, moet u mogelijk contact opnemen met intune om de app uit te staan. Zie [een nieuwe app toevoegen](#supported-oemconfig-apps) (in dit artikel).

5. Kies in **instellingen configureren met**de optie **Configuration Designer** of **JSON editor**gebruiken:

    > [!TIP]
    > Lees de OEM-documentatie om te controleren of u de eigenschappen correct configureert. Deze app-eigenschappen zijn opgenomen in de OEM, niet in intune. InTune heeft een minimale validatie van de eigenschappen of wat u invoert. Als u bijvoorbeeld `abcd` opgeeft voor een poort nummer, wordt het profiel opgeslagen als-is en op uw apparaten geïmplementeerd met de waarden die u configureert. Zorg ervoor dat u de juiste informatie invoert.

    - **Configuration Designer**: wanneer u deze optie selecteert, worden de eigenschappen die beschikbaar zijn in het app-schema weer gegeven die u kunt configureren.

      - Context menu's in de Configuration Designer geven aan dat er meer opties beschikbaar zijn. In het context menu kunt u bijvoorbeeld instellingen toevoegen, verwijderen en de volg orde wijzigen. Deze opties zijn opgenomen in de OEM. Lees de documentatie van de OEM-app voor meer informatie over het gebruik van deze opties voor het maken van profielen.

      - Veel instellingen hebben standaard waarden die zijn opgegeven door de OEM. Als u wilt zien of er een standaard waarde is, houdt u de muis aanwijzer boven het info pictogram naast de instelling. In de knop info worden de standaard waarden voor die instelling (indien van toepassing) en meer details van de OEM weer gegeven.

      - Als u op **wissen** klikt, wordt een instelling uit het profiel verwijderd. Als een instelling zich niet in het profiel bevindt, wordt de waarde op het apparaat niet gewijzigd wanneer het profiel wordt toegepast.
        
      - Als u in de Configuration Designer een lege (niet-geconfigureerde) bundel maakt, wordt deze verwijderd wanneer u overschakelt naar de JSON-editor.

    - **JSON-editor**: wanneer u deze optie selecteert, wordt er een JSON-editor geopend met een sjabloon voor het volledige configuratie schema dat in de app is inge sloten. Pas in de editor de sjabloon aan met waarden voor de verschillende instellingen. Als u de **ontwerp functie voor configuratie** gebruikt om uw waarden te wijzigen, overschrijft de JSON-editor de sjabloon met waarden van de Configuration Designer.
    
      - Als u een bestaand profiel bijwerkt, toont de JSON-editor de instellingen die voor het laatst zijn opgeslagen bij het profiel.

      - OEMConfig-schema's kunnen groot en complex zijn. Als u deze instellingen liever met behulp van een andere editor wilt bijwerken, selecteert u de knop **JSON-sjabloon downloaden** . Gebruik een editor van uw keuze om uw configuratie waarden toe te voegen aan de sjabloon. Kopieer en plak vervolgens uw bijgewerkte JSON in naar de eigenschap **JSON-editor** .

      - U kunt de JSON-editor gebruiken om een back-up te maken van uw configuratie. Nadat u uw instellingen hebt geconfigureerd, gebruikt u deze functie om de JSON-instellingen op te halen met uw waarden. Kopieer en plak de JSON naar een bestand en sla het op. U hebt nu een back-upbestand.

    Wijzigingen die zijn aangebracht in de configuratie Designer, worden ook automatisch gemaakt in de JSON-editor. Op dezelfde manier worden wijzigingen die in de JSON-editor zijn aangebracht, automatisch aangebracht in de Configuration Designer. Als uw invoer ongeldige waarden bevat, kunt u niet scha kelen tussen de Configuration Designer en de JSON-editor totdat u de problemen hebt opgelost.

6. Selecteer **OK** > **Toevoegen** om uw wijzigingen op te slaan. Het beleid wordt gemaakt en in de lijst weergegeven.

Zorg ervoor dat u [het profiel toewijst](device-profile-assign.md) en [de status ervan controleert](device-profile-monitor.md).

 > [!NOTE]
 > Wijs één profiel toe aan elk apparaat. Het OEMConfig-model ondersteunt slechts één beleid per apparaat.

De volgende keer dat het apparaat controleert op configuratie-updates, worden de OEM-specifieke instellingen die u hebt geconfigureerd, toegepast op de OEMConfig-app.

> [!NOTE]
> De OEMConfig-standaard bevat momenteel geen status rapportage. Profielen tonen standaard de status **in behandeling** .

## <a name="supported-oemconfig-apps"></a>Ondersteunde OEMConfig-apps

Vergeleken met standaard-apps, OEMConfig-apps vouwen de bevoegdheden voor beheerde configuraties uit die door Google worden verleend ter ondersteuning van complexere schema's. InTune ondersteunt momenteel de volgende OEMConfig-apps:

-----------------

| OEM | Bundel-id | OEM-documentatie (indien beschikbaar) |
| --- | --- | ---|
| Samsung | com. Samsung. Android. Knox. KPU | [Beheerders handleiding voor de Knox-service-invoeg toepassing](https://docs.samsungknox.com/knox-service-plugin/admin-guide/welcome.htm) |
| Zebra Technologies | com. Zebra. oemconfig. common | [Overzicht van Zebra OEMConfig](http://techdocs.zebra.com/oemconfig ) |
| Datalogic | com. Datalogic. oemconfig | [Gebruikers documentatie voor Datalogic OEMConfig](https://datalogic.github.io/oemconfig/) |
| Honeywell | com. Honeywell. oemconfig |  |
| Kyocera | JP. Kyocera. enterprisedeviceconfig |  |

-----------------

Als er een OEMConfig-toepassing voor uw apparaat bestaat, maar dit niet in de bovenstaande tabel staat of niet wordt weer gegeven in de intune-console, kunt u het e-mail adres `IntuneOEMConfig@microsoft.com`.

> [!NOTE]
> OEMConfig-apps moeten aan de boord zijn van intune voordat ze kunnen worden geconfigureerd met OEMConfig-profielen. Zodra een app wordt ondersteund, hoeft u geen contact op te nemen met micro soft over het instellen van het programma in uw Tenant. Volg de instructies op deze pagina.

## <a name="next-steps"></a>Volgende stappen

- [Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
