---
title: Problemen met het registreren van apparaten oplossen | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: meer informatie over het oplossen van problemen bij het registreren van apparaten.'
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c324c74e-e225-40ad-88b7-72a6d9ea09b5
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: 8d56b6600ca86faabbb50d29405969385eb29940


---

# <a name="troubleshoot-device-enrollment-in-intune"></a>Problemen bij de apparaatinschrijving oplossen

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Dit onderwerp bevat suggesties voor het oplossen van problemen met de registratie van apparaat. Zie [Ondersteuning voor Microsoft Intune krijgen](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) voor meer manieren om hulp te krijgen als u het probleem niet kunt oplossen met deze informatie.


## <a name="initial-troubleshooting-steps"></a>Eerste stappen om het probleem op te lossen

Voordat u het probleem probeert op te lossen, controleert u of u Intune op de juiste manier hebt geconfigureerd om registratie mogelijk te maken. Zie [Android- en Standard Knox-apparaten registreren](/intune-azure/enroll-devices/enroll-android-and-knox-standard-devices.md) voor koppelingen naar registratiestappen voor elk platform.

Gebruikers van beheerde apparaten kunnen registratie- en diagnostische gegevens laten vastleggen in logboeken, zodat u deze kunt bekijken. Gebruikersinstructies voor het vastleggen van gegevens in logboeken vindt u in:

- [Android-inschrijvingsfouten verzenden naar de IT-beheerder](https://docs.microsoft.com/intune/enduser/send-enrollment-errors-to-your-it-admin-android)
- [iOS-fouten naar uw IT-beheerder verzenden](https://docs.microsoft.com/intune/enduser/send-errors-to-your-it-admin-ios)

## <a name="general-enrollment-issues"></a>Problemen bij het registreren van apparaten
Deze problemen kunnen optreden op alle apparaatplatforms.

### <a name="device-cap-reached"></a>Apparaatlimiet bereikt
**Probleem:** een gebruiker ontvangt tijdens de registratie een foutbericht op het apparaat, zoals het foutbericht **De bedrijfsportal is tijdelijk niet beschikbaar** op een iOS-apparaat, en DMPdownloader.log in Configuration Manager bevat de fout **DeviceCapReached**.

**Oplossing:**

#### <a name="check-number-of-devices-enrolled-and-allowed"></a>Controleer het aantal apparaten dat is ingeschreven en dat wordt toegestaan

Kies in Azure-portal **Meer services** > **Bewaking en beheer** > **Intune**. Ga op de blade Intune van Azure Portal naar **Apparaten inschrijven** > **Inschrijvingsbeperkingen** en controleer of aan de gebruiker niet meer dan het toegestane maximum van 15 apparaten is toegewezen.

<!--- Mobile device users can delete devices at the following URL: [https://byodtestservice.azurewebsites.net/](https://byodtestservice.azurewebsites.net/). --->

Beheerders kunnen apparaten verwijderen in de Azure Active Directory-portal.

#### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>U kunt als volgt apparaten verwijderen in de Azure Active Directory-portal:

1.  Blader naar [http://aka.ms/accessaad](http://aka.ms/accessaad) of kies **Beheer** &gt; **Azure AD** op [https://portal.office.com](https://portal.office.com).

2.  Meld u aan met uw organisatie-id via de koppeling aan de linkerkant van de pagina.

3.  Een Azure-abonnement maken als u er nog geen hebt. U kunt dit zonder creditcard of betaling doen als u beschikt over een betaald account (kies de abonnementskoppeling **Uw gratis Azure Active Directory registreren**).

4.  Selecteer **Active Directory** en vervolgens uw organisatie.

5.  Selecteer het tabblad **Gebruikers** .

6.  Selecteer de gebruiker waarvoor u de apparaten wilt verwijderen.

7.  Kies **Apparaten**.

8.  Verwijder waar nodig apparaten, zoals apparaten die niet langer in gebruik zijn of die onjuist zijn gedefinieerd.

> [!NOTE]

> U kunt de limiet voor apparaatregistraties vermijden met behulp van apparaatregistratiebeheerders, zoals wordt beschreven in [Enroll devices using device enrollment manager](/intune-azure/enroll-devices/enroll-devices-using-device-enrollment-manager.md) (Apparaten registreren met de apparaatregistratiebeheerder).
>
> Met een gebruikersaccount dat is toegevoegd aan de groep Apparaatregistratiebeheerders kunnen geen apparaten worden geregistreerd wanneer een beleid voor voorwaardelijke toegang van kracht is voor die specifieke gebruikersaanmelding.

### <a name="company-portal-temporarily-unavailable"></a>Bedrijfsportal is tijdelijk niet beschikbaar
**Probleem:** een gebruiker ontvangt op zijn of haar apparaat de fout **De bedrijfsportal tijdelijk niet beschikbaar**.

**Oplossing:**

1.  Verwijder de Intune-bedrijfsportal-app van het apparaat.

2.  Open de browser op het apparaat, ga naar [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com)en meld u aan.

3.  Als de gebruiker zich niet kan aanmelden, vraagt u deze om zich bij een ander netwerk aan te melden.

4.  Als dat mislukt, controleert u of de referenties van de gebruiker juist zijn gesynchroniseerd met Azure Active Directory.

5.  Als de gebruiker zich heeft aangemeld, wordt u op een iOS-apparaat gevraagd om de Intune-bedrijfsportal-app te installeren en het apparaat in te schrijven. Op een Android-apparaat moet u de Intune-bedrijfsportal-app handmatig installeren, waarna u het apparaat opnieuw kunt inschrijven.

### <a name="mdm-authority-not-defined"></a>De MDM-instantie is niet gedefinieerd
**Probleem:** een gebruiker ontvangt de fout **De MDM-instantie is niet gedefinieerd**.

**Oplossing:**

1.  Controleer of de MDM-instantie juist is ingesteld voor het type Intune-service dat u gebruikt (dat wil zeggen Intune, Office 365 of System Center Configuration Manager met Intune). Zie [De instantie voor het beheer van mobiele apparaten instellen](https://docs.microsoft.com/en-us/intune-azure/enroll-devices/set-mdm-authority) voor instructies.

    > [!NOTE]
    > Wanneer u de MDM-instantie eenmaal hebt ingesteld, kunt u deze alleen wijzigen door contact op te nemen met Ondersteuning, zoals wordt beschreven in [Ondersteuning voor Microsoft Intune krijgen](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

2.  Controleer of de referenties van de gebruiker juist zijn gesynchroniseerd met Azure Active Directory door te controleren of de UPN overeenkomt met de Active Directory-gegevens in de accountportal.
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


**Oplossing:** Microsoft Office 365-klanten die gebruikmaken van eenmalige aanmelding (SSO) via AD FS 2.0 en meerdere domeinen op het hoogste niveau hebben voor UPN-achtervoegsels van gebruikers in hun organisatie (bijvoorbeeld @contoso.com of @fabrikam.com)), moeten voor elk achtervoegsel een afzonderlijk exemplaar van de AD FS 2.0 Federation Service implementeren.  Er is nu een [updatepakket voor AD FS 2.0](http://support.microsoft.com/kb/2607496) dat kan worden gebruikt met de schakeloptie **SupportMultipleDomain** om de AD FS-server in te schakelen voor ondersteuning van dit scenario zonder extra AD FS 2.0-servers. Lees [deze blog](https://blogs.technet.microsoft.com/abizerh/2013/02/05/supportmultipledomain-switch-when-managing-sso-to-office-365/) voor meer informatie.


## <a name="android-issues"></a>Problemen met Android
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

Vraag uw gebruikers de instructies te volgen in [Er ontbreekt een vereist certificaat voor uw apparaat](https://docs.microsoft.com/intune/enduser/your-device-is-missing-a-required-certificate-landing-android#your-device-is-missing-a-certificate-required-by-your-it-administrator). Als de fout nog steeds wordt weergegeven nadat gebruikers de instructies hebben gevolgd, probeert u oplossing 2.

**Oplossing 2**:

Als gebruikers nog steeds de fout voor het ontbrekende certificaat krijgen te zien nadat ze hun bedrijfsreferenties hebben ingevoerd en worden omgeleid voor de federatieve aanmeldingservaring, is het mogelijk dat er een tussencertificaat mogelijk van uw AD FS-server (Active Directory Federation Services).

De certificaatfout treedt op omdat Android-apparaten vereisen dat er tussencertificaten zijn opgenomen in een [SSL Server hello](https://technet.microsoft.com/library/cc783349.aspx), maar momenteel verstuurt een standaard AD FS-server of AD FS-proxyserverinstallatie alleen het SSL-certificaat van de AD FS-service in het SSL server hello-antwoord op een SSL Client hello.

Als u dit probleem wilt oplossen, importeert u als volgt de certificaten in het persoonlijke certificaatarchief op de AD FS-server of proxy’s:

1.    Op de ADFS- en proxyservers start u de Certificate Management-console voor de lokale computer door met de rechtermuisknop op de knop **Start** te klikken, de optie **Uitvoeren** te kiezen en **certlm.msc** te typen.
2.    Vouw de optie **Persoonlijk** uit en selecteer **Certificaten**.
3.    Zoek het certificaat voor uw AD FS-servicecommunicatie (een openbaar ondertekend certificaat) en dubbelklik erop om de eigenschappen weer te geven.
4.    Selecteer het tabblad **Certificeringspad** om de bovenliggende certificaten weer te geven.
5.    Selecteer voor elk bovenliggend certificaat **Certificaat weergeven**.
6.    Selecteer het tabblad **Details** en kies **Kopiëren naar bestand...**.
7.    Volg de aanwijzingen in de wizard om de openbare sleutel van het certificaat te exporteren of op te slaan naar de gewenste bestandslocatie.
8.    Importeer de bovenliggende certificaten die tijdens stap 3 zijn geëxporteerd naar Lokale computer\Persoonlijk\Certificaten door met de rechtermuisknop op **Certificaten** te klikken, **Alle taken** > **Importeren** te selecteren en vervolgens de aanwijzingen in de wizard te volgen om de certificaten te importeren.
9.    Start de AD FS-servers opnieuw op.
10.    Herhaal de stappen hierboven op al uw AD FS- en proxyservers.
De gebruiker moet zich nu kunnen aanmelden bij de bedrijfsportal op het Android-apparaat.

**Valideren dat het certificaat correct is geïnstalleerd**:

In de volgende stappen wordt slechts een van de vele methoden en hulpprogramma's beschreven die u kunt gebruiken om te valideren of het certificaat goed is geïnstalleerd.

1. Ga naar het [gratis hulpprogramma Digicert](ttps://www.digicert.com/help/).
2. Geef de Fully Qualified Domain Name van uw AD FS-server op (bijvoorbeeld sts.contoso.com) en selecteer **SERVER CONTROLERENSERVER**.

Als het servercertificaat goed is geïnstalleerd, worden er allemaal vinkjes weergegeven in de resultaten. Als het bovenstaande probleem bestaat, ziet u in de rapportsecties 'Certificaatnaam komt overeen met' en 'SSL-certificaat is correct geïnstalleerd' een rode X.


## <a name="ios-issues"></a>Problemen met iOS

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

### <a name="profile-installation-failed"></a>De profielinstallatie is mislukt
**Probleem:** een gebruiker ontvangt op een iOS-apparaat de fout **Profiel is niet geïnstalleerd**.

### <a name="troubleshooting-steps-for-failed-profile-installation"></a>Stappen voor de probleemoplossing bij een mislukte profielinstallatie

1.  Controleer of er een juiste licentie aan de gebruiker is toegewezen voor de versie van de Intune-service die u gebruikt.

2.  Controleer of het apparaat niet al is ingeschreven met een andere MDM-provider of dat er voor het apparaat niet al een beheerprofiel is geïnstalleerd.

3.  Navigeer naar [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) en probeer het profiel te installeren als u daarom wordt gevraagd.

4.  Controleer of Safari for iOS de standaardbrowser is en of cookies zijn ingeschakeld.

### <a name="enrolled-ios-device-doesnt-appear-in-console-when-using-system-center-configuration-manager-with-intune"></a>Het geregistreerde iOS-apparaat wordt niet weergegeven in de console wanneer u System Center Configuration Manager met Intune gebruikt
**Probleem:** een gebruiker registreert zijn of haar iOS-apparaat, maar het apparaat wordt niet weergegeven in de beheerconsole van Configuration Manager. Op het apparaat wordt niet aangegeven dat het is geregistreerd. Mogelijke oorzaken:

- Misschien hebt u uw Intune-connector geregistreerd bij het ene account en vervolgens geregistreerd bij een ander account.
- Misschien hebt u het MDM-certificaat gedownload vanuit het ene account en het vervolgens gebruikt in een ander account.


**Oplossing**: voer de volgende stappen uit:

1. Schakel iOS uit in de Windows Intune-connector.
    1. Klik met de rechtermuisknop op het Intune-abonnement en selecteer **Eigenschappen**.
    1. Schakel op het tabblad iOS de optie iOS-registratie inschakelen uit.



2. Voer in SQL de volgende stappen uit voor de CAS-database

    1. update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%'
    1. delete from MDMPolicy where PolicyType = 7
    1. delete from MDMPolicyAssignment where PolicyType = 7
    1. update SC_ClientComponent_Property set Value2 = '' where Name like '%APNS%'
    1. delete from MDMPolicy where PolicyType = 11
    1. delete from MDMPolicyAssignment where PolicyType = 11
    1. DELETE Drs_Signals
3. Start de service SMS Executive opnieuw of start de CM-server opnieuw.

4. Haal een nieuw APN-certificaat op en upload dit. Klik hiertoe met de rechtermuisknop op het Intune-abonnement in het linkerdeelvenster van Configuration Manager. Selecteer **APNs-certificaataanvraag maken** en volg de instructies.
5. 
## <a name="issues-when-using-system-center-configuration-manager-with-intune"></a>Problemen bij het gebruik van System Center Configuration Manager met Intune

### <a name="mobile-devices-disappear"></a>Mobiele apparaten verdwijnen

**Probleem:** nadat een mobiel apparaat bij Configuration Manager is geregistreerd, verdwijnt het uit de verzameling van mobiele apparaten, maar het apparaat heeft nog steeds een beheerprofiel en wordt vermeld in CSS Gateway.

**Oplossing:** dit probleem kan optreden omdat er een aangepast proces actief is dat apparaten verwijdert die niet aan een domein zijn toegevoegd, of omdat de gebruiker het apparaat uit het abonnement heeft verwijderd. Als u wilt nagaan door welk gebruikersaccount of proces het apparaat uit de Configuration Manager-console is verwijderd, voert u de volgende stappen uit om te controleren hoe het apparaat is verwijderd.

1.  Selecteer in de Configuration Manager-beheerconsole **Bewaking** &gt; **Systeemstatus** &gt; **Statusberichtquery's**.

2.  Klik met de rechtermuisknop op **Resources van verzamelingsleden die handmatig zijn verwijderd** en selecteer **Berichten weergeven**.

3.  Kies de juiste tijd/datum of de afgelopen 12 uur.

4.  Zoek het betreffende apparaat en bekijk hoe het is verwijderd. In het volgende voorbeeld ziet u dat het apparaat via een onbekende toepassing is verwijderd door het account SCCMInstall.

    ![Schermopname voor diagnose van apparaatverwijdering](./media/cm-with-intune-unknown-app-deleted-device.png)

5.  Controleer of er geen geplande taak, script of ander proces voor Configuration Manager voorkomt waarmee apparaten die niet tot een domein behoren, mobiele apparaten of gerelateerde apparaten worden gewist.




### <a name="other-ios-enrollment-errors"></a>iOS-registratiefouten

U kunt een lijst weergeven met de [iOS-registratiefouten](https://docs.microsoft.com/intune/enduser/you-see-errors-while-trying-to-enroll-your-device-in-intune-ios) die mogelijk voor eindgebruikers worden weergegeven. De lijst bevat informatie over foutberichten die eindgebruikers kunnen ontvangen en de stappen die u kunt ondernemen om het probleem te verhelpen.

## <a name="pc--issues"></a>Pc-problemen

### <a name="the-machine-is-already-enrolled---error-hr-0x8007064c"></a>De computer is al geregistreerd: fout hr 0x8007064c
**Probleem:** de registratie is mislukt met de fout **De computer is al geregistreerd**. In het registratielogboek wordt de fout **hr 0x8007064c** vermeld.

Deze fout treedt mogelijk op doordat de computer eerder is geregistreerd of een gekloonde installatiekopie bevat van een computer die is geregistreerd. Het accountcertificaat van het vorige account staat nog op de computer.

**Oplossing:**

1.. Voer in het menu **Start** de opdracht **Uitvoeren** -> **MMC** in.
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
    > Zie [How to back up and restore the registry in Windows](https://support.microsoft.com/en-us/kb/322756) (Een back-up maken van het register en het terugzetten in Windows) voor meer informatie over het maken en terugzetten van een back-up van het register.

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
|0x80043008, 0x80CF3008|De Microsoft Online Management Updates-service kan niet worden gestart.|Neem contact op met Microsoft Ondersteuning, zoals wordt beschreven in [Ondersteuning voor Microsoft Intune krijgen](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).|
|0x80043009, 0x80CF3009|De clientcomputer is al ingeschreven bij de service.|U moet de clientcomputer buiten gebruik stellen voordat u deze opnieuw in de service kunt inschrijven.|
|0x8004300B, 0x80CF300B|Het installatiepakket voor de clientsoftware kan niet worden uitgevoerd omdat de versie van Windows die op de client wordt uitgevoerd, niet wordt ondersteund.|Intune biedt geen ondersteuning voor de versie van Windows die wordt uitgevoerd op de clientcomputer.|
|0xAB2|Windows Installer heeft geen toegang tot VBScript-runtime voor aangepaste actie.|Deze fout wordt veroorzaakt door een aangepaste actie die is gebaseerd op DLL-bestanden. Wanneer u problemen met de DLL oplost, moet u mogelijk gebruikmaken van de hulpprogramma's die worden beschreven in [Microsoft Ondersteuning KB198038: Useful Tools for Package and Deployment Issues (Nuttige hulpprogramma's voor pakket- en implementatieproblemen)](https://support.microsoft.com/en-us/kb/198038).|
|0x80cf0440|De verbinding met het service-eindpunt is beëindigd.|Het proefaccount of het betaalde account is onderbroken. Maak een nieuw proefaccount of betaald account en schrijf u opnieuw in.|




### <a name="next-steps"></a>Volgende stappen
Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).



<!--HONumber=Feb17_HO3-->


