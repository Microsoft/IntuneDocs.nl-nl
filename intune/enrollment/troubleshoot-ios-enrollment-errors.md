---
title: Problemen met inschrijving van iOS-apparaten in Microsoft Intune oplossen
titleSuffix: Microsoft Intune
description: Suggesties voor het oplossen van problemen met een aantal van de meest voorkomende problemen bij het inschrijven van iOS-apparaten in intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/25/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1a02e403fdba34b576aa90b82062b7a602cbb517
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71735685"
---
# <a name="troubleshoot-ios-device-enrollment-problems-in-microsoft-intune"></a>Problemen met inschrijving van iOS-apparaten in Microsoft Intune oplossen

Dit artikel helpt intune-beheerders bij het registreren en oplossen van problemen bij het inschrijven van iOS-apparaten in intune.

## <a name="prerequisites"></a>Vereisten

Voordat u begint met het oplossen van problemen, is het belang rijk om enkele basis informatie te verzamelen. Deze informatie kan u helpen het probleem beter te begrijpen en de tijd te verkorten om een oplossing te vinden.

Verzamel de volgende informatie over het probleem:

- Wat is het exacte foutbericht?
- Waar wordt het fout bericht weer gegeven?
- Wanneer is het probleem begonnen? Heeft de inschrijving ooit gewerkt?
- Welk platform (Android, iOS, Windows) heeft het probleem?
- Hoeveel gebruikers zijn er betrokken? Zijn alle gebruikers betrokken of slechts een deel ervan?
- Hoeveel apparaten heeft het probleem? Zijn alle apparaten betrokken of slechts een deel ervan?
- Wat is de MDM-instantie? Als het System Center Configuration Manager, welke versie van Configuration Manager gebruikt u?
- Hoe wordt de inschrijving uitgevoerd? Kunt u uw eigen apparaat (BYOD) of Apple Device Enrollment Program (DEP) met inschrijvings profielen meenemen?

## <a name="error-messages"></a>Foutberichten

### <a name="profile-installation-failed-a-network-error-has-occurred"></a>De profielinstallatie is mislukt. Er is een netwerk fout opgetreden.

**Oorzaak:** Er is een niet-opgegeven probleem met iOS op het apparaat.

#### <a name="resolution"></a>Oplossing

1. Als u gegevens verlies in de volgende stappen wilt voor komen (het terugzetten van iOS verwijdert alle gegevens op het apparaat), moet u een back-up van uw gegevens maken.
2. Plaats het apparaat in de herstel modus en herstel het. Zorg ervoor dat u deze als een nieuw apparaat hebt ingesteld. Zie [https://support.apple.com/HT201263](https://support.apple.com/HT201263)voor meer informatie over het herstellen van Ios-apparaten.
3. Schrijf het apparaat opnieuw in.

### <a name="profile-installation-failed-connection-to-the-server-could-not-be-established"></a>De profielinstallatie is mislukt. Er kan geen verbinding met de server tot stand worden gebracht.

**Oorzaak:** Uw intune-Tenant is zo geconfigureerd dat alleen apparaten in bedrijfs eigendom worden toegestaan. 

#### <a name="resolution"></a>Oplossing
1. Meld u aan bij Azure Portal.
2. Selecteer **Meer Services**, zoek naar Intune en selecteer vervolgens **Intune**.
3. Selecteer **Apparaatinschrijving** > **Inschrijvingsbeperkingen**.
4. Onder **beperkingen voor het type apparaat**, selecteer de beperking die u wilt instellen **> Eigenschappen** > **platforms selecteren** > Selecteer **toestaan** voor **IOS**en klik vervolgens op **OK**.
5. Selecteer **platforms configureren**, selecteer **toestaan** voor IOS-apparaten in persoonlijk eigendom en klik vervolgens op **OK**.
6. Schrijf het apparaat opnieuw in.

### <a name="this-service-is-not-supported-no-enrollment-policy"></a>Deze service wordt niet ondersteund. Geen registratiebeleid.

**Oorzaak**: een Apple MDM-push certificaat is niet geconfigureerd in intune of het certificaat is ongeldig. 

#### <a name="resolution"></a>Oplossing

- Als het MDM-push certificaat niet is geconfigureerd, volgt u de stappen in [een Apple MDM-push certificaat ophalen](apple-mdm-push-certificate-get.md#steps-to-get-your-certificate).
- Als het MDM-push certificaat ongeldig is, volgt u de stappen in [Apple MDM-push certificaat vernieuwen](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate).

### <a name="company-portal-temporarily-unavailable-the-company-portal-app-encountered-a-problem-if-the-problem-persists-contact-your-system-administrator"></a>Bedrijfsportal is tijdelijk niet beschikbaar. Er is een probleem opgetreden in de app Bedrijfsportal. Neem contact op met uw systeembeheerder als het probleem zich blijft voordoen.

**Oorzaak:** De app Bedrijfsportal is verouderd of beschadigd.

#### <a name="resolution"></a>Oplossing
1. Verwijder de Bedrijfsportal-app van het apparaat.
2. Download en installeer de **Microsoft Intune Company Portal**-app uit de **App Store**.
3. Schrijf het apparaat opnieuw in.

### <a name="device-cap-reached"></a>Apparaatlimiet bereikt

**Oorzaak:** De gebruiker probeert meer apparaten in te schrijven dan de registratie limiet van het apparaat.

#### <a name="resolution"></a>Oplossing
1. Open de [intune-beheer portal](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview) > **apparaten** > **alle apparaten**en controleer het aantal apparaten dat de gebruiker heeft inge schreven.
    > [!NOTE]
    > U moet ook de betrokken gebruiker aanmelden bij de [intune-gebruikers Portal](https://portal.manage.microsoft.com/) en apparaten controleren die zijn Inge schreven. Er zijn mogelijk apparaten die worden weer gegeven in de [intune-gebruikers Portal](https://portal.manage.microsoft.com/) , maar niet in de [intune-beheer Portal](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview), maar deze apparaten tellen ook mee voor de registratie limiet van het apparaat.
2. Ga naar **beheer** > **beheer van mobiele apparaten** > **inschrijvings regels** > Controleer de limiet voor de inschrijving van apparaten. De limiet is standaard ingesteld op 15. 
3. Als het aantal apparaten dat is inge schreven, de limiet heeft bereikt, overbodige apparaten verwijdert of de registratie limiet van het apparaat verhoogt. Omdat elk geregistreerd apparaat een intune-licentie gebruikt, raden we u aan om altijd eerst overbodige apparaten te verwijderen.
4. Schrijf het apparaat opnieuw in.

### <a name="workplace-join-failed"></a>Workplace Join is mislukt

**Oorzaak:** De app Bedrijfsportal is verouderd of beschadigd.  

#### <a name="resolution"></a>Oplossing
1. Verwijder de Bedrijfsportal-app van het apparaat.
2. Download en installeer de **Microsoft Intune Company Portal**-app uit de **App Store**.
3. Schrijf het apparaat opnieuw in.

### <a name="user-license-type-invalid"></a>Het type gebruikers licentie is ongeldig

**Oorzaak:** De gebruiker die het apparaat probeert te registreren heeft geen geldige intune-licentie.

#### <a name="resolution"></a>Oplossing
1. Ga naar het [Microsoft 365-beheer centrum](https://portal.office.com/adminportal/home#/homepage)en kies **gebruikers** > **actieve gebruikers**.
2. Selecteer het betrokken gebruikers account > **product licenties** > **bewerken**.
3. Controleer of er een geldige intune-licentie is toegewezen aan deze gebruiker.
4. Schrijf het apparaat opnieuw in.

### <a name="user-name-not-recognized-this-user-account-is-not-authorized-to-use-microsoft-intune-contact-your-system-administrator-if-you-think-you-have-received-this-message-in-error"></a>Gebruikersnaam wordt niet herkend. Dit gebruikers account is niet gemachtigd om Microsoft Intune te gebruiken. Neem contact op met de systeem beheerder als u denkt dat u dit bericht hebt ontvangen.

**Oorzaak:** De gebruiker die het apparaat probeert te registreren heeft geen geldige intune-licentie.

1. Ga naar het [Microsoft 365-beheer centrum](https://portal.office.com/adminportal/home#/homepage)en kies **gebruikers** > **actieve gebruikers**.
2. Selecteer het betrokken gebruikers account en kies vervolgens **product licenties** > **bewerken**.
3. Controleer of er een geldige intune-licentie is toegewezen aan deze gebruiker.
4. Schrijf het apparaat opnieuw in.

### <a name="profile-installation-failed-the-new-mdm-payload-does-not-match-the-old-payload"></a>De profielinstallatie is mislukt. De nieuwe MDM-nettolading komt niet overeen met de oude nettolading.

**Oorzaak:** Er is al een beheer profiel op het apparaat geïnstalleerd.

#### <a name="resolution"></a>Oplossing

1. Open de **instellingen** op het IOS-apparaat > **algemene** > -**Apparaatbeheer**.
2. Tik op het bestaande beheer profiel en tik op **beheer verwijderen**.
3. Schrijf het apparaat opnieuw in.

### <a name="noenrollmentpolicy"></a>NoEnrollmentPolicy

**Oorzaak:** Het certificaat van de Apple Push Notification Service (APNs) ontbreekt, is ongeldig of is verlopen.

#### <a name="resolution"></a>Oplossing
Controleer of er een geldig APNs-certificaat is toegevoegd aan intune. Zie [IOS-en Mac-Apparaatbeheer instellen](https://docs.microsoft.com/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)voor meer informatie. 

### <a name="accountnotonboarded"></a>AccountNotOnboarded

**Oorzaak:** Er is een probleem met het APNs-certificaat (Apple Push Notification Service) dat is geconfigureerd in intune.

#### <a name="resolution"></a>Oplossing
Vernieuw het APNs-certificaat en schrijf het apparaat opnieuw in.

> [!IMPORTANT]
> Zorg ervoor dat u het APNs-certificaat vernieuwt. Vervang het APNs-certificaat niet. Als u het certificaat vervangt, moet u alle iOS-apparaten opnieuw inschrijven in intune. 

- Zie [Apple MDM-push certificaat vernieuwen](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate)voor informatie over het vernieuwen van het APNs-certificaat in de zelfstandige versie van intune.
- Als u het APNs-certificaat in intune Hybrid wilt vernieuwen met Configuration Manager, raadpleegt u [IOS Hybrid Device Management instellen met System Center Configuration Manager en Microsoft intune](https://docs.microsoft.com/sccm/mdm/deploy-use/enroll-hybrid-ios-mac).
- Zie [een apns-certificaat voor IOS-apparaten maken](https://support.office.com/article/Create-an-APNs-Certificate-for-iOS-devices-522b43f4-a2ff-46f6-962a-dd4f47e546a7)voor informatie over het vernieuwen van het apns-certificaat in Office 365.

### <a name="xpc_type_error-connection-invalid"></a>XPC_TYPE_ERROR-verbinding is ongeldig

Wanneer u een DEP-beheerd apparaat inschakelt dat is toegewezen aan een inschrijvings profiel, mislukt de registratie en wordt het volgende fout bericht weer gegeven:

```
asciidoc
mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" } }
iPhone mobileassetd[83] <Notice>: Client connection invalid (Connection invalid); terminating connection
iPhone com.apple.accessibility.AccessibilityUIServer(MobileAsset)[288] <Notice>: [MobileAssetError:29] Unable to copy asset information from https://mesu.apple.com/assets/ for asset type com.apple.MobileAsset.VoiceServices.CombinedVocalizerVoices
iPhone mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" }
```

**Oorzaak:** Er is een verbindings probleem tussen het apparaat en de Apple DEP-service.

#### <a name="resolution"></a>Oplossing
Los het verbindings probleem op of gebruik een andere netwerk verbinding om het apparaat in te schrijven. Mogelijk moet u contact opnemen met Apple als het probleem zich blijft voordoen.


## <a name="other-issues"></a>Overige problemen

### <a name="dep-enrollment-doesnt-start"></a>DEP-inschrijving wordt niet gestart
Wanneer u een DEP-beheerd apparaat inschakelt dat is toegewezen aan een inschrijvings profiel, wordt het intune-inschrijvings proces niet gestart.

**Oorzaak:** Het inschrijvings profiel wordt gemaakt voordat het DEP-token wordt geüpload naar intune.

#### <a name="resolution"></a>Oplossing

1. Bewerk het inschrijvings profiel. U kunt een wijziging aanbrengen in het profiel. Het doel is de wijzigings tijd van het profiel bij te werken.
2. Met DEP beheerde apparaten synchroniseren: Open de intune-Portal >- **beheer** > **beheer van mobiele apparaten** > **iOS** > **Device Enrollment Program** > **Nu synchroniseren**. Er wordt een synchronisatieaanvraag verzonden naar Apple.

### <a name="dep-enrollment-stuck-at-user-login"></a>DEP-inschrijving is vastgelopen bij gebruikers aanmelding
Wanneer u een DEP-beheerd apparaat inschakelt dat is toegewezen aan een inschrijvings profiel, wordt de eerste Setup-stickes nadat u referenties hebt ingevoerd.

**Oorzaak:** Multi-factor Authentication (MFA) is ingeschakeld. Momenteel werkt MFA niet tijdens inschrijving op DEP-apparaten.

#### <a name="resolution"></a>Oplossing
Schakel MFA uit en schrijf het apparaat opnieuw in.

## <a name="next-steps"></a>Volgende stappen

- [Problemen bij de apparaatinschrijving oplossen](../troubleshoot-device-enrollment-in-intune.md)
- [Stel een vraag op het Intune-forum](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Raadpleeg de blog van het Microsoft Intune-ondersteunings team](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Bekijk de micro soft Enter prise Mobility and Security-Blog](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)
