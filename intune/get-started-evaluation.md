---
title: Wat kan Microsoft Intune voor mijn bedrijf doen?
titleSuffix: ''
description: Algemene bedrijfsproblemen die Microsoft Intune u helpt op te lossen.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6bfab644-c1e2-4154-a254-e95b9a1d75f2
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1df3676b4259ac84cf1ae5f0ce76ee300aa92f85
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55839138"
---
# <a name="what-can-intune-do-for-my-company"></a>Wat kan Intune voor mijn bedrijf doen?
Microsoft Intune is een cloudgebaseerde service voor het beheer van bedrijfsmobiliteit (Enterprise Mobility Management, EMM) die uw werknemers in staat stelt om productief te zijn terwijl uw zakelijke gegevens veilig blijven.

Met Intune kunt u het volgende doen:

- De mobiele apparaten beheren die door uw werknemers worden gebruikt voor toegang tot bedrijfsgegevens.
- De mobiele apps beheren waarvan uw werknemers gebruikmaken.
- Gegevens van uw bedrijf beschermen door te bepalen hoe uw werknemers toegang hebben tot de gegevens en deze delen.
- Garanderen dat apparaten en apps compatibel zijn met de beveiligingsvereisten van het bedrijf.

## <a name="common-business-problems-that-intune-helps-solve"></a>Algemene bedrijfsproblemen die Intune u helpt op te lossen

* [Uw on-premises-e-mail en -gegevens beveiligen, zodat deze veilig kunnen worden geopend vanaf mobiele apparaten](common-scenarios.md#protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Uw Office 365-e-mail en -gegevens beveiligen, zodat deze veilig kunnen worden geopend vanaf mobiele apparaten](common-scenarios.md#protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Bedrijfstelefoons ter hand stellen aan uw medewerkers](common-scenarios.md#issue-corporate-owned-phones-to-your-employees)
* [Een Bring Your Own Device-programma (BYOD) aan alle werknemers aanbieden](common-scenarios.md#offer-a-bring-your-own-device-program-to-all-employees)
* [Uw werknemers in staat stellen Office 365 veilig te gebruiken vanuit een niet-beheerde openbare kiosk](common-scenarios.md#enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk)
* [Tablets voor beperkt gebruik verstrekken aan taakgerichte werknemers](common-scenarios.md#issue-limited-use-shared-tablets-to-your-employees)

## <a name="quickstarts"></a>Snelstartgidsen

We begrijpen dat het moeilijk kan zijn om te starten met het beheren van mobiele apparaten. U moet immers veel verschillende beslissingen namens uw bedrijf nemen. Aan de hand van de volgende snelstartinstructies kunt u aan de slag met Intune en in een zo kort mogelijke tijd een aantal algemene taken voltooien.

U kunt de beoogde volgorde van de **Snelstartgidsen** volgen aan de hand van de inhoudsopgave aan de linkerkant van de pagina.

- [Intune gratis proberen](free-trial-sign-up.md): maak een gratis abonnement om Intune in een testomgeving te proberen.    
- [Een gebruiker maken](quickstart-create-user.md): voeg een gebruiker aan Intune toe om deze toe te staan zakelijke resources te openen op mobiele apparaten.
- [Een groep maken](quickstart-create-group.md): deel gebruikers in groepen in om het beleid en de apps waartoe ze toegang hebben gemakkelijker te beheren.
- [Automatische inschrijving instellen](quickstart-setup-auto-enrollment.md): stel Microsoft Intune zo in dat apparaten automatisch worden ingeschreven wanneer bepaalde gebruikers zich aanmelden bij Windows 10-apparaten.
- [Uw apparaat registreren](quickstart-enroll-windows-device.md): neem de rol aan van Intune-gebruiker en registreer uw apparaat in Microsoft Intune. Ga dan terug naar Intune en bevestig het geregistreerde apparaat.
- [Een nalevingsbeleid voor apparaten maken](quickstart-set-password-length-android.md): maak een apparaatnalevingsbeleid en wijs een groep aan het beleid toe.
- [Meldingen sturen naar niet-compatibele apparaten](quickstart-send-notification.md): stuur een e-mailmelding naar uw personeelsleden die niet-compatibele apparaten hebben door een nalevingsbeleid te maken en toe te wijzen.
- [Een app toevoegen en toewijzen](quickstart-add-assign-app.md): u kunt een client-app toevoegen en toewijzen aan het personeel van uw bedrijf.
- [Een beveiligingsbeleid voor apps maken en toewijzen](quickstart-create-assign-app-policy.md): maak een app-beveiligingsbeleid en wijs dit aan een client-app op een apparaat van een eindgebruiker toe.
- [Een aangepaste rol](quickstart-create-custom-role.md): maak en wijs een aangepaste rol toe met specifieke machtigingen voor de afdeling Beveiligingsactiviteiten. 
- [Een e-mail-apparaatprofiel voor iOS maken](quickstart-email-profile.md): maak een e-mailapparaatprofiel voor iOS-apparaten.

## <a name="prerequisites"></a>Vereisten

U moet een Intune-beheerdersaccount en een tenantaccount activeren voordat u begint. Maak een gratis abonnement om [Intune gratis te proberen](free-trial-sign-up.md) in een testomgeving. Huidige abonnees kunnen deze activiteiten ook voltooien in de live-tenant. In deze artikelen Aan de slag wordt ervan uitgegaan dat u met testapparaten werkt.

U moet er ook voor zorgen dat u de globale beheerder voor uw organisatie bent om alle taken in de 'Aan de slag'-taken te kunnen uitvoeren.

## <a name="intune-architecture"></a>Intune-architectuur

Intune is het onderdeel van Microsoft Enterprise Mobility + Security (EMS) dat mobiele apparaten en apps beheert. De oplossing is nauw geïntegreerd met andere EMS-onderdelen, zoals Azure Active Directory (Azure AD), voor identiteits- en toegangsbeheer en met Azure Information Protection voor gegevensbeveiliging. Als u de oplossing in combinatie met Office 365 gebruikt, kunt u uw medewerkers in staat stellen om productief te zijn op al hun apparaten terwijl de gegevens van uw organisatie beschermd blijven.

![Architectuurdiagram op hoog niveau voor Microsoft Intune](/intune/media/intunearchitecture.svg)

## <a name="next-steps"></a>Volgende stappen

[Aan de slag met Azure](get-started-azure.md) - Begrijp de anatomie van de Azure-portal en leer hoe u veranderingen kunt aanbrengen op de pagina die u ziet.

## <a name="learn-more"></a>Meer informatie

* [Wat is Intune?](introduction-intune.md)
* [Wat is Azure Portal?](what-is-intune.md)
* [Levenscycli van apparaten en apps](introduction-device-app-lifecycles.md)
