---
title: Problemen bij toegang tot bedrijfsbronnen oplossen | Microsoft Intune
description: In dit onderwerp vindt u fout- en statuscodes die u kunt gebruiken bij het oplossen van problemen met de toegang tot bedrijfsresources.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 40622ced-6029-4abf-873e-b51d2b51934c
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6adfb7375f9747f64e7037164f48918789bd7ee0
ms.openlocfilehash: 76056f04440b53aa76f833b5fd4f5cf3cbeb88b5


---

# <a name="troubleshoot-company-resource-access-problems-with-microsoft-intune"></a>Problemen bij toegang tot bedrijfsbronnen oplossen met Microsoft Intune
Wanneer een Microsoft Intune-actie een foutcode retourneert, kunt u aan de hand van de fout- en statuscodes in dit onderwerp het probleem proberen op te lossen.

Zie [Ondersteuning voor Microsoft Intune krijgen](../troubleshoot/how-to-get-support-for-microsoft-intune.md) voor meer manieren om hulp te krijgen als u het probleem niet kunt oplossen met deze informatie.

## <a name="status-codes-for-mdm-managed-windows-devices"></a>Statuscodes voor met MDM beheerde Windows-apparaten

|Statuscode|Foutbericht|Wat u moet doen|
|---------------|-----------------|--------------|
|10 (APP_CI_ENFORCEMENT_IN_PROGRESS)|Installatie wordt uitgevoerd||
|20 (APP_CI_ENFORCEMENT_IN_PROGRESS_WAITING_CONTENT)|Wachten op inhoud||
|30 (APP_CI_ENFORCEMENT_ERROR_RETRIEVING_CONTENT)|Ophalen van inhoud|Waarschijnlijke oorzaak: de taakstatus 30 geeft aan dat het downloaden van een app door een gebruiker is mislukt.<br /><br />Mogelijke oorzaken hiervoor zijn:<br /><br />De internetverbinding van het apparaat is tijdens het downloaden verbroken.<br /><br />Het certificaat dat voor het apparaat is uitgegeven, is op het moment van de inschrijving mogelijk verlopen.<br /><br />Oplossing:<br /><br />Start op het apparaat in Configuratiescherm de app Bedrijfsapps om te controleren of het apparaatcertificaat niet is verlopen. Als dat wel het geval is, moet u het apparaat opnieuw inschrijven.<br /><br />Controleer of het apparaat verbinding heeft met internet en probeer de app opnieuw te starten.|
|40 (APP_CI_ENFORCEMENT_IN_PROGRESS_CONTENT_DOWNLOADED)|Downloaden van inhoud is voltooid||
|50 (APP_CI_ENFORCEMENT_IN_PROGRESS_INSTALLING)|Installatie wordt uitgevoerd||
|60 (APP_CI_ENFORCEMENT_ERROR_INSTALLING)|Er is een installatiefout opgetreden|De app kon na het downloaden niet worden geïnstalleerd.<br /><br />Het certificaat voor ondertekening van programmacode waarmee de app is ondertekend, bevindt zich niet op het apparaat.<br /><br />Een framework-afhankelijkheid waarvan de toepassing afhankelijk is, is niet op het apparaat geïnstalleerd.<br /><br /><br />Wanneer een ontbrekende structuurafhankelijkheid er de oorzaak van is dat de installatie is mislukt, moet de beheerder de toepassing opnieuw publiceren, waarbij de structuur in het toepassingspakket moet worden opgenomen.<br /><br />Het toepassingspakket dat is gedownload, is geen geldig pakket, is mogelijk beschadigd of misschien niet compatibel met de versie van het besturingssysteem op het apparaat.|
|70 (APP_CI_ENFORCEMENT_SUCCEEDED)|Installatie voltooid||
|80 (APP_CI_ENFORCEMENT_IN_PROGRESS)|Wordt verwijderd||
|90 (APP_CI_ENFORCEMENT_ERROR)|Er is een fout opgetreden bij het verwijderen||
|100 (APP_CI_ENFORCEMENT_SUCCEEDED)|Verwijderen voltooid||
|110 (APP_CI_ENFORCEMENT_ERROR)|Inhoudshash komt niet overeen||
|120 (APP_CI_ENFORCEMENT_ERROR)|SLK/sideloading is niet ingeschakeld||
|130 (APP_CI_ENFORCEMENT_ERROR)|Installatie van MSADP-licentie is mislukt||
|Geen status (APP_CI_ENFORCEMENT_UNKNOWN)|n.v.t.|De status is momenteel onbekend.|

## <a name="company-resource-access-common-errors"></a>Toegang tot bedrijfsbronnen (veelvoorkomende fouten)

|Statuscode|Hexadecimale foutcode|Foutbericht|
|---------------|--------------------------|-----------------|
|-2016281101|0x87D1FDF3|MDM CRP-aanvraag is niet gevonden|
|-2016281102|0x87D1FDF2|Kan de NDES-URL niet vinden|
|-2016281103|0x87D1FDF1|MDM CRP-certificaatinformatie is niet gevonden|
|-2016281104|0x87D1FDF0|MDM CI-certificaatinformatie is niet gevonden|
|-2016281105|0x87D1FDEF|Kan de regel niet evalueren|
|-2016281106|0x87D1FDEE|Niet van toepassing omdat conflictoplossing niet is gelukt|
|-2016281107|0x87D1FDED|Niet-ondersteunde bron van instellingendetectie|
|-2016281108|0x87D1FDEC|De instelling waarnaar wordt verwezen, is niet gevonden in CI|
|-2016281109|0x87D1FDEB|Conversie van gegevenstype is mislukt|
|-2016281110|0x87D1FDEA|Ongeldige parameter voor CIM-instelling|
|-2016281111|0x87D1FDE9|Niet van toepassing voor dit apparaat|
|-2016281112|0x87D1FDE8|Doorvoeren is mislukt|
|-2016330905|0x87D13B67|De status van de app is onbekend|
|-2016330906|0x87D13B66|De app is beheerd, maar werd verwijderd door de gebruiker|
|-2016330907|0x87D13B65|Het apparaat wisselt de inwisselcode in|
|-2016330908|0x87D13B64|De installatie van de app is mislukt|
|-2016330909|0x87D13B63|De gebruiker heeft de aanbieding voor een update van de app afgewezen|
|-2016330910|0x87D13B62|De gebruiker heeft de aanbieding voor het installeren van de app afgewezen|
|-2016330911|0x87D13B61|De gebruiker heeft de app geïnstalleerd voordat de beheerde installatie van de app kon worden uitgevoerd|
|-2016330912|0x87D13B60|Deze app staat ingepland om te worden geïnstalleerd, maar er is een inwisselcode vereist om de transactie te voltooien|
|-2016341109|0x87D1138B|iOS-apparaat heeft een fout geretourneerd|
|-2016341110|0x87D1138A|iOS-apparaat heeft de opdracht afgewezen vanwege een onjuiste indeling|
|-2016341111|0x87D11389|iOS-apparaat heeft een onverwachte status Niet-actief geretourneerd|
|-2016341112|0x87D11388|iOS-apparaat is momenteel bezig|

## <a name="errors-returned-by-ios-devices"></a>Fouten geretourneerd door iOS-apparaten

|Statuscode|Hexadecimale foutcode|Foutbericht|
|---------------|--------------------------|-----------------|
|-2016299111|0x87D1B799|Interne fout|
|-2016299112|0x87D1B798|Interne fout|
|-2016300111|0x87D1B3B1|36001:(interne fout)|
|-2016300112|0x87D1B3B0|36000:Mobiel reeds geconfigureerd|
|-2016301110|0x87D1AFCA|35002:Meerdere lettertypen in één nettolading|
|-2016301111|0x87D1AFC9|35001:Mislukte lettertype-installatie|
|-2016301112|0x87D1AFC8|35000:Ongeldige lettertypegegevens|
|-2016302109|0x87D1ABE3|34003:Kerberos principal-naam is ongeldig|
|-2016302110|0x87D1ABE2|34002:Kerberos-principal-naam ontbreekt|
|-2016302111|0x87D1ABE1|34001:Ongeldig URL-matchpatroon|
|-2016302112|0x87D1ABE0|34000:Ongeldig app-id-matchpatroon|
|-2016304112|0x87D1A410|32000:Te veel apps|
|-2016305111|0x87D1A029|31001:Kan instellingen niet toepassen|
|-2016305112|0x87D1A028|31000:Kan referenties niet toepassen|
|-2016306111|0x87D19C41|30001:Time-out opgetreden|
|-2016306112|0x87D19C40|30000:Verificatie is mislukt|
|-2016307109|0x87D1985B|29003:Ongeldige certificeringsgegevens|
|-2016307110|0x87D1985A|29002:|
|-2016307111|0x87D19859|29001:|
|-2016307112|0x87D19858|29000:Apparaat niet onder supervisie|
|-2016308110|0x87D19472|28002:Kan achtergrond niet instellen|
|-2016308111|0x87D19471|28001:Ongeldige achtergrondafbeelding|
|-2016308112|0x87D19470|28000:Onbekend item|
|-2016310111|0x87D18CA1|26001:Versleuteling op bestandsniveau niet ondersteund|
|-2016310112|0x87D18CA0|26001:Versleuteling op blokniveau niet ondersteund|
|-2016311110|0x87D188BA|25002:Kan niet verwijderen|
|-2016311111|0x87D188B9|25001:Kan niet installeren|
|-2016311112|0x87D188B8|25000:Ongeldig profiel|
|-2016312109|0x87D184D3|24003:Ongeldig eindprofiel|
|-2016312110|0x87D184D2|24002:Ongeldige identiteit nettolading|
|-2016312111|0x87D184D1|24001:Kan kenmerkbibliotheek niet ondertekenen|
|-2016312112|0x87D184D0|24001:Kan kenmerkbibliotheek niet maken|
|-2016313110|0x87D180EA|23002:Ongeldig servercertificaat|
|-2016313111|0x87D180E9|23001:Ongeldige reactie van server|
|-2016313112|0x87D180E8|23000:Ongeldige identiteit|
|-2016314099|0x87D17D0D|22013:Ongeldige reactie van PKIOperation|
|-2016314100|0x87D17D0C|22012:Kan CACertificate niet opslaan|
|-2016314101|0x87D17D0B|22011:Kan CSR niet genereren|
|-2016314102|0x87D17D0A|22010:Kan tijdelijke identiteit niet opslaan|
|-2016314103|0x87D17D09|22009: tijdelijke identiteit kan niet worden gemaakt|
|-2016314104|0x87D17D08|22008:Kan identiteit niet maken|
|-2016314105|0x87D17D07|22007:Ongeldig ondertekend certificaat|
|-2016314106|0x87D17D06|22006:Onvoldoende CACaps|
|-2016314107|0x87D17D05|22005:Netwerkfout|
|-2016314108|0x87D17D04|22004:Niet-ondersteunde certificaatconfiguratie|
|-2016314109|0x87D17D03|22003:Ongeldige RAResponse|
|-2016314110|0x87D17D02|22003:Ongeldige CaResponse|
|-2016314111|0x87D17D01|22001:Kan sleutelpaar niet genereren|
|-2016314112|0x87D17D00|22000:Ongeldig sleutelgebruik|
|-2016315105|0x87D1791F|21007:Kan account niet verifiëren|
|-2016315106|0x87D1791E|21006:Kan certificaat niet ontsleutelen|
|-2016315107|0x87D1791D|21005: Account niet uniek (e-mailprofiel bestaat al op apparaat)|
|-2016315108|0x87D1791C|21007:Kan account niet maken|
|-2016315109|0x87D1791B|21003:Geen hostnaam|
|-2016315110|0x87D1791A|21002:Kan niet voldoen aan versleutelingsbeleid van server|
|-2016315111|0x87D17919|21001:Kan niet voldoen aan beleid van server|
|-2016315112|0x87D17918|21000:Kan beleid van server niet ophalen|
|-2016316110|0x87D17532|20002:Account niet uniek|
|-2016316111|0x87D17531|20001:Geen hostnaam|
|-2016316112|0x87D17530|20000:Kan account niet maken|
|-2016317110|0x87D1714A|19002:Account niet uniek|
|-2016317111|0x87D17149|19001:Geen hostnaam|
|-2016317112|0x87D17148|19000:Kan account niet maken|
|-2016318110|0x87D16D62|18002:Ongeldige referenties|
|-2016318111|0x87D16D61|18001:Kan host niet bereiken|
|-2016318112|0x87D16D60|18000:Onbekende fout|
|-2016319110|0x87D1697A|17002:Account niet uniek|
|-2016319111|0x87D16979|17001:Geen hostnaam|
|-2016319112|0x87D16978|17000:Kan account niet maken|
|-2016320110|0x87D16592|16002:Account niet uniek|
|-2016320111|0x87D16591|16001:Geen hostnaam|
|-2016320112|0x87D16590|16000:Kan geen abonnement maken|
|-2016321109|0x87D161AB|15003:Ongeldig certificaat|
|-2016321110|0x87D161AA|15002:Kan netwerkconfiguratie niet vergrendelen|
|-2016321111|0x87D161A9|15001:Kan VPN niet verwijderen|
|-2016321112|0x87D161A8|15000:Kan VPN niet installeren|
|-2016322110|0x87D15DC2|14002:Cloudconfiguratie bestaat al|
|-2016322111|0x87D15DC1|14001:Apparaat vergrendeld|
|-2016322112|0x87D15DC0|14000:Ongeldig veld|
|-2016323107|0x87D159DD|13005:Kan proxy niet instellen|
|-2016323108|0x87D159DC|13004:Kan EAP niet instellen|
|-2016323109|0x87D159DB|13003:Kan Wifi-configuratie niet maken|
|-2016323110|0x87D159DA|13002:Wachtwoord vereist|
|-2016323111|0x87D159D9|13001:Gebruikersnaam vereist|
|-2016323112|0x87D159D8|13000:Kan niet installeren|
|-2016324070|0x87D1561A|12042:Onbekende landinstellingscode|
|-2016324071|0x87D15619|12041:Onbekende taalcode|
|-2016324072|0x87D15618|12040:Aanmelden iTunes Store vereist|
|-2016324073|0x87D15617|12039:(niet gebruikt)|
|-2016324074|0x87D15616|12038:App niet beheerd|
|-2016324075|0x87D15615|12037:Ongeldige inwisselcode|
|-2016324076|0x87D15614|12036:Kan app in de huidige status niet verwijderen|
|-2016324077|0x87D15613|12035:App kan niet worden aangekocht|
|-2016324078|0x87D15612|12034:URL is geen HTTPS|
|-2016324079|0x87D15611|12033:Ongeldig manifest|
|-2016324080|0x87D15610|12032:Te veel apps in manifest|
|-2016324081|0x87D1560F|12031:App-installatie uitgeschakeld|
|-2016324082|0x87D1560E|12030:Ongeldige URL|
|-2016324083|0x87D1560D|12029:App niet beheerd|
|-2016324084|0x87D1560C|12028:Niet wachten op inwisseling|
|-2016324085|0x87D1560B|12027:Geen app|
|-2016324086|0x87D1560A|12026:App staat al in de wachtrij|
|-2016324087|0x87D15609|12025:App is al geïnstalleerd|
|-2016324088|0x87D15608|12024:Kan app-manifest niet valideren|
|-2016324089|0x87D15607|12023:Kan app-id niet valideren|
|-2016324090|0x87D15606|12022:Ongeldig onderwerp|
|-2016324091|0x87D15605|12021:Ongeldig aanvraagtype|
|-2016324092|0x87D15604|12020:Niet geautoriseerd door server|
|-2016324093|0x87D15603|12019:Kan escrow-geheim niet kopiëren|
|-2016324094|0x87D15602|12018:Kan escrow-versleutelingsgegevens niet kopiëren|
|-2016324095|0x87D15601|12017:Kan escrow-versleuteling niet maken|
|-2016324096|0x87D15600|12016:Identiteit ontbreekt|
|-2016324097|0x87D155FF|12015:Kan geen push-token ophalen|
|-2016324098|0x87D155FE|12014:Profiel voor inrichting niet beheerd|
|-2016324099|0x87D155FD|12013:Profiel niet beheerd|
|-2016324100|0x87D155FC|12012:MDM-vervanging niet gelijk|
|-2016324101|0x87D155FB|12011:Ongeldige MDM-configuratie|
|-2016324102|0x87D155FA|12010:Fout interne inconsistentie|
|-2016324103|0x87D155F9|12009:Ongeldig vervangingsprofiel|
|-2016324104|0x87D155F8|12008:Onjuist gevormde aanvraag|
|-2016324105|0x87D155F7|12007:Niet gemachtigd|
|-2016324106|0x87D155F6|12006:Omleiding afgewezen|
|-2016324107|0x87D155F5|12005:Kan certificaat niet vinden|
|-2016324108|0x87D155F4|12004:Ongeldig push-certificaat|
|-2016324109|0x87D155F3|12003:Reactie ongeldige uitdaging|
|-2016324110|0x87D155F2|12002:Kan niet inchecken|
|-2016324111|0x87D155F1|12001:Meerdere MDM-exemplaren|
|-2016324112|0x87D155F0|12000:Ongeldige toegangsrechten|
|-2016325111|0x87D15209|11001:Aangepaste APN is al geïnstalleerd|
|-2016325112|0x87D15208|11000:Kan APN niet installeren|
|-2016326111|0x87D14E21|10001:Ongeldige ondertekenaar|
|-2016326112|0x87D14E20|11000:Kan standaardinstellingen niet installeren|
|-2016327106|0x87D14A3E|9006:Certificaat is geen identiteit|
|-2016327107|0x87D14A3D|9005:Certificaat is misvormd|
|-2016327108|0x87D14A3C|9004:Kan basiscertificaat niet opslaan|
|-2016327109|0x87D14A3B|9003:Kan WAPI-gegevens  niet opslaan|
|-2016327110|0x87D14A3A|9002:Kan Store-certificaat niet opslaan|
|-2016327111|0x87D14A39|9001:Te veel certificaten in een nettolading|
|-2016327112|0x87D14A38|9000:Ongeldig wachtwoord|
|-2016328112|0x87D14650|8000:Kan Web Clip niet installeren|
|-2016329105|0x87D1426F|7007:SMTP-account is onjuist geconfigureerd|
|-2016329106|0x87D1426E|7006:POP-account is onjuist geconfigureerd|
|-2016329107|0x87D1426D|7005:IMAP-account onjuist geconfigureerd|
|-2016329108|0x87D1426C|7004:SMIME-certificaat is beschadigd|
|-2016329109|0x87D1426B|7003:SMIME-certificaat is niet gevonden|
|-2016329110|0x87D1426A|7002:Onbekende fout tijdens validatie|
|-2016329111|0x87D14269|7001:Ongeldige referenties|
|-2016329112|0x87D14268|7000:Kan host niet bereiken|
|-2016330110|0x87D13E82|6002:Kan query niet maken|
|-2016330111|0x87D13E81|6001:Lege tekenreeks|
|-2016330112|0x87D13E80|6000:Systeemfout in sleutelketengegevens|
|-2016331097|0x87D13AA7|5015:Kan geen respijtperiode instellen|
|-2016331098|0x87D13AA6|5014:Kan geen wachtwoordcode instellen|
|-2016331099|0x87D13AA5|5013:Kan wachtwoordcode niet wissen|
|-2016331100|0x87D13AA4|5012:(niet gebruikt)|
|-2016331101||5011:Verkeerde wachtwoordcode|
|-2016331102||5010:Apparaat vergrendeld|
|-2016331103|0x87D13AA4|5009:(niet gebruikt)|
|-2016331104|0x87D13AA0|5008:Wachtwoordcode te recent|
|-2016331105|0x87D13A9F|5007:Wachtwoordcode verlopen|
|-2016331106|0x87D13AA3|5006:Wachtwoordcode vereist alfabettekens|
|-2016331107|0x87D13A9D|5005:Wachtwoordcode vereist getal|
|-2016331108|0x87D13A9C|5004:Wachtwoordcode bevat oplopende aflopende tekens|
|-2016331109|0x87D13A9B|5003:Wachtwoordcode bevat herhaalde tekens|
|-2016331110|0x87D13A9A|5002:Te weinig complexe tekens|
|-2016331111|0x87D13A99|5001:Te weinig unieke tekens|
|-2016331112|0x87D13A98|5000:Wachtwoordcode is te kort|
|-2016332093|0x87D136C3|4019:Nettoladingen voor meerdere app-vergrendelingen|
|-2016332094|0x87D136C2|4018:Meerdere APN- of mobiele nettoladingen|
|-2016332095|0x87D136C1|4017:Meerdere algemene HTTPProxy-nettoladingen|
|-2016332096|0x87D136C0|4016:(Interne fout)|
|-2016332097|0x87D136BF|4015:Vervangingsprofiel bevat geen MDM-nettolading|
|-2016332098|0x87D136BE|4014:Geen apparaat-id beschikbaar|
|-2016332099|0x87D136BD|4013:Update mislukt|
|-2016332100|0x87D136BC|4012:Profiel kan niet worden bijgewerkt|
|-2016332101|0x87D136BB|4011:Eindprofiel is geen configuratieprofiel|
|-2016332102|0x87D136BA|4010:Bijgewerkt profiel heeft niet dezelfde id|
|-2016332103|0x87D136B9|4009:Apparaat vergrendeld|
|-2016332104|0x87D136B8|4008:Certificaten komen niet overeen|
|-2016332105|0x87D136B7|4007:Niet-herkende bestandsindeling|
|-2016332106|0x87D136B6|4006:Datum verwijdering profiel is verstreken|
|-2016332107|0x87D136B5|4005:Wachtwoordcode voldoet niet|
|-2016332108|0x87D136B4|4004:Installatie geannuleerd door de gebruiker|
|-2016332109|0x87D136B3|4003:Profiel niet in wachtrij voor installatie|
|-2016332110|0x87D136B2|4002:Dubbele UUID|
|-2016332111|0x87D136B1|4001:Installatie mislukt|
|-2016332112|0x87D136B0|4000:Kan profiel niet parseren|
|-2016333111|0x87D132C9|3001:Inconsistent waardevergelijkingsinzicht (interne fout)|
|-2016333112|0x87D132C8|3000:Inconsistent beperkingsinzicht (interne fout)|
|-2016334108|0x87D12EE4|2004:Niet-ondersteunde veldwaarde|
|-2016334109|0x87D12EE3|2003:Ongeldig gegevenstype in veld|
|-2016334110|0x87D12EE2|2002:Vereist veld ontbreekt|
|-2016334111|0x87D12EE1|2001:Niet-ondersteunde versie nettolading|
|-2016334112|0x87D12EE0|2000:Onjuist gevormde nettolading|
|-2016335102|0x87D12B02|1010:Niet-ondersteunde veldwaarde|
|-2016335103|0x87D12B01|1009:Installatiefout profiel|
|-2016335104|0x87D12B00|1008:Niet-unieke nettolading-id's|
|-2016335105|0x87D12AFF|1007:Niet-unieke UUID's|
|-2016335106|0x87D12AFE|1006:Kan niet ontsleutelen|
|-2016335107|0x87D12AFD|1005:Leeg profiel|
|-2016335108|0x87D12AFC|1004:Ongeldige handtekening|
|-2016335109|0x87D12AFB|1003:Ongeldig gegevenstype in veld|
|-2016335110|0x87D12AFA|1002:Vereist veld ontbreekt|
|-2016335111|0x87D12AF9|1001:Niet-ondersteunde profielversie|
|-2016335112|0x87D12AF8|1000:Onjuist gevormd profiel|

## <a name="oma-response-codes"></a>OMA-reactiecodes

|Statuscode|Hexadecimale foutcode|Foutbericht|
|---------------|--------------------------|-----------------|
|-2016344008|0x87D10838|(1404): certificaattoegang geweigerd|
|-2016344009|0x87D10837|(1403): kan certificaat niet vinden|
|-2016344010|0x87D10836|DCMO(1402): de bewerking is mislukt|
|-2016344011|0x87D10835|DCMO(1401): de gebruiker heeft ervoor gekozen de bewerking niet te accepteren toen daarom werd gevraagd|
|-2016344012|0x87D10834|DCMO(1400): clientfout|
|-2016344108|0x87D107D4|DCMO(1204): de apparaatondersteuning is uitgeschakeld en de gebruiker mag deze opnieuw inschakelen|
|-2016344109|0x87D107D3|DCMO(1203): de apparaatondersteuning is uitgeschakeld en de gebruiker mag deze niet opnieuw inschakelen|
|-2016344110|0x87D107D2|DCMO(1202): de inschakelbewerking is uitgevoerd, maar de apparaatondersteuning is momenteel losgekoppeld|
|-2016344111|0xF3FB4D95|DCMO(1201): de inschakelbewerking is uitgevoerd en de apparaatondersteuning is momenteel gekoppeld|
|-2016344112|0x87D107D0|DCMO(1200): de bewerking is uitgevoerd|
|-2016345595|0x87D10205|Syncml(517): de reactie op een atomische opdracht is te groot voor één bericht.|
|-2016345596|0x87D10204|Syncml(516): de opdracht bevindt zich in een Atomic-element en Atomic is mislukt. Deze opdracht is niet teruggedraaid.|
|-2016345598|0x87D10202|Syncml(514): de SyncML-opdracht is niet voltooid, omdat de bewerking is geannuleerd voordat de opdracht werd verwerkt.|
|-2016345599|0x87D10201|Syncml(513): de ontvanger biedt geen ondersteuning of weigert deze voor de opgegeven versie van het SyncML-synchronisatieprotocol dat wordt gebruikt in het aanvraag-SyncML-bericht.|
|-2016345600|0x87D10200|Syncml(512): er is een toepassingsfout opgetreden tijdens de synchronisatiesessie.|
|-2016345601|0x87D101FF|Syncml(511): er is een ernstige fout opgetreden in de server tijdens het verwerken van de aanvraag.|
|-2016345602|0x87D101FE|Syncml(510): er is een fout opgetreden tijdens het verwerken van de aanvraag. De fout is gerelateerd aan een fout in de gegevensopslag van de ontvanger.|
|-2016345603|0x87D101FD|Syncml(509): gereserveerd voor toekomstig gebruik.|
|-2016345604|0x87D101FC|Syncml:(508): er is een fout opgetreden die het vernieuwen van de huidige synchronisatiestatus van de client bij de server noodzakelijk maakt.|
|-2016345605|0x87D101FB|Syncml(507): door de fout zijn alle SyncML-opdrachten binnen een Atomic-elementtype mislukt.|
|-2016345606|0x87D101FA|Syncml(506): er is een toepassingsfout opgetreden tijdens het verwerken van de aanvraag.|
|-2016345607|0x87D101F9|Syncml(505): de ontvanger biedt geen ondersteuning of weigert deze voor de opgegeven versie van SyncML DTD die wordt gebruikt in het aanvraag-SyncML-bericht.|
|-2016345608|=0x87D101F8|Syncml(504): de ontvanger, fungerend als gateway of proxy, heeft geen tijdige reactie ontvangen van de upstream-ontvanger die is opgegeven door de URI (bijvoorbeeld HTTP, FTP of LDAP) of een andere hulpontvanger (bijvoorbeeld DNS) waartoe toegang nodig is om de aanvraag te voltooien.|
|-2016345609|0x87D101F7|Syncml(503): de ontvanger kan de aanvraag momenteel niet afhandelen door tijdelijke overbelasting of onderhoud van de ontvanger.|
|-2016345610|0x87D101F6|Syncml(502): de ontvanger, fungerend als gateway of proxy, heeft een ongeldige reactie ontvangen van de upstream-ontvanger die is geopend om aan de aanvraag te voldoen.|
|-2016345611|0x87D101F5|Syncml(501): de ontvanger ondersteunt de opdracht niet die nodig is om aan de aanvraag te voldoen.|
|-2016345612|0x87D101F4|Syncml(500): er is een onverwachte status opgetreden bij de ontvanger, waardoor niet aan de aanvraag kan worden voldaan.|
|-2016345684|0x87D101AC|Syncml(428): het verplaatsen is mislukt|
|-2016345685|0x87D101AB|Syncml(427): het bovenliggende item kan niet worden verwijderd, omdat het onderliggende items bevat.|
|-2016345686|0x87D101AA|Syncml(426): het gedeeltelijke item wordt niet geaccepteerd.|
|-2016345687|0x87D101A9|Syncml(425): de aangevraagde opdracht is mislukt, omdat de afzender niet over de juiste toegangsbeheermachtigingen (ACL) beschikt voor de ontvanger.|
|-2016345688|0x87D101A8|Syncml(424): het gesegmenteerde object is ontvangen, maar de grootte van het ontvangen object komt niet overeen met de grootte die in het eerste segment is gedeclareerd.|
|-2016345689|0x87D101A7|Syncml(423): de aangevraagde opdracht is mislukt omdat het voorlopig verwijderde item eerder permanent is verwijderd op de server.|
|-2016345690|0x87D101A6|Syncml(422): de aangevraagde opdracht is mislukt op de server, omdat CGI-scripts in de LocURI geen correcte indeling hebben.|
|-2016345691|0x87D101A5|Syncml(421): de aangevraagde opdracht is mislukt op de server, omdat de opgegeven zoeksyntaxis niet bekend is.|
|-2016345692|0x87D101A4|Syncml(420): de ontvanger heeft geen opslagruimte meer voor de resterende synchronisatiegegevens.|
|-2016345693|0x87D101A3|Syncml(419): de clientaanvraag heeft gezorgd voor een conflict; dit is opgelost door de serveropdracht voorrang te geven.|
|-2016345694|0x87D101A2|Syncml(418): de aangevraagde opdracht Plaatsen of Toevoegen is mislukt, omdat het doel al bestaat.|
|-2016345695|0x87D101A1|Syncml(417): de aanvraag is nu mislukt en de oorspronkelijke aanvrager moet de aanvraag later opnieuw proberen.|
|-2016345696|0x87D101A0|Syncml(416): de aanvraag is mislukt, omdat de opgegeven bytegrootte in de aanvraag te groot is.|
|-2016345697|0x87D1019F|Syncml(415): het type of de indeling van het medium wordt niet ondersteund.|
|-2016345698|0x87D1019E|Syncml(414): de aangevraagde opdracht is mislukt, omdat de doel-URI te lang is voor wat de ontvanger kan of wil verwerken.|
|-2016345699|0x87D1019D|Syncml(413): de ontvanger weigert de aangevraagde opdracht uit te voeren, omdat het aangevraagde item groter is dan wat de ontvanger kan of wil verwerken.|
|-2016345700|0x87D1019C|Syncml(412): de aangevraagde opdracht is mislukt bij de ontvanger, omdat deze onvolledig is of een onjuiste indeling heeft.|
|-2016345701|0x87D1019B|Syncml(411): de aangevraagde opdracht moet vergezeld gaan van de bytegrootte of lengtegegevens in het meta-elementtype.|
|-2016345702|0x87D1019A|Syncml(410): het aangevraagde doel bevindt zich niet meer bij de ontvanger en er is geen doorstuur-URI bekend.|
|-2016345703|0x87D10199|Syncml(409): de aanvraag is mislukt, omdat er een updateconflict tussen de client- en serverversies van de gegevens is opgetreden.|
|-2016345704|0x87D10198|Syncml(408): een verwacht bericht is niet ontvangen binnen de vereiste periode.|
|-2016345705|0x87D10197|Syncml(407): de aangevraagde opdracht is mislukt, omdat de oorspronkelijke aanvrager de juiste verificatiegegevens moet opgeven.|
|-2016345706|0x87D10196|Syncml(406): de aangevraagde opdracht is mislukt, omdat een optionele functie in de aanvraag niet wordt ondersteund.|
|-2016345707|0x87D10195|Syncml(405): de aangevraagde opdracht is niet toegestaan bij het doel.|
|-2016345708|0x87D10194|Syncml(404): het aangevraagde doel is niet gevonden.|
|-2016345709|0x87D10193|Syncml(403): de aangevraagde opdracht is mislukt, maar de ontvanger heeft de aangevraagde opdracht begrepen.|
|-2016345710|0x87D10192|Syncml(402): de aangevraagde opdracht is mislukt, omdat de juiste betaling nodig is.|
|-2016345711|0x87D10191|Syncml(401): de aangevraagde opdracht is mislukt, omdat de aanvrager de juiste verificatiegegevens moet opgeven.|
|-2016345712|0x87D10190|Syncml(400): de aangevraagde opdracht kan niet worden uitgevoerd door een ongeldige syntaxis in de opdracht.|
|-2016345807|0x87D10131|Syncml(305): het aangevraagde doel moet worden geopend via de opgegeven proxy-URI.|
|-2016345808|0x87D10130|Syncml (304): De aangevraagde SyncML-opdracht is niet uitgevoerd op het doel.|
|-2016345809|0x87D1012F|Syncml(303): het aangevraagde doel kan worden gevonden op een andere URI.|
|-2016345810|0x87D1012E|Syncml(302): het aangevraagde doel is tijdelijk verplaatst naar een andere URI.|
|-2016345811|0x87D1012D|Syncml(301): het aangevraagde doel heeft een nieuwe URI.|
|-2016345812|0x87D1012C|Syncml(300): het aangevraagde doel is een van meerdere alternatieve aangevraagde doelen.|
|-2016345896|0x87D100D8|Syncml(216): een opdracht bevindt zich in een Atomic-element en Atomic is mislukt. Deze opdracht is teruggedraaid.|
|-2016345897|0x87D100D7|Syncml(215): een opdracht is niet uitgevoerd als gevolg van een gebruikersinteractie waarbij de gebruiker de keuze niet heeft geaccepteerd.|
|-2016345898|0x87D100D6|Syncml(214): de bewerking is geannuleerd. De SyncML-opdracht is uitgevoerd, maar er worden niet meer opdrachten verwerkt in de sessie.|
|-2016345899|0x87D100D5|Syncml(213): het gesegmenteerde item is geaccepteerd en in een buffer opgeslagen|
|-2016345900|0x87D100D4|Syncml(212): de authenticatie is geaccepteerd. Geen verdere authenticatie vereist voor het restant van de synchronisatiesessie. Deze antwoordcode kan alleen worden gebruikt als antwoord op een aanvraag waarin de referenties zijn opgenomen.|
|-2016345901|0x87D100D3|Syncml(211): het item is niet verwijderd. Het opgevraagde item is niet gevonden. Mogelijk is het eerder verwijderd.|
|-2016345902|0x87D100D2|Syncml(210): verwijderen zonder archivering. Het antwoord geeft aan dat de opgevraagde gegevens zijn verwijderd, maar niet gearchiveerd vóór de verwijdering, omdat deze OPTIONELE functie niet wordt ondersteund door de implementatie.|
|-2016345903|0x87D100D1|Conflict opgelost met duplicaat. Het antwoord geeft aan dat de aanvraag heeft geleid tot een updateconflict dat vervolgens is opgelost doordat de gegevens van de client zijn gedupliceerd in de serverdatabase. Het antwoord bevat de doel-URI van het duplicaat in het statusitem. In het geval van tweerichtingssynchronisatie wordt er bovendien een Add-opdracht geretourneerd met de definitie van de duplicaatgegevens.|
|-2016345904|0x87D100D0|Conflict opgelost doordat de opdracht van de client heeft 'gewonnen'. Het antwoord geeft aan dat er een updateconflict was dat is opgelost doordat de opdracht van de client met prioriteit is uitgevoerd.|
|-2016345905|0x87D100CF|Conflict opgelost door samenvoeging. Het antwoord geeft aan dat de aanvraag heeft geleid tot een conflict dat vervolgens is opgelost doordat de client- en serverinstanties van de gegevens zijn samengevoegd. Het antwoord bevat de doel-URL en de bron-URL in het statusitem. Bovendien is een Replace-opdracht geretourneerd met de samengevoegde gegevens.|
|-2016345906|0x87D100CE|Het antwoord geeft aan dat de opdracht slechts gedeeltelijk is uitgevoerd. Als het restant van de opdracht later kan worden uitgevoerd, MOET, na het voltooien van de volledige opdracht, een andere correcte statuscode voor het voltooien van de aanvraag worden gemaakt.|
|-2016345907|0x87D100CD|De bron MOET zijn inhoud bijwerken. De oorspronkelijke aanvrager wordt verteld dat zijn inhoud MOET worden gesynchroniseerd om een bijgewerkte versie te krijgen.|
|-2016345908|0x87D100CC|De aanvraag is voltooid, maar er worden geen gegevens geretourneerd. De antwoordcode wordt ook geretourneerd als antwoord op een Get-opdracht wanneer het doel geen inhoud bevat.|
|-2016345909|0x87D100CB|Niet-bindend antwoord. De aanvraag wordt beantwoord door een andere entiteit dan de doelentiteit. Het antwoord zou alleen moeten worden geretourneerd wanneer de aanvraag had geleid tot een 200-antwoordcode van de gezaghebbende doelentiteit.|
|-2016345910|0x87D100CA|Geaccepteerd voor verwerking. De aanvraag om een toepassing extern uit te voeren of om een gebruiker of toepassing te waarschuwen, is met succes uitgevoerd.|
|-2016345911|0x87D100C9|Het opgevraagde item is toegevoegd.|
|-2016345912|0x87D100C8|De SyncML-opdracht is uitgevoerd.|
|-2016346011|0x87D10065|De opgegeven SyncML-opdracht wordt uitgevoerd, maar is niet voltooid.|

### <a name="next-steps"></a>Volgende stappen
Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](../troubleshoot/how-to-get-support-for-microsoft-intune.md).



<!--HONumber=Dec16_HO2-->


