---
title: Apple DEP-beheer voor iOS-apparaten
description: Draadloos een registratieprofiel waarmee iOS-apparaten worden geregistreerd die via het Device Enrollment Program (DEP) zijn aangeschaft, implementeren om Apple-apparaten te beheren.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 75d2a54f065e04b3f6c923dc4e83cfea498ead76
ms.sourcegitcommit: c36f74323b57c9d9ef972322082923c449a1a74f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/03/2017
---
# <a name="enroll-corporate-owned-device-enrollment-program-ios-devices"></a>iOS-apparaten in bedrijfseigendom met het Device Enrollment Program inschrijven

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune kan 'draadloos' een inschrijvingsprofiel implementeren op iOS-apparaten die via het Device Enrollment Program zijn aangeschaft. Het inschrijvingspakket kan configuratieassistentopties voor het apparaat bevatten.

>[!NOTE]
>Inschrijving via DEP kan niet worden gebruikt bij de methode van de [apparaatinschrijvingsmanager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).
>Als gebruikers hun iOS-apparaten registreren (via de bedrijfsportal-app) en de serienummers van deze apparaten vervolgens worden geïmporteerd en toegewezen aan een DEP-profiel, wordt de registratie van het apparaat opgeheven bij Intune.

## <a name="prerequisites-for-enrolling-ios-devices-by-using-apple-dep-management"></a>Vereisten voor de inschrijving van iOS-apparaten met behulp van Apple DEP-beheer

- [Een APNs-certificaat installeren](set-up-ios-and-mac-management-with-microsoft-intune.md)

- Uw organisatie moet lid worden van Apple DEP en apparaten via dat programma ophalen. Details van dit proces kunt u vinden op: [https://deploy.apple.com](https://deploy.apple.com). Voordelen van het programma zijn onder andere handsfree instellen, dus zonder dat elk apparaat via een USB-verbinding op een computer moet worden aangesloten.

- Voordat u iOS-apparaten van het bedrijf met DEP kunt inschrijven, moet u een DEP-token van Apple ontvangen. Intune kan met dit token informatie synchroniseren over apparaten binnen uw bedrijf die aan DEP deelnemen. Ook kan Intune hiermee inschrijvingsprofielen naar Apple uploaden en apparaten toewijzen aan die profielen.

## <a name="steps-to-enroll-ios-devices-by-using-apple-dep-management"></a>Stappen voor de inschrijving van iOS-apparaten met behulp van Apple DEP-beheer

In de volgende stappen wordt uitgelegd hoe u iOS-apparaten vanaf het begin kunt inschrijven met behulp van Apple DEP-beheer. Als apparaten in uw organisatie worden toegevoegd of verwijderd, herhaalt u waarschijnlijk een aantal van deze stappen, bijvoorbeeld om serienummers toe te voegen of te verwijderen, zoals hieronder wordt beschreven.

### <a name="get-an-encryption-key"></a>Een coderingssleutel ophalen

1. Open de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) als gebruiker met beheerdersrechten, ga naar **Beheer** &gt; **Beheer van mobiele apparaten** &gt; **iOS** &gt; **Programma apparaatinschrijving** en klik op **Coderingssleutel downloaden**.

2. Sla het coderingssleutelbestand (.pem) lokaal op. Het .pem-bestand wordt gebruikt om een vertrouwensrelatiecertificaat bij de portal Apple Device Enrollment Program aan te vragen.

![Een Device Enrollment Program-token bijwerken](../media/dev-sa-ios-dep.png)

### <a name="get-a-device-enrollment-program-token"></a>Een Device Enrollment Program-token ophalen

1. Ga naar de [Device Enrollment Program-portal](https://deploy.apple.com) (https://deploy.apple.com) en meld u aan met de Apple-id van uw bedrijf. Deze Apple ID moet later worden gebruikt om uw DEP-token te verlengen.

2.  Ga in de portal voor apparaatinschrijving naar **Programma apparaatinschrijving** &gt; **Servers beheren** en kies **MDM-server toevoegen**.

3.  Voer de **MDM-servernaam** in en kies **Volgende**. De servernaam is voor eigen referentie en dient om de MDM-server te identificeren. Het is niet de naam of URL van de Microsoft Intune-server.

4.  Het dialoogvenster **&lt;Servernaam&gt; toevoegen** wordt geopend. Kies **Bestand selecteren...** om het .pem-bestand te uploaden en kies **Volgende**.

5.  In het dialoogvenster **&lt;Servernaam&gt; toevoegen** wordt een koppeling met **Uw servertoken** weergegeven. Download het servertokenbestand (.p7m) naar uw computer en kies **Gereed**.

   Dit certificaatbestand (.p7m) wordt gebruikt om een vertrouwensrelatie tussen Intune en de Device Enrollment Program-servers van Apple tot stand te brengen.

### <a name="add-the-dep-token-to-intune"></a>Het DEP-token toevoegen aan Intune

1. In de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) gaat u naar **Beheer** &gt; **Beheer van mobiele apparaten** &gt; **iOS** &gt; **Programma apparaatinschrijving**.

2. Kies **Het DEP-token uploaden**. **Blader** naar het certificaatbestand (.p7m), voer uw **Apple ID**in en kies **Uploaden**.

### <a name="add-the-corporate-device-enrollment-policy"></a>Inschrijvingsbeleid voor bedrijfsapparaten toevoegen

1. Ga in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) naar **Beleid** &gt; **Inschrijving van bedrijfsapparaten** en kies **Toevoegen**.

2. Geef **algemene gegevens** op, zoals een **Naam** en **Beschrijving**, en geef aan of apparaten die aan het profiel zijn toegewezen, gebruikersaffiniteit hebben of deel uitmaken van een groep.

   - **Vragen om gebruikersaffiniteit**: het apparaat moet aan een gebruiker worden gekoppeld tijdens de eerste configuratie voordat toegang tot gegevens en e-mail van het bedrijf kan worden verleend. **Gebruikersaffiniteit** moet worden ingesteld voor DEP-beheerde apparaten die eigendom zijn van gebruikers en de bedrijfsportal moeten gebruiken (bijvoorbeeld om apps te installeren). Multi-Factor Authentication (MFA) werkt niet tijdens inschrijving op DEP-apparaten met gebruikersaffiniteit. Na de inschrijving werkt MFA zoals verwacht op deze apparaten. Nieuwe gebruikers die hun wachtwoord moeten wijzigen wanneer ze zich voor het eerst aanmelden, kunnen geen prompt krijgen tijdens de inschrijving voor DEP-apparaten. Daarnaast wordt gebruikers waarvan de wachtwoorden zijn verlopen niet gevraagd hun wachtwoord opnieuw in te stellen tijdens de DEP-inschrijving, en moeten deze het wachtwoord vanaf een ander apparaat opnieuw instellen.

    >[!NOTE]
    >Voor DEP met gebruikersaffiniteit moet [WS-Trust 1.3 gebruikersnaam/mixed-eindpunt](https://technet.microsoft.com/en-us/library/adfs2-help-endpoints) zijn ingeschakeld om een gebruikerstoken aan te vragen. [Meer informatie over WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

   - **Geen gebruikersaffiniteit**: het apparaat is niet gekoppeld aan een gebruiker. Gebruik deze relatie voor apparaten waarmee taken worden uitgevoerd zonder toegang tot lokale gebruikersgegevens. Apps waarvoor een gebruikersrelatie is vereist, zoals de bedrijfsportal-app die gebruikt wordt voor het installeren van LOB-apps, zullen niet werken.

   U kunt ook **apparaten aan de volgende groep toewijzen**. Kies **Selecteren** om een groep te kiezen.

   > [!Important]
   > Groepstoewijzingen worden verplaatst van Intune naar Azure Active Directory. Als uw Intune-account de toepasselijke update ontvangt, is de optie **Apparaten aan de volgende groep toewijzen** niet aanwezig. [Meer informatie](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune#changes-to-intune-group-assignments).

3. Schakel **DEP-instellingen (programma apparaatinschrijving) voor dit beleid configureren** in om DEP te ondersteunen.

      ![Deelvenster van de configuratieassistent](../media/pol-sa-corp-enroll.png)

   De volgende instellingen zijn beschikbaar voor DEP-beheerde apparaten:

   - **Afdeling**: wordt weergegeven wanneer gebruikers tijdens de activering op **Over configuratie** tikken
   - **Telefoonnummer van ondersteuning**: wordt weergegeven wanneer de gebruiker tijdens de activering de knop **Hulp nodig?** kiest
   - **Voorbereidingsmodus**: wordt ingesteld tijdens de activering en kan niet worden gewijzigd zonder het apparaat op de fabrieksinstellingen terug te zetten:
       - **Niet onder supervisie**: beperkte beheermogelijkheden
       - **Onder supervisie**: hiermee worden standaard meer beheeropties ingeschakeld en de activeringsvergrendeling uitgeschakeld
   - **Registratieprofiel vergrendelen voor het apparaat**: wordt ingesteld tijdens de activering en kan niet worden gewijzigd zonder het apparaat op de fabrieksinstellingen terug te zetten
       - **Uitschakelen**: hiermee kan het beheerprofiel worden verwijderd uit het menu **Instellingen**
       - **Inschakelen**: (vereist **Voorbereidingsmodus** = **Onder supervisie**) hiermee wordt de menuoptie in de iOS-instellingen uitgeschakeld om het beheerprofiel te verwijderen
   - **Configuratieassistentopties**: deze instellingen zijn optioneel en kunnen naderhand worden geconfigureerd in het iOS-menu **Instellingen**.
        - **Wachtwoordcode**: hiermee wordt tijdens de activering gevraagd om de wachtwoordcode. Vraag altijd om een wachtwoordcode tenzij het apparaat wordt beveiligd of de toegang tot het apparaat op een andere manier wordt beheerd (bijvoorbeeld de kioskmodus waarmee op het apparaat maar één app kan worden uitgevoerd)
       - **Locatieservices**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om de service gevraagd
       - **Herstellen**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent gevraagd om een iCloud-back-up
       - **Apple ID**: als deze optie is ingeschakeld, worden gebruikers door iOS gevraagd om een Apple ID wanneer Intune een app zonder een id probeert te installeren. Een Apple ID is vereist voor het downloaden van iOS-apps uit de App Store, waaronder de apps die zijn geïnstalleerd door Intune.
       - **Voorwaarden**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent gevraagd de voorwaarden van Apple te accepteren
       - **Touch ID**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
       - **Apple Pay**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
       - **In- en uitzoomen**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
       - **Siri**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
       - **Diagnostische gegevens verzenden naar Apple**: als deze optie is ingeschakeld, wordt tijdens de activering door Configuratieassistent om deze service gevraagd
   -  **Extra beheer via Apple Configurator inschakelen**: stel deze optie in op **Niet toestaan** om te voorkomen dat bestanden met iTunes of beheer via Apple Configurator worden gesynchroniseerd. Het is een goed idee om **Niet toestaan** in te stellen, verdere configuraties vanuit Apple Configurator te exporteren en vervolgens als een aangepast iOS-configuratieprofiel via Intune te implementeren in plaats van deze instelling te gebruiken om een handmatige implementatie met of zonder een certificaat toe te staan.
       - **Niet toestaan**: hiermee wordt voorkomen dat het apparaat communiceert via USB (het koppelen wordt uitgeschakeld)
       - **Toestaan**: hiermee wordt toegestaan dat een apparaat communiceert via een USB-verbinding voor een pc of Mac
       - **Certificaat vereisen**: hiermee is het mogelijk een Mac te koppelen met een certificaat dat is geïmporteerd in het registratieprofiel

### <a name="assign-the-profile-to-devices"></a>Het profiel aan apparaten toewijzen

1. Ga in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) naar **Beleid** &gt; **Inschrijving van bedrijfsapparaten** en kies **Toewijzen**.

2. Kies de apparaten waaraan u het gemaakte profiel wilt toewijzen. U kunt **Alle apparaten** kiezen of specifieke apparaten selecteren. Kies vervolgens **Toevoegen**.

> [!Important]
> Op dit moment kunt u in Intune een 'standaard' inschrijvingsprofiel voor apparaten aanwijzen en nieuwe serienummers worden automatisch aan dit standaardprofiel toegewezen als u nieuwe serienummers met de Apple DEP-service synchroniseert. Als uw tenant in de nabije toekomst naar de nieuwe Azure-portal wordt gemigreerd, kunt u geen standaardprofiel meer instellen om serienummers automatisch toe te wijzen aan dit profiel. U moet in plaats daarvan serienummers toewijzen aan een specifiek profiel. [Meer informatie](https://docs.microsoft.com/intune/device-enrollment-program-enroll-ios)

### <a name="assign-dep-devices-for-management"></a>DEP-apparaten toewijzen voor beheer

1. Ga naar de [Device Enrollment Program-portal](https://deploy.apple.com) (https://deploy.apple.com) en meld u aan met de Apple-id van uw bedrijf.

2. Ga naar **Implementatieprogramma** &gt; **Programma apparaatinschrijving** &gt; **Apparaten beheren**.

3. Geef een manier voor **Apparaten kiezen** op, geef apparaatgegevens op en geef apparaatdetails op aan de hand van **Serienummer** en **Bestelnummer** of voer **CSV-bestand uploaden** uit.

4. Selecteer **Toewijzen aan server**, kies de &lt;Servernaam&gt; die is opgegeven voor Microsoft Intune en kies vervolgens **OK**.

### <a name="synchronize-dep-managed-devices"></a>Door DEP beheerde apparaten synchroniseren

Deze stap synchroniseert apparaten met de Apple DEP-service en zorgt ervoor dat de apparaten worden weergegeven in de Intune-console.

1. Open de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) als gebruiker met beheerdersrechten, ga naar **Beheer** &gt; **Beheer van mobiele apparaten** &gt; **iOS** &gt; **Programma apparaatinschrijving** en kies vervolgens **Nu synchroniseren**. Er wordt een synchronisatieaanvraag verzonden naar Apple.

2. Als u DEP-beheerde apparaten wilt bekijken na de synchronisatie, gaat u in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) naar **Groepen** &gt; **Alle apparaten** &gt; **Vooraf geregistreerde bedrijfsapparaten** &gt; **Op iOS-serienummer**. In de werkruimte  **Op iOS-serienummer** wordt de **Status** voor beheerde apparaten weergegeven als 'Geen contact gemaakt' totdat het apparaat wordt ingeschakeld en de configuratieassistent wordt uitgevoerd om het apparaat in te schrijven.

   Om te voldoen aan de voorwaarden van Apple voor acceptabel DEP-verkeer, worden door Intune de volgende beperkingen opgelegd:

   - Een volledige DEP-synchronisatie kan niet vaker dan eens in de zeven dagen worden uitgevoerd. Tijdens een volledige synchronisatie vernieuwt Intune elk serienummer dat door Apple aan Intune is toegewezen, of het serienummer eerder is gesynchroniseerd of niet. Als een volledige synchronisatie wordt uitgevoerd binnen zeven dagen na de vorige volledige synchronisatie, vernieuwt Intune alleen serienummers die nog niet aanwezig zijn in Intune.

   - Een synchronisatieaanvraag krijgt 10 minuten de tijd om te worden uitgevoerd. Gedurende deze tijd of totdat de aanvraag is geslaagd, is de knop **Synchronisatie** uitgeschakeld.

### <a name="distribute-devices-to-users"></a>Apparaten onder gebruikers distribueren

Uw apparaten in bedrijfseigendom kunnen nu onder gebruikers worden gedistribueerd. Wanneer een iOS-apparaat wordt ingeschakeld, zal het worden ingeschreven voor beheer door Intune. De limiet voor het aantal apparaten per gebruiker geldt voor DEP-beheerde apparaten.

>[!NOTE]
>Als een gebruiker een DEP-apparaat wil inschrijven, maar de limiet voor het aantal apparaten heeft overschreden, mislukt de inschrijving zonder dat de gebruiker hierover wordt gewaarschuwd.

## <a name="changes-to-intune-group-assignments"></a>Wijzigingen aan Intune-groepstoewijzingen

In April 2017 wordt apparaatgroepsbeheer verplaatst naar Azure Active Directory. Na de overgang naar Azure Active Directory-groepen wordt groepstoewijzing niet weergegeven in de opties voor het registratieprofiel voor bedrijfsapparaten. Omdat deze wijziging in een aantal maanden wordt geïmplementeerd, ziet u de wijziging mogelijk niet meteen. Na de overgang naar de nieuwe portal kunnen er dynamische apparaatgroepstoewijzingen worden gedefinieerd op basis van de namen van de inschrijvingsprofielen voor bedrijven.

Voor elke Intune-apparaatgroep die vooraf is toegewezen door een inschrijvingsprofiel voor bedrijfsapparaten, wordt tijdens de migratie een overeenkomende dynamische apparaatgroep in AAD gemaakt op basis van de naam van het inschrijvingsprofiel. Nieuwe profielnamen hebben de indeling *EnrollmentProfile:&lt;naam van gekoppelde profiel&gt;*. Dit proces zorgt ervoor dat apparaten die vooraf zijn toegewezen aan een apparaatgroep al automatisch worden geregistreerd bij de groep waarvoor het beleid en de apps zijn geïmplementeerd.

Het automatisch maken van deze groep gebeurt slechts één keer tijdens de migratie van groepen. Na de migratie moeten Intune-admins maken van groepen met behulp van de Azure-portal. Zie [Changes to Automatic Grouping for Corporate Pre-enrolled iOS Devices](https://blogs.technet.microsoft.com/intunesupport/2017/04/19/changes-to-automatic-grouping-for-corporate-pre-enrolled-ios-devices/) (Wijzigingen aan automatische groepering van zakelijke iOS-apparaten die vooraf zijn geregistreerd) voor meer informatie over de invloed hiervan op de registratie van iOS-apparaten die bedrijfseigendom zijn.

U vindt hier ook [Meer informatie over Azure Active Directory-groepen](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/).

### <a name="see-also"></a>Zie tevens
[Vereisten voor het inschrijven van apparaten](prerequisites-for-enrollment.md)
