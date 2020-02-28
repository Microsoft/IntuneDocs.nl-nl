---
title: Problemen met inschrijving van iOS-/iPadOS-apparaten in Microsoft Intune oplossen
titleSuffix: Microsoft Intune
description: Suggesties voor het oplossen van een aantal van de meestvoorkomende problemen bij het inschrijven van iOS-/iPadOS-apparaten in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/18/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a29fab4be6e2046b2c6757505001a7ba3455b8d6
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514316"
---
# <a name="troubleshoot-iosipados-device-enrollment-problems-in-microsoft-intune"></a>Problemen met inschrijving van iOS-/iPadOS-apparaten in Microsoft Intune oplossen

Dit artikel helpt Intune-beheerders om problemen bij het inschrijven van iOS-/iPadOS-apparaten in Intune te begrijpen en op te lossen.

## <a name="prerequisites"></a>Vereisten

Voordat u begint met de probleemoplossing, is het belangrijk om enkele basisgegevens te verzamelen. Deze gegevens kunnen u helpen het probleem beter te begrijpen en sneller een oplossing voor het probleem te vinden.

Verzamel de volgende gegevens van het probleem:

- Wat is het exacte foutbericht?
- Waar wordt het foutbericht weergegeven?
- Wanneer is het probleem begonnen? Heeft de inschrijving ooit gewerkt?
- Op welk platform (Android, iOS/iPadOS, Windows) doet het probleem zich voor?
- Hoeveel gebruikers treft het probleem? Geldt het probleem voor alle gebruikers of voor bepaalde gebruikers?
- Voor hoeveel apparaten geldt het probleem? Geldt het probleem voor alle apparaten of voor bepaalde apparaten?
- Wat is de MDM-instantie?
- Hoe wordt de inschrijving uitgevoerd? Wordt BYOD (Bring Your Own Device) of Apple DEP (Device Enrollment Program) gebruikt met inschrijvingsprofielen?

## <a name="error-messages"></a>Foutberichten

### <a name="profile-installation-failed-a-network-error-has-occurred"></a>De profielinstallatie is mislukt. Er is een netwerkfout opgetreden.

**Oorzaak:** Er is een niet nader omschreven probleem met iOS/iPadOS op het apparaat.

#### <a name="resolution"></a>Oplossing

1. Als u gegevensverlies wilt voorkomen in de volgende stappen (door het herstellen van iOS/iPadOS verwijdert u alle gegevens op het apparaat), zorg er dan voor dat u een back-up maakt van uw gegevens.
2. Plaats het apparaat in de herstelmodus en herstel het vervolgens. Zorg ervoor dat u het apparaat als een nieuw apparaat instelt. Zie [https://support.apple.com/HT201263](https://support.apple.com/HT201263) voor meer informatie over het herstellen van iOS-/iPadOS-apparaten.
3. Schrijf het apparaat opnieuw in.

### <a name="profile-installation-failed-connection-to-the-server-could-not-be-established"></a>De profielinstallatie is mislukt. Er kan geen verbinding met de server tot stand worden gebracht.

**Oorzaak:** Uw Intune-tenant is zo geconfigureerd dat alleen apparaten in bedrijfseigendom zijn toegestaan. 

#### <a name="resolution"></a>Oplossing
1. Meld u aan bij Azure Portal.
2. Selecteer **Meer Services**, zoek naar Intune en selecteer vervolgens **Intune**.
3. Selecteer **Apparaatinschrijving** > **Inschrijvingsbeperkingen**.
4. Selecteer onder **Beperking voor apparaattypen** de beperking die u wilt instellen > **Eigenschappen** > **Platformen selecteren** > selecteer **Toestaan** voor **iOS** en klik vervolgens op **OK**.
5. Selecteer **Platformen configureren**, selecteer **Toestaan** voor iOS-/iPadOS-apparaten in persoonlijk eigendom en klik vervolgens op **OK**.
6. Schrijf het apparaat opnieuw in.

**Oorzaak:** De benodigde CNAME-records in DNS bestaan niet.

#### <a name="resolution"></a>Oplossing
Maak CNAME-DNS-bronrecords voor uw bedrijfsdomein. Als het domein van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleidt naar EnterpriseEnrollment-s.manage.microsoft.com.

Hoewel het maken van CNAME-DNS-vermeldingen optioneel is, maken CNAME-records het voor gebruikers makkelijker om zich in te schrijven. Als er geen CNAME-inschrijvingsrecord wordt gevonden, wordt gebruikers gevraagd de MDM-servernaam (enrollment.manage.microscoft.com) handmatig in te voeren.

Als er meer dan één gecontroleerd domein is, maakt u een CNAME-record voor elk domein. De CNAME-resourcerecords moeten de volgende informatie bevatten:

|TYPE|Hostnaam|Verwijst naar|TTL|
|------|------|------|------|
|CNAME|EnterpriseEnrollment.bedrijfsdomein.com|EnterpriseEnrollment-s.manage.microsoft.com|1 uur|
|CNAME|EnterpriseRegistration.bedrijfsdomein.com|EnterpriseRegistration.windows.net|1 uur|

Als uw bedrijf meerdere domeinen heeft voor gebruikersreferenties, maakt u CNAME-records voor elk domein.

> [!NOTE]
> Het kan 72 uur duren voordat wijzigingen in DNS-records zijn doorgegeven. U kunt de DNS-wijziging in Intune pas controleren wanneer de DNS-record is doorgegeven.

**Oorzaak:** U schrijft een apparaat in dat eerder is ingeschreven met een ander gebruikersaccount en de vorige gebruiker is niet op de juiste manier verwijderd uit Intune.

#### <a name="resolution"></a>Oplossing
1. Annuleer de eventuele installatie van een profiel.
2. Open [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com) in Safari.
3. Schrijf het apparaat opnieuw in.

> [!NOTE]
> Als de inschrijving nog steeds niet lukt, verwijdert u cookies in Safari (cookies niet blokkeren) en schrijft u het apparaat vervolgens opnieuw in.

**Oorzaak:** Het apparaat is al ingeschreven bij een andere MDM-provider.

#### <a name="resolution"></a>Oplossing
1. Open **Instellingen** op het iOS-/iPadOS-apparaat en ga naar **Algemeen > Apparaatbeheer**.
2. Verwijder bestaande beheerprofielen.
3. Schrijf het apparaat opnieuw in.

**Oorzaak:** De gebruiker die het apparaat probeert in te schrijven, heeft geen licentie voor Microsoft Intune.

#### <a name="resolution"></a>Oplossing
1. Ga naar het [Office 365-beheercentrum](https://portal.office.com/adminportal/home#/homepage)en kies **Gebruikers > Actieve gebruikers**.
2. Selecteer het gebruikersaccount waaraan u een Intune-gebruikerslicentie wilt toewijzen en selecteer vervolgens **Productlicenties > Bewerken**.
3. Selecteer **Aan**voor de licentie die u aan deze gebruiker wilt toewijzen en kies vervolgens **Opslaan**.
4. Schrijf het apparaat opnieuw in.

### <a name="this-service-is-not-supported-no-enrollment-policy"></a>Deze service wordt niet ondersteund. Geen registratiebeleid.

**Oorzaak**: Er is geen Apple MDM-pushcertificaat geconfigureerd in Intune of het certificaat is ongeldig. 

#### <a name="resolution"></a>Oplossing

- Als het MDM-pushcertificaat niet is geconfigureerd, volgt u de stappen in [Een Apple MDM-pushcertificaat ophalen](apple-mdm-push-certificate-get.md#steps-to-get-your-certificate).
- Als het MDM-pushcertificaat ongeldig is, volgt u de stappen in [Een Apple MDM-pushcertificaat verlengen](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate).

### <a name="company-portal-temporarily-unavailable-the-company-portal-app-encountered-a-problem-if-the-problem-persists-contact-your-system-administrator"></a>Bedrijfsportal is tijdelijk niet beschikbaar. Er is een probleem opgetreden in de Bedrijfsportal-app. Neem contact op met uw systeembeheerder als het probleem zich blijft voordoen.

**Oorzaak:** De Bedrijfsportal-app is verouderd of beschadigd.

#### <a name="resolution"></a>Oplossing
1. Verwijder de Bedrijfsportal-app van het apparaat.
2. Download en installeer de **Microsoft Intune Company Portal**-app uit de **App Store**.
3. Schrijf het apparaat opnieuw in.
 > [!NOTE]
    > Deze fout kan ook optreden als de gebruiker probeert om meer apparaten in te schrijven dan is toegestaan. Volg de stappen hieronder voor **Apparaatlimiet bereikt** als u het probleem niet kunt oplossen met deze stappen.

### <a name="device-cap-reached"></a>Apparaatlimiet bereikt

**Oorzaak:** De gebruiker probeert meer apparaten in te schrijven dan is toegestaan volgens de inschrijvingslimiet van het apparaat.

#### <a name="resolution"></a>Oplossing
1. Kies in het [beheercentrum van Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) **Apparaten** > **Alle apparaten** en kijk hoeveel apparaten de gebruiker heeft ingeschreven.
    > [!NOTE]
    > U moet ook de betrokken gebruikersaanmelding voor de [Intune-gebruikersportal](https://portal.manage.microsoft.com/) hebben en controleren welke apparaten zijn ingeschreven. Het is mogelijk dat er apparaten worden weergegeven in de [Intune-gebruikersportal](https://portal.manage.microsoft.com/), maar niet in de [Intune-beheerportal](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview). Dergelijke apparaten tellen ook mee voor de inschrijvingslimiet van het apparaat.
2. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) **Apparaat** > **Inschrijvingsbeperkingen** > controleer de limiet voor apparaatinschrijving. De limiet is standaard ingesteld op 15. 
3. Als het aantal apparaten dat is ingeschreven de limiet heeft bereikt, verwijdert u overbodige apparaten of verhoogt u de inschrijvingslimiet van het apparaat. Omdat elk ingeschreven apparaat een Intune-licentie verbruikt, raden we aan om altijd eerst overbodige apparaten te verwijderen.
4. Schrijf het apparaat opnieuw in.

### <a name="workplace-join-failed"></a>Koppelen aan werkplek is mislukt

**Oorzaak:** De Bedrijfsportal-app is verouderd of beschadigd.  

#### <a name="resolution"></a>Oplossing
1. Verwijder de Bedrijfsportal-app van het apparaat.
2. Download en installeer de **Microsoft Intune Company Portal**-app uit de **App Store**.
3. Schrijf het apparaat opnieuw in.

### <a name="user-license-type-invalid"></a>Het type gebruikerslicentie is ongeldig

**Oorzaak:** De gebruiker die het apparaat probeert in te schrijven, heeft geen geldige Intune-licentie.

#### <a name="resolution"></a>Oplossing
1. Ga naar het [Microsoft 365-beheercentrum](https://portal.office.com/adminportal/home#/homepage)en kies **Gebruikers** > **Actieve gebruikers**.
2. Selecteer het betrokken gebruikersaccount > **Productlicenties** > **Bewerken**.
3. Controleer of er een geldige Intune-licentie is toegewezen aan deze gebruiker.
4. Schrijf het apparaat opnieuw in.

### <a name="user-name-not-recognized-this-user-account-is-not-authorized-to-use-microsoft-intune-contact-your-system-administrator-if-you-think-you-have-received-this-message-in-error"></a>Gebruikersnaam wordt niet herkend. Dit gebruikersaccount is niet bevoegd om Microsoft Intune te gebruiken. Neem contact op met de systeembeheerder als u denkt dat u dit bericht ten onrechte hebt ontvangen.

**Oorzaak:** De gebruiker die het apparaat probeert in te schrijven, heeft geen geldige Intune-licentie.

1. Ga naar het [Microsoft 365-beheercentrum](https://portal.office.com/adminportal/home#/homepage)en kies **Gebruikers** > **Actieve gebruikers**.
2. Selecteer het betrokken gebruikersaccount en kies vervolgens **Productlicenties** > **Bewerken**.
3. Controleer of er een geldige Intune-licentie is toegewezen aan deze gebruiker.
4. Schrijf het apparaat opnieuw in.

### <a name="profile-installation-failed-the-new-mdm-payload-does-not-match-the-old-payload"></a>De profielinstallatie is mislukt. De nieuwe MDM-payload komt niet overeen met de oude payload.

**Oorzaak:** Er is al een beheerprofiel op het apparaat geïnstalleerd.

#### <a name="resolution"></a>Oplossing

1. Open **Instellingen** op het iOS-/iPadOS-apparaat > **Algemeen** > **Apparaatbeheer**.
2. Tik op het bestaande beheerprofiel en tik op **Beheer verwijderen**.
3. Schrijf het apparaat opnieuw in.

### <a name="noenrollmentpolicy"></a>NoEnrollmentPolicy

**Oorzaak:** Het APNs-certificaat (Apple Push Notification service) ontbreekt, is ongeldig of is verlopen.

#### <a name="resolution"></a>Oplossing
Controleer of er een geldig APNs-certificaat is toegevoegd aan Intune. Zie [iOS-/iPadOS-inschrijving instellen](ios-enroll.md) voor meer informatie.

### <a name="accountnotonboarded"></a>AccountNotOnboarded

**Oorzaak:** Er is een probleem met het APNs-certificaat (Apple Push Notification Service) dat is geconfigureerd in Intune.

#### <a name="resolution"></a>Oplossing
Vernieuw het APNs-certificaat en schrijf het apparaat opnieuw in.

> [!IMPORTANT]
> Zorg ervoor dat u het APNs-certificaat vernieuwt. U moet het APNs-certificaat dus niet vervangen. Als u het certificaat vervangt, moet u alle iOS-/iPadOS-apparaten opnieuw inschrijven in Intune. 

- Zie [Een Apple MDM-pushcertificaat verlengen](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate) voor informatie over het vernieuwen van het APNs-certificaat in de zelfstandige versie van Intune.
- Zie [Een APNs-certificaat maken voor iOS-/iPadOS-apparaten](https://support.office.com/article/Create-an-APNs-Certificate-for-iOS-devices-522b43f4-a2ff-46f6-962a-dd4f47e546a7)voor informatie over het vernieuwen van het APNs-certificaat in Office 365.

### <a name="xpc_type_error-connection-invalid"></a>XPC_TYPE_ERROR Verbinding ongeldig

Wanneer u een met DEP beheerd apparaat inschakelt waaraan een inschrijvingsprofiel is toegewezen, mislukt de inschrijving en ziet u het volgende foutbericht:

```
asciidoc
mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" } }
iPhone mobileassetd[83] <Notice>: Client connection invalid (Connection invalid); terminating connection
iPhone com.apple.accessibility.AccessibilityUIServer(MobileAsset)[288] <Notice>: [MobileAssetError:29] Unable to copy asset information from https://mesu.apple.com/assets/ for asset type com.apple.MobileAsset.VoiceServices.CombinedVocalizerVoices
iPhone mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" }
```

**Oorzaak:** Er is een verbindingsprobleem tussen het apparaat en de Apple DEP-service.

#### <a name="resolution"></a>Oplossing
Los het verbindingsprobleem op of gebruik een andere netwerkverbinding om het apparaat in te schrijven. Mogelijk moet u contact opnemen met Apple als het probleem zich blijft voordoen.


## <a name="other-issues"></a>Overige problemen

### <a name="dep-enrollment-doesnt-start"></a>DEP-inschrijving wordt niet gestart
Wanneer u een met DEP beheerd apparaat inschakelt waaraan een inschrijvingsprofiel is toegewezen, wordt het Intune-inschrijvingsproces niet gestart.

**Oorzaak:** Het inschrijvingsprofiel wordt gemaakt voordat het DEP-token wordt geüpload naar Intune.

#### <a name="resolution"></a>Oplossing

1. Bewerk het inschrijvingsprofiel. U kunt het profiel aanpassen zoals u wilt. Het gaat erom de wijzigingstijd van het profiel bij te werken.
2. Door DEP beheerde apparaten synchroniseren: Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Tokens voor het inschrijvingsprogramma** > kies een token **Nu synchroniseren**. Er wordt een synchronisatieaanvraag verzonden naar Apple.

### <a name="dep-enrollment-stuck-at-user-login"></a>DEP-inschrijving is vastgelopen bij gebruikersaanmelding
Wanneer u een met DEP beheerd apparaat inschakelt waaraan een inschrijvingsprofiel is toegewezen, loopt de eerste configuratie vast nadat u de referenties hebt ingevoerd.

**Oorzaak:** Multi-Factor Authentication (MFA) is ingeschakeld. Momenteel werkt MFA niet tijdens inschrijving op DEP-apparaten.

#### <a name="resolution"></a>Oplossing
Schakel MFA uit en schrijf het apparaat opnieuw in.


## <a name="next-steps"></a>Volgende stappen

- [Problemen bij de apparaatinschrijving oplossen](../troubleshoot-device-enrollment-in-intune.md)
- [Stel een vraag op het Intune-forum](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Lees de blog van het Microsoft Intune Support Team](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Lees de blog Microsoft Enterprise Mobility and Security](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)
