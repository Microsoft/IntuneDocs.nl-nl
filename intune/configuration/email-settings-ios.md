---
title: E-mailinstellingen voor iOS-apparaten configureren in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een lijst van alle e-mailinstellingen die u kunt configureren en aan iOS-apparaten kunt toevoegen in Microsoft Intune, waaronder Exchange-servers gebruiken en kenmerken ophalen uit Azure Active Directory. U kunt tevens SSL inschakelen, gebruikers verifiëren met certificaten of gebruikersnaam/wachtwoord, en e-mail synchroniseren op iOS-apparaten met behulp van apparaatconfiguratieprofielen in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/12/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 73de0ac94ff02e43fe73ca6357f6008ba71e3b93
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390824"
---
# <a name="add-e-mail-settings-for-ios-devices-in-microsoft-intune"></a>E-mailinstellingen voor iOS-apparaten toevoegen in Microsoft Intune

In Microsoft Intune kunt u e-mail zo maken en configureren dat deze verbinding maakt met een e-mailserver of de wijze van verificatie kiest voor gebruikers, S/MIME gebruikt voor versleuteling, enzovoort.

In dit artikel worden alle e-mailinstellingen vermeld en beschreven, die beschikbaar zijn voor iOS-apparaten. U kunt een apparaatconfiguratieprofiel maken om deze e-mailinstellingen naar/op uw iOS-apparaten pushen/implementeren.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](../email-settings-configure.md).

> [!NOTE]
> Deze instellingen zijn beschikbaar voor alle inschrijvings typen. Zie [IOS-inschrijving](../ios-enroll.md)voor meer informatie over de inschrijvings typen.

## <a name="exchange-activesync-account-settings"></a>Exchange ActiveSync-account instellingen

- **E-mailserver**: voer de hostnaam in van uw Exchange-server.
- **Accountnaam**: voer de weergavenaam in voor het e-mailaccount. Deze naam zien gebruikers op hun apparaat.
- **Het kenmerk gebruikersnaam van AAD**: deze naam is het kenmerk dat Intune uit Azure Active Directory (AAD) ophaalt. In Intune wordt de gebruikersnaam die wordt gebruikt door dit profiel dynamisch gegenereerd. Uw opties zijn:
  - **User Principal Name**: hiermee wordt de naam opgehaald, zoals `user1` of `user1@contoso.com`
  - **Primair SMTP-adres**: haalt de naam op in de indeling van het e-mailadres, zoals `user1@contoso.com`
  - **sAM-accountnaam**: hiervoor is het domein vereist, zoals `domain\user1`. Voer ook in:  
    - **Bron van gebruikersdomeinnaam**: kies **AAD** (Azure Active Directory) of **Aangepast**.
      - **Aad**: Haal de kenmerken op uit Azure AD. Voer ook in:
        - **Kenmerk voor gebruikersdomeinnaam van AAD**: kies de optie om de **volledige domeinnaam** (`contoso.com`) of het kenmerk **NetBIOS-naam** (`contoso`) van de gebruiker op te halen.

      - **Aangepast**: Haal de kenmerken op uit een aangepaste domein naam. Voer ook in:
        - **Te gebruiken aangepaste domeinnaam**: voer een waarde in die Intune voor de domeinnaam gebruikt, zoals `contoso.com` of `contoso`.

- **Kenmerk van het e-mailadres van AAD**: kies op welke manier het e-mailadres voor de gebruiker wordt gegenereerd. Uw opties zijn:
  - **User principal name**: gebruik de volledige principal name, zoals `user1@contoso.com` of `user1`, als het e-mailadres.
  - **Primair SMTP-adres**: gebruik het primaire SMTP-adres om bij Exchange aan te melden, zoals `user1@contoso.com`.
- **Verificatie methode**: Kies hoe gebruikers moeten worden geverifieerd bij de e-mail server. Uw opties zijn:
  - **Certificaat**: selecteer een SCEP- of PKCS-certificaatprofiel dat u eerder hebt gemaakt voor verificatie van de Exchange-verbinding. Deze optie biedt de meest veilige en naadloze ervaring voor uw gebruikers.
  - **Gebruikers naam en wacht woord**: gebruikers wordt gevraagd om de gebruikers namen en wacht woorden in te voeren.
  - **Afgeleide referentie**: gebruik een certificaat dat is afgeleid van de Smart Card van een gebruiker. Zie [afgeleide referenties gebruiken in Microsoft intune](../protect/derived-credentials.md)voor meer informatie.

  >[!NOTE]
  > Meervoudige verificatie van Azure wordt niet ondersteund.
  
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

## <a name="exchange-activesync-profile-configuration"></a>Configuratie van Exchange ActiveSync-profiel

> [!IMPORTANT]
> Door deze instellingen te configureren, wordt een nieuw profiel geïmplementeerd op het apparaat, zelfs wanneer een bestaand e-mail profiel wordt bijgewerkt met deze instellingen. Gebruikers wordt gevraagd hun Exchange ActiveSync-account wachtwoord in te voeren. Deze instellingen zijn van invloed op het moment dat het wacht woord wordt ingevoerd.

- **Exchange-gegevens die moeten worden gesynchroniseerd**: als u Exchange ActiveSync gebruikt, kiest u de Exchange-services die zijn gesynchroniseerd op het apparaat: agenda, contact personen, herinneringen, notities en e-mail adres. Uw opties zijn:
  - **Alle gegevens** (standaard): synchronisatie is ingeschakeld voor alle services.
  - **Alleen e-mail**: synchronisatie is alleen ingeschakeld voor e-mail. Synchronisatie is uitgeschakeld voor de andere services.
  - **Alleen agenda**: synchronisatie is alleen ingeschakeld voor kalender. Synchronisatie is uitgeschakeld voor de andere services.
  - **Alleen agenda en contact personen**: synchronisatie is alleen ingeschakeld voor agenda en contact personen. Synchronisatie is uitgeschakeld voor de andere services.
  - **Alleen contact personen**: synchronisatie is alleen ingeschakeld voor contact personen. Synchronisatie is uitgeschakeld voor de andere services.

  Deze functie is van toepassing op:  
  - iOS 13.0 en hoger
  - iPadOS 13.0 en hoger

- **Gebruikers toestaan om synchronisatie-instellingen te wijzigen**: Kies of gebruikers de Exchange ActiveSync-instellingen voor de Exchange-services op het apparaat kunnen wijzigen: agenda, contact personen, herinneringen, notities en e-mail. Uw opties zijn:

  - **Ja** (standaard instelling): gebruikers kunnen het synchronisatie gedrag van alle services wijzigen. Als u **Ja** kiest, worden wijzigingen aan *alle* Services toegestaan.
  - **Nee**: gebruikers kunnen de synchronisatie-instellingen van alle services niet wijzigen. Als u geen blokken selecteert, worden *alle* Services **niet** gewijzigd.

  > [!TIP]
  > Als u de instelling voor het **synchroniseren van Exchange-gegevens** hebt geconfigureerd om alleen bepaalde services te synchroniseren, raden we u aan om **Nee** te selecteren voor deze instelling. Als u Nee kiest, kunnen gebruikers de Exchange-service die is gesynchroniseerd **niet** wijzigen.

  Deze functie is van toepassing op:  
  - iOS 13.0 en hoger
  - iPadOS 13.0 en hoger

## <a name="exchange-activesync-email-settings"></a>E-mail instellingen voor Exchange ActiveSync

- **S/MIME**: s/MIME maakt gebruik van e-mail certificaten die extra beveiliging bieden voor uw e-mail communicatie door te ondertekenen, versleutelen en ontsleutelen. Wanneer u S/MIME bij een e-mailbericht gebruikt, bevestigt u de authenticiteit van de afzender en de integriteit en vertrouwelijkheid van het bericht.

  Uw opties zijn:

  - **S/MIME uitschakelen** (standaard): maakt geen gebruik van een s/MIME-e-mail certificaat voor het ondertekenen, versleutelen of ontsleutelen van e-mail berichten.
  - **S/MIME inschakelen**: staat toe dat gebruikers zich aanmelden en/of e-mail kunnen versleutelen in de systeemeigen iOS-e-mailtoepassing. Voer ook in:

    - **S/MIME-ondertekening ingeschakeld**: **uitschakelen** (standaard) Hiermee kunnen gebruikers het bericht niet digitaal ondertekenen. **Inschakelen** staat gebruikers toe uitgaande e-mailberichten digitaal te laten ondertekenen voor het account dat u hebt ingevoerd. Ondertekening biedt gebruikers die berichten ontvangen de zekerheid dat het bericht afkomstig is van de specifieke afzender en niet van iemand die zich voordoet als de afzender.
      - **Gebruiker toestaan instelling te wijzigen**: als u deze optie **inschakelt** , kunnen gebruikers de Onderteken opties wijzigen. Als u deze **optie uitschakelt** , kunnen gebruikers de ondertekening niet wijzigen en kunnen gebruikers de door u geconfigureerde ondertekening gebruiken.
      - **Type handtekening certificaat**: uw opties:
        - **Niet geconfigureerd**: deze instelling wordt niet bijgewerkt of gewijzigd door intune.
        - **Geen**: als beheerder kunt u geen specifiek certificaat afdwingen. Selecteer deze optie zodat gebruikers hun eigen certificaat kunnen kiezen.
        - **Afgeleide referentie**: gebruik een certificaat dat is afgeleid van de Smart Card van een gebruiker. Zie [afgeleide referenties gebruiken in Microsoft intune](../protect/derived-credentials.md)voor meer informatie.
        - **Certificaten**: selecteer een bestaand PKCS- of SCEP-certificaatprofiel dat wordt gebruikt voor het ondertekenen van e-mailberichten.
      - **Gebruiker toestaan instelling te wijzigen**: als u deze **optie inschakelt** , kunnen gebruikers het handtekening certificaat wijzigen. Met **Uitschakelen** (standaardinstelling) voorkomt u dat gebruikers het ondertekeningscertificaat wijzigen en dwingt u gebruikers het certificaat te gebruiken dat u hebt geconfigureerd.

        Deze functie is van toepassing op:  
        - iOS 12 en hoger
        - iPadOS 12 en hoger

    - **Standaard versleutelen**: met **Inschakelen** worden alle berichten standaard versleuteld. Met **Uitschakelen** (standaardinstelling) worden alle berichten standaard niet versleuteld.
      - **Gebruiker toestaan om instelling te wijzigen**: **Inschakelen** geeft gebruikers toestemming om het standaardgedrag voor versleuteling te wijzigen. Met **Uitschakelen** voorkomt u dat gebruikers het standaardgedrag voor versleuteling wijzigen en dwingt u gebruikers de versleuteling te gebruiken die u hebt geconfigureerd.

        Deze functie is van toepassing op:  
        - iOS 12 en hoger
        - iPadOS 12 en hoger

    - **Versleuteling per bericht afdwingen**: met Versleuteling per bericht kunnen gebruikers kiezen welke e-mailberichten worden versleuteld voordat ze worden verzonden.

      Kies **Inschakelen** om de optie Versleuteling per bericht weer te geven bij het maken van een nieuw e-mailbericht. Gebruikers kunnen vervolgens voor opt-in of opt-out kiezen ten aanzien van Versleuteling per bericht. Als de instelling **Standaard versleutelen** ook is ingeschakeld, kunnen gebruikers door Versleuteling per bericht in te schakelen ervoor kiezen om per bericht versleuteling uit te schakelen.

      Met **Uitschakelen** (standaardinstelling) wordt voorkomen dat de optie Versleuteling per bericht wordt weergegeven. Als de instelling **Standaard versleutelen** ook is uitgeschakeld, kunnen gebruikers door Versleuteling per bericht in te schakelen ervoor kiezen om per bericht versleuteling in te schakelen.

      - **Type versleutelings certificaat**: uw opties:
        - **Niet geconfigureerd**: deze instelling wordt niet bijgewerkt of gewijzigd door intune.
        - **Geen**: als beheerder kunt u geen specifiek certificaat afdwingen. Selecteer deze optie zodat gebruikers hun eigen certificaat kunnen kiezen.
        - **Afgeleide referentie**: gebruik een certificaat dat is afgeleid van de Smart Card van een gebruiker. Zie [afgeleide referenties gebruiken in Microsoft intune](../protect/derived-credentials.md)voor meer informatie.
        - **Certificaten**: selecteer een bestaand PKCS- of SCEP-certificaatprofiel dat wordt gebruikt voor het ondertekenen van e-mailberichten.
      - **Gebruiker toestaan om instelling te wijzigen**: kies **Inschakelen** om gebruikers toe te staan het versleutelingscertificaat te wijzigen. Met **Uitschakelen** (standaardinstelling) voorkomt u dat gebruikers het versleutelingscertificaat wijzigen en dwingt u gebruikers het certificaat te gebruiken dat u hebt geconfigureerd.

        Deze functie is van toepassing op:  
        - iOS 12 en hoger
        - iPadOS 12 en hoger

- **Aantal dagen e-mail voor synchronisatie**: kies het aantal dagen waarvoor u e-mail wilt synchroniseren. Of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.
- **Toestaan dat berichten worden verplaatst naar andere e-mailaccounts**: u kunt deze optie **inschakelen** (standaardinstelling) om toe te staan dat gebruikers e-mailberichten verplaatsen naar andere accounts die gebruikers op hun apparaat hebben geconfigureerd.
- **Toestaan dat e-mails worden verzonden vanuit toepassingen van derden**: met **Inschakelen** (standaardinstelling) kunnen gebruikers dit profiel als standaardaccount voor het verzenden van e-mail selecteren. Hiermee staat u toe dat toepassingen van derden e-mails kunnen openen in de systeemeigen e-mail-app om er bijvoorbeeld bestanden als bijlage aan toe te voegen.
- **Recent gebruikte e-mailadressen synchroniseren**: u kunt deze optie **inschakelen** (standaardinstelling) om toe te staan dat gebruikers de lijst synchroniseren met e-mailadressen die onlangs zijn gebruikt op het apparaat met de server.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens kunt u [het profiel toewijzen](../device-profile-assign.md) en [de status ervan controleren](../device-profile-monitor.md).

E-mail instellingen configureren voor [Android](../email-settings-android.md)-, [Android Enter prise](../email-settings-android-enterprise.md)-, [Windows 10](email-settings-windows-10.md)-en [Windows Phone 8,1](email-settings-windows-phone-8-1.md) -apparaten.
