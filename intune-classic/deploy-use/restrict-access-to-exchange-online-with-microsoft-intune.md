---
title: E-mail op Exchange Online beveiligen | Microsoft Docs
description: "Toegang tot bedrijfs-e‑mail op Exchange Online beschermen en controleren met voorwaardelijke toegang."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 09c82f5d-531c-474d-add6-784c83f96d93
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 742a989744a11dbc1c9e17a25b70388e06dd5ae7
ms.contentlocale: nl-nl
ms.lasthandoff: 05/31/2017


---


# <a name="protect-email-access-to-exchange-online-and-new-exchange-online-dedicated-with-intune"></a>De toegang tot e-mail beveiligen bij Exchange Online en het nieuwe Exchange Online Dedicated met Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

U kunt voorwaardelijke toegang voor Exchange Online of Exchange Online Dedicated configureren met behulp van Microsoft Intune. Zie het artikel [De toegang tot e-mail, O365 en andere services beveiligen](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) voor meer informatie over hoe voorwaardelijke toegang werkt.

> [!NOTE]
>Als u een Exchange Online Dedicated-omgeving hebt en wilt weten of deze de nieuwe of oudere configuratie heeft, neem dan contact op met uw accountmanager.

## <a name="before-you-begin"></a>Voordat u begint

Als u voorwaardelijke toegang wilt configureren, moet u:

-   Een **Office 365-abonnement hebben waarin Exchange Online (zoals E3) is inbegrepen**. Gebruikers moeten bovendien een licentie hebben voor Exchange Online.

- Een **EMS-abonnement (Enterprise Mobility + Security)** of een **Azure AD Premium-abonnement (Azure Active Directory)** hebben. Daarnaast moeten gebruikers een licentie hebben voor EMS of Azure AD. Zie de [Enterprise Mobility-pagina met prijzen](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) of de [Azure Active Directory-pagina met prijzen](https://azure.microsoft.com/pricing/details/active-directory/) voor meer informatie.

-  U kunt eventueel de optionele **Intune Service to Service Connector** configureren, waarmee u Intune koppelt aan Exchange Online en u apparaatgegevens kunt beheren via de Intune-console. U hoeft de connector niet te gebruiken om nalevingsbeleid of beleidsregels voor voorwaardelijke toegang te kunnen gebruiken, maar de connector is wel vereist voor het uitvoeren van rapporten die helpen bij het evalueren van de impact van voorwaardelijke toegang.
    -  Meer informatie over de [Intune-service-naar-serviceconnector](intune-service-to-service-exchange-connector.md).

   > [!NOTE]
   > Configureer de Intune-service-naar-serviceconnector niet als u voorwaardelijke toegang wilt gebruiken voor Exchange Online en Exchange On-Premises.

### <a name="device-compliance-requirements"></a>Apparaatcompatibiliteitsvereisten

Wanneer u beleid voor voorwaardelijke toegang configureert en dat toepast op een gebruiker, moet het volgende met het **apparaat** zijn gedaan voordat een gebruiker verbinding kan maken met diens e-mail:

-   Het apparaat moet een pc zijn die lid is van een domein of is **geregistreerd** zijn bij Intune.

-  Het apparaat moet zijn **geregistreerd bij Azure Active Directory**. Dit gebeurt automatisch wanneer het apparaat wordt geregistreerd bij Intune. Bovendien moet de client-id van Exchange ActiveSync zijn geregistreerd bij Azure Active Directory.

  De Azure Active Directory Device Registration Service wordt automatisch geactiveerd voor Intune- en Office 365-klanten. Klanten die de ADFS Device Registration Service al hebben geïmplementeerd, zien geen geregistreerde apparaten in on-premises Active Directory.

-   **Voldoen** aan het Intune-nalevingsbeleid dat is geïmplementeerd op het apparaat, of lid zijn van een domein dat is gekoppeld aan een lokaal domein.

### <a name="when-the-device-is-not-compliant"></a>Wanneer het apparaat niet compatibel is

Als niet is voldaan aan een beleid voor voorwaardelijke toegang, wordt het apparaat onmiddellijk in quarantaine geplaatst en ontvangen de gebruikers een e-mailbericht met een van de volgende quarantainemeldingen wanneer ze zich aanmelden:

- Als het apparaat niet is geregistreerd bij Intune of niet is geregistreerd bij Azure Active Directory, verschijnt er een bericht met instructies over het installeren van de bedrijfsportal-app, het registreren van het apparaat en het activeren van e-mail. Dit proces zorgt er ook voor dat de Exchange ActiveSync-id van het apparaat wordt gekoppeld aan het record in Azure Active Directory.

-   Als wordt vastgesteld dat het apparaat niet voldoet aan de regels van het nalevingsbeleid, wordt de gebruiker omgeleid naar de website of app van de Intune-bedrijfsportal. Hier vindt de gebruiker informatie over het probleem en aanwijzingen om dit op te lossen.

### <a name="how-conditional-access-works-with-exchange-online"></a>Hoe voorwaardelijke toegang werkt voor Exchange Online

Het volgende diagram illustreert de werkstroom die door beleid voor voorwaardelijke toegang wordt gevolgd voor Exchange Online.

![Het diagram illustreert de beslissingspunten die bepalen of een apparaat toegang mag hebben of moet worden geblokkeerd](../media/ConditionalAccess8-1.png)

## <a name="support-for-mobile-devices"></a>Ondersteuning voor mobiele apparaten
U kunt toegang tot e-mail van Exchange Online beveiligen vanuit **Outlook** en andere **apps waarbij gebruik wordt gemaakt van moderne verificatie**. Het volgende wordt ondersteund:

- Android 4.0 en hoger, Samsung Knox Standard 4.0 en hoger, en Android for Work
- iOS 8.0 en hoger

**Moderne verificatie** houdt aanmelding bij Microsoft Office-clients in op basis van Active Directory Authentication Library (ADAL).

-   Dankzij verificatie op basis van ADAL is voor Office-clients verificatie via een browser (ook wel passieve verificatie genoemd) mogelijk. Een gebruiker wordt hierbij naar een aanmeldingspagina geleid om de verificatie uit te voeren.
-   Deze nieuwe aanmeldingsmethode zorgt voor betere beveiliging, zoals **Multi-Factor Authentication** en **op certificaten gebaseerde verificatie**. Zie [Hoe moderne verificatie werkt](https://support.office.com/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517) voor meer informatie. U kunt ADFS-claimregels instellen om niet-moderne-verificatieprotocollen te blokkeren. Gedetailleerde instructies vindt u in [Scenario 3: alle toegang tot O365 blokkeren behalve op browser gebaseerde toepassingen](https://technet.microsoft.com/library/dn592182.aspx).

U kunt de toegang tot **Outlook Web Access (OWA)** via Exchange Online beveiligen wanneer een gebruiker deze service opent vanuit een browser op een **iOS**- of **Android**-apparaat. Toegang wordt alleen toegestaan vanaf ondersteunde browsers op compatibele apparaten:

* Safari (iOS)
* Chrome (Android)
* Intune Managed Browser (iOS, Android 5.0 en hoger)

   > [!IMPORTANT]
   > **Niet-ondersteunde browsers worden geblokkeerd**.

**De OWA-app voor iOS en Android kan zodanig worden aangepast dat er geen moderne verificatie wordt gebruikt, die dan ook niet wordt ondersteund. Toegang vanuit de OWA-app moet worden geblokkeerd met ADFS-claimregels.**


Op de volgende platformen kunt u toegang tot Exchange-e-mail beveiligen vanuit de ingebouwde **Exchange ActiveSync-e-mailclient**:

- Android 4.0 of hoger, Samsung Knox Standard 4.0 of hoger

- iOS 8.0 en hoger

- Windows Phone 8.1 en hoger

## <a name="support-for-pcs"></a>Ondersteuning voor pc's

U kunt voorwaardelijke toegang instellen voor pc's waarop Office-bureaubladtoepassingen worden uitgevoerd zodat deze toegang hebben tot **Exchange Online** en **SharePoint Online** als de pc's aan de volgende vereisten voldoen:

-   Op de pc moet Windows 7.0, Windows 8.1 of Windows 10 worden uitgevoerd.

  >[!NOTE]
  > Als u voorwaardelijke toegang met Windows 10-pc's wilt gebruiken, moet u deze pc's bijwerken met de Windows 10 Jubileumupdate.

  De pc moet lid zijn van een domein of voldoen aan de regels van het nalevingsbeleid.

  De pc moet zijn geregistreerd bij Intune en moet voldoen aan het beleid om te worden beschouwd als een apparaat dat het beleid naleeft.

  Voor pc's die lid zijn van een domein, moet u voorwaardelijke toegang zodanig instellen dat de pc's [automatisch worden geregistreerd](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/) bij Azure Active Directory.

  >[!NOTE]
    >Voorwaardelijke toegang wordt niet ondersteund op pc's waarop de Intune-computerclient wordt uitgevoerd.

-   [Moderne verificatie van Office 365-moet zijn ingeschakeld](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) en alle nieuwe Office-updates moeten zijn geïnstalleerd.

    Moderne verificatie houdt aanmelding bij Office 2013/Windows-clients in op basis van Active Directory Authentication Library (ADAL). Deze methode zorgt voor betere beveiliging, zoals **Multi-Factor Authentication** en **op certificaten gebaseerde verificatie**.

-   ADFS-claimregels worden ingesteld om niet-moderne-verificatieprotocollen te blokkeren. Gedetailleerde instructies vindt u in [Scenario 3: alle toegang tot O365 blokkeren behalve op browser gebaseerde toepassingen](https://technet.microsoft.com/library/dn592182.aspx).

## <a name="configure-conditional-access"></a>Voorwaardelijke toegang configureren
### <a name="step-1-configure-and-deploy-a-compliance-policy"></a>Stap 1: nalevingsbeleid configureren en implementeren
Zorg ervoor dat u nalevingsbeleid [maakt](create-a-device-compliance-policy-in-microsoft-intune.md) en [implementeert](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) voor de gebruikersgroepen die ook het beleid voor voorwaardelijke toegang krijgen.


> [!IMPORTANT]
> Als u geen nalevingsbeleid hebt geïmplementeerd, worden de apparaten beschouwd als apparaten die het beleid naleven en wordt toegang tot Exchange toegestaan.

### <a name="step-2-evaluate-the-effect-of-the-conditional-access-policy"></a>Stap 2: het effect van het beleid voor voorwaardelijke toegang beoordelen.
U kunt de **inventarisrapporten voor mobiele apparaten** gebruiken om de apparaten te identificeren waarvoor de toegang tot Exchange mogelijk wordt geblokkeerd nadat u het beleid voor voorwaardelijke toegang hebt geconfigureerd.

Configureer hiervoor een verbinding tussen Intune en Exchange met behulp van de [Microsoft Intune Service to Service Connector](intune-service-to-service-exchange-connector.md).
1.  Ga naar **Rapporten** > **Inventarisrapporten voor mobiele apparaten**.
![Schermafbeelding van de pagina Inventarisrapporten voor mobiele apparaten](../media/IntuneSA2bMobileDeviceInventoryReport.png)

2.  Selecteer in de rapportparameters de Intune-groep die u wilt beoordelen en, indien nodig, de apparaatplatformen waarop het beleid wordt toegepast.
3.  Nadat u de criteria hebt geselecteerd die voldoen aan de behoeften van uw organisatie, kiest u **Rapport weergeven**.
De Rapportviewer wordt geopend in een nieuw venster.
![Schermafbeelding van een voorbeeld van een inventarisrapport voor mobiele apparaten](../media/IntuneSA2cViewReport.PNG)

Nadat u het rapport hebt uitgevoerd, controleert u deze vier kolommen om te bepalen of een gebruiker wordt geblokkeerd:

-   **Beheerkanaal**: geeft aan of het apparaat wordt beheerd door Intune, Exchange ActiveSync of beide.

-   **Geregistreerd bij AAD**: geeft aan of het apparaat is geregistreerd bij Azure Active Directory (ook wel 'toegevoegd aan werkplek' genoemd).

-   **Compatibel**: geeft aan of het apparaat voldoet aan alle nalevingsbeleidsregels die u hebt geïmplementeerd.

-   **Exchange ActiveSync-id**: op iOS- en Android-apparaten moet de Exchange ActiveSync-id zijn gekoppeld aan de apparaatregistratierecord in Azure Active Directory. Dit gebeurt wanneer een gebruiker in de e-mail met betrekking tot de quarantaine op de koppeling **E-mail activeren** klikt.

    > [!NOTE]
    > Op Windows Phone-apparaten wordt altijd een waarde weergegeven in deze kolom.

Apparaten die deel uitmaken van een doelgroep, krijgen geen toegang tot Exchange tenzij de kolomwaarden overeenkomen met de waarden die in de volgende tabel worden weergegeven:

--------------------------
|Beheerkanaal|AAD-geregistreerd|Compliant|Exchange ActiveSync-id|Resulterende actie|
|----------------------|------------------|-------------|--------------------------|--------------------|
|**Beheerd door Microsoft Intune en Exchange ActiveSync**|Ja|Ja|Een waarde wordt weergegeven|Toegang tot e-mail is toegestaan|
|Een andere waarde|Nee|Nee|Er wordt geen waarde weergegeven|Toegang tot e-mail is geblokkeerd|
----------------------
U kunt de inhoud van het rapport exporteren en de kolom **E-mailadres** gebruiken om uw gebruikers ervan op de hoogte te stellen dat toegang voor hen wordt geblokkeerd.

### <a name="step-3-configure-user-groups-for-the-conditional-access-policy"></a>Stap 3: gebruikersgroepen configureren voor het beleid voor voorwaardelijke toegang.
Beleid voor voorwaardelijke toegang is gericht op andere Azure Active Directory-beveiligingsgroepen met gebruikers. U kunt ook bepaalde gebruikersgroepen van beleid voor voorwaardelijke toegang uitsluiten. Wanneer een gebruiker deel uitmaakt van de doelgroep voor het beleid, moet elk apparaat dat wordt gebruikt, compatibel zijn om toegang te kunnen krijgen tot e-mail.

U kunt deze groepen configureren in het **Office 365-beheercentrum** of in de **Intune-accountportal**.

U kunt twee soorten groepen opgeven in elk beleid:

-   **Doelgroepen**: gebruikersgroepen waarop het beleid wordt toegepast.

-   **Uitgesloten groepen**: gebruikersgroepen waarop het beleid niet van toepassing is (optioneel).

Als een gebruiker zich in beide groepen bevindt, wordt het beleid niet op de gebruiker toegepast.

Alleen de doelgroepen van het voorwaardelijk toegangsbeleid worden beoordeeld.

### <a name="step-4-configure-the-conditional-access-policy"></a>Stap 4: het beleid voor voorwaardelijke toegang configureren

>[!NOTE]
> U kunt ook een beleid voor voorwaardelijke toegang maken in de Azure AD-beheerconsole. Met de Azure AD-beheerconsole kunt u beleid voor voorwaardelijke toegang voor een Intune-apparaat maken (aangeduid als het **op apparaten gebaseerd beleid voor voorwaardelijke toegang** in Azure AD), naast ander beleid voor voorwaardelijke toegang zoals Multi-Factor Authentication.

>U kunt ook beleid voor voorwaardelijke toegang instellen voor bedrijfs-apps van derden die door Azure AD worden ondersteund, zoals voor Salesforce en Box. Zie voor meer informatie [How to set Azure Active Directory device-based conditional access policy for access control to Azure Active Directory connected applications](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/) (Het instellen van het op apparaten gebaseerde beleid voor voorwaardelijke toegang tot toepassingen die zijn verbonden met Azure Active Directory).


1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) achtereenvolgens **Beleid** > **Voorwaardelijke toegang** > **Beleid voor Exchange Online**.

2.  Kies op de pagina **Exchange Online-beleid** de optie **Enable conditional access policy for Exchange Online**(Beleid voor voorwaardelijke toegang inschakelen voor Exchange Online).

    > [!NOTE]
    > Als u geen nalevingsbeleid hebt geïmplementeerd, worden apparaten beschouwd als apparaten die het beleid naleven.
    >
    > Ongeacht de nalevingsstatus moeten alle gebruikers waarop het beleid van toepassing is hun apparaten registreren bij Intune.

3.  Onder **Toegang voor toepassingen** zijn er, voor apps die moderne verificatie gebruiken, twee manieren om te kiezen op welke platforms het beleid moet worden toegepast. Ondersteunde platforms zijn Android, iOS, Windows en Windows Phone.

    -   **Alle platforms**

        Hiervoor is vereist dat alle apparaten die worden gebruikt om toegang te krijgen tot **SharePoint Online**, moeten worden ingeschreven in Intune en aan het nalevingsbeleid moeten voldoen. Elke clienttoepassing die **moderne verificatie** gebruikt, is onderworpen aan beleid voor voorwaardelijke toegang. Als het platform momenteel niet wordt ondersteund door Intune, wordt toegang tot **Exchange Online** geblokkeerd.

        Als u **Alle platformen** selecteert, betekent dat dit beleid met Azure Active Directory wordt toegepast op alle verificatieaanvragen, ongeacht het platform dat wordt gerapporteerd door de clienttoepassing. Alle platformen moeten worden geregistreerd en voldoen aan de voorwaarden, met uitzondering van:
        *    Windows-apparaten moeten worden ingeschreven, voldoen aan het beleid en lid zijn van een domein met om-premises Active Directory, of beide.
        * Niet-ondersteunde platformen, zoals Mac OS. Apps met moderne verificatie die afkomstig zijn van deze platformen, worden wel nog geblokkeerd.

    -   **Specifieke platformen**

         Het beleid voor voorwaardelijke toegang wordt toegepast op elke clienttoepassing die **moderne verificatie** gebruikt op de door u geselecteerde apparaatplatformen.

4. Onder **Outlook Web Access (OWA)** kunt u ervoor kiezen om toegang tot Exchange Online alleen toe te staan via de ondersteunde browsers: Safari (iOS) en Chrome (Android). Toegang vanaf andere browsers wordt geblokkeerd. De platformbeperkingen die u hebt geselecteerd voor toegang tot Outlook zijn hier ook van toepassing.

  Op **Android**-apparaten moeten gebruikers browsertoegang inschakelen. Om dit te doen, moeten gebruikers de optie **Browsertoegang inschakelen** als volgt inschakelen op geregistreerde apparaten:
  1.    Open de **Bedrijfsportal-app**.
  2.    Ga naar de pagina **Instellingen** via de beletseltekens (...) of via de menuknop Hardware.
  3.    Selecteer **Browsertoegang inschakelen**.
  4.    In de browser Chrome meldt u zich af bij Office 365. Start vervolgens Chrome opnieuw op.

  Op **iOS**- en **Android**-platformen genereert Azure Active Directory een TLS-certificaat (Transport Layer Security) voor het apparaat om te bepalen welk apparaat wordt gebruikt om de service te openen. Op het apparaat wordt het certificaat met een prompt weergegeven aan de gebruiker; deze kan het certificaat dan selecteren zoals in de volgende schermafbeeldingen wordt weergegeven. De gebruiker moet dit certificaat selecteren om de browser te kunnen blijven gebruiken.

  **iOS**

  ![Schermafbeelding van de certificaatprompt op een ipad](../media/mdm-browser-ca-ios-cert-prompt.png)

  **Android**

  ![schermopname van het certificaatprompt op een Android-apparaat](../media/mdm-browser-ca-android-cert-prompt.png)

5.  Onder **Exchange ActiveSync-apps** kunt u de toegang tot Exchange Online blokkeren van apparaten die niet aan het nalevingsbeleid voldoen. U kunt ook aangeven of u toegang tot e-mail wilt toestaan of blokkeren wanneer het apparaat niet op een ondersteund platform wordt uitgevoerd. Ondersteunde platformen zijn Android, iOS, Windows en Windows Phone.

 Exchange Active Sync-apps op **Android for Work**-apparaten:
 -  Alleen de apps **Gmail** en **Nine Work** in het **werkprofiel** worden ondersteund op Android for Work-apparaten. Voorwaardelijke toegang werkt alleen op Android for Work-apparaten als u een e-mailprofiel voor de app Gmail of Nine Work implementeert en de installatie daarvan **verplicht** stelt.

6.  Onder **Doelgroepen** selecteert u de Active Directory-beveiligingsgebruikersgroepen waarop het beleid van toepassing moet zijn. U kunt kiezen of u zich wilt richten op alle gebruikers of op een geselecteerde lijst met gebruikersgroepen.
![Schermafbeelding van de pagina met het beleid voor voorwaardelijke toegang van Exchange Online met opties voor doelgroepen en uitgesloten groepen](../media/IntuneSA5eTargetedExemptedGroups.PNG)
    > [!NOTE]
    > Voor gebruikers in **Doelgroepen** wordt het Intune-beleid vervangen door Exchange-regels en -beleid.
    >
    > Door Exchange worden alleen in de volgende gevallen de in Exchange gedefinieerde regels voor toestaan, blokkeren en in quarantaine plaatsen en Exchange-beleid afgedwongen:
    >
    > -   Een gebruiker heeft geen licentie voor Intune.
    > -   Een gebruiker heeft een licentie voor Intune, maar de gebruiker behoort niet tot een beveiligingsgroep die is gedefinieerd in het beleid voor voorwaardelijke toegang.

6.  Onder **Uitgesloten groepen**selecteert u de Active Directory-beveiligingsgebruikersgroepen waarop dit beleid niet van toepassing is. Als een gebruiker deel uitmaakt van beide groepen, wordt het beleid niet op de gebruiker toegepast.

7.  Als u klaar bent, kiest u **Opslaan**.

-   U hoeft het beleid voor voorwaardelijke toegang niet te implementeren. Het wordt direct van kracht.

-   Wanneer een gebruiker een e-mailaccount maakt, wordt het apparaat onmiddellijk geblokkeerd.

-   Als een geblokkeerde gebruiker het apparaat registreert bij Intune en alle eventuele problemen met het niet-naleven van beleid oplost, wordt de toegangsblokkade voor e-mail binnen twee minuten opgeheven.

-   Als de gebruiker het apparaat uitschrijft, wordt de toegang tot e-mail na circa zes uur geblokkeerd.

Raadpleeg [Voorbeeldscenario's voor het beveiligen van toegang tot e-mail](restrict-email-access-example-scenarios.md) voor enkele **scenario's met voorbeelden van het configureren van beleid voor voorwaardelijke toegang om de toegang van apparaten te beveiligen**.

## <a name="monitor-the-compliance-and-conditional-access-policies"></a>De compatibiliteit en het beleid voor voorwaardelijke toegang bewaken

#### <a name="to-view-devices-that-are-blocked-from-exchange"></a>Apparaten weergeven die geen toegang hebben tot Exchange

In het Intune-dashboard kiest u de tegel **Apparaten geblokkeerd voor gebruik in Exchange** om het aantal geblokkeerde apparaten en koppelingen naar meer informatie weer te geven.
![Schermafdruk van het Intune-dashboard met het aantal apparaten waarvoor de toegang tot Exchange is geblokkeerd](../media/IntuneSA6BlockedDevices.PNG)

## <a name="next-steps"></a>Volgende stappen
- [Toegang tot SharePoint Online beveiligen](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

- [Toegang tot Skype voor Bedrijven Online beveiligen](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)

