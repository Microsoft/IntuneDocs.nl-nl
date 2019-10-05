---
title: E-mailinstellingen voor iOS-apparaten configureren in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een lijst van alle e-mailinstellingen die u kunt configureren en aan iOS-apparaten kunt toevoegen in Microsoft Intune, waaronder Exchange-servers gebruiken en kenmerken ophalen uit Azure Active Directory. U kunt tevens SSL inschakelen, gebruikers verifiëren met certificaten of gebruikersnaam/wachtwoord, en e-mail synchroniseren op iOS-apparaten met behulp van apparaatconfiguratieprofielen in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3bd91891fa6da770404dc0af6d59016aeefe30b3
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71734593"
---
# <a name="add-e-mail-settings-for-ios-devices-in-microsoft-intune"></a>E-mailinstellingen voor iOS-apparaten toevoegen in Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

In Microsoft Intune kunt u e-mail zo maken en configureren dat deze verbinding maakt met een e-mailserver of de wijze van verificatie kiest voor gebruikers, S/MIME gebruikt voor versleuteling, enzovoort.

In dit artikel worden alle e-mailinstellingen vermeld en beschreven, die beschikbaar zijn voor iOS-apparaten. U kunt een apparaatconfiguratieprofiel maken om deze e-mailinstellingen naar/op uw iOS-apparaten pushen/implementeren.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](../email-settings-configure.md).

> [!NOTE]
> Deze instellingen zijn beschikbaar voor alle inschrijvings typen. Zie [IOS-inschrijving](../ios-enroll.md)voor meer informatie over de inschrijvings typen.

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

- **S/MIME**: **schakel S/MIME in**, waarmee gebruikers zich kunnen aanmelden en/of e-mail kunnen versleutelen in de systeemeigen iOS-e-mailtoepassing. 

  Wanneer u S/MIME bij een e-mailbericht gebruikt, bevestigt u de authenticiteit van de afzender en de integriteit en vertrouwelijkheid van het bericht.

  - **S/MIME-ondertekening ingeschakeld**: Kies **Inschakelen** om gebruikers uitgaande e-mailberichten digitaal te laten ondertekenen voor het account dat u hebt ingevoerd. Ondertekening biedt gebruikers die berichten ontvangen de zekerheid dat het bericht afkomstig is van de specifieke afzender en niet van iemand die zich voordoet als de afzender. Met **Uitschakelen** wordt gebruikers niet toegestaan om het bericht digitaal te ondertekenen.
    - **Gebruiker toestaan om instelling te wijzigen**: kies **Inschakelen** om gebruikers toe te staan om S/MIME-ondertekeningsgedrag te wijzigen. Met **Uitschakelen** voorkomt u dat gebruikers de S/MIME-ondertekeningsinstelling wijzigen die u hebt geconfigureerd. Beschikbaar in iOS 12 en hoger.

  - **S/MIME-ondertekeningscertificaat**: selecteer een bestaand PKCS- of SCEP-certificaatprofiel dat wordt gebruikt voor het ondertekenen van e-mailberichten.
    - **Gebruiker toestaan om instelling te wijzigen**: kies **Inschakelen** om gebruikers toe te staan om het ondertekeningscertificaat te wijzigen. Met **Uitschakelen** voorkomt u dat gebruikers het ondertekeningscertificaat wijzigen en dwingt u gebruikers het certificaat te gebruiken dat u hebt geconfigureerd. Beschikbaar in iOS 12 en hoger.

  - **Standaard versleutelen**: met **Inschakelen** worden alle berichten standaard versleuteld. Met **Uitschakelen** worden alle berichten standaard niet versleuteld.
    - **Gebruiker toestaan om instelling te wijzigen**: kies **Inschakelen** om gebruikers toe te staan het standaardgedrag voor versleuteling te wijzigen. Met **Uitschakelen** voorkomt u dat gebruikers het standaardgedrag voor versleuteling wijzigen en dwingt u gebruikers de instelling te gebruiken die u hebt geconfigureerd. Beschikbaar in iOS 12 en hoger.

  - **Versleuteling per bericht afdwingen**: met Versleuteling per bericht kunnen gebruikers kiezen welke e-mailberichten worden versleuteld voordat ze worden verzonden. Kies **Inschakelen** om de optie Versleuteling per bericht weer te geven bij het maken van een nieuw e-mailbericht. Gebruikers kunnen vervolgens voor opt-in of opt-out kiezen ten aanzien van Versleuteling per bericht. Met **Uitschakelen** wordt voorkomen dat de optie Versleuteling per bericht wordt weergegeven.

    Als de instelling **Standaard versleutelen** is ingeschakeld, kunnen gebruikers door Versleuteling per bericht in te schakelen ervoor kiezen om per bericht versleuteling uit te schakelen. Als de instelling **Standaard versleutelen** is uitgeschakeld, kunnen gebruikers door Versleuteling per bericht in te schakelen ervoor kiezen om per bericht versleuteling in te schakelen.

  - **S/MIME-versleutelingscertificaat**: selecteer een bestaand PKCS- of SCEP-certificaatprofiel dat wordt gebruikt voor het versleutelen van e-mailberichten.
    - **Gebruiker toestaan om instelling te wijzigen**: kies **Inschakelen** om gebruikers toe te staan het versleutelingscertificaat te wijzigen. Met **Uitschakelen** voorkomt u dat gebruikers het versleutelingscertificaat wijzigen en dwingt u gebruikers het certificaat te gebruiken dat u hebt geconfigureerd. Beschikbaar in iOS 12 en hoger.
- **Aantal dagen e-mail voor synchronisatie**: kies het aantal dagen waarvoor u e-mail wilt synchroniseren. Of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Toestaan dat berichten worden verplaatst naar andere e-mailaccounts**: u kunt deze optie **inschakelen** om toe te staan dat gebruikers e-mailberichten verplaatsen naar andere accounts die gebruikers op hun apparaat hebben geconfigureerd.
- **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden**: met **Inschakelen** kunnen gebruikers dit profiel als standaardaccount voor het verzenden van e-mail selecteren. Hiermee staat u toe dat toepassingen van derden e-mails kunnen openen in de systeemeigen e-mail-app om er bijvoorbeeld bestanden als bijlage aan toe te voegen.
- **Recent gebruikte e-mailadressen synchroniseren**: u kunt deze optie **inschakelen** om toe te staan dat gebruikers de lijst synchroniseren met e-mailadressen die onlangs zijn gebruikt op het apparaat met de server.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens kunt u [het profiel toewijzen](../device-profile-assign.md) en [de status ervan controleren](../device-profile-monitor.md).

E-mail instellingen configureren voor [Android](../email-settings-android.md)-, [Android Enter prise](../email-settings-android-enterprise.md)-, [Windows 10](email-settings-windows-10.md)-en [Windows Phone 8,1](email-settings-windows-phone-8-1.md) -apparaten.
