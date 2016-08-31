---
title: iOS- en OS X-installatie | Azure RMS
description: "iOS- en OS X-toepassingen kunnen gebruikmaken van de RMS SDK 4.2 voor geïntegreerde gegevensbeveiliging in hun toepassingen met behulp van de AAD RM."
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: b31e5b72-e65e-450a-b1b8-d46e81e9fb34
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 024a29d7c7db2e4c0578a95c93e22f8e7a5b173e
ms.openlocfilehash: 65c5b290278405152d0377a686886ff5be14b52b


---

# iOS- en OS X-installatie

iOS- en OS X-toepassingen kunnen de Microsoft Rights Management SDK 4.2 gebruiken om geïntegreerde informatiebeveiliging in de toepassing in te schakelen met behulp van de Azure Rights Management (Azure RMS).

Dit onderwerp leidt u door het instellen van uw omgeving voor het maken van uw eigen nieuwe apps.

**Opmerking** Deze SDK biedt geen ondersteuning voor de iPod Touch.


-   [Vereisten](#prerequisites)
-   [Optioneel](#optional)
-   [Uw ontwikkelingsomgeving configureren](#configuring-your-development-environment)
-   [Zie ook](#see-also)

## Vereisten

We bevelen de volgende software aan voor uw ontwikkelsysteem:

-   OS X is vereist voor alle iOS-ontwikkeling.
-   Xcode versie 6.0 en hoger

    Xcode is beschikbaar via de [Mac App Store](https://developer.apple.com/technologies/mac/).

-   Het MS RMS SDK 4.2-pakket voor iOS en OS X. Zie voor meer informatie [Aan de slag](get-started.md).

    Deze SDK kan worden gebruikt voor het ontwikkelen voor iOS 7.0 en OS X 10.8 en hoger.

-   Verificatiebibliotheek: U kunt het beste de [Azure AD Authentication Library (ADAL)](https://msdn.microsoft.com/library/jj573266.aspx) gebruiken. Andere verificatiebibliotheken die ondersteuning bieden voor OAuth 2.0, kunnen echter ook worden gebruikt.

    Zie [ADAL voor iOS](https://github.com/MSOpenTech/azure-activedirectory-library-for-ios) of [ADAL voor OS X](https://github.com/MSOpenTech/azure-activedirectory-library-for-ios/tree/OSXUniversal) voor meer informatie

Lees het onderwerp [Wat is er nieuw?](release-notes.md) voor informatie over API-updates, opmerkingen bij de release en veelgestelde vragen (FAQ).

## Optioneel

Onze UI-bibliotheek biedt een herbruikbare UI voor gebruiks- en beveiligingsbewerkingen voor ontwikkelaars die geen eigen aangepaste UI willen maken: [UI-bibliotheek en voorbeeldapp voor iOS](https://github.com/AzureAD/rms-sdk-ui-for-ios).

## Uw ontwikkelingsomgeving configureren

-   Als u een nieuw project wilt maken, klikt u in het menu **Bestand** op **Nieuw** en vervolgens op **Project**.
-   Selecteer **Enkelvoudige weergave van toepassing**.

    ![Een nieuw project maken](../media/iOS-Project.png)

-   Voer een naam en id in voor het nieuwe project.

    ![Uw project een naam geven](../media/iOS-project-options.png)

-   Klik op **Volgende** en selecteer een locatie voor uw project.
-   Als u het **MSRightsManagement**-framework wilt toevoegen aan uw iOS-frameworks, sleept u de map .framework uit de SDK-installatiemap naar het gedeelte **Frameworks** van uw **Projectnavigator**.

    ![Locatie instellen](../media/ios-add-dependencies-01a.png)

-   Selecteer het keuzerondje **Groepen maken voor alle toegevoegde mappen** en schakel het selectievakje bij **Items kopiëren naar de map van de bestemmingsgroep (indien nodig)** uit.

    Met deze actie wordt de verwijzing naar de SDK-installatiemap behouden in plaats van er een kopie van te maken.

    ![Verwijzing naar de SDK-installatiemap instellen](../media/iOS-create-groups.png)

-   Als u de MS RMS SDK 4.2 wilt toevoegen aan het resourcepakket, versleept u het bestand MSRightsManagementResources.bundle uit de map MSRightsManagement.framework/Resources naar het gedeelte **Frameworks** van de projectnavigator.

    ![Resourcepakket toevoegen](../media/iOS-add-resource-bundle-02a.png)

-   Net als bij het kopiëren van het framework selecteert u het keuzerondje **Groepen maken voor alle toegevoegde mappen** en schakelt u het selectievakje bij **Items kopiëren naar de map van de bestemmingsgroep (indien nodig)** uit.
-   De SDK is afhankelijk van andere frameworks, met inbegrip van: **CoreData**, **MessageUI**, **SystemConfiguration**, **Libresolv** en **Security**. Als u deze frameworks wilt toevoegen, gaat u naar het gedeelte **Gekoppelde frameworks en bibliotheken** van het deelvenster **Samenvatting** van het doel. Vouw het gedeelte uit om de frameworks toe te voegen.

    De frameworks **UIKit** en **Foundation** zijn vereist en over het algemeen standaard aanwezig.

    ![Resources toevoegen](../media/iOS-add-libraries.png)

-   Voeg de markering **-ObjC** toe aan **Overige Linker-markeringen** in de gewenste **Buildinstellingen**.

    ![Buildinstellingen toevoegen](../media/iOS-linker-flags.png)

-   Uw **projectnavigator** zou er nu moeten uitzien als deze structuur.

    ![Project controleren](../media/iOS-verify-setup-01a.png)

-   U bent er nu klaar voor om uw eigen nieuwe iOS-/OS X-apps te maken.

### Zie ook

* [Aan de slag](get-started.md)

* [Wat is er nieuw?](release-notes.md)

* [Termen en begrippen voor ontwikkelaars](core-concepts.md)

* [iOS-/ OS X API-verwijzing](/rights-management/sdk/4.2/api/ios/ios)

 

 






<!--HONumber=Aug16_HO4-->


