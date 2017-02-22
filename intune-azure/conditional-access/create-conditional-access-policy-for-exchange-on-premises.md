---
title: Beleid voor voorwaardelijke toegang voor Exchange On-Premises | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u voorwaardelijke toegang voor Exchange On-Premises en oudere Exchange Online Dedicated in Intune kunt configureren'
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 581f9be824ea883fd0208abc3b2ecc09174cb911
ms.openlocfilehash: a80d6a19948291cc80e42ad5a9a2f016effb2f37


---

# <a name="how-to-create-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated-in-microsoft-intune-azure-preview"></a>Een beleid voor voorwaardelijke toegang maken voor Exchange On-Premises en oudere Exchange Online Dedicated-omgevingen in Microsoft Intune Azure Preview


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Dit onderwerp begeleidt u bij het proces van het configureren van voorwaardelijke toegang voor Exchange On-Premises op basis van apparaatnaleving.

Als u een Exchange Online Dedicated-omgeving hebt en wilt weten of deze de nieuwe of oudere configuratie heeft, neemt u contact op met uw accountmanager. Als u de toegang tot e-mail op Exchange On-premises of de oude Exchange Online-specifieke omgeving wilt beheren, configureer dan beleid voor voorwaardelijke toegang tot Exchange On-premises in Intune.

## <a name="prerequisites"></a>Vereisten

Controleer het volgende **voordat** u voorwaardelijke toegang configureert:

- Uw versie van Exchange moet **Exchange 2010 of hoger** zijn. De CAS-matrix (Client Access Server) voor Exchange-servers wordt ondersteund.
- U moet de **Exchange On-Premises-connector Exchange Active Sync** gebruiken, die Intune verbindt met Microsoft Exchange On-Premises. Zie <link> voor meer informatie over de connector.

  - De Exchange On-premises-connector die u in de Intune-console vindt, is uitsluitend bestemd voor uw Intune-tenant en mag niet worden gebruikt met een andere tenant. U moet er ook voor zorgen dat de Exchange-connector voor uw tenant **op slechts één machine** is geïnstalleerd.

Deze connector moet worden gedownload vanuit de Intune-beheerconsole. Zie <link to new topic> voor een overzicht van het configureren van On-Premises Exchange Connector.

De connector kan op elke machine worden geïnstalleerd, zolang die machine maar kan communiceren met de Exchange-server.

- De connector ondersteunt de **Exchange CAS-omgeving**. Vanuit technisch oogpunt kunt u de connector desgewenst rechtstreeks op de Exchange CAS-server installeren, maar dit wordt niet aangeraden, omdat hiermee de belasting van de server wordt verhoogd. Wanneer u de connector configureert, moet u deze zodanig instellen dat deze communiceert met een van de Exchange CAS-servers.
- **Exchange ActiveSync** kan worden geconfigureerd met verificatie op basis van certificaten of het invoeren van gebruikersreferenties.

Wanneer beleid voor voorwaardelijke toegang wordt geconfigureerd en een gebruiker deel uitmaakt van de doelgroep voor het beleid, moet het volgende met het **apparaat** zijn gedaan voordat een gebruiker verbinding kan maken met zijn e-mail:

- Het apparaat moet zijn **ingeschreven** bij Intune of lid zijn van een domein.
- Het apparaat moet zijn **geregistreerd bij Azure Active Directory**. Bovendien moet de client-id van Exchange ActiveSync zijn geregistreerd bij Azure Active Directory.

AAD DRS wordt automatisch geactiveerd voor Intune- en Office 365-klanten. Klanten die de ADFS Device Registration Service al hebben geïmplementeerd, zien geen geregistreerde apparaten in hun on-premises Active Directory. **Dit geldt niet voor Windows-pc's en Windows Phone-apparaten**.

- Het apparaat moet **compatibel** zijn met alle Intune-nalevingsbeleidsregels die op het apparaat zijn geïmplementeerd.

Als het apparaat niet aan de instellingen voor voorwaardelijke toegang voldoet, krijgt de gebruiker een van de volgende berichten te zien wanneer deze zich aanmeldt:

- Als het apparaat niet is ingeschreven bij Intune of niet is geregistreerd bij Azure Active Directory, wordt er een bericht weergegeven met instructies over hoe de bedrijfsportal-app moet worden geïnstalleerd, het apparaat moet worden ingeschreven en e-mail moet worden geactiveerd. Dit proces zorgt er ook voor dat de Exchange ActiveSync-id van het apparaat wordt gekoppeld aan de apparaatrecord in Azure Active Directory.
- Als het apparaat niet aan het beleid voldoet, wordt er een bericht weergegeven waarin de gebruiker naar de website van de Intune-bedrijfsportal of de bedrijfsportal-app wordt verwezen, waar informatie te vinden is over het probleem en hoe het kan worden opgelost.

## <a name="support-for-mobile-devices"></a>Ondersteuning voor mobiele apparaten

- Windows Phone 8.1 en hoger
- Systeemeigen e-mailapp voor iOS.
- EAS-mailclients zoals Gmail op Android 4 of hoger.
- EAS-mailclients **Android for Work-apparaten:** alleen de apps **Gmail** en **Nine Work** in het **werkprofiel** worden ondersteund op Android for Work-apparaten. Voorwaardelijke toegang werkt alleen in combinatie met Android for Work als u een e-mailprofiel voor de app Gmail of Nine Work implementeert en die apps ook implementeert als verplicht te installeren apps.

>[!NOTE]
>De Microsoft Outlook-app voor Android en iOS wordt niet ondersteund.

> Android for Work wordt de komende maanden beschikbaar gemaakt voor Intune-tenants.

Lees de aankondiging over Android for Work in de editie van oktober 2016 van [Wat is er nieuw in Microsoft Intune?](https://docs.microsoft.com/en-us/intune/whats-new/whats-new-archive#october-2016) voor meer informatie over de ondersteuningstatus van Android for Work.

## <a name="support-for-pcs"></a>Ondersteuning voor pc's

De **Mail**-toepassing voor Windows 8.1 en hoger (indien geregistreerd bij Intune)


## <a name="configure-exchange-on-premises-access"></a>Toegang tot Exchange On-Premises configureren

1. Kies de workload **Voorwaardelijke toegang** in Azure Portal om de blade On-premises te openen.
2. Op de blade **On-premises** vindt u de status van het beleid voor voorwaardelijke toegang en de apparaten die door het beleid worden beïnvloed.
3. Kies **On-premises toegang tot Exchange** onder **Beheer**.
4. Kies **Ja** op de blade **On-premises toegang tot Exchange** om on-premises toegang tot Exchange in te schakelen.

  >[!NOTE]
  >Als u de on-premises connector Exchange Active Sync niet hebt geconfigureerd, wordt deze optie uitgeschakeld.  U moet deze connector eerst installeren en configureren voordat u voorwaardelijke toegang voor Exchange On-Premises inschakelt. Zie [Intune On-Premises Exchange Connector installeren](install-intune-on-premises-exchange-connector.md) voor meer informatie.

5. Kies **Opgenomen groepen** onder **Toewijzing**.  Gebruik de beveiligingsgebruikersgroep waarop u voorwaardelijke toegang wilt toepassen.  Hiervoor moeten de gebruikers hun apparaten inschrijven in Intune en moeten de apparaten voldoen aan de nalevingsprofielen.
6. Als u een bepaalde groepen met gebruikers wilt uitsluiten, kiest u **Uitgesloten groepen** en selecteert u de gebruikersgroep die u wilt uitsluiten van vereiste apparaatinschrijving en -naleving.
7. Kies **Gebruikersmeldingen** onder **Instellingen** om het standaard-e-mailbericht te wijzigen. Dit bericht wordt naar gebruikers verzonden als hun apparaten niet compatibel zijn en gebruikers toegang willen tot Exchange On-Premises. Voor de berichtsjabloon wordt Markup Language gebruikt.  Tijdens het typen ziet u een voorbeeld van het bericht. Zie dit Wikipedia-[artikel](https://en.wikipedia.org/wiki/Markup_language) voor meer informatie over Markup Language.
8. Stel op de blade **Geavanceerde toegangsinstellingen voor Exchange Active Sync** de globale standaardregel in voor toegang van apparaten die niet worden beheerd door Intune, en voor regels op platformniveau zoals in de volgende twee stappen wordt beschreven.
9. Als er apparaten zijn die niet worden beïnvloed door voorwaardelijke toegang of door andere regels, kunt u zelf kiezen of deze toegang krijgen tot Exchange, of de toegang blokkeren.
  - Wanneer u toegang toestaat, kunnen alle apparaten direct toegang krijgen tot Exchange On-Premises.  Apparaten die deel uitmaken van de gebruikers in de **opgenomen groepen**, worden geblokkeerd als wordt bepaald dat ze niet aan het nalevingsbeleid voldoen of niet zijn ingeschreven in Intune.
  - Wanneer u de toegang blokkeert, wordt de toegang van alle apparaten tot Exchange On-Premises in eerste instantie geblokkeerd.  Apparaten die deel uitmaken van gebruikers in de **opgenomen groepen** krijgen toegang zodra de apparaten zijn ingeschreven in Intune en zijn geëvalueerd als compatibel. Android-apparaten waarop Samsung KNOX Standard niet wordt uitgevoerd, worden altijd geblokkeerd omdat deze instelling niet wordt ondersteund op deze apparaten.
10. Kies **Toevoegen** onder **Uitzonderingen van apparaatplatform** om de platformen op te geven. Als de instelling **Toegang tot onbeheerde apparaten** is ingesteld op **Geblokkeerd**, kunnen apparaten die zijn ingeschreven en compatibel zijn ook toegang krijgen, zelfs als er een platformuitzondering van toepassing is waardoor de apparaten worden geblokkeerd. Kies **OK** om de instellingen op te slaan.
11. Klik op de blade **On-premises** op **Opslaan** om het beleid voor voorwaardelijke toegang op te slaan.



<!--HONumber=Feb17_HO1-->


