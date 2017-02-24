---
title: Apps gebruiken met MAM CA | Microsoft Docs
description: Dit onderwerp helpt u te begrijpen hoe MAM CA kan helpen bij het beheren van welke apps toegang hebben tot O365-services.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71dcf9bc-bfd1-4e06-b7ad-14b33a2288d0
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: fbb41a8cf6fada76b72213b8cb04fdc0428515e9
ms.openlocfilehash: 2ab3769ff878cf8b6223e4f46244f16eab8743a0


---
# <a name="what-to-expect-when-using-an-app-with-app-based-ca"></a>Wat u kunt verwachten wanneer u een app met app-CA gebruikt

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Met app-CA wordt de identiteit van de goedgekeurde toepassing geverifieerd via een broker-app die geïnstalleerd moet zijn op het apparaat:
*  Voor **iOS** is de **Azure Authenticator-app** de broker-app.
* Voor **Android** is de **Intune-bedrijfsportal-app** de broker-app. 

Eindgebruikers die zich voor het eerst aanmelden bij een app die wordt ondersteund door app-CA, zoals OneDrive of Outlook, wordt gevraagd de broker-app te installeren en het apparaat te registreren bij Azure AD. Met Apparaatregistratie in Azure AD (voorheen bekend als Aan werkplek toevoegen) wordt een apparaatrecord gemaakt en een certificaat waartegen tokens worden uitgegeven.  Dit is **niet** hetzelfde als **MDM-registratie**. Er worden geen beheerprofielen of beleidsregels toegepast, en apps op het apparaat worden niet geïnventariseerd.  Het proces voor het installeren van de broker-app en het registreren van het apparaat wordt alleen uitgevoerd bij het eerste gebruik van een beheerde app.

Hier volgt een lijst met eigenschappen die rechtstreeks zijn afgeleid van het apparaat:

* alternativeSecurityIds (certificaatvingerafdruk van Azure Active Directory en openbare sleutel-hash)
* deviceOSType
* deviceOSVersion
* displayName

## <a name="to-remove-a-device-from-azure-ad-registration"></a>Een apparaat verwijderen uit Azure AD-registratie.
U kunt de apparaatregistratie verwijderen via de Azure AD-beheerconsole. Doorgaans doet de IT-beheerder dit.  De apparaatregistratie kan echter ook door de eindgebruiker op het apparaat zelf worden verwijderd.

* **Azure AD-beheerconsole**: verwijder in de Azure AD-beheerconsole** het gewenste apparaat.
* **iOS-apparaat**: open de Azure Authenticator-app, veeg links in het account en kies Registratie ongedaan maken.  
* **Android-apparaat**: verwijder de bedrijfsportal-app of verwijder het account uit de **Systeeminstellingen**.



## <a name="app-based-ca-with-conditional-access-based-on-device-compliance"></a>App-CA met voorwaardelijke toegang op basis van apparaatcompatibiliteit  

U kunt [voorwaardelijke toegang op basis van apparaatcompatibiliteit](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**Device CA**) configureren in de [Intune-beheerdersconsole](https://manage.microsoft.com) of de [Azure AD Premium-beheerconsole] (https://manage.windowsazure.com). Voor Device CA mogen gebruikers alleen verbinding maken met Exchange Online via door Intune beheerde apparaten die compatibel zijn met het Intune-apparaatcompatibiliteitsbeleid of pc's die lid zijn van een domein.  Als een gebruiker tot een of meer beveiligingsgroepen behoort die zijn geconfigureerd voor app-CA- en Device CA-beleid, moet de gebruiker aan een van deze twee vereisten voldoen:
* De app die wordt gebruikt voor toegang tot de service is een mobiele app die wordt ondersteund door 
* , en op het apparaat waarop de app wordt uitgevoerd, is **iOS verificator (voor iOS-apparaten)** of de **bedrijfsportal-app (voor Android-apparaten)** geïnstalleerd.
* Het apparaat dat wordt gebruikt om toegang tot de service te verkrijgen, wordt **door Intune beheerd en is compatibel** met het Intune-apparaatcompatibiliteitsbeleid of is een **pc die lid is van een domein**.  Hier volgen enkele voorbeelden om dit te verduidelijken:
  * Als een gebruiker verbinding wil maken vanuit de **systeemeigen e-mail-app voor iOS**, moet hij of zij dat doen op een **beheerd en compatibel apparaat**, omdat de systeemeigen e-mail-app niet wordt ondersteund door app-CA.
  * Als een gebruiker verbinding wil maken vanaf een **Windows Home-pc**, geldt het **Device CA-beleid** en moet hij of zij een pc gebruiken die lid is van een domein.

## <a name="next-steps"></a>Volgende stappen
[Een Exchange Online-beleid voor MAM-apps maken](mam-ca-for-exchange-online.md)

[Apps die geen gebruik maken van moderne verificatie blokkeren](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Zie tevens

[Beveilig app-gegevens met beveiligingsbeleid voor apps](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Feb17_HO2-->


