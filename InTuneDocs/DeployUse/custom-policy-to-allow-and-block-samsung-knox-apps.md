---
title: Toegestane en geblokkeerde apps voor KNOX | Microsoft Intune
description: Aangepast profiel voor het maken van een lijst met toegestane en geblokkeerde apps voor KNOX.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/09/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc8e0df-7bf3-494e-8bc4-dac59a98ab41
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 65d2c9c1f5d81dae33422bd4bf7c0e2e21bb96e4
ms.openlocfilehash: 937e291f193f61329598395baa63c24d7fefa25f



---
# Aangepaste beleidsregels gebruiken om apps toe te staan of te blokkeren voor Samsung KNOX-apparaten

Gebruik de procedures in dit onderwerp om een aangepast Microsoft Intune-beleid op te stellen voor het maken van een van de volgende lijsten:

- Een lijst met apps die niet kunnen worden uitgevoerd op het apparaat. Er mogen geen andere apps worden uitgevoerd. Apps in deze lijst worden geblokkeerd, wat betekent dat ze niet worden uitgevoerd, ook niet al ze al waren geïnstalleerd toen het beleid werd toegepast.
- Een lijst met apps die gebruikers van het apparaat kunnen installeren uit de Google Play Store. Alleen de apps die u in de lijst opneemt, kunnen worden geïnstalleerd. Geen andere apps kunnen worden geïnstalleerd uit de Store.

Deze instellingen kunnen alleen worden gebruikt door apparaten met Samsung KNOX.

## En lijst met toegestane of geblokkeerde apps maken

1. Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) de optie **Beleid** &gt; **Configuratiebeleid** &gt; **Toevoegen**.
2. Vouw in het dialoogvenster **Een nieuw beleid maken** de optie **Android** uit, kies **Aangepaste configuratie** en kies vervolgens **Beleid maken**.
3. Geef een naam op en voer eventueel een beschrijving in voor het beleid en kies vervolgens in de sectie **OMA-URI-instellingen** de optie **Toevoegen**.
4. Geef in het dialoogvenster **OMA-URI-instelling toevoegen of bewerken** het volgende op: Voor een lijst met apps die zijn geblokkeerd en dus niet kunnen worden uitgevoerd op het apparaat:
    
    - **naam van instelling.** Voer **PreventStartPackages** in.
    - **Beschrijving van instelling.** Voer eventueel een beschrijving in, zoals 'Lijst met apps die zijn geblokkeerd'.
    -   **Gegevenstype.** Kies **Tekenreeks** in de vervolgkeuzelijst.
    -   **OMA-URI.** Voer **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages** in.
    -   **Waarde.** Voer een lijst in van de app-pakketnamen die u wilt toestaan. U kunt **; : ,** of **|** gebruiken als scheidingsteken. (Voorbeeld: pakket1; pakket2;)

    Voor een lijst met apps die gebruikers mogen installeren vanuit de Google Play Store, terwijl alle andere apps worden uitgesloten:

    - **naam van instelling.** Voer **AllowInstallPackages** in.
    - **Beschrijving van instelling.** Voer eventueel een beschrijving in, zoals 'Lijst met apps die gebruikers kunnen installeren vanuit Google Play'.
    - **Gegevenstype.** Kies **Tekenreeks** in de vervolgkeuzelijst.
    - **OMA-URI.** Voer **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages** in.
    - **Waarde.** Voer een lijst in van de app-pakketnamen die u wilt toestaan. U kunt **; : ,** of **|** gebruiken als scheidingsteken. (Voorbeeld: pakket1; pakket2;)

4. Klik op **OK** en vervolgens op **Beleid opslaan**. 

>[TIP] U kunt de pakket-id van een app vinden door te bladeren naar de app in de Google Play Store. De pakket-id is opgenomen in de URL van de pagina van de app. De pakket-id van de Microsoft Word-app is bijvoorbeeld **com.microsoft.office.word**.

De volgende keer dat een doelapparaat incheckt, worden de app-instellingen toegepast.


## Het beleid implementeren

1.  Selecteer het beleid dat u wilt implementeren in de werkruimte **Beleid** en klik vervolgens op **Implementatie beheren**.

2.  Selecteer in het dialoogvenster **Implementatie beheren** een of meer groepen waarvoor u het beleid wilt implementeren en klik vervolgens op **Toevoegen** &gt; **OK**.

 
Wanneer u een geïmplementeerde beleid selecteert, kunt u meer informatie over de implementatie weergeven onder in de lijst met beleidsregels.

### Zie tevens
[Instellingen voor het Android- en Samsung KNOX-beleid in Microsoft Intune](android-policy-settings-in-microsoft-intune.md)



<!--HONumber=Aug16_HO3-->


