---
title: iOS-/iPadOS-apps beheren die zijn gekocht via het Volume Purchase Program
titleSuffix: Microsoft Intune
description: Meer informatie over hoe u boeken kunt synchroniseren die u via het volumeaankoopprogramma in de iOS Store hebt gekocht, hoe u deze boeken kunt beheren en hoe u het gebruik ervan kunt bijhouden.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f5617074-2384-4812-b913-dc94f64c0818
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f7c2bd0603961b9d618b3f743ecb323fb7fc9823
ms.sourcegitcommit: ecaff388038fb800f2e646f8efcf8f3b1e2fd1b1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2020
ms.locfileid: "77437865"
---
# <a name="how-to-manage-iosipados-ebooks-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>iOS-/iPadOS-apps beheren die u via een volume-aankoopprogramma hebt aangeschaft met Microsoft Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Via het Apple Volume Purchase Program (VPP) kunt u meerdere licenties voor een boek kopen dat u wilt distribueren naar gebruikers in uw bedrijf. U kunt boeken distribueren via de stores voor bedrijven of het onderwijs.

U kunt Microsoft Intune gebruiken om de boeken die u via dit programma hebt gekocht, te synchroniseren, beheren en toe te wijzen. U kunt licentiegegevens uit de store importeren en bijhouden hoeveel van de licenties u hebt gebruikt.

De procedures voor het beheren van boeken zijn vergelijkbaar met die voor het [beheren van VPP-apps](../vpp-apps-ios.md).

## <a name="manage-volume-purchased-books-for-ios-devices"></a>Boeken voor iOS-apparaten beheren die zijn gekocht via het Volum Purchase Program
U koopt meerdere licenties voor iOS-/iPadOS-boeken via het [Apple Volume Purchase Program voor bedrijven](https://www.apple.com/business/vpp/) of het [Apple Volume Purchase Program voor onderwijs](https://volume.itunes.apple.com/us/store). Hiervoor moet u een Apple VPP-account via de website van Apple instellen en het Apple VPP-token uploaden naar Intune.  U kunt uw gegevens over volume-aankopen vervolgens synchroniseren met Intune en het gebruik bijhouden van de boeken die u via het Volume Purchase Program hebt gekocht.

## <a name="before-you-start"></a>Voordat u begint
Voordat u begint, moet u een VPP-token van Apple verkrijgen en dit uploaden naar uw Intune-account. Aanvullend:

* Als u eerder een VPP-token hebt gebruikt voor een ander product, moet u een nieuw token voor gebruik met Intune genereren.
* Elke token is één jaar geldig.
* Standaard wordt Intune twee keer per dag gesynchroniseerd met de Apple VPP-service. U kunt op elk gewenst moment een handmatige synchronisatie starten.
* Nadat u het VPP-token hebt geïmporteerd in Intune, kunt u hetzelfde token niet in een andere oplossing voor apparaatbeheer importeren. Dit kan leiden tot verlies van licentietoewijzngen en gebruikersrecords.
* Voordat u begint met het gebruik van iOS-/iPadOS-boeken met Intune, verwijdert u eventuele bestaande VPP-gebruikersaccounts die zijn gemaakt met andere MDM-leveranciers (Mobile Device Management). Uit veiligheidsoverwegingen worden deze gebruikersaccounts niet met Intune gesynchroniseerd. Er worden alleen gegevens uit de Apple VPP-service gesynchroniseerd die zijn gemaakt met Intune.
* Wanneer u een boek aan een apparaat toewijst, moet op dat apparaat de ingebouwde app iBooks geïnstalleerd zijn. Als dat niet het geval is, moet de gebruiker de app opnieuw installeren om het boek te kunnen lezen. U kunt Intune momenteel niet gebruiken voor het herstellen van verwijderde ingebouwde apps.
* U kunt alleen boeken op de site van het Apple Volume Purchase Program toewijzen. U kunt niet uploaden en vervolgens de boeken toewijzen die u intern hebt gemaakt.
* U kunt boeken momenteel niet op dezelfde manier toewijzen aan eindgebruikerscategorieën als apps.
* U kunt een licentie niet opnieuw claimen zodra het boek is toegewezen.
* Wanneer een nieuwe gebruiker met een in aanmerking komend apparaat een VPP-boek wil installeren, moet deze zich eerst aanmelden voor het Apple Volume Purchase Program. U kunt ook licenties toewijzen aan beveiligingsgroepen met beheerde Apple-id's. Als u dit doet, worden gebruikers niet naar hun Apple-id gevraagd wanneer een boek wordt geïnstalleerd.
* Apparaten moeten worden ingeschreven met gebruikersaffiniteit omdat e-books alleen kunnen worden toegewezen aan gebruikersgroepen.   


## <a name="to-get-and-upload-an-apple-vpp-token"></a>Een Apple VPP-token verkrijgen en uploaden

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Tenantbeheer** > **Connectors en tokens** > **Apple VPP-tokens**.
3. Klik in het deelvenster met de lijst met VPP-tokens op **Maken**.
5. Geef in het deelvenster **Nieuw VPP-token** de volgende gegevens op:
    - **VPP-tokenbestand**: zorg dat u zich hebt aangemeld voor het VPP-programma voor bedrijven of voor het VPP-programma voor onderwijs. Download vervolgens het Apple VPP-token voor uw account en selecteer het hier.
    - **Apple ID**: voer de Apple ID in van het account dat aan het VPP is gekoppeld.
    - **Type VPP-account**: u hebt de keuze uit **Bedrijven** of **Onderwijs**.
5. Wanneer u klaar bent, klikt u op **Maken**.

Het token wordt weergegeven in het deelvenster met de lijst met tokens.


U kunt de gegevens waarover Apple beschikt, op elk gewenst moment synchroniseren met Intune door **Nu synchroniseren** te kiezen.

## <a name="to-assign-a-volume-purchased-app"></a>Een app toewijzen die is gekocht via het volume-aankoopprogramma

1. Selecteer **Apps** > **eBooks** > **Alle eBooks**.
2. Kies in het deelvenster met de lijst met boeken het boek dat u wilt toewijzen en kies vervolgens ' **...** ' > **Groepen toewijzen**.
3. Kies in het deelvenster <*boeknaam*> - **Toegewezen groepen** achtereenvolgens **Beheren** > **Toegewezen groepen**.
4. Kies **Groepen toewijzen** en kies in het deelvenster **Groepen selecteren** de Azure AD-gebruikersgroepen waaraan u het boek wilt toewijzen. Apparaatgroepen worden momenteel niet ondersteund.
Kies een toewijzingsactie: **Beschikbaar** of **Vereist**. 
5. Als u klaar bent, kiest u **Opslaan**.

## <a name="next-steps"></a>Volgende stappen

Zie [How to monitor apps](apps-monitor.md) (Apps controleren) voor meer informatie over het controleren van boektoewijzingen.






