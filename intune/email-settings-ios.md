---
title: E-mailinstellingen voor iOS-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Het e-mailprofiel van een apparaatconfiguratie maken die gebruikmaakt van Exchange-servers en kenmerken ophaalt uit Azure Active Directory. U kunt tevens SSL inschakelen, gebruikers verifiëren met certificaten of gebruikersnaam/wachtwoord, en e-mail synchroniseren op iOS-apparaten met behulp van Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a6fd10ab6a1e9dd7249e2ae1d4bf558d190276ed
ms.sourcegitcommit: b0ee8626191961dc07f9f7f9d8e6a5fb09c63350
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/09/2018
ms.locfileid: "51505875"
---
# <a name="email-profile-settings-for-ios-devices---intune"></a>E-mailprofielinstellingen voor iOS-apparaten - Intune

U kunt met de e-mailprofielinstellingen uw apparaten met iOS configureren.

> [!IMPORTANT]
> Er worden enkele verbeteringen aangebracht aan de S/MIME-functie die in dit artikel wordt beschreven. Als gevolg hiervan is de S/MIME-functie tijdelijk uit Intune verwijderd. Wanneer deze functie wordt uitgebracht, wordt deze opmerking verwijderd.

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

- **Kenmerk van het e-mailadres van AAD**: kies op welke manier het e-mailadres voor de gebruiker wordt gegenereerd. Selecteer **User principal name** (`user1@contoso.com` of `user1`) om de volledige principal-naam als het e-mailadres te gebruiken. Selecteer **Primair SMTP-adres** (`user1@contoso.com`) om u met het primaire SMTP-adres bij Exchange aan te melden.
- **Verificatiemethode**: selecteer **Gebruikersnaam en wachtwoord** of **Certificaten** als verificatiemethode voor het e-mailprofiel. Meervoudige verificatie van Azure wordt niet ondersteund.
  - Als u **Certificaat** hebt geselecteerd, selecteert u een SCEP- of PKCS-clientcertificaatprofiel dat u eerder hebt gemaakt en dat wordt gebruikt voor verificatie van de Exchange-verbinding.
- **SSL**: u kunt deze optie **inschakelen** om SSL-communicatie (Secure Sockets Layer) te gebruiken wanneer u e-mailberichten verzendt, e-mailberichten ontvangt en communiceert met de Exchange-server.
- **OAuth**: **Inschakelen** gebruikt OAuth-communicatie (Open Authorization) om e-mails te verzenden en te ontvangen en met Exchange te communiceren. Als uw OAuth-server verificatie van certificaten gebruikt, kiest u **Certificaat** als **Verificatiemethode** en voegt u het certificaat in het profiel in. Kies anders **Gebruikersnaam en wachtwoord** als **verificatiemethode**. Als u OAuth gebruikt, moet u:

  - Controleren of uw e-mailoplossing OAuth ondersteunt voordat u dit profiel naar uw gebruikers stuurt. Controleren of Office 365 Exchange online ondersteuning biedt voor OAuth. Mogelijk bieden on-premises Exchange en andere oplossingen van partners of derden geen ondersteuning voor OAuth. On-premises Exchange kan worden geconfigureerd voor Modern Authentication (zie de blogpost [Announcing Hybrid Modern Authentication for Exchange On-Premises](https://blogs.technet.microsoft.com/exchange/2017/12/06/announcing-hybrid-modern-authentication-for-exchange-on-premises/) (Aankondiging van Hybride moderne verificatie voor on-premises Exchange)).

    Als OAuth voor het e-mailprofiel wordt gebruikt en de e-mailservice hier geen ondersteuning voor biedt, wordt de optie **Wachtwoord opnieuw invoeren** gebroken weergegeven. Er gebeurt bijvoorbeeld niets wanneer de gebruiker de optie **Wachtwoord opnieuw invoeren** selecteert bij de apparaatinstellingen in Apple.

  - Wanneer OAuth is ingeschakeld, hebben eindgebruikers een andere ervaring bij het aanmelden voor e-mail door middel van moderne verificatie die ondersteuning biedt voor meervoudige verificatie (MFA). 

  - Sommige organisaties schakelen voor eindgebruikers de mogelijkheid uit om [via selfservice toegang te krijgen tot toepassingen](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-self-service-access). In dit scenario kunt u zich mogelijk niet aanmelden bij Modern Authentication totdat een beheerder de zakelijke app iOS Accounts maakt en gebruikers toegang geeft tot de app in Azure AD.

    De standaardactie is een toepassing toevoegen met de functie [Toegangsvenster voor toepassingen](https://docs.microsoft.com/azure/active-directory/user-help/active-directory-saas-access-panel-introduction) **App toevoegen**  **zonder goedkeuring van het bedrijf**. Raadpleeg [Gebruikers toewijzen aan toepassingen](https://docs.microsoft.com/azure/active-directory/manage-apps/ways-users-get-assigned-to-applications) voor meer informatie.

  > [!NOTE]
  > Wanneer u OAuth inschakelt, gebeurt het volgende:  
  > 1. Apparaten die al als doel zijn ingesteld, krijgen een nieuw profiel.
  > 2. Eindgebruikers wordt gevraagd hun referenties opnieuw in te voeren.

- **S/MIME**: u kunt **S/MIME inschakelen** om uitgaande e-mail met S/MIME-ondertekening te versturen. Wanneer dit is ingeschakeld, kunt u ook e-mailberichten versleutelen naar ontvangers die versleutelde e-mailberichten kunnen ontvangen, en e-mailberichten van afzenders ontsleutelen.
  - Als u **Certificaat** selecteert, kiest u een bestaand PKCS-certificaatprofiel voor verificatie van de Exchange-verbinding en/of versleuteling van e-mailverkeer.
- **Aantal dagen e-mail voor synchronisatie**: kies het aantal dagen waarvoor u e-mail wilt synchroniseren. Of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Toestaan dat berichten worden verplaatst naar andere e-mailaccounts**: u kunt deze optie **inschakelen** om toe te staan dat gebruikers e-mailberichten verplaatsen naar andere accounts die gebruikers op hun apparaat hebben geconfigureerd.
- **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden**: met **Inschakelen** kunnen gebruikers dit profiel als standaardaccount voor het verzenden van e-mail selecteren. Hiermee staat u toe dat toepassingen van derden e-mails kunnen openen in de systeemeigen e-mail-app om er bijvoorbeeld bestanden als bijlage aan toe te voegen.
- **Recent gebruikte e-mailadressen synchroniseren**: u kunt deze optie **inschakelen** om toe te staan dat gebruikers de lijst synchroniseren met e-mailadressen die onlangs zijn gebruikt op het apparaat met de server.

## <a name="next-steps"></a>Volgende stappen
[E-mailinstellingen configureren in Intune](email-settings-configure.md)
