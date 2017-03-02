---
title: Intune-beleid voor het toestaan/blokkeren van apps voor Samsung KNOX | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: een aangepast profiel maken om apps toe te staan of te blokkeren voor Samsung KNOX Standard-apparaten.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: f5267d2e06f1cd7ec471fd1782bfd965843d1c7e
ms.lasthandoff: 02/16/2017



---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices-in-microsoft-intune"></a>Aangepast beleid gebruiken om apps toe te staan of te blokkeren voor Samsung KNOX Standard-apparaten in Microsoft Intune
[!INCLUDE[azure_preview](../includes/azure_preview.md)] Gebruik de procedures in dit onderwerp om een aangepast Microsoft Intune-beleid op te stellen voor het maken van een van de volgende lijsten:

- Een lijst met apps die niet kunnen worden uitgevoerd op het apparaat. Apps in deze lijst worden geblokkeerd, wat betekent dat ze niet worden uitgevoerd, ook niet al ze al waren geïnstalleerd toen het beleid werd toegepast.
- Een lijst met apps die gebruikers van het apparaat kunnen installeren uit de Google Play Store. Alleen de apps die u in de lijst opneemt, kunnen worden geïnstalleerd. Geen andere apps kunnen worden geïnstalleerd uit de Store.

Deze instellingen kunnen alleen worden gebruikt door apparaten met Samsung KNOX Standard.

## <a name="create-an-allowed-or-blocked-app-list"></a>En lijst met toegestane of geblokkeerde apps maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Apparaten configureren** op de blade **Intune**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
2. Kies **Profiel maken** op de blade met de profielenlijst.
3. Voer op de blade **Profiel maken** een **naam** en desgewenst een **beschrijving** in voor dit apparaatprofiel.
2. Kies voor **Platformtype** de optie **Android** en kies voor het profieltype de optie **Aangepast**.
3. Klik op **Instellingen**.
3. Kies **Toevoegen** op de blade **Aangepaste OMA-URI-instellingen**.
4. Geef in het dialoogvenster **OMA-URI-instelling toevoegen of bewerken** het volgende op:

### <a name="for-a-list-of-apps-that-are-blocked-from-running-on-the-device"></a>Voor een lijst met apps die worden geblokkeerd voor uitvoering op het apparaat:

- **Naam**: voer **PreventStartPackages** in.
- **Beschrijving**: voer eventueel een beschrijving in, zoals 'Lijst met apps die zijn geblokkeerd'.
-     **Gegevenstype**: kies **Tekenreeks** in de vervolgkeuzelijst.
-     **OMA-URI**: voer **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages** in
-     **Waarde**: voer een lijst in met de app-pakketnamen die u wilt toestaan. U kunt **; : ,** of **|** gebruiken als scheidingsteken. (Voorbeeld: pakket1; pakket2;)

### <a name="for-a-list-of-apps-that-users-are-allowed-to-install-from-the-google-play-store-while-excluding-all-other-apps"></a>Voor een lijst met apps die gebruikers mogen installeren vanuit de Google Play Store, terwijl alle andere apps worden uitgesloten:
- **Naam**: voer **AllowInstallPackages** in.
- **Beschrijving**: voer eventueel een beschrijving in, zoals 'Lijst met apps die gebruikers kunnen installeren vanuit Google Play'.
- **Gegevenstype**: kies **Tekenreeks** in de vervolgkeuzelijst.
- **OMA-URI**: voer **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages** in
- **Waarde**: voer een lijst in met de app-pakketnamen die u wilt toestaan. U kunt **; : ,** of **|** gebruiken als scheidingsteken. (Voorbeeld: pakket1; pakket2;)

4. Klik op **OK** en kies vervolgens op de blade **Profiel maken** de optie **Maken**.

>[!TIP]
> U kunt de pakket-id van een app vinden door te bladeren naar de app in de Google Play-store. De pakket-id is opgenomen in de URL van de pagina van de app. De pakket-id van de Microsoft Word-app is bijvoorbeeld **com.microsoft.office.word**.

De volgende keer dat een doelapparaat incheckt, worden de app-instellingen toegepast.


<!---## Assign the custom profile--->

