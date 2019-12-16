---
title: Nalevingsbeleid voor apparaten bewaken in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik het apparaatnalevingsdashboard om de algehele apparaatnaleving te bewaken, rapporten te bekijken en de apparaatnaleving per beleidsregel en per instelling te bekijken.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 947472c5e589cb443c9a15d20a732c299cc48b44
ms.sourcegitcommit: df8e2c052fafb2d5d4e9b4fcd831ae0ecf7f8d16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2019
ms.locfileid: "74992982"
---
# <a name="monitor-intune-device-compliance-policies"></a>Nalevingsbeleid voor Intune-apparaten controleren

U kunt met behulp van nalevingsrapporten apparaatcompatibiliteit controleren en problemen met betrekking tot naleving in uw organisatie oplossen. Met behulp van deze rapporten, kunt u informatie bekijken over:

- De algemene nalevingsstatussen van apparaten
- De nalevingsstatus voor een specifieke instelling
- De nalevingsstatus voor een specifiek beleid
- Inzoomen op afzonderlijke apparaten om specifieke instellingen en beleidsregels te bekijken die van invloed zijn op het apparaat

## <a name="open-the-compliance-dashboard"></a>Het nalevingsdashboard openen

Open het **dashboard voor apparaatnaleving van Intune**:

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. Selecteer **Apparaatnaleving** > **Overzicht**. Het **dashboard voor apparaatnaleving** wordt geopend.

> [!IMPORTANT]
> Apparaten moeten worden ingeschreven bij Intune om het nalevingsbeleid voor apparaten te ontvangen.

## <a name="dashboard-overview"></a>Dashboardoverzicht

Als het dashboard wordt geopend, krijgt u een overzicht met alle nalevingsrapporten. U kunt in deze rapporten de volgende onderdelen bekijken en controleren:

- Algehele apparaatnaleving
- Apparaatnaleving per beleid
- Apparaatnaleving per instelling
- Status van de dreigingsagent
- Status van de apparaatbeveiliging

![In de dashboardafbeelding ziet u het dashboard voor apparaatnaleving en de verschillende rapporten](./media/compliance-policy-monitor/idc-1.png)

Als u dieper wilt ingaan op deze rapporten, kunt u tevens specifieke nalevingsbeleidsregels en instellingen bekijken die betrekking hebben op een specifiek apparaat, met inbegrip van de nalevingsstatus voor elke instelling.

### <a name="device-compliance-status"></a>De nalevingsstatus van apparaten

De grafiek **Nalevingsstatus van apparaten** toont de nalevingsstatus voor alle bij Intune geregistreerde apparaten. De statussen van apparaatnaleving worden opgeslagen in twee verschillende databases: Intune en Azure Active Directory.

> [!IMPORTANT]
> Intune volgt het incheckschema van het apparaat voor alle nalevingsevaluaties op het apparaat. [Meer informatie over het incheckschema van het apparaat](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

Beschrijvingen van verschillende statussen van het nalevingsbeleid voor apparaten:

- **Compatibel**: Op het apparaat zijn een of meer nalevingsbeleidsinstellingen voor apparaten toegepast.

- **In respijtperiode:** Het apparaat is het doelwit van een of meer nalevingsbeleidsinstellingen voor apparaten. Maar de gebruiker heeft het beleid nog niet toegepast. Dit betekent dat het apparaat niet compatibel is, maar zich in de respijtperiode bevindt die door de beheerder is vastgesteld.

  - Meer informatie over [Acties voor niet-compatibele apparaten](actions-for-noncompliance.md).

- **Niet geëvalueerd**: Een initiële status voor nieuw geregistreerde apparaten. Andere mogelijke oorzaken voor deze status zijn onder andere:

  - Apparaten die niet aan nalevingsbeleid zijn toegewezen en geen trigger bevatten voor de controle op naleving
  - Apparaten die niet zijn ingecheckt nadat het nalevingsbeleid voor het laatst is bijgewerkt
  - Apparaten die niet aan een specifieke gebruiker zijn gekoppeld, zoals:
    - iOS-apparaten die zijn gekocht via het Device Enrollment Program (DEP) van Apple en zonder gebruikersaffiniteit
    - Kiosk-apparaten met Android of toegewezen Android Enterprise-apparaten
  - Apparaten die zijn ingeschreven met een DEM-account (apparaatinschrijvingsmanager)

- **Niet compatibel**: Op het apparaat kunnen een of meer nalevingsbeleidsinstellingen voor apparaten niet worden toegepast. Of de gebruiker heeft niet voldaan aan het beleid.

- **Apparaat niet gesynchroniseerd:** Voor het apparaat is de nalevingsbeleidsstatus niet doorgegeven, om een van de volgende redenen:

  - **Onbekend**: Het apparaat is offline of kan om andere redenen niet communiceren met Intune of Azure AD.

  - **Fout**: Het apparaat kan niet communiceren met Intune en Azure AD en heeft een foutbericht met de reden ontvangen.

> [!IMPORTANT]
> Apparaten die zijn ingeschreven bij Intune, maar waarop geen nalevingsbeleid voor apparaten is gericht, worden in dit rapport opgenomen onder de bucket **Compatibel**.

#### <a name="drill-down-for-more-details"></a>Inzoomen voor meer details

Selecteer een status in het diagram **Nalevingstatus apparaten**. Selecteer bijvoorbeeld de status **Niet compatibel**:

![De status Niet compatibel kiezen](./media/compliance-policy-monitor/select-not-compliant-status.png)

Met deze actie wordt het venster **Apparaatnaleving** geopend en worden apparaten weergegeven in de grafiek **Apparaatstatus**. De grafiek toont meer informatie over de apparaten met die status, met inbegrip van besturingssysteemplatform en datum van laatste check-in en meer.
![In de dashboardafbeelding ziet u meer informatie over het apparaat met die specifieke status](./media/compliance-policy-monitor/drill-down-details.png)

Als u alle apparaten wilt zien van een specifieke gebruiker, kunt u het diagramrapport ook filteren door het e-mailadres van de gebruiker in te typen.

#### <a name="filter-and-columns"></a>Filteren en kolommen

![Selecteer Filter en Kolom om de resultaten in het diagram te wijzigen](./media/compliance-policy-monitor/filter-columns.png)

Wanneer u de knop **Filteren** selecteert, wordt het uitvoegfilter geopend met meer opties, inclusief de **nalevingsstatus**, apparaten die zijn **opengebroken** en meer. **Pas** het filter toe om de resultaten bij te werken.

Gebruik de eigenschap **Kolommen** om kolommen uit de diagramuitvoer toe te voegen of te verwijderen. Zo geeft **Principal-naam van gebruiker** mogelijk het e-mailadres weer dat is geregistreerd op het apparaat. **Pas** de kolommen toe om de resultaten bij te werken.

#### <a name="device-details"></a>Apparaatgegevens

Selecteer in de grafiek **Apparaatgegevens** een specifiek apparaat en selecteer **Apparaatnaleving**:

![Kies een specifiek apparaat en vervolgens Apparaatnaleving om het nalevingsbeleid te zien dat is toegepast](./media/compliance-policy-monitor/see-policies-applied-specific-device.png)

In Intune wordt meer gedetailleerde informatie weergegeven over de nalevingsbeleidsinstelling die op dat apparaat is toegepast. Wanneer u het specifieke beleid selecteert, worden alle instellingen in het beleid weergegeven.

### <a name="devices-without-compliance"></a>Apparaten zonder nalevingsbeleid

Op de pagina *Nalevingsstatus*, naast de grafiek *Beleidsnaleving*, kunt u de tegel **Apparaten zonder nalevingsbeleid** selecteren om informatie weer te geven over apparaten waaraan geen nalevingsbeleid is toegewezen:

![Apparaten zonder nalevingsbeleid bekijken](./media/compliance-policy-monitor/devices-without-policies.png)

Wanneer u de tegel selecteert, ziet u alle apparaten zonder nalevingsbeleid. U ziet ook de gebruiker van het apparaat, de status van de beleidsimplementatie en het apparaatmodel.

#### <a name="what-you-need-to-know"></a>Wat u dient te weten

- Bij de optie **Apparaten markeren waaraan geen nalevingsbeleid is toegewezen als** beveiligingsinstelling is het belangrijk om apparaten zonder nalevingsbeleid te identificeren. Vervolgens kunt u hier ten minste één nalevingsbeleid aan toewijzen.

  De beveiligingsinstelling kan worden geconfigureerd in de Intune-portal. Ga naar **Apparaten** > **Nalevingsbeleid** > **Instellingen van het nalevingsbeleid**. Stel vervolgens de optie **Apparaten markeren waaraan geen nalevingsbeleid is toegewezen** in op **Compatibel** of **Niet compatibel**.

  Lees meer informatie over deze [beveiligingsverbetering in de Intune-service](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/).

- Gebruikers aan wie een nalevingsbeleid van welk type dan ook is toegewezen, worden niet weergegeven in het rapport, ongeacht het apparaatplatform. Als u bijvoorbeeld een nalevingsbeleid voor Windows aan een gebruiker met een Android-apparaat hebt toegewezen, wordt het apparaat niet weergegeven in het rapport. Intune beschouwt echter dat Android-apparaat als niet compatibel. Om problemen te voorkomen, wordt aangeraden dat u beleid voor elk apparaatplatform maakt en dit naar alle gebruikers implementeert.

### <a name="per-policy-device-compliance"></a>Apparaatnaleving per beleid

In de grafiek **Beleidsnaleving** ziet u het beleid en het aantal apparaten dat compatibel en niet-compatibel is.

![Bekijk een overzicht van het beleid en het aantal compatibele apparaten ten opzichte van het aantal niet-compatibele apparaten voor dat beleid](./media/compliance-policy-monitor/idc-8.png)

### <a name="setting-compliance"></a>Naleving van instelling

In de grafiek **Naleving van instelling** worden alle instellingen van het nalevingsbeleid voor de apparaten van alle beleidsregels voor naleving, de platforms waarop de beleidsinstellingen zijn toegepast en het aantal niet-compatibele apparaten weergegeven.

![Een overzicht bekijken van alle instellingen in de verschillende beleidsregels](./media/compliance-policy-monitor/idc-10.png)

## <a name="view-compliance-reports"></a>Nalevingsrapporten weergeven

Naast het gebruik van de grafieken met betrekking tot de *Status van naleving* kunt u nalevingsrapporten bekijken op de pagina *Bewaken* van het beheercentrum.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Apparaten** > **Bewaken** en vervolgens onder **Naleving** het rapport dat u wilt bekijken. Enkele van de beschikbare nalevingsrapporten zijn:

   - Apparaatnaleving
   - Niet-compatibele apparaten
   - Apparaten zonder nalevingsbeleid
   - Naleving van instelling
   - Beleidsnaleving
   - Windows Health Attestation-rapport
   - Status van de dreigingsagent

Zie [Intune-rapporten](../fundamentals/reports.md) voor meer informatie over rapporten

## <a name="view-status-of-device-policies"></a>Status van apparaatbeleid weergeven

U kunt de verschillende statussen van uw beleid per platform controleren. U hebt bijvoorbeeld een macOS-nalevingsbeleid. U wilt de apparaten zien die worden beïnvloed door dit beleid en wilt weten of er conflicten of fouten zijn.

Deze functie is opgenomen in de statusrapportage voor het apparaat:

1. Selecteer **Apparaten** > **Nalevingsbeleid** > **Beleid**. Als een beleid is toegewezen, wordt een lijst met beleidsregels en meer informatie weergegeven.
2. Selecteer een beleid > **Overzicht**. In deze weergave bevat de beleidstoewijzing de volgende statussen:

    - **Geslaagd**: Het beleid is toegepast
    - **Fout**: Het beleid is niet toegepast. Het bericht wordt doorgaans weergegeven met een foutcode en een link naar een uitleg.
    - **Conflict**: Twee instellingen worden toegepast op hetzelfde apparaat en Intune kan het conflict niet oplossen. Dit moet door een beheerder worden bekeken.
    - **In behandeling**: Het apparaat is nog niet ingecheckt bij Intune om het beleid te ontvangen.
    - **Niet van toepassing**: Het apparaat kan het beleid niet ontvangen. Het beleid werkt bijvoorbeeld een instelling bij die specifiek voor iOS 11.1 is, maar het apparaat gebruikt iOS 10.

3. Selecteer een van de statussen voor informatie over de apparaten die dit beleid gebruiken. Selecteer bijvoorbeeld **Geslaagd**. In het volgende venster ziet u specifieke apparaatdetails, waaronder de apparaatnaam en de implementatiestatus.

## <a name="how-intune-resolves-policy-conflicts"></a>Hoe Intune beleidsconflicten oplost

Conflicterende beleidsinstellingen kunnen zich voordoen wanneer er meerdere Intune-beleidsregels op een apparaat worden toegepast. Als de beleidsinstellingen elkaar overlappen, lost Intune de conflicten aan de hand van de volgende regels op:

- Als de conflicterende instellingen uit een Intune-configuratiebeleid en een nalevingsbeleid voortkomen, hebben de instellingen in het nalevingsbeleid prioriteit boven de instellingen in het configuratiebeleid. Dit gebeurt zelfs als de instellingen in het configuratiebeleid veiliger zijn.

- Als u meerdere nalevingsbeleidsregels hebt geïmplementeerd, gebruikt Intune het veiligste beleid.
