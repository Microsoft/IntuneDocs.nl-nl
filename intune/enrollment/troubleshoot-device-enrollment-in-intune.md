---
title: Hoe los ik problemen met de inschrijving van apparaten op?
titleSuffix: Microsoft Intune
description: Suggesties voor het oplossen van problemen met het inschrijven van apparaten in Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/09/2018
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6982ba0e-90ff-4fc4-9594-55797e504b62
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: 48ad9ffe32dc7493195ec161e070734776381427
ms.sourcegitcommit: a82d25d98fdf0ba766f8f074871d4f13725e23f9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/31/2019
ms.locfileid: "75547795"
---
# <a name="troubleshoot-device-enrollment-in-microsoft-intune"></a>Problemen bij de apparaatinschrijving in Microsoft Intune oplossen

Dit artikel bevat suggesties voor het oplossen van problemen met de [inschrijving van het apparaat](device-enrollment.md). Zie [Ondersteuning voor Microsoft Intune krijgen](../fundamentals/get-support.md) voor meer manieren om hulp te krijgen als u het probleem niet kunt oplossen met deze informatie.


## <a name="initial-troubleshooting-steps"></a>Eerste stappen om het probleem op te lossen

Voordat u het probleem probeert op te lossen, controleert u of u Intune op de juiste manier hebt geconfigureerd om registratie mogelijk te maken. U kunt meer over deze configuratievereisten lezen in:

- [Bereid u voor op het registreren van apparaten in Microsoft Intune](../fundamentals/setup-steps.md)
- [iOS- en Mac-apparaatbeheer instellen](../ios-enroll.md)
- [Windows apparaatbeheer instellen](windows-enroll.md)
- [Android-apparaatbeheer instellen](android-enroll.md): geen aanvullende stappen vereist

U kunt er ook voor zorgen dat de datum en tijd op het apparaat van de gebruiker juist zijn ingesteld:

1. Start het apparaat opnieuw op.
2. Zorg ervoor dat de datum en tijd zo dicht mogelijk bij de GMT-standaarden (+ of - 12 uur) voor de tijdzone van de eindgebruiker zijn ingesteld.
3. Verwijder de Intune-bedrijfsportal en installeer deze opnieuw (indien van toepassing).

Gebruikers van beheerde apparaten kunnen registratie- en diagnostische gegevens laten vastleggen in logboeken, zodat u deze kunt bekijken. Gebruikersinstructies voor het vastleggen van gegevens in logboeken vindt u in:

- [Android-inschrijvingsfouten verzenden naar de IT-beheerder](https://docs.microsoft.com/intune-user-help/send-enrollment-errors-to-your-it-admin-android)
- [iOS-fouten naar uw IT-beheerder verzenden](https://docs.microsoft.com/intune-user-help/send-errors-to-your-it-admin-ios)


## <a name="general-enrollment-issues"></a>Problemen bij het registreren van apparaten
Deze problemen kunnen optreden op alle apparaatplatforms.

### <a name="device-cap-reached"></a>Apparaatlimiet bereikt
**Probleem:** Een gebruiker ontvangt tijdens de inschrijving een foutbericht, zoals **De bedrijfsportal is tijdelijk niet beschikbaar** en DMPdownloader.log in Configuration Manager bevat de fout **DeviceCapReached**.

**Oplossing:**

#### <a name="check-number-of-devices-enrolled-and-allowed"></a>Controleer het aantal apparaten dat is ingeschreven en dat wordt toegestaan

Voer de volgende stappen uit om te controleren of aan de gebruiker niet meer dan het maximale aantal apparaten is toegewezen:

1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaatinschrijving** > **Inschrijvingsbeperkingen** > **Beperkingen voor apparaatlimieten**. Noteer de waarde in de kolom **Apparaatlimiet**.

2. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Gebruikers** > **Alle gebruikers** > selecteer de gebruiker > **Apparaten**. Noteer het aantal apparaten.

3. Als het aantal ingeschreven apparaten van de gebruiker al gelijk is aan de apparaatlimietbeperking, kunnen er pas meer worden ingeschreven als:
    - [Bestaande apparaten worden verwijderd](../remote-actions/devices-wipe.md) of
    - U de apparaatlimiet verhoogt door [apparaatbeperkingen in te stellen](enrollment-restrictions-set.md).

Om te voorkomen dat apparaatlimieten worden bereikt, moet u ervoor zorgen dat verouderde apparaatrecords worden verwijderd.

> [!NOTE]
> 
> U kunt de limiet voor apparaatinschrijvingen vermijden met behulp van het apparaatinschrijvingsmanageraccount, zoals wordt beschreven in [Apparaten in bedrijfseigendom inschrijven met de apparaatinschrijvingsmanager in Microsoft Intune](device-enrollment-manager-enroll.md).
> 
> Met een gebruikersaccount dat is toegevoegd aan het apparaatinschrijvingsmanageraccount, kunnen geen apparaten worden ingeschreven wanneer beleid voor voorwaardelijke toegang van kracht is voor die specifieke gebruikersaanmelding.

### <a name="company-portal-temporarily-unavailable"></a>Bedrijfsportal is tijdelijk niet beschikbaar
**Probleem:** Gebruikers ontvangen op hun apparaat de fout **Bedrijfsportal tijdelijk niet beschikbaar**.

**Oplossing:**

1. Verwijder de Intune-bedrijfsportal-app van het apparaat.

2. Open de browser op het apparaat, ga naar [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) en meld u aan.

3. Als gebruikers zich niet kunnen aanmelden, vraagt u ze zich bij een ander netwerk aan te melden.

4. Als dat mislukt, controleert u of de referenties van de gebruiker juist zijn gesynchroniseerd met Azure Active Directory.

5. Als de gebruiker zich heeft aangemeld, wordt u op een iOS-apparaat gevraagd om de Intune-bedrijfsportal-app te installeren en het apparaat in te schrijven. Op een Android-apparaat moet u de Intune-bedrijfsportal-app handmatig installeren, waarna u het apparaat opnieuw kunt inschrijven.

### <a name="mdm-authority-not-defined"></a>De MDM-instantie is niet gedefinieerd
**Probleem:** Een gebruiker ontvangt de fout **De MDM-instantie is niet gedefinieerd**.

**Oplossing:**

1. Controleer of de MDM-instantie [op de juiste wijze is ingesteld](../fundamentals/mdm-authority-set.md).
    
2. Controleer of de referenties van de gebruiker juist zijn gesynchroniseerd met Azure Active Directory. U kunt controleren of de UPN van de gebruiker overeenkomt met de Active Directory-gegevens in het Microsoft 365-beheercentrum.
    Als de UPN niet overeenkomt met de Active Directory-gegevens, doet u het volgende:

    1. Schakel DirSync uit op de lokale server.

    2. Verwijder de gebruiker waarvoor geen overeenkomende gegevens zijn gevonden uit de gebruikerslijst van de **Intune-accountportal** .

    3. Wacht ongeveer één uur zodat de onjuiste gegevens door de Azure-service kunnen worden verwijderd.

    4. Schakel DirSync weer in en controleer of de gebruiker nu juist is gesynchroniseerd.

3. Als u gebruikmaakt van Configuration Manager met Intune, controleert u of de gebruiker over een geldige cloudgebruikers-id beschikt:

    1. Open SQL Management Studio.

    2. Maak verbinding met de betreffende database.

    3. Open de databasemap, ga naar de map **CM_DBName** en open deze. Hierbij staat DBName voor de naam van de klantendatabase.

    4. Kies bovenaan **Nieuwe query** en voer de volgende query's uit:

        - Als u alle gebruikers wilt weergeven: `select * from [CM_ DBName].[dbo].[User_DISC]`

        - Als u specifieke gebruikers wilt weergeven, gebruikt u de volgende query waarbij %testuser1% een tijdelijke aanduiding is voor username@domain.com voor de gebruiker die u wilt weergeven: `select * from [CM_ DBName].[dbo].[User_DISC] where User_Principal_Name0 like '%testuser1%'`

        Nadat u de query hebt opgesteld, kiest u **!Execute**.
        Wanneer de resultaten worden weergegeven, zoekt u naar de cloudgebruikers-id.  Als er geen id is gevonden, beschikt de gebruiker niet over een licentie om Intune te gebruiken.

### <a name="unable-to-create-policy-or-enroll-devices-if-the-company-name-contains-special-characters"></a>Kan geen beleid maken of apparaten registreren als de bedrijfsnaam speciale tekens bevat
**Probleem:** U kunt geen beleid maken of apparaten registreren.

**Oplossing:** Verwijder in het [Microsoft 365-beheercentrum](https://admin.microsoft.com/) de speciale tekens uit de bedrijfsnaam en sla de bedrijfsgegevens op.

### <a name="unable-to-sign-in-or-enroll-devices-when-you-have-multiple-verified-domains"></a>U kunt zich niet aanmelden of apparaten registreren wanneer u meerdere geverifieerde domeinen hebt
**Probleem:** Dit probleem kan optreden wanneer u een tweede geverifieerd domein aan de ADFS toevoegt. Gebruikers met het UPN-achtervoegsel (User Principal Name) van het tweede domein kunnen zich mogelijk niet aanmelden bij de portals of apparaten inschrijven.


<strong>Oplossing:</strong> Microsoft Office 365-klanten moeten een afzonderlijke instantie van ADFS 2.0 Federation Service implementeren voor elk achtervoegsel als ze:
- eenmalige aanmelding (SSO) gebruiken via ADFS 2.0, en
- over meerdere domeinen op het hoogste niveau beschikken voor UPN-achtervoegsels van gebruikers in hun organisatie (bijvoorbeeld @contoso.com of @fabrikam.com).


Een [updatepakket voor ADFS 2.0](http://support.microsoft.com/kb/2607496) kan worden gebruikt met de schakeloptie <strong>SupportMultipleDomain</strong> om de ADFS-server in te schakelen voor ondersteuning van dit scenario zonder extra ADFS 2.0-servers. Lees [deze blog](https://blogs.technet.microsoft.com/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/) voor meer informatie.


## <a name="android-issues"></a>Problemen met Android

### <a name="android-enrollment-errors"></a>Inschrijvingsfouten met Android

De volgende tabel bevat fouten die eindgebruikers mogelijk in Intune krijgen te zien tijdens het registreren van een Android-apparaat.

|Foutbericht|Probleem|Oplossing|
|---|---|---|
|**De IT-beheerder moet een licentie toewijzen voor toegang**<br>Uw IT-beheerder heeft u geen toegang verleend om deze app te gebruiken. Neem contact op met uw IT-beheerder of probeer het later opnieuw.|Het apparaat kan niet worden ingeschreven omdat het account van de gebruiker niet de benodigde licentie heeft.|Voordat gebruikers hun apparaat kunnen inschrijven, moet de benodigde licentie aan hen zijn toegewezen. Dit bericht betekent dat de gebruiker het verkeerde licentietype heeft voor de Mobile Device Management-instantie. Ze krijgen deze fout bijvoorbeeld te zien als aan de twee volgende voorwaarden wordt voldaan:<ol><li>Intune is ingesteld als Mobile Device Management-instantie</li><li>De gebruiker gebruikt een System Center 2012 R2 Configuration Manager-licentie.</li></ol>Zie [Intune-licenties toewijzen aan uw gebruikersaccounts](/intune/licenses-assign) voor meer informatie.|
|**De IT-beheerder moet de MDM-instantie instellen**<br>Het lijkt erop dat uw IT-beheerder geen MDM-instantie heeft ingesteld. Neem contact op met uw IT-beheerder of probeer het later opnieuw.|De Mobile Device Management-instantie is niet gedefinieerd.|De Mobile Device Management-instantie is niet ingesteld in Intune. Informatie over het [instellen van de instantie voor het beheer van mobiele apparaten](/intune/mdm-authority-set).|


### <a name="devices-fail-to-check-in-with-the-intune-service-and-display-as-unhealthy-in-the-intune-admin-console"></a>Apparaten kunnen niet inchecken bij de Intune-service en worden in de Intune-beheerconsole weergegeven als Niet in orde
**Probleem:** Sommige Samsung-apparaten met Android-versies 4.4.x en 5.x checken mogelijk niet meer in bij de Intune-service. Als apparaten niet inchecken:

- Kunnen ze geen beleid, apps en externe opdrachten ontvangen van de Intune-service.
- Wordt voor deze apparaten in de beheerconsole de Beheerstatus **Niet in orde** weergegeven.
- Gebruikers die worden beschermd door beleid voor voorwaardelijke toegang hebben mogelijk geen toegang meer tot bedrijfsbronnen.

Samsung Smart Manager-software, die wordt geleverd op sommige Samsung-apparaten, kan de Intune-bedrijfsportal en de onderdelen ervan deactiveren. Wanneer de bedrijfsportal is gedeactiveerd, kan deze niet op de achtergrond worden uitgevoerd en kan deze geen contact maken met de Intune-service.

**Oplossing 1:**

Laat gebruikers de bedrijfsportal-app handmatig starten. Zodra de app opnieuw is gestart, checkt het apparaat in bij de Intune-service.

> [!IMPORTANT]
> Het handmatig openen van de bedrijfsportal-app is een tijdelijke oplossing omdat Samsung Smart Manager de bedrijfsportal-app opnieuw kan deactiveren.

**Oplossing 2:**

Vertel uw gebruikers om een upgrade naar Android 6.0 uit te voeren. Het deactiveringsprobleem komt niet voor op Android 6.0-apparaten. Als u wilt controleren of een update beschikbaar is, gaat u naar **Instellingen** > **Apparaat** > **Updates handmatig downloaden** en volgt u de aanwijzingen op het apparaat.

**Oplossing 3:**

Als oplossing 2 niet werkt, laat u gebruikers de volgende stappen uitvoeren om in Smart Manager de bedrijfsportal-app uit te sluiten:

1. Start de Smart Manager-app op het apparaat.

   ![Het pictogram Smart Manager op het apparaat selecteren](./media/troubleshoot-device-enrollment-in-intune/smart-manager-app-icon.png)

2. Kies de tegel **Batterij**.

   ![De tegel Batterij selecteren](./media/troubleshoot-device-enrollment-in-intune/smart-manager-battery-tile.png)

3. Selecteer onder **App-energiebeheer** of **App-optimalisatie** **Details**.

   ![Details selecteren onder App-energiebeheer App-optimalisatie](./media/troubleshoot-device-enrollment-in-intune/smart-manager-app-power-saving-detail.png)

4. Kies **bedrijfsportal** uit de lijst met apps.

   ![Bedrijfsportal-app selecteren uit de lijst met apps](./media/troubleshoot-device-enrollment-in-intune/smart-manager-company-portal.png)

5. Kies **Uitschakelen**.

   ![Uitschakelen selecteren in het dialoogvenster App-optimalisatie](./media/troubleshoot-device-enrollment-in-intune/smart-manager-app-optimization-turned-off.png)

6. Controleer onder **App-energiebeheer** of **App-optimalisatie** of bedrijfsportal is uitgeschakeld.

   ![Controleren of bedrijfsportal is uitgeschakeld](./media/troubleshoot-device-enrollment-in-intune/smart-manager-verify-comp-portal-turned-off.png)


### <a name="profile-installation-failed"></a>De profielinstallatie is mislukt
**Probleem:** Een gebruiker ontvangt op een Android-apparaat de fout **Profiel is niet geïnstalleerd**.

**Oplossing:**

1. Controleer of er een juiste licentie aan de gebruiker is toegewezen voor de versie van de Intune-service die u gebruikt.

2. Controleer of het apparaat niet al is ingeschreven bij een andere MDM-provider.

3. Controleer of op het apparaat niet al een beheerprofiel is geïnstalleerd.

4. Controleer of Chrome for Android de is zijn en of cookies zijn ingeschakeld.

### <a name="android-certificate-issues"></a>Problemen met Android-certificaten

**Probleem**: Gebruikers ontvangen het volgende bericht op hun apparaat: *U kunt zich niet aanmelden. Er ontbreekt een vereist certificaat voor uw apparaat.*

**Oplossing 1**:

De gebruiker kan wellicht het ontbrekende certificaat ophalen door de instructies in [Er ontbreekt een vereist certificaat voor uw apparaat](/intune-user-help/your-device-is-missing-a-required-certificate-android) te volgen. Als de fout zich blijft voordoen, gaat u naar Oplossing 2.

**Oplossing 2**:

Nadat gebruikers hun zakelijke referenties hebben ingevoerd en zijn omgeleid voor federatieve aanmelding, krijgen ze mogelijk nog steeds het foutbericht voor een ontbrekend certificaat te zien. In dat geval betekent de fout mogelijk dat er een tussencertificaat ontbreekt op uw ADFS-server (Active Directory Federation Services)

De certificaatfout treedt op omdat er voor Android-apparaten tussencertificaten moeten worden opgenomen in een [Hallo van een SSL-server](https://technet.microsoft.com/library/cc783349.aspx). Momenteel verzendt een standaard AD FS-server of WAP - AD FS-proxyserver alleen het AD FS-service SSL-certificaat in de Hallo-reactie van de SSL-server op een Hallo van een SSL-client.

Als u dit probleem wilt oplossen, importeert u als volgt de certificaten in het persoonlijke certificaatarchief op de AD FS-server of proxy’s:

1. Klik op de ADFS- en proxyservers met de rechtermuisknop op **Start** > **Uitvoeren** > **certlm.msc** om Local Machine Certificate Management Console te starten.
2. Vouw de optie **Persoonlijk** uit en kies **Certificaten**.
3. Zoek het certificaat voor uw AD FS-servicecommunicatie (een openbaar ondertekend certificaat) en dubbelklik erop om de eigenschappen weer te geven.
4. Selecteer het tabblad **Certificeringspad** om de bovenliggende certificaten weer te geven.
5. Kies voor elk bovenliggend certificaat de optie **Certificaat weergeven**.
6. Kies **Details** > **Kopiëren naar bestand...** .
7. Volg de aanwijzingen in de wizard om de openbare sleutel van het bovenliggende certificaat te exporteren of op te slaan op de bestandslocatie van uw keuze.
8. Klik met de rechtermuisknop op **Certificaten** > **Alle taken** > **Importeren**.
9. Volg de aanwijzingen van de wizard om de bovenliggende certificaten te importeren in **Lokale computer\Persoonlijk\Certificaten**.
10. Start de AD FS-servers opnieuw op.
11. Herhaal de stappen hierboven op al uw AD FS- en proxyservers.

U kunt het hulpprogramma voor diagnostische gegevens op [https://www.digicert.com/help/](https://www.digicert.com/help/) gebruiken om te controleren of het juiste certificaat is geïnstalleerd. Voer in het vak **Serveradres** de FQDN-naam van uw ADFS-server in (IE: sts.contso.com) en klik op **Server controleren**.

**Valideren dat het certificaat correct is geïnstalleerd**:

In de volgende stappen wordt slechts een van de vele methoden en hulpprogramma's beschreven die u kunt gebruiken om te valideren of het certificaat goed is geïnstalleerd.

1. Ga naar het [gratis hulpprogramma Digicert](ttps://www.digicert.com/help/).
2. Geef de Fully Qualified Domain Name van uw AD FS-server op (bijvoorbeeld sts.contoso.com) en selecteer **SERVER CONTROLEREN**.

Als het servercertificaat goed is geïnstalleerd, worden er allemaal vinkjes weergegeven in de resultaten. Als het bovenstaande probleem bestaat, ziet u in de rapportsecties 'Certificaatnaam komt overeen met' en 'SSL-certificaat is correct geïnstalleerd' een rode X.


## <a name="ios-issues"></a>Problemen met iOS

### <a name="ios-enrollment-errors"></a>iOS-inschrijvingsfouten
De volgende tabel bevat fouten die eindgebruikers mogelijk in Intune krijgen te zien tijdens het registreren van een iOS-apparaat.

|Foutbericht|Probleem|Oplossing|
|-------------|-----|----------|
|NoEnrollmentPolicy|Geen registratiebeleid gevonden|Controleer of alle vereisten voor registratie zijn geconfigureerd, zoals het Apple Push Notification Service-certificaat (APNs) en of iOS als platform is ingeschakeld. Zie [iOS- en Mac-apparaatbeheer instellen](../ios-enroll.md) voor instructies.|
|DeviceCapReached|Er zijn al te veel mobiele apparaten geregistreerd.|De gebruiker moet een van de momenteel geregistreerde mobiele apparaten verwijderen uit de bedrijfsportal voordat een ander mobiel apparaat kan worden geregistreerd. Zie de instructies voor het type apparaat dat u gebruikt: [Android](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-android), [iOS](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-ios) of [Windows](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows).|
|APNSCertificateNotValid|Er is een probleem met het certificaat dat door het mobiele apparaat wordt gebruikt voor communicatie met het netwerk van uw bedrijf.<br /><br />|De Apple Push Notification Service (APNs) biedt een kanaal om contact te maken met ingeschreven iOS-apparaten. De inschrijving zal mislukken en dit bericht zal worden weergegeven als:<ul><li>De stappen voor het ophalen van een APNs-certificaat niet zijn uitgevoerd, of</li><li>Het APNs-certificaat is verlopen.</li></ul>Lees de informatie over het instellen van gebruikers in [Active Directory synchroniseren en gebruikers toevoegen aan Intune](../fundamentals/users-add.md) en [Gebruikers en apparaten organiseren](../fundamentals/groups-add.md).|
|AccountNotOnboarded|Er is een probleem met het certificaat dat door het mobiele apparaat wordt gebruikt voor communicatie met het netwerk van uw bedrijf.<br /><br />|De Apple Push Notification Service (APNs) biedt een kanaal om contact te maken met ingeschreven iOS-apparaten. De inschrijving zal mislukken en dit bericht zal worden weergegeven als:<ul><li>De stappen voor het ophalen van een APNs-certificaat niet zijn uitgevoerd, of</li><li>Het APNs-certificaat is verlopen.</li></ul>Zie [iOS- en Mac-beheer instellen met Microsoft Intune](../ios-enroll.md) voor meer informatie.|
|DeviceTypeNotSupported|Mogelijk heeft de gebruiker geprobeerd een ander apparaat dan een iOS-apparaat te registreren. Het type mobiele apparaat dat u probeert in te schrijven, wordt niet ondersteund.<br /><br />Controleer of iOS-versie 8.0 of hoger op het apparaat wordt uitgevoerd.<br /><br />|Controleer of iOS-versie 8.0 of hoger op het apparaat van de gebruiker wordt uitgevoerd.|
|UserLicenseTypeInvalid|Het apparaat kan niet worden ingeschreven, omdat het account van de gebruiker nog geen lid is van een vereiste gebruikersgroep.<br /><br />|Gebruikers die hun apparaten willen registreren, moeten lid zijn van de juiste gebruikersgroep. Dit bericht betekent dat de gebruiker het verkeerde licentietype heeft voor de Mobile Device Management-instantie. Ze krijgen deze fout bijvoorbeeld te zien als aan de twee volgende voorwaarden wordt voldaan:<ol><li>Intune is ingesteld als de Mobile Device Management-instantie</li><li>De gebruiker gebruikt een System Center 2012 R2 Configuration Manager-licentie.</li></ol>Zie de volgende artikelen voor meer informatie:<br /><br />Zie [iOS- en Mac-beheer instellen met Microsoft Intune](../ios-enroll.md) en informatie over het instellen van gebruikers in [Active Directory synchroniseren en gebruikers toevoegen aan Intune](../fundamentals/users-add.md) en [Gebruikers en apparaten organiseren](../fundamentals/groups-add.md).|
|MdmAuthorityNotDefined|De Mobile Device Management-instantie is niet gedefinieerd.<br /><br />|De Mobile Device Management-instantie is niet ingesteld in Intune.<br /><br />Lees artikel 1 in de sectie 'Stap 6: Mobiele apparaten registreren en een app installeren' in [Aan de slag met een evaluatieversie van Microsoft Intune van 30 dagen](../fundamentals/free-trial-sign-up.md).|

### <a name="devices-are-inactive-or-the-admin-console-cant-communicate-with-them"></a>Apparaten zijn inactief of de beheerconsole kan er niet mee communiceren
**Probleem:** iOS-apparaten checken niet in bij de Intune-service. Apparaten moeten regelmatig worden ingecheckt bij de service om toegang te behouden tot beveiligde bedrijfsresources. Als apparaten niet worden ingecheckt:

- Kunnen ze geen beleid, apps en externe opdrachten ontvangen van de Intune-service.
- Wordt voor deze apparaten in de beheerconsole de Beheerstatus **Niet in orde** weergegeven.
- Gebruikers die worden beschermd door beleid voor voorwaardelijke toegang hebben mogelijk geen toegang meer tot bedrijfsbronnen.

**Oplossing:** Deel de volgende oplossingen met uw eindgebruikers om ervoor te zorgen dat ze weer toegang kunnen verkrijgen tot bedrijfsresources.

Wanneer gebruikers aan de slag gaan met de iOS-bedrijfsportal-app, wordt het gemeld als het apparaat geen contact meer heeft met Intune. Als er wordt gedetecteerd dat er geen contact is, wordt automatisch geprobeerd om te synchroniseren met Intune om opnieuw verbinding te maken. Gebruikers krijgen dan de melding **Er wordt geprobeerd om te synchroniseren...** te zien.

  ![De melding Poging tot synchronisatie...](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_trying_to_sync_notification.png)

Als het synchroniseren lukt, ziet u de melding **De synchronisatie is voltooid** in de iOS-bedrijfsportal-app; deze geeft aan dat de status van uw apparaat in orde is.

  ![De melding De synchronisatie is voltooid](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_sync_successful_notification.png)

Als het synchroniseren mislukt, krijgen gebruikers de melding **Kan niet synchroniseren** te zien in de iOS-bedrijfsportal-app.

  ![De melding Kan niet synchroniseren](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_unable_to_sync_notification.png)

Als gebruikers het probleem willen oplossen, moeten ze de knop **Instellen** selecteren. Deze staat rechts van de melding **Kan niet synchroniseren**. Wanneer gebruikers op de knop Instellen klikken, gaan ze naar het scherm om de bedrijfsportal in te stellen. Hier volgen ze instructies om hun apparaat in te schrijven.

  ![Het scherm Instellen van bedrijfstoegang](./media/troubleshoot-device-enrollment-in-intune/ios_cp_app_company_access_setup.png)

Na het inschrijven krijgen de apparaten weer een goede status en is er weer toegang mee te verkrijgen tot de bedrijfsresources.

### <a name="verify-ws-trust-13-is-enabled"></a>Controleren of WS-Trust 1.3 is ingeschakeld
**Probleem:** iOS-apparaten van het Device Enrollment Program (DEP) kunnen niet worden ingeschreven

Voor het inschrijven van DEP-apparaten met gebruikersaffiniteit moet het WS-Trust 1.3 Username/Mixed-eindpunt zijn ingeschakeld om gebruikerstokens aan te vragen. Dit eindpunt wordt standaard door Active Directory ingeschakeld. U kunt een lijst van ingeschakelde eindpunten ophalen met de PowerShell-cmdlet Get-AdfsEndpoint en vervolgens naar het eindpunt trust/13/UsernameMixed zoeken. Bijvoorbeeld:

      Get-AdfsEndpoint -AddressPath “/adfs/services/trust/13/UsernameMixed”

Zie de [documentatie over Get-AdfsEndpoint](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint) voor meer informatie.

Zie [Aanbevolen procedures voor het beveiligen van Active Directory Federation Services](https://technet.microsoft.com/windows-server-docs/identity/ad-fs/operations/best-practices-securing-ad-fs) voor meer informatie. Doe het volgende om te bepalen of WS-Trust 1.3 Username/Mixed is ingeschakeld in uw provider voor identiteitsfederaties:
- Neem contact op met Microsoft Ondersteuning als u ADFS gebruikt
- Neem contact op met de externe leverancier van identiteiten.


### <a name="profile-installation-failed"></a>De profielinstallatie is mislukt
**Probleem:** Een gebruiker ontvangt op een iOS-apparaat de fout **Profiel is niet geïnstalleerd**.

### <a name="troubleshooting-steps-for-failed-profile-installation"></a>Stappen voor de probleemoplossing bij een mislukte profielinstallatie

1. Controleer of er een juiste licentie aan de gebruiker is toegewezen voor de versie van de Intune-service die u gebruikt.

2. Controleer of het apparaat niet al is ingeschreven bij een andere MDM-provider.

3. Controleer of op het apparaat niet al een beheerprofiel is geïnstalleerd.

4. Ga naar [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) en probeer het gevraagde profiel te installeren.

5. Controleer of Safari for iOS de standaardbrowser is en of cookies zijn ingeschakeld.

### <a name="enrolled-ios-device-doesnt-appear-in-console-when-using-configuration-manager-with-intune"></a>Het geregistreerde iOS-apparaat wordt niet weergegeven in de console wanneer u Configuration Manager met Intune gebruikt
**Probleem:** Een gebruiker registreert zijn of haar iOS-apparaat, maar het apparaat wordt niet weergegeven in de beheerconsole van Configuration Manager. Op het apparaat wordt niet aangegeven dat het is ingeschreven. Mogelijke oorzaken:

- Er is geen communicatie tussen de Microsoft Intune-connector in de Configuration Manager-site en de Intune-service.
- Berichten van de Intune-service worden niet verwerkt met het onderdeel voor gegevensdetectiebeheer (ddm) of het onderdeel voor statusbeheer (statmgr).
- Misschien hebt u het MDM-certificaat gedownload vanuit het ene account en het vervolgens gebruikt in een ander account.


**Oplossing:** Controleer de volgende logboekbestanden op mogelijke fouten:

- dmpdownloader.log
- ddm.log
- statmgr.log

Binnenkort worden voorbeelden toegevoegd met betrekking tot de informatie waarnaar u moet zoeken in deze logboekbestanden.


### <a name="users-ios-device-is-stuck-on-an-enrollment-screen-for-more-than-10-minutes"></a>Het iOS-apparaat van de gebruiker is meer dan 10 minuten vastgelopen op een scherm voor inschrijving

**Probleem**: Een apparaat dat wordt geregistreerd, kan op een van de volgende twee schermen vastlopen:
- In afwachting van definitieve configuratie van 'Microsoft'
- De app voor begeleide toegang is niet beschikbaar. Neem contact op met de beheerder.

Dit probleem kan zich voordoen als:
- Er zich een tijdelijke storing voordoet voor Apple-services, of
- De iOS-inschrijving zo is ingesteld dat VPP-tokens worden gebruikt, zoals wordt weergegeven in de tabel, maar er iets mis is met het VPP-token.

| Inschrijvingsinstellingen | Waarde |
| ---- | ---- |
| Platform | iOS |
| Gebruikersaffiniteit | Inschrijven met gebruikersaffiniteit |
|Verifiëren met de bedrijfsportal in plaats van met de Apple-configuratieassistent | Ja |
| De bedrijfsportal installeren met VPP | Token gebruiken: adres van token |
| De bedrijfsportal uitvoeren in de modus voor één app tot de verificatie | Ja |

**Oplossing**: Als u het probleem wilt oplossen, moet u het volgende doen:
1. Bepalen of er iets mis is met het VPP-token en dit oplossen.
2. Vaststellen welke apparaten zijn geblokkeerd.
3. De betreffende apparaten wissen.
4. Laat de gebruiker de inschrijvingsprocedure opnieuw starten.

#### <a name="determine-if-theres-something-wrong-with-the-vpp-token"></a>Bepalen of er iets mis is met het VPP-token
1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Tokens voor het inschrijvingsprogramma** > tokennaam > **Profielen** > profielnaam > **Beheren** > **Eigenschappen**.
2. Controleer de eigenschappen om na te gaan of een van de volgende fouten optreden:
    - Dit token is verlopen.
    - Dit token is niet opgenomen in de bedrijfsportallicenties.
    - Dit token wordt gebruikt door een andere service.
    - Dit token wordt gebruikt door een andere tenant.
    - Dit token is verwijderd.
3. Los de problemen voor het token op.

#### <a name="identify-which-devices-are-blocked-by-the-vpp-token"></a>Vaststellen welke apparaten zijn geblokkeerd door het VPP-token
1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Tokens voor inschrijvingsprogramma** > tokennaam > **Apparaten**.
2. Filter de kolom **Profielstatus** op **Geblokkeerd**.
3. Noteer de serienummers van alle apparaten die zijn **geblokkeerd**.

#### <a name="remotely-wipe-the-blocked-devices"></a>De geblokkeerde apparaten op afstand wissen
Nadat u de problemen met het VPP-token hebt opgelost, moet u de geblokkeerde apparaten wissen.
1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **Alle apparaten** > **Kolommen** > **Serienummer** > **Toepassen**. 
2. Kies in de lijst **Alle apparaten** elk apparaat dat is geblokkeerd en kies vervolgens **Wissen** > **Ja**.

#### <a name="tell-the-users-to-restart-the-enrollment-process"></a>Laat de gebruikers de inschrijvingsprocedure opnieuw starten
Nadat u de geblokkeerde apparaten hebt gewist, kunt u de gebruikers de inschrijvingsprocedure opnieuw laten starten.

## <a name="macos-issues"></a>problemen met macOS

### <a name="macos-enrollment-errors"></a>macOS-inschrijvingsfouten
**Foutbericht 1:** *Het lijkt erop dat u een virtuele machine gebruikt. Zorg ervoor dat u uw virtuele machine volledig hebt geconfigureerd, inclusief het serienummer en hardwaremodel. Neem contact op met ondersteuning als dit geen virtuele machine is.*  

**Foutbericht 2:** *Er zijn momenteel problemen met het beheer van uw apparaat. Dit probleem kan worden veroorzaakt als u een virtuele machine gebruikt, over een beperkt serienummer beschikt of als dit apparaat al aan iemand anders is toegewezen. Ontdek hoe u deze problemen kunt oplossen of neem contact op met het ondersteuningsteam van uw bedrijf.*

**Probleem:** Dit bericht kan het gevolg zijn van een van de volgende redenen:  
- Een virtuele machine (VM) met macOS is niet correct geconfigureerd  
- U hebt de apparaatbeperkingen ingeschakeld die vereisen dat het apparaat in eigendom moet zijn van het bedrijf of over een geregistreerd serienummer van het apparaat in Intune moet beschikken  
- Het apparaat is al geregistreerd en is nog steeds toegewezen aan iemand anders in Intune  

**Oplossing:** Neem eerst contact op met uw gebruiker om te bepalen welke probleem van invloed is op hun apparaat. Voer vervolgens de meest relevante uit van de volgende oplossingen:

- Als de gebruiker een virtuele machine inschrijft om deze te testen, zorg er dan voor dat deze volledig is geconfigureerd, zodat Intune het serienummer en hardwaremodel kan herkennen. Meer informatie over [het installeren van VM's](macos-enroll.md#enroll-virtual-macos-machines-for-testing) in Intune.
- Als uw organisatie inschrijvingsbeperkingen heeft ingeschakeld die persoonlijke macOS-apparaten blokkeert, moet u handmatig [Voeg het serienummer van het persoonlijke apparaat](corporate-identifiers-add.md#manually-enter-corporate-identifiers) aan Intune toevoegen.  
- Als het apparaat nog steeds aan een andere gebruiker in Intune is toegewezen, heeft de vorige eigenaar de bedrijfsportal-app niet gebruikt voor het verwijderen of herstellen ervan. Het verouderde apparaat uit Intune verwijderen:  

    1. Meld u met uw beheerdersreferenties aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
    2. Kies **Apparaten** > **Alle apparaten**.  
    3. Zoek het apparaat op met het inschrijvingsprobleem. Zoek op apparaatnaam of MAC/HW-adres om uw resultaten te verfijnen.
    4. Selecteer het apparaat > **Verwijderen**. Verwijder alle andere vermeldingen die aan het apparaat zijn gekoppeld.  

## <a name="issues-when-using-configuration-manager-with-intune"></a>Problemen bij het gebruik van Configuration Manager met Intune

### <a name="mobile-devices-disappear"></a>Mobiele apparaten verdwijnen

**Probleem:** Nadat een mobiel apparaat bij Configuration Manager is geregistreerd, verdwijnt het uit de verzameling van mobiele apparaten. Het apparaat heeft echter nog steeds een beheerprofiel en wordt vermeld in CSS Gateway.

**Oplossing:** Dit probleem kan om de volgende reden optreden:

- U gebruikt een aangepaste procedure voor het verwijderen van apparaten die niet lid zijn van een domein, of
- De gebruiker heeft het apparaat uit het abonnement verwijderd.
Als u wilt nagaan door welk gebruikersaccount of proces het apparaat uit de Configuration Manager-console is verwijderd, voert u de volgende stappen uit.

#### <a name="check-how-device-was-removed"></a>Controleer hoe het apparaat is verwijderd

1. Selecteer in de Configuration Manager-beheerconsole **Bewaking** &gt; **Systeemstatus** &gt; **Statusberichtquery's**.

2. Klik met de rechtermuisknop op **Resources van verzamelingsleden die handmatig zijn verwijderd** en selecteer **Berichten weergeven**.

3. Kies een passende tijd/datum of de afgelopen 12 uur.

4. Zoek het betreffende apparaat en bekijk hoe het is verwijderd. In het volgende voorbeeld ziet u dat het apparaat via een onbekende toepassing is verwijderd door het account SCCMInstall.

    ![Schermopname voor diagnose van apparaatverwijdering](./media/troubleshoot-device-enrollment-in-intune/CM_With_Intune_Unknown_App_Deleted_Device.jpg)

5. Controleer of er geen geplande taak, script of ander proces voor Configuration Manager voorkomt waarmee apparaten die niet tot een domein behoren, mobiele apparaten of gerelateerde apparaten, worden gewist.

### <a name="other-ios-enrollment-errors"></a>iOS-registratiefouten

U vindt een lijst met iOS-inschrijvingsfouten in onze documentatie in [Troubleshooting iOS device enrollment problems in Microsoft Intune](https://support.microsoft.com/help/4039809/troubleshooting-ios-device-enrollment-in-intune) (Problemen met iOS-apparaatinschrijving in Microsoft Intune oplossen).

## <a name="pc-issues"></a>Pc-problemen

|Foutbericht|Probleem|Oplossing|
|---|---|---|
|**De IT-beheerder moet een licentie toewijzen voor toegang**<br>Uw IT-beheerder heeft u geen toegang verleend om deze app te gebruiken. Neem contact op met uw IT-beheerder of probeer het later opnieuw.|Het apparaat kan niet worden ingeschreven omdat het account van de gebruiker niet de benodigde licentie heeft.|Voordat gebruikers hun apparaat kunnen inschrijven, moet de benodigde licentie aan hen zijn toegewezen. Dit bericht betekent dat de gebruiker het verkeerde licentietype heeft voor de Mobile Device Management-instantie. Ze krijgen deze fout bijvoorbeeld te zien als aan de twee volgende voorwaarden wordt voldaan: <ol><li>Intune is ingesteld als Mobile Device Management-instantie</li><li>De gebruiker gebruikt een System Center 2012 R2 Configuration Manager-licentie.</li></ol>Zie [Intune-licenties toewijzen aan uw gebruikersaccounts](../fundamentals/licenses-assign.md) voor meer informatie.|

### <a name="the-machine-is-already-enrolled---error-hr-0x8007064c"></a>De computer is al geregistreerd: fout hr 0x8007064c

**Probleem:** De registratie is mislukt met de fout **De computer is al geregistreerd**. In het registratielogboek wordt de fout **hr 0x8007064c** vermeld.

Deze fout kan optreden omdat de computer:

- Eerder is ingeschreven, of
- De gekloonde installatiekopie bevat van een computer die al is ingeschreven.
Het accountcertificaat van het vorige account staat nog op de computer.

**Oplossing:**

1. Voer in het menu **Start** de opdracht **Uitvoeren** -> **MMC** in.
1. Kies **Bestand** > **Modules toevoegen of verwijderen**.
1. Dubbelklik op **Certificaten**, kies **Computeraccount** > **Volgende** en selecteer **Lokale computer**.
1. Dubbelklik op **Certificaten (lokale computer)** en kies **Persoonlijke certificaten**.
1. Zoek het Intune-certificaat dat is uitgegeven door Sc_Online_Issuing en verwijder dit als het aanwezig is.
1. Verwijder de volgende registersleutel als deze bestaat en alle subsleutels: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\OnlineManagement regkey**.
1. Probeer opnieuw in te schrijven.
1. Als de pc nog steeds niet kan worden geregistreerd, zoekt en verwijdert u de volgende sleutel als deze bestaat: **KEY_CLASSES_ROOT\Installer\Products\6985F0077D3EEB44AB6849B5D7913E95**.
1. Probeer opnieuw in te schrijven.

    > [!IMPORTANT]
    > Deze sectie, methode of taak bevat stappen voor het wijzigen van het register. Als u het register onjuist bewerkt, kunnen er echter ernstige problemen optreden. Zorg daarom ervoor dat u deze stappen zorgvuldig uitvoert. Maak voor de zekerheid een back-up van het register voordat u het aanpast. Vervolgens kunt u het register herstellen als er een probleem optreedt.
    > Lees [Een back-up maken van het register en het herstellen in Windows](https://support.microsoft.com/kb/322756) voor meer informatie over het maken en terugzetten een back-up van het register

## <a name="general-enrollment-error-codes"></a>Codes voor algemene registratiefouten

|Foutcode|Mogelijk probleem|Voorgestelde oplossing|
|--------------|--------------------|----------------------------------------|
|0x80CF0437 |De klok op de clientcomputer is niet ingesteld op de juiste tijd.|Zorg ervoor dat de klok en de tijdzone op de clientcomputer zijn ingesteld op de juiste tijd en tijdzone.|
|0x80240438, 0x80CF0438, 0x80CF402C|Er kan geen verbinding worden gemaakt met de Intune-service. Controleer de proxy-instellingen voor de client.|Controleer of Intune de proxyconfiguratie op de clientcomputer ondersteunt. Controleer of de clientcomputer internettoegang heeft.|
|0x80240438, 0x80CF0438|De proxy-instellingen in Internet Explorer en Lokaal systeem zijn niet geconfigureerd.|Er kan geen verbinding worden gemaakt met de Intune-service. Controleer de proxy-instellingen voor de clientcomputer. Controleer of Intune de proxyconfiguratie op de clientcomputer ondersteunt. Controleer of de clientcomputer internettoegang heeft.|
|0x80043001, 0x80CF3001, 0x80043004, 0x80CF3004|Inschrijvingspakket is verouderd.|Download en installeer het huidige clientsoftwarepakket via de beheerwerkruimte.|
|0x80043002, 0x80CF3002|Account is in onderhoudsmodus.|U kunt geen nieuwe clientcomputers inschrijven wanneer het account in onderhoudsmodus is. Meld u aan bij uw account om uw accountinstellingen weer te geven.|
|0x80043003, 0x80CF3003|Account is verwijderd.|Controleer of uw account en abonnement op Intune nog actief zijn. Meld u aan bij uw account om uw accountinstellingen weer te geven.|
|0x80043005, 0x80CF3005|De clientcomputer is buiten gebruik gesteld.|Wacht enkele uren, verwijder oudere versies van de clientsoftware van de computer en voer de installatie van de clientsoftware opnieuw uit.|
|0x80043006, 0x80CF3006|Het maximum aantal toegestane seats voor het account is bereikt.|Uw organisatie moet extra seats aanschaffen voordat u meer clientcomputers bij de service kunt inschrijven.|
|0x80043007, 0x80CF3007|Kan het certificaatbestand niet vinden in dezelfde map als het installatieprogramma.|Pak alle bestanden uit voordat u de installatie start. Wijzig niet de naam van de uitgepakte bestanden en verplaats deze niet: alle bestanden moeten aanwezig zijn in dezelfde map, anders mislukt de installatie.|
|0x8024D015, 0x00240005, 0x80070BC2, 0x80070BC9, 0x80CFD015|De software kan niet worden geïnstalleerd omdat een herstart van de client in behandeling is.|Start de computer opnieuw op en voer de installatie van de clientsoftware opnieuw uit.|
|0x80070032|Een of meer vereisten voor het installeren van de clientsoftware zijn niet gevonden op de clientcomputer.|Zorg ervoor dat alle vereiste updates zijn geïnstalleerd op de clientcomputer en voer de installatie van de clientsoftware opnieuw uit.|
|0x80043008, 0x80CF3008|De Microsoft Online Management Updates-service kan niet worden gestart.|Neem contact op met Microsoft Ondersteuning, zoals wordt beschreven in [Ondersteuning voor Microsoft Intune krijgen](../fundamentals/get-support.md).|
|0x80043009, 0x80CF3009|De clientcomputer is al ingeschreven bij de service.|U moet de clientcomputer buiten gebruik stellen voordat u deze opnieuw in de service kunt inschrijven.|
|0x8004300B, 0x80CF300B|Het installatiepakket voor de clientsoftware kan niet worden uitgevoerd omdat de versie van Windows die op de client wordt uitgevoerd niet wordt ondersteund.|Intune biedt geen ondersteuning voor de versie van Windows die op de clientcomputer wordt uitgevoerd.|
|0xAB2|Windows Installer heeft geen toegang tot de VBScript-runtime voor een aangepaste actie.|Deze fout wordt veroorzaakt door een aangepaste actie die is gebaseerd op DLL-bestanden. Bij het oplossen van problemen met de DLL moet u mogelijk gebruikmaken van de hulpmiddelen die worden beschreven in [KB198038 van Microsoft Ondersteuning: Nuttige hulpprogramma's voor pakket- en implementatieproblemen](https://support.microsoft.com/kb/198038).|
|0x80cf0440|De verbinding met het service-eindpunt is beëindigd.|Het proefaccount of het betaalde account is onderbroken. Maak een nieuw proefaccount of betaald account en schrijf u opnieuw in.|

## <a name="next-steps"></a>Volgende stappen

Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](../fundamentals/get-support.md).
