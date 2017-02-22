---
title: iOS-apps beheren die zijn gekocht via het volume-aankoopprogramma | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp vindt u informatie over hoe u de apps kunt synchroniseren die u via het volume-aankoopprogramma in de iOS Store hebt gekocht, hoe u deze apps kunt beheren en hoe u het gebruik ervan kunt bijhouden.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87250baede6c86e7ac5c402e79026908e712f48c
ms.openlocfilehash: 809fe8d8eea7e472d80f6ee22e26c1f376e870eb

---

# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program"></a>iOS-apps beheren die u hebt gekocht via een volume-aankoopprogramma


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

De iOS App Store biedt u de mogelijkheid meerdere licenties te kopen voor een app die u wilt uitvoeren binnen uw bedrijf. Zodoende kunt u de administratieve overhead voor het bijhouden reduceren als u meerdere exemplaren van apps hebt aangeschaft.

Met Microsoft Intune kunt u nu apps beheren die u via een dergelijk programma hebt aangeschaft, door de licentiegegevens uit de App Store te importeren en bij te houden hoeveel licenties u hebt gebruikt. Zo wordt voorkomen dat u meer exemplaren van de app installeert dan u hebt aangeschaft.

> [!Important]
> Op dit moment wijst Intune iOS VPP-applicenties (Volume Purchase Program voor bedrijven) toe aan gebruikers en niet aan apparaten. Als gevolg hiervan moeten gebruikers het wachtwoord van hun Apple-id invoeren om de app te installeren.

## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Volume-purchased apps voor iOS-apparaten beheren
U koopt meerdere licenties voor iOS-apps via het [Apple-VPP voor bedrijven (Volume Purchase Program)](http://www.apple.com/business/vpp/) of het [Apple VPP voor onderwijs (Volume Purchase Program)](http://volume.itunes.apple.com/us/store). Hiervoor moet u een Apple VPP-account via de website van Apple instellen en het Apple VPP-token uploaden naar Intune.  U kunt uw gegevens over volume-aankopen vervolgens synchroniseren met Intune en het gebruik bijhouden van uw via het volume-aankoopprogramma gekochte apps.

## <a name="before-you-start"></a>Voordat u begint
Voordat u begint, moet u een VPP-token van Apple verkrijgen en dit uploaden naar uw Intune-account. Bovendien moet u het volgende weten:

* U kunt meerdere VPP-tokens aan uw Intune-account koppelen.
* Als u eerder een VPP-token hebt gebruikt voor een ander product, moet u een nieuw token voor gebruik met Intune genereren.
* Elke token is één jaar geldig.
* Standaard wordt Intune twee keer per dag gesynchroniseerd met de Apple VPP-service. U kunt op elk gewenst moment een handmatige synchronisatie starten.
* Nadat u het VPP-token hebt geïmporteerd in Intune, kunt u hetzelfde token niet in een andere oplossing voor apparaatbeheer importeren. Dit kan leiden tot verlies van licentietoewijzngen en gebruikersrecords.
* Voordat u begint met het gebruik van iOS VPP met Intune, verwijdert u eventuele bestaande VPP-gebruikersaccounts die zijn gemaakt met andere MDM-leveranciers (Mobile Device Management). Uit veiligheidsoogpunt worden deze gebruikersaccounts niet met Intune gesynchroniseerd. Intune synchroniseert alleen gegevens uit de Apple VPP-service, die zijn gemaakt door Intune.
* U kunt geen iOS VPP-apps implementeren op apparaten die zijn ingeschreven met Device Enrollment Protocol (DEP).

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Een Apple VPP-token verkrijgen en uploaden

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Apps beheren** op de blade **Intune**.
1.  Kies **Instellen** > **VPP-tokens voor iOS** in de workload **Apps beheren**.
2.  Klik op de blade met de lijst met VPP-tokens en klik op **Toevoegen**.
3.  Geef op de blade Nieuw VPP-token de volgende gegevens op:
    - **VPP-tokenbestand**: meld u aan voor het VPP-programma voor bedrijven of voor het VPP-programma voor onderwijs als u dit nog niet hebt gedaan. Nadat u bent aangemeld, downloadt u het Apple VPP-token voor uw account en selecteert u dit hier.
    - **Apple ID**: voer de Apple ID in van het account dat aan het VPP is gekoppeld.
    - **Type VPP-account**: u hebt de keuze uit **Bedrijven** of **Onderwijs**.
4. Klik wanneer u klaar bent op **Uploaden**.

Het token wordt weergegeven op de blade met de lijst met tokens.


U kunt de gegevens waarover Apple beschikt, op elk gewenst moment synchroniseren met Intune door **Nu synchroniseren** te kiezen.

## <a name="to-assign-a-volume-purchased-app"></a>Een app toewijzen die is gekocht via het volume-aankoopprogramma

1. Kies **Beheren** > **Apps met licenties** in de workload **Beheerde apps**.
2. Kies de app die u wilt toewijzen op de blade met de lijst met apps en kies vervolgens **...** > **Groepen toewijzen**.
3. Kies **Beheren** > **Toegewezen groepen** op de blade <*app-naam*> - **Toegewezen groepen**.
4. Kies **Groepen toewijzen** en kies op de blade **Groepen selecteren** de Azure AD-groepen waaraan u de app wilt toewijzen.
U moet de toewijzingsactie instellen op **Vereist**. Beschikbare installaties worden momenteel niet ondersteund.
5. Als u klaar bent, kiest u **Opslaan**.

Zie [How to monitor apps](monitor-apps.md) (Apps controleren) voor meer informatie over het controleren van app-toewijzingen.

## <a name="further-information"></a>Meer informatie

Wanneer u de app als een **vereiste** installatie toewijst, gebruikt elke gebruiker die de app installeert een licentie.

Als u een licentie wilt vrijmaken, moet u de toewijzingsactie wijzigen in **Verwijderen**. De licentie wordt vrijgemaakt nadat de app is verwijderd.

Wanneer een gebruiker met een in aanmerking komend apparaat voor de eerste keer probeert een VPP-app te installeren, wordt deze gevraagd om deel te nemen aan het volume-aankoopprogramma van Apple. Dit moet plaatsvinden voordat de installatie van de app wordt voortgezet.



<!--HONumber=Feb17_HO2-->


