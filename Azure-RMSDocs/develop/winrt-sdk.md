---
title: Windows Store-instelling | Azure RMS
description: "Windows Store-toepassingen kunnen gebruikmaken van de Microsoft Rights Management SDK 4.2 om geïntegreerde informatiebeveiliging in de toepassing in te schakelen."
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 2720aa0e-0d37-469f-be99-678bf95a9c51
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
ms.sourcegitcommit: f7dd88d90357c99c69fe4fdde67c1544595e02f8
ms.openlocfilehash: 0b8e0fb6d872506ac3529bd137286f0e8fa562ee


---

# Windows Store-instelling

Windows Store-toepassingen kunnen gebruikmaken van de Microsoft Rights Management SDK 4.2 om geïntegreerde informatiebeveiliging in de toepassing in te schakelen met behulp van Azure Active Directory Rights Management (AAD RM).

Dit onderwerp leidt u door het instellen van een omgeving voor het maken van uw eigen nieuwe apps.

-   [Vereisten](#prerequisites)
-   [Optioneel](#optional)
-   [Uw ontwikkelomgeving configureren](#configuring-your-development-environment)
-   [Zie ook](#see-also)

## Vereisten


Op uw ontwikkelingssysteem moet de volgende software aanwezig zijn:

-   Het besturingssysteem [Windows 8.1](http://windows.microsoft.com/en-US/windows-8/meet).
-   De [Windows SDK voor Windows 8.1](https://msdn.microsoft.com/windows/desktop/bg162891.aspx)
-   Microsoft [Visual Studio 2012](http://www.microsoft.com/visualstudio/eng/products/visual-studio-overview) of hoger, of Visual Studio Express 2012, dat wordt meegeleverd met de Windows SDK voor Windows 8.0/8.1.
-   Het MS RMS SDK 4.2-pakket voor Windows Store-toepassingen Zie [Aan de slag](get-started.md) voor meer informatie.
-   Verificatiebibliotheek: u kunt het beste de [Azure AD-verificatiebibliotheek](https://msdn.microsoft.com/en-us/library/jj573266.aspx) en andere verificatiebibliotheken gebruiken.

Lees het onderwerp [Wat is er nieuw?](release-notes.md) voor meer informatie over API-updates, informatie over apparaten en omgeving, release-opmerkingen en veelgestelde vragen.

## Optioneel

Onze UI-bibliotheek biedt een herbruikbare UI voor gebruiks- en beveiligingsbewerkingen voor ontwikkelaars die geen eigen aangepaste UI willen maken: [UI-bibliotheek voor Windows Store-apps](https://github.com/AzureAD/rms-sdk-ui-for-windowsstore). We bieden ook een voorbeeldtoepassing van een Windows Store-app: [RMS-voorbeeldtoepassing voor Windows Store](https://github.com/AzureADSamples/rms-samples-for-windowsstore).

## Uw ontwikkelingsomgeving configureren


-   Open Visual Studio.
-   Klik achtereenvolgens op **Bestand**, **Nieuw** en **Project**.
-   Klik in het dialoogvenster **Nieuw project** op **Visual C\#**, selecteer **Lege app (Windows)** en klik vervolgens op **OK**.

    ![Een nieuw project maken](../media/winrtsetup-newproj.png)

-   Klik in **Solution Explorer** met de rechtermuisknop op uw project en selecteer vervolgens **Verwijzing toevoegen** om het dialoogvenster **Verwijzing toevoegen** te openen.

    ![Verwijzing toevoegen](../media/winrtsetup-addref.png)

-   Klik in het dialoogvenster **Verwijzing toevoegen** op **Bladeren** en selecteer het bestand *Microsoft.RightsManagment.dll*. Dit bevindt zich in de map waarin u het SDK-pakket hebt uitgepakt.
-   **Beheerde apps**: voor het bouwen van een beheerde app moet u deze verwijzing toevoegen. Selecteer **Windows 8.1**-&gt;**Extensies** en schakel het selectievakje in voor **Windows Visual C++ Runtime-pakket voor Windows**.

    ![Uitbreidingen toevoegen](../media/winrtsetup-refmngr.png)

-   **Mogelijkheden toevoegen**: de toepassing heeft de mogelijkheid 'Internet (client en server)' nodig voor het gebruik van de SDK. Om deze mogelijkheid toe te voegen aan uw app, opent u het bestand *Package.appxmanifest* in het project en navigeert u naar het tabblad **Mogelijkheden** om dit toe te voegen.

U bent er nu klaar voor om uw eigen nieuwe Windows Store-apps te maken.

### Zie ook

[Aan de slag](get-started.md)

[Wat is er nieuw?](release-notes.md)

[Termen en begrippen voor ontwikkelaars](core-concepts.md)

[Windows 8](http://windows.microsoft.com/en-US/windows-8/meet)

[Visual Studio 2012](http://www.microsoft.com/visualstudio/eng/products/visual-studio-overview)

[Windows API-referentiemateriaal](/rights-management/sdk/4.2/api/winrt/Microsoft.RightsManagement)



<!--HONumber=Jun16_HO4-->


