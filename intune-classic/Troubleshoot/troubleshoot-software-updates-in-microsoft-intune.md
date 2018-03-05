---
title: Problemen met software-updates oplossen
description: Problemen met software-updates in Microsoft Intune oplossen.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d17b70f4-17b4-4d89-88fd-70fa4f34fbea
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 66cca236d2779fb9a7a01ad6aa10a57edf8ab657
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/30/2018
---
# <a name="troubleshoot-software-updates-in-microsoft-intune"></a>Problemen met software-updates oplossen in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Met de informatie in deze sectie kunt u problemen met software-updates in Microsoft Intune oplossen.

Zie [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md) voor meer manieren om hulp te krijgen als u het probleem niet kunt oplossen met deze informatie.

## <a name="update-agent-error-codes"></a>Foutcodes voor update-agent

De volgende tabel bevat de foutcodes voor de Intune **Update-agent**. Als u een specifieke foutcode niet in deze tabel kunt vinden, raadpleegt u [Resultaatcodes voor Windows Update Agent](http://go.microsoft.com/fwlink/?LinkID=221542).

|Foutcode|Symbolische naam|Meer informatie|
|--------------|-----------------|--------------------|
|**0x00cf0001**|OM_S_SERVICE_STOP|De agent is gestopt.|
|**0x00cf0003**|OM_S_UPDATE_ERROR|De bewerking is voltooid, maar er zijn fouten opgetreden tijdens de toepassing van updates.|
|**0x00cf0004**|OM_S_MARKED_FOR_DISCONNECT|Een retouraanroep is gemarkeerd om later te worden losgekoppeld omdat de aanvraag om de bewerking los te koppelen zich voordeed terwijl er een retouraanroep werd uitgevoerd.|
|**0x00cf0005**|OM_S_REBOOT_REQUIRED|Het systeem moet opnieuw worden opgestart om de installatie van de update te voltooien.|
|**0x00cf0006**|OM_S_ALREADY_INSTALLED|De te installeren update is al geïnstalleerd op het systeem.|
|**0x00cf0007**|OM_S_ALREADY_UNINSTALLED|De te verwijderen update is niet geïnstalleerd op het systeem.|
|**0x00cf2015**|OM_S_UH_INSTALLSTILLPENDING|De installatie van de update wordt uitgevoerd.|
|**0x80cf0001**|OM_E_NO_SERVICE|De agent kan de service niet leveren.|
|**0x80cf0002**|OM_E_MAX_CAPACITY_REACHED|De maximale capaciteit van de service is overschreden.|
|**0x80cf0003**|OM_E_UNKNOWN_ID|Een id kan niet worden gevonden.|
|**0x80cf0004**|OM_E_NOT_INITIALIZED|Het object kan niet worden geïnitialiseerd.|
|**0x80cf0007**|OM_E_INVALIDINDEX|De index van een verzameling is ongeldig.|
|**0x80cf0008**|OM_E_ITEMNOTFOUND|De sleutel voor het opgevraagde item kan niet worden gevonden.|
|**0x80cf0009**|OM_E_OPERATIONINPROGRESS|Er wordt een conflicterende bewerking uitgevoerd. Bepaalde bewerkingen, zoals meervoudige installaties, kunnen niet tegelijkertijd worden uitgevoerd.|
|**0x80cf000B**|OM_E_CALL_CANCELLED|De bewerking is geannuleerd.|
|**0x80cf000C**|OM_E_NOOP|Er is geen bewerking vereist.|
|**0x80cf000D**|OM_E_XML_MISSINGDATA|De agent kan de vereiste gegevens niet vinden in de XML-gegevens van de update.|
|**0x80cf000E**|OM_E_XML_INVALID|De agent heeft in de XML-gegevens van de update informatie gevonden die ongeldig is.|
|**0x80cf000F**|OM_E_CYCLE_DETECTED|Er zijn circulaire updaterelaties gedetecteerd in de metagegevens.|
|**0x80cf0010**|OM_E_TOO_DEEP_RELATION|De updaterelaties zijn te diep genest om te kunnen evalueren.|
|**0x80cf0011**|OM_E_INVALID_RELATIONSHIP|Er is een updaterelatie gevonden die ongeldig is.|
|**0x80cf0012**|OM_E_REG_VALUE_INVALID|Er is een registerwaarde gelezen die ongeldig is.|
|**0x80cf0013**|OM_E_DUPLICATE_ITEM|De bewerking heeft geprobeerd een dubbel item toe te voegen aan een lijst.|
|**0x80cf0014**|OM_E_INVALID_INSTALL_REQUESTED|De aanroeper kan geen updates installeren die zijn aangevraagd voor installatie.|
|**0x80cf0016**|OM_E_INSTALL_NOT_ALLOWED|Er is een installatiebewerking geprobeerd terwijl een andere installatie werd uitgevoerd of terwijl verplicht opnieuw opstarten van het systeem in behandeling was.|
|**0x80cf0017**|OM_E_NOT_APPLICABLE|De bewerking is mislukt, omdat er geen beschikbare updates zijn.|
|**0x80cf0018**|OM_E_NO_USERTOKEN|De bewerking is mislukt, omdat een vereiste token ontbreekt.|
|**0x80cf0019**|OM_E_EXCLUSIVE_INSTALL_CONFLICT|Een exclusieve update kan niet tegelijkertijd met andere updates worden geïnstalleerd.|
|**0x80cf001A**|OM_E_POLICY_NOT_SET|Er is geen beleidswaarde ingesteld.|
|**0x80cf001D**|OM_E_INVALID_UPDATE|Een update bevat metagegevens die ongeldig zijn.|
|**0x80cf001E**|OM_E_SERVICE_STOP|De bewerking kan niet worden voltooid omdat de service of het systeem werd afgesloten.|
|**0x80cf001F**|OM_E_NO_CONNECTION|De bewerking kan niet worden voltooid omdat de netwerkverbinding niet beschikbaar is.|
|**0x80cf0020**|OM_E_NO_INTERACTIVE_USER|De bewerking kan niet worden voltooid omdat er geen interactieve gebruiker is aangemeld.|
|**0x80cf0021**|OM_E_TIME_OUT|De bewerking kan niet worden voltooid omdat er een time-out is opgetreden.|
|**0x80cf0022**|OM_E_ALL_UPDATES_FAILED|De bewerking is voor alle updates mislukt.|
|**0x80cf0024**|OM_E_NO_UPDATE|Er zijn geen updates.|
|**0x80cf0025**|OM_E_USER_ACCESS_DISABLED|Toegang tot Windows Update wordt verhinderd door groepsbeleidinstellingen.|
|**0x80cf0026**|OM_E_INVALID_UPDATE_TYPE|Het type update is ongeldig.|
|**0x80cf0028**|OM_E_UNINSTALL_NOT_ALLOWED|De update kan niet worden verwijderd omdat het verzoek niet van een WSUS-server komt.|
|**0x80cf0029**|OM_E_INVALID_PRODUCT_LICENSE|Zoeken kan een aantal updates hebben gemist omdat er een niet-gelicentieerde toepassing in het systeem bestaat.|
|**0x80cf002C**|OM_E_BIN_SOURCE_ABSENT|Een delta-gecomprimeerde update kan niet worden geïnstalleerd omdat daarvoor de bron nodig is.|
|**0x80cf002D**|OM_E_SOURCE_ABSENT|Een volledig-bestandupdate kan niet worden geïnstalleerd omdat daarvoor de bron nodig is.|
|**0x80cf002E**|OM_E_WU_DISABLED|Toegang tot een onbeheerde server is niet toegestaan.|
|**0x80cf002F**|OM_E_CALL_CANCELLED_BY_POLICY|De bewerking kan niet worden voltooid omdat het beleid **DisableWindowsUpdateAccess** is ingesteld.|
|**0x80cf0030**|OM_E_INVALID_PROXY_SERVER|De indeling van de proxylijst is ongeldig.|
|**0x80cf0031**|OM_E_INVALID_FILE|Het bestand heeft de verkeerde indeling.|
|**0x80cf0032**|OM_E_INVALID_CRITERIA|De zoekcriteriatekenreeks is ongeldig.|
|**0x80cf0034**|OM_E_DOWNLOAD_FAILED|De update kan niet worden gedownload.|
|**0x80cf0035**|OM_E_UPDATE_NOT_PROCESSED|De update is niet verwerkt.|
|**0x80cf0036**|OM_E_INVALID_OPERATION|De huidige status van het object staat de bewerking niet toe.|
|**0x80cf0037**|OM_E_NOT_SUPPORTED|De bewerking wordt niet ondersteund.|
|**0x80cf0038**|OM_E_WINHTTP_INVALID_FILE|Het gedownloade bestand heeft een onverwacht inhoudstype.|
|**0x80cf0039**|OM_E_TOO_MANY_RESYNC|De server heeft de agent te vaak gevraagd om te synchroniseren.|
|**0x80cf0043**|OM_E_NO_UI_SUPPORT|Windows Automatische updates-UI wordt niet ondersteund.|
|**0x80cf0044**|OM_E_PER_MACHINE_UPDATE_ACCESS_DENIED|Alleen beheerders kunnen deze bewerking uitvoeren op updates per computer.|
|**0x80cf0045**|OM_E_UNSUPPORTED_SEARCHSCOPE|Er is een zoekopdracht geprobeerd met een niet-ondersteund bereik.|
|**0x80cf0046**|OM_E_BAD_FILE_URL|De URL wijst niet naar een bestand.|
|**0x80cf0047**|OM_E_NOTSUPPORTED|De gevraagde bewerking wordt niet ondersteund.|
|**0x80cf0049**|OM_E_OUTOFRANGE|De gegevens vallen buiten het bereik.|
|**0x80cf004A**|OM_E_INVALIDWUAVERSION|De gegevens bevatten een versie die ongeldig is.|
|**0x80cf004B**|OM_E_SEARCH_COMPLETED_WITH_SOME_FAILURES|De aanroep van de zoekopdracht is voltooid, maar sommige updates zijn niet gedetecteerd.|
|**0x80cf004C**|OM_E_DOWNLOAD_COMPLETED_WITH_SOME_FAILURES|De aanroep van de downloadopdracht is voltooid, maar sommige updates zijn niet gedownload.|
|**0x80cf004D**|OM_E_INSTALL_COMPLETED_WITH_SOME_FAILURES|De aanroep van de installatieopdracht is voltooid, maar sommige updates zijn niet geïnstalleerd.|
|**0x80cf004E**|OM_E_WINUPDATE_CACHE_UNINITIALIZED|De Windows Update-cache is leeg omdat deze niet is geïnitialiseerd.|
|**0x80cf0436**|OM_E_PT_CATALOG_SYNC_REQUIRED|De server ondersteunt geen categoriespecifieke zoekopdrachten; in plaats daarvan moet een volledige cataloguszoekopdracht worden uitgevoerd.|
|**0x80cf0437**|OM_E_PT_SECURITY_VERIFICATION_FAILURE|Er is een probleem opgetreden bij het verifiëren van de service.|
|**0x80cf0438**|OM_E_PT_ENDPOINT_UNREACHABLE|Er is geen route naar of netwerkverbinding met het eindpunt.|
|**0x80cf0439**|OM_E_PT_INVALID_FORMAT|De ontvangen gegevens voldoen niet aan de verwachtingen van het gegevenscontract.|
|**0x80cf043A**|OM_E_PT_INVALID_URL|De URL is ongeldig.|
|**0x80cf043B**|OM_E_PT_NWS_NOT_LOADED|Kan NWS-runtime niet laden.|
|**0x80cf043C**|OM_E_PT_PROXY_AUTH_SCHEME_NOT_SUPPORTED|Het verificatieschema voor de proxy wordt niet ondersteund.|
|**0x80cf043D**|OM_E_SERVICEPROP_NOTAVAIL|De aangevraagde service-eigenschap is niet beschikbaar.|
|**0x80cf043E**|OM_E_PT_ENDPOINT_REFRESH_REQUIRED|De invoegtoepassing van de eindpuntprovider vereist dat online wordt vernieuwd.|
|**0x80cf043F**|OM_E_PT_ENDPOINTURL_NOTAVAIL|Er is geen URL beschikbaar voor het aangevraagde service-eindpunt.|
|**0x80cf0440**|OM_E_PT_ENDPOINT_DISCONNECTED|De verbinding met het service-eindpunt is beëindigd.|
|**0x80cf0441**|OM_E_PT_INVALID_OPERATION|De bewerking is ongeldig omdat de protocoltalker niet de juiste status heeft.|
|**0x80cf0FFF**|OM_E_UNEXPECTED|Een bewerking is mislukt om redenen die niet worden gedekt door een andere foutcode.|
|**0x80cf1001**|OM_E_MSI_WRONG_VERSION|Zoeken kan een aantal updates hebben gemist omdat de Windows Installer-versie lager is dan 3.1.|
|**0x80cf1002**|OM_E_MSI_NOT_CONFIGURED|Zoeken kan een aantal updates hebben gemist omdat Windows Installer niet is geconfigureerd.|
|**0x80cf1003**|OM_E_MSP_DISABLED|Zoeken kan een aantal updates hebben gemist omdat Windows Installer-patching is uitgeschakeld door beleid.|
|**0x80cf1004**|OM_E_MSI_WRONG_APP_CONTEXT|Een update kan niet worden toegepast omdat de toepassing per gebruiker wordt geïnstalleerd.|
|**0x80cf2000**|OM_E_UH_REMOTEUNAVAILABLE|Een verzoek voor een externe updatehandler kan niet worden voltooid omdat er geen extern proces beschikbaar is.|
|**0x80cf2001**|OM_E_UH_LOCALONLY|Een verzoek voor een externe updatehandler kan niet worden voltooid omdat de handler uitsluitend lokaal is.|
|**0x80cf2003**|OM_E_UH_REMOTEALREADYACTIVE|Een externe updatehandler kan niet worden gemaakt omdat er al een bestaat.|
|**0x80cf2004**|OM_E_UH_DOESNOTSUPPORTACTION|Een verzoek aan de handler voor het installeren (verwijderen) van een update kan niet worden voltooid omdat de update installeren (verwijderen) niet ondersteunt.|
|**0x80cf2005**|OM_E_UH_WRONGHANDLER|Een bewerking kan niet worden voltooid omdat de verkeerde handler is opgegeven.|
|**0x80cf2006**|OM_E_UH_INVALIDMETADATA|Een handlerbewerking kan niet worden voltooid omdat de update metagegevens bevat die ongeldig zijn.|
|**0x80cf2007**|OM_E_UH_INSTALLERHUNG|Een bewerking kan niet worden voltooid omdat het installatieprogramma de tijdslimiet heeft overschreden. Controleer of een update die gebruikersinteractie vereist, is goedgekeurd voor implementatie. In dit geval moet u de installatieparameters van de update wijzigen zodat deze op de achtergrond wordt geïnstalleerd.|
|**0x80cf2008**|OM_E_UH_OPERATIONCANCELLED|Een bewerking die werd uitgevoerd door de updatehandler, is geannuleerd.|
|**0x80cf2009**|OM_E_UH_BADHANDLERXML|Een bewerking kan niet worden voltooid omdat de handlerspecifieke metagegevens ongeldig zijn.|
|**0x80cf200B**|OM_E_UH_INSTALLERFAILURE|Het installatieprogramma kan een of meer updates niet installeren (verwijderen).|
|**0x80cf200D**|OM_E_UH_NEEDANOTHERDOWNLOAD|De updatehandler heeft de update niet geïnstalleerd omdat deze opnieuw moet worden gedownload.|
|**0x80cf200E**|OM_E_UH_NOTIFYFAILURE|De updatehandler kan geen kennisgeving verzenden van de status van de installatiebewerking (verwijderen).|
|**0x80cf2014**|OM_E_UH_POSTREBOOTSTILLPENDING|De bewerking na opnieuw opstarten wordt nog uitgevoerd voor de update.|
|**0x80cf2015**|OM_E_UH_POSTREBOOTRESULTUNKNOWN|Het resultaat van de bewerking na opnieuw opstarten voor de update kan niet worden bepaald.|
|**0x80cf2016**|OM_E_UH_POSTREBOOTUNEXPECTEDSTATE|De status van de update na het voltooien van de bewerking na opnieuw opstarten is onverwacht.|
|**0x80cf2017**|OM_E_UH_NEW_SERVICING_STACK_REQUIRED|De OS-servicestack moet worden bijgewerkt voordat deze update wordt gedownload of geïnstalleerd.|
|**0x80cf2018**|OM_E_UH_CALLED_BACK_FAILURE|Een retouraanroepinstallatieprogramma heeft een retouraanroep uitgevoerd met een fout.|
|**0x80cf2019**|OM_E_UH_CUSTOMINSTALLER_INVALID_SIGNATURE|De aangepaste handtekening van het installatieprogramma stemt niet overeen met de handtekening die vereist is voor de update.|
|**0x80cf201A**|OM_E_UH_UNSUPPORTED_INSTALLCONTEXT|Het installatieprogramma ondersteunt de installatieconfiguratie niet.|
|**0x80cf201B**|OM_E_UH_INVALID_TARGETSESSION|De doelsessie voor installatie is ongeldig.|
|**0x80cf2FFF**|OM_E_UH_UNEXPECTED|Een updatehandlerfout wordt niet gedekt door een andere OM_E_UH_&#42;-code.|
|**0x80cf3FFD**|OM_E_NON_UI_MODE|Kan UI niet weergeven in niet-UI-modus. UI-modules WU-client zijn mogelijk niet geïnstalleerd.|
|**0x80cf3FFE**|OM_E_WUCLTUI_UNSUPPORTED_VERSION|Niet-ondersteunde versie van geëxporteerde functies van WU-client-UI.|
|**0x80cf3FFF**|OM_E_AUCLIENT_UNEXPECTED|Er is een gebruikersinterfacefout opgetreden die niet wordt gedekt door een andere OM_E_AUCLIENT_&#42;-foutcode.|
|**0x80cf4007**|OM_E_PT_SOAPCLIENT_SOAPFAULT|Hetzelfde als **SOAPCLIENT_SOAPFAULT**. De SOAP-client is mislukt omdat er een SOAP-fout van het foutcodetype **OM_E_PT_SOAP_&#42;** is opgetreden.|
|**0x80cf4008**|OM_E_PT_SOAPCLIENT_PARSEFAULT|Hetzelfde als **SOAPCLIENT_PARSEFAULT_ERROR**.  SOAP-client kan een SOAP-fout niet parseren.|
|**0x80cf400A**|OM_E_PT_SOAPCLIENT_PARSE|Hetzelfde als **SOAPCLIENT_PARSE_ERROR**.  SOAP-client kan de reactie van de server niet parseren.|
|**0x80cf400B**|OM_E_PT_SOAP_VERSION|Hetzelfde als **SOAP_E_VERSION_MISMATCH**. SOAP-client heeft een onherkenbare naamruimte voor de SOAP-envelop gevonden.|
|**0x80cf400C**|OM_E_PT_SOAP_MUST_UNDERSTAND|Hetzelfde als **SOAP_E_MUST_UNDERSTAND**. SOAP-client kan een koptekst niet interpreteren.|
|**0x80cf400D**|OM_E_PT_SOAP_CLIENT|Hetzelfde als **SOAP_E_CLIENT**. SOAP-client beschouwt het bericht als onjuist gevormd. Herstel dit alvorens opnieuw te verzenden.|
|**0x80cf400E**|OM_E_PT_SOAP_SERVER|Hetzelfde als **SOAP_E_SERVER**. Het SOAP-bericht kan niet worden verwerkt vanwege een serverfout. Verzend later opnieuw.|
|**0x80cf4010**|OM_E_PT_EXCEEDED_MAX_SERVER_TRIPS|Het aantal retouren naar de server heeft de limiet overschreden.|
|**0x80cf4012**|OM_E_PT_DOUBLE_INITIALIZATION|Initialisatie mislukt omdat het object al is geïnitialiseerd.|
|**0x80cf4013**|OM_E_PT_INVALID_COMPUTER_NAME|De computernaam kan niet worden bepaald.|
|**0x80cf4015**|OM_E_PT_REFRESH_CACHE_REQUIRED|Het antwoord van de server geeft aan dat de server is gewijzigd of dat de cookie ongeldig is. Vernieuw de status van de interne cache en probeer opnieuw.|
|**0x80cf4016**|OM_E_PT_HTTP_STATUS_BAD_REQUEST|Hetzelfde als **HTTP-status 400**. De server kan het verzoek niet verwerken vanwege ongeldige syntaxis.|
|**0x80cf4017**|OM_E_PT_HTTP_STATUS_DENIED|Hetzelfde als **HTTP-status 401**. De gevraagde resource vereist verificatie van gebruiker.|
|**0x80cf4018**|OM_E_PT_HTTP_STATUS_FORBIDDEN|Hetzelfde als **HTTP-status 403**. Server heeft het verzoek begrepen, maar geweigerd.|
|**0x80cf4019**|OM_E_PT_HTTP_STATUS_NOT_FOUND|Hetzelfde als **HTTP-status 404**. Server kan gevraagde URI (Uniform Resource Identifier) niet vinden.|
|**0x80cf401A**|OM_E_PT_HTTP_STATUS_BAD_METHOD|Hetzelfde als **HTTP-status 405**. HTTP-methode is niet toegestaan.|
|**0x80cf401B**|OM_E_PT_HTTP_STATUS_PROXY_AUTH_REQ|Hetzelfde als **HTTP-status 407**. Proxyverificatie is vereist.|
|**0x80cf401C**|OM_E_PT_HTTP_STATUS_REQUEST_TIMEOUT|Hetzelfde als **HTTP-status 408**. Er is een time-out opgetreden bij de server bij het wachten op het verzoek.|
|**0x80cf401D**|OM_E_PT_HTTP_STATUS_CONFLICT|Hetzelfde als **HTTP-status 409**. Het verzoek is niet voltooid vanwege een conflict met de huidige status van de resource.|
|**0x80cf401E**|OM_E_PT_HTTP_STATUS_GONE|Hetzelfde als **HTTP-status 410**. Gevraagde resource is niet meer beschikbaar op de server.|
|**0x80cf401F**|OM_E_PT_HTTP_STATUS_SERVER_ERROR|Hetzelfde als **HTTP-status 500**. Een interne fout bij de server heeft ervoor gezorgd dan niet kan worden voldaan aan het verzoek.|
|**0x80cf4020**|OM_E_PT_HTTP_STATUS_NOT_SUPPORTED|Hetzelfde als **HTTP-status 500**. De server ondersteunt de functionaliteit niet die nodig is om te voldoen aan het verzoek.|
|**0x80cf4021**|OM_E_PT_HTTP_STATUS_BAD_GATEWAY|Hetzelfde als **HTTP-status 502**. De server heeft bij het fungeren als gateway of proxy een ongeldige reactie ontvangen van de upstreamserver die is aangesproken bij een poging te voldoen aan het verzoek.|
|**0x80cf4022**|OM_E_PT_HTTP_STATUS_SERVICE_UNAVAIL|Hetzelfde als **HTTP-status 503**. De service is tijdelijk overbelast.|
|**0x80cf4023**|OM_E_PT_HTTP_STATUS_GATEWAY_TIMEOUT|Hetzelfde als **HTTP-status 503**. Er is een time-out voor het verzoek opgetreden bij het wachten op een gateway.|
|**0x80cf4024**|OM_E_PT_HTTP_STATUS_VERSION_NOT_SUP|Hetzelfde als **HTTP-status 505**. De server ondersteunt het HTTP-protocol niet dat in de aanvraag is gebruikt.|
|**0x80cf4025**|OM_E_PT_FILE_LOCATIONS_CHANGED|Bewerking mislukt vanwege een gewijzigde bestandslocatie. Vernieuw de interne status en verzend opnieuw.|
|**0x80cf4027**|OM_E_PT_NO_AUTH_PLUGINS_REQUESTED|De server heeft een lege verificatiegegevenslijst geretourneerd.|
|**0x80cf4028**|OM_E_PT_NO_AUTH_COOKIES_CREATED|De agent kan geen geldige verificatiecookies maken.|
|**0x80cf4029**|OM_E_PT_INVALID_CONFIG_PROP|Een configuratie-eigenschapwaarde is onjuist.|
|**0x80cf402A**|OM_E_PT_CONFIG_PROP_MISSING|Er ontbreekt een configuratie-eigenschapwaarde.|
|**0x80cf402B**|OM_E_PT_HTTP_STATUS_NOT_MAPPED|De HTTP-aanvraag kan niet worden voltooid en de reden komt niet overeen met een van de **OM_E_PT_HTTP_&#42;**-foutcodes.|
|**0x80cf402C**|OM_E_PT_WINHTTP_NAME_NOT_RESOLVED|Hetzelfde als **ERROR_WINHTTP_NAME_NOT_RESOLVED**. De naam van de proxyserver of doelserver kan niet worden omgezet.|
|**0x80cf402F**|OM_E_PT_ECP_SUCCEEDED_WITH_ERRORS|De verwerking van het externe CAB-bestand is voltooid met fouten.|
|**0x80cf4030**|OM_E_PT_ECP_INIT_FAILED|De initialisatie van de externe CAB-processor is niet voltooid.|
|**0x80cf4031**|OM_E_PT_ECP_INVALID_FILE_FORMAT|De indeling van een bestand met metagegevens is ongeldig.|
|**0x80cf4032**|OM_E_PT_ECP_INVALID_METADATA|Externe cabinetprocessor heeft ongeldige metagegevens gevonden.|
|**0x80cf4033**|OM_E_PT_ECP_FAILURE_TO_EXTRACT_DIGEST|De controlesom kan niet uit een extern cabinetbestand worden gehaald.|
|**0x80cf4034**|OM_E_PT_ECP_FAILURE_TO_DECOMPRESS_CAB_FILE|Een extern cabinetbestand kan niet worden gedecomprimeerd.|
|**0x80cf4035**|OM_E_PT_ECP_FILE_LOCATION_ERROR|Externe cabinetprocessor kan bestandslocaties niet ophalen.|
|**0x80cf4FFF**|OM_E_PT_UNEXPECTED|Er is een communicatiefout opgetreden die niet wordt gedekt door een andere **OM_E_PT_&#42;**-foutcode.|
|**0x80cf6001**|OM_E_DM_URLNOTAVAILABLE|Een downloadbeheerbewerking kan niet worden voltooid omdat het gevraagde bestand geen URL heeft.|
|**0x80cf6002**|OM_E_DM_INCORRECTFILEHASH|Een downloadbeheerbewerking kan niet worden voltooid omdat de controlesom niet is herkend.|
|**0x80cf6003**|OM_E_DM_UNKNOWNALGORITHM|Een downloadbeheerbewerking kan niet worden voltooid omdat de bestandsmetagegevens een niet-herkend hash-algoritme heeft gevraagd.|
|**0x80cf6005**|OM_E_DM_NONETWORK|Een downloadbeheerbewerking kan niet worden voltooid, omdat de netwerkverbinding niet beschikbaar is.|
|**0x80cf6007**|OM_E_DM_NOTDOWNLOADED|De update is niet gedownload.|
|**0x80cf6008**|OM_E_DM_FAILTOCONNECTTOBITS|Er is een downloadbeheerbewerking mislukt omdat het downloadbeheer geen verbinding kan maken met de BITS (Background Intelligent Transfer Service).|
|**0x80cf6009**|OM_E_DM_BITSTRANSFERERROR|Er is een downloadbeheerbewerking mislukt omdat er een niet-opgegeven BITS-overdrachtsfout (Background Intelligent Transfer Service) is opgetreden.|
|**0x80cf600a**|OM_E_DM_DOWNLOADLOCATIONCHANGED|Een download moet opnieuw worden gestart omdat de locatie van de bron van de download is gewijzigd.|
|**0x80cf600B**|OM_E_DM_CONTENTCHANGED|Een download moet opnieuw worden gestart omdat de update-inhoud is gewijzigd in een nieuwe revisie.|
|**0x80cf6FFF**|OM_E_DM_UNEXPECTED|Er is een downloadbeheerfout opgetreden die niet wordt gedekt door een andere **OM_E_DM_&#42;**-foutcode.|
|**0x80cf7003**|OM_E_INVALID_EVENT_PAYLOAD|Er is een ongeldige nettolading opgegeven.|
|**0x80cf7004**|OM_E_INVALID_EVENT_PAYLOADSIZE|De grootte van de verzonden nettolading is ongeldig.|
|**0x80cf7005**|OM_E_SERVICE_NOT_REGISTERED|De service is niet geregistreerd.|
|**0x80cf8000**|OM_E_DS_SHUTDOWN|Een bewerking is mislukt omdat de agent wordt afgesloten.|
|**0x80cf8001**|OM_E_DS_INUSE|Een bewerking is mislukt omdat het gegevensarchief in gebruik was.|
|**0x80cf8002**|OM_E_DS_INVALID|De huidige en de verwachte status van het gegevensarchief komen niet overeen.|
|**0x80cf8003**|OM_E_DS_TABLEMISSING|Er ontbreekt een tabel in het gegevensarchief.|
|**0x80cf8004**|OM_E_DS_TABLEINCORRECT|Het gegevensarchief bevat een tabel met onverwachte kolommen.|
|**0x80cf8005**|OM_E_DS_INVALIDTABLENAME|Een tabel kan niet worden geopend omdat de tabel zich niet in het gegevensarchief bevindt.|
|**0x80cf8006**|OM_E_DS_BADVERSION|De huidige en de verwachte versie van het gegevensarchief komen niet overeen.|
|**0x80cf8007**|OM_E_DS_NODATA|De vereiste gegevens ontbreken in het gegevensarchief.|
|**0x80cf8008**|OM_E_DS_MISSINGDATA|In het gegevensarchief ontbreekt informatie, of het gegevensarchief bevat een NULL-waarde in een tabel die een andere waarde dan null vereist.|
|**0x80cf8009**|OM_E_DS_MISSINGREF|Er ontbreekt vereiste informatie in het gegevensarchief of het gegevensarchief bevat een verwijzing naar ontbrekende licentievoorwaarden, een ontbrekend bestand, een ontbrekende vertaalde eigenschap of gekoppelde rij.|
|**0x80cf800A**|OM_E_DS_UNKNOWNHANDLER|De update is niet verwerkt omdat de updatehandler ervan niet is herkend.|
|**0x80cf800B**|OM_E_DS_CANTDELETE|De update is niet verwijderd omdat er nog steeds verwijzingen naar zijn opgenomen in een of meer services.|
|**0x80cf800C**|OM_E_DS_LOCKTIMEOUTEXPIRED|De gegevensarchiefsectie kan niet worden vergrendeld binnen de toegewezen tijd.|
|**0x80cf800E**|OM_E_DS_ROWEXISTS|De rij is niet toegevoegd omdat een bestaande rij dezelfde primaire sleutel heeft.|
|**0x80cf800F**|OM_E_DS_STOREFILELOCKED|Het gegevensarchief kan niet worden geïnitialiseerd omdat het is vergrendeld door een ander proces.|
|**0x80cf8010**|OM_E_DS_CANNOTREGISTER|Het gegevensarchief mag in het huidige proces niet worden geregistreerd met COM.|
|**0x80cf8011**|OM_E_DS_UNABLETOSTART|Een bewerking kan geen gegevensarchiefobject in een ander proces maken.|
|**0x80cf8013**|OM_E_DS_DUPLICATEUPDATEID|De server heeft dezelfde update naar de client verzonden met twee verschillende revisie-ID's.|
|**0x80cf8014**|OM_E_DS_UNKNOWNSERVICE|Een operatie is niet voltooid omdat de service zich niet in de gegevensarchiefopslag bevindt.|
|**0x80cf8015**|OM_E_DS_SERVICEEXPIRED|Een bewerking is niet voltooid omdat de registratie van de service is verlopen.|
|**0x80cf8016**|OM_E_DS_DECLINENOTALLOWED|Een verzoek om een update te verbergen is afgewezen omdat dit een verplichte update is of omdat de update is geïmplementeerd met een deadline.|
|**0x80cf8017**|OM_E_DS_TABLESESSIONMISMATCH|Een tabel is niet afgesloten omdat deze niet is gekoppeld aan de sessie.|
|**0x80cf8018**|OM_E_DS_SESSIONLOCKMISMATCH|Een tabel is niet afgesloten omdat deze niet is gekoppeld aan de sessie.|
|**0x80cf8019**|OM_E_DS_NEEDWINDOWSSERVICE|Een verzoek voor het verwijderen van de service of het verwijderen van de registratie ervan is afgewezen, omdat dit een ingebouwde service is of omdat Automatische updates niet kan terugvallen op een andere service.|
|**0x80cf801A**|OM_E_DS_INVALIDOPERATION|Een verzoek is afgewezen omdat de bewerking niet is toegestaan.|
|**0x80cf801B**|OM_E_DS_SCHEMAMISMATCH|De planning van de huidige gegevensarchiefopslag en de planning van een tabel in een XML-reservekopiedocument komen niet overeen.|
|**0x80cf801C**|OM_E_DS_RESETREQUIRED|Het gegevensarchief vereist dat de sessie opnieuw wordt gestart. Breek de sessie af en probeer opnieuw met een nieuwe sessie.|
|**0x80cf801D**|OM_E_DS_IMPERSONATED|Een gegevensarchiefbewerking is niet voltooid omdat deze is gevraagd met een geïmiteerde identiteit.|
|**0x80cf8FFF**|OM_E_DS_UNEXPECTED|Er is een gegevensarchieffout opgetreden die niet wordt gedekt door een andere **OM_E_DS_&#42;**-code.|
|**0x80cfA000**|OM_E_AU_NOSERVICE|Automatische updates kan binnenkomende verzoeken niet verwerken.|
|**0x80cfA004**|OM_E_AU_PAUSED|Windows Update Agent kan geen binnenkomende verzoeken verwerken omdat het programma is onderbroken.|
|**0x80cfA005**|OM_E_AU_NO_REGISTERED_SERVICE|Er is geen onbeheerde service geregistreerd bij AU.|
|**0x80cfA006**|OM_E_AU_DETECT_SVCID_MISMATCH|De standaardservice die is geregistreerd bij Automatische updates, is gewijzigd tijdens de zoekopdracht.|
|**0x80cfA007**|OM_E_AU_ALREADY_PROMPTING_FOR_REBOOT|Automatische updates vraagt de gebruiker al om opnieuw op te starten.|
|**0x80cfAFFF**|OM_E_AU_UNEXPECTED|Er is een Automatische updates-fout opgetreden die niet wordt gedekt door een andere **OM_E_AU &#42;**-code.|
|**0x80cfE001**|OM_E_EE_UNKNOWN_EXPRESSION|Een expressie-evaluatorbewerking kan niet worden voltooid omdat een expressie niet wordt herkend.|
|**0x80cfE002**|OM_E_EE_INVALID_EXPRESSION|Een expressie-evaluatorbewerking kan niet worden voltooid omdat een expressie ongeldig is.|
|**0x80cfE003**|OM_E_EE_MISSING_METADATA|Een expressie-evaluatorbewerking kan niet worden voltooid omdat een expressie een onjuist aantal metagegevensknooppunten bevat.|
|**0x80cfE004**|OM_E_EE_INVALID_VERSION|Een expressie-evaluatorbewerking kan niet worden voltooid omdat de versie van de expressiegegevens met serienummer ongeldig is.|
|**0x80cfE005**|OM_E_EE_NOT_INITIALIZED|De expressie-evaluator kan niet worden geïnitialiseerd.|
|**0x80cfE006**|OM_E_EE_INVALID_ATTRIBUTEDATA|Een expressie-evaluatorbewerking kan niet worden voltooid omdat er een ongeldig kenmerk is.|
|**0x80cfE007**|OM_E_EE_CLUSTER_ERROR|Een expressie-evaluatorbewerking kan niet worden voltooid omdat de clusterstatus van de computer niet kan worden bepaald.|
|**0x80cfEFFF**|OM_E_EE_UNEXPECTED|Er is een fout opgetreden in de expressie-evaluator die niet wordt gedekt door een andere **OM_E_EE_&#42;**-foutcode.|
|**0x80cfF001**|OM_E_REPORTER_EVENTCACHECORRUPT|Het gebeurteniscachebestand is defect.|
|**0x80cfF002**|OM_E_REPORTER_EVENTNAMESPACEPARSEFAILED|De XML in de naamruimtebeschrijving van de gebeurtenis kan niet worden geparseerd.|
|**0x80cfF003**|OM_E_INVALID_EVENT|De XML in de naamruimtebeschrijving van de gebeurtenis is ongeldig.|
|**0x80cfF004**|OM_E_SERVER_BUSY|De server heeft een gebeurtenis afgewezen omdat de server bezet was.|
|**0x80cfFFFF**|OM_E_REPORTER_UNEXPECTED|Er was een rapporteurfout die niet wordt gedekt door een andere foutcode.|
|**0x80af0005**|OMC_E_INSTALL_NOT_ALLOWED_REBOOT_REQUIRED|Installatie is mislukt omdat de computer nog opnieuw moet worden opgestart.|
|**0x80af0006**|OMC_E_DOWNLOAD_CANCELLED|Het downloaden is geannuleerd.|

## <a name="windows-7-based-computers-with-lots-of-superseded-updates-stop-reporting-to-the-microsoft-intune-console"></a>Windows 7-computers met veel vervangen updates stoppen met rapporteren aan de Microsoft Intune-beheerconsole
**Probleem**: het kan gebeuren dat Microsoft Intune-clients een of meer van de volgende symptomen ervaren:
- Er wordt opeens niet meer gerapporteerd aan de Microsoft-beheerconsole.  
- Er is sprake van hoog CPU-verbruik.
- De installatie van toepassingen verloopt traag wanneer ze worden geïnstalleerd via de Intune-portal.
- Microsoft Intune Center genereert de volgende fout: *Er is een fout opgetreden bij het bijwerken van uw computer. Er is een fout gevonden: code 0x800705b4*.
- In het statusveld onder Intune-beheerconsole > Groepen > Alle apparaten wordt het volgende weergegeven: *Er zijn fouten bij een of meer agents die op deze computer zijn geïnstalleerd. De gegevens voor deze computer zijn mogelijk niet juist of up-to-date*.

Dit probleem kan optreden als vervangen updates (updates die zijn vervangen door een andere update) gedurende een langere periode niet zijn afgewezen. Tijdens bepaalde processen, zoals het installeren van een toepassing, controleert Windows alle vervangen updates in de juiste volgorde, zodat de updates en de opvolgers hiervan correct kunnen worden toegewezen. Als de lijst met vervangen updates te groot is, kan deze controletaak leiden tot hoog CPU-verbruik door de verwerkingsbelasting en de daarvoor benodigde tijd. Dit probleem is hoofdzakelijk van invloed op clients waarop Windows 7 wordt uitgevoerd, door het grote aantal vervangen updates dat beschikbaar is voor Windows 7. Windows 8 en latere besturingssystemen hebben niet zo veel vervangen updates en zijn daarom niet zo vatbaar voor dit probleem.

**Oplossing**: voer de volgende stappen uit om dit probleem op te lossen:
1. Meld u aan bij de [Intune-beheerconsole](https://manage.microsoft.com).
2. Selecteer **Updates** > **Alle updates**.
3. Gebruik de filteroptie op de bovenste werkbalk om te filteren op vervangen updates.
4. Wijs alle vervangen updates af die van toepassing zijn op Windows 7 of op toepassingen (zoals Microsoft Office) die zijn geïnstalleerd op de betreffende clients.
5. Start de betreffende clients opnieuw op.

Als u met Windows 7 werkt, moet u ook controleren of de volgende update is geïnstalleerd:[3050265 Windows Update-client voor Windows 7: juni 2015](https://support.microsoft.com/kb/3050265).

### <a name="next-steps"></a>Volgende stappen
Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).
