---
title: Microsoft Intune-beleid voor het toestaan/blokkeren van apps voor Samsung Knox
titleSuffix: ''
description: Een aangepast profiel maken om apps toe te staan of te blokkeren voor Samsung Knox Standard-apparaten.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4b83a0339d87375502159467af323fceae5eb6e2
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207074"
---
# <a name="use-custom-policies-in-microsoft-intune-to-allow-and-block-apps-for-samsung-knox-standard-devices"></a>Aangepast beleid gebruiken in Microsoft Intune om apps toe te staan of te blokkeren voor Samsung Knox Standard-apparaten 

Gebruik de procedures in dit artikel om een aangepast Microsoft Intune-beleid op te stellen voor het maken van een van de volgende lijsten:

- Een lijst met apps die niet kunnen worden uitgevoerd op het apparaat. Apps in deze lijst worden geblokkeerd, wat betekent dat ze niet worden uitgevoerd, ook niet al ze al waren geïnstalleerd toen het beleid werd toegepast.
- Een lijst met apps die gebruikers van het apparaat kunnen installeren uit de Google Play Store. Alleen de apps die u in de lijst opneemt, kunnen worden geïnstalleerd. Geen andere apps kunnen worden geïnstalleerd uit de Store.

Deze instellingen kunnen alleen worden gebruikt door apparaten met Samsung Knox Standard.

## <a name="create-an-allowed-or-blocked-app-list"></a>En lijst met toegestane of geblokkeerde apps maken

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Configuratieprofielen** > **Profiel maken**.
3. Voer de volgende instellingen in:

    - **Naam**: Voer een beschrijvende naam in voor het profiel. Geef uw profielen een naam zodat u ze later eenvoudig kunt identificeren. Een goede profiel naam is bijvoorbeeld een **aangepast Windows Phone-profiel**.
    - **Beschrijving**: Voer een beschrijving in met een overzicht van de instelling en eventuele andere belangrijke details.
    - **Platform**: Selecteer **Android**.
    - **Profiel type**: Selecteer **aangepast**.

4. Selecteer in **Aangepaste OMA-URI-instellingen** de optie **Toevoegen**. Voer de volgende instellingen in:

    Voor een lijst met apps die worden geblokkeerd voor uitvoering op het apparaat:

    - **Naam**: Voer **PreventStartPackages** in.
    - **Beschrijving**: Geef een beschrijving op met een overzicht van de instelling en overige relevante informatie, zodat u het profiel beter kunt vinden. Voer bijvoorbeeld een **lijst in met apps die niet kunnen worden uitgevoerd**.
    - **OMA-URI** (hoofdlettergevoelig): Voer **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages** in.
    - **Gegevens type**: Selecteer **teken reeks**.
    - **Waarde**: Voer een lijst in van de app-pakketnamen die u wilt toestaan. U kunt `;`, `:` of `|` gebruiken als scheidingsteken. Voer bijvoorbeeld `package1;package2;` in.

   Voor een lijst met apps die gebruikers mogen installeren vanuit de Google Play Store, terwijl alle andere apps worden uitgesloten:

    - **Naam**: Voer **AllowInstallPackages** in.
    - **Beschrijving**: Voer een beschrijving in met een overzicht van de instelling en overige relevante informatie zodat u het profiel beter kunt vinden. Voer bijvoorbeeld een **lijst in met apps die gebruikers kunnen installeren vanaf Google Play**.
    - **OMA-URI** (hoofdlettergevoelig): Voer **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages** in.
    - **Gegevens type**: Selecteer **teken reeks**.
    - **Waarde**: Voer een lijst in van de app-pakketnamen die u wilt toestaan. U kunt `;`, `:` of `|` gebruiken als scheidingsteken. Voer bijvoorbeeld `package1;package2;` in.

5. Selecteer **OK** om uw wijzigingen op te slaan.
6. Wanneer u klaar bent, selecteert u **OK** > **Maken** om het Intune-profiel te maken. Wanneer het profiel is gemaakt, wordt dit weergegeven in de lijst **Apparaten - Configuratieprofielen**.

>[!TIP]
> U kunt de pakket-id van een app vinden door te bladeren naar de app in de Google Play-store. De pakket-id is opgenomen in de URL van de pagina van de app. De pakket-id van de Microsoft Word-app is bijvoorbeeld **com.microsoft.office.word**.

De volgende keer dat een doelapparaat incheckt, worden de appinstellingen toegepast.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens kunt u [het profiel toewijzen](../device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
