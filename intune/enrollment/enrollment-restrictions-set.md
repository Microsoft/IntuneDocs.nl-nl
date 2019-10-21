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
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3f041c76b4d9b3814a020d51ad4cbb8e33df6c27
ms.sourcegitcommit: 60ed93682a21860e9d99ba1592ede120477f2b4d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72379817"
---
# <a name="set-enrollment-restrictions"></a>Registratiebeperkingen instellen

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Als Intune-beheerder kunt u inschrijvingsbeperkingen maken en beheren waarmee wordt gedefinieerd welke apparaten kunnen worden ingeschreven bij Intune, inclusief:
- aantal apparaten
- besturingssystemen en versies. U kunt meerdere beperkingen maken en deze toepassen op verschillende gebruikersgroepen. U kunt de [volgorde van prioriteit](#change-enrollment-restriction-priority) voor uw andere beperkingen instellen.

>[!NOTE]
>Inschrijvingsbeperkingen vormen geen beveiligingsfuncties. Aangetaste apparaten kunnen zich anders voordoen dan ze in werkelijkheid zijn. Deze beperkingen zijn een best-effort barrière voor niet-kwaadwillende gebruikers.

U kunt onder ander de volgende registratiebeperkingen maken:

- Maximum aantal geregistreerde apparaten.
- De ondersteunde apparaatplatformen:
  - Android-apparaatbeheerder
  - Android Enterprise - Werkprofiel
  - iOS
  - macOS
  - Windows
  - Windows Mobile
- Platformbesturingssysteemversie voor iOS, Android-apparaatbeheerder, Android-werkprofiel, Windows en Windows Mobile. (Alleen Windows 10-versies kunnen worden gebruikt. Laat dit veld leeg als Windows 8.1 is toegestaan.)
  - Minimale versie.
  - Maximale versie.
- Beperk [apparaten in persoonlijk eigendom](device-enrollment.md#bring-your-own-device) (alleen iOS, Android-apparaatbeheerder, Android-werkprofiel, macOS, Windows en Windows Mobile).

## <a name="default-restrictions"></a>Standaardbeperkingen

Standaardbeperkingen worden automatisch opgegeven voor registratiebeperkingen voor zowel het apparaattype als de apparaatlimiet. U kunt de opties voor de standaardinstellingen wijzigen. De standaardbeperkingen zijn van toepassing op alle gebruikersregistraties en registraties zonder gebruikers. U kunt deze standaardinstellingen onderdrukken door nieuwe beperkingen met een hogere prioriteit te maken.

## <a name="create-a-device-type-restriction"></a>Een beperking voor apparaattype maken

1. Meld u aan bij Azure Portal.
2. Selecteer **Meer Services**, zoek naar **Intune** en kies vervolgens **Intune**.
3. Selecteer **Apparaatinschrijving** > **Inschrijvingsbeperkingen** > **Beperking maken** > **Beperking voor apparaattype**.
    ![Schermopname voor het maken van een beperking voor apparaattype](./media/enrollment-restrictions-set/create-device-type-restriction.png)
4. Geef op de pagina **Basisinformatie** de beperking op voor een **Naam** en optioneel ook voor **Beschrijving**.
5. Kies **Volgende** om naar de pagina **Platforminstellingen** te gaan.
6. Kies onder **Platform** de optie **Toestaan** voor de platforms waarvoor u deze beperking wilt toestaan.
    ![Schermopname voor het kiezen van platforminstellingen](./media/enrollment-restrictions-set/choose-platform-settings.png)
7. Kies onder **Versies** de minimale en maximale versies die u wilt ondersteunen op de toegestane platforms. Versiebeperkingen zijn alleen van toepassing op apparaten die zijn ingeschreven via de bedrijfsportal.
     Ondersteunde versie-indelingen omvatten:
    - Android-apparaatbeheerder en Android Enterprise-werkprofiel bieden ondersteuning voor major.minor.rev.build.
    - iOS ondersteunt major.minor.rev. Versies van besturingssystemen zijn niet van toepassing op Apple-apparaten die worden ingeschreven met Device Enrollment Program, Apple School Manager of de app Apple Configurator.
    - Windows biedt alleen ondersteuning voor major.minor.build.rev voor Windows 10.
    > [!Note]
    > Windows 10 verstrekt niet het rev-nummer tijdens het inschrijven. Als u bijvoorbeeld 10.0.17134.100 invoert en het apparaat nummer 10.0.17134.174 heeft, wordt het apparaat geblokkeerd.

8. Kies onder **Persoonlijk eigendom** de optie **Toestaan** voor de platforms die u wilt toestaan als apparaten in persoonlijk eigendom.
9. Kies **Volgende** om naar de pagina **Toewijzingen** te gaan.
10. Kies **Groepen selecteren om op te nemen** en gebruik vervolgens het zoekvak om groepen te vinden die u wilt opnemen in deze beperking. De beperking geldt alleen voor de groepen waaraan deze is toegewezen. Als u geen beperking aan ten minste één groep toewijst, heeft deze bewerking dit geen effect. Kies dan de optie **Selecteren**. 
    ![Schermopname voor het kiezen van platforminstellingen](./media/enrollment-restrictions-set/select-groups.png)
11. Selecteer **Volgende** om naar de pagina **Controleren en maken** te gaan.
12. Selecteer **Maken** om de beperking te maken.
13. De nieuwe beperking wordt gemaakt met een prioriteit boven de standaardwaarde. U kunt [de prioriteit wijzigen](#change-enrollment-restriction-priority).


## <a name="create-a-device-limit-restriction"></a>Een beperking voor apparaatlimiet maken

1. Meld u aan bij Azure Portal.
2. Selecteer **Meer Services**, zoek naar **Intune** en kies vervolgens **Intune**.
3. Selecteer **Apparaatinschrijving** > **Inschrijvingsbeperkingen** > **Beperking maken** > **Beperking voor apparaatlimiet**.
    ![Schermopname voor het maken van een beperking voor apparaatlimiet](./media/enrollment-restrictions-set/create-device-limit-restriction.png)
4. Geef op de pagina **Basisinformatie** de beperking op voor een **Naam** en optioneel ook voor **Beschrijving**.
5. Kies **Volgende** om naar de pagina **Apparaatlimiet** te gaan.
6. Selecteer voor **Apparaatlimiet** het maximum aantal apparaten dat een gebruiker kan inschrijven.
    ![Schermopname voor het kiezen van de apparaatlimiet](./media/enrollment-restrictions-set/choose-device-limit.png)
7. Kies **Volgende** om naar de pagina **Toewijzingen** te gaan.
8. Kies **Groepen selecteren om op te nemen** en gebruik vervolgens het zoekvak om groepen te vinden die u wilt opnemen in deze beperking. De beperking geldt alleen voor de groepen waaraan deze is toegewezen. Als u geen beperking aan ten minste één groep toewijst, heeft deze bewerking dit geen effect. Kies dan de optie **Selecteren**. 
    ![Schermopname voor het selecteren van groepen](./media/enrollment-restrictions-set/select-groups-device-limit.png)
11. Selecteer **Volgende** om naar de pagina **Controleren en maken** te gaan.
12. Selecteer **Maken** om de beperking te maken.
13. De nieuwe beperking wordt gemaakt met een prioriteit boven de standaardwaarde. U kunt [de prioriteit wijzigen](#change-enrollment-restriction-priority).

Bij BYOD-registraties wordt er een melding aan gebruikers weergegeven waarin staat wanneer zij hun limiet van geregistreerde apparaten hebben bereikt. Bijvoorbeeld in iOS:

![Limietmelding op iOS-apparaat](./media/enrollment-restrictions-set/enrollment-restrictions-ios-set-limit-notification.png)

> [!IMPORTANT]
> Apparaatlimietbeperkingen zijn niet van toepassing op de volgende typen Windows-inschrijvingen:
> - Gezamenlijk beheerde inschrijvingen
> - GPO-inschrijvingen
> - Gezamenlijke Azure Active Directory-inschrijvingen
> - Gezamenlijke Azure Active Directory-inschrijvingen in bulk
> - Autopilot-inschrijvingen
> - Inschrijvingen met Apparaatinschrijvingsmanager
>
> Apparaatlimietbeperkingen worden niet afgedwongen voor deze inschrijvingstypen, omdat ze worden beschouwd als gedeelde apparaten.
> U kunt [in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/device-management-azure-portal#configure-device-settings) vaste limieten instellen voor deze typen inschrijvingen.


## <a name="change-enrollment-restrictions"></a>Inschrijvingsbeperkingen wijzigen

U kunt de instellingen voor een inschrijvingsbeperking wijzigen via de onderstaande stappen. Deze beperkingen hebben geen invloed op apparaten die al zijn ingeschreven. Apparaten die zijn geregistreerd bij de [Intune PC-agent](../fundamentals/manage-windows-pcs-with-microsoft-intune.md), kunnen niet met deze functie worden geblokkeerd.

1. Meld u aan bij Azure Portal.
2. Selecteer **Meer Services**, zoek naar **Intune** en kies vervolgens **Intune**.
3. Selecteer **Apparaatinschrijving** > **Inschrijvingsbeperkingen** > kies de beperking die u wilt wijzigen > **Eigenschappen**.
4. Kies **Bewerken** naast de instellingen die u wilt wijzigen.
5. Breng op de pagina **Bewerken** de gewenste wijzigingen aan, ga door naar de pagina **Controleren en opslaan**, en kies vervolgens **Opslaan**.


## <a name="blocking-personal-android-devices"></a>Persoonlijke Android-apparaten blokkeren
- Als u het inschrijven van apparaten met Android-apparaatbeheerder die persoonlijk eigendom zijn, blokkeert, kunnen apparaten met een Android Enterprise-werkprofiel nog steeds worden ingeschreven.
- Standaard zijn instellingen voor uw apparaten met een Android Enterprise-werkprofiel gelijk aan de instellingen voor uw apparaten met Android-apparaatbeheerder. Nadat u uw Android Enterprise-werkprofiel of de instellingen voor Android-apparaatbeheerder hebt gewijzigd, is dit niet meer het geval.
- Als u het inschrijven van persoonlijke apparaten met een Android-werkprofiel blokkeert, kunnen alleen Android-apparaten in bedrijfseigendom worden ingeschreven met een Android Enterprise-werkprofiel.

## <a name="blocking-personal-windows-devices"></a>Persoonlijke Windows-apparaten blokkeren
Als u uw eigen Windows-apparaten blokkeert voor inschrijving, wordt door Intune gecontroleerd of elke nieuwe Windows-registratieaanvraag wordt geautoriseerd als een zakelijke inschrijving. Niet-geautoriseerde inschrijvingen worden geblokkeerd.

De volgende methoden worden gezien als een zakelijke Windows-registratie:
- De ingeschreven gebruiker maakt gebruik van [een apparaatinschrijvingsmanageraccount]( device-enrollment-manager-enroll.md).
- Het apparaat is ingeschreven via [Windows AutoPilot](enrollment-autopilot.md).
- Het apparaat wordt met Windows Autopilot geregistreerd, maar is geen Alleen MDM-inschrijving-optie van Windows-instellingen.
- Het IMEI-nummer van het apparaat wordt vermeld onder **Apparaatinschrijving** >  **[Zakelijke apparaat-id's](corporate-identifiers-add.md)** . (Wordt niet ondersteund voor Windows Phone 8.1.)
- Het apparaat is geregistreerd via een [pakket voor bulkinrichting](windows-bulk-enroll.md).
- Het apparaat is geregistreerd via GPO, of er is sprake van [automatische inschrijving met behulp van SCCM voor co-beheer](https://docs.microsoft.com/sccm/comanage/quickstart-paths#bkmk_path1).
 
De volgende inschrijvingen zijn door Intune gemarkeerd als zakelijk. Maar omdat ze de controle Intune-beheerder per apparaat niet aanbieden, worden ze geblokkeerd:
- [Automatische MDM-inschrijving](windows-enroll.md#enable-windows-10-automatic-enrollment) met [Azure Active Directory-koppeling tijdens het instellen van Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx)\*.
- [Automatische MDM-inschrijving](windows-enroll.md#enable-windows-10-automatic-enrollment) met [Azure Active Directory-koppeling vanuit Windows-instellingen](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network)*.
 
Ook de volgende persoonlijke registratiemethoden worden geblokkeerd:
- [Automatische MDM-inschrijving](windows-enroll.md#enable-windows-10-automatic-enrollment) via [Werkaccount toevoegen vanuit de Windows-instellingen](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network)\*.
- De optie [Alleen inschrijven voor MDM]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) in de Windows-instellingen.

\* Deze worden niet geblokkeerd als ze zijn geregistreerd met Autopilot.


## <a name="blocking-personal-ios-devices"></a>Persoonlijke iOS-apparaten blokkeren
iOS-apparaten worden in Intune standaard geclassificeerd als persoonlijk eigendom. Een iOS-apparaat moet voldoen aan een van de volgende voorwaarden om te worden geclassificeerd als bedrijfseigendom:
- Het apparaat moet zijn geregistreerd met een serienummer of IMEI.
- Het apparaat moet zijn ingeschreven met behulp van Automatische apparaatinschrijving (voorheen Device Enrollment Program)


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
