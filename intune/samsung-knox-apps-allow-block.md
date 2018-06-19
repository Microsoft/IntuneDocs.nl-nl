---
title: Microsoft Intune-beleid voor het toestaan/blokkeren van apps voor Samsung Knox
titlesuffix: ''
description: Een aangepast profiel maken om apps toe te staan of te blokkeren voor Samsung Knox Standard-apparaten.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 28aab246778610691ee78c447fd08f2a923ec6c0
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31830847"
---
# <a name="use-custom-policies-in-microsoft-intune-to-allow-and-block-apps-for-samsung-knox-standard-devices"></a>Aangepast beleid gebruiken in Microsoft Intune om apps toe te staan of te blokkeren voor Samsung Knox Standard-apparaten 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Gebruik de procedures in dit artikel om een aangepast Microsoft Intune-beleid op te stellen voor het maken van een van de volgende lijsten:

- Een lijst met apps die niet kunnen worden uitgevoerd op het apparaat. Apps in deze lijst worden geblokkeerd, wat betekent dat ze niet worden uitgevoerd, ook niet al ze al waren geïnstalleerd toen het beleid werd toegepast.
- Een lijst met apps die gebruikers van het apparaat kunnen installeren uit de Google Play Store. Alleen de apps die u in de lijst opneemt, kunnen worden geïnstalleerd. Geen andere apps kunnen worden geïnstalleerd uit de Store.

Deze instellingen kunnen alleen worden gebruikt door apparaten met Samsung Knox Standard.

## <a name="create-an-allowed-or-blocked-app-list"></a>En lijst met toegestane of geblokkeerde apps maken

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Apparaatconfiguratie**.
2. Kies **Beheren** > **Profielen** in het deelvenster **Apparaatconfiguratie**.
2. Kies **Profiel maken** in het deelvenster met de profielenlijst.
3. Voer in het deelvenster **Profiel maken** een **naam** en desgewenst een **beschrijving** in voor dit apparaatprofiel.
2. Kies voor **Platformtype** de optie **Android** en kies voor het **Profieltype** de optie **Aangepast**.
3. Klik op **Instellingen**.
3. Kies **Toevoegen** in het deelvenster **Aangepaste OMA-URI-instellingen**.
4. Geef in het dialoogvenster **OMA-URI-instelling toevoegen of bewerken** de volgende instellingen op:

   Voor een lijst met apps die worden geblokkeerd voor uitvoering op het apparaat:

   - **Naam**: voer **PreventStartPackages** in.
   - **Beschrijving**: voer eventueel een beschrijving in, zoals 'Lijst met apps die zijn geblokkeerd'.
   -    **Gegevenstype**: kies **Tekenreeks** in de vervolgkeuzelijst.
   -    **OMA-URI**: voer **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages** in
   -    **Waarde**: voer een lijst in met de app-pakketnamen die u wilt toestaan. U kunt **; : ,** of **|** gebruiken als scheidingsteken. (Voorbeeld: pakket1; pakket2;)

   Voor een lijst met apps die gebruikers mogen installeren vanuit de Google Play Store, terwijl alle andere apps worden uitgesloten:
   - **Naam**: voer **AllowInstallPackages** in.
   - **Beschrijving**: voer eventueel een beschrijving in, zoals 'Lijst met apps die gebruikers kunnen installeren vanuit Google Play'.
   - **Gegevenstype**: kies **Tekenreeks** in de vervolgkeuzelijst.
   - **OMA-URI**: voer **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages** in
   - **Waarde**: voer een lijst in met de app-pakketnamen die u wilt toestaan. U kunt **; : ,** of **|** gebruiken als scheidingsteken. (Voorbeeld: pakket1; pakket2;)

4. Klik op **OK** en kies vervolgens in het deelvenster **Profiel maken** de optie **Maken**.

>[!TIP]
> U kunt de pakket-id van een app vinden door te bladeren naar de app in de Google Play-store. De pakket-id is opgenomen in de URL van de pagina van de app. De pakket-id van de Microsoft Word-app is bijvoorbeeld **com.microsoft.office.word**.

De volgende keer dat een doelapparaat incheckt, worden de app-instellingen toegepast.


<!---## Assign the custom profile--->
