---
title: Op apps gebaseerde voorwaardelijke toegang tot O365 | Microsoft Docs
description: Dit onderwerp helpt u te begrijpen hoe MAM CA kan helpen bij het beheren van welke apps toegang hebben tot O365-services.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 2babdeaaf10e9a58716d299cbde0babe45967fb1


---

# <a name="allow-only-mobile-apps-that-support-intune-mam-policies-to-access-office-365-services"></a>Toestaan dat alleen mobiele apps met ondersteuning voor Intune MAM-beleid toegang kunnen krijgen tot Office 365-services

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

U kunt [Intune MAM-beleid (Mobile Application Management)](protect-apps-and-data-with-microsoft-intune.md) gebruiken om te helpen bij het beveiligen van uw bedrijfsgegevens op apparaten die zijn geregistreerd voor beheer in Intune. U kunt ook MAM-beleid gebruiken op **apparaten die in het bezit zijn van werknemers en die niet zijn geregistreerd voor beheer in Intune**.  In dit geval moet u, zelfs als u het apparaat niet beheert, er nog steeds voor zorgen dat uw bedrijfsgegevens en -bronnen zijn beveiligd. Met voorwaardelijke toegang voor MAM (MAM CA) kunt u een beleid maken waarmee alleen mobiele apps met ondersteuning voor Intune MAM-beleid toegang kunnen krijgen tot O365-services zoals Exchange Online.

Als u bijvoorbeeld alleen de **Microsoft Outlook-app** toegang geeft tot Exchange Online, kunt u **de ingebouwde e-mail-apps op iOS en Android blokkeren**. Deze hebben immers niet de gegevensbeveiliging van Intune MAM-beleid voor het ophalen van e-mail van **Exchange Online**.

In het volgende diagram ziet u de stroom die door het MAM CA-beleid wordt gebruikt om te bepalen of de toegang moet worden toegestaan of geblokkeerd: ![Diagram met de verschillende opgenomen criteria om te bepalen of toegang moet worden toegestaan of geblokkeerd ](../media/mam-ca-decision-flow_simple.png).

Beschrijving van de afkortingen die in de diagrammen worden gebruikt:
* **CP**: Company Portal-app (bedrijfsportal-app)
* **AA**: Azure Authenticator-app
* **AAD**: Azure Active Directory
* **EAS**: Exchange Active Sync

## <a name="prerequisites"></a>Vereisten
**Voordat** u MAM CA-beleid kunt configureren, moet u een **abonnement voor Enterprise Mobility + Security of Azure Active Directory Premium** hebben, en moeten de gebruikers een licentie hebben voor EMS of Azure AD. Zie de [Enterprise Mobility-pagina met prijzen](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) of de [Azure Active Directory-pagina met prijzen](https://azure.microsoft.com/en-us/pricing/details/active-directory/) voor meer informatie.


## <a name="supported-apps"></a>Ondersteunde apps
**Exchange Online**: **Microsoft Outlook** voor Android en iOS.

Zie [What to expect when using an app with MAM CA](use-apps-with-mam-ca.md) (Wat u kunt verwachten wanneer u een app met MAM CA gebruikt) voor meer informatie over de gebruikerservaring voor apps met MAM CA-beleidsregels.


## <a name="next-steps"></a>Volgende stappen
[Een Exchange Online-beleid voor MAM-apps maken](mam-ca-for-exchange-online.md)

[Apps die geen gebruik maken van moderne verificatie blokkeren](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Zie tevens

[App-gegevens beveiligen met MAM-beleid](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


