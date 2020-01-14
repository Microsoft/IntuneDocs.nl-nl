---
title: Office 365 bijwerken met beheersjablonen in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik beheersjablonen in Microsoft Intune om Office 365-apps bij te werken naar de nieuwste versie en kies hoe vaak op updates moet worden gecontroleerd. Zie de registersleutels van het apparaat die worden bijgewerkt wanneer er een Intune-beleid wordt toegepast op Office Update.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 63ebbc22c5452c99439d34813509b5652daef1f0
ms.sourcegitcommit: a82d25d98fdf0ba766f8f074871d4f13725e23f9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/31/2019
ms.locfileid: "75548097"
---
# <a name="use-update-channel-and-target-version-settings-to-update-office-365-with-microsoft-intune-administrative-templates"></a>Instellingen van het updatekanaal en de doelversie gebruiken om Office 365 bij te werken met Microsoft Intune-beheersjablonen

In Intune kunt u [Windows 10-sjablonen gebruiken om instellingen voor groepsbeleid te configureren](administrative-templates-windows.md). In dit artikel wordt beschreven hoe u Office 365 bijwerkt met behulp van een beheersjabloon in Intune. Het biedt ook richtlijnen om te bevestigen dat uw beleid is toegepast. U kunt deze informatie ook gebruiken bij het oplossen van problemen.

In dit scenario maakt u een beheersjabloon in Intune waarmee Office 365 op uw apparaten wordt bijgewerkt.

Zie [Windows 10-sjablonen gebruiken voor het configureren van instellingen voor groepsbeleid](administrative-templates-windows.md) voor meer informatie over beheersjablonen.

Van toepassing op:

- Windows 10 en hoger
- Office 365

## <a name="prerequisites"></a>Vereisten

[Schakel automatische updates voor Office365 ProPlus in](https://docs.microsoft.com/deployoffice/configure-update-settings-for-office-365-proplus) op uw Office-apps. U kunt dit doen met behulp van groepsbeleid of met de Intune Office 2016 ADMX-sjabloon:

![De instelling Automatische updates inschakelen voor Office instellen in de Intune-beheersjabloon](./media/administrative-templates-update-office/admx-enable-automatic-updates.png)

## <a name="set-the-update-channel-in-the-intune-administrative-template"></a>Het updatekanaal instellen in de Intune-beheersjabloon instellen

1. Ga in de [Intune-beheersjabloon](administrative-templates-windows.md#create-a-template) naar de instelling **Updatekanaal** en voer het gewenste kanaal in. Kies bijvoorbeeld `Semi-Annual Channel`:

    ![Stel in de Intune-beheersjabloon de instelling Updatekanaal in voor Office](./media/administrative-templates-update-office/admx-enable-update-channel-setting.png)

    > [!NOTE]
    > Het wordt aanbevolen om regelmatig updates uit te voeren. Hier wordt halfjaarlijks slechts als voorbeeld gebruikt.

2. [Wijs het beleid toe](device-profile-assign.md) aan uw Windows 10-apparaten. Als u het beleid sneller wilt testen, kunt u het beleid ook synchroniseren:

    - [Het beleid in Intune synchroniseren](../remote-actions/device-sync.md)
    - [Het beleid handmatig op het apparaat synchroniseren](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows#sync-from-settings-app)

## <a name="check-the-intune-registry-keys"></a>Intune-registersleutels controleren

Nadat u het beleid en de apparaatsynchronisaties hebt toegewezen, kunt u bevestigen dat het beleid wordt toegepast:

1. Open de app **Register-editor** op het apparaat.
2. Ga naar het pad van het Intune-beleid: `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\Providers\<Provider ID>\default\Device\office16~Policy~L_MicrosoftOfficemachine~L_Updates`.

    > [!TIP]
    > De `<Provider ID>` in de registersleutel wordt gewijzigd. U kunt de provider-id voor uw apparaat vinden door de app **Register-editor** te openen en naar `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\AdmxInstalled` te gaan. De provider-id wordt weer gegeven.

    Wanneer het beleid wordt toegepast, ziet u de volgende registersleutels:

    - `L_UpdateBranch`
    - `L_UpdateTargetVersion`

    Bekijk het volgende voorbeeld. U ziet dat `L_UpdateBranch` een vergelijkbare waarde heeft als `<enabled /><data id="L_UpdateBranchID" value="Deferred" />`. Deze waarde betekent dat deze is ingesteld op Semi-Annual-kanaal:

    ![Voorbeeld: registersleutel L_Updatebranch in beheersjabloon](./media/administrative-templates-update-office/admx-update-branch-registry-key.png)

    > [!TIP]
    > In [Office 365 ProPlus beheren met Configuration Manage](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates#bkmk_channel) worden de waarden met hun betekenis vermeld. De registerwaarden zijn gebaseerd op het geselecteerde distributiekanaal:
    >
    >- Monthly-kanaal                - waarde="Current"
    >- Monthly-kanaal (Targeted)     - waarde="Current"
    >- Semi-Annual-kanaal            - waarde="Current"
    >- Semi-Annual-kanaal (targeted) - waarde="FirstReleaseDeferred"
    >- Insider Fast                   - waarde="InsiderFast"

Op dit punt wordt het Intune-beleid toegepast op het apparaat.

## <a name="check-the-office-registry-keys"></a>Office-registersleutels controleren

1. Open de app **Register-editor** op het apparaat.
2. Ga naar het pad van het Office-beleid: `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Configuration`.

    U ziet de volgende registersleutels:

    - `UpdateChannel`: een dynamische sleutel die wordt gewijzigd, afhankelijk van de geconfigureerde instellingen.
    - `CDNBaseUrl`: deze wordt ingesteld wanneer Office 365 op het apparaat wordt geïnstalleerd.

3. Bekijk de waarde `UpdateChannel`. De waarde vertelt u hoe vaak Office wordt bijgewerkt. In [Office 365 ProPlus beheren met Configuration Manage](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates#bkmk_channel) worden de waarden vermeld en waarvoor ze zijn ingesteld.

    In het volgende voorbeeld ziet u dat `UpdateChannel` is ingesteld op `http://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60`, dus op **maandelijks**:

    ![Voorbeeld: registersleutel UpdateChannel van Office in beheersjabloon](./media/administrative-templates-update-office/admx-update-channel-office-registry-key.png)

    Dit voorbeeld betekent dat het beleid nog niet wordt toegepast, omdat het nog steeds is ingesteld op **maandelijks** in plaats van **halfjaarlijks**.

Deze registersleutel wordt bijgewerkt wanneer **Task Scheduler** > **Automatische updates voor Office 2.0** wordt uitgevoerd of wanneer een gebruiker zich aanmeldt op het apparaat. Open de taak **Automatische updates voor Office 2.0** > **Triggers** om te bevestigen. Afhankelijk van uw triggers kan het minstens een dag of langer duren voordat registersleutel `UpdateChannel` wordt bijgewerkt.

## <a name="force-office-automatic-updates-to-run"></a>Automatische updates van Office afdwingen om te worden uitgevoerd

Als u het beleid wilt testen, kunt u de beleidsinstellingen op het apparaat afdwingen. Het register wordt in de volgende stappen bijgewerkt. Wees altijd voorzichtig bij het bijwerken van het register.

1. Registersleutel wissen:

    1. Ga naar `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Updates`.
    2. Selecteer tweemaal sleutel `UpdateDetectionLastRunTime`, verwijder de waardegegevens > **OK**.

2. Taak Automatische updates van Office uitvoeren:

    1. Open de app **Task Scheduler** op het apparaat.
    2. Vouw **Task Scheduler-bibliotheek** > **Microsoft** > **Office** uit.
    3. Selecteer **Automatische updates van Office 2.0** > **Uitvoeren**:

        ![Task Scheduler openen en Automatische updates van Office uitvoeren](./media/administrative-templates-update-office/admx-task-scheduler-office-automatic-updates.png)

        Wacht tot de taak is voltooid. Dit kan enkele minuten duren.

3. Ga in de app **Register-editor** naar `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\ClickToRun\Configuration`. Controleer waarde `UpdateChannel`.

    Deze moet worden bijgewerkt met de waarde die in het beleid is ingesteld. In ons voorbeeld moet de waarde worden ingesteld op `http://officecdn.microsoft.com/pr/7ffbc6bf-bc32-4f92-8982-f9dd17fd3114`.

Op dit moment wordt het Office-updatekanaal op het apparaat gewijzigd. Als u de status wilt controleren, kunt u een Office 365-app openen voor een gebruiker die deze update ontvangt.

## <a name="force-the-office-synchronization-to-update-account-information"></a>Office-synchronisatie afdwingen accountgegevens bij te werken  

Als u meer wilt doen, kunt u Office afdwingen de nieuwste versie-update op te halen. De volgende stappen moeten alleen worden uitgevoerd als een bevestiging of als u de meest recente versie-update van dat kanaal snel wilt ophalen. Laat anders Office het werk doen en laat automatisch bijwerken.

### <a name="step-1-force-the-office-version-to-update"></a>Stap 1: Office-versie afdwingen tot bijwerken

1. Bevestig dat de Office-versie ondersteuning biedt voor het updatekanaal dat u kiest. [Update history for Office 365 ProPlus](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date) (Updategeschiedenis van Office 365 ProPlus) bevat de buildnummers die de verschillende updatekanalen ondersteunen.

2. Ga in de [Intune-beheersjabloon](administrative-templates-windows.md#create-a-template) naar de instelling **Doelversie** en voer de gewenste versie in.

    De instelling **Doelversie** lijkt op de volgende instelling:

    ![Stel in de Intune-beheersjabloon de instelling Doelversie in voor Office](./media/administrative-templates-update-office/admx-enable-target-version-setting.png)

> [!IMPORTANT]
>
> - Wijs het beleid toe.
> - Als u een bestaand beleid wijzigt, zijn uw wijzigingen van invloed op alle toegewezen gebruikers.
> - Als u deze functie test, is het raadzaam om een testbeleid te maken en het beleid toe te wijzen aan een testgroep van gebruikers.

### <a name="step-2-check-the-office-version"></a>Stap 2: Office-versie controleren

U kunt deze stappen gebruiken om uw beleid te testen voordat u het beleid voor alle gebruikers implementeert.

1. Ga in de app **Register-editor** naar `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\Providers\<Provider ID>\default\Device\office16~Policy~L_MicrosoftOfficemachine~L_Updates`

2. Bekijk de waarde `L_UpdateTargetVersion`. Zodra het beleid van toepassing is, wordt de waarde ingesteld op de versie die u hebt ingevoerd, bijvoorbeeld `<enabled /><data id="L_UpdateTargetVersionID" value="16.0.10730.20344" />`.

    Op dit punt wordt het Intune-beleid toegepast op het apparaat.

3. Vervolgens kunt u Office afdwingen dat er wordt bijgewerkt. Open een Office-app, bijvoorbeeld Excel. Kies ervoor om nu bij te werken (mogelijk in het menu **Account**).

    Het duurt enkele minuten voordat de update is uitgevoerd. U kunt controleren of Office de door u ingevoerde versie ophaalt:

      1. Ga op het apparaat naar `C:\Program Files (x86)\Microsoft Office\Updates\Detection\Version`.
      2. Open bestand `VersionDescriptor.xml` en ga naar sectie `<Version>`. De beschikbare versie moet dezelfde versie zijn die u hebt ingevoerd in het Intune-beleid, bijvoorbeeld:

          ![Controleer de versiesectie in het Office XML-bestand met de versiedescriptor](./media/administrative-templates-update-office/office-version-descriptor-xml-example.png)

4. Nadat de update is geïnstalleerd, moet de Office-app de nieuwe versie weergeven (bijvoorbeeld in het menu **Account**)

## <a name="next-steps"></a>Volgende stappen

[Kanaalwaarden voor Office 365-clients bijwerken](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates#bkmk_channel)

[Overview of the Office cloud policy service for Office 365 ProPlus](https://docs.microsoft.com/deployoffice/overview-office-cloud-policy-service) (Overzicht van de Office-cloudbeleidsservice voor Office 365 ProPlus)

[Windows 10-sjablonen gebruiken voor het configureren van instellingen voor groepsbeleid (ADMX-sjablonen) in Microsoft Intune](administrative-templates-windows.md)
