---
title: Op apps gebaseerde voorwaardelijke toegang tot 0365
description: Dit onderwerp helpt u te begrijpen hoe MAM CA kan helpen bij het beheren van welke apps toegang hebben tot O365-services.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8fc53e8717277a4075bc7ecde31fd60c3539a5f7
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="allow-only-mobile-apps-that-support-intune-app-protection-policies-to-access-office-365-services"></a>Alleen mobiele apps met ondersteuning voor app-beschermingsbeleid van Intune toegang geven tot Office 365-services

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

U kunt [beveiligingsbeleid voor apps in Intune](protect-apps-and-data-with-microsoft-intune.md) gebruiken om te helpen bij het beveiligen van uw bedrijfsgegevens op apparaten die zijn geregistreerd voor beheer in Intune. U kunt ook beveiligingsbeleid voor apps gebruiken op **apparaten die in het bezit zijn van werknemers en die niet zijn geregistreerd voor beheer in Intune**.  In dit geval moet u, zelfs als u het apparaat niet beheert, er nog steeds voor zorgen dat uw bedrijfsgegevens en -bronnen zijn beveiligd. Met voorwaardelijke toegang voor apps met MAM kunt u een beleid maken waarmee alleen mobiele apps met ondersteuning voor beveiligingsbeleid voor apps in Intune toegang kunnen krijgen tot O365-services zoals Exchange Online.

Als u bijvoorbeeld alleen de **Microsoft Outlook-app** toegang geeft tot Exchange Online, kunt u **de ingebouwde e-mail-apps op iOS en Android blokkeren**. Deze hebben immers niet de gegevensbeveiliging van Intune MAM-beleid voor het ophalen van e-mail van **Exchange Online**. Of u kunt mobiele apps die geen Intune MAM- ondersteuning hebben blokkeren tegen toegang tot **SharePoint Online**.

In het volgende diagram ziet u de stroom die door het beleid voor voorwaardelijke toegang voor apps wordt gebruikt om te bepalen of de toegang moet worden toegestaan of geblokkeerd: ![Diagram met de verschillende opgenomen criteria om te bepalen of toegang moet worden toegestaan of geblokkeerd ](../media/mam-ca-decision-flow_simple.png).

Beschrijving van de afkortingen die in de diagrammen worden gebruikt:
* **CP**: Company Portal-app (bedrijfsportal-app)
* **AA**: Azure Authenticator-app
* **AAD**: Azure Active Directory
* **EAS**: Exchange Active Sync

## <a name="prerequisites"></a>Vereisten
**Voordat** u een beleid voor voorwaardelijke toegang voor apps kunt configureren, moet u een **abonnement voor Enterprise Mobility + Security of Azure Active Directory Premium** hebben, en moeten de gebruikers een licentie hebben voor EMS of Azure AD. Zie de [Enterprise Mobility-pagina met prijzen](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) of de [Azure Active Directory-pagina met prijzen](https://azure.microsoft.com/pricing/details/active-directory/) voor meer informatie.


## <a name="supported-apps"></a>Ondersteunde apps
**Exchange Online**:
* **Microsoft Outlook** voor Android en iOS.

**SharePoint Online**
* Microsoft Word voor iOS en Android
* Microsoft Excel voor iOS en Android
* Microsoft PowerPoint voor iOS en Android
* Microsoft OneDrive voor Bedrijven voor iOS en Android
* Microsoft OneNote voor iOS

>[!IMPORTANT]
>Voor Android-apparaten moet de eerste apparaatregistratie worden gedaan door u aan te melden bij de app OneDrive of Outlook. De app OneNote voor Android biedt nog geen ondersteuning voor MAM zonder registratie.

Zie [Wat u kunt verwachten wanneer u een app met MAM CA gebruikt](use-apps-with-mam-ca.md) voor meer informatie over de gebruikerservaring voor apps met beleid voor voorwaardelijke toegang.


## <a name="next-steps"></a>Volgende stappen
[Een Exchange Online-beleid voor MAM-apps maken](mam-ca-for-exchange-online.md)

[Een SharePoint Online-beleid voor MAM-apps maken](mam-ca-for-sharepoint-online.md)

[Apps die geen gebruik maken van moderne verificatie blokkeren](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Zie tevens

[Beveilig app-gegevens met beveiligingsbeleid voor apps](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
