---
title: Nalevingsbeleid voor apparaten bewaken in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik het apparaatnalevingsdashboard om de algehele apparaatnaleving te bewaken, rapporten te bekijken en de apparaatnaleving per beleidsregel en per instelling te bekijken.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8711b4c71c3581bde9ed1de8a5cc02f6b1a07ca7
ms.sourcegitcommit: d8edd1c3d24123762dd6d14776836df4ff2a31dd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2018
ms.locfileid: "51576899"
---
# <a name="monitor-intune-device-compliance-policies"></a>Nalevingsbeleid voor Intune-apparaten controleren

U kunt met behulp van nalevingsrapporten apparaatcompatibiliteit controleren en problemen met betrekking tot naleving in uw organisatie oplossen. Met behulp van deze rapporten, kunt u informatie bekijken over:

- De algemene nalevingsstatussen van apparaten
- De nalevingsstatus voor een specifieke instelling
- De nalevingsstatus voor een specifiek beleid
- Inzoomen op afzonderlijke apparaten om specifieke instellingen en beleidsregels te bekijken die van invloed zijn op het apparaat

## <a name="open-the-compliance-dashboard"></a>Het nalevingsdashboard openen

Open het **dashboard voor apparaatnaleving van Intune**:

1. Selecteer in [Azure Portal](https://portal.azure.com) **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.

2. Selecteer **Apparaatnaleving** > **Overzicht**. Het **dashboard voor apparaatnaleving** wordt geopend.

> [!IMPORTANT]
> Apparaten moeten worden ingeschreven bij Intune om het nalevingsbeleid voor apparaten te ontvangen.

## <a name="dashboard-overview"></a>Dashboardoverzicht

Als het dashboard wordt geopend, krijgt u een overzicht met alle nalevingsrapporten. U kunt in deze rapporten de volgende onderdelen bekijken en controleren:

- Algehele apparaatnaleving
- Apparaatnaleving per beleid
- Apparaatnaleving per instelling
- Status van de apparaatbeveiliging
- Status van de dreigingsagent

![In de dashboardafbeelding ziet u het dashboard voor apparaatnaleving en de verschillende rapporten](./media/compliance-policy-monitor/idc-1.png)

Als u dieper wilt ingaan op deze rapporten, kunt u tevens specifieke nalevingsbeleidsregels en instellingen bekijken die betrekking hebben op een specifiek apparaat, met inbegrip van de nalevingsstatus voor elke instelling.

### <a name="device-compliance-status-report"></a>Statusrapport apparaatnaleving

De grafiek toont de nalevingsstatus voor alle bij Intune geregistreerde apparaten. De statussen van apparaatnaleving worden opgeslagen in twee verschillende databases: Intune en Azure Active Directory. 

Beschrijvingen van verschillende statussen van het nalevingsbeleid voor apparaten:

- **Compatibel**: op het apparaat zijn een of meer nalevingsbeleidsinstellingen voor apparaten toegepast.

- **In respijtperiode:** het apparaat is het doelwit van een of meer nalevingsbeleidsinstellingen voor apparaten. Maar de gebruiker heeft het beleid nog niet toegepast. Dit betekent dat het apparaat niet compatibel is, maar zich in de respijtperiode bevindt die door de beheerder is vastgesteld.

  - Meer informatie over [Acties voor niet-compatibele apparaten](actions-for-noncompliance.md).

- **Niet geëvalueerd**: een initiële status voor nieuw geregistreerde apparaten. Of apparaten die niet aan nalevingsbeleid zijn toegewezen en geen trigger bevatten voor de controle op naleving.

- **Niet compatibel**: op het apparaat kan een of meer nalevingsbeleidsinstellingen voor apparaten niet worden toegepast. Of de gebruiker heeft niet voldaan aan het beleid.

- **Het apparaat is niet gesynchroniseerd:** voor het apparaat is de nalevingsbeleidsstatus niet doorgegeven, om een van de volgende redenen:

  - **Onbekend**: het apparaat is offline of kan om andere redenen niet communiceren met Intune of Azure AD.

  - **Fout**: het apparaat kan niet communiceren met Intune en Azure AD en heeft een foutbericht met de reden ontvangen.

> [!IMPORTANT]
> Apparaten die zijn ingeschreven bij Intune, maar waarop geen nalevingsbeleid voor apparaten is gericht, worden in dit rapport opgenomen onder de bucket **Compatibel**.

#### <a name="drill-down-for-more-details"></a>Inzoomen voor meer details

Selecteer een status in het diagram **Nalevingstatus apparaten**. Selecteer bijvoorbeeld de status **Niet compatibel**:

![De status Niet compatibel kiezen](./media/compliance-policy-monitor/select-not-compliant-status.png)

Hier ziet u meer informatie over de apparaten met die status, met inbegrip van besturingssysteemplatform en datum van laatste check-in en meer. 

![In de dashboardafbeelding ziet u meer informatie over het apparaat met die specifieke status](./media/compliance-policy-monitor/drill-down-details.png)

Als u alle apparaten wilt zien van een specifieke gebruiker, kunt u het diagramrapport ook filteren door het e-mailadres van de gebruiker in te typen.

#### <a name="filter-and-columns"></a>Filteren en kolommen

![Selecteer Filter en Kolom om de resultaten in het diagram te wijzigen](./media/compliance-policy-monitor/filter-columns.png)

Wanneer u de knop **Filteren** selecteert, wordt het uitvoegfilter geopend met meer opties, met inbegrip van de nalevingsstatus en apparaten die zijn opengebroken en meer. **Pas** het filter toe om de resultaten bij te werken.

Gebruik de eigenschap **Kolommen** om kolommen uit de diagramuitvoer toe te voegen of te verwijderen. Zo geeft **Principal-naam van gebruiker** mogelijk het e-mailadres weer dat is geregistreerd op het apparaat. **Pas** de kolommen toe om de resultaten bij te werken.

#### <a name="device-details"></a>Apparaatgegevens

Selecteer een apparaat in het diagram en selecteer vervolgens **Apparaatnaleving**:

![Kies een specifiek apparaat en vervolgens Apparaatnaleving om het nalevingsbeleid te zien dat is toegepast](./media/compliance-policy-monitor/see-policies-applied-specific-device.png)

Hier vindt u meer gedetailleerde informatie over de nalevingsbeleidsinstelling die op dat apparaat is toegepast. Wanneer u het specifieke beleid selecteert, worden alle instellingen in het beleid weergegeven.

### <a name="devices-without-compliance-policy"></a>Apparaten zonder nalevingsbeleid
In **Apparaatnaleving** > **Overzicht** worden tevens de apparaten vermeld waaraan geen nalevingsbeleidsregels zijn toegewezen:

![Apparaten zonder nalevingsbeleid bekijken](./media/compliance-policy-monitor/devices-without-policies.png)

Wanneer u de tegel selecteert, ziet u alle apparaten zonder nalevingsbeleid. U ziet ook de gebruiker van het apparaat, de status van de beleidsimplementatie en het apparaatmodel.

#### <a name="what-you-need-to-know"></a>Wat u dient te weten

- Bij de optie **Apparaten markeren waaraan geen nalevingsbeleid is toegewezen als** beveiligingsinstelling is het belangrijk om apparaten zonder nalevingsbeleid te identificeren. Vervolgens kunt u hier ten minste één nalevingsbeleid aan toewijzen.

  De beveiligingsinstelling kan worden geconfigureerd in de Intune-portal. Selecteer **Apparaatnaleving** > **Instellingen voor nalevingsbeleid**. Stel vervolgens de optie **Apparaten markeren waaraan geen nalevingsbeleid is toegewezen** in op **Compatibel** of **Niet compatibel**. 

  Lees meer informatie over deze [beveiligingsverbetering in de Intune-service](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/).

- Gebruikers aan wie een nalevingsbeleid van welk type dan ook is toegewezen, worden niet weergegeven in het rapport, ongeacht het apparaatplatform. Als u bijvoorbeeld een nalevingsbeleid voor Windows aan een gebruiker met een Android-apparaat hebt toegewezen, wordt het apparaat niet weergegeven in het rapport. Intune beschouwt echter dat Android-apparaat als niet compatibel. Om problemen te voorkomen, wordt aangeraden dat u beleid voor elk apparaatplatform maakt en dit naar alle gebruikers implementeert.

### <a name="per-policy-device-compliance-report"></a>Rapport apparaatnaleving per beleid

In het rapport **Apparaatnaleving** > **Beleidsnaleving** ziet u het beleid en het aantal apparaten dat compatibel en niet compatibel is. 

![Bekijk een overzicht van het beleid en het aantal compatibele apparaten ten opzichte van het aantal niet-compatibele apparaten voor dat beleid](./media/compliance-policy-monitor/idc-8.png)

Wanneer u een specifiek beleid selecteert, kunt u de **nalevingsstatus**, de **e-mailalias van de gebruiker**, het **apparaatmodel** en de **locatie** zien voor elk apparaat waarvoor dat nalevingsbeleid is bedoeld.

## <a name="setting-compliance-report"></a>Rapport nalevingsinstellingen

In het rapport **Apparaatcompliantie** > **Nalevingsinstelling** kunt u per nalevingsinstelling het totale aantal apparaten in elke nalevingsstatus bekijken. Hierin worden alle instellingen van het apparaatnalevingsbeleid, alle beleidsregels voor naleving, de platforms waarop de beleidsinstellingen zijn toegepast en het aantal niet-compatibele apparaten weergegeven.

![Een overzicht bekijken van alle instellingen in de verschillende beleidsregels](./media/compliance-policy-monitor/idc-10.png)

Wanneer u een specifieke instelling selecteert, kunt u de **nalevingsstatus**, de **e-mailalias van de gebruiker**, het **apparaatmodel** en de **locatie** zien voor elk apparaat waarvoor die instelling is bedoeld.

> [!NOTE]
> Windows 10-apparaten die aan Azure AD zijn toegevoegd, kunnen het systeemaccount als een niet-conforme gebruiker weergeven. Dit is het verwachte gedrag en heeft geen invloed op de algemene naleving van het apparaat. 

## <a name="view-status-of-device-policies"></a>Status van apparaatbeleid weergeven

U kunt de verschillende statussen van uw beleid per platform controleren. U hebt bijvoorbeeld een macOS-nalevingsbeleid. U wilt de apparaten zien die worden beïnvloed door dit beleid en wilt weten of er conflicten of fouten zijn.

Deze functie is opgenomen in de statusrapportage voor het apparaat:

1. Selecteer **Apparaatnaleving** > **Beleid**. Als een beleid is toegewezen, wordt een lijst met beleidsregels en meer informatie weergegeven.
2. Selecteer een beleid > **Overzicht**. In deze weergave bevat de beleidstoewijzing de volgende statussen:

    - Geslaagd: het beleid is toegepast
    - Fout: het beleid is niet toegepast. Het bericht wordt doorgaans weergegeven met een foutcode en een link naar een uitleg. 
    - Conflict: twee instellingen worden toegepast op hetzelfde apparaat en Intune kan het conflict niet oplossen. Dit moet door een beheerder worden bekeken.
    - In behandeling: het apparaat heeft niet nog ingecheckt bij Intune om het beleid te ontvangen. 
    - Niet van toepassing: het apparaat kan het beleid niet ontvangen. Het beleid werkt bijvoorbeeld een instelling bij die specifiek voor iOS 11.1 is, maar het apparaat gebruikt iOS 10. 

3. Selecteer een van de statussen voor informatie over de apparaten die dit beleid gebruiken. Selecteer bijvoorbeeld **Geslaagd**. In het volgende venster ziet u specifieke apparaatdetails, waaronder de apparaatnaam en de implementatiestatus.

## <a name="how-intune-resolves-policy-conflicts"></a>Hoe Intune beleidsconflicten oplost
Conflicterende beleidsinstellingen kunnen zich voordoen wanneer er meerdere Intune-beleidsregels op een apparaat worden toegepast. Als de beleidsinstellingen elkaar overlappen, lost Intune de conflicten aan de hand van de volgende regels op:

- Als de conflicterende instellingen uit een Intune-configuratiebeleid en een nalevingsbeleid voortkomen, hebben de instellingen in het nalevingsbeleid prioriteit boven de instellingen in het configuratiebeleid. Dit gebeurt zelfs als de instellingen in het configuratiebeleid veiliger zijn.

- Als u meerdere nalevingsbeleidsregels hebt geïmplementeerd, gebruikt Intune het veiligste beleid.
