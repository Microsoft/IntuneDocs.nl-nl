---
title: E-mailinstellingen voor iOS-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Het e-mailprofiel van een apparaatconfiguratie maken die gebruikmaakt van Exchange-servers en kenmerken ophaalt uit Azure Active Directory. U kunt tevens SSL inschakelen, gebruikers verifiëren met certificaten of gebruikersnaam/wachtwoord, en e-mail synchroniseren op iOS-apparaten met behulp van Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2d2fc7f697d03c1ffcb952cd30e29f4959f2b7e9
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321166"
---
# <a name="email-profile-settings-for-ios-devices---intune"></a>E-mailprofielinstellingen voor iOS-apparaten - Intune

U kunt met de e-mailprofielinstellingen uw apparaten met iOS configureren.

## <a name="email-settings"></a>E-mailinstellingen

- **E-mailserver**: voer de hostnaam in van uw Exchange-server.
- **Accountnaam**: voer de weergavenaam in voor het e-mailaccount. Deze naam zien gebruikers op hun apparaat.
- **Het kenmerk gebruikersnaam van AAD**: deze naam is het kenmerk dat Intune uit Azure Active Directory (AAD) ophaalt. In Intune wordt de gebruikersnaam die wordt gebruikt door dit profiel dynamisch gegenereerd. Uw opties zijn:
  - **User Principal Name**: hiermee wordt de naam opgehaald, zoals `user1` of `user1@contoso.com`
  - **Primair SMTP-adres**: haalt de naam op in de indeling van het e-mailadres, zoals `user1@contoso.com`
  - **sAM-accountnaam**: hiervoor is het domein vereist, zoals `domain\user1`.

    Voer ook in:  
    - **Bron van gebruikersdomeinnaam**: kies **AAD** (Azure Active Directory) of **Aangepast**.

      Voer, wanneer u ervoor kiest om de kenmerken op te halen van **AAD**, het volgende in:
      - **Kenmerk voor gebruikersdomeinnaam van AAD**: kies de optie om de **volledige domeinnaam** of het kenmerk **NetBIOS-naam** van de gebruiker op te halen

      Wanneer u ervoor kiest om **aangepaste** kenmerken te gebruiken, moet u het volgende invoeren:
      - **Te gebruiken aangepaste domeinnaam**: voer een waarde in die Intune voor de domeinnaam gebruikt, zoals `contoso.com` of `contoso`

- **Kenmerk van het e-mailadres van AAD**: kies op welke manier het e-mailadres voor de gebruiker wordt gegenereerd. Selecteer **User principal name** (`user1@contoso.com` of `user1`) om de volledige user principal name als e-mailadres te gebruiken, of **Primair SMTP-adres** (`user1@contoso.com`) om het primaire SMTP-adres te gebruiken om u aan te melden bij Exchange.
- **Verificatiemethode**: selecteer **Gebruikersnaam en wachtwoord** of **Certificaten** als verificatiemethode voor het e-mailprofiel. Meervoudige verificatie van Azure wordt niet ondersteund.
  - Als u **Certificaat** hebt geselecteerd, selecteert u een SCEP- of PKCS-clientcertificaatprofiel dat u eerder hebt gemaakt en dat wordt gebruikt voor verificatie van de Exchange-verbinding.
- **SSL**: u kunt deze optie **inschakelen** om SSL-communicatie (Secure Sockets Layer) te gebruiken wanneer u e-mailberichten verstuurt, e-mailberichten ontvangt en communiceert met de Exchange-server.
- **S/MIME**: u kunt **S/MIME inschakelen** om uitgaande e-mail met S/MIME-ondertekening te versturen. Wanneer dit is ingeschakeld, kunt u ook e-mailberichten versleutelen naar ontvangers die versleutelde e-mailberichten kunnen ontvangen, en e-mailberichten van afzenders ontsleutelen.
  - Als u **Certificaat** hebt geselecteerd, selecteert u een PKCS-certificaatprofiel dat u eerder hebt gemaakt voor verificatie van de Exchange-verbinding en/of versleuteling van e-mailverkeer.
- **Aantal dagen e-mail voor synchronisatie**: kies het aantal dagen waarvoor u e-mail wilt synchroniseren. Of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Toestaan dat berichten worden verplaatst naar andere e-mailaccounts**: u kunt deze optie **inschakelen** om toe te staan dat gebruikers e-mailberichten verplaatsen naar andere accounts die op hun apparaat zijn geconfigureerd.
- **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden**: u kunt deze optie **inschakelen** om toe te staan dat de gebruiker dit profiel selecteert als het standaardaccount voor het versturen van e-mail en toe te staan dat toepassingen van derden e-mail openen in de systeemeigen e-mail-app, om bijvoorbeeld bestanden als bijlagen aan e-mail toe te voegen.
- **Recent gebruikte e-mailadressen synchroniseren**: u kunt deze optie **inschakelen** om toe te staan dat gebruikers de lijst synchroniseren met e-mailadressen die onlangs zijn gebruikt op het apparaat met de server.

## <a name="next-steps"></a>Volgende stappen
[E-mailinstellingen configureren in Intune](email-settings-configure.md)
