---
title: Inschrijving met het Apple School Manager Program voor iOS-apparaten instellen
titlesuffix: Azure portal
description: Meer informatie over het instellen van inschrijving met het Apple School Manager Program voor zakelijke iOS-apparaten met Intune.
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 87e4c16fbb87ee83a01fe44a46c55c6243c8fc8a
ms.sourcegitcommit: 9bd6278d129fa29f184b2d850138f8f65f3674ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2018
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>Inschrijving van iOS-apparaten inschakelen met Apple School Manager

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

> [!NOTE]
> ### <a name="temporary-user-interface-differences"></a>Tijdelijke verschillen in de gebruikersinterface
>
>De gebruikersinterfaces voor de functies die op deze pagina worden beschreven, worden op dit moment bijgewerkt. Deze updates moeten tegen het einde van april in alle gebruikersaccounts zijn geïmplementeerd.
>
>Als uw pagina **Apparaatinschrijving** niet op de onderstaande afbeelding lijkt, is uw account nog niet bijgewerkt naar de nieuwe gebruikersinterface en kunt u deze Help-pagina gebruiken.
>
>![Oude gebruikersinterface](./media/appleenroll-oldui.png)
>
>Als uw pagina **Apparaatinschrijving** op de onderstaande afbeelding lijkt, beschikt u over de bijgewerkte gebruikersinterfaces.  Ga dan naar [deze Help-pagina](apple-school-manager-set-up-ios-newui.md).
>
>![Nieuwe gebruikersinterface](./media/appleenroll-newui.png)

Met de informatie in dit onderwerp kunt u iOS-apparaten registreren die zijn aangeschaft via het programma [Apple School Manager](https://school.apple.com/). Als u Intune gebruikt in combinatie met Apple School Manager, kunt u een groot aantal iOS-apparaten registreren zonder ze ooit aan te raken. Wanneer een student of docent het apparaat inschakelt, wordt Configuratieassistent uitgevoerd met vooraf gedefinieerde instellingen en wordt het apparaat geregistreerd voor beheer.

Als u registratie via Apple School Manager wilt inschakelen, gebruikt u zowel de Intune- als Apple School Manager-portal. U hebt een lijst met serienummers of een aankoopordernummer nodig om apparaten voor beheer aan Intune toe te wijzen. U maakt DEP-inschrijvingsprofielen met instellingen die tijdens de inschrijving op de apparaten van toepassing zijn geweest.

Registratie via Apple School Manager kan niet worden gebruikt voor het [Device Enrollment Program van Apple](device-enrollment-program-enroll-ios.md) of de [apparaatinschrijvingsmanager](device-enrollment-manager-enroll.md).

**Vereisten**
- [Apple MDM-pushcertificaat](apple-mdm-push-certificate-get.md)
- [MDM-instantie](mdm-authority-set.md)
- [Apple MDM-pushcertificaat](apple-mdm-push-certificate-get.md)
- Gebruikersaffiniteit vereist [WS-Trust 1.3 gebruikersnaam/gemengd eindpunt](https://technet.microsoft.com/library/adfs2-help-endpoints). [Meer informatie](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
- Apparaten die zijn gekocht via het programma [Apple School Management](http://school.apple.com)

>[!NOTE]
>Multi-Factor Authentication (MFA) werkt niet tijdens inschrijving op Apple School Manager-apparaten met gebruikersaffiniteit. Na de inschrijving werkt MFA zoals verwacht op deze apparaten. Na de inschrijving werkt MFA zoals verwacht op apparaten. Op apparaten wordt de gebruiker niet gevraagd het wachtwoord te wijzigen als ze zich de eerste keer aanmelden. Daarnaast wordt gebruikers met verlopen wachtwoorden niet gevraagd hun wachtwoord opnieuw in te stellen tijdens de inschrijving. Deze gebruikers moeten het wachtwoord vanaf een ander apparaat opnieuw instellen.

## <a name="get-the-apple-token-and-assign-devices"></a>De Apple-token downloaden en apparaten toewijzen

Voordat u iOS-bedrijfsapparaten met Apple School Manager kunt inschrijven, hebt u een token (.p7m) van Apple nodig. Intune kan met dit token informatie synchroniseren over apparaten die aan Apple School Manager deelnemen. Ook kan Intune hiermee inschrijvingsprofielen naar Apple uploaden en apparaten toewijzen aan die profielen. Als u zich in de Apple-portal bevindt, kunt u ook apparaatserienummers voor beheer toewijzen.

**Stap 1. Download een openbare-sleutelcertificaat van Intune dat is vereist voor het maken van een Apple-token.**<br>
1. Kies in [Azure Portal in Intune](https://aka.ms/intuneportal) achtereenvolgens **Apparaatinschrijving** en **Token voor het inschrijvingsprogramma**.

  ![Schermopname van het deelvenster Token voor het inschrijvingsprogramma in de werkruimte Apple-certificaten voor het downloaden van de openbare sleutel.](./media/enrollment-program-token-download.png)

2. Kies in de blade **Token voor het inschrijvingsprogramma** de optie **Uw openbare sleutel downloaden** om de versleutelingssleutel (.pem) lokaal op te slaan. Het .pem-bestand wordt gebruikt om een vertrouwensrelatiecertificaat bij de portal Apple School Manager aan te vragen.

**Stap 2. Download een token en wijs apparaten toe.**<br>
1. Kies **Een token via Apple School Manager maken** en meld u aan met de Apple-id van uw bedrijf. U kunt dit Apple-id gebruiken om uw Apple School Manager-token te verlengen.
2.  Ga in de [Apple School Manager-portal](https://school.apple.com) naar **MDM-servers** en kies vervolgens **MDM-server toevoegen** (rechtsboven).
3.  Voer de **MDM-servernaam** in. De servernaam is voor eigen referentie en dient om de MDM-server te identificeren. Het is niet de naam of URL van de Microsoft Intune-server.
   ![Schermopname van de Apple School Manager-portal met de optie voor het serienummer geselecteerd](./media/asm-server-assignment.png)

4.  Kies in de Apple-portal de optie **Bestand uploaden...**, blader naar het PEM-bestand en selecteer **MDM-server opslaan** (rechtsonder).
5.  Kies **Token ophalen** en download het servertokenbestand (.p7m) naar uw computer.
6. Ga naar **Toewijzingen van apparaten** en **Apparaat kiezen** door handmatige invoer van de **serienummers** of het **volgordenummer**, of selecteer **CSV-bestand uploaden**.
     ![Schermopname van de Apple School Manager-portal met de optie voor het serienummer geselecteerd](./media/asm-device-assignment.png)
7.  Kies de actie **Toewijzen aan server** en kies de **MDM-server** die u hebt gemaakt.
8. Geef uw apparaat aan onder **Apparaten kiezen** en geef de apparaatgegevens op.
9. Selecteer **Toewijzen aan server**, kies de &lt;Servernaam&gt; die is opgegeven voor Microsoft Intune en kies vervolgens **OK**.

**Stap 3. Voer de Apple-id in die u hebt gebruikt om uw Apple School Manager-token te maken.**<br>Deze id moet worden gebruikt om uw Apple School Manager-token te verlengen. De id wordt voor toekomstige referentie opgeslagen.

![Schermopname van het invoeren van de Apple ID die is gebruikt voor het maken van het token voor het inschrijvingsprogramma en het uploaden van het token.](./media/enrollment-program-token-apple-id.png)

**Stap 4. Uw token zoeken en uploaden.**<br>
Ga naar het certificaatbestand (.p7m), kies **Openen** en kies vervolgens **Uploaden**. Intune synchroniseert automatisch de Apple School Manager-apparaten van Apple.

## <a name="create-an-apple-enrollment-profile"></a>Een Apple-inschrijvingsprofiel maken
Met een inschrijvingsprofiel voor apparaten worden de instellingen gedefinieerd die worden toegepast op een groep apparaten tijdens de inschrijving.

1. Kies in Intune in Azure Portal achtereenvolgens **Apparaatinschrijving** en **Apple-inschrijving**.
2. Selecteer bij **Inschrijvingsprogramma** **Profielen voor het inschrijvingsprogramma**.
3. Kies op de blade **Profielen voor het inschrijvingsprogramma** de optie **Maken**.
4. Voer op de blade **Inschrijvingsprofiel maken** een **naam** en een **beschrijving** in voor het profiel dat wordt weergegeven in Intune.
5. Geef voor **Gebruikersaffiniteit** aan of u andere apparaten met dit profiel wilt inschrijven met of zonder gebruikersaffiniteit.

 - **Inschrijven met gebruikersaffiniteit**: hiermee wordt het apparaat tijdens de installatie aan een gebruiker gelieerd.

  Voor de modus Gedeelde iPad in Apple School Manager moeten gebruikers worden ingeschreven zonder gebruikersaffiniteit.

 - **Inschrijven zonder gebruikersaffiniteit**: kies deze optie voor een apparaat dat niet aan één gebruiker is gelieerd, zoals gedeelde apparaten. Gebruikt voor apparaten waarmee taken worden uitgevoerd zonder toegang tot lokale gebruikersgegevens. Apps als de bedrijfsportal-app werken niet.

6. Kies **Instellingen voor apparaatbeheer**. Deze items worden ingesteld tijdens de activering en om deze te wijzigen, moeten de instellingen naar de fabrieksinstellingen worden hersteld. Configureer de volgende profielinstellingen en kies vervolgens **Opslaan**:

  ![Schermopname van het kiezen van de beheermodus. Het apparaat heeft de volgende instellingen: Onder supervisie, Vergrendelde inschrijving, Koppelen toestaan, ingesteld om alles te weigeren. Apple Configurator-certificaten zijn niet beschikbaar voor een nieuw profiel van het inschrijvingsprogramma.](./media/enrollment-program-profile-mode.png)

    - **Onder supervisie**: een beheermodus waarmee standaard meer beheeropties worden ingeschakeld en de activeringsvergrendeling wordt uitgeschakeld. Als u het selectievakje leeg laat, hebt u beperkte beheermogelijkheden.

     - **Vergrendelde registratie** (hiervoor is Onder supervisie als beheermodus vereist): hiermee worden de iOS-instellingen uitgeschakeld waarmee het beheerprofiel kan worden verwijderd. Als u dit selectievakje leeg laat, kan het beheerprofiel uit het menu Instellingen worden verwijderd.
   - **Gedeelde iPad**: (hiervoor zijn **Registreren zonder gebruikersaffiniteit** en de supervisiemodus vereist.) Hiermee kunnen meerdere gebruikers zich met een beheerde Apple-id aanmelden bij geregistreerde iPads. Beheerde Apple-id's worden gemaakt in de portal Apple School Manager. Meer informatie over [gedeelde iPad](education-settings-configure-ios-shared.md). Controleer ook [de vereisten van Apple voor gedeelde iPad](https://help.apple.com/classroom/ipad/2.0/#/cad7e2e0cf56).

   >[!NOTE]
   >Als **Gebruikersaffiniteit** is ingesteld op **Met gebruikersaffiniteit** of als de modus **Onder supervisie** is ingesteld op **Uit**, wordt de modus Gedeelde iPad uitgeschakeld voor het inschrijvingsprofiel.

        - **Maximum Cached Users** - (Requires **Shared iPad** = **Yes**) Creates a partition on the device for each user. The recommended value is the number of students likely to use the device over a period of time. For example, if six students use the device regularly during the week, set this number to six.  

    - **Koppelen toestaan**: hiermee wordt aangegeven of iOS-apparaten kunnen worden gesynchroniseerd met computers. Als u **Apple Configurator per certificaat toestaan** kiest, moet u een certificaat kiezen onder **Apple Configurator-certificaten**.

      - **Apple Configurator-certificaten**: als u **Apple Configurator per certificaat toestaan** onder **Koppelen toestaan** hebt gekozen, kiest u het Apple Configurator-certificaat dat u wilt importeren.

7. Kies **Instellingen voor Configuratieassistent**, configureer de volgende profielinstellingen en kies vervolgens **Opslaan**:

    - **Naam van afdeling**: wordt weergegeven wanneer gebruikers tijdens de activering op **Over configuratie** tikken.

    - **Telefoonnummer van afdeling**: wordt weergegeven wanneer de gebruiker tijdens de activering de knop Hulp nodig? klikt.
    - **Configuratieassistentopties**: als deze instellingen waren uitgesloten in de configuratieassistentopties, kunnen ze naderhand worden ingesteld in het iOS-menu **Instellingen**.
        - **Wachtwoordcode**: hiermee wordt tijdens de activering gevraagd om de wachtwoordcode. Vraag altijd om een wachtwoordcode tenzij het apparaat wordt beveiligd of de toegang tot het apparaat op een andere manier wordt beheerd (bijvoorbeeld de kioskmodus waarmee op het apparaat maar één app kan worden uitgevoerd).
        - **Locatieservices**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om de service gevraagd
        - **Herstellen**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent gevraagd om een iCloud-back-up
        - **Apple-id**: als deze optie is ingeschakeld, worden gebruikers door iOS gevraagd om een Apple-id wanneer Intune een app zonder een id probeert te installeren. Een Apple-id is vereist voor het downloaden van iOS-apps uit de App Store, waaronder de apps die zijn geïnstalleerd door Intune.
        - **Voorwaarden**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent gevraagd de voorwaarden van Apple te accepteren
        - **Touch ID**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
        - **Apple Pay**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
        - **In- en uitzoomen**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
        - **Siri**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
        - **Diagnostische gegevens**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd.

8. Kies **Maken** op de blade **Inschrijvingsprofiel maken** om de profielinstellingen op te slaan.

## <a name="connect-school-data-sync"></a>Verbinding maken met Schoolgegevens synchroniseren
(Optioneel) Apple School Manager biedt ondersteuning voor het synchroniseren van gegevens van het lesrooster met Azure Active Directory (AD) met Microsoft School Data Sync (SDS). Voltooi de volgende stappen voor het gebruik van SDS om schoolgegevens te synchroniseren.

1. Kies op de blade **Token voor het inschrijvingsprogramma** de blauwe informatiebanner of **Verbinding maken met SDS**.
2. Kies **Toestaan dat dit token wordt gebruikt door Microsoft School Data Sync**, zodat deze instelling wordt **Toegestaan**. Met deze instelling kan Intune verbinding maken met SDS in Office 365.
3. Als u een verbinding tussen Apple School Manager en Azure AD wilt maken, kiest u **Microsoft School Data Sync instellen**. Meer informatie over [het instellen van Microsoft School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
4. Klik op **OK** om de gegevens op te slaan en door te gaan.

## <a name="sync-managed-devices"></a>Beheerde apparaten synchroniseren
Nu Intune toestemming heeft om uw Apple School Manager-apparaten te beheren, kunt u Intune synchroniseren met de Apple-service om uw beheerde apparaten weer te geven in Intune.

1. Kies **Apparaatinschrijving** > **Apple-inschrijving** > **Apparaten voor het inschrijvingsprogramma** > **Synchroniseren** in Intune in Azure Portal. Op de voortgangsbalk wordt aangegeven hoe lang u moet wachten voordat u opnieuw synchronisatie kunt aanvragen.

  ![Schermopname van het geselecteerde knooppunt Apparaten voor het inschrijvingsprogramma en een pijl naar de koppeling Synchroniseren.](./media/enrollment-program-device-sync.png)
2. Kies **Synchronisatie aanvragen** op de blade **Synchroniseren**. Op de voortgangsbalk wordt aangegeven hoe lang u moet wachten voordat u opnieuw synchronisatie kunt aanvragen.

  ![Schermopname van de blade Synchroniseren met een pijl naar de koppeling Synchronisatie aanvragen.](./media/enrollment-program-device-request-sync.png)

  Om te voldoen aan de voorwaarden van Apple voor acceptabel verkeer, worden de volgende beperkingen opgelegd:
   -    Een volledige synchronisatie kan niet vaker dan eens in de zeven dagen worden uitgevoerd. Tijdens een volledige synchronisatie vernieuwt Intune elk serienummer dat door Apple aan Intune is toegewezen, of het serienummer eerder is gesynchroniseerd of niet. Als een volledige synchronisatie wordt uitgevoerd binnen zeven dagen na de vorige volledige synchronisatie, vernieuwt Intune alleen serienummers die nog niet aanwezig zijn in Intune.
   -    Een synchronisatieaanvraag krijgt 15 minuten de tijd om te worden uitgevoerd. Gedurende deze tijd of totdat de aanvraag is geslaagd, is de knop **Synchronisatie** uitgeschakeld.

>[!NOTE]
>U kunt ook Apple School Manager-serienummers toewijzen aan profielen vanaf de blade **Apparaten voor het inschrijvingsprogramma**.

## <a name="assign-a-profile-to-devices"></a>Een profiel aan apparaten toewijzen
Apple School Manager-apparaten die worden beheerd door Intune, moeten een profiel voor het inschrijvingsprogramma toegewezen krijgen voordat ze worden ingeschreven.

1. Kies in Intune in Azure Portal **Apparaatinschrijving** > **Apple-inschrijving** en vervolgens **Profielen voor het inschrijvingsprogramma**.
2. Kies in de lijst **Profielen voor het inschrijvingsprogramma** het profiel dat u wilt toewijzen aan apparaten en kies vervolgens **Apparaattoewijzingen**

 ![Schermopname van Apparaattoewijzingen waarin Toewijzen is geselecteerd.](./media/enrollment-program-device-assign.png)

3. Kies **Toewijzen** en kies vervolgens de Apple School Manager-apparaten die u aan dit profiel wilt toewijzen. U kunt filteren om beschikbare apparaten weer te geven:
  - **niet-toegewezen**
  - **alle**
  - **&lt;profielnaam&gt;**
4. Kies de apparaten die u wilt toewijzen. Het selectievakje boven de kolom selecteert maximaal 1000 apparaten in de lijst. Klik op **Toewijzen**. Als u meer dan 1000 apparaten wilt registreren, herhaalt u de stappen voor toewijzing totdat aan alle apparaten een inschrijvingsprofiel is toegewezen.

  ![Schermopname van de knop Toewijzen voor het toewijzen van een profiel voor het inschrijvingsprogramma in Intune](media/dep-profile-assignment.png)

## <a name="distribute-devices-to-users"></a>Apparaten onder gebruikers distribueren

U kunt apparaten in bedrijfseigendom nu distribueren aan gebruikers. Wanneer een iOS Apple School Manager-apparaat wordt ingeschakeld, wordt het door Intune ingeschreven voor beheer. Als het apparaat is geactiveerd en gebruikt wordt, kan het profiel kan niet worden toegepast totdat het apparaat wordt ingesteld op de fabrieksinstellingen.
