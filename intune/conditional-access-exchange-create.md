---
title: Beleid voor voorwaardelijke toegang tot Exchange maken
titlesuffix: Microsoft Intune
description: Configureer voorwaardelijke toegang voor Exchange On-Premises en oudere Exchange Online Dedicated in Intune.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 183eb3f121e1b5c53673d10a04d0710baeb5a703
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated"></a>Een beleid voor voorwaardelijke toegang maken voor Exchange On-Premises en verouderde Exchange Online Dedicated

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel leest u hoe u de voorwaardelijke toegang voor Exchange On-Premises configureert op basis van apparaatnaleving.

Als u een Exchange Online Dedicated-omgeving hebt en wilt weten of deze de nieuwe of oudere configuratie heeft, neemt u contact op met uw accountmanager. Als u de toegang tot e-mail op Exchange On-premises of de oude Exchange Online-specifieke omgeving wilt beheren, configureer dan beleid voor voorwaardelijke toegang tot Exchange On-premises in Intune.

## <a name="before-you-begin"></a>Voordat u begint

Controleer het volgende voordat u voorwaardelijke toegang configureert:

- Uw versie van Exchange moet **Exchange 2010 SP1 of hoger** zijn. De CAS-matrix (Client Access Server) voor Exchange-servers wordt ondersteund.

- U moet de [Exchange On-Premises-connector Exchange Active Sync](exchange-connector-install.md) gebruiken, die Intune verbindt met Exchange On-Premises.

    >[!IMPORTANT]
    >De Exchange On-premises-connector is uitsluitend bestemd voor uw Intune-tenant en mag niet worden gebruikt met een andere tenant. U moet er ook voor zorgen dat de Exchange-connector voor uw tenant **op slechts één machine** is geïnstalleerd.

- De connector kan op elke machine worden geïnstalleerd, zolang die machine maar kan communiceren met de Exchange-server.

- De connector ondersteunt de **Exchange CAS-omgeving**. Vanuit technisch oogpunt kunt u de connector desgewenst rechtstreeks op de Exchange CAS-server installeren, maar dit wordt niet aangeraden, omdat hiermee de belasting van de server wordt verhoogd. Wanneer u de connector configureert, moet u deze zodanig instellen dat deze communiceert met een van de Exchange CAS-servers.

- **Exchange ActiveSync** kan worden geconfigureerd met verificatie op basis van certificaten of het invoeren van gebruikersreferenties.

- Wanneer beleid voor voorwaardelijke toegang wordt geconfigureerd en een gebruiker deel uitmaakt van de doelgroep voor het beleid, moet het volgende met het **apparaat** zijn gedaan voordat een gebruiker verbinding kan maken met zijn e-mail:
    - Het apparaat moet zijn **ingeschreven** bij Intune of lid zijn van een domein.
    - Het apparaat moet zijn **geregistreerd bij Azure Active Directory**. Bovendien moet de client-id van Exchange ActiveSync zijn geregistreerd bij Azure Active Directory.
<br></br>
- AAD DRS wordt automatisch geactiveerd voor Intune- en Office 365-klanten. Klanten die de ADFS Device Registration Service al hebben geïmplementeerd, zien geen geregistreerde apparaten in hun on-premises Active Directory. **Dit geldt niet voor Windows-pc's en Windows Phone-apparaten**.

- Het apparaat moet **compatibel** zijn met alle soorten nalevingsbeleid die worden geïmplementeerd op het apparaat.

- Als het apparaat niet aan de instellingen voor voorwaardelijke toegang voldoet, krijgt de gebruiker een van de volgende berichten te zien wanneer deze zich aanmeldt:
    - Als het apparaat niet is ingeschreven bij Intune of niet is geregistreerd bij Azure Active Directory, wordt er een bericht weergegeven met instructies over hoe de bedrijfsportal-app moet worden geïnstalleerd, het apparaat moet worden ingeschreven en e-mail moet worden geactiveerd. Dit proces zorgt er ook voor dat de Exchange ActiveSync-id van het apparaat wordt gekoppeld aan de apparaatrecord in Azure Active Directory.
    - Als het apparaat niet aan het beleid voldoet, wordt er een bericht weergegeven waarin de gebruiker naar de website van de Intune-bedrijfsportal of de bedrijfsportal-app wordt verwezen, waar informatie te vinden is over het probleem en hoe het kan worden opgelost.

### <a name="support-for-mobile-devices"></a>Ondersteuning voor mobiele apparaten

- Windows Phone 8.1 en hoger
- Systeemeigen e-mailapp voor iOS.
- EAS-mailclients zoals Gmail op Android 4 of hoger.
- EAS-mailclients **Android for Work-apparaten:** alleen de apps **Gmail** en **Nine Work** in het **werkprofiel** worden ondersteund op Android for Work-apparaten. Voorwaardelijke toegang werkt alleen in combinatie met Android for Work als u een e-mailprofiel voor de app Gmail of Nine Work implementeert en die apps ook implementeert als verplicht te installeren apps.

> [!NOTE]
> De Microsoft Outlook-app voor Android en iOS wordt niet ondersteund. 

### <a name="support-for-pcs"></a>Ondersteuning voor pc's

De native **Mail**-toepassing voor Windows 8.1 en hoger (indien geregistreerd bij Intune)


## <a name="configure-exchange-on-premises-access"></a>Toegang tot Exchange On-Premises configureren

1. Ga naar [Azure Portal](https://portal.azure.com/) en meld u aan met uw Intune-referenties.

1. Nadat u zich hebt aangemeld, ziet u het **Azure-dashboard**.

1. Kies **Alle services** in het linkermenu en typ dan **Intune** in het filtertekstvak.

1. Kies **Intune**. Vervolgens ziet u het **Intune-Dashboard**.

1. Kies **On-premises toegang**. In het deelvenster **On-premises toegang** vindt u de status van het beleid voor voorwaardelijke toegang en de apparaten die door het beleid worden beïnvloed.

1. Kies **On-premises toegang tot Exchange** onder **Beheer**.

1. Kies **Ja** in het deelvenster **On-premises toegang tot Exchange** om on-premises toegang tot Exchange in te schakelen.

    > [!NOTE]
    > Als u de on-premises connector Exchange Active Sync niet hebt geconfigureerd, is deze optie uitgeschakeld.  U moet deze connector eerst installeren en configureren voordat u voorwaardelijke toegang voor Exchange On-Premises inschakelt. Zie [Intune On-Premises Exchange Connector installeren](exchange-connector-install.md) voor meer informatie.

1. Kies **Opgenomen groepen** onder **Toewijzing**.  Gebruik de beveiligingsgebruikersgroep waarop u voorwaardelijke toegang wilt toepassen. Voor deze actie moeten de gebruikers hun apparaten inschrijven in Intune en moeten de apparaten voldoen aan de nalevingsprofielen.

1. Als u een bepaalde groepen met gebruikers wilt uitsluiten, kiest u **Uitgesloten groepen** en selecteert u de gebruikersgroep die u wilt uitsluiten van vereiste apparaatinschrijving en -naleving.

1. Kies **Gebruikersmeldingen** onder **Instellingen** om het standaard-e-mailbericht te wijzigen. Dit bericht wordt naar gebruikers verzonden als hun apparaten niet compatibel zijn en gebruikers toegang willen tot Exchange On-Premises. Voor de berichtsjabloon wordt Markup Language gebruikt.  Tijdens het typen ziet u een voorbeeld van het bericht.
    > [!TIP]
    > Zie dit Wikipedia-[artikel](https://en.wikipedia.org/wiki/Markup_language) voor meer informatie over Markup Language.

1. Stel in het deelvenster **Geavanceerde toegangsinstellingen voor Exchange Active Sync** de globale standaardregel in voor toegang van apparaten die niet worden beheerd door Intune, en voor regels op platformniveau zoals in de volgende twee stappen wordt beschreven.

1. Als er apparaten zijn die niet worden beïnvloed door voorwaardelijke toegang of door andere regels, kunt u zelf kiezen of deze toegang krijgen tot Exchange, of de toegang blokkeren.

   - Wanneer u toegang toestaat, kunnen alle apparaten direct toegang krijgen tot Exchange On-Premises.  Apparaten die deel uitmaken van de gebruikers in de **opgenomen groepen**, worden geblokkeerd als wordt bepaald dat ze niet aan het nalevingsbeleid voldoen of niet zijn ingeschreven in Intune.
   - Wanneer u de toegang blokkeert, wordt de toegang van alle apparaten tot Exchange On-Premises in eerste instantie geblokkeerd.  Apparaten die deel uitmaken van gebruikers in de **opgenomen groepen** krijgen toegang zodra de apparaten zijn ingeschreven in Intune en zijn geëvalueerd als compatibel. Android-apparaten waarop Samsung Knox Standard niet wordt uitgevoerd, worden altijd geblokkeerd omdat deze instelling niet wordt ondersteund op deze apparaten.

1. Kies **Toevoegen** onder **Uitzonderingen van apparaatplatform** om de platformen op te geven. Als de instelling **Toegang tot onbeheerde apparaten** is ingesteld op **Geblokkeerd**, kunnen apparaten die zijn ingeschreven en compatibel zijn ook toegang krijgen, zelfs als er een platformuitzondering van toepassing is waardoor de apparaten worden geblokkeerd. Kies **OK** om de instellingen op te slaan.

1. Klik in het deelvenster **On-premises** op **Opslaan** om het beleid voor voorwaardelijke toegang op te slaan.

## <a name="create-azure-ad-conditional-access-policies-in-intune"></a>Voorwaardelijk toegangsbeleid voor Azure AD maken in Intune

Vanaf versie Intune 1704 kunnen beheerders Azure AD-beleidsregels voor voorwaardelijke toegang vanuit Intune Azure Portal maken, zodat u niet hoeft te wisselen tussen de workloads in Azure en Intune.

> [!IMPORTANT]
> Als u beleid voor voorwaardelijke toegang voor Azure AD wilt instellen vanuit Intune Azure Portal, moet u een Azure AD Premium-licentie hebben.

### <a name="to-create-azure-ad-conditional-access-policy"></a>Beleid voor voorwaardelijke toegang voor Azure AD maken

1. Kies in het**Intune-dashboard** **Voorwaardelijke toegang**.

2. Kies in het deelvenster **Beleid** de optie **Nieuw beleid** om uw nieuwe beleid voor voorwaardelijke toegang in Azure AD te maken.

## <a name="see-also"></a>Zie ook

[Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
