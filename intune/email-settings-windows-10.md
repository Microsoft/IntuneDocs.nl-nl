---
title: E-mailinstellingen voor Windows 10-apparaten in Intune
titleSuffix: Azure portal
description: Meer informatie over de Intune-instellingen die u kunt gebruiken om e-mailverbindingen op Windows 10-apparaten te configureren.
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ffafbd0-4b5d-4c86-a46b-611f9b7a58e5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 61cd80fafa961ec75c400a03dbbc00ce24b99abb
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2017
---
# <a name="email-profile-settings-for-windows-10-devices-in-microsoft-intune"></a>E-mailprofielinstellingen voor Windows 10-apparaten in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]



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
