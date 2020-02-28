---
title: E-mailinstellingen voor iOS-/iPadOS-apparaten configureren in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een lijst met alle e-mailinstellingen die u kunt configureren en aan iOS-/iPadOS-apparaten kunt toevoegen in Microsoft Intune, waaronder het gebruiken van Exchange-servers en het ophalen van kenmerken uit Azure Active Directory. U kunt tevens SSL inschakelen, gebruikers verifiëren met certificaten of gebruikersnaam/wachtwoord, en e-mail synchroniseren op iOS-/iPadOS-apparaten met behulp van apparaatconfiguratieprofielen in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0ea06c50b1da237d4a822e80a8085b3b51913cec
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512803"
---
# <a name="add-e-mail-settings-for-ios-and-ipados-devices-in-microsoft-intune"></a>E-mailinstellingen toevoegen voor iOS-/iPadOS-apparaten in Microsoft Intune

In Microsoft Intune kunt u e-mail zo maken en configureren dat deze verbinding maakt met een e-mailserver of de wijze van verificatie kiest voor gebruikers, S/MIME gebruikt voor versleuteling, enzovoort.

In dit artikel worden alle e-mailinstellingen vermeld en beschreven, die beschikbaar zijn voor iOS-/iPadOS-apparaten. U kunt een apparaatconfiguratieprofiel maken om deze e-mailinstellingen te pushen naar of te implementeren op uw iOS-/iPadOS-apparaten.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](../email-settings-configure.md).

> [!NOTE]
> Deze instellingen zijn beschikbaar voor alle inschrijvingstypen. Zie [iOS-/iPadOS-inschrijving](../ios-enroll.md) voor meer informatie over de inschrijvingstypen.

## <a name="exchange-activesync-account-settings"></a>Exchange ActiveSync-accountinstellingen

- **E-mailserver**: Voer de hostnaam van uw Exchange-server in.
- **Accountnaam**: Voer de weergavenaam voor het e-mailaccount in. Deze naam zien gebruikers op hun apparaat.
- **Het kenmerk Gebruikersnaam van AAD**: Deze naam is het kenmerk dat Intune uit Azure Active Directory (AAD) ophaalt. In Intune wordt de gebruikersnaam die wordt gebruikt door dit profiel dynamisch gegenereerd. Uw opties zijn:
  - **User Principal Name**: Hiermee wordt de naam opgehaald, zoals `user1` of `user1@contoso.com`
  - **Primair SMTP-adres**: Hiermee haalt u de naam op in de indeling van het e-mailadres, zoals `user1@contoso.com`
  - **sAM-accountnaam**: Hiervoor is het domein vereist, zoals `domain\user1`. Voer ook in:  
    - **Bron van gebruikersdomeinnaam**: Kies **AAD** (Azure Active Directory) of **Aangepast**.
      - **AAD**: haal de kenmerken op uit Azure AD. Voer ook in:
        - **Het kenmerk Gebruikersdomeinnaam van AAD**: Kies de optie om de **volledige domeinnaam** (`contoso.com`) of het kenmerk **NetBIOS-naam** (`contoso`) van de gebruiker op te halen.

      - **Aangepast**: haal de kenmerken op uit een aangepaste domeinnaam. Voer ook in:
        - **Te gebruiken aangepaste domeinnaam**: Voer een waarde in die voor de domeinnaam wordt gebruikt in Intune, zoals `contoso.com` of `contoso`.

- **Kenmerk van het e-mailadres van AAD**: Kies op welke manier het e-mailadres voor de gebruiker wordt gegenereerd. Uw opties zijn:
  - **User Principal Name**: Gebruik de volledige principal-naam als het e-mailadres, zoals `user1@contoso.com` of `user1`.
  - **Primair SMTP-adres**: Gebruik het primaire SMTP-adres voor aanmelding bij Exchange, zoals `user1@contoso.com`.
- **Verificatiemethode**: kies hoe gebruikers worden geverifieerd bij de e-mailserver. Uw opties zijn:
  - **Certificaat**: Selecteer een SCEP- of PKCS-certificaatprofiel dat u eerder hebt gemaakt, voor verificatie van de Exchange-verbinding. Deze optie biedt de meest veilige en soepele ervaring voor uw gebruikers.
  - **Gebruikersnaam en wachtwoord**: gebruikers wordt gevraagd om hun gebruikersnaam en wachtwoord in te voeren.
  - **Afgeleide referentie**: gebruik een certificaat dat is afgeleid van de smartcard van een gebruiker. Zie [Afgeleide referenties gebruiken in Microsoft Intune](../protect/derived-credentials.md) voor meer informatie.

  >[!NOTE]
  > Meervoudige verificatie van Azure wordt niet ondersteund.
  
- **SSL**: U kunt deze optie **inschakelen** om SSL-communicatie (Secure Sockets Layer) te gebruiken wanneer u e-mailberichten verzendt, e-mailberichten ontvangt en communiceert met de Exchange-server.
- **OAuth**: Met **Inschakelen** gebruikt u OAuth-communicatie (Open Authorization) om e-mails te verzenden en te ontvangen en met Exchange te communiceren. Als uw OAuth-server verificatie van certificaten gebruikt, kiest u **Certificaat** als **Verificatiemethode** en voegt u het certificaat in het profiel in. Kies anders **Gebruikersnaam en wachtwoord** als **verificatiemethode**. Als u OAuth gebruikt, moet u:

  - Controleren of uw e-mailoplossing OAuth ondersteunt voordat u dit profiel naar uw gebruikers stuurt. Controleren of Office 365 Exchange online ondersteuning biedt voor OAuth. Mogelijk bieden on-premises Exchange en andere oplossingen van partners of derden geen ondersteuning voor OAuth. On-premises Exchange kan worden geconfigureerd voor Modern Authentication (zie de blogpost [Announcing Hybrid Modern Authentication for Exchange On-Premises](https://blogs.technet.microsoft.com/exchange/2017/12/06/announcing-hybrid-modern-authentication-for-exchange-on-premises/) (Aankondiging van Hybride moderne verificatie voor on-premises Exchange)).

    Als OAuth voor het e-mailprofiel wordt gebruikt en de e-mailservice hier geen ondersteuning voor biedt, wordt de optie **Wachtwoord opnieuw invoeren** gebroken weergegeven. Er gebeurt bijvoorbeeld niets wanneer de gebruiker de optie **Wachtwoord opnieuw invoeren** selecteert bij de apparaatinstellingen in Apple.

  - Wanneer OAuth is ingeschakeld, hebben eindgebruikers een andere ervaring bij het aanmelden voor e-mail door middel van moderne verificatie die ondersteuning biedt voor meervoudige verificatie (MFA). 

  - Sommige organisaties schakelen voor eindgebruikers de mogelijkheid uit om [via selfservice toegang te krijgen tot toepassingen](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-self-service-access). In dit scenario kunt u zich mogelijk niet aanmelden bij Modern Authentication totdat een beheerder de zakelijke app iOS Accounts maakt en gebruikers toegang geeft tot de app in Azure AD.

    De standaardactie is het toevoegen van een toepassing met behulp van de functie [Toegangsvenster voor toepassingen](https://docs.microsoft.com/azure/active-directory/user-help/active-directory-saas-access-panel-introduction) **App toevoegen**  **zonder goedkeuring van het bedrijf**. Raadpleeg [Gebruikers toewijzen aan toepassingen](https://docs.microsoft.com/azure/active-directory/manage-apps/ways-users-get-assigned-to-applications) voor meer informatie.

  > [!NOTE]
  > Wanneer u OAuth inschakelt, gebeurt het volgende:  
  > 1. Apparaten die al als doel zijn ingesteld, krijgen een nieuw profiel.
  > 2. Eindgebruikers wordt gevraagd hun referenties opnieuw in te voeren.

## <a name="exchange-activesync-profile-configuration"></a>Exchange ActiveSync-profielconfiguratie

> [!IMPORTANT]
> Als u deze instellingen configureert, wordt er een nieuw profiel geïmplementeerd op het apparaat, zelfs wanneer een bestaand e-mailprofiel is bijgewerkt en nu deze instellingen bevat. Gebruikers wordt gevraagd om het wachtwoord van hun Exchange ActiveSync-account in te voeren. Deze instellingen worden van kracht wanneer het wachtwoord is ingevoerd.

- **Exchange-gegevens om te synchroniseren**: wanneer u Exchange ActiveSync gebruikt, kiest u de Exchange-services die zijn gesynchroniseerd op het apparaat: Agenda, Contactpersonen, Herinneringen, Notities en E-mail. Uw opties zijn:
  - **Alle gegevens** (standaard): synchronisatie is ingeschakeld voor alle services.
  - **Alleen e-mail**: synchronisatie is alleen ingeschakeld voor E-mail. Synchronisatie is uitgeschakeld voor de andere services.
  - **Alleen agenda**: synchronisatie is alleen ingeschakeld voor Agenda. Synchronisatie is uitgeschakeld voor de andere services.
  - **Alleen Agenda en Contactpersonen**: synchronisatie is alleen ingeschakeld voor Agenda en Contactpersonen. Synchronisatie is uitgeschakeld voor de andere services.
  - **Alleen Contactpersonen**: synchronisatie is alleen ingeschakeld voor Contactpersonen. Synchronisatie is uitgeschakeld voor de andere services.

  Deze functie is van toepassing op:  
  - iOS 13.0 en hoger
  - iPadOS 13.0 en hoger

- **Gebruikers toestaan om synchronisatie-instellingen te wijzigen**: kies of gebruikers de Exchange ActiveSync-instellingen voor de Exchange-services op het apparaat kunnen wijzigen: Agenda, Contactpersonen, Herinneringen, Notities en E-mail. Uw opties zijn:

  - **Ja** (standaard): gebruikers kunnen het synchronisatiegedrag van alle services wijzigen. Als u **Ja** kiest, zijn wijzigingen in *alle* services toegestaan.
  - **Nee**: gebruikers kunnen niet voor alle services de synchronisatie-instellingen wijzigen. Als u **Nee** kiest, worden wijzigingen in *alle* services geblokkeerd.

  > [!TIP]
  > Als u de instelling voor **Exchange-gegevens om te synchroniseren** hebt geconfigureerd om alleen bepaalde services te synchroniseren, raden we u aan om **Nee** te selecteren voor deze instelling. Als u **Nee** kiest, kunnen gebruikers de Exchange-service die wordt gesynchroniseerd, niet wijzigen.

  Deze functie is van toepassing op:  
  - iOS 13.0 en hoger
  - iPadOS 13.0 en hoger

## <a name="exchange-activesync-email-settings"></a>Exchange ActiveSync-e-mailinstellingen

- **S/MIME**: S/MIME maakt gebruik van e-mailcertificaten die uw e-mailberichten extra beveiliging bieden door gebruik te maken van ondertekening, versleuteling en ontsleuteling. Wanneer u S/MIME bij een e-mailbericht gebruikt, bevestigt u de authenticiteit van de afzender en de integriteit en vertrouwelijkheid van het bericht.

  Uw opties zijn:

  - **S/MIME uitschakelen** (standaard): maakt geen gebruik van S/MIME-e-mailcertificaat voor het ondertekenen, versleutelen en ontsleutelen van e-mailberichten.
  - **S/MIME inschakelen**: Staat toe dat gebruikers e-mail ondertekenen en/of versleutelen in de systeemeigen iOS-/iPadOS-e-mailtoepassing. Voer ook in:

    - **S/MIME-handtekening ingeschakeld**: met **Uitschakelen** (standaard) kunnen gebruikers het bericht niet digitaal ondertekenen. **Inschakelen** staat gebruikers toe uitgaande e-mailberichten digitaal te laten ondertekenen voor het account dat u hebt ingevoerd. Ondertekening biedt gebruikers die berichten ontvangen de zekerheid dat het bericht afkomstig is van de specifieke afzender en niet van iemand die zich voordoet als de afzender.
      - **Gebruiker toestaan om instelling te wijzigen**: **Inschakelen** staat gebruikers toe om de opties voor ondertekenen te wijzigen. Met **Uitschakelen** (standaard) wordt voorkomen dat gebruikers de ondertekening wijzigen, en worden gebruikers gedwongen de ondertekening te gebruiken die u hebt geconfigureerd.
      - **Type ondertekeningscertificaat**: uw opties:
        - **Niet geconfigureerd**: Deze instelling wordt niet bijgewerkt of gewijzigd in Intune.
        - **Geen**: als beheerder kunt u geen specifiek certificaat afdwingen. Selecteer deze optie zodat gebruikers hun eigen certificaat kunnen kiezen.
        - **Afgeleide referentie**: gebruik een certificaat dat is afgeleid van de smartcard van een gebruiker. Zie [Afgeleide referenties gebruiken in Microsoft Intune](../protect/derived-credentials.md) voor meer informatie.
        - **Certificaten**: Selecteer een bestaand PKCS- of SCEP-certificaatprofiel dat wordt gebruikt voor het ondertekenen van e-mailberichten.
      - **Gebruiker toestaan om instelling te wijzigen**: **Inschakelen** staat gebruikers toe om het ondertekeningscertificaat te wijzigen. Met **Uitschakelen** (standaardinstelling) voorkomt u dat gebruikers het ondertekeningscertificaat wijzigen en dwingt u gebruikers het certificaat te gebruiken dat u hebt geconfigureerd.

        Deze functie is van toepassing op:  
        - iOS 12 en hoger
        - iPadOS 12 en hoger

    - **Standaard versleutelen**: Met **Inschakelen** worden alle berichten standaard versleuteld. Met **Uitschakelen** (standaardinstelling) worden alle berichten standaard niet versleuteld.
      - **Gebruiker toestaan de instelling te wijzigen**: **Inschakelen** staat gebruikers toe het standaardgedrag voor versleuteling te wijzigen. Met **Uitschakelen** voorkomt u dat gebruikers het standaardgedrag voor versleuteling wijzigen en dwingt u gebruikers de versleuteling te gebruiken die u hebt geconfigureerd.

        Deze functie is van toepassing op:  
        - iOS 12 en hoger
        - iPadOS 12 en hoger

    - **Versleuteling per bericht afdwingen**: Met Versleuteling per bericht kunnen gebruikers kiezen welke e-mailberichten worden versleuteld voordat ze worden verzonden.

      Kies **Inschakelen** om de optie Versleuteling per bericht weer te geven bij het maken van een nieuw e-mailbericht. Gebruikers kunnen vervolgens voor opt-in of opt-out kiezen ten aanzien van Versleuteling per bericht. Als de instelling **Standaard versleutelen** ook is ingeschakeld, kunnen gebruikers door Versleuteling per bericht in te schakelen ervoor kiezen om per bericht versleuteling uit te schakelen.

      Met **Uitschakelen** (standaardinstelling) wordt voorkomen dat de optie Versleuteling per bericht wordt weergegeven. Als de instelling **Standaard versleutelen** ook is uitgeschakeld, kunnen gebruikers door Versleuteling per bericht in te schakelen ervoor kiezen om per bericht versleuteling in te schakelen.

      - **Type versleutelingscertificaat**: uw opties:
        - **Niet geconfigureerd**: Deze instelling wordt niet bijgewerkt of gewijzigd in Intune.
        - **Geen**: als beheerder kunt u geen specifiek certificaat afdwingen. Selecteer deze optie zodat gebruikers hun eigen certificaat kunnen kiezen.
        - **Afgeleide referentie**: gebruik een certificaat dat is afgeleid van de smartcard van een gebruiker. Zie [Afgeleide referenties gebruiken in Microsoft Intune](../protect/derived-credentials.md) voor meer informatie.
        - **Certificaten**: Selecteer een bestaand PKCS- of SCEP-certificaatprofiel dat wordt gebruikt voor het ondertekenen van e-mailberichten.
      - **Gebruiker toestaan de instelling te wijzigen**: **Inschakelen** staat gebruikers toe om het versleutelingscertificaat te wijzigen. Met **Uitschakelen** (standaardinstelling) voorkomt u dat gebruikers het versleutelingscertificaat wijzigen en dwingt u gebruikers het certificaat te gebruiken dat u hebt geconfigureerd.

        Deze functie is van toepassing op:  
        - iOS 12 en hoger
        - iPadOS 12 en hoger

- **Aantal dagen e-mail voor synchronisatie**: Kies het aantal dagen waarvoor u e-mail wilt synchroniseren. Of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Toestaan dat berichten worden verplaatst naar andere e-mailaccounts**: Met **Inschakelen** (standaard) kunnen gebruikers e-mailberichten verplaatsen tussen de verschillende accounts die ze op hun apparaat hebben geconfigureerd.
- **Toestaan dat e-mail wordt verzonden vanuit toepassingen van derden**: Met **Inschakelen** (standaard) kunnen gebruikers dit profiel selecteren als standaardaccount voor het verzenden van e-mail. Hiermee staat u toe dat toepassingen van derden e-mails kunnen openen in de systeemeigen e-mail-app om er bijvoorbeeld bestanden als bijlage aan toe te voegen.
- **Recent gebruikte e-mailadressen synchroniseren**: Met **Inschakelen** (standaard) staat u gebruikers toe om de lijst met e-mailadressen te synchroniseren die onlangs zijn gebruikt op het apparaat met de server.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens kunt u [het profiel toewijzen](../device-profile-assign.md) en [de status ervan controleren](../device-profile-monitor.md).

Configureer e-mailinstellingen op apparaten met [Android](../email-settings-android.md), [Android Enterprise](../email-settings-android-enterprise.md), [Windows 10](email-settings-windows-10.md) en [Windows Phone 8.1](email-settings-windows-phone-8-1.md).
