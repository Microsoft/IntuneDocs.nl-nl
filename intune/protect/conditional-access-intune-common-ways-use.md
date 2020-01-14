---
title: Scenario's voor voorwaardelijke toegang
titleSuffix: Microsoft Intune
description: Meer informatie over hoe voorwaardelijke toegang van Intune doorgaans wordt gebruikt voor voorwaardelijke toegang op basis van apparaten of apps.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a0b8e55e-c3d8-4599-be25-dc10c1027b62
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d30749a7eaa3d516bef2f2acff3e010d69db1c0e
ms.sourcegitcommit: a82d25d98fdf0ba766f8f074871d4f13725e23f9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/31/2019
ms.locfileid: "75547048"
---
# <a name="what-are-common-ways-to-use-conditional-access-with-intune"></a>Wat zijn gebruikelijke manieren om voorwaardelijke toegang met Intune te gebruiken?

[!INCLUDE [azure_portal](../includes/azure_portal.md)]


Er zijn twee soorten voorwaardelijke toegang met Intune: voorwaardelijke toegang op basis van apparaten en voorwaardelijke toegang op basis van apps. U moet het gerelateerde nalevingsbeleid configureren voor naleving van de voorwaardelijke toegang binnen uw organisatie. Voorwaardelijke toegang wordt meestal gebruikt voor zaken als toegang tot Exchange toestaan of blokkeren, toegang tot het netwerk bepalen of integratie realiseren met een Mobile Threat Defense-oplossing.
 
Met de informatie in dit artikel kunt u meer inzicht krijgen in hoe u de Intune-nalevingsmogelijkheden voor mobiele *apparaten* kunt gebruiken én in hoe Intune Mobile *Application* Management (MAM) werkt. 

> [!NOTE]
> Voorwaardelijke toegang is een Azure Active Directory-functie die is opgenomen in een Azure Active Directory Premium-licentie. Deze mogelijkheid wordt verbeterd door Intune door het toevoegen van nalevingsbeleid voor mobiele apparaten en beheer van mobiele apps aan de oplossing. Het knooppunt voor voorwaardelijke toegang dat via *Intune* wordt geopend, is hetzelfde als het knooppunt dat u opent via *Azure AD*.  

## <a name="device-based-conditional-access"></a>Voorwaardelijke toegang op basis van het apparaat

Intune en Azure Active Directory werken samen om ervoor te zorgen dat alleen beheerde en compatibele apparaten toegang kunnen krijgen tot e-mail, Office 365-services, SaaS-apps (Software as a Service) en [on-premises apps](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started). U kunt daarnaast een beleid in Azure Active Directory instellen, zodat alleen computers die zijn toegevoegd aan een domein of mobiele apparaten die zijn ingeschreven in Intune, toegang tot Office 365-services hebben.

Met Intune beschikt u over mogelijkheden voor apparaatnalevingsbeleid waarmee u de nalevingsstatus van het apparaat kunt evalueren. De nalevingsstatus wordt gerapporteerd aan Azure Active Directory om het voorwaardelijke toegangsbeleid af te dwingen dat in Azure Active Directory wordt gemaakt wanneer de gebruiker zich toegang tot uw bedrijfsresources probeert te verschaffen.

De op apparaten gebaseerde beleidsregels voor voorwaardelijke toegang voor Exchange Online en andere Office 365-producten geconfigureerd via de [Azure-portal](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).  

- Meer informatie over [het vereisen van beheerde apparaten met voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/require-managed-devices).

- Meer informatie over [Intune-apparaatnaleving](device-compliance-get-started.md).

- Meer informatie over [ondersteunde browsers met voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#supported-browsers).

> [!NOTE]
> Als u op Android-apparaten Op apparaten gebaseerde toegang voor Sharepoint Online of Op browsers gebaseerde toegang tot Exchange Online inschakelt, moeten gebruikers de optie **Browsertoegang inschakelen** als volgt op het ingeschreven apparaat inschakelen:
> 1. Open de **app Bedrijfsportal**.
> 2. Ga naar de pagina **Instellingen** via de drie puntjes (...) of via de menuknop van de hardware.
> 3. Selecteer **Browsertoegang inschakelen**. 
> 4. In de browser Chrome meldt u zich af bij Office 365. Start vervolgens Chrome opnieuw op.

### <a name="conditional-access-based-on-network-access-control"></a>Voorwaardelijke toegang op basis van netwerktoegangsbeheer

Intune kan worden geïntegreerd met partners als Cisco ISE, Aruba Clear Pass en Citrix NetScaler voor toegangsbeheer op basis van de Intune-inschrijving en de nalevingsstatus van het apparaat.

Gebruikers kan toegang tot het Wi-Fi-netwerk of de VPN-resources worden verleend of geweigerd door te controleren of het apparaat dat ze gebruiken, wordt beheerd met en voldoet aan het Intune-nalevingsbeleid voor apparaten.

- Meer informatie over de [NAC-integratie met Intune](network-access-control-integrate.md).

### <a name="conditional-access-based-on-device-risk"></a>Voorwaardelijk op basis van het apparaatrisico

Intune werkt samen met leveranciers van Mobile Threat Defense, die een beveiligingsoplossing bieden voor het detecteren van malware, Trojaans paarden en andere bedreigingen op mobiele apparaten.

#### <a name="how-the-intune-and-mobile-threat-defense-integration-works"></a>Hoe de integratie van Intune en Mobile Threat Defense werkt

Wanneer de Mobile Threat Defense-agent op een mobiel apparaat is geïnstalleerd, stuurt de agent berichten over de nalevingsstatus naar Intune om te melden wanneer er op het mobiele apparaat zelf een bedreiging wordt gevonden.

De integratie van Intune en Mobile Threat Defense speelt een rol bij de beslissingen die op basis van de apparaatrisico's worden genomen voor de voorwaardelijke toegang.

- Meer informatie over [Intune Mobile Threat Defense](mobile-threat-defense.md).

### <a name="conditional-access-for-windows-pcs"></a>Voorwaardelijke toegang voor Windows-pc's

Voorwaardelijke toegang voor pc's biedt mogelijkheden die vergelijkbaar zijn met de mogelijkheden voor mobiele apparaten. Laten we eens kijken op welke manieren u voorwaardelijke toegang kunt gebruiken wanneer u pc's met Intune beheert.

#### <a name="corporate-owned"></a>In bedrijfseigendom

- **On-premises AD-domein is toegevoegd:** Deze optie wordt doorgaans gebruikt door organisaties die redelijk tevreden zijn met de manier waarop hun pc's al worden beheerd met AD-groepsbeleid of Configuration Manager.

- **Azure AD-domein toegevoegd en Intune-beheerprogramma:** Dit scenario is bedoeld voor organisaties die voornamelijk cloudservices gebruiken, met het doel om het gebruik van een on-premises infrastructuur te beperken, of alleen cloudservices gebruiken (geen on-premises infrastructuur). Azure AD Join werkt goed in een hybride omgeving en biedt toegang tot zowel cloud- als on-premises apps en bronnen. Het apparaat wordt toegevoegd aan Azure AD en wordt geregistreerd bij Intune, dat kan worden gebruikt als criterium voor voorwaardelijke toegang bij het openen van bedrijfsresources.

- **AD-domein toegevoegd en Configuration Manager:** Vanaf de huidige vertakking biedt Configuration Manager niet alleen de mogelijkheid om een pc toe te voegen aan een domein, maar beschikt u ook over mogelijkheden voor voorwaardelijke toegang om specifieke nalevingscriteria te evalueren:

  - Is de pc versleuteld?

  - Is er anti-malware geïnstalleerd? Is de pc up-to-date?

  - Is het apparaat gekraakt of geroot?

#### <a name="bring-your-own-device-byod"></a>BYOD (Bring Your Own Device)

- **Workplace join en Intune-beheer:** Hier kan de gebruiker de eigen persoonlijke apparaten toevoegen voor toegang tot bedrijfsresources en -services. U kunt Workplace Join gebruiken en apparaten bij Intune MDM registreren om beleidsregels op apparaatniveau te ontvangen. Dit is een alternatieve optie om de criteria voor voorwaardelijke toegang te evalueren.

Meer informatie over [apparaatbeheer in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/overview).

## <a name="app-based-conditional-access"></a>Voorwaardelijke toegang op basis van apps

Intune en Azure Active Directory werken samen om ervoor te zorgen dat alleen beheerde apps toegang hebben tot de bedrijfs-e-mail of andere Office 365-services.

- Meer informatie over [op apps gebaseerde voorwaardelijke toegang met Intune](app-based-conditional-access-intune.md).

### <a name="intune-conditional-access-for-exchange-on-premises"></a>Voorwaardelijke toegang van Intune voor Exchange On-Premises

Voorwaardelijke toegang kan worden gebruikt de toegang tot **Exchange On-Premises** toe te staan of te blokkeren op basis van de beleidsregels voor apparaatcompatibiliteit en de registratiestatus. Wanneer voorwaardelijke toegang wordt gebruikt in combinatie met een nalevingsbeleid voor apparaten, hebben alleen apparaten die voldoen aan het beleid toegang voor Exchange On-Premises.

U kunt geavanceerde instellingen configureren voor de voorwaardelijke toegang. Zodoende hebt u voor gedetailleerdere controle over onder meer het volgende:

- Toestaan of blokkeren van bepaalde platforms.

- Onmiddellijk blokkeren van apparaten die niet worden beheerd door Intune.

Wanneer er beleidsregels voor apparaatcompatibiliteit en voorwaardelijke toegang zijn toegepast, wordt voor elk apparaat dat wordt gebruikt voor toegang tot Exchange On-Premises gecontroleerd of de beleidsregels worden nageleefd.

Wanneer apparaten niet voldoen aan de gestelde voorwaarden, wordt de eindgebruiker door de registratieprocedure voor het apparaat geleid om het probleem te verhelpen dat ervoor zorgt dat het apparaat niet-compatibel is.

#### <a name="how-conditional-access-for-exchange-on-premises-works"></a>Hoe voorwaardelijke toegang voor Exchange On-Premises werkt

Voorwaardelijke toegang voor Exchange On-Premises werkt anders dan het beleid voor voorwaardelijke toegang op basis van Azure. U installeert de Intune Exchange On-Premises-connector om rechtstreeks te communiceren met Exchange Server. Intune Exchange Connector haalt alle EAS-records (Exchange Active Sync) op de Exchange-server op, zodat de EAS-records via Intune kunnen worden gekoppeld aan records Intune-apparaten. Deze records zijn apparaten die zijn geregistreerd bij Intune en door Intune worden herkend. Met dit proces wordt de toegang tot e-mail toegestaan of geblokkeerd.

Als de EAS-record nieuw is en deze niet door Intune wordt herkend, wordt er een cmdlet (uitgesproken als commandlet) uitgegeven waarmee de Exchange-server opdracht wordt gegeven de toegang tot e-mail te blokkeren. Hier volgt meer informatie over de werking van dit proces:

![Exchange on-Premises met CA-stroomdiagram](./media/conditional-access-intune-common-ways-use/ca-intune-common-ways-1.png)

1. De gebruiker probeert toegang te krijgen tot de bedrijfs-e-mail, die wordt gehost op Exchange On-Premises 2010 SP1 of later.

2. Als het apparaat niet wordt beheerd door Intune, wordt de toegang tot e-mail geblokkeerd. Intune verzendt een blokmelding naar de EAS-client.

3. EAS ontvangt de blokmelding, waarna het apparaat in quarantaine wordt geplaatst. Vervolgens wordt de quarantaine-e-mail verzonden. Deze bevat herstelstappen met koppelingen, zodat de gebruikers hun apparaten kunnen registreren.

4. Het Workplace Join-proces wordt uitgevoerd. Dit is de eerste stap om een apparaat met Intune te beheren.

5. Het apparaat wordt geregistreerd bij Intune.

6. Intune wijst de EAS-record toe aan een apparaatrecord en slaat de nalevingsstatus voor het apparaat op.

7. De EAS-client-id wordt geregistreerd middels het apparaatregistratieproces van Azure AD, zodat er een relatie tussen de Intune-apparaatrecord en de EAS-client-id wordt gemaakt.

8. De apparaatregistratie van Azure AD slaat de informatie over de apparaatstatus op.

9. Als de gebruiker aan de beleidsregels voor voorwaardelijke toegang voldoet, geeft Intune een cmdlet via Intune Exchange Connector uit, zodat het postvak kan worden gesynchroniseerd.

10. De Exchange-server verzendt de melding naar de EAS-client, zodat de gebruiker toegang heeft tot e-mail.


#### <a name="whats-the-intune-role"></a>Wat is de rol van Intune?

Met Intune wordt de apparaatstatus beoordeeld en beheerd.

#### <a name="whats-the-exchange-server-role"></a>Wat is de rol van de Exchange-server?

De Exchange-server biedt de API en infrastructuur om apparaten in quarantaine te plaatsen.

> [!IMPORTANT]
> Houd er rekening mee dat er een nalevingsprofiel en Intune-licentie moet worden toegewezen aan de gebruiker van het apparaat, zodat het apparaat op naleving kan worden gecontroleerd. Als er geen nalevingsbeleid wordt geïmplementeerd voor de gebruiker, wordt het apparaat beschouwd als een apparaat dat voldoet aan het beleid en worden er geen toegangsbeperkingen toegepast.

## <a name="next-steps"></a>Volgende stappen

[Voorwaardelijke toegang in Azure Active Directory configureren](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

[Op apps gebaseerd beleid voor voorwaardelijke toegang instellen](app-based-conditional-access-intune-create.md)

[De on-premises Exchange-connector installeren met Intune](exchange-connector-install.md).

[Beleid maken voor voorwaardelijke toegang voor Exchange On-premises](conditional-access-exchange-create.md)
