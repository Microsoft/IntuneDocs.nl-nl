---
title: Problemen met app-implementatie oplossen
description: Dit onderwerp helpt u bij het oplossen van problemen met app-implementaties in Microsoft Intune.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ebfc1249ab1138643220e9c4e5548a4d0b007b61
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2017
---
# <a name="troubleshoot-app-deployment-problems-in-microsoft-intune"></a>Problemen met app-implementaties oplossen in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Als u problemen hebt met het implementeren en beheren van apps met Intune, begint u hier. Dit onderwerp bevat oplossingen voor een aantal veelvoorkomende problemen.

## <a name="common-app-deployment-error-codes"></a>Veelvoorkomende foutcodes bij app-implementatie

|Foutcode|Mogelijk probleem|Voorgestelde oplossing|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (clientfout)|Als u deze app wilt installeren, moet u beschikken over een systeem waarop sideloading is ingeschakeld.|Controleer of het app-pakket is ondertekend met een vertrouwde handtekening en is geïnstalleerd op een apparaat dat lid is van een domein en waarop het AllowAllTrustedApps-beleid is ingeschakeld of op een apparaat dat een Windows Sideloading-licentie bevat en waarop het AllowAllTrustedApps-beleid is ingeschakeld.|
|0x80073CF0|Het pakket kan niet worden geopend.|Mogelijke oorzaken:<br /><br />-   Het pakket is niet ondertekend.<br />-   De naam van de uitgever komt niet overeen met de ondertekenende certificaathouder.<br /><br />Controleer het gebeurtenislogboek AppxPackagingOM op meer informatie.|
|0x80073CF3|Validatie van updates, afhankelijkheid of conflict voor het pakket is mislukt|Mogelijke oorzaken:<br /><br />-   Het binnenkomende pakket conflicteert met een geïnstalleerd pakket.<br />-   Kan een opgegeven pakketafhankelijkheid niet vinden.<br />-   Het pakket biedt geen ondersteuning voor de juiste processorarchitectuur.<br /><br />Controleer het gebeurtenislogboek AppXDeployment-Server voor meer informatie.|
|0x80073CFB|Het opgegeven pakket is al geïnstalleerd en opnieuw installeren van het pakket is geblokkeerd|Dit foutbericht kan worden weergegeven als u een pakket installeert dat niet gelijk is aan het pakket dat al is geïnstalleerd. Controleer of de digitale handtekening ook onderdeel is van het pakket. Wanneer een pakket opnieuw is samengesteld of opnieuw is ondertekend, is dat pakket niet meer bitsgewijs identiek aan het eerder geïnstalleerde pakket. Er zijn twee mogelijke opties om deze fout te herstellen:<br /><br />-   Verhoog het versienummer van de app, stel het pakket opnieuw samen en onderteken het opnieuw.<br />-   Verwijder het oude pakket voor elke gebruiker op het systeem voordat u het nieuwe pakket installeert.|
|0x87D1041C|De toepassing is geïnstalleerd, maar de toepassing wordt niet gedetecteerd.|-De app is geïmplementeerd met Intune en daarna verwijderd (mogelijk door de eindgebruiker). Geef de gebruiker de opdracht de app opnieuw te installeren via de bedrijfsportal. Vereiste apps worden automatisch opnieuw geïnstalleerd wanneer het apparaat vervolgens incheckt.|

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>Het oplossen van problemen met apps van Microsoft Store

De informatie in het Engelstalige onderwerp [Troubleshooting packaging, deployment, and query of Windows Store apps](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) (Het oplossen van problemen bij het verpakken, implementeren en zoeken van Microsoft Store-apps) helpt u om algemene problemen op te lossen die optreden tijdens het installeren van apps in Microsoft Store, hetzij met behulp van Intune of op een andere manier.

## <a name="troubleshooting-app-deployment-to-pcs-managed-by-the-intune-software-client"></a>Het oplossen van problemen bij het implementeren van apps naar pc's die worden beheerd door de Intune-softwareclient
Voor hulp bij het oplossen van problemen met het implementeren van apps naar de pc's die worden beheerd door de Intune-softwareclient, kunt u de volgende twee logboekbestanden raadplegen:
- %ProgramFiles%\Microsoft\OnlineManagement\Logs folder
- %ProgramFiles%\Microsoft\OnlineManagement\Updates\ReportingEvents.log

Daarnaast is het ook handig als u deze logboeken naar Microsoft verzendt in het geval u een ondersteuningsaanvraag voor Intune opent.


### <a name="next-steps"></a>Volgende stappen
Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning, zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).
