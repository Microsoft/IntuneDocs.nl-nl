---
title: iOS-apps beheren die zijn gekocht via het Volume Purchase Program
titlesuffix: Microsoft Intune
description: Meer informatie over hoe u boeken kunt synchroniseren die u via het volumeaankoopprogramma in de iOS Store hebt gekocht, hoe u deze boeken kunt beheren en hoe u het gebruik ervan kunt bijhouden.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f5617074-2384-4812-b913-dc94f64c0818
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b43e7df72e709cfdd929085b1d6718f1afcdf9f
ms.sourcegitcommit: 2d1e89fa5fa721e79648e41fde147a035e7b047d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/31/2018
ms.locfileid: "43347349"
---
# <a name="how-to-manage-ios-ebooks-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>iOS-apps beheren die u via een volume-aankoopprogramma hebt aangeschaft met Microsoft Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Via het Apple Volume Purchase Program (VPP) kunt u meerdere licenties voor een boek kopen dat u wilt distribueren naar gebruikers in uw bedrijf. U kunt boeken distribueren via de stores voor bedrijven of het onderwijs.

U kunt Microsoft Intune gebruiken om de boeken die u via dit programma hebt gekocht, te synchroniseren, beheren en toe te wijzen. U kunt licentiegegevens uit de store importeren en bijhouden hoeveel van de licenties u hebt gebruikt.

De procedures voor het beheren van boeken zijn vergelijkbaar met die voor het [beheren van VPP-apps](vpp-apps-ios.md).

## <a name="manage-volume-purchased-books-for-ios-devices"></a>Boeken voor iOS-apparaten beheren die zijn gekocht via het Volum Purchase Program
U koopt meerdere licenties voor iOS-boeken via het [Apple Volume Purchase Program voor bedrijven](http://www.apple.com/business/vpp/) of het [Apple Volume Purchase Program voor onderwijs](http://volume.itunes.apple.com/us/store). Hiervoor moet u een Apple VPP-account via de website van Apple instellen en het Apple VPP-token uploaden naar Intune.  U kunt uw gegevens over volume-aankopen vervolgens synchroniseren met Intune en het gebruik bijhouden van de boeken die u via het Volume Purchase Program hebt gekocht.

## <a name="before-you-start"></a>Voordat u begint
Voordat u begint, moet u een VPP-token van Apple verkrijgen en dit uploaden naar uw Intune-account. Aanvullend:

* U kunt maximaal 256 VPP-tokens koppelen aan uw Intune-account.
* Als u eerder een VPP-token hebt gebruikt voor een ander product, moet u een nieuw token voor gebruik met Intune genereren.
* Elke token is één jaar geldig.
* Standaard wordt Intune twee keer per dag gesynchroniseerd met de Apple VPP-service. U kunt op elk gewenst moment een handmatige synchronisatie starten.
* Nadat u het VPP-token hebt geïmporteerd in Intune, kunt u hetzelfde token niet in een andere oplossing voor apparaatbeheer importeren. Dit kan leiden tot verlies van licentietoewijzngen en gebruikersrecords.
* Voordat u begint met het gebruik van iOS-boeken met Intune, verwijdert u eventuele bestaande VPP-gebruikersaccounts die zijn gemaakt met andere MDM-leveranciers (Mobile Device Management). Uit veiligheidsoverwegingen worden deze gebruikersaccounts niet met Intune gesynchroniseerd. Er worden alleen gegevens uit de Apple VPP-service gesynchroniseerd die zijn gemaakt met Intune.
* Wanneer u een boek aan een apparaat toewijst, moet op dat apparaat de ingebouwde app iBooks geïnstalleerd zijn. Als dat niet het geval is, moet de gebruiker de app opnieuw installeren om het boek te kunnen lezen. U kunt Intune momenteel niet gebruiken voor het herstellen van verwijderde ingebouwde apps.
* U kunt alleen boeken op de site van het Apple Volume Purchase Program toewijzen. U kunt niet uploaden en vervolgens de boeken toewijzen die u intern hebt gemaakt.
* U kunt boeken momenteel niet op dezelfde manier toewijzen aan eindgebruikerscategorieën als apps.
* U kunt een licentie niet opnieuw claimen zodra het boek is toegewezen.
* Wanneer een nieuwe gebruiker met een in aanmerking komend apparaat een VPP-boek wil installeren, moet deze zich eerst aanmelden voor het Apple Volume Purchase Program. U kunt ook licenties toewijzen aan beveiligingsgroepen met beheerde Apple-id's. Als u dit doet, worden gebruikers niet naar hun Apple-id gevraagd wanneer een boek wordt geïnstalleerd.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Een Apple VPP-token verkrijgen en uploaden

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Client-apps**.
1.  Kies in de workload **Client-apps** de optie **Instellen** > **VPP-tokens voor iOS**.
2.  Klik in het deelvenster met de lijst met VPP-tokens op **Maken**.
3.  Geef in het deelvenster **Nieuw VPP-token** de volgende gegevens op:
    - **VPP-tokenbestand**: zorg dat u zich hebt aangemeld voor het VPP-programma voor bedrijven of voor het VPP-programma voor onderwijs. Download vervolgens het Apple VPP-token voor uw account en selecteer het hier.
    - **Apple ID**: voer de Apple ID in van het account dat aan het VPP is gekoppeld.
    - **Type VPP-account**: u hebt de keuze uit **Bedrijven** of **Onderwijs**.
4. Wanneer u klaar bent, klikt u op **Maken**.

Het token wordt weergegeven in het deelvenster met de lijst met tokens.


U kunt de gegevens waarover Apple beschikt, op elk gewenst moment synchroniseren met Intune door **Nu synchroniseren** te kiezen.

## <a name="to-assign-a-volume-purchased-app"></a>Een app toewijzen die is gekocht via het volume-aankoopprogramma

3. Kies **eBooks** in het deelvenster **Intune**.
1. Kies in de workload **eBooks** achtereenvolgens **Beheren** > **Alle eBooks**.
2. Kies in het deelvenster met de lijst met boeken het boek dat u wilt toewijzen en kies vervolgens '**...**' > **Groepen toewijzen**.
3. Kies in het deelvenster <*boeknaam*> - **Toegewezen groepen** achtereenvolgens **Beheren** > **Toegewezen groepen**.
4. Kies **Groepen toewijzen** en kies in het deelvenster **Groepen selecteren** de Azure AD-gebruikersgroepen waaraan u het boek wilt toewijzen. Apparaatgroepen worden momenteel niet ondersteund.
Kies een toewijzingsactie: **Beschikbaar** of **Vereist**. 
5. Als u klaar bent, kiest u **Opslaan**.

## <a name="next-steps"></a>Volgende stappen

Zie [How to monitor apps](apps-monitor.md) (Apps controleren) voor meer informatie over het controleren van boektoewijzingen.






