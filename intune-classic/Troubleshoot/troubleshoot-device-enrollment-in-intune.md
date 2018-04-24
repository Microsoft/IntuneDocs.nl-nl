---
title: Hoe los ik problemen met de inschrijving van apparaten op?
description: Suggesties voor het oplossen van problemen met het inschrijven van apparaten.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 09/15/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6982ba0e-90ff-4fc4-9594-55797e504b62
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4c69dec5903f25b9e7f09f6a20fc35068f3329d4
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="troubleshoot-device-enrollment-in-intune"></a>Problemen bij de apparaatinschrijving oplossen

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Dit onderwerp bevat suggesties voor het oplossen van problemen met de registratie van apparaat. Zie [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md) voor meer manieren om hulp te krijgen als u het probleem niet kunt oplossen met deze informatie.


## <a name="initial-troubleshooting-steps"></a>Eerste stappen om het probleem op te lossen

Voordat u het probleem probeert op te lossen, controleert u of u Intune op de juiste manier hebt geconfigureerd om registratie mogelijk te maken. U kunt meer over deze configuratievereisten lezen in:

-   [Bereid u voor op het registreren van apparaten in Microsoft Intune](/intune-classic/deploy-use/prerequisites-for-enrollment)
-   [iOS- en Mac-apparaatbeheer instellen](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
-   [Windows apparaatbeheer instellen](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune)
-   [Android-apparaatbeheer instellen](/intune-classic/deploy-use/set-up-android-management-with-microsoft-intune): geen aanvullende stappen vereist
-   [Android for Work-apparaatbeheer instellen](/intune-classic/deploy-use/set-up-android-for-work)

U kunt er ook voor zorgen dat de datum en tijd op het apparaat van de gebruiker juist zijn ingesteld:

1. Start het apparaat opnieuw op.
2. Zorg ervoor dat de datum en tijd zo dicht mogelijk zijn ingesteld op de GMT-standaarden (+ of - 12 uur) ten opzichte van de tijdzone van de eindgebruiker.
3. Verwijder de Intune-bedrijfsportal en installeer deze opnieuw (indien van toepassing).

Gebruikers van beheerde apparaten kunnen registratie- en diagnostische gegevens laten vastleggen in logboeken, zodat u deze kunt bekijken. Gebruikersinstructies voor het vastleggen van gegevens in logboeken vindt u in:

- [Android-inschrijvingsfouten verzenden naar de IT-beheerder](https://docs.microsoft.com/intune-user-help/send-enrollment-errors-to-your-it-admin-android)
- [iOS-fouten naar uw IT-beheerder verzenden](https://docs.microsoft.com/intune-user-help/send-errors-to-your-it-admin-ios)


## <a name="general-enrollment-issues"></a>Problemen bij het registreren van apparaten
Deze problemen kunnen optreden op alle apparaatplatforms.

### <a name="device-cap-reached"></a>Apparaatlimiet bereikt
**Probleem:** een gebruiker ontvangt tijdens de registratie een foutbericht op het apparaat, zoals het foutbericht **De bedrijfsportal is tijdelijk niet beschikbaar** op een iOS-apparaat, en DMPdownloader.log in Configuration Manager bevat de fout **DeviceCapReached**.

**Oplossing:**

#### <a name="check-number-of-devices-enrolled-and-allowed"></a>Controleer het aantal apparaten dat is ingeschreven en dat wordt toegestaan

1.  Controleer in de Intune-beheerportal of er niet meer dan het toegestane maximum van 15 apparaten aan de gebruiker zijn toegewezen.

2.  Controleer in de Intune-beheerconsole onder **Admin** > **Mobile Device Management** > **Inschrijvingsregels** of de limiet voor de apparaatinschrijving is ingesteld op 15.

<!--- Mobile device users can delete devices at the following URL: [https://byodtestservice.azurewebsites.net/](https://byodtestservice.azurewebsites.net/). --->

Beheerders kunnen apparaten verwijderen in de Azure Active Directory-portal.

#### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>U kunt als volgt apparaten verwijderen in de Azure Active Directory-portal:

1.  Ga naar [http://aka.ms/accessaad](http://aka.ms/accessaad) of kies **Beheer** &gt; **Azure AD** vanaf [https://portal.office.com](https://portal.office.com).

2.  Meld u aan met uw organisatie-id via de koppeling aan de linkerkant van de pagina.

3.  Als u er nog geen hebt, maakt u een Azure-abonnement aan door de abonnementskoppeling **Uw gratis Azure Active Directory registreren** te selecteren. Als u een betaalde account hebt, is hiervoor geen creditcard of betaling nodig.

4.  Selecteer **Active Directory** en vervolgens uw organisatie.

5.  Selecteer het tabblad **Gebruikers** .

6.  Selecteer de gebruiker waarvoor u de apparaten wilt verwijderen.

7.  Kies **Apparaten**.

8.  Verwijder waar nodig apparaten, zoals apparaten die niet langer in gebruik zijn of die onjuist zijn gedefinieerd.

> [!NOTE]
> 
> U kunt de limiet voor apparaatinschrijvingen vermijden met behulp van het apparaatinschrijvingsmanageraccount, zoals wordt beschreven in [Apparaten in bedrijfseigendom inschrijven met de apparaatinschrijvingsmanager in Microsoft Intune](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
> 
> Met een gebruikersaccount dat is toegevoegd aan het apparaatinschrijvingsmanageraccount, kunnen geen apparaten worden ingeschreven wanneer beleid voor voorwaardelijke toegang van kracht is voor die specifieke gebruikersaanmelding.

### <a name="company-portal-temporarily-unavailable"></a>Bedrijfsportal is tijdelijk niet beschikbaar
**Probleem:** gebruikers ontvangen op hun apparaat de fout **Bedrijfsportal tijdelijk niet beschikbaar**.

**Oplossing:**

1.  Verwijder de Intune-bedrijfsportal-app van het apparaat.

2.  Open de browser op het apparaat, ga naar [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) en meld u aan.

3.  Als de gebruiker zich niet kan aanmelden, vraagt u deze om zich bij een ander netwerk aan te melden.

4.  Als dat mislukt, controleert u of de referenties van de gebruiker juist zijn gesynchroniseerd met Azure Active Directory.

5.  Als de gebruiker zich heeft aangemeld, wordt u op een iOS-apparaat gevraagd om de Intune-bedrijfsportal-app te installeren en het apparaat in te schrijven. Op een Android-apparaat moet u de Intune-bedrijfsportal-app handmatig installeren, waarna u het apparaat opnieuw kunt inschrijven.

### <a name="mdm-authority-not-defined"></a>De MDM-instantie is niet gedefinieerd
**Probleem:** een gebruiker ontvangt de fout **De MDM-instantie is niet gedefinieerd**.

**Oplossing:**

1.  Controleer of de MDM-instantie juist is ingesteld voor het type Intune-service dat u gebruikt (dat wil zeggen Intune, Office 365 of System Center Configuration Manager met Intune). Voor Intune wordt de MDM-instantie ingesteld in **Beheer** &gt; **Mobile Device Management**. Voor Configuration Manager met Intune stelt u deze in wanneer u de Intune-connector configureert. In Office 365 is het een instelling in **Mobiele apparaten**.

    > [!NOTE]    
    > In Configuration Manager versie 1610 of hoger en Microsoft Intune versie 1705 kunt u de MDM-instantie wijzigen zonder dat u contact hoeft op te nemen met Microsoft Ondersteuning en zonder dat u de registratie van bestaande beheerde apparaten ongedaan hoeft te maken om ze vervolgens opnieuw te registreren. Zie [Wat te doen als u de verkeerde instelling kiest voor de MDM-instantie](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting) voor meer informatie.

2.  Controleer of de referenties van de gebruiker juist zijn gesynchroniseerd met Azure Active Directory door te controleren of de UPN van de gebruiker overeenkomt met de Active Directory-gegevens in de Office 365-portal.
    Doe het volgende als de UPN niet overeenkomt met de Active Directory-gegevens:

    1.  Schakel DirSync uit op de lokale server.

    2.  Verwijder de gebruiker waarvoor geen overeenkomende gegevens zijn gevonden uit de gebruikerslijst van de **Intune-accountportal** .

    3.  Wacht ongeveer één uur zodat de onjuiste gegevens door de Azure-service kunnen worden verwijderd.

    4.  Schakel DirSync weer in en controleer of de gebruiker nu juist is gesynchroniseerd.

3.  Als u gebruikmaakt van System Center Configuration Manager met Intune, controleert u of de gebruiker over een geldige cloudgebruikers-id beschikt:

    1.  Open SQL Management Studio.

    2.  Maak verbinding met de betreffende database.

    3.  Open de databasemap, ga naar de map **CM_DBName** en open deze. Hierbij staat DBName voor de naam van de klantendatabase.

    4.  Kies bovenaan **Nieuwe query** en voer de volgende query's uit:

        -   Als u alle gebruikers wilt weergeven: `select * from [CM_ DBName].[dbo].[User_DISC]`

        -   Als u specifieke gebruikers wilt weergeven, gebruikt u de volgende query waarbij %testuser1% staat voor username@domain.com voor de gebruiker die u wilt weergeven: `select * from [CM_ DBName].[dbo].[User_DISC] where User_Principal_Name0 like '%testuser1%'`

        Nadat u de query hebt opgesteld, kiest u **!Execute**.
        Wanneer de resultaten worden weergegeven, zoekt u naar de cloudgebruikers-id.  Als er geen id is gevonden, beschikt de gebruiker niet over een licentie om Intune te gebruiken.

### <a name="unable-to-create-policy-or-enroll-devices-if-the-company-name-contains-special-characters"></a>Kan geen beleid maken of apparaten registreren als de bedrijfsnaam speciale tekens bevat
**Probleem:** u kunt geen beleid maken of apparaten registreren.

**Oplossing:** verwijder in het [Office 365-beheercentrum](https://portal.office.com/) de speciale tekens uit de bedrijfsnaam en sla de bedrijfsgegevens op.

### <a name="unable-to-log-in-or-enroll-devices-when-you-have-multiple-verified-domains"></a>U kunt zich niet aanmelden of apparaten registreren wanneer u meerdere geverifieerde domeinen hebt
**Probleem:** als u een tweede geverifieerd domein toevoegt aan uw ADFS, kunnen gebruikers met het UPN-achtervoegsel (User Principal Name) van het tweede domein zich mogelijk niet aanmelden bij de portals of kunnen ze geen apparaten registreren.


<strong>Oplossing:</strong> Microsoft Office 365-klanten die gebruikmaken van eenmalige aanmelding (SSO) via AD FS 2.0 en meerdere domeinen op het hoogste niveau hebben voor UPN-achtervoegsels van gebruikers in hun organisatie (bijvoorbeeld @contoso.com of @fabrikam.com), moeten voor elk achtervoegsel een afzonderlijk exemplaar van AD FS 2.0 Federation Service implementeren. Er is nu een [updatepakket voor AD FS 2.0](http://support.microsoft.com/kb/2607496) dat kan worden gebruikt met de schakeloptie <strong>SupportMultipleDomain</strong> om de AD FS-server in te schakelen voor ondersteuning van dit scenario zonder extra AD FS 2.0-servers. Lees [deze blog](https://blogs.technet.microsoft.com/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/) voor meer informatie.


## <a name="android-issues"></a>Problemen met Android

### <a name="android-enrollment-errors"></a>Inschrijvingsfouten met Android

De volgende tabel bevat fouten die eindgebruikers mogelijk in Intune krijgen te zien tijdens het registreren van een Android-apparaat.

|Foutbericht|Probleem|Oplossing|
|---|---|---|
|**De IT-beheerder moet een licentie toewijzen voor toegang**<br>Uw IT-beheerder heeft u geen toegang gegeven voor het gebruik van deze app. Neem contact op met uw IT-beheerder of probeer het later opnieuw.|Het apparaat kan niet worden ingeschreven omdat het gebruikersaccount de benodigde licentie niet heeft.|Voordat gebruikers hun apparaat kunnen inschrijven, moet de benodigde licentie aan hen zijn toegewezen. Dit bericht betekent dat de gebruiker het verkeerde licentietype heeft voor de aangewezen Mobile Device Management-instantie. Als Intune bijvoorbeeld is aangewezen als de instantie om mobiele apparaten te beheren, maar er een licentie voor System Center 2012 R2 Configuration Manager wordt gebruikt, zien gebruikers deze fout.<br><br>Zie [Intune-licenties toewijzen aan uw gebruikersaccounts](/intune/licenses-assign) voor meer informatie.
|**De IT-beheerder moet de MDM-instantie instellen**<br>Het lijkt erop dat uw IT-beheerder geen MDM-instantie heeft ingesteld. Neem contact op met uw IT-beheerder of probeer het later opnieuw.|De Mobile Device Management-instantie is niet gedefinieerd in Intune.|De Mobile Device Management-instantie is niet aangewezen in Intune. Informatie over het [instellen van de instantie voor het beheer van mobiele apparaten](/intune/mdm-authority-set).|


### <a name="devices-fail-to-check-in-with-the-intune-service-and-display-as-unhealthy-in-the-intune-admin-console"></a>Apparaten kunnen niet inchecken bij de Intune-service en worden in de Intune-beheerconsole weergegeven als Niet in orde
**Probleem:** sommige Samsung-apparaten met Android-versies 4.4.x en 5.x checken mogelijk niet meer in bij de Intune-service. Als apparaten niet inchecken:

- Kunnen ze geen beleid, apps en externe opdrachten ontvangen van de Intune-service.
- Wordt voor deze apparaten in de beheerconsole de Beheerstatus **Niet in orde** weergegeven.
- Gebruikers die worden beschermd door beleid voor voorwaardelijke toegang hebben mogelijk geen toegang meer tot bedrijfsbronnen.

Samsung heeft bevestigd dat de Samsung Smart Manager-software, die wordt geleverd op sommige Samsung-apparaten, de Intune bedrijfsportal en de bijbehorende onderdelen kan deactiveren. Wanneer de bedrijfsportal is gedeactiveerd, kan deze niet op de achtergrond worden uitgevoerd en kan deze geen contact maken met de Intune-service.

**Oplossing 1:**

Laat gebruikers de bedrijfsportal-app handmatig starten. Zodra de app opnieuw is gestart, checkt het apparaat in bij de Intune-service.

> [!IMPORTANT]
> Het handmatig openen van de bedrijfsportal-app is een tijdelijke oplossing omdat Samsung Smart Manager de bedrijfsportal-app opnieuw kan deactiveren.

**Oplossing 2:**

Vertel uw gebruikers om een upgrade naar Android 6.0 uit te voeren. Het deactiveringsprobleem komt niet voor op Android 6.0-apparaten. Als gebruikers willen controleren of een update beschikbaar is, gaan deze naar **Instellingen** > **Apparaat** > **Updates handmatig downloaden** en volgen ze de aanwijzingen op het apparaat.

**Oplossing 3:**

Als oplossing 2 niet werkt, laat u gebruikers de volgende stappen uitvoeren om in Smart Manager de bedrijfsportal-app uit te sluiten:

1. Start de Smart Manager-app op het apparaat.

   ![Het pictogram Smart Manager op het apparaat selecteren](./media/smart-manager-app-icon.png)

2. Kies de tegel **Batterij**.

   ![De tegel Batterij selecteren](./media/smart-manager-battery-tile.png)

3. Selecteer onder **App-energiebeheer** of **App-optimalisatie** **Details**.

   ![Details selecteren onder App-energiebeheer App-optimalisatie](./media/smart-manager-app-power-saving-detail.png)

4. Kies **bedrijfsportal** uit de lijst met apps.

   ![Bedrijfsportal-app selecteren uit de lijst met apps](./media/smart-manager-company-portal.png)

5. Kies **Uitschakelen**.

   ![Uitschakelen selecteren in het dialoogvenster App-optimalisatie](./media/smart-manager-app-optimization-turned-off.png)

6. Controleer onder **App-energiebeheer** of **App-optimalisatie** of bedrijfsportal is uitgeschakeld.

   ![Controleren of bedrijfsportal is uitgeschakeld](./media/smart-manager-verify-comp-portal-turned-off.png)


### <a name="profile-installation-failed"></a>De profielinstallatie is mislukt
**Probleem:** een gebruiker ontvangt op een Android-apparaat de fout **Profiel is niet geïnstalleerd**.

**Oplossing:**

1.  Controleer of er een juiste licentie aan de gebruiker is toegewezen voor de versie van de Intune-service die u gebruikt.

2.  Controleer of het apparaat niet al is ingeschreven met een andere MDM-provider of dat er voor het apparaat niet al een beheerprofiel is geïnstalleerd.

3.  Controleer of Chrome for Android de is zijn en of cookies zijn ingeschakeld.

### <a name="android-certificate-issues"></a>Problemen met Android-certificaten

**Probleem**: gebruikers ontvangen het volgende bericht op een apparaat: *U kunt u niet aanmelden omdat een vereist certificaat ontbreekt op het apparaat.*

**Oplossing 1**:

De gebruiker kan wellicht het ontbrekende certificaat ophalen door de instructies in [Er ontbreekt een vereist certificaat voor uw apparaat](/intune-user-help/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) te volgen. Als de fout zich blijft voordoen, gaat u naar Oplossing 2.

**Oplossing 2**:

Als gebruikers nog steeds de fout voor het ontbrekende certificaat te zien krijgen nadat ze hun bedrijfsreferenties hebben ingevoerd en worden omgeleid voor federatieve aanmelding, is het mogelijk dat er een tussencertificaat op uw AD FS-server (Active Directory Federation Services) ontbreekt.

De certificaatfout treedt op omdat er voor Android-apparaten tussencertificaten moeten worden opgenomen in een [Hallo van een SSL-server](https://technet.microsoft.com/library/cc783349.aspx). Momenteel verzendt een standaard AD FS-server of WAP - AD FS-proxyserver alleen het AD FS-service SSL-certificaat in de Hallo-reactie van de SSL-server op een Hallo van een SSL-client.

Als u dit probleem wilt oplossen, importeert u als volgt de certificaten in het persoonlijke certificaatarchief op de AD FS-server of proxy’s:

1.  Klik op de ADFS- en proxyservers met de rechtermuisknop op **Start** > **Uitvoeren** > **certlm.msc**. Daarmee wordt de beheerconsole van het certificaatarchief van de lokale machine gestart.
2.  Vouw de optie **Persoonlijk** uit en kies **Certificaten**.
3.  Zoek het certificaat voor uw AD FS-servicecommunicatie (een openbaar ondertekend certificaat) en dubbelklik erop om de eigenschappen weer te geven.
4.  Selecteer het tabblad **Certificeringspad** om de bovenliggende certificaten weer te geven.
5.  Kies voor elk bovenliggend certificaat de optie **Certificaat weergeven**.
6.  Selecteer het tabblad **Details** > **Kopiëren naar bestand...**.
7.  Volg de aanwijzingen in de wizard om de openbare sleutel van het bovenliggende certificaat te exporteren of op te slaan in de gewenste bestandslocatie.
8.  Klik met de rechtermuisknop op **Certificaten** > **Alle taken** > **Importeren**.
9.  Volg de aanwijzingen van de wizard om de bovenliggende certificaten te importeren in **Lokale computer\Persoonlijk\Certificaten**.
10. Start de AD FS-servers opnieuw op.
11. Herhaal de stappen hierboven op al uw AD FS- en proxyservers.

U kunt het hulpprogramma voor diagnostische gegevens op [https://www.digicert.com/help/](https://www.digicert.com/help/) gebruiken om te controleren of het juiste certificaat is geïnstalleerd. Voer in het vak **Serveradres** de FQDN-naam van uw ADFS-server in (IE: sts.contso.com) en klik op **Server controleren**.

**Valideren dat het certificaat correct is geïnstalleerd**:

In de volgende stappen wordt slechts een van de vele methoden en hulpprogramma's beschreven die u kunt gebruiken om te valideren of het certificaat goed is geïnstalleerd.

1. Ga naar het [gratis hulpprogramma Digicert](ttps://www.digicert.com/help/).
2. Geef de Fully Qualified Domain Name van uw AD FS-server op (bijvoorbeeld sts.contoso.com) en selecteer **SERVER CONTROLERENSERVER**.

Als het servercertificaat goed is geïnstalleerd, worden er allemaal vinkjes weergegeven in de resultaten. Als het bovenstaande probleem bestaat, ziet u in de rapportsecties 'Certificaatnaam komt overeen met' en 'SSL-certificaat is correct geïnstalleerd' een rode X.


## <a name="ios-issues"></a>Problemen met iOS

### <a name="ios-enrollment-errors"></a>iOS-inschrijvingsfouten
De volgende tabel bevat fouten die eindgebruikers mogelijk in Intune krijgen te zien tijdens het registreren van een iOS-apparaat.

|Foutbericht|Probleem|Oplossing|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|NoEnrollmentPolicy|Geen registratiebeleid gevonden|Controleer of alle vereisten voor registratie zijn geconfigureerd, zoals het Apple Push Notification Service-certificaat (APNs) en of iOS als platform is ingeschakeld. Zie [iOS- en Mac-apparaatbeheer instellen](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) voor instructies.|
|DeviceCapReached|Er zijn al te veel mobiele apparaten geregistreerd.|De gebruiker moet een van zijn momenteel geregistreerd mobiele apparaten verwijderen uit de bedrijfsportal voordat hij een ander mobiel apparaat kan registreren. Zie de instructies voor het type apparaat dat u gebruikt: [Android](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-android), [iOS](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-ios), [Windows](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows).|
|APNSCertificateNotValid|Er is een probleem met het certificaat dat door het mobiele apparaat wordt gebruikt voor communicatie met het netwerk van uw bedrijf.<br /><br />|De Apple Push Notification Service (APNs) biedt een kanaal om ingeschreven iOS-apparaten te bereiken. Als de stappen om een APNs-certificaat te verkrijgen, niet zijn uitgevoerd of als het APNs-certificaat is verlopen, mislukken pogingen tot registratie en wordt dit bericht weergegeven.<br /><br />Lees de informatie over het instellen van gebruikers in [Active Directory synchroniseren en gebruikers toevoegen aan Intune](/intune/users-permissions-add) en [Gebruikers en apparaten organiseren](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|AccountNotOnboarded|Er is een probleem met het certificaat dat door het mobiele apparaat wordt gebruikt voor communicatie met het netwerk van uw bedrijf.<br /><br />|De Apple Push Notification Service (APNs) biedt een kanaal om ingeschreven iOS-apparaten te bereiken. Als de stappen om een APNs-certificaat te verkrijgen, niet zijn uitgevoerd of als het APNs-certificaat is verlopen, mislukken pogingen tot registratie en wordt dit bericht weergegeven.<br /><br />Zie [iOS- en Mac-beheer instellen met Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) voor meer informatie.|
|DeviceTypeNotSupported|Mogelijk heeft de gebruiker geprobeerd een ander apparaat dan een iOS-apparaat te registreren. Het type mobiele apparaat dat u probeert te registreren, wordt niet ondersteund.<br /><br />Controleer of iOS-versie 8.0 of hoger op het apparaat wordt uitgevoerd.<br /><br />|Controleer of iOS-versie 8.0 of hoger op het apparaat van de gebruiker wordt uitgevoerd.|
|UserLicenseTypeInvalid|Het apparaat kan niet worden geregistreerd, omdat het account van de gebruiker nog geen lid is van een vereiste gebruikersgroep.<br /><br />|Gebruikers die hun apparaten willen registreren, moeten lid zijn van de juiste gebruikersgroep. Dit bericht betekent dat de gebruiker het verkeerde licentietype heeft voor de aangewezen Mobile Device Management-instantie. Als Intune bijvoorbeeld is aangewezen als de instantie om mobiele apparaten te beheren, maar er een licentie voor System Center 2012 R2 Configuration Manager wordt gebruikt, zien gebruikers deze fout.<br /><br />Controleer het volgende voor meer informatie:<br /><br />Zie [iOS- en Mac-beheer instellen met Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) en informatie over het instellen van gebruikers in [Active Directory synchroniseren en gebruikers toevoegen aan Intune](/intune/users-permissions-add) en [Gebruikers en apparaten organiseren](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|MdmAuthorityNotDefined|De Mobile Device Management-instantie is niet gedefinieerd in Intune.<br /><br />|De Mobile Device Management-instantie is niet aangewezen in Intune.<br /><br />Lees artikel 1 in de sectie 'Stap 6: mobiele apparaten registreren en een app installeren' in [Aan de slag met een evaluatieversie van Microsoft Intune van 30 dagen](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune).|

### <a name="devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Apparaten zijn inactief of de beheerconsole kan er niet mee communiceren
**Probleem:** iOS-apparaten checken niet in bij de Intune-service. Apparaten moeten regelmatig worden ingecheckt bij de service om toegang te behouden tot beveiligde bedrijfsresources. Als apparaten niet worden ingecheckt:

- Kunnen ze geen beleid, apps en externe opdrachten ontvangen van de Intune-service.
- Wordt voor deze apparaten in de beheerconsole de Beheerstatus **Niet in orde** weergegeven.
- Gebruikers die worden beschermd door beleid voor voorwaardelijke toegang hebben mogelijk geen toegang meer tot bedrijfsbronnen.

**Oplossing:** deel de volgende oplossingen met uw eindgebruikers om ervoor te zorgen dat ze weer toegang kunnen verkrijgen tot bedrijfsresources.

Wanneer gebruikers aan de slag gaan met de iOS-bedrijfsportal-app, wordt het gemeld als het apparaat geen contact meer heeft met Intune. Als er wordt gedetecteerd dat er geen contact is, wordt automatisch geprobeerd om te synchroniseren met Intune om opnieuw verbinding te maken. Gebruikers krijgen dan de melding **Poging tot synchronisatie...** te zien.

  ![De melding Poging tot synchronisatie...](./media/ios_cp_app_trying_to_sync_notification.png)

Als het synchroniseren lukt, ziet u de melding **De synchronisatie is voltooid** in de iOS-bedrijfsportal-app; deze geeft aan dat de status van uw apparaat in orde is.

  ![De melding De synchronisatie is voltooid](./media/ios_cp_app_sync_successful_notification.png)

Als het synchroniseren mislukt, krijgen gebruikers de melding **Kan niet synchroniseren** te zien in de iOS-bedrijfsportal-app.

  ![De melding Kan niet synchroniseren](./media/ios_cp_app_unable_to_sync_notification.png)

Als gebruikers het probleem willen oplossen, moeten ze de knop **Instellen** selecteren. Deze staat rechts van de melding **Kan niet synchroniseren**. Wanneer gebruikers op de knop Instellen klikken, gaan ze naar het scherm om de bedrijfsportal in te stellen. Hier volgen ze instructies om hun apparaat in te schrijven.

  ![Het scherm Instellen van bedrijfstoegang](./media/ios_cp_app_company_access_setup.png)

Na het inschrijven krijgen de apparaten weer een goede status en is er weer toegang mee te verkrijgen tot de bedrijfsresources.

### <a name="verify-ws-trust-13-is-enabled"></a>Controleren of WS-Trust 1.3 is ingeschakeld
**Probleem** iOS-apparaten van het Device Enrollment Program (DEP) kunnen niet worden ingeschreven

Voor de inschrijving van DEP-apparaten met gebruikersaffiniteit moet de gebruikersnaam/het gemengde eindpunt voor WS-Trust 1.3 zijn ingeschakeld zodat gebruikerstokens kunnen worden aangevraagd. Dit eindpunt wordt standaard door Active Directory ingeschakeld. U kunt een lijst van ingeschakelde eindpunten ophalen met PowerShell-cmdlet Get-AdfsEndpoint en vervolgens naar het eindpunt trust/13/UsernameMixed zoeken. Bijvoorbeeld:

      Get-AdfsEndpoint -AddressPath “/adfs/services/trust/13/UsernameMixed”

Zie de [documentatie over Get-AdfsEndpoint](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint) voor meer informatie.

Zie [Aanbevolen procedures voor het beveiligen van Active Directory Federation Services](https://technet.microsoft.com/windows-server-docs/identity/ad-fs/operations/best-practices-securing-ad-fs) voor meer informatie. Als u extra hulp nodig hebt om te bepalen of de gebruikersnaam/het gemengde eindpunt voor WS-Trust 1.3 is ingeschakeld bij uw provider voor identiteitsfederaties, neemt u contact op met Microsoft Ondersteuning als u gebruikmaakt van AD FS of met uw externe identiteitsleverancier.


### <a name="profile-installation-failed"></a>De profielinstallatie is mislukt
**Probleem:** een gebruiker ontvangt op een iOS-apparaat de fout **Profiel is niet geïnstalleerd**.

### <a name="troubleshooting-steps-for-failed-profile-installation"></a>Stappen voor de probleemoplossing bij een mislukte profielinstallatie

1.  Controleer of er een juiste licentie aan de gebruiker is toegewezen voor de versie van de Intune-service die u gebruikt.

2.  Controleer of het apparaat niet al is ingeschreven met een andere MDM-provider of dat er voor het apparaat niet al een beheerprofiel is geïnstalleerd.

3.  Ga naar [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) en probeer het gevraagde profiel te installeren.

4.  Controleer of Safari for iOS de standaardbrowser is en of cookies zijn ingeschakeld.

### <a name="enrolled-ios-device-doesnt-appear-in-console-when-using-system-center-configuration-manager-with-intune"></a>Het geregistreerde iOS-apparaat wordt niet weergegeven in de console wanneer u System Center Configuration Manager met Intune gebruikt
**Probleem:** een gebruiker registreert zijn of haar iOS-apparaat, maar het apparaat wordt niet weergegeven in de beheerconsole van Configuration Manager. Op het apparaat wordt niet aangegeven dat het is geregistreerd. Mogelijke oorzaken:

- Er is geen communicatie tussen de Microsoft Intune-connector in de Configuration Manager-site en de Intune-service.
- Berichten van de Intune-service worden niet verwerkt met het onderdeel voor beheer van gegevensdetectie (ddm) of het onderdeel voor statusbeheer (statmgr).
- Misschien hebt u het MDM-certificaat gedownload vanuit het ene account en het vervolgens gebruikt in een ander account.


**Oplossing:** Controleer de volgende logboekbestanden voor mogelijke fouten:

- dmpdownloader.log
- ddm.log
- statmgr.log

Binnenkort worden voorbeelden toegevoegd met betrekking tot de informatie waarnaar u moet zoeken in deze logboekbestanden.


## <a name="issues-when-using-system-center-configuration-manager-with-intune"></a>Problemen bij het gebruik van System Center Configuration Manager met Intune
### <a name="mobile-devices-disappear"></a>Mobiele apparaten verdwijnen
**Probleem:** nadat een mobiel apparaat bij Configuration Manager is ingeschreven, verdwijnt het uit de verzameling van mobiele apparaten, maar het apparaat heeft nog steeds een beheerprofiel en wordt vermeld in CSS Gateway.

**Oplossing:** dit probleem kan optreden omdat er een aangepast proces actief is dat apparaten verwijdert die niet aan een domein zijn toegevoegd, of omdat de gebruiker het apparaat uit het abonnement heeft verwijderd. Als u wilt nagaan door welk gebruikersaccount of proces het apparaat uit de Configuration Manager-console is verwijderd, voert u de volgende stappen uit.

#### <a name="check-how-device-was-removed"></a>Controleer hoe het apparaat is verwijderd

1.  Selecteer in de Configuration Manager-beheerconsole **Bewaking** &gt; **Systeemstatus** &gt; **Statusberichtquery's**.

2.  Klik met de rechtermuisknop op **Resources van verzamelingsleden die handmatig zijn verwijderd** en selecteer **Berichten weergeven**.

3.  Kies een passende tijd/datum of de afgelopen 12 uur.

4.  Zoek het betreffende apparaat en bekijk hoe het is verwijderd. In het volgende voorbeeld ziet u dat het apparaat via een onbekende toepassing is verwijderd door het account SCCMInstall.

    ![Schermopname voor diagnose van apparaatverwijdering](./media/CM_With_Intune_Unknown_App_Deleted_Device.jpg)

5.  Controleer of er geen geplande taak, script of ander proces voor Configuration Manager voorkomt waarmee apparaten die niet tot een domein behoren, mobiele apparaten of gerelateerde apparaten worden gewist.




### <a name="other-ios-enrollment-errors"></a>iOS-registratiefouten
U vindt een lijst met iOS-inschrijvingsfouten in onze documentatie in [Troubleshooting iOS device enrollment problems in Microsoft Intune](https://support.microsoft.com/help/4039809/troubleshooting-ios-device-enrollment-in-intune) (Problemen met iOS-apparaatinschrijving in Microsoft Intune oplossen).

## <a name="pc-issues"></a>Pc-problemen


|Foutbericht|Probleem|Oplossing|
|---|---|---|
|**De IT-beheerder moet een licentie toewijzen voor toegang**<br>Uw IT-beheerder heeft u geen toegang gegeven voor het gebruik van deze app. Neem contact op met uw IT-beheerder of probeer het later opnieuw.|Het apparaat kan niet worden ingeschreven omdat het gebruikersaccount de benodigde licentie niet heeft.|Voordat gebruikers hun apparaat kunnen inschrijven, moet de benodigde licentie aan hen zijn toegewezen. Dit bericht betekent dat de gebruiker het verkeerde licentietype heeft voor de aangewezen Mobile Device Management-instantie. Als Intune bijvoorbeeld is aangewezen als de instantie om mobiele apparaten te beheren, maar er een licentie voor System Center 2012 R2 Configuration Manager wordt gebruikt, zien gebruikers deze fout.<br>Zie [Intune-licenties toewijzen aan uw gebruikersaccounts](https://docs.microsoft.com/intune/licenses-assign) voor meer informatie.|



### <a name="the-machine-is-already-enrolled---error-hr-0x8007064c"></a>De computer is al geregistreerd: fout hr 0x8007064c
**Probleem:** de registratie is mislukt met de fout **De computer is al geregistreerd**. In het registratielogboek wordt de fout **hr 0x8007064c** vermeld.

Dit komt mogelijk doordat de computer eerder is geregistreerd of een gekloonde installatiekopie bevat van een computer die is geregistreerd. Het accountcertificaat van het vorige account staat nog op de computer.



**Oplossing:**

1. Voer in het menu **Start** de opdracht **Uitvoeren** -> **MMC** in.
1. Kies **Bestand** > **Modules toevoegen of verwijderen**.
1. Dubbelklik op **Certificaten**, kies **Computeraccount** > **Volgende** en selecteer **Lokale computer**.
1. Dubbelklik op **Certificaten (lokale computer)** en kies **Persoonlijke certificaten**.
1. Zoek het Intune-certificaat dat is uitgegeven door Sc_Online_Issuing en verwijder dit als het aanwezig is.
1. Controleer of de volgende registersleutel bestaat. Als deze bestaat, verwijdert u deze én alle subsleutels: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\OnlineManagement regkey**.
1. Probeer opnieuw in te schrijven.
1. Als de computer nog steeds niet kan worden ingeschreven, zoekt u de volgende sleutel en verwijdert u de sleutel als deze bestaat: **KEY_CLASSES_ROOT\Installer\Products\6985F0077D3EEB44AB6849B5D7913E95**.
1. Probeer opnieuw in te schrijven.

    > [!IMPORTANT]
    > Deze sectie, methode of taak bevat stappen voor het wijzigen van het register. Als u het register onjuist bewerkt, kunnen er echter ernstige problemen optreden. Zorg daarom ervoor dat u deze stappen zorgvuldig uitvoert. Maak voor de zekerheid een back-up van het register voordat u het aanpast. Vervolgens kunt u het register herstellen als er een probleem optreedt.
    > Lees [Een back-up maken van het register en het herstellen in Windows](https://support.microsoft.com/kb/322756) voor meer informatie over het maken en terugzetten een back-up van het register

## <a name="general-enrollment-error-codes"></a>Codes voor algemene registratiefouten

|Foutcode|Mogelijk probleem|Voorgestelde oplossing|
|--------------|--------------------|----------------------------------------|
|0x80CF0437 |De klok op de clientcomputer is niet ingesteld op de juiste tijd.|Zorg ervoor dat de klok en de tijdzone op de clientcomputer zijn ingesteld op de juiste tijd en tijdzone.|
|0x80240438, 0x80CF0438, 0x80CF402C|Kan geen verbinding maken met de Intune-service. Controleer de proxy-instellingen voor de client.|Controleer of de proxyconfiguratie op de clientcomputer door Intune wordt ondersteund en of de clientcomputer internettoegang heeft.|
|0x80240438, 0x80CF0438|Proxy-instellingen in Internet Explorer en lokaal systeem zijn niet geconfigureerd.|Kan geen verbinding maken met de Intune-service. Controleer de proxy-instellingen van de client en bevestig dat de proxyconfiguratie op de clientcomputer door Intune wordt ondersteund, en dat de clientcomputer internettoegang heeft.|
|0x80043001, 0x80CF3001, 0x80043004, 0x80CF3004|Inschrijvingspakket is verouderd.|Download en installeer het huidige clientsoftwarepakket via de beheerwerkruimte.|
|0x80043002, 0x80CF3002|Account is in onderhoudsmodus.|U kunt geen nieuwe clientcomputers inschrijven wanneer de account in onderhoudsmodus is. Meld u aan bij uw account om uw accountinstellingen weer te geven.|
|0x80043003, 0x80CF3003|Account is verwijderd.|Controleer of uw account en abonnement op Intune nog actief zijn. Meld u aan bij uw account om uw accountinstellingen weer te geven.|
|0x80043005, 0x80CF3005|De clientcomputer is buiten gebruik gesteld.|Wacht enkele uren, verwijder oudere versies van de clientsoftware van de computer en voer de installatie van de clientsoftware opnieuw uit.|
|0x80043006, 0x80CF3006|Het maximum aantal toegestane seats voor het account is bereikt.|Uw organisatie moet extra plaatsen aanschaffen voordat u meer clientcomputers in de service kunt inschrijven.|
|0x80043007, 0x80CF3007|Kan het certificaatbestand niet vinden in dezelfde map als het installatieprogramma.|Pak alle bestanden uit voordat u de installatie start. Wijzig of verplaats de uitgepakte bestanden niet: alle bestanden moeten aanwezig zijn in dezelfde map, anders mislukt de installatie.|
|0x8024D015, 0x00240005, 0x80070BC2, 0x80070BC9, 0x80CFD015|De software kan niet worden geïnstalleerd omdat een herstart van de client in behandeling is.|Start de computer opnieuw op en voer de installatie van de clientsoftware opnieuw uit.|
|0x80070032|Een of meer vereisten voor het installeren van de clientsoftware zijn niet gevonden op de clientcomputer.|Zorg ervoor dat alle vereiste updates zijn geïnstalleerd op de clientcomputer en voer de installatie van de clientsoftware opnieuw uit.|
|0x80043008, 0x80CF3008|De Microsoft Online Management Updates-service kan niet worden gestart.|Neem contact op met Microsoft Ondersteuning, zoals wordt beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).|
|0x80043009, 0x80CF3009|De clientcomputer is al ingeschreven bij de service.|U moet de clientcomputer buiten gebruik stellen voordat u deze opnieuw in de service kunt inschrijven.|
|0x8004300B, 0x80CF300B|Het installatiepakket voor de clientsoftware kan niet worden uitgevoerd omdat de versie van Windows die op de client wordt uitgevoerd, niet wordt ondersteund.|Intune biedt geen ondersteuning voor de versie van Windows die wordt uitgevoerd op de clientcomputer.|
|0xAB2|Windows Installer heeft geen toegang tot VBScript-runtime voor aangepaste actie.|Deze fout wordt veroorzaakt door een aangepaste actie die is gebaseerd op DLL-bestanden. Wanneer u problemen met de DLL oplost, moet u mogelijk gebruikmaken van de hulpprogramma's die worden beschreven in [Microsoft Ondersteuning KB198038: Useful Tools for Package and Deployment Issues (Nuttige hulpprogramma's voor pakket- en implementatieproblemen)](https://support.microsoft.com/kb/198038).|
|0x80cf0440|De verbinding met het service-eindpunt is beëindigd.|Het proefaccount of het betaalde account is onderbroken. Maak een nieuw proefaccount of betaald account en schrijf u opnieuw in.|




### <a name="next-steps"></a>Volgende stappen
Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).
