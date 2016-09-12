---
title: Toepassingen configureren voor Azure Rights Management | Azure RMS
description: "Nadat u voor uw organisatie Azure Rights Management (Azure RMS) hebt geïmplementeerd, raadpleegt u de volgende informatie voor het configureren van toepassingen en services die Azure RMS ondersteunen. Hieronder vallen Office-toepassingen zoals Word 2010 en Word 2013, en services als Exchange Online (transportregels, voorkomen van gegevensverlies, tegengaan van het doorsturen van berichten en berichtversleuteling) en SharePoint Online (beveiligde bibliotheken)."
author: cabailey
manager: mbaldwin
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: ea09cbc5-b98b-444e-8b60-5bc3cb199c36
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 024a29d7c7db2e4c0578a95c93e22f8e7a5b173e
ms.openlocfilehash: 7e592d99bcd2a143d63b35aa4afb92b1e45cb74a


---

# Toepassingen voor Azure Rights Management configureren

>*Van toepassing op: Azure Rights Management, Office 365*

> [!NOTE]
> Deze informatie is bedoeld voor IT-beheerders en consultants die Azure Rights Management hebben geïmplementeerd. Als u op zoek bent naar gebruikersondersteuning en informatie over het gebruik van Rights Management voor een bepaalde toepassing of over het openen van een met rechten beveiligd bestand, raadpleegt u de Help-onderwerpen en instructies bij uw toepassing.
>
> Voor Office-toepassingen klikt u bijvoorbeeld op het Help-pictogram en typt u een zoekterm als **Rights Management** of **IRM**. Zie de [Gebruikershandleiding voor de Rights Management-toepassing voor delen](../rms-client/sharing-app-user-guide.md) voor informatie over de Rights Management-toepassing voor delen.

Nadat u voor uw organisatie Azure Rights Management (Azure RMS) hebt geïmplementeerd, raadpleegt u de volgende informatie voor het configureren van toepassingen en services die Azure RMS ondersteunen. Hieronder vallen Office-toepassingen zoals Word 2010 en Word 2013, en services als Exchange Online (transportregels, voorkomen van gegevensverlies, tegengaan van het doorsturen van berichten en berichtversleuteling) en SharePoint Online (beveiligde bibliotheken). Zie [Hoe toepassingen ondersteuning bieden voor Azure Rights Management](../understand-explore/applications-support.md) voor informatie over de wijze waarop deze toepassingen en services ondersteuning bieden voor Azure Rights Management.

> [!IMPORTANT]
> Zie [Vereisten voor Azure Rights Management](../get-started/requirements-azure-rms.md) voor informatie over de versies die worden ondersteund en andere vereisten.

-   [Office 365: configuratie voor clients en onlineservices](configure-office365.md)

    -   [Exchange Online: IRM-configuratie](configure-office365.md#exchange-online-irm-configuration)

    -   [SharePoint Online en OneDrive voor Bedrijven: IRM-configuratie](configure-office365.md#sharepoint-online-and-onedrive-for-business-irm-configuration)

- [Office-toepassingen: configuratie voor clients](configure-office-apps.md)

    -   [Office 2016 en Office 2013](configure-office-apps.md#office-2016-and-office-2013)

    -   [Office 2010](configure-office-apps.md#office-2010)

-   [Rights Management-toepassing voor delen: installatie en configuratie voor clients](configure-sharing-app.md)

    -   [De RMS-toepassing voor delen voor Windows: installatie en configuratie](configure-sharing-app.md#the-rms-sharing-application-for-windows-installation-and-configuration)

    -   [De Rights Management-toepassing voor delen voor mobiele platforms: installatie en beheer](configure-sharing-app.md#the-rms-sharing-application-for-mobile-platforms-installation-and-management)


Zie [De Azure Rights Management-connector implementeren](deploy-rms-connector.md) voor informatie over het configureren van on-premises servers zoals Exchange-Server en SharePoint Server.

> [!TIP]
> Zie [Azure RMS in actie: wat beheerders en gebruikers zien](../understand-explore/what-admins-users-see.md) voor voorbeelden en schermopnamen van toepassingen die zijn geconfigureerd voor het gebruik van Azure RMS.


Naast deze toepassingen en services zijn er ook andere toepassingen die ondersteuning bieden voor de RMS-API's. Hiertoe behoren line-of-business-toepassingen die intern zijn geschreven met behulp van de RMS SDK en toepassingen van softwareleveranciers die zijn geschreven met behulp van de RMS SDK. Volg voor deze toepassingen de instructies die met de toepassing zijn meegeleverd.

## Volgende stappen
Nadat u uw toepassingen voor Azure Rights Management hebt geconfigureerd, controleert u met het [Azure Rights Management-implementatieschema](../plan-design/deployment-roadmap.md) of er andere configuratiestappen zijn die u zou willen uitvoeren voordat u [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] implementeert voor gebruikers en beheerders. Als dat niet het geval is, vindt u mogelijk de volgende operationele informatie handig:

- [Azure Rights Management controleren](verify.md)

- [Gebruikers helpen bij het beveiligen van bestanden door gebruik te maken van Azure Rights Management](help-users.md)

- [Logboekregistratie en analyse van Azure Rights Management](log-analyze-usage.md)

- [Bewerkingen voor uw Azure Rights Management-tenantsleutel](operations-tenant-key.md)





<!--HONumber=Aug16_HO4-->


