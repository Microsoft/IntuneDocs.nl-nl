---
title: Inschrijvingsbeperkingen instellen in Microsoft Intune
titleSuffix: ''
description: Beperk het registreren per platform en geef een registratielimiet voor apparaten op in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/17/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1080ae8a73223ad16445d0d2233434faa818b04b
ms.sourcegitcommit: 71314481e644025c005019b478b4cbeaf2390ea9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/05/2019
ms.locfileid: "59569113"
---
# <a name="set-enrollment-restrictions"></a>Registratiebeperkingen instellen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Als Intune-beheerder kunt u registratiebeperkingen maken en beheren om voor apparaten het aantal en de typen van die op te geven dat /die onder beheer met Intune kan/kunnen worden geregistreerd. U kunt meerdere beperkingen maken en deze toepassen op verschillende gebruikersgroepen. U kunt de [volgorde van prioriteit](#change-enrollment-restriction-priority) voor uw andere beperkingen instellen.

>[!NOTE]
>Inschrijvingsbeperkingen vormen geen beveiligingsfuncties. Aangetaste apparaten kunnen zich anders voordoen dan ze in werkelijkheid zijn. Deze beperkingen zijn een best-effort barrière voor niet-kwaadwillende gebruikers.

U kunt onder ander de volgende registratiebeperkingen maken:

- Maximum aantal geregistreerde apparaten.
- De ondersteunde apparaatplatformen:
  - Android
  - Android-werkprofiel
  - iOS
  - macOS
  - Windows
  - Windows Mobile
- Platformbesturingssysteemversie voor iOS, Android, Android-werkprofielen, Windows en Windows Mobile. (Alleen Windows 10-versies kunnen worden gebruikt. Laat dit veld leeg als Windows 8.1 is toegestaan.)
  - Minimale versie.
  - Maximale versie.
- Beperkingen opleggen voor apparaten die persoonlijk eigendom zijn (alleen iOS, Android, Android-werkprofielen, macOS, Windows en Windows Mobile).

## <a name="default-restrictions"></a>Standaardbeperkingen

Standaardbeperkingen worden automatisch opgegeven voor registratiebeperkingen voor zowel het apparaattype als de apparaatlimiet. U kunt de opties voor de standaardinstellingen wijzigen. De standaardbeperkingen zijn van toepassing op alle gebruikersregistraties en registraties zonder gebruikers. U kunt deze standaardinstellingen onderdrukken door nieuwe beperkingen met een hogere prioriteit te maken.

## <a name="create-a-restriction"></a>Een beperking maken

1. Meld u aan bij Azure Portal.
2. Selecteer **Meer Services**, zoek naar **Intune** en kies vervolgens **Intune**.
3. Selecteer **Apparaatinschrijving** > **Inschrijvingsbeperkingen**.
4. Selecteer **Beperking maken**.
5. Geef een naam en beschrijving voor de beperking op.
6. Kies een **beperkingstype** en selecteer **Maken**.
7. Selecteer **Apparaatlimiet** voor apparaatlimietbeperkingen om het maximum aantal apparaten in te stellen dat een gebruiker kan inschrijven.
8. Selecteer **Platforms** en **Platformconfiguraties** voor apparaattypebeperkingen om verschillende platforms en versies toe te staan of te blokkeren.
9. Selecteer **Toewijzingen** > **+ Groepen selecteren**.
10. Selecteer onder **Groepen selecteren** een of meer groepen en kies vervolgens **Selecteren**. De beperking geldt alleen voor de groepen waaraan deze is toegewezen. Als u geen beperking aan ten minste één groep toewijst, heeft deze bewerking dit geen effect.
11. Selecteer **Opslaan**.
12. De nieuwe beperking wordt gemaakt met een prioriteit boven de standaardwaarde. U kunt [de prioriteit wijzigen](#change-enrollment-restriction-priority).

## <a name="set-device-type-restrictions"></a>Beperkingen voor apparaattypen instellen

U kunt de instellingen voor een beperking van het type apparaat wijzigen via onderstaande stappen. Deze beperkingen hebben geen invloed op apparaten die al zijn geregistreerd. Apparaten die zijn geregistreerd bij de [Intune PC-agent](manage-windows-pcs-with-microsoft-intune.md), kunnen niet met deze functie worden geblokkeerd.

1. Meld u aan bij Azure Portal.
2. Selecteer **Meer Services**, zoek naar **Intune** en kies vervolgens **Intune**.
3. Selecteer **Apparaatinschrijving** > **Inschrijvingsbeperkingen**.
4. Kies onder **Beperking voor apparaattypen** de beperking die u wilt instellen > **Eigenschappen** > **Platformen selecteren**. Kies **Toestaan** of **Blokkeren** voor elk weergegeven platform.
    ![Schermlimiet voor het toestaan of blokkeren van een platform](media/enrollment-restrictions-set/platform-allow-block.png)
5. Kies **OK**.
6. Kies **Platformen configureren**.
    ![Schermlimiet voor het configureren van platformen](media/enrollment-restrictions-set/configure-platforms.png)
7. Kies de minimale en maximale **versies** voor de platformen die worden weergegeven. Ondersteunde versie-indelingen omvatten:
    - Android-werkprofielen bieden ondersteuning voor major.minor.rev.build.
    - iOS ondersteunt major.minor.rev. Versies van besturingssystemen zijn niet van toepassing op Apple-apparaten die worden ingeschreven met Device Enrollment Program, Apple School Manager of de app Apple Configurator.
    - Windows ondersteunt alleen major.minor.rev.build voor Windows 10.
> [!Note]
> Windows 10 verstrekt niet het buildnummer tijdens het inschrijven. Als u bijvoorbeeld 10.0.17134.100 invoert en het apparaat nummer 10.0.17134.174 heeft, wordt het apparaat geblokkeerd.
8. Kies voor elk vermeld platform of u apparaten die **persoonlijk eigendom zijn** wilt **Toestaan** of **Blokkeren**.
9. Kies **OK**.

### <a name="blocking-personal-android-devices"></a>Persoonlijke Android-apparaten blokkeren
- Als u instelt dat Android-apparaten niet mogen worden geregistreerd als deze persoonlijk eigendom zijn, kunnen apparaten met een Android-werkprofiel die persoonlijk eigendom zijn, nog wel worden geregistreerd.
- Standaard zijn instellingen voor uw apparaten met een Android-werkprofiel gelijk aan de instellingen voor uw Android-apparaten. Wanneer u de instellingen voor Android-werkprofielen wijzigt, is dat niet meer het geval.
- Als u het registreren van persoonlijke apparaten met een Android-werkprofiel blokkeert, kunnen alleen zakelijke Android-apparaten worden geregistreerd als apparaat met een Android-werkprofiel.

### <a name="blocking-personal-windows-devices"></a>Persoonlijke Windows-apparaten blokkeren
Als u uw eigen Windows-apparaten blokkeert voor inschrijving, wordt door Intune gecontroleerd of elke nieuwe Windows-registratieaanvraag wordt geautoriseerd als een zakelijke inschrijving. Niet-geautoriseerde inschrijvingen worden geblokkeerd.

De volgende methoden worden gezien als een zakelijke Windows-registratie:
 - De ingeschreven gebruiker maakt gebruik van [een apparaatinschrijvingsmanageraccount]( device-enrollment-manager-enroll.md).
- Het apparaat is geregistreerd via [Windows AutoPilot](enrollment-autopilot.md).
- Het apparaat wordt met Windows Autopilot geregistreerd, maar is geen Alleen MDM-inschrijving-optie van Windows-instellingen.
- Het IMEI-nummer van het apparaat wordt vermeld onder **Apparaatinschrijving** > **[Zakelijke apparaat-id's](corporate-identifiers-add.md)**. (Wordt niet ondersteund voor Windows Phone 8.1.)
- Het apparaat is geregistreerd via een [pakket voor bulkinrichting](windows-bulk-enroll.md).
- Het apparaat is geregistreerd via GPO, of er is sprake van [automatische inschrijving met behulp van SCCM voor co-beheer](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview#how-to-configure-co-management.md).
 
De volgende inschrijvingen zijn door Intune gemarkeerd als zakelijk. Maar omdat ze de controle Intune-beheerder per apparaat niet aanbieden, worden ze geblokkeerd:
 - [Automatische MDM-inschrijving](windows-enroll.md#enable-windows-10-automatic-enrollment) met [Azure Active Directory-koppeling tijdens het instellen van Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx)\*.
- [Automatische MDM-inschrijving](windows-enroll.md#enable-windows-10-automatic-enrollment) met [Azure Active Directory-koppeling vanuit Windows-instellingen](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network)*.
 
Ook de volgende persoonlijke registratiemethoden worden geblokkeerd:
- [Automatische MDM-inschrijving](windows-enroll.md#enable-windows-10-automatic-enrollment) via [Werkaccount toevoegen vanuit de Windows-instellingen](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network)\*.
- De optie [Alleen inschrijven voor MDM]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) in de Windows-instellingen.

\* Deze worden niet geblokkeerd als ze zijn geregistreerd met Autopilot.

## <a name="set-device-limit-restrictions"></a>Apparaatlimietbeperkingen instellen

U kunt de instellingen voor een beperking van de apparaatlimiet als volgt wijzigen:

1. Meld u aan bij Azure Portal.
2. Selecteer **Meer Services**, zoek naar **Intune** en kies vervolgens **Intune**.
3. Selecteer **Apparaatinschrijving** > **Inschrijvingsbeperkingen**.
4. Kies onder **Apparaatlimietbeperkingen** de beperking die u wilt instellen.
5. Selecteer **Apparaatlimiet** en selecteer in de vervolgkeuzelijst het maximum aantal apparaten dat een gebruiker kan registreren.
    ![De blade Apparaatlimietbeperkingen met beperkingen voor het aantal apparaten](./media/device-restrictions-limit.png)
6. Selecteer **Opslaan**.


Bij BYOD-registraties wordt er een melding aan gebruikers weergegeven waarin staat wanneer zij hun limiet van geregistreerde apparaten hebben bereikt. Bijvoorbeeld in iOS:

![Limietmelding op iOS-apparaat](./media/enrollment-restrictions-ios-set-limit-notification.png)

> [!IMPORTANT]
> Apparaatlimietbeperkingen zijn niet van toepassing op de volgende typen Windows-inschrijvingen:
> - Gezamenlijk beheerde inschrijvingen
> - GPO-inschrijvingen
> - Gezamenlijke Azure Active Directory-inschrijvingen
> - Gezamenlijke Azure Active Directory-inschrijvingen in bulk
> - Autopilot-inschrijvingen
>
> Apparaatlimietbeperkingen worden niet afgedwongen voor deze typen inschrijven, omdat ze worden beschouwd als gedeelde apparaten.
> U kunt [in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/devices/device-management-azure-portal#configure-device-settings) vaste limieten instellen voor deze typen inschrijvingen.

## <a name="change-enrollment-restriction-priority"></a>De prioriteit van de registratiebeperking wijzigen

Prioriteit wordt gebruikt wanneer een gebruiker voorkomt in meerdere groepen waaraan beperkingen zijn toegewezen. Voor gebruikers gelden alleen de hoogste prioriteitsbeperkingen die aan de groep waarvan zij deel uitmaken zijn toegewezen. Jan maakt bijvoorbeeld deel uit van groep A waaraan beperkingen met prioriteit 5 zijn toegewezen. Bovendien maakt hij deel uit van groep B waaraan beperkingen met prioriteit 2 zijn toegewezen. Voor Jan gelden alleen de beperkingen met prioriteit 2.

Wanneer u een beperking maakt, wordt deze net boven de standaardbeperking in de lijst geplaatst.

Voor apparaatinschrijving gelden standaardbeperkingen voor zowel het apparaattype als de apparaatlimiet. Deze twee beperkingen gelden voor alle gebruikers, tenzij ze worden overschreven door beperkingen met een hogere prioriteit.

U kunt de prioriteit van een niet-standaard-beperking wijzigen.

1. Meld u aan bij Azure Portal.
2. Selecteer **Meer Services**, zoek naar **Intune** en kies vervolgens **Intune**.
3. Selecteer **Apparaatinschrijving** > **Inschrijvingsbeperkingen**.
4. Beweeg de muisaanwijzer over de beperking in de lijst met prioriteiten.
5. Sleep de drie verticale puntjes voor de prioriteit naar de gewenste positie in de lijst.
