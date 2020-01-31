---
title: Problemen met app-installatie oplossen
titleSuffix: Microsoft Intune
description: Gebruik het Microsoft Intune-deelvenster voor probleemoplossing om u te helpen bij het oplossen van installatieproblemen.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/21/2020
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: be66f99006b06dce9f9bfe21eafa9f2be302e7b9
ms.sourcegitcommit: 70b40aa4743c8396f8d6a0163893c4a337d67c48
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2020
ms.locfileid: "76540976"
---
# <a name="troubleshoot-app-installation-issues"></a>Problemen met app-installatie oplossen

Op apparaten die met Microsoft Intune MDM worden beheerd, mislukken app-installaties wel eens. Als deze apps niet kunnen worden geïnstalleerd, is het soms lastig om de reden van het probleem te achterhalen of om het probleem op te lossen. Microsoft Intune biedt details van app-installatiefouten. Zo kunnen helpdeskmedewerkers en Intune-beheerders app-informatie bekijken om de hulpverzoeken van gebruikers te beantwoorden. Het deelvenster voor probleemoplossing binnen Intune biedt foutdetails, waaronder details over beheerde apps op een apparaat van een gebruiker. Er worden details van de end-to-end-levenscyclus van een app van elk afzonderlijk apparaat getoond in het deelvenster **Beheerde apps**. U kunt installatieproblemen bekijken, zoals wanneer de app was gemaakt, bewerkt, ingericht op en geleverd aan een apparaat. 

> [!NOTE]
> Zie [Naslaginformatie voor installatiefouten voor Intune-apps](~/apps/app-install-error-codes.md) voor specifieke informatie over foutcodes bij de installatie van apps.

## <a name="app-troubleshooting-details"></a>Details van de app-probleemoplossing

Intune biedt details van app-probleemoplossing op basis van de geïnstalleerde apps op een specifiek apparaat van een gebruiker.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Selecteer **Problemen oplossen + ondersteuning**.
4. Klik op **Gebruiker selecteren** om een gebruiker te selecteren waarvoor er problemen opgelost moeten worden. Het deelvenster **Gebruikers selecteren** wordt weergegeven.
5. Selecteer de gebruiker door een naam of e-mailadres te typen. Klik onder aan het deelvenster op **Selecteren**. De informatie voor het oplossen van problemen voor de gebruiker wordt weergegeven in het deelvenster **Probleemoplossing**. 
6. Selecteer in de lijst **Apparaten** het apparaat waarbij u problemen wilt oplossen.
    ![Het deelvenster Intune-probleemoplossing.](./media/troubleshoot-app-install/troubleshoot-app-install-01.png)
7. Selecteer **Beheerde apps** in het deelvenster van het geselecteerde apparaat. Er wordt een lijst met beheerde apps weergegeven.
    ![Details van een specifiek apparaat dat door Intune wordt beheerd.](./media/troubleshoot-app-install/troubleshoot-app-install-02.png)
8. Selecteer een app in de lijst waarbij de **Installatiestatus** een fout aangeeft.
    ![Een geselecteerde app waarbij een installatiefout wordt aangegeven.](./media/troubleshoot-app-install/troubleshoot-app-install-03.png)

    > [!Note]  
    > Dezelfde app kan worden toegewezen aan meerdere groepen, maar met verschillende beoogde acties (intenties) voor de app. Een opgeloste intentie voor een app wordt bijvoorbeeld weergegeven als **uitgesloten** als de app voor een gebruiker is uitgesloten tijdens de app-toewijzing. Raadpleeg [Hoe conflicten tussen app-intenties worden opgelost](apps-deploy.md#how-conflicts-between-app-intents-are-resolved) voor meer informatie.<br><br>
    > Als er een installatiefout bij een vereiste app optreedt, kunt u noch uw helpdesk het apparaat synchroniseren en opnieuw proberen de app te installeren.

De details van de app-installatieproblemen geven het probleem aan. U kunt deze details gebruiken om de beste actie vast te stellen waarmee het probleem wordt opgelost. Zie [Installatiefouten voor Android-apps](app-install-error-codes.md#android-app-installation-errors) en [Installatiefouten voor iOS-apps](app-install-error-codes.md#ios-app-installation-errors) voor meer informatie over het oplossen van problemen met appinstallatie.

> [!Note]  
> U kunt het deelvenster **Probleemoplossing** ook openen door in uw browser naar het volgende adres te gaan: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="user-group-targeted-app-installation-does-not-reach-device"></a>Het apparaat is niet bereikbaar voor de installatie van de doel-app voor de gebruikersgroep
U kunt een van de volgende acties uitvoeren als u problemen hebt met het installeren van apps:
- Controleer of de app is geïmplementeerd met de intentie **Beschikbaar** en of de gebruiker toegang heeft tot de bedrijfsportal met het apparaattype dat door de app wordt ondersteund als de app niet in de bedrijfsportal wordt weergegeven.
- Op Windows BYOD-apparaten moet de gebruiker een werkaccount toevoegen aan het apparaat.
- Controleer of de gebruiker de limiet voor AAD-apparaten overschrijdt:
  1. Navigeer naar [Azure Active Directory-apparaatinstellingen](https://portal.azure.com/#pane/Microsoft_AAD_IAM/DevicesMenupane/DeviceSettings/menuId).
  2. Noteer de waarde die is ingesteld voor **Maximumaantal apparaten per gebruiker**.
  3. Navigeer naar [Azure Active Directory-gebruikers](https://portal.azure.com/#pane/Microsoft_AAD_IAM/UsersManagementMenupane/AllUsers).
  4. Selecteer de betrokken gebruiker en klik op **Apparaten**.
  5. Verwijder alle verouderde records die niet meer nodig zijn als de gebruiker de ingestelde limiet overschrijdt.
- Controleer voor iOS DEP-apparaten of de gebruiker in het deelvenster Overzicht van Intune-apparaten wordt vermeld als **Geregistreerd door gebruiker**. Implementeer een configuratiebeleid voor de Intune-bedrijfsportal als er n.v.t. wordt weergegeven. Zie [De bedrijfsportal-app configureren](app-configuration-policies-use-ios.md#configure-the-company-portal-app-to-support-ios-dep-devices) voor meer informatie.

## <a name="win32-app-installation-troubleshooting"></a>Problemen met de installatie van Win32-app oplossen

Selecteer de Win32-app die is geïmplementeerd met behulp van de Intune-beheerextensie. U kunt de optie **Logboeken verzamelen** selecteren wanneer de installatie van de Win32-app is mislukt. 

> [!IMPORTANT]
> De optie **Logboeken verzamelen** wordt niet ingeschakeld wanneer de Win32-app succesvol is geïnstalleerd op het apparaat.<p>Voordat u logboekgegevens over de Win32-app kunt verzamelen, moet de Intune-beheerextensie geïnstalleerd zijn op de Windows-client. De Intune-beheerextensie wordt geïnstalleerd wanneer een PowerShell-script of een Win32-app wordt geïmplementeerd in een gebruikers- of apparaatbeveiligingsgroep. Zie [Intune-beheerextensie - vereisten](intune-management-extension.md#prerequisites). voor meer informatie.

### <a name="collect-log-file"></a>Logboekbestand verzamelen

Volg eerst de stappen in de sectie [Details van de app-probleemoplossing](troubleshoot-app-install.md#app-troubleshooting-details) om de installatielogboeken van de Win32-app te verzamelen. Ga vervolgens verder met de volgende stappen:

1. Klik op de optie **Logboeken verzamelen** in het deelvenster **Installatiegegevens**.

    <image alt="Win32 app installation details - Collect log option" src="./media/troubleshoot-app-install/troubleshoot-app-install-04.png" width="500" />

2. Geef bestandspaden met logboekbestandsnamen op om te beginnen met het verzamelen van logboekbestanden en klik op **OK**.

    > [!NOTE]
    > Het verzamelen van logboeken duur minder dan twee uur. Ondersteunde bestandstypen: *.log, .txt, .dmp, .cab, .zip, .xml, .evtx, en .evtl*. Er zijn maximaal 25 bestandspaden toegestaan.

3. Zodra de logboekbestanden zijn verzameld, kunt u de koppeling **Logboeken** selecteren om de logboekbestanden te downloaden.

    <image alt="Win32 app log details - Download logs" src="./media/troubleshoot-app-install/troubleshoot-app-install-05.png" width="500" />

    > [!NOTE]
    > Er wordt een melding weergegeven om aan te geven dat de app-logboeken zijn verzameld.

#### <a name="win32-log-collection-requirements"></a>Vereisten voor het verzamelen van Win32-logboeken

Er zijn specifieke vereisten voor het verzamelen van logboekbestanden:

- U moet het volledige pad naar het logboekbestand opgeven. 
- U kunt omgevingsvariabelen voor het verzamelen van logboeken opgeven, bijvoorbeeld:<br>
  *%PROGRAMFILES%, %PROGRAMDATA% %PUBLIC%, %WINDIR%, %TEMP%, %TMP%*
- Alleen precieze bestandsextensies zijn toegestaan, zoals:<br>
  *.log, .txt, .dmp, .cab, .zip, .xml*
- U kunt maximaal een logboekbestand van 60 MB of 25 bestanden uploaden, wat zich het eerst voordoet. 
- Het verzamelen van Win32-app-installatielogboeken is ingeschakeld voor apps die voldoen aan de vereiste, beschikbare en app-verwijdertoewijzingsintentie.
- Opgeslagen logboeken worden versleuteld om persoonlijke identificeerbare gegevens in de logboeken te beveiligen.
- Voeg bij het openen van ondersteuningstickets voor Win32-app-fouten de gerelateerde foutenlogboeken bij met behulp van de bovenstaande stappen.

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>Het oplossen van problemen met apps van Microsoft Store

De informatie in het Engelstalige onderwerp [Troubleshooting packaging, deployment, and query of Windows Store apps](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) (Het oplossen van problemen bij het verpakken, implementeren en zoeken van Microsoft Store-apps) helpt u om algemene problemen op te lossen die optreden tijdens het installeren van apps in Microsoft Store, hetzij met behulp van Intune of op een andere manier.

## <a name="app-troubleshooting-resources"></a>Resources voor het oplossen van problemen met apps
- [Visio en Project implementeren als onderdeel van uw Office Pro Plus-implementatie](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Deploying-Visio-and-Project-as-part-of-your-Office/ba-p/701795)
- [Actie ondernemen om te zorgen dat MSfB-apps worden geïmplementeerd via Intune-installatie op Windows 10 1903](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Take-Action-to-Ensure-MSfB-Apps-deployed-through/ba-p/658864)
- [Problemen met de implementatie van MSI-apps in Microsoft Intune oplossen](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-MSI-App-deployments-in-Microsoft/ba-p/359125)
- [Aanbevolen procedures voor softwaredistributie naar de klassieke Intune-agent voor Windows-pc’s](https://support.microsoft.com/en-us/help/2583929/best-practices-for-intune-software-distribution-to-windows-pc)

## <a name="next-steps"></a>Volgende stappen

- Raadpleeg [De portal voor probleemoplossing gebruiken om gebruikers in uw bedrijf te helpen](../fundamentals/help-desk-operators.md) voor meer informatie over probleemoplossing met Intune. 
- Ontdek meer over bekende problemen in Microsoft Intune. Zie [Intune-klantsucces](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess) voor meer informatie.
- Extra hulp nodig? Zie [Ondersteuning voor Microsoft Intune krijgen](../fundamentals/get-support.md).
