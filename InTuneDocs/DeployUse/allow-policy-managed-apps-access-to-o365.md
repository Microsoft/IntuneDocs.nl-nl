---
title: Op apps gebaseerde voorwaardelijke toegang tot 0365 | Microsoft Intune
description: Dit onderwerp helpt u te begrijpen hoe MAM CA kan helpen bij het beheren van welke apps toegang hebben tot O365-services.
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 64eaba6918c4a5c7ccc39fb8ccfeae729a34ff4c
ms.openlocfilehash: a03faa57f9bf1ec6784f0b1ec2d41d3f4cd88a12


---

# Een beleid maken waarmee alleen mobiele apps met ondersteuning voor Intune MAM-beleid toegang kunnen krijgen tot Office 365-services
U kunt [Intune MAM-beleid (Mobile Application Management)](protect-apps-and-data-with-microsoft-intune.md) gebruiken om te helpen bij het beveiligen van uw bedrijfsgegevens op apparaten die zijn geregistreerd voor beheer in Intune. U kunt ook MAM-beleid gebruiken op **apparaten die in het bezit zijn van werknemers en die niet zijn geregistreerd voor beheer in Intune**.  In dit geval moet u, zelfs als u het apparaat niet beheert, er nog steeds voor zorgen dat uw bedrijfsgegevens en -bronnen zijn beveiligd. Met voorwaardelijke toegang voor MAM (MAM CA) kunt u een beleid maken waarmee alleen mobiele apps met ondersteuning voor Intune MAM-beleid toegang kunnen krijgen tot O365-services zoals Exchange Online.

Als u bijvoorbeeld alleen de **Microsoft Outlook-app** toegang geeft tot Exchange Online, kunt u **de ingebouwde e-mailapps op iOS en Android blokkeren**. Deze hebben immers niet de gegevensbeveiliging van Intune MAM-beleid voor het ophalen van e-mail van **Exchange Online**.

## Vereisten
**Voordat** u MAM CA-beleid kunt configureren, moet u een **abonnement voor Enterprise Mobility + Security of Azure Active Directory Premium** hebben, en moeten de gebruikers een licentie hebben voor EMS of Azure AD. Zie de [Enterprise Mobility-pagina met prijzen](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) of de [Azure Active Directory-pagina met prijzen](https://azure.microsoft.com/en-us/pricing/details/active-directory/) voor meer informatie.


## Ondersteunde apps
**Exchange Online**
* Microsoft Outlook voor Android en iOS

## Overlappen met andere methoden voor voorwaardelijke toegang en verificatie
### MAM CA en op Azure Active Directory gebaseerde verificatie via certificaat

MAM CA mag niet worden gebruikt in combinatie met verificatie via het certificaat op basis van Azure Active Directory (Azure AD). U mag slechts een van beide geconfigureerd hebben.
### MAM CA met voorwaardelijke toegang op basis van apparaatcompatibiliteit  

U kunt [voorwaardelijke toegang op basis van apparaatcompatibiliteit](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**Device CA**) configureren in de [Intune-beheerdersconsole](https://manage.microsoft.com) of de [Azure AD Premium-beheerconsole] (https://manage.windowsazure.com). Voor Device CA mogen gebruikers alleen verbinding maken met Exchange Online via door Intune beheerde apparaten die compatibel zijn met het Intune-apparaatcompatibiliteitsbeleid of pc's die lid zijn van een domein.  Als een gebruiker tot een of meer beveiligingsgroepen behoort die zijn geconfigureerd voor MAM CA- en Device CA-beleid, moet de gebruiker aan een van deze twee vereisten voldoen:
* De app die wordt gebruikt om toegang tot de service te verkrijgen, is een mobiele app die wordt ondersteund door MAM CA en op het apparaat waarop de app wordt uitgevoerd, is **iOS verificator (voor iOS-apparaten)** of de **bedrijfsportalapp (voor Android-apparaten)** geïnstalleerd.
* Het apparaat dat wordt gebruikt om toegang tot de service te verkrijgen, wordt **door Intune beheerd en is compatibel** met het Intune-apparaatcompatibiliteitsbeleid of is een **pc die lid is van een domein**.  Hier volgen enkele voorbeelden om dit te verduidelijken:
  * Als een gebruiker verbinding wil maken vanuit de **systeemeigen e-mailapp voor iOS**, moet hij of zij dat doen op een **beheerd en compatibel apparaat** omdat de systeemeigen e-mailapp niet wordt ondersteund door MAM CA.
  * Als een gebruiker verbinding wil maken vanaf een **Windows Home-pc**, geldt het **Device CA-beleid** en moet hij of zij een pc gebruiken die lid is van een domein.


## Wat u kunt verwachten wanneer u een app met MAM CA gebruikt
Met MAM CA wordt de identiteit van de goedgekeurde toepassing geverifieerd via een broker-app die geïnstalleerd moet zijn op het apparaat:
*  Voor **iOS** is de **Azure Authenticator-app** de broker-app.
* Voor **Android** is de **Intune-bedrijfsportalapp** de broker-app. 

Eindgebruikers die zich voor het eerst aanmelden bij een app die wordt ondersteund door MAM CA, zoals OneDrive of Outlook, wordt gevraagd de broker-app te installeren en het apparaat te registreren bij Azure AD. Met Apparaatregistratie in Azure AD (voorheen bekend als Aan werkplek toevoegen) wordt een apparaatrecord gemaakt en een certificaat waartegen tokens worden uitgegeven.  Dit is **niet** hetzelfde als **MDM-registratie**. Er worden geen beheerprofielen of beleidsregels toegepast, en apps op het apparaat worden niet geïnventariseerd.  Het proces voor het installeren van de broker-app en het registreren van het apparaat wordt alleen uitgevoerd bij het eerste gebruik van een beheerde app.


## Volgende stappen
[Een Exchange Online-beleid voor MAM-apps maken](mam-ca-for-exchange-online.md)

[Apps die geen gebruik maken van moderne verificatie blokkeren](block-apps-with-no-modern-authentication.md)

### Zie tevens

[App-gegevens beveiligen met MAM-beleid](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


