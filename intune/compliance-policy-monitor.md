---
title: Nalevingsbeleid voor apparaten bewaken in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik het apparaatnalevingsdashboard om de algehele apparaatnaleving te bewaken, rapporten te bekijken en de apparaatnaleving per beleidsregel en per instelling te bekijken.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5e9de6f1ac8bca1d65a94294d3b049dfccbe44c7
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905356"
---
# <a name="monitor-intune-device-compliance-policies"></a>Nalevingsbeleid voor Intune-apparaten controleren

Nalevingsrapporten helpen beheerders het nalevingspostuur van apparaten in hun organisatie te analyseren en snel de door gebruikers binnen hun organisatie aangetroffen problemen met naleving op te lossen. U kunt informatie weergeven over de algemene nalevingsstatus van apparaten, de nalevingsstatus voor een specifieke instelling en de nalevingsstatus voor een specifiek beleid, en inzoomen op afzonderlijke apparaten om specifieke instellingen en beleidsregels die van invloed zijn op het apparaat weer te geven.

## <a name="before-you-begin"></a>Voordat u begint

Volg deze stappen om te zoeken naar het **Intune-dashboard voor apparaatnaleving** in Azure Portal:

1. Meld u in [Azure Portal](https://portal.azure.com) aan met uw Intune-referenties.

2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.

3. Selecteer **Apparaatnaleving** > **Overzicht**. Het **dashboard voor apparaatnaleving** wordt geopend.

> [!IMPORTANT]
> Apparaten moeten worden ingeschreven bij Intune om het nalevingsbeleid voor apparaten te ontvangen.

## <a name="device-compliance-dashboard"></a>Dashboard voor apparaatnaleving

In het **dashboard voor apparaatnaleving** kunt u de compatibiliteit van verschillende apparaten, hun beveiligingsstatus en meer bewaken. U kunt de volgende rapporten bekijken:

- Cumulatieve algehele apparaatnaleving

- Apparaatnaleving per beleid

- Apparaatnaleving per instelling

- Status van de apparaatbeveiliging

- Status van de dreigingsagent

![Afbeelding met het dashboard voor apparaatnaleving](./media/idc-1.png)

U kunt ook de specifieke nalevingsbeleidsregels en -instellingen bekijken die van toepassing zijn op een bepaald apparaat en de laatste nalevingsstatus voor elk van deze instellingen op het apparaat weergeven.

### <a name="overall-device-compliance-aggregate-report"></a>Rapport cumulatieve algehele apparaatnaleving

Dit is een ringdiagram met de cumulatieve nalevingsstatus voor alle bij Intune ingeschreven apparaten. De nalevingsstatussen van een apparaat worden opgeslagen in twee verschillende databases, te weten Intune en Azure Active Directory. Hieronder vindt u meer informatie over de statussen van het nalevingsbeleid van het apparaat:

- **Compatibel**: op het apparaat is een of meer nalevingsbeleidsinstellingen voor apparaten toegepast waarop de beheerder zich richt.

- **Niet-compatibel:** op het apparaat is een of meer nalevingsbeleidsinstellingen niet toegepast waarop de beheerder zich richt, of de gebruiker voldoet niet aan de beleidsregels waarop de beheerder zich richt.

- **In respijtperiode:** de beheerder heeft of meer nalevingsbeleidsinstellingen voor apparaten gericht op het apparaat, maar de gebruiker heeft het beleid nog niet toegepast, wat betekent dat het apparaat niet compatibel is, maar zich in de respijtperiode bevindt die door de beheerder is vastgesteld.

  - Meer informatie over Acties voor niet-compatibele apparaten.

- **Het apparaat is niet gesynchroniseerd:** voor het apparaat is de nalevingsbeleidsstatus niet doorgegeven, om een van de volgende redenen:

  - **Onbekend**: het apparaat is offline of kan om andere redenen niet communiceren met Intune of Azure AD.

  - **Fout**: het apparaat kan niet communiceren met Intune en Azure AD en heeft een foutbericht met de reden ontvangen.

> [!IMPORTANT]
> Apparaten die zijn ingeschreven bij Intune, maar waarop geen nalevingsbeleid voor apparaten is gericht, worden in dit rapport opgenomen onder de bucket **Compatibel**.

#### <a name="drill-down-option"></a>Inzoomoptie

Selecteer in het **dashboard voor apparaatnaleving** een tegel voor apparaatnaleving om in te zoomen op een specifieke **nalevingsstatus**, **e-mailalias van de gebruiker**, **apparaatmodel** en **locatie**  voor elk apparaat waarop het nalevingsbeleid voor apparaten is gericht.

![Afbeelding ingezoomd op het dashboard voor apparaatnaleving](./media/idc-2.png)

Als u meer informatie over een specifieke gebruiker nodig hebt, kunt u filteren in het rapport Apparaatnalevingsgrafiek door de e-mailalias van de gebruiker in te voeren.

![Afbeelding met een gebruiker in het dashboard voor apparaatnaleving](./media/idc-3.png)

U kunt ook op de afwijkende nalevingsstatus in de Apparaatnalevingsgrafiek klikken voor meer informatie over statussen van de gebruiker met betrekking tot het nalevingsbeleid.

![Afbeelding met verschillende statussen in het dashboard voor apparaatnaleving](./media/idc-4.png)

#### <a name="filter"></a>Filter

Wanneer u de **knop Filteren** selecteert, wordt het uitvoegfilter geopend met de volgende opties:

- Model

  - Tekstvak waarin een vrije zoekreeks kan worden ingevoerd

- Platform

  - Android

  - iOS

  - macOS

  - Windows

  - Windows Phone

- Status

  - Compliant

  - Niet compatibel

  - In Respijtperiode

  - Onbekend

  - Fout

Wanneer u de **knop Bijwerken** selecteert, wordt het uitvoegfilter gesloten en worden resultaten bijgewerkt aan de hand van de geselecteerde filtercriteria.

##### <a name="device-details"></a>Apparaatgegevens

Wanneer u een apparaat selecteert, wordt **Apparaten** geopend met het apparaat geselecteerd. Hier vindt u gedetailleerde informatie over de nalevingsbeleidsinstelling die op het apparaat is toegepast.

Wanneer u het nalevingsbeleid voor apparaten zelf selecteert, ziet u de naam van het nalevingsbeleid waaruit de nalevingsinstelling afkomstig is waarop de beheerder zich richt.

### <a name="devices-without-compliance-policy"></a>Apparaten zonder nalevingsbeleid
In dit rapport worden de apparaten vermeld waaraan geen nalevingsbeleidsregels zijn toegewezen. Bij de introductie van de beveiligingsinstelling waarmee alle apparaten zonder nalevingsbeleid als Niet-compatibel worden gemarkeerd, is het belangrijk om deze apparaten te kunnen identificeren. Vervolgens kunt u hier ten minste één nalevingsbeleid aan toewijzen.

> [!NOTE]
> De nieuwe beveiligingsinstelling kan worden geconfigureerd in de Intune-portal. Selecteer **Apparaatnaleving** en klik onder **Setup** de optie **Instellingen van het nalevingsbeleid**. Gebruik vervolgens de wisselknop om **Apparaten markeren waaraan geen nalevingsbeleid is toegewezen** in te stellen op **Compatibel** of **Niet compatibel**. Lees meer informatie over deze [beveiligingsverbetering in de Intune-service](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/).

![Afbeelding van rapport Apparaten zonder nalevingsbeleid](./media/idc-12.png)

De tegel **Apparaten zonder nalevingsbeleid** is beschikbaar vanuit het dashboard Apparaatnaleving. U ziet hier alle apparaten zonder een nalevingsbeleid, de gebruiker van het apparaat, de nalevingsstatus en het apparaatmodel.

> [!NOTE]
> Gebruikers aan wie een nalevingsbeleid van welk type dan ook is toegewezen, worden niet weergegeven in het rapport, ongeacht het apparaatplatform. Als u bijvoorbeeld per ongeluk een nalevingsbeleid voor Windows aan een gebruiker met een Android-apparaat hebt toegewezen, wordt het apparaat niet weergegeven in het rapport. Intune beschouwt dat Android-apparaat echter als niet-compatibel. Om problemen te voorkomen, wordt aangeraden dat u beleid voor elk apparaatplatform maakt en dit naar alle gebruikers implementeert.

### <a name="per-policy-device-compliance-report"></a>Rapport apparaatnaleving per beleid

Dit rapport biedt een weergave per nalevingsbeleid en het totale aantal apparaten in elke nalevingsstatus. De tegel **Beleidsnaleving** is beschikbaar vanuit het **Dashboard voor apparaatnaleving**. Hierin worden alle beleidsregels die zijn gemaakt door de beheerder, de platforms waarop het beleid wordt toegepast, het aantal compatibele apparaten en het aantal niet-compatibele apparaten weergegeven.

![Afbeelding met het rapport voor apparaatnaleving per beleid](./media/idc-8.png)

Als u op de tegel Beleidsnaleving klikt, en vervolgens klikt op een van de nalevingsbeleidsregels voor apparaten, ziet u de **nalevingsstatus**, het **e-mailalias van de gebruiker**, het **apparaatmodel** en de **locatie** voor elk apparaat waarop dat nalevingsbeleid voor apparaten is gericht.

## <a name="setting-compliance-report"></a>Rapport nalevingsinstellingen

Met dit rapport kunt u per nalevingsinstelling het totale aantal apparaten in elke nalevingsstatus bekijken. De tegel **Naleving van instellingen** is beschikbaar vanuit het **dashboard voor apparaatnaleving**. Hierin worden alle nalevingsbeleidsinstellingen voor apparaten van alle nalevingsbeleidsregels voor apparaten die door de beheerder zijn gemaakt, de platforms waarop de beleidsinstellingen zijn toegepast en het aantal niet-compatibele apparaten weergegeven.

![Afbeelding met het rapport voor apparaatnaleving per instelling](./media/idc-10.png)

Als u op de tegel Naleving van instelling klikt, en vervolgens klikt op een van de nalevingsbeleidsinstellingen voor apparaten, ziet u de **nalevingsstatus**, het **e-mailalias van de gebruiker**, het **apparaatmodel** en de **locatie** voor elk apparaat waarop die nalevingsbeleidsinstelling voor apparaten is gericht.

## <a name="view-status-of-device-policies"></a>Status van apparaatbeleid weergeven

U kunt de verschillende statussen van uw beleid per platform controleren. U hebt bijvoorbeeld een macOS-nalevingsbeleid. U wilt de apparaten zien die worden beïnvloed door dit beleid en wilt weten of er conflicten of fouten zijn.

Deze functie is opgenomen in de statusrapportage voor het apparaat:

1. Selecteer **Apparaatnaleving** > **Beleid**. Als een beleid is toegewezen, wordt een lijst met beleidsregels en meer informatie weergegeven.
2. Selecteer een beleid > **Overzicht**. In deze weergave bevat de beleidstoewijzing de volgende statussen:

  - Geslaagd
  - Fout
  - Conflict
  - In behandeling
  - Niet van toepassing

3. Selecteer een van de statussen voor informatie over de apparaten die dit beleid gebruiken. Selecteer bijvoorbeeld **Geslaagd**. In het volgende venster ziet u specifieke apparaatdetails, waaronder de apparaatnaam en de implementatiestatus.

## <a name="how-intune-resolves-policy-conflicts"></a>Hoe Intune beleidsconflicten oplost
Conflicterende beleidsinstellingen kunnen zich voordoen wanneer er meerdere Intune-beleidsregels op een apparaat worden toegepast. Als de beleidsinstellingen elkaar overlappen, lost Intune de conflicten aan de hand van de volgende regels op:

- Als de conflicterende instellingen uit een Intune-configuratiebeleid en een nalevingsbeleid voortkomen, hebben de instellingen in het nalevingsbeleid prioriteit boven de instellingen in het configuratiebeleid. Dit gebeurt zelfs als de instellingen in het configuratiebeleid veiliger zijn.

- Als u meerdere nalevingsbeleidsregels hebt geïmplementeerd, gebruikt Intune het veiligste beleid.

