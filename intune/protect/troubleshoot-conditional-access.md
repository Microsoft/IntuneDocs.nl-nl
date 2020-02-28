---
title: Problemen met voorwaardelijke toegang oplossen
titleSuffix: Microsoft Intune
description: Dit kunt u doen wanneer uw gebruikers geen toegang krijgen tot bedrijfsresources via voorwaardelijke toegang van Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/23/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 5fa59501-5f33-46b7-a5f5-75eeae9f1209
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0d6dc10eca80a7d403d0ff44c25d3cfaed85fafa
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514197"
---
# <a name="troubleshoot-conditional-access"></a>Problemen met voorwaardelijke toegang oplossen
In dit artikel wordt beschreven wat u moet doen wanneer uw gebruikers geen toegang kunnen krijgen tot resources die met voorwaardelijke toegang zijn beschermd, of wanneer gebruikers wel toegang tot beschermde resources kunnen krijgen, maar eigenlijk zouden moeten worden geblokkeerd.

Met Intune en voorwaardelijke toegang kunt u de toegang tot services beveiligen, zoals:
- Office 365-services zoals Exchange Online, SharePoint Online en Skype voor Bedrijven Online
- Exchange On-premises
- Verschillende andere services

Hiermee zorgt u ervoor dat alleen apparaten die bij Intune zijn ingeschreven en de regels voor voorwaardelijke toegang naleven die u in de Intune-beheerconsole of via Azure Active Directory hebt ingesteld toegang hebben tot uw bedrijfsresources. 

## <a name="requirements-for-conditional-access"></a>Vereisten voor voorwaardelijke toegang

Er moet aan de volgende vereisten zijn voldaan voordat voorwaardelijke toegang werkt:

- Het apparaat moet worden ingeschreven bij MDM en beheerd door Intune.

- Zowel de gebruiker als het apparaat moeten voldoen aan het toegewezen nalevingsbeleid van Intune.

- Aan de gebruiker moet standaard een apparaatnalevingsbeleid zijn toegewezen. Dit kan afhankelijk zijn van de manier waarop de instelling **Apparaten waaraan geen nalevingsbeleid is toegewezen markeren als** onder **Apparaatnaleving** > **Instellingen nalevingsbeleid** in de Intune-beheerportal is geconfigureerd.

- EAS (Exchange ActiveSync) moet worden geactiveerd op het apparaat als de gebruiker de systeemeigen e-mailclient van het apparaat gebruikt in plaats van Outlook. Dit gebeurt automatisch voor iOS-, Windows Phone- en Android Knox-apparaten.

- Voor on-premises Exchange, moet de Intune Exchange-connector juist zijn geconfigureerd. Raadpleeg [Het oplossen van problemen met de Exchange Connector in Microsoft Intune](troubleshoot-exchange-connector.md) voor meer informatie.

- Voor on-premises Skype moet u hybride moderne verificatie configureren. Raadpleeg [Overzicht van hybride moderne verificatie](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview).

Deze voorwaarden voor elk apparaat zijn terug te vinden in Azure Portal en in het inventarisrapport van het apparaat.

## <a name="devices-appear-compliant-but-users-are-still-blocked"></a>Het lijkt of apparaten aan de eisen voldoen, maar gebruikers zijn nog steeds geblokkeerd

- Zorg dat aan de gebruiker een Intune-licentie is toegewezen voor een juiste nalevingsbeoordeling.

- Aan Android-apparaten zonder Knox wordt pas toegang verleend zodra de gebruiker op de koppeling **Nu aan de slag** klikt die in de quarantaine-e-mail staat die ze hebben ontvangen. Dit is zelfs van toepassing wanneer de gebruiker al is ingeschreven in Intune. Als gebruikers de e-mail met de koppeling niet op hun telefoon hebben ontvangen, kunnen ze een pc gebruiken voor toegang tot hun e-mail en de e-mail doorsturen naar een e-mailaccount op hun apparaat.

- Wanneer een apparaat voor de eerste keer wordt ingeschreven, kan het even duren voordat de nalevingsinformatie voor een apparaat is geregistreerd. Wacht een paar minuten en probeer het opnieuw.

- Voor iOS-/iPadOS-apparaten kan een bestaand e-mailprofiel de implementatie blokkeren van een door een Intune-beheerder gemaakt e-mailprofiel dat aan deze gebruiker is toegewezen, waardoor het apparaat niet meer aan de vereisten voldoet. In dit scenario deelt de bedrijfsportal-app de gebruiker mee dat deze niet voldoet aan de eisen vanwege het handmatig geconfigureerde e-mailprofiel en wordt de gebruiker gevraagd dit profiel te verwijderen. Zodra de gebruiker het bestaande e-mailprofiel verwijdert, kan het Intune-e-mailprofiel worden geïmplementeerd. Om dit probleem te voorkomen, moet u uw gebruikers opdragen eventuele bestaande e-mailprofielen op hun apparaat te verwijderen voordat ze zich gaan inschrijven.

- Een apparaat kan vast komen te zitten in een status voor het controleren van nalevingsvereisten, waardoor de gebruiker wordt verhinderd om een andere incheckprocedure te beginnen. Als u een apparaat hebt met deze status:
  - Controleer of op het apparaat de nieuwste versie van de bedrijfsportal-app wordt gebruikt.
  - Start het apparaat opnieuw op.
  - Kijk of het probleem zich ook voordoet bij andere netwerken (bijvoorbeeld een mobiel netwerk of via Wi-Fi).

  Als dit probleem zich blijft voordoen, neemt u contact op met Microsoft Ondersteuning, zoals wordt beschreven in [Ondersteuning voor Microsoft Intune krijgen](../fundamentals/get-support.md).

- Bepaalde Android-apparaten lijken mogelijk te zijn versleuteld, maar de bedrijfsportal-app herkent deze apparaten als niet-versleuteld en markeert deze als apparaten die niet aan de eisen voldoen. In dit scenario krijgt de gebruiker een bericht in de bedrijfsportal-app waarin wordt gevraagd om een wachtwoordcode voor het opstarten van het apparaat in te stellen. Wanneer u op het bericht tikt en de bestaande pincode of het wachtwoord hebt bevestigd, kiest u de optie **Pincode vereisen voor het starten van het apparaat** op het scherm **Beveiligd opstarten**. Tik vervolgens vanuit de bedrijfsportal-app op de knop **Naleving controleren** voor het apparaat. Het apparaat moet nu worden gedetecteerd als versleuteld. 

  > [!NOTE]
  > Sommige apparaatfabrikanten versleutelen hun apparaten met behulp van een standaardpincode in plaats van een pincode die door de gebruiker wordt ingesteld. Intune beschouwt versleuteling met een standaardpincode als onveilig en markeert die apparaten als niet-conform totdat de gebruiker een nieuwe, niet-standaard pincode heeft gemaakt.

- Een Android-apparaat dat is ingeschreven en aan de eisen voldoet, kan alsnog worden geblokkeerd en een quarantainemelding ontvangen wanneer een gebruiker voor de eerste keer bedrijfsresources probeert te openen. Als dit gebeurt, controleert u of de bedrijfsportal-app niet wordt uitgevoerd en selecteert u vervolgens op de koppeling **Nu aan de slag** in de quarantaine-e-mail om evaluatie te activeren. Dit hoeft alleen te gebeuren wanneer voorwaardelijke toegang voor de eerste keer wordt ingeschakeld.

- Op een Android-apparaat dat is ingeschreven, ziet de gebruiker mogelijk Geen certificaten gevonden, en krijgt de gebruiker geen toegang tot O365-resources. De gebruikers moeten de optie *Browsertoegang inschakelen* als volgt inschakelen op geregistreerde apparaten:
  1. Open de app Bedrijfsportal.
  2. Ga naar de pagina Instellingen via de drie puntjes (...) of via de menuknop van de hardware.
  3. Selecteer de knop *Browsertoegang inschakelen*.
  4. In de browser Chrome meldt u zich af bij Office 365. Start vervolgens Chrome opnieuw op.  


## <a name="devices-are-blocked-and-no-quarantine-email-is-received"></a>Apparaten worden geblokkeerd en er is geen quarantaine-e-mail ontvangen

- Controleer of het apparaat in de Intune-beheerconsole te zien is als een Exchange ActiveSync-apparaat. Indien dit niet het geval is, werkt waarschijnlijk de apparaatdetectie niet, mogelijk vanwege een probleem in de Exchange-connector. Raadpleeg [Problemen met de Intune on-premises Exchange-connector oplossen](troubleshoot-exchange-connector.md) voor meer informatie.

- Voordat de Exchange-connector een apparaat blokkeert, wordt een activerings-e-mail (quarantaine) verzonden. Als het apparaat offline is, wordt de activerings-e-mail mogelijk niet ontvangen. 

- Controleer of de e-mailclient op het apparaat is geconfigureerd voor het ophalen van e-mail met behulp van **Push** in plaats van **Poll**. Als dit het geval is, kan dit ertoe leiden dat de gebruiker de e-mail over het hoofd ziet. Schakel over naar **Poll** en kijk of de e-mail op het apparaat wordt ontvangen.

## <a name="devices-are-noncompliant-but-users-are-not-blocked"></a>Apparaten zijn niet-conform maar gebruikers worden niet geblokkeerd

- Voor Windows-pc's wordt met voorwaardelijke toegang alleen de systeemeigen e-mail-app, Office 2013 met moderne verificatie of Office 2016 geblokkeerd. Voor het blokkeren van eerdere versies van Outlook of alle mail-apps op Windows-pc's zijn AAD-apparaatregistraties en Active Directory Federation Services-configuraties (AD FS) vereist conform de instructies in [Voorwaardelijke toegang instellen voor SharePoint Online en Exchange Online voor Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication).

- Als het apparaat selectief wordt gewist of buiten gebruik wordt gesteld in Intune, kan het zijn dat het apparaat nog enige uren na de buitengebruikstelling toegang heeft. Dit komt doordat Exchange de toegangsrechten gedurende zes uur in het cachegeheugen opslaat. Overweeg andere manieren om gegevens op buiten gebruik gestelde apparaten te beveiligen in dit scenario.

- Surface Hub, bulksgewijs ingeschreven, en met DEM ingeschreven Windows-apparaten kunnen ondersteuning bieden voor voorwaardelijke toegang wanneer een gebruiker is aangemeld aan wie een Intune-licentie is toegewezen. Voor een juiste evaluatie moet u echter wel het nalevingsbeleid implementeren in apparaatgroepen (niet in gebruikersgroepen).

- Controleer de toewijzingen voor uw nalevingsbeleid en uw beleid voor voorwaardelijke toegang. Als een gebruiker geen lid is van de groep waaraan het beleid is toegewezen, of lid is van een groep die is uitgesloten, wordt deze gebruiker niet geblokkeerd. Alleen apparaten voor gebruikers in een toegewezen groep worden gecontroleerd op naleving.

## <a name="noncompliant-device-is-not-blocked"></a>Niet-compatibel apparaat wordt niet geblokkeerd

Als een apparaat niet compatibel is, maar nog steeds toegang heeft, voert u de volgende acties uit.

- Controleer de doelgroepen en de groepen die zijn uitgesloten. Als een gebruiker zich niet in de juiste doelgroep of in de groep die is uitgesloten bevindt, wordt deze niet geblokkeerd. Alleen apparaten van gebruikers in een doelgroep worden gecontroleerd op naleving.

- Zorg ervoor dat het apparaat wordt gedetecteerd. Verwijst de Exchange-Connector naar een Exchange 2010 CAS terwijl de gebruiker zich op een Exchange 2013-server bevindt? In dit geval, mits de standaardregel voor Exchange Toestaan is, kan Intune de verbinding van het apparaat met Exchange niet detecteren, zelfs als de gebruiker zich in de doelgroep bevindt.

- Bestaan apparaat/toegangsstatus in Exchange controleren:
  - Gebruik deze PowerShell-cmdlet om een lijst met alle mobiele apparaten voor een postvak op te halen: Get-ActiveSyncDeviceStatistics -mailbox mbx. Als het apparaat niet wordt weergegeven, heeft het geen toegang tot Exchange.
  
  - Als het apparaat wordt weergegeven, gebruikt u de cmdlet 'Get-CASmailbox -identity:’upn’ | fl' voor gedetailleerde informatie over de toegangsstatus en om die informatie aan Microsoft Ondersteuning te verstrekken.

## <a name="next-steps"></a>Volgende stappen
Als deze informatie geen oplossing biedt, kunt u ook [ondersteuning voor Microsoft Intune krijgen](../fundamentals/get-support.md).
