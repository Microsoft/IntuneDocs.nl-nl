---
title: Problemen met het gebruik van SCEP-certificaatprofielen oplossen om certificaten in te richten met Microsoft Intune | Microsoft Docs
description: Problemen met het gebruik van SCEP door apparaten oplossen om certificaten aan te vragen voor gebruik met Intune, waaronder communicatie van apparaten met NDES, van NDES met certificeringsinstanties en van de Intune Certificate Connector met de Intune-service.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/30/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4496a5bbc6d5ee5134dc4e6a795494710ea6865d
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77515217"
---
# <a name="overview-for-troubleshooting-scep-certificate-profiles-with-microsoft-intune"></a>Overzicht van het oplossen van problemen met SCEP-certificaatprofielen met Microsoft Intune

Het gebruik van SCEP-certificaatprofielen (Simple Certificate Enrollment Protocol) kan lastig zijn om problemen op te lossen in Intune. In dit artikel vindt u een overzicht van het oplossen van problemen door:

- Een uitleg van de architectuur en de communicatiestroom van het SCEP-proces
- U te helpen beperken waar een probleem zich in die communicatiestroom voordoet
- De belangrijkste logboekbestanden aan te geven waarnaar wordt verwezen in volgende artikelen voor het oplossen van problemen met certificaatprofielen

De informatie in deze en de gerelateerde artikelen voor het oplossen van problemen met SCEP-certificaten zijn van toepassing op het gebruik van SCEP-certificaatprofielen met Android-, iOS/iPad- en Windows-apparaten. Soortgelijke informatie voor macOS is op dit moment niet beschikbaar.

Raadpleeg de volgende artikelen op support.microsoft.com om problemen met de registratieservice voor netwerkapparaten (NDES) op te lossen:

- [NDES-configuratie on-premises controleren op SCEP-certificaten in Intune](https://support.microsoft.com/help/4490130/ndes-configuration-on-premises-for-scep-certificates-in-intune)
- [Troubleshooting NDES configuration for use with Microsoft Intune certificate profiles]( https://support.microsoft.com/help/4459540/troubleshoot-ndes-configuration-for-use-with-intune) (Problemen oplossen met NDES-configuratie voor gebruik met Microsoft Intune-certificaatprofielen)

Controleer voordat u verdergaat of u voldoet aan de [vereisten voor het gebruik van SCEP-certificaatprofielen](certificates-scep-configure.md#prerequisites-for-using-scep-for-certificates), inclusief de implementatie van een basiscertificaat via een vertrouwd certificaatprofiel.

## <a name="scep-communication-flow-overview"></a>Overzicht van de SCEP-communicatiestroom

Op de volgende afbeelding ziet u een eenvoudig overzicht van het SCEP-communicatieproces in Intune.

![Stroom van SCEP-certificaatprofiel](../protect/media/troubleshoot-scep-certificate-profiles/scep-certificate-profile-flow.png)

1. [Een SCEP-certificaatprofiel implementeren](troubleshoot-scep-certificate-profile-deployment.md). Er wordt door Intune een controlereeks gegenereerd, waarvoor een specifieke gebruiker, een certificaatdoeleinde en een certificaattype nodig zijn.

2. [Communicatie van apparaat met NDES-server](troubleshoot-scep-certificate-device-to-ndes.md). Het apparaat gebruikt de URI voor NDES van het profiel om contact op te nemen met de NDES-server, zodat deze een vraag kan stellen.

3. [Communicatie van NDES met beleidsmodule](troubleshoot-scep-certificate-ndes-policy-module.md). NDES stuurt de vraag door naar de beleidsmodule van de Intune Certificate Connector op de server, die de aanvraag valideert.

4. [NDS met certificeringsinstantie](troubleshoot-scep-certificate-ndes-policy-module.md). NDES stuurt geldige aanvragen door om een certificaat aan de certificeringsinstantie (CA) uit te geven.

5. [Levering van certificaat aan het apparaat](troubleshoot-scep-certificate-delivery.md). Het certificaat wordt aan het apparaat geleverd.

6. [Rapportage van de implementatie aan Intune](troubleshoot-scep-certificate-reporting.md). De Intune Certificate Connector rapporteert de certificaatuitgifte aan Intune.

## <a name="log-files"></a>Logboekbestanden

Als u problemen wilt identificeren voor de werkstroom voor communicatie en inrichting van certificaten, bekijkt u de logboekbestanden van zowel de serverinfrastructuur als van apparaten. In latere secties voor het oplossen van problemen met SCEP-certificaatprofielen komen logboekbestanden aan de orde waarnaar in deze sectie wordt verwezen.

- [Infrastructuur- en serverlogboeken](#logs-for-on-premises-infrastructure)

Apparaatlogboeken zijn afhankelijk van het platform van het apparaat:  

- [iOS en iPadOS](#logs-for-ios-and-ipados-devices)
- [Android](#logs-for-android-devices)
- [Windows](#logs-for-windows-devices)

### <a name="logs-for-on-premises-infrastructure"></a>Logboeken voor on-premises infrastructuur
  
Een on-premises infrastructuur die ondersteuning biedt voor het gebruik van SCEP-certificaatprofielen voor certificaatimplementaties omvat de Microsoft Intune Certificate Connector, NDES die wordt uitgevoerd op een Windows-Server en de certificeringsinstantie.

Logboekbestanden voor deze rollen omvatten onder andere Windows Logboeken, certificaatconsoles en verschillende logboekbestanden die specifiek zijn voor de Intune Certificate Connector, NDES of andere functies en bewerkingen die deel uitmaken van de on-premises infrastructuur.

De volgende lijst bevat logboeken of consoles waarnaar wordt verwezen in volgende artikelen over SCEP-probleemoplossing. 

- **NDESConnector_date_time.svclog**:

  In dit logboek wordt communicatie van de Microsoft Intune Certificate Connector met de Intune-cloudservice weergegeven. U kunt de [viewer voor servicetraceringen](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe) gebruiken om dit logboekbestand weer te geven.

  Gerelateerde registersleutel: *HKLM\SW\Microsoft\MicrosoftIntune\NDESConnector\ConnectionStatus*

  Locatie: Op de server die als host fungeert voor NDES in *%program_files%\Microsoft intune\ndesconnectorsvc\logs\logs*

- **CertificateRegistrationPoint_date_time.svclog**:

  In dit logboek wordt de NDES-beleidsmodule die certificaataanvragen ontvangt en verifieert weergegeven. U kunt de [viewer voor servicetraceringen](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe) gebruiken om dit logboekbestand weer te geven.

  Locatie: Op de server die als host fungeert voor NDES in *%program_files%\Microsoft intune\ndesconnectorsvc\logs\logs*

- **NDESPlugin.log**:

  In dit logboek wordt het doorgeven van certificaataanvragen aan het certificaatregistratiepunt en de resulterende verificatie van deze aanvragen weergegeven.

  Locatie: Op de server die als host fungeert voor NDES in *%program_files%\Microsoft Intune\NDESPolicyModule\logs*

- **IIS-logboeken**:

  In IIS-logboeken worden de certificaataanvragen weergegeven van mobiele apparaten die NDES binnenkomen.

  Locatie: Op de server die als host fungeert voor NDES in *c:\inetpub\logs\LogFiles\W3SVC1*

- **Windows-logboek**:

  Dit logboek is handig bij het onderzoeken van IIS-problemen, zoals de groep van SCEP-toepassingen.

  Locatie: Op de server die als host fungeert voor NDES: voer **eventvwr. msc** uit om Windows Logboeken te openen




### <a name="logs-for-android-devices"></a>Logboeken voor Android-apparaten

Voor apparaten met Android gebruikt u het **Android-bedrijfsportal**, app-logboekbestand **OMADM. log**. Voordat u logboeken verzamelt en bekijkt, moet u ervoor zorgen dat [Uitgebreide logboekregistratie](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android) is ingeschakeld en reproduceert u vervolgens het probleem.

Zie [Logboeken uploaden en e-mailen via een USB-kabel](/intune-user-help/send-logs-to-your-it-admin-using-cable-android) voor informatie over het verzamelen van de OMADM.-logboeken van een apparaat.

U kunt [logboeken ook uploaden en e-mailen](/intune-user-help/send-logs-to-your-it-admin-by-email-android#upload-and-email-logs-from-microsoft-intune-app) naar de ondersteuningsafdeling.

### <a name="logs-for-ios-and-ipados-devices"></a>Logboeken voor iOS- en iPadOS-apparaten

Voor apparaten waarop iOS/iPadOS wordt uitgevoerd, gebruikt u logboeken voor foutopsporing en **Xcode** die wordt uitgevoerd op een Mac-computer:

1. Verbind het iOS/iPadOS-apparaat met Mac en ga vervolgens naar **Toepassingen** > **Hulpprogramma's** om de console-app te openen. 

2. Selecteer onder **Actie** de opties **Infoberichten opnemen** en  **Foutopsporingsberichten opnemen**.

   ![Logboekopties selecteren](../protect/media/troubleshoot-scep-certificate-profiles/message-options.png)

3. Reproduceer het probleem en sla de logboeken op in een tekstbestand:
   1. Selecteer **Bewerken** > **Alles selecteren** om alle berichten op het huidige scherm te selecteren en selecteer vervolgens **Bewerken** > **Kopiëren** om de berichten naar het klembord te kopiëren. 
   2. Open de toepassing TextEdit, plak de gekopieerde logboeken in een nieuw tekstbestand en sla het bestand op.


Het bedrijfsportal-logboek voor iOS- en iPadOS-apparaten bevat geen informatie over SCEP-certificaatprofielen.

### <a name="logs-for-windows-devices"></a>Logboeken voor Windows-apparaten

Voor apparaten waarop Windows wordt uitgevoerd, gebruikt u de Windows-gebeurtenislogboeken om problemen met registratie of apparaatbeheer op te sporen voor apparaten die u met Intune beheert.

Open **Logboeken** > **Logboeken Toepassingen en Services** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostics-Provider**

![Windows-gebeurtenislogboeken](../protect/media/troubleshoot-scep-certificate-profiles/windows-event-log.png)

## <a name="next-steps"></a>Volgende stappen

[Implementatie van SCEP-certificaatprofielen](troubleshoot-scep-certificate-profile-deployment.md) controleren 
