---
title: Windows Phone-instelling | Azure RMS
description: "Windows Phone-toepassingen kunnen gebruikmaken van de Microsoft Rights Management SDK 4.2 om geïntegreerde informatiebeveiliging in de toepassing in te schakelen."
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: e25a446e-b977-4736-9c65-7711171fb0e1
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 90552435666b8f25c893fcffe8c8cf3355a5942d
ms.openlocfilehash: 136d6e9d0c45a9779f87e32eed8288fe8ee3a622


---

# Windows Phone-instelling


Windows Phone-toepassingen kunnen gebruikmaken van de Microsoft Rights Management SDK 4.2 om geïntegreerde informatiebeveiliging in de toepassing in te schakelen met behulp van Azure Active Directory Rights Management (AAD RM).

Dit onderwerp leidt u door het instellen van een omgeving voor het maken van uw eigen nieuwe apps.

-   [Vereisten](#prerequisites)
-   [Uw ontwikkelingsomgeving configureren](#configuring_your_development_environment)
-   [Zie ook](#see_also)

## Vereisten


Op uw ontwikkelingssysteem moet de volgende software aanwezig zijn:

-   Het besturingssysteem [Windows 8.1](http://windows.microsoft.com/en-US/windows-8/meet).
-   [De Windows Phone 8.1-ontwikkelingsprogramma's (SDK)](http://dev.windowsphone.com/en-us/downloadsdk)
-   Microsoft [Visual Studio 2012](http://www.microsoft.com/visualstudio/eng/products/visual-studio-overview) of hoger, of Visual Studio Express 2012, dat wordt meegeleverd met de Windows Phone SDK 8.0/8.1
-   Het MS RMS SDK 4.2-pakket voor Windows Phone Zie [Aan de slag](get-started.md) voor meer informatie.
-   Verificatiebibliotheek: u kunt het beste de [Azure AD-verificatiebibliotheek](https://msdn.microsoft.com/en-us/library/jj573266.aspx) en andere verificatiebibliotheken gebruiken.

Lees het onderwerp [Wat is er nieuw?](release-notes.md) voor meer informatie over API-updates, informatie over apparaten en omgeving, release-opmerkingen en veelgestelde vragen.

Lees de informatie in de handleiding [Windows Phone-ontwikkeling](https://msdn.microsoft.com/en-us/library/windowsphone/develop/ff402535.aspx) in het Windows Phone Dev Center.

## Uw ontwikkelingsomgeving configureren


-   Open *Visual Studio*.
-   Klik op **Bestand**. Klik in het menu **Bestand** op **Nieuw** en vervolgens op **Project**.
-   Selecteer in het dialoogvenster **Nieuw project** de optie **Visual C\#**, selecteer **Lege app (Windows Phone)** en klik vervolgens op **OK**.

    ![Een nieuw project maken](../media/wpsetup-newproj.png)

-   Klik in Solution Explorer met de rechtermuisknop op uw project en selecteer vervolgens **Verwijzing toevoegen** om het dialoogvenster **Verwijzing toevoegen** te openen.

    ![Verwijzing toevoegen](../media/wpsetup-addref.png)

-   Klik in de linkerbenedenhoek van het dialoogvenster **Verwijzing toevoegen** op **Bladeren** en selecteer het bestand *Microsoft.RightsManagment.dll*. Dit bevindt zich in de map waarin u het pakket hebt uitgepakt.
-   **Beheerde apps**: voor het bouwen van een beheerde app moet u deze verwijzing toevoegen. Selecteer **Windows 8.1**-&gt;**Extensies** en schakel het selectievakje in voor **Windows Visual C++ Runtime-pakket voor Windows**.

    ![Uitbreidingen toevoegen](../media/wpsetup-refmngr.png)

-   **Mogelijkheden toevoegen**: de toepassing heeft de mogelijkheid 'Internet (client en server)' nodig voor het gebruik van de SDK. Om deze mogelijkheid toe te voegen aan uw app, opent u het bestand *Package.appxmanifest* in het project en navigeert u naar het tabblad **Mogelijkheden** om dit toe te voegen.

U bent er nu klaar voor om uw eigen nieuwe Windows Phone-apps te maken.

### Zie ook

[Aan de slag](get-started.md)

[Wat is er nieuw?](release-notes.md)

[Belangrijkste concepten](core-concepts.md)

[Windows Phone-ontwikkeling](https://msdn.microsoft.com/en-us/library/windowsphone/develop/ff402535.aspx)

[Windows API-referentiemateriaal](/rights-management/sdk/4.2/api/winrt/Microsoft.RightsManagement)

[Visual Studio 2012](http://www.microsoft.com/visualstudio/eng/products/visual-studio-overview)

[Windows Phone SDK](http://dev.windowsphone.com/en-us/downloadsdk)

 

 






<!--HONumber=Jun16_HO4-->


