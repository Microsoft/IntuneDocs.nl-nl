---
title: SharePoint Online beveiligen | Microsoft Docs
description: U kunt voorwaardelijke toegang gebruiken om bedrijfsgegevens te beschermen en te beheren op SharePoint Online.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 33febef8787887401960592d95356347f6917681
ms.openlocfilehash: 4a8b3f5a3ab5df9f31741e3331d2b6bbfd2c0c9f
ms.contentlocale: nl-nl
ms.lasthandoff: 05/04/2017


---

# <a name="protect-access-to-sharepoint-online-with-microsoft-intune"></a>Toegang tot SharePoint Online beveiligen met Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Gebruik de voorwaardelijke toegang van Microsoft Intune om de toegang tot bestanden op SharePoint Online te beheren.
Voorwaardelijke toegang bestaat uit twee onderdelen:
- Een nalevingsbeleid voor apparaten waaraan het apparaat moet voldoen om te worden beschouwd als een apparaat dat het beleid naleeft.
- Een beleid voor voorwaardelijke toegang waarin u de voorwaarden opgeeft waaraan het apparaat moet voldoen om toegang tot de service te krijgen.
Zie het onderwerp [De toegang tot e-mail, O365 en andere services beveiligen](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) voor meer informatie over hoe voorwaardelijke toegang werkt.

U implementeert het beleid voor naleving en voorwaardelijke toegang voor gebruikers. Een apparaat dat een gebruiker gebruikt voor toegang tot de services, wordt gecontroleerd op naleving van het beleid.

Wanneer een gebruiker probeert verbinding te maken met een bestand via een ondersteunde app, zoals OneDrive, op zijn of haar apparaat, wordt de volgende evaluatie uitgevoerd:

![Diagram dat de beslissingspunten aangeeft die bepalen of een apparaat toegang tot SharePoint heeft of wordt geblokkeerd](../media/ConditionalAccess8-6.png)


**Voordat** u beleid voor voorwaardelijke toegang configureert voor SharePoint Online, moet u:
- Een **SharePoint Online-abonnement** hebben. Gebruikers moeten bovendien een licentie voor SharePoint Online hebben.
- Een **EMS-abonnement (Enterprise Mobility + Security)** of een **Azure AD Premium-abonnement (Azure Active Directory)** hebben. Daarnaast moeten gebruikers een licentie hebben voor EMS of Azure AD. Zie de [Enterprise Mobility-pagina met prijzen](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) of de [Azure Active Directory-pagina met prijzen](https://azure.microsoft.com/pricing/details/active-directory/) voor meer informatie.


  Als u verbinding met de vereiste bestanden wilt maken, moet het apparaat voldoen aan de volgende voorwaarden:
-   Het apparaat moet **geregistreerd** zijn bij Intune of moet een pc zijn die lid is van een domein.

-   Het apparaat moet zijn **geregistreerd** bij Azure Active Directory (dit gebeurt automatisch wanneer het apparaat wordt geregistreerd bij Intune).


-   Het apparaat moet **voldoen** aan het geïmplementeerde Intune-nalevingsbeleid.

De apparaatstatus wordt opgeslagen in Azure Active Directory, die toegang tot de bestanden verleent of blokkeert op basis van de opgegeven voorwaarden.

Als niet aan een voorwaarde wordt voldaan, krijgt de gebruiker een van de volgende berichten te zien tijdens het aanmelden:

-   Als het apparaat niet is geregistreerd bij Intune of niet is geregistreerd bij Azure Active Directory, wordt er een bericht weergegeven met instructies voor het installeren van de bedrijfsportal-app en het registreren van het apparaat.

-   Als het apparaat niet aan het beleid voldoet, wordt er een bericht weergegeven waarin de gebruiker naar de website van de Intune-bedrijfsportal wordt verwezen. Hier staat informatie over het probleem en aanwijzingen voor het oplossen ervan.

**Voorwaardelijke toegang is niet van toepassing op extern delen**. Zie [Extern delen voor uw SharePoint Online-omgeving beheren](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) om te lezen hoe u extern delen in uw tenant of siteverzameling kunt voorkomen.

>[!NOTE]
>Als u voorwaardelijke toegang voor SharePoint Online inschakelt, raden wij aan het domein in de lijst uit te schakelen zoals staat beschreven in het onderwerp [Remove-SPOTenantSyncClientRestriction](https://technet.microsoft.com/library/dn917451.aspx).  

## <a name="support-for-mobile-devices"></a>Ondersteuning voor mobiele apparaten
Het volgende wordt ondersteund:
- iOS 8.0 en hoger
- Android 4.0 en hoger, Samsung Knox Standard 4.0 en hoger
- Windows Phone 8.1 en hoger

U kunt de toegang tot SharePoint Online beveiligen wanneer **iOS**- en **Android**-apparaten zich via een browser toegang tot de service verschaffen. Toegang wordt alleen toegestaan vanaf ondersteunde browsers op compatibele apparaten:
* Safari (iOS)
* Chrome (Android)
* Intune Managed Browser (iOS en Android 5.0 en hoger)

**Niet-ondersteunde browsers worden geblokkeerd**.

## <a name="support-for-pcs"></a>Ondersteuning voor pc's
Het volgende wordt ondersteund:
- Windows 8.1 en hoger (mits geregistreerd bij Intune)
- Windows 7.0, Windows 8.1 of Windows 10 (mits lid van een domein)
> [!NOTE]
>Als u voorwaardelijke toegang met Windows 10-pc's wilt gebruiken, moet u deze pc's bijwerken met de Windows 10 Jubileumupdate.

  - U moet pc's die deel uitmaken van een domein, zodanig instellen dat ze [automatisch worden geregistreerd](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/) bij Azure Active Directory. De Azure AD Device Registration Service wordt automatisch geactiveerd voor Intune- en Office 365-klanten. Klanten die de ADFS Device Registration Service al hebben geïmplementeerd, zien geen geregistreerde apparaten in on-premises Active Directory.

  - Als het beleid zo is ingesteld dat de pc lid moet zijn van een domein en de pc geen lid is van een domein, wordt in een bericht weergegeven dat er contact moet worden opgenomen met de IT-beheerder.

  - Als het beleid zodanig is ingesteld dat de pc lid moet zijn van een domein of aan het beleid moet voldoen en de pc niet aan één of beide vereisten voldoet, wordt er een bericht weergegeven met instructies voor het installeren van de bedrijfsportal-app en het registreren van de pc.
  >[!NOTE]
  >Voorwaardelijke toegang wordt niet ondersteund op computers waarop de Intune-computerclient wordt uitgevoerd.

[Moderne verificatie van Office 365-moet zijn ingeschakeld](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) en alle nieuwe Office-updates moeten zijn geïnstalleerd.

Moderne verificatie maakt aanmelding op basis van Active Directory Authentication Library (ADAL) beschikbaar op Windows-clients met Office 2013 en zorgt voor een betere beveiliging, zoals **meervoudige verificatie** en **verificatie op basis van een certificaat**.


## <a name="configure-conditional-access-for-sharepoint-online"></a>Beleid voor voorwaardelijke toegang voor SharePoint Online

### <a name="step-1-configure-active-directory-security-groups"></a>Stap 1: Active Directory-beveiligingsgroepen configureren
Voordat u begint, moet u Azure Active Directory-beveiligingsgroepen configureren voor het beleid voor voorwaardelijke toegang. U kunt deze groepen configureren in het **Office 365-beheercentrum** of in de **Intune-accountportal**. U gebruikt deze groepen om gebruikers op te nemen in of uit te sluiten van het beleid. Wanneer een gebruiker deel uitmaakt van de doelgroep voor het beleid, moet elk apparaat dat hij of zij gebruikt, aan het beleid voldoen om toegang te krijgen tot bronnen.

U kunt twee soorten groepen opgeven in een SharePoint Online-beleid:

-   **Doelgroepen**: bevat groepen gebruikers waarop het beleid van toepassing is.

-   **Uitgesloten groepen**: bevat groepen gebruikers waarop het beleid niet van toepassing is.

Als een gebruiker zich in beide groepen bevindt, wordt het beleid niet op de gebruiker toegepast.

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a>Stap 2: Nalevingsbeleid configureren en implementeren
Als u dit nog niet hebt gedaan, maakt u een nalevingsbeleid en implementeert u dit voor gebruikers waarop het SharePoint Online-beleid van toepassing is.

> [!NOTE]
> Terwijl nalevingsbeleid wordt geïmplementeerd voor Intune-groepen, is beleid voor voorwaardelijke toegang gericht op Azure Active Directory-beveiligingsgroepen.

Zie [Een nalevingsbeleid maken](create-a-device-compliance-policy-in-microsoft-intune.md) voor meer informatie over het configureren van het nalevingsbeleid.

> [!IMPORTANT]
> Als u geen nalevingsbeleid hebt geïmplementeerd, worden de apparaten beschouwd als apparaten die het beleid naleven.

Wanneer u klaar bent, gaat u door naar **Stap 3**.

### <a name="step-3-configure-the-sharepoint-online-policy"></a>Stap 3: Het SharePoint Online-beleid configureren
Configureer vervolgens het beleid om ervoor te zorgen dat alleen beheerde apparaten en apparaten die aan het beleid voldoen toegang hebben tot SharePoint Online. Dit beleid wordt opgeslagen in Azure Active Directory.

#### <a name="bkmk_spopolicy"></a>

>[!NOTE]
> U kunt ook in de Azure AD-beheerconsole een beleid voor voorwaardelijke toegang maken voor Intune-apparaten (dit beleid wordt in Azure AD ook wel **op apparaat gebaseerd beleid voor voorwaardelijke toegang** genoemd). Daarnaast kunt u andere beleidsregels voor voorwaardelijke toegang maken, zoals meervoudige verificatie. U kunt ook beleid voor voorwaardelijke toegang instellen voor bedrijfs-apps van derden die door Azure AD worden ondersteund, zoals voor Salesforce en Box. Zie voor meer informatie [How to set Azure Active Directory device-based conditional access policy for access control to Azure Active Directory connected applications](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/) (Het instellen van het op apparaten gebaseerde beleid voor voorwaardelijke toegang tot toepassingen die zijn verbonden met Azure Active Directory).


1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Beleid** > **Voorwaardelijke toegang** > **SharePoint Online-beleid**.
![Schermopname van de pagina SharePoint Online-beleid](../media/mdm-ca-spo-policy-configuration.png)

2.  Selecteer **Beleid voor voorwaardelijke toegang inschakelen voor SharePoint Online**.

3.  Onder **Toegang voor toepassingen**kunt u beleid voor voorwaardelijke toegang toepassen op:

    -   **Alle platforms**

        Hiervoor is vereist dat alle apparaten die worden gebruikt om toegang te krijgen tot **SharePoint Online**, moeten worden ingeschreven bij Intune en voldoen aan het nalevingsbeleid. Elke clienttoepassing die **moderne verificatie** gebruikt, is onderworpen aan beleid voor voorwaardelijke toegang. Als het platform momenteel niet wordt ondersteund door Intune, wordt toegang tot **SharePoint Online** geblokkeerd.

        Als u **Alle platformen** selecteert, betekent dat dit beleid met Azure Active Directory wordt toegepast op alle verificatieaanvragen, ongeacht het platform dat wordt gerapporteerd door de clienttoepassing. Alle platformen moeten worden geregistreerd en voldoen aan de voorwaarden, behalve:
        *    Windows-apparaten moeten worden ingeschreven, voldoen aan het beleid en lid zijn van een domein met om-premises Active Directory, of beide.
        * Niet-ondersteunde platformen, zoals Mac. Apps met moderne verificatie die afkomstig zijn van deze platformen, worden wel nog geblokkeerd.

    -   **Specifieke platforms**

         Het beleid voor voorwaardelijke toegang wordt toegepast op elke clienttoepassing die moderne verificatie gebruikt op de door u geselecteerde platformen.

     Voor Windows-pc's moet de pc lid zijn van een domein of zijn geregistreerd bij Intune en voldoen aan het beleid. U kunt de volgende vereisten instellen:

     -   **Apparaten moeten lid zijn van een domein of voldoen aan het beleid.** Kies deze optie om te vereisen dat pc's lid moeten zijn van een domein of het beleid moeten naleven dat is ingesteld in Intune. Als een pc niet aan een van deze vereisten voldoet, wordt de gebruiker gevraagd het apparaat te registreren bij Intune.

     -   **Apparaten moeten voldoen aan het beleid.** Kies deze optie om verplicht te stellen dat pc's geregistreerd zijn bij Intune en aan het beleid voldoen. Als een pc niet is geregistreerd, wordt een bericht met instructies voor de registratie weergegeven.

4.   Onder **Browsertoegang** tot SharePoint Online en OneDrive voor Bedrijven kunt u ervoor kiezen om toegang tot Exchange Online alleen toe te staan via de ondersteunde browsers: Safari (iOS) en Chrome (Android). Toegang vanaf andere browsers wordt geblokkeerd. De platformbeperkingen die u hebt geselecteerd voor toegang tot OneDrive zijn hier ook van toepassing.

  Op **Android**-apparaten moeten gebruikers browsertoegang inschakelen. Om dit te doen, moet een gebruiker de optie **Browsertoegang inschakelen** als volgt inschakelen op geregistreerde apparaten:
  1.    Open de app **Bedrijfsportal**.
  2.    Ga naar de pagina **Instellingen** via de beletseltekens (...) of via de menuknop Hardware.
  3.    Selecteer **Browsertoegang inschakelen**.
  4.    In de browser Chrome meldt u zich af bij Office 365. Start vervolgens Chrome opnieuw op.

  Op **iOS**- en **Android**-platformen genereert Azure Active Directory een TLS-certificaat (Transport Layer Security) voor het apparaat om te bepalen welk apparaat wordt gebruikt om de service te openen. Op het apparaat wordt het certificaat met een prompt weergegeven aan de gebruiker; deze kan het certificaat dan selecteren zoals in de volgende schermafbeeldingen wordt weergegeven. De gebruiker moet dit certificaat selecteren voordat de browser kan worden gebruikt.

  **iOS**

  ![Schermafbeelding van de certificaatprompt op een ipad](../media/mdm-browser-ca-ios-cert-prompt.png)

  **Android**

  ![Schermopname van het certificaatprompt op een Android-apparaat](../media/mdm-browser-ca-android-cert-prompt.png)
5.  Selecteer bij **Doelgroepen** de optie **Wijzigen** om de Active Directory-beveiligingsgroepen te selecteren waarop het beleid van toepassing moet zijn. U kunt ervoor kiezen dit op alle gebruikers of alleen op een bepaalde groep gebruikers toe te passen.

6.  Selecteer desgewenst onder **Uitgesloten groepen** de optie **Wijzigen** om de Active Directory-beveiligingsgroepen te selecteren waarop dit beleid niet van toepassing is.

7.  Als u klaar bent, kiest u **Opslaan**.

U hoeft het beleid voor voorwaardelijke toegang niet te implementeren. Het wordt direct van kracht.

### <a name="step-4-monitor-the-compliance-and-conditional-access-policies"></a>Stap 4: Het nalevingsbeleid en het beleid voor voorwaardelijke toegang bewaken
In de werkruimte **Groepen** kunt u de status van uw apparaten bekijken.

Selecteer een groep mobiele apparaten. Kies op het tabblad **Apparaten** vervolgens een van de volgende **Filters**:

-   **Apparaten die niet zijn geregistreerd bij AAD**. Deze apparaten zijn geblokkeerd voor SharePoint Online.

-   **Apparaten die niet voldoen aan het beleid**. Deze apparaten zijn geblokkeerd voor SharePoint Online.

-   **Apparaten die zijn geregistreerd bij AAD en die voldoen aan het beleid**. Deze apparaten hebben toegang tot SharePoint Online.

### <a name="see-also"></a>Zie tevens
[De toegang tot e-mail en O365-services beveiligen met Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)

