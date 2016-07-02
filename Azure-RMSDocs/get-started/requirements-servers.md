---
title: Azure RMS-vereisten&#58; lokale servers die Azure Rights Management ondersteunen | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: e7d91f2d-d6a7-4c7e-821f-c94e4be9967d
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed50d87138c428fadfd22cd5b3ef3c7f7e421848
ms.openlocfilehash: 7e718d8178dd7c4b18ea7a19eb3165ee06dc4b36


---


# Azure RMS-vereisten: lokale servers die Azure RMS ondersteunen

*Van toepassing op: Azure Rights Management, Office 365*

De volgende lokale serverproducten worden ondersteund door Azure RMS wanneer u de Azure RMS-connector gebruikt die als communicatie-interface (relais) fungeert tussen de lokale servers en Azure RM. Daarnaast vereist deze configuratie dat u adreslijstsynchronisatie configureert tussen uw Active Directory-forests en Azure Active Directory.

-   **Exchange Server**:

    -   Exchange Server 2016

    -   Exchange Server 2013

    -   Exchange Server 2010

-   **Office SharePoint Server**:

    -   Office SharePoint Server 2016

    -   Office SharePoint Server 2013

    -   Office SharePoint Server 2010

-   **Bestandsservers met Windows Server en File Classification Infrastructure (FCI)**:

    -   Windows Server 2012 R2

    -   Windows Server 2012

    > [!NOTE]
    > Omdat bestandsservers met Windows Server 2008 R2 geen ingebouwde taakactie voor bestandsbeheer hebben om RMS-beveiliging toe te passen, kunt u de RMS-connector gebruiken voor dit scenario. U kunt echter File Classification Infrastructure en Azure RMS op deze besturingssystemen gebruiken als u een taak voor het bestandsbeheer configureert om van een programmabestand of script uit te voeren dat bestanden met Azure RMS kan beveiligen. Bijvoorbeeld een Windows PowerShell-script waarin de [cmdlets voor RMS-beveiliging](https://msdn.microsoft.com/library/azure/mt433195.aspx) worden gebruikt
    > 
    > U kunt deze cmdlets ook gebruiken op servers met latere versies van Windows Server, wat als voordeel heeft dat u met deze cmdlets alle bestandstypen kunt beveiligen. De RMS-connector beveiligt alleen Office-bestanden. Zie [RMS-beveiliging met infrastructuur voor bestandsclassificatie &#40;FCI&#41 voor Windows Server](../rms-client/configure-fci.md) voor instructies.

De RMS-connector wordt ondersteund op Windows Server 2012 R2, Windows Server 2012 en Windows Server 2008 R2.

Zie [De Azure Rights Management-connector implementeren](../deploy-use/deploy-rms-connector.md) voor meer informatie over het configureren van de RMS-connector voor deze lokale servers.

## Volgende stappen
Zie [Vereisten voor Azure Rights Management](requirements-azure-rms.md) voor informatie over andere vereisten.



<!--HONumber=Jun16_HO4-->


