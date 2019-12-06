---
title: Problemen met logboeken met W-Fi-apparaatprofielen oplossen en bekijken in Microsoft Intune - Azure | Microsoft Docs
description: Problemen met Wi-Fi-apparaatconfiguratieprofielen in Android-, iOS- en Windows-apparaten begrijpen en oplossen in Microsoft Intune. Bekijk de logboeken en zie een aantal veelvoorkomende problemen en mogelijke oplossingen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 77f5787509438ec3280f29be8449d78979806042
ms.sourcegitcommit: 16a9109b4028589c17695d41271ca4fee8b1d697
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/26/2019
ms.locfileid: "74542660"
---
# <a name="troubleshoot-wi-fi-device-configuration-profiles-in-microsoft-intune"></a>Problemen met Wi-Fi-apparaatconfiguratieprofielen oplossen in Microsoft Intune

In Intune kunt u configuratieprofielen voor apparaten maken die verbindingsinstellingen voor uw Wi-Fi-netwerk bevatten. Gebruik deze instellingen om de Android-, iOS- en Windows-apparaten van gebruikers te verbinden met het netwerk van de organisatie.

In dit artikel ziet u hoe een Wi-Fi-profiel eruitziet wanneer het op apparaten is toegepast. Het bevat ook logboekgegevens, veelvoorkomende problemen en meer. Gebruik dit artikel bij het oplossen van problemen met uw Wi-Fi-profielen.

Zie [Wi-Fi-instellingen toevoegen en gebruiken op uw apparaten](wi-fi-settings-configure.md) voor meer informatie over Wi-Fi-profielen in Intune.

## <a name="before-you-begin"></a>Voordat u begint

In de voorbeelden in dit artikel wordt SCEP-certificaatverificatie voor de Intune-profielen gebruikt. Ook wordt ervan uitgegaan dat de vertrouwde basis- en SCEP-profielen correct op het apparaat worden uitgevoerd.

## <a name="android"></a>Android

In deze sectie maken we gebruik van de eindgebruikerservaring bij het installeren van de configuratieprofielen op een Android-apparaat.

### <a name="end-user-experience-example"></a>Voorbeeld van eindgebruikerservaring

In dit scenario wordt een Nokia 6.1-apparaat gebruikt. Voordat het Wi-Fi-profiel op het apparaat wordt geïnstalleerd, installeert u de vertrouwde basis- en SCEP-profielen.

1. Eindgebruikers ontvangen een melding om het vertrouwde basiscertificaatprofiel te installeren:

    > [!div class="mx-imgBorder"]
    > ![Voorbeeld van een Bedrijfsportal-appmelding in Android voor het installeren van een vertrouwd basiscertificaatprofiel](./media/troubleshoot-wi-fi-profiles/android-end-user-company-portal-trusted-root.png)

2. De volgende melding vraagt het SCEP-certificaatprofiel te installeren:

    > [!div class="mx-imgBorder"]
    > ![Voorbeeld van een Bedrijfsportal-appmelding in Android voor het installeren van een SCEP-certificaatprofiel](./media/troubleshoot-wi-fi-profiles/android-end-user-company-portal-scep-certificate.png)

    > [!TIP]
    > Wanneer u een Android-apparaat gebruikt dat door een apparaatbeheerder wordt beheerd, kunnen er meerdere certificaten worden weergegeven. Wanneer een certificaatprofiel wordt ingetrokken of verwijderd, blijft het certificaat op het apparaat aanwezig. In dit scenario selecteert u het nieuwste certificaat. Het is doorgaans het laatste certificaat dat in de lijst wordt vermeld.
    >
    > Deze situatie doet zich niet voor op Android Enterprise- en Samsung Knox-apparaten. Zie [Apparaten met een Android-werkprofiel beheren](../enrollment/android-enterprise-overview.md) en [SCEP- en PKCS-certificaten verwijderen](../protect/remove-certificates.md#android-knox-devices) voor meer informatie.

3. Vervolgens ontvangen gebruikers een melding om het Wi-Fi-profiel te installeren:

    > [!div class="mx-imgBorder"]
    > ![Voorbeeld van een Bedrijfsportal-appmelding in Android voor het installeren van een SCEP-certificaatprofiel](./media/troubleshoot-wi-fi-profiles/android-end-user-install-wifi-profile.png)

4. Wanneer dit is voltooid, wordt de Wi-Fi-verbinding weergegeven als een opgeslagen netwerk:

    > [!div class="mx-imgBorder"]
    > ![Wi-Fi-verbinding wordt weergegeven als een opgeslagen netwerk](./media/troubleshoot-wi-fi-profiles/android-end-user-saved-networks.png)

### <a name="review-company-portal-app-logs"></a>Logboeken van Bedrijfsportal-app bekijken

In Android worden de activiteiten van het op het apparaat geïnstalleerde Wi-Fi-profiel beschreven in het bestand **Omadmlog.log**. U kunt maximaal vijf Omadmlog-logboekbestanden hebben. Zorg ervoor dat u de tijdstempel van de laatste synchronisatie krijgt, zodat u de bijbehorende logboekvermeldingen kunt vinden.

In het volgende voorbeeld gebruikt u [CMTrace](https://docs.microsoft.com/configmgr/core/support/cmtrace) om de logboeken te lezen en zoekt u naar wifimgr:

> [!div class="mx-imgBorder"]
> ![Wi-Fi-verbinding wordt weergegeven als een opgeslagen netwerk](./media/troubleshoot-wi-fi-profiles/android-cmtrace-filter-wifimgr.png)

In het volgende logboek worden de zoekresultaten weergegeven en wordt het toegepaste Wi-Fi-profiel weergegeven:

```log
2019-08-01T19:22:46.7340000    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Starting to parse Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:46.7490000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Starting to parse OneX from Wifi XML.
2019-08-01T19:22:46.8100000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Completed parsing OneX from Wifi XML.
2019-08-01T19:22:46.8209999    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Completed parsing Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:46.8240000    INFO    com.microsoft.omadm.utils.CertificateSelector    15118    04142    Selected ca certificate with alias: 'user:205xxxxx.0' and thumbprint '<thumbprint>'.
2019-08-01T19:22:47.0990000    VERB    com.microsoft.omadm.platforms.android.certmgr.CertificateChainBuilder    15118    04142    Complete certificate chain built with Complete certs.
2019-08-01T19:22:47.1010000    VERB    com.microsoft.omadm.utils.CertUtils    15118    04142    1 cert(s) matched criteria: User<ID>[i:<ID>,17CECEA1D337FAA7D167AD83A8CC7A8FCBF9xxxx;eku:1.3.6.1.5.5.7.3.1,1.3.6.1.5.5.7.3.2]
2019-08-01T19:22:47.1090000    VERB    com.microsoft.omadm.utils.CertUtils    15118    04142    0 cert(s) excluded by criteria:
2019-08-01T19:22:47.1110000    INFO    com.microsoft.omadm.utils.CertificateSelector    15118    04142    Selected client cert with alias 'User<ID>' and requestId 'ModelName=<ModelName>%2FLogicalName_<LogicalName>;Hash=-912418295'.
2019-08-01T19:22:47.4120000    VERB    com.microsoft.omadm.Services    15118    04142    Successfully applied, enabled and saved wifi profile '<profile ID>'
2019-08-01T19:22:47.4240000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Starting to parse OneX from Wifi XML.
2019-08-01T19:22:47.4910000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Completed parsing OneX from Wifi XML.
2019-08-01T19:22:47.4970000    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Starting to parse Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:47.5080000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Starting to parse OneX from Wifi XML.
2019-08-01T19:22:47.5820000    VERB    com.microsoft.omadm.platforms.android.wifimgr.OneX    15118    04142    Completed parsing OneX from Wifi XML.
2019-08-01T19:22:47.5900000    VERB    com.microsoft.omadm.platforms.android.wifimgr.WifiProfile    15118    04142    Completed parsing Wifi Profile XML with name '<profile ID>'.
2019-08-01T19:22:47.5910000    INFO    com.microsoft.omadm.platforms.android.wifimgr.WifiProfileManager    15118    04142    Applied profile <profile ID>

```

## <a name="ios"></a>iOS

Nadat het Wi-Fi-profiel op het apparaat is geïnstalleerd, wordt dit weergegeven in het **beheerprofiel**:

> [!div class="mx-imgBorder"]
> ![Beheerprofiel op iOS-apparaat](./media/troubleshoot-wi-fi-profiles/ios-management-profile.png)

> [!div class="mx-imgBorder"]
> ![Wi-Fi-verbinding wordt weergegeven als een Wi-Fi-netwerk op iOS-apparaat](./media/troubleshoot-wi-fi-profiles/ios-wifi-connection-in-management-profile.png)

### <a name="review-the-ios-console-and-device-logs"></a>De iOS-console en apparaatlogboeken bekijken

Op iOS-apparaten bevat het logboek van de Bedrijfsportal-app geen informatie over Wi-Fi-profielen. Als u de installatiegegevens van uw Wi-Fi-profielen wilt bekijken, gebruikt u de logboeken van de console of het apparaat:

1. Verbind het iOS-apparaat met de Mac. Ga naar **Toepassingen** > **Hulpprogramma's** en open de console-app.
2. Selecteer onder **Actie** de opties **Infoberichten opnemen** en **fout Foutopsporingsberichten opnemen**:

    > [!div class="mx-imgBorder"]
    > ![Infoberichten opnemen en Foutopsporingsgegevens opnemen in iOS-console-app](./media/troubleshoot-wi-fi-profiles/ios-console-app-include-info-messages-debug-messages.png)

3. Reproduceer het scenario en sla de logboeken op in een tekstbestand:

    1. Selecteer alle berichten op het huidige scherm: **Bewerken** > **Alles selecteren**.
    2. Kopieer de berichten: **Bewerken** > **Kopiëren**.
    3. Plak de logboekgegevens in een teksteditor en sla het bestand op.

4. Doorzoek het opgeslagen logboekbestand op gedetailleerde informatie. Wanneer het profiel is geïnstalleerd, ziet uw uitvoer er ongeveer uit als in het volgende logboek:

    ```log
    Line 390870: debug    11:19:58.994815 -0400    profiled    Adding dependent www.windowsintune.com.wifi.Contoso to parent Microsoft.Profiles.MDM in domain ManagingProfileToManagedProfile to system\
    Line 390872: debug    11:19:58.995210 -0400    profiled    Adding dependent Microsoft.Profiles.MDM to parent www.windowsintune.com.wifi.Contoso in domain ManagedProfileToManagingProfile to system\
    Line 392346: default    11:19:59.360460 -0400    profiled    Profile \'93www.windowsintune.com.wifi.Contoso\'94 installed.\
    ```

## <a name="windows"></a>Windows

Als het Wi-Fi-profiel is geïnstalleerd, gaat op het apparaat naar **Instellingen** > **Accounts** > **Toegang tot werk of school**. Selecteer uw account > **Info**:

> [!div class="mx-imgBorder"]
> ![Uw werk- of schoolaccount openen en gegevens selecteren op een Windows-apparaat](./media/troubleshoot-wi-fi-profiles/windows-access-work-school-info.png)

In **gebieden die door Microsoft worden beheerd**, wordt **Wi-Fi** weergegeven:

> [!div class="mx-imgBorder"]
> ![Controleren of Wi-Fi in Windows is vermeld in gebieden die door Microsoft worden beheerd](./media/troubleshoot-wi-fi-profiles/windows-wifi-areas-managed-by-microsoft.png)

Als u de Wi-Fi-verbinding wilt zien, gaat u naar **Instellingen** > **Netwerk en Internet**  > **Wi-Fi**:

> [!div class="mx-imgBorder"]
> ![In Windows controleren of de Wi-Fi-verbinding als een bekend netwerk in instellingen staat](./media/troubleshoot-wi-fi-profiles/windows-wifi-connection-known-networks.png)

### <a name="review-event-viewer-logs"></a>Logboeken in Logboeken bekijken

Op Windows-apparaten worden de gegevens over Wi-Fi-profielen vastgelegd in Logboeken:

1. Open de **Logboeken**-app.
2. Selecteer in het menu **Weergave** **Logboeken voor analyseren en foutopsporing weergeven**.
3. Vouw uit: **Logboeken Toepassingen en Services** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Beheerder**

De uitvoer zier eruit als die van de volgende logboeken:

```log
Log Name:      Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider/Admin
Source:        Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider
Date:          8/7/2019 8:01:41 PM
Event ID:      1506
Task Category: (1)
Level:         Information
Keywords:      (2)
User:          SYSTEM
Computer:      <Computer Name>
Description:
WiFiConfigurationServiceProvider: Node set value, type: (0x4), Result: (The operation completed successfully.).
```

## <a name="common-issues"></a>Veelvoorkomende problemen

### <a name="issue-1-the-wi-fi-profile-isnt-deployed-to-the-device"></a>Probleem 1: Het Wi-Fi-profiel wordt niet op het apparaat geïmplementeerd

- Bevestig dat het Wi-Fi-profiel is toegewezen aan de juiste groep:

    1. Selecteer in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **Configuratieprofielen**.
    2. Selecteer het gewenste profiel > **Toewijzingen**. Bevestig dat de geselecteerde groepen juist zijn.
    3. Selecteer in Endpoint Manager **Ondersteuning en probleemoplossing**. Bekijk de informatie in **Toewijzingen**.

- Selecteer in Endpoint Manager **Ondersteuning en probleemoplossing**. Bevestig dat het apparaat kan worden gesynchroniseerd met Intune door de **laatste inchecktijd** te controleren.

- Als het Wi-Fi-profiel is gekoppeld aan de vertrouwde basis- en SCEP-profielen, bevestigt u dat beide profielen op het apparaat. zijn geïmplementeerd. Het Wi-Fi-profiel is afhankelijk van deze profielen.

- In apparaten met Windows 10 en nieuwere apparaten raadpleegt u het logboek met diagnostische gegevens over MDM:

  1. Ga naar **Instellingen** > **Accounts** > **Toegang tot werk of school**.
  2. Selecteer uw werk- of schoolaccount > **Info**.
  3. Selecteer onder aan de pagina **Instellingen** de optie **Rapport maken**.
  4. Er wordt een venster geopend waarin het pad naar de logboekbestanden wordt weergegeven. Selecteer **Exporteren**.
  5. Ga naar het `\Users\Public\Documents\MDMDiagnostics`-pad en bekijk het rapport:

      > [!div class="mx-imgBorder"]
      > ![Voorbeeld van diagnostische gegevens over MDM waarin WiFi-profielconfiguratie op Windows 10-apparaten wordt weergeven](./media/troubleshoot-wi-fi-profiles/windows-mdm-diagnostic-info.png)

  > [!TIP]
  > Zie [Diagnose MDM failures in Windows 10](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) (MDM-fouten in Windows 10 diagnosticeren) voor meer informatie.

- OP Android-apparaten: als de vertrouwde basis- en SCEP-profielen niet op het apparaat zijn geïnstalleerd, ziet u de volgende vermelding in het Omadmlog-bestand van de Bedrijfsportal-app:

  ``` log
  2019-08-01T19:18:13.5120000    INFO    com.microsoft.omadm.platforms.android.wifimgr.WifiProfileManager    15118    04105    Skipping Wifi profile <profile ID> because it is pending certificates.
  ```

  - Wanneer de vertrouwde basis- en SCEP-profielen zich op het Android-apparaat bevinden en compatibel zijn, bevindt het Wi-Fi-profiel zich mogelijk niet op het apparaat. Dit probleem treedt op wanneer de **CertificateSelector**-provider van de Bedrijfsportal-app geen certificaat vindt dat overeenkomt met de opgegeven criteria. De specifieke criteria kunnen zich in het certificaatsjabloon of in het SCEP-profiel bevinden.

    Als het overeenkomende certificaat niet wordt gevonden, worden de certificaten op het apparaat niet geïnstalleerd. Het Wi-Fi-profiel wordt niet toegepast omdat het niet over het juiste certificaat beschikt. In dit scenario ziet u de volgende vermelding in het Omadmlog-bestand van de Bedrijfsportal-app:

    ` Skipping Wifi profile <profile ID> because it is pending certificates.`

    In het volgende voorbeeld van het logboek worden certificaten weergegeven die worden uitgesloten, omdat de criteria **Any Purpose** EKU (Extended Key Usage) zijn opgegeven. De certificaten die zijn toegewezen aan het apparaat, beschikken echter niet over deze EKU:

    ```log
    2018-11-27T21:10:37.6390000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    Excluding cert with alias User<ID1> and requestId <requestID1> as it does not have any purpose EKU.
    2018-11-27T21:10:37.6400000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    Excluding cert with alias User<ID2> and requestId <requestID2> as it does not have any purpose EKU.
    2018-11-27T21:10:37.6400000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    0 cert(s) matched criteria:
    2018-11-27T21:10:37.6400000    VERB     com.microsoft.omadm.utils.CertUtils      14210    00948    2 cert(s) excluded by criteria:
    2018-11-27T21:10:37.6400000    INFO       com.microsoft.omadm.platforms.android.wifimgr.WifiProfileManager       14210                00948     Skipping Wifi profile <profile ID> because it is pending certificates.
    ```

    In het volgende voorbeeld ziet u het SCEP-profiel **Any Purpose** EKU. Maar het is niet ingevoerd in het certificaatsjabloon in de certificeringsinstantie (CA). U kunt het probleem oplossen door de optie **Any Purpose** aan het certificaatsjabloon toe te voegen. Of verwijder de optie **Any Purpose** uit het SCEP-profiel.

    > [!div class="mx-imgBorder"]
    > ![Voeg op Android Any Purpose toe de certificaatsjabloon in de certificeringsinstantie](./media/troubleshoot-wi-fi-profiles/android-add-any-purpose-eku.png)

    > [!div class="mx-imgBorder"]
    > ![Voeg op Android Any Purpose toe aan het configuratieprofiel van het SCEP-certificaat in Intune](./media/troubleshoot-wi-fi-profiles/android-any-purpose-scep-device-config-profile.png)

  - Bevestig dat alle vereiste certificaten in de volledige certificaatketen zich op het Android-apparaat bevinden. Anders kan het Wi-Fi-profiel niet op het apparaat worden geïnstalleerd. Zie [Missing intermediate certificate authority](https://developer.android.com/training/articles/security-ssl#MissingCa) (Ontbrekende tussenliggende certificeringsinstantie) voor meer informatie (hiermee wordt de website van Android geopend).
  - Filter Omadmlog met trefwoorden om naar informatie te zoeken, bijvoorbeeld welk certificaat wordt gebruikt in het Wi-Fi-profiel en of het profiel is toegepast.

    Gebruik bijvoorbeeld [CMTrace](https://docs.microsoft.com/sccm/core/support/cmtrace) om de logboeken te lezen. Gebruik de zoekreeks om op wifimgr te filteren:

    > [!div class="mx-imgBorder"]
    > ![Op CMTrace filteren om naar WiFiMgr-configuratieprofielen op Android-apparaten te zoeken](./media/troubleshoot-wi-fi-profiles/cmtrace-filter-wifimgr.png)

    De uitvoer ziet er ongeveer uit zoals in het volgende logboek:

    > [!div class="mx-imgBorder"]
    > ![Voorbeeld van CMTrace-logboekuitvoer waarin wordt getoond dat WiFi Intune-configuratieprofiel op apparaten is toegepast](./media/troubleshoot-wi-fi-profiles/cmtrace-sample-log-output.png)

    Als er een fout in het logboek wordt weergeven, kopieert u het tijdstempel van de fout en maakt u het filter voor het logboek ongedaan. Gebruik vervolgens de optie find met de tijdstempel om te zien wat er is gebeurd vóór de fout.

### <a name="issue-2-the-wi-fi-profile-is-deployed-to-the-device-but-the-device-cant-connect-to-the-network"></a>Probleem 2: Het Wi-Fi-profiel wordt geïmplementeerd op het apparaat, maar het apparaat kan geen verbinding maken met het netwerk

Dit probleem wordt meestal veroorzaakt door iets buiten Intune. Met de volgende taken krijgt u inzicht in verbindingsproblemen en kunt u ze oplossen:

- Maak handmatig verbinding met het netwerk met behulp van een certificaat met dezelfde criteria als in het Wi-Fi-profiel.

  Als u verbinding kunt maken, bekijkt u de eigenschappen van het certificaat in de handmatige verbinding. Werk vervolgens het Wi-Fi-profiel van Intune bij met dezelfde certificaateigenschappen.
- Connectiviteitsfouten worden gewoonlijk vastgelegd in het logboek van de RADIUS-server. Hier moet bijvoorbeeld staan of het apparaat heeft geprobeerd verbinding te maken met het Wi-Fi-profiel.

## <a name="need-more-help"></a>Meer hulp nodig?

- Kijk op de [Intune user forums](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc) (Intune-gebruikersforums) of [vraag ondersteuning van Microsoft](../fundamentals/get-support.md).

- Raadpleeg de volgende artikelen voor meer informatie over Wi-Fi-profielen in Microsoft Intune:

  - Wi-Fi-instellingen toevoegen voor apparaten met [Android](wi-fi-settings-android.md), [iOS](wi-fi-settings-ios.md) en [Windows 10 en hoger](wi-fi-settings-windows.md).
  - [Support Tip - How to configure NDES for SCEP certificate deployments in Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-How-to-configure-NDES-for-SCEP-certificate/ba-p/455125) (Tip voor ondersteuning: NDES configureren voor SCEP-certificaatimplementaties in Intune)
  - Los problemen op met de [implementatie van SCEP-certificaatprofielen](https://support.microsoft.com/help/4526725/troubleshooting-scep-profile-deployment-to-android-devices-in-intune) en [NDES-configuratie](https://support.microsoft.com/help/4459540/troubleshoot-ndes-configuration-for-use-with-intune).

- Zie de officiële blogs voor het laatste nieuws, informatie en technische tips:
  - [Microsoft Intune Support Team blog](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess) (Blog van het ondersteuningsteam van Microsoft Intune)
  - [Microsoft Enterprise Mobility and Security blog](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/bg-p/enterprisemobilityandsecurity) (Blog over Microsoft Enterprise Mobility and Security)

## <a name="next-steps"></a>Volgende stappen

[Profielen bewaken](device-profile-monitor.md).
