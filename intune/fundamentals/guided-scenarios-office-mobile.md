---
title: 'Begeleid scenario: veilige mobiele apps voor Microsoft Office'
titleSuffix: Microsoft Intune
description: Meer informatie over het begeleide scenario voor het implementeren van veilige mobiele apps voor Microsoft Office vanuit de portal voor Microsoft 365-apparaatbeheer.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bd02e2b7f9582308109d1e6986d7e6a8014e5af7
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72585706"
---
# <a name="guided-scenario---secure-microsoft-office-mobile-apps"></a>Begeleid scenario: veilige mobiele apps voor Microsoft Office 

Als u dit begeleide scenario in de portal voor apparaatbeheer volgt, kunt u basisbeveiliging voor Intune-apps inschakelen op iOS- en Android-apparaten.

Met de app-beveiliging die u inschakelt, worden de volgende acties afgedwongen: 
- Werkbestanden versleutelen.
- Een pincode vereisen voor toegang tot werkbestanden.
- Vereisen dat de pincode opnieuw wordt ingesteld na vijf mislukte pogingen.
- Voorkomen dat er een back-up wordt gemaakt van werkbestanden in back-upservices van iTunes-, iCloud of Android.  
- Vereisen dat werkbestanden alleen worden opgeslagen in OneDrive of SharePoint.
- Voorkomen dat beveiligde apps werkbestanden laden op gekraakte of geroote apparaten.
- Toegang tot werkbestanden blokkeren als het apparaat gedurende 720 minuten offline is.
- Werkbestanden verwijderen als het apparaat gedurende 90 dagen offline is. 

## <a name="background"></a>Achtergrond

Zowel Office Mobile-apps als Microsoft Edge voor mobiel bieden ondersteuning voor het gebruik van dubbele identiteiten. Door een dubbele identiteit te gebruiken, kunnen apps werkbestanden gescheiden van persoonlijke bestanden beheren. 

![Afbeelding van bedrijfsgegevens versus persoonlijke gegevens](./media/guided-scenarios-office-mobile/guided-scenarios-office-mobile-01.png)

U kunt [beveiligingsbeleid voor apps in Intune](~/apps/app-protection-policy.md) gebruiken om u te helpen bij het beveiligen van uw werkbestanden op apparaten die zijn geregistreerd in Intune. U kunt ook beveiligingsbeleid voor apps gebruiken op apparaten die in het bezit zijn van werknemers en die niet zijn geregistreerd voor beheer in Intune. In dit geval moet u, zelfs als uw organisatie het apparaat niet beheert, er nog steeds voor zorgen dat uw werkbestanden en resources zijn beveiligd.

U kunt beveiligingsbeleid voor apps gebruiken om te voorkomen dat gebruikers werkbestanden opslaan op niet-beveiligde locaties. U kunt ook gegevensverplaatsing beperken naar andere apps die niet zijn beveiligd met beveiligingsbeleid voor apps. Beveiligingsbeleidsinstellingen voor apps bevatten:
- Beleid voor gegevensverplaatsing, zoals Opslaan als voorkomen en knippen, kopiëren en plakken beperken.
- Instellingen voor toegangsbeleid zoals Eenvoudige pincode vereisen voor toegang en Beheerde apps blokkeren op gekraakte of geroote apparaten.

Met op apps gebaseerde voorwaardelijke toegang en beheer van client-apps voegt u een beveiligingslaag toe door ervoor te zorgen dat alleen client-apps die app-beveiligingsbeleid van Intune ondersteunen, toegang hebben tot Exchange Online en andere Office 365-services.

U kunt de ingebouwde e-mailapps voor iOS en Android blokkeren wanneer u alleen toegang van de Microsoft Outlook-app tot Exchange Online toestaat. Bovendien kunt u de toegang tot SharePoint Online blokkeren voor apps waarvoor geen app-beveiligingsbeleid in Intune is ingesteld.

In dit voorbeeld heeft de beheerder beveiligingsbeleid voor de Outlook-app toegepast, gevolgd door een regel voor voorwaardelijke toegang waarmee de Outlook-app wordt toegevoegd aan een lijst met goedgekeurde apps die kunnen worden gebruikt bij het openen van bedrijfs-e-mail.

![Processtroom voorwaardelijke toegang voor Outlook-app](./media/guided-scenarios-office-mobile/guided-scenarios-office-mobile-02.png)

## <a name="prerequisites"></a>Vereisten

U hebt de volgende machtigingen van een Intune-beheerder nodig:

   - Machtigingen voor het lezen, maken, verwijderen en toewijzen van beheerde apps
   - Machtigingen voor het lezen, maken en toewijzen van beleidssets
   - Machtigingen voor het lezen van organisaties

## <a name="step-1---introduction"></a>Stap 1: inleiding

Door het begeleide scenario **Intune-app-beveiliging** te volgen kunt u voorkomen dat gegevens buiten uw organisatie worden gedeeld of gelekt. 

Toegewezen iOS- en Android-gebruikers moeten elke keer dat ze een Office-app openen een pincode invoeren. Na 5 mislukte pincodepogingen moeten gebruikers hun pincode opnieuw instellen. Als er al een pincode voor het apparaat vereist is, heeft dit geen gevolgen voor de gebruikers.

### <a name="what-you-will-need-to-continue"></a>Wat u nodig hebt om verder te gaan

U krijgt vragen over de apps die uw gebruikers nodig hebben en wat er nodig is om er toegang tot te krijgen. Zorg ervoor dat u de volgende informatie bij de hand hebt:
- Lijst met Office-apps die zijn goedgekeurd voor gebruik binnen het bedrijf.
- Eventuele pincodevereisten voor het starten van goedgekeurde apps op niet-beheerde apparaten.

## <a name="step-2---basics"></a>Stap 2: basisinformatie

In deze stap moet u een **voorvoegsel** en **beschrijving** voor het nieuwe beveiligingsbeleid voor uw apps invoeren. Wanneer u het **voorvoegsel toevoegt**, worden de gegevens bijgewerkt die betrekking hebben op de resources die met behulp van het begeleide scenario worden gemaakt. Met deze gegevens kunt u uw beleid later gemakkelijk vinden als u de toewijzingen en configuratie wilt wijzigen. 

> [!TIP]
> U kunt een notitie maken van de resources die worden gemaakt, zodat u deze later kunt raadplegen.

## <a name="step-3---apps"></a>Stap 3: apps

Om u op weg te helpen, worden in dit begeleide scenario de volgende mobiele apps die moeten worden beveiligd op iOS- en Android-apparaten, vooraf geselecteerd:
- Microsoft Excel 
- Microsoft Word 
- Microsoft Teams 
- Microsoft Edge 
- Microsoft PowerPoint 
- Microsoft Outlook 
- Microsoft OneDrive 

In dit begeleide scenario worden deze apps ook geconfigureerd om er webkoppelingen mee te openen in Microsoft Edge, zodat u zeker weet dat werksites altijd in een beveiligde browser worden geopend.

Wijzig de lijst met door beleid beheerde apps die u wilt beveiligen. Voeg apps toe aan deze lijst of verwijder ze eruit. 

Wanneer u de apps hebt geselecteerd, klikt u op **Volgende**.

## <a name="step-4---configuration"></a>Stap 4: configuratie

In deze stap moet u de vereisten configureren die nodig zijn voor het verkrijgen van toegang tot bedrijfsbestanden en e-mails, en het delen ervan in deze apps. Standaard kunnen gebruikers gegevens opslaan in de OneDrive- en SharePoint-accounts van uw organisatie.

| Instelling | Beschrijving | Standaardwaarde |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|
| Pincodetype | Numerieke pincodes bestaan geheel uit getallen. Wachtwoordcodes bestaan uit alfanumerieke tekens en speciale tekens.  Als u op iOS/iPadOS het type wachtwoordcode wilt configureren, moet de app beschikken over de Intune-SDK, versie 7.1.12 of hoger. Bij het type Numeriek is er geen versiebeperking voor de Intune-SDK. | Numeriek |
| Minimale lengte pincode selecteren | geef het minimale aantal cijfers op waaruit een pincode moet bestaan. | 6 |
| Toegangsvereisten opnieuw controleren na (minuten van inactiviteit) | Als de door beleid beheerde app langer dan het opgegeven aantal minuten inactief is, vraagt de app om de toegangsvereisten (zoals de pincode, instellingen voor voorwaardelijk starten) die opnieuw moeten worden gecontroleerd nadat de app is gestart. | 30 |
| Organisatiegegevens afdrukken | Als de app is geblokkeerd, kunnen er geen beveiligde gegevens mee worden afgedrukt. | Blokkeren |
| Door beleid beheerde app-koppelingen openen in niet-beheerde browsers | Indien geblokkeerd, moeten de door beleid beheerde app-koppelingen worden geopend in een beheerde browser. | Blokkeren |
| Gegevens naar niet-beheerde apps kopiëren | Indien geblokkeerd, blijven beheerde gegevens in beheerde apps aanwezig. | Toestaan |

## <a name="step-5---assignments"></a>Stap 5: toewijzingen

In deze stap kunt u de gebruikersgroepen kiezen die u wilt gebruiken, zodat deze toegang hebben tot uw bedrijfsgegevens. App-beveiliging wordt toegewezen aan gebruikers en niet aan apparaten, zodat uw bedrijfsgegevens veilig zijn, ongeacht het apparaat dat wordt gebruikt en de inschrijvingsstatus ervan.

Gebruikers waaraan geen app-beveiligingsbeleid en instellingen voor voorwaardelijke toegang zijn toegewezen, kunnen gegevens vanuit hun bedrijfsprofiel opslaan in persoonlijke apps en in niet-beheerde lokale opslag op hun mobiele apparaten. Ze kunnen met persoonlijke apps ook verbinding maken met zakelijke gegevensservices, zoals Microsoft Exchange.

## <a name="step-6---review--create"></a>Stap 6: beoordelen en maken

In de laatste stap kunt u een samenvatting beoordelen van de instellingen die u hebt geconfigureerd. Nadat u uw keuzes hebt beoordeeld, klikt u op **Maken** om het begeleide scenario te voltooien. Zodra het begeleide scenario is voltooid, wordt er een tabel met resources weergegeven. U kunt deze resources later bewerken, maar bij het verlaten van de samenvattingsweergave wordt de tabel niet opgeslagen.

> [!IMPORTANT]
> Als het begeleide scenario is voltooid, wordt een samenvatting weergegeven. U kunt de resources in de samenvatting later wijzigen, maar de tabel waarin deze resources worden weergegeven, wordt niet opgeslagen.
## <a name="next-steps"></a>Volgende stappen

- Verbeter de beveiliging van werkbestanden door aan gebruikers een op apps gebaseerd beleid voor voorwaardelijke toegang toe te wijzen, zodat cloudservices worden beveiligd tegen het verzenden van werkbestanden naar niet-beveiligde apps. Zie [Op apps gebaseerd beleid voor voorwaardelijke toegang instellen met Intune](~/protect/app-based-conditional-access-intune-create.md) voor meer informatie.

