---
title: E-mailinstellingen voor Windows Phone 8.1 in Microsoft Intune
titleSuffix: ''
description: Meer informatie over de Intune-instellingen die u kunt gebruiken om e-mailverbindingen op apparaten met Windows Phone 8.1 te configureren.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2f7a14d605ae3d1a5a951f40ec789c50c847c455
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565703"
---
# <a name="email-profile-settings-in-microsoft-intune-for-devices-running-windows-phone-81"></a>E-mailprofielinstellingen in Microsoft Intune voor apparaten met Windows Phone 8.1

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel ziet u de e-mailprofielinstellingen die u kunt configureren voor uw apparaten met Windows Phone 8.1.


- **Alle instellingen alleen op Windows Phone 8.1 toepassen**: dit is een instelling die u in de klassieke Intune-portal kunt configureren. In Azure Portal kan deze instelling niet worden gewijzigd. Als de instelling is ingesteld op **Geconfigureerd**, worden instellingen alleen toegepast op Windows Phone 8.1-apparaten. Als de instelling is ingesteld op **Niet geconfigureerd**, gelden deze instellingen ook voor Windows 10 Mobile-apparaten.
- **E-mailserver**: de hostnaam van uw Exchange-server.
- **Accountnaam**: de weergavenaam voor het e-mailaccount die wordt weergegeven op de apparaten van de gebruikers.
- **Kenmerk van de gebruikersnaam van AAD**: dit is het kenmerk in Active Directory (AD) of Azure AD dat wordt gebruikt voor het genereren van de gebruikersnaam voor dit e-mailprofiel. Selecteer het **primaire SMTP-adres**, zoals **user1@contoso.com** of de **User Principal Name**, zoals **gebruiker1** of **user1@contoso.com**.
- **Kenmerk van het e-mailadres van AAD**: de manier waarop het e-mailadres voor de gebruiker op elk apparaat wordt gegenereerd. Selecteer **Primair SMTP-adres** om het primaire SMTP-adres te gebruiken voor aanmelding bij Exchange of gebruik **User Principal Name** om de volledige User Principal Name te gebruiken als het e-mailadres.


## <a name="security-settings"></a>Beveiligingsinstellingen

- **SSL**: gebruik SSL-communicatie (Secure Sockets Layer) wanneer u e-mailberichten verzendt, e-mailberichten ontvangt en communiceert met de Exchange-server.



## <a name="synchronization-settings"></a>Synchronisatie-instellingen

- **Aantal dagen e-mail voor synchronisatie**: kies het aantal dagen waarvoor u e-mail wilt synchroniseren of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Synchronisatieschema**: selecteer het schema dat voor apparaten wordt gebruikt om gegevens van de Exchange-server te synchroniseren. U kunt ook **Wanneer berichten binnenkomen** selecteren als u wilt dat de berichten meteen worden gesynchroniseerd wanneer ze binnenkomen of **Handmatig** selecteren als u wilt dat de gebruiker van het apparaat de synchronisatie zelf uitvoert.

## <a name="content-sync-settings"></a>Instellingen voor inhoudssynchronisatie

- **Inhoudstype voor synchronisatie**: selecteer de inhoudstypen die u wilt synchroniseren met apparaten. U hebt de volgende opties:
    - **Contactpersonen**
    - **Kalender**
    - **Taken**
