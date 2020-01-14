---
title: Microsoft Intune reports
titleSuffix: Microsoft Intune
description: Intune biedt specifieke rapporttypen met gerichte weergaven die consistente en actuele gegevens bevatten.
keywords: ''
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.assetid: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3ae06ae3f9f76d86a792721d45f8319bfe6491fd
ms.sourcegitcommit: 8d7406b75ef0d75cc2ed03b1a5e5f74ff10b98c0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/03/2020
ms.locfileid: "75654223"
---
# <a name="intune-reports"></a>Intune-rapporten
Met Microsoft Intune-rapporten kunt u de status en activiteit van eindpunten in uw organisatie effectiever en proactief in de gaten houden. Het biedt ook andere rapportagegegevens in Intune. U kunt bijvoorbeeld rapporten zien over de compatibiliteit, de status en de trends van apparaten. Daarnaast kunt u aangepaste rapporten maken om meer specifieke gegevens te verkrijgen. 

> [!NOTE]
> De wijzigingen in de Intune-rapportage worden geleidelijk gedurende een bepaalde periode uitgebracht zodat u de nieuwe structuur kunt voorbereiden en u zich eraan kunt aanpassen.

De rapporttypen zijn ingedeeld in de volgende aandachtsgebieden:
- **Operationeel**: geeft actuele, gerichte gegevens waarmee u zich kunt concentreren en actie ondernemen. Beheerders, vakdeskundigen en de Helpdesk zullen deze rapporten erg nuttig vinden.
- **Organisatorisch**: biedt een uitgebreid overzicht van een algemene weergave, zoals de status van apparaatbeheer. Managers en beheerders zullen deze rapporten erg nuttig vinden.
- **Historisch**: bevat patronen en trends gedurende een bepaalde periode. Managers en beheerders zullen deze rapporten erg nuttig vinden.
- **Specialistisch**: hiermee kunt u onbewerkte gegevens gebruiken om uw eigen aangepaste rapporten te maken. Beheerders zullen deze rapporten erg nuttig vinden.

Het rapportageframework biedt een consistente en meer uitgebreide wijze van rapporteren. De beschikbare rapporten bieden de volgende functionaliteit:
- **Zoeken en sorteren**: u kunt zoeken en sorteren in alle kolommen, ongeacht de omvang van de gegevensset.
- **Gegevenspaginering**: u kunt uw gegevens scannen op basis van paginering, ofwel per pagina of door naar een specifieke pagina te springen.
- **Prestaties**: u kunt rapporten die zijn gemaakt op basis van grote tenants, snel genereren en weergeven.
- **Exporteren**: u kunt rapportagegegevens die zijn gegenereerd op basis van grote tenants, snel exporteren.

### <a name="who-can-access-the-data"></a>Wie hebben er toegang tot de gegevens?

Gebruikers met de volgende machtigingen kunnen logboeken bekijken:

- Hoofdbeheerder
- Intune-servicebeheerder
- Beheerders die zijn toegewezen aan een Intune-rol met machtigingen voor **Lezen**

## <a name="non-compliant-devices-report-operational"></a>Rapport over niet-compatibele apparaten (operationeel)
In het rapport Niet-compatibele apparaten komen gegevens aan de orde die doorgaans worden gebruikt door de Helpdesk of beheerdersrollen om problemen op te sporen en op te lossen. De gegevens uit deze rapporten zijn actueel, signaleren onverwacht gedrag en zijn bedoeld om actie te ondernemen. Het rapport is naast de werkbelasting beschikbaar, waardoor het rapport Niet-compatibele apparaten kan worden geopend zonder dat u actieve werkstromen hoeft te verlaten. Dit rapport bevat opties voor filteren, zoeken, pagineren en sorteren. U kunt ook inzoomen om problemen te helpen oplossen.

U kunt het rapport **Niet-compatibele apparaten** weergeven door de volgende stappen uit te voeren:

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Bewaken** > **Niet-compatibele apparaten**.

    ![Rapport Niet-compatibele apparaten](./media/intune-reports/intune-reports-02.png)

    > [!TIP]
    > Als u Intune eerder hebt gebruikt in Azure Portal, hebt u de bovenstaande gegevens in Azure Portal gevonden door u aan te melden bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en **Apparaatnaleving** > **Niet-compatibele apparaten** te selecteren.

## <a name="device-compliance-report-organizational"></a>Rapport Apparaatcompatibiliteit (organisatorisch)
Rapporten over apparaatcompatibiliteit zijn algemeen van aard en bieden een meer traditionele rapportageweergave van gegevens voor het identificeren van cumulatieve metrische gegevens. Dit rapport is ontworpen voor het werken met grote gegevenssets om een volledig beeld van de apparaatcompatibiliteit te krijgen. Het rapport over apparaatcompatibiliteit toont bijvoorbeeld alle compatibiliteitsstatussen voor apparaten om een meer algemeen overzicht van de gegevens te geven, ongeacht de omvang van de gegevensset. In dit rapport wordt de volledige onderverdeling van records weergegeven en bovendien een handige visualisatie van cumulatieve metrische gegevens. Dit rapport kan worden gegenereerd door er filters op toe te passen en de knop Rapport genereren te selecteren. Hierdoor worden de gegevens vernieuwd en wordt de meest recente status weergegeven, met de mogelijkheid om de afzonderlijke records weer te geven waaruit de cumulatieve gegevens zijn samengesteld. Net als bij de meeste rapporten in het nieuwe framework kunnen deze records worden gesorteerd en doorzocht, zodat u zich kunt richten op de informatie die u nodig hebt. 

Als u een gegenereerd rapport over een apparaatstatus wilt zien, kunt u de volgende stappen uitvoeren:
1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Rapporten** om een samenvatting van de rapporten te bekijken.
3. Selecteer **Apparaatnaleving**.
4. Selecteer de filters **Compatibiliteitsstatus**, **OS** en **Eigendom** om het rapport te verfijnen.
5. Klik op **Rapport genereren** (of **Opnieuw genereren**) om de huidige gegevens op te halen.

    ![Rapport Apparaatcompatibiliteit](./media/intune-reports/intune-reports-02a.png)

    > [!NOTE]
    > Het rapport **Apparaatcompatibiliteit** bevat een tijdstempel van het moment waarop het rapport voor het laatst is gegenereerd. 

Zie [Naleving voor Microsoft Defender ATP met voorwaardelijke toegang in Intune afdwingen](~/protect/advanced-threat-protection.md) voor gerelateerde informatie.

## <a name="reports-summary"></a>Rapportenoverzicht 

Het rapport Apparaatcompatibiliteit is beschikbaar als overzichtsrapport in de werkbelasting **Rapporten**. Gebruik de volgende stappen om het rapport Apparaatcompatibiliteit weer te geven:

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Rapporten** om een samenvatting van de rapporten te bekijken.

    ![Rapportenoverzicht van Intune](./media/intune-reports/intune-reports-01.png)

## <a name="device-compliance-trend-report-historical"></a>Trendrapport Apparaatcompatibiliteit (historisch)
Trendrapporten over apparaatcompatibiliteit worden waarschijnlijk meer gebruikt door beheerders en architecten om langetermijntrends te identificeren voor apparaatcompatibiliteit. De cumulatieve gegevens worden gedurende een bepaalde periode weergegeven en zijn handig voor het maken van toekomstige investeringsbeslissingen, het bevorderen van procesverbeteringen of het stimuleren van onderzoek naar eventuele afwijkingen. Filters kunnen ook worden toegepast om specifieke trends te bekijken. De gegevens die in dit rapport worden gegeven, zijn een momentopname van de huidige tenantstatus (bijna in realtime). 

Een trendrapport over trends in apparaatcompatibiliteit kan gedurende een bepaalde periode de trend van de compatibiliteitsstatussen van het apparaat tonen. U kunt nagaan waar compatibiliteitspieken zijn opgetreden en uw tijd en inspanningen op basis hiervan focussen.

U kunt het rapport **Trends** weergeven door de volgende stappen uit te voeren:

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Rapporten** > **Trends** om de apparaatcompatibiliteit te bekijken voor een 60-daagse trend.

    ![Trendrapport van Intune](./media/intune-reports/intune-reports-03.png)

## <a name="azure-monitor-integration-reports-specialist"></a>Azure Monitor-integratierapporten (specialistisch)
U kunt uw eigen rapporten aanpassen om de gewenste gegevens op te halen. De gegevens in uw rapporten zijn optioneel beschikbaar via [Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) met behulp van [Log Analytics](reports.md#log-analytics) en [Azure Monitor-werkmappen](reports.md#workbooks). Met deze oplossingen kunt u aangepaste query's maken, waarschuwingen configureren en dashboards maken om de compatibiliteitsgegevens van het apparaat op de gewenste manier weer te geven. Daarnaast kunt u de activiteitenlogboeken in uw Azure Storage-account bewaren, integreren met de rapporten met behulp van [security information and event management (SIEM) tools](https://docs.microsoft.com/microsoft-365/security/office-365-security/siem-server-integration) (hulpprogramma's voor SIEM (Security Information and Event Management)) en de rapporten correleren met Azure AD-activiteitenlogboeken. Azure Monitor-werkmappen kunnen worden gebruikt naast het importeren van dashboards indien er behoefte is aan aangepaste rapportage.

> [!NOTE]
> Voor de functionaliteit van complexe rapporten is een Azure-abonnement vereist.

Zo zou bijvoorbeeld een gespecialiseerd rapport gegevens over het eigendom van het apparaat correleren met gegevens over platforminschrijving in een aangepast rapport. Dit aangepaste rapport kan vervolgens worden weergegeven op een bestaand dashboard in de Azure Active Directory-portal.

U kunt aangepaste rapporten maken en weergeven met behulp van de volgende stappen:

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Rapporten** > **Diagnostische instellingen** en voeg een [diagnostische instelling](reports.md#diagnostic-settings) toe.

    ![Rapportenoverzicht van Intune](./media/intune-reports/intune-reports-04.png)

3. Klik op **Diagnostische instelling toevoegen** om het deelvenster **Diagnostische instellingen** weer te geven. 
4. Voeg een **naam** toe voor de diagnostische instellingen. 
5. Selecteer de instellingen **Verzenden naar Log Analytics** en **DeviceComplianceOrg**.

    ![Rapportenoverzicht van Intune](./media/intune-reports/intune-reports-04a.png)

6. Klik op **Opslaan**.
7. Selecteer vervolgens **Log Analytics** om een nieuwe logboekquery te maken en uit te voeren met behulp van [Log Analytics](reports.md#log-analytics).

   ![Log Analytics: logboekquery](./media/intune-reports/intune-reports-05.png)

8. Selecteer **Werkmappen** om een interactief rapport te maken of openen met behulp van [Azure Monitor-werkmappen](reports.md#workbooks).

   ![Werkmappen: interactieve rapporten](./media/intune-reports/intune-reports-07.png)

### <a name="diagnostic-settings"></a>Diagnostische instellingen
Elke Azure-resource vereist een eigen diagnostische instelling. De diagnostische instelling definieert het volgende voor een resource:

- Categorieën van logboeken en metrische gegevens die worden verzonden naar de doelen die in de instelling zijn gedefinieerd. De beschikbare categorieën verschillen per resourcetype.
- Een of meer doelen voor het verzenden van de logboeken. Huidige doelen omvatten Log Analytics-werkruimte, Event Hubs en Azure Storage.
- Bewaarbeleid voor gegevens die zijn opgeslagen in Azure Storage.

Met één diagnostische instelling kan een van beide doelen worden gedefinieerd. Als u gegevens wilt verzenden naar meer dan één bepaald type doel (bijvoorbeeld twee verschillende Log Analytics-werkruimten), maakt u meerdere instellingen. Elke resource kan maximaal vijf diagnostische instellingen hebben.

Zie [Diagnostische instelling maken voor het verzamelen van platformlogboeken en metrische gegevens in Azure](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-settings) voor meer informatie over diagnostische instellingen.

### <a name="log-analytics"></a>Log Analytics
Log Analytics is het primaire hulpprogramma in de Azure-portal voor het schrijven van logboekquery's en het interactief analyseren van de resultaten van de query's. Zelfs als een logboekquery elders in Azure Monitor wordt gebruikt, moet u de query doorgaans eerst schrijven en testen met behulp van Log Analytics. Zie [Overzicht van logboekquery's in Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/log-query/log-query-overview) voor meer informatie over het gebruik van Log Analytics en het maken van logboekquery's. 

### <a name="workbooks"></a>Werkmappen
Werkmappen combineren tekst, query's van Log Analytics, metrische gegevens van Azure en parameters in uitgebreide interactieve rapporten. Werkmappen kunnen worden bewerkt door andere teamleden die toegang hebben tot dezelfde Azure-resources. Zie [Azure Monitor-werkmappen](https://docs.microsoft.com/azure/azure-monitor/app/usage-workbooks) voor meer informatie over werkmappen. U kunt ook werken met werkmapsjablonen en eraan bijdragen. Zie [Azure Monitor Workbook Templates](https://go.microsoft.com/fwlink/?linkid=867045) (Azure Monitor-werkmapsjablonen) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen 

Meer informatie over de volgende technologieën:
- [Blog - Microsoft Intune reporting framework](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Reporting-Framework-Coming-to-Intune/ba-p/1009553) (Blog: Microsoft Intune-rapportageframework)
- [Azure Monitor](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-activity-logs-azure-monitor)
- [Wat is Log Analytics?](https://docs.microsoft.com/azure/azure-monitor/log-query/log-query-overview#what-is-log-analytics)
- [Logboekquery's](https://docs.microsoft.com/azure/azure-monitor/log-query/log-query-overview)
- [Aan de slag met Log Analytics in Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/log-query/get-started-portal)
- [Azure Monitor-werkmappen](https://docs.microsoft.com/azure/azure-monitor/app/usage-workbooks)
- [Security information and event management (SIEM) tools](https://docs.microsoft.com/microsoft-365/security/office-365-security/siem-server-integration) (Hulpprogramma's voor SIEM (Security Information and Event Management))
