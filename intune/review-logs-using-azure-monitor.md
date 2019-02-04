---
title: Auditlogboeken in Azure Monitor routeren met behulp van Monitor Intune - Azure | Microsoft Docs
description: Gebruik Diagnostische instellingen om auditlogboeken en operationele logboeken in Microsoft Intune te verzenden naar opslagaccounts, Event Hubs of Log Analytics in Azure. Kies hoe lang u de gegevens wilt behouden en bekijk de geschatte kosten voor tenants van verschillende groottes.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 6323eda16ef54df3cb14f9a8dd4f8349e51d1b01
ms.sourcegitcommit: 17f58d35a6bdff3e179662f3731fc74d39144470
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/28/2019
ms.locfileid: "55105150"
---
# <a name="send-log-data-to-storage-event-hubs-or-log-analytics-in-intune-preview"></a>Logboekgegevens verzenden naar opslag, Event Hubs of Log Analytics in Intune (preview)

Microsoft Intune omvat ingebouwde logboeken die informatie bieden over uw omgeving. In **auditlogboeken** worden details weergegeven van verschillende gebeurtenissen of taken in Intune. In **Operationele logboeken (preview)** worden details weergegeven van gebruikers en apparaten waarvan de inschrijving is geslaagd (of niet).

Deze logboeken kunnen ook worden verzonden naar Azure Monitor-services, inclusief opslagaccounts, Event Hubs, en Log Analytics. Meer specifiek, u kunt:

* Intune-logboeken archiveren in een Azure-opslagaccount om de gegevens te behouden of gedurende een ingestelde periode te archiveren.
* Intune-logboeken naar een Azure Event Hub streamen voor analyse met behulp van populaire SIEM-hulpprogramma’s (Security Information and Event Management), zoals Splunk en QRadar.
* Intune-logboeken integreren met uw eigen aangepaste logboekoplossingen door ze naar een Event Hub te streamen.
* Intune-logboeken naar Log Analytics verzenden om rijke visualisaties, bewaking, en waarschuwingen mogelijk te maken voor de verbonden gegevens.

Deze functies maken deel uit van de **Diagnostische instellingen** in Intune. 

In dit artikel ziet u hoe u **Diagnostische instellingen** kunt gebruiken om logboekgegevens te verzenden naar verschillende services. Ook worden er voorbeelden gegeven van de geschatte kosten, en wordt een aantal veelgestelde vragen beantwoord.

## <a name="prerequisites"></a>Vereisten

U hebt het volgende nodig om deze functie te gebruiken:

* Een Azure-abonnement: Als u niet over een Azure-abonnement beschikt, kunt u [zich registreren voor een gratis proefversie](https://azure.microsoft.com/free/).
* Een Microsoft Intune-omgeving (tenant) in Azure
* Een gebruiker die **Globale beheerder** of **Intune-servicebeheerder** is voor de Intune-tenant.

Afhankelijk van waarheen u de auditlogboekgegevens wilt routeren, hebt u een van de volgende services nodig:

* Een [Azure-opslagaccount](https://docs.microsoft.com/azure/storage/common/storage-account-overview) met *ListKeys*-machtigingen. We raden u aan om een algemeen opslagaccount te gebruiken en geen blob-opslagaccount. Zie de [Prijscalculator voor Azure Storage](https://azure.microsoft.com/pricing/calculator/?service=storage) voor prijsinformatie over opslag. 
* Een [naamruimte voor Azure Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-create#create-an-event-hubs-namespace) voor integratie met oplossingen van derden.
* Een [Log Analytics-werkruimte in Azure](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) voor het verzenden van logboeken naar Log Analytics.

## <a name="send-logs-to-azure-monitor"></a>Logboeken verzenden naar Azure Monitor

1. Selecteer in [Azure Portal](https://portal.azure.com/) de optie **Alle services** > filter op **Intune** > selecteer **Intune**.
2. Selecteer onder **Bewaking** de optie **Diagnostische instellingen**. De eerste keer dat u dit opent, schakelt u het in:

    ![Diagnostische instellingen inschakelen in Intune om logboeken te verzenden naar Azure Monitor](media/diagnostics-settings-turn-on.png)

3. Voer de volgende eigenschappen in:

    - **Naam**: Voer een naam in voor de diagnostische instellingen. Deze instelling omvat alle eigenschappen die u invoert. Voer bijvoorbeeld `Route audit logs to storage account` in.
    - **Archiveren naar een opslagaccount**: Hiermee worden de logboekgegevens opgeslagen in een Azure-opslagaccount. Gebruik deze optie als u de gegevens wilt opslaan of archiveren.

        1. Selecteer deze optie > **Configureren**. 
        2. Kies een bestaand opslagaccount in de lijst > **OK**.

    - **Streamen naar een Event Hub**: Hiermee worden de logboeken naar een Azure Event Hub gestreamd. Kies deze optie als u de logboekgegevens wilt analyseren met behulp van SIEM-hulpprogramma’s, zoals Splunk QRadar.

        1. Selecteer deze optie > **Configureren**. 
        2. Kies een bestaande Event Hub-naamruimte en bestaand beleid in de lijst > **OK**.

    - **Verzenden naar Log Analytics**: Hiermee worden de gegevens verzonden naar Azure Log Analytics. Kies deze optie als u visualisaties, bewaking en waarschuwingen wilt gebruiken voor uw logboeken.

        1. Selecteer deze optie > **Configureren**. 
        2. Maak een nieuwe werkruimte en voer de details van de werkruimte in. Of kies een bestaande werkruimte in de lijst > **OK**.

            [Azure Logboek Analytics-werkruimte](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) biedt meer details over deze instellingen.

    - **LOG** > **AuditLogs**: Kies deze optie om de [Intune-auditlogboeken](monitor-audit-logs.md) te verzenden naar uw opslagaccount, Event Hub, of Log Analytics. In de auditlogboeken wordt de geschiedenis weergegeven van elke taak die een wijziging genereert in Intune, inclusief wie dit heeft uitgevoerd en wanneer.

      Als u ervoor kiest om een opslagaccount te gebruiken, voert u ook in hoeveel dagen u de gegevens wilt behouden (retentie). Als u de gegevens voorgoed wilt behouden, stelt u **Retentie (dagen)** in op `0` (nul).

    - **LOG** > **OperationalLogs**: Operationele logboeken (preview) laten zien of de inschrijving van gebruikers en apparaten in Intune is geslaagd of mislukt. Kies deze optie om de inschrijvingslogboeken te verzenden naar uw opslagaccount, Event Hub, of Log Analytics.

      Als u ervoor kiest om een opslagaccount te gebruiken, voert u ook in hoeveel dagen u de gegevens wilt behouden (retentie). Als u de gegevens voorgoed wilt behouden, stelt u **Retentie (dagen)** in op `0` (nul).

      > [!NOTE]
      > Operationele logboeken zijn in de preview-versie. Als u feedback wilt geven, inclusief informatie die is opgenomen in de operationele logboeken, gaat u naar [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/suggestions/36613948-diagnostics-settings-feedback) (wordt geopend op een nieuwe website).

    Wanneer dit is voltooid, zien uw instellingen er ongeveer uit zoals de volgende instellingen: 

    ![Voorbeeldafbeelding waarin Intune-auditlogboeken worden verzonden naar een Azure-opslagaccount](media/diagnostics-settings-example.png)

4. U moet vervolgens de wijzigingen **Opslaan**. De instelling wordt weergegeven in de lijst. Zodra de instellingen zijn gemaakt, kunt u deze wijzigen door **Instelling bewerken** > **Opslaan** te selecteren.

## <a name="cost-considerations"></a>Kostenoverwegingen

Als u al een Microsoft Intune-licentie hebt, hebt u een Azure-abonnement nodig om het opslagaccount en de Event Hub in te stellen. Het Azure-abonnement is meestal gratis. U betaalt echter wel voor het gebruik van Azure-resources, inclusief het opslagaccount voor archivering en de Event Hub voor streaming. De hoeveelheid gegevens en de kosten verschillen, afhankelijk van de grootte van de tenant.

### <a name="storage-size-for-activity-logs"></a>Opslaggrootte voor activiteitenlogboeken

Elke gebeurtenis in een auditlogboek gebruikt ongeveer 2 kB gegevensopslag. Een tenant met 100.000 gebruikers kan ongeveer 1,5 miljoen gebeurtenissen per dag hebben. Dan hebt u ongeveer 3 GB gegevensopslag per dag nodig. Omdat schrijfbewerkingen meestal plaatsvinden in batches van vijf minuten, kunt u 9.000 schrijfbewerkingen per maand verwachten.

In de volgende tabellen wordt een kostenschatting weergegeven die afhankelijk is van de grootte van de tenant. Dit omvat ook een opslagaccount voor algemeen gebruik v2 in US - west voor gegevensretentie van minstens één jaar. Gebruik de [Prijscalculator voor Azure-opslag](https://azure.microsoft.com/pricing/details/storage/blobs/) voor een schatting van het gegevensvolume dat u kunt verwachten voor uw logboeken.

**Auditlogboek met 100.000 gebruikers**

| | |
|---|---|
|Gebeurtenissen per dag| 1,5 miljoen|
|Geschatte hoeveelheid gegevens per maand| 90 GB|
|Geschatte kosten per maand (USD)| $ 1,93|
|Geschatte kosten per jaar (USD)| $ 23,12|

**Auditlogboek met 1.000 gebruikers**

| | |
|---|---|
|Gebeurtenissen per dag| 15.000|
|Geschatte hoeveelheid gegevens per maand| 900 MB|
|Geschatte kosten per maand (USD)| $ 0,02|
|Geschatte kosten per jaar (USD)| $ 0,24|

### <a name="event-hub-messages-for-activity-logs"></a>Event Hub-berichten voor activiteitenlogboeken

Gebeurtenissen worden meestal verdeeld in batches van intervallen van vijf minuten, en verzonden als één bericht met alle gebeurtenissen binnen dit tijdsbestek. Een bericht in de Event Hub heeft een maximale grootte van 256 kB. Als de totale grootte van alle berichten binnen dit tijdsbestek dit volume heeft overschreden, worden er meerdere berichten verzonden.

Bijvoorbeeld: een grote tenant van meer dan 100.000 gebruikers heeft meestal 18 gebeurtenissen per seconde. Dit komt neer op 5.400 gebeurtenissen per vijf minuten (300 seconden x 18 gebeurtenissen). Auditlogboeken zijn ongeveer 2 kB per gebeurtenis. Dit komt neer op 10,8 MB aan gegevens. Er worden in een interval van 5 minuten dus 43 berichten naar de Event Hub verzonden.

De volgende tabel bevat de geschatte kosten per maand voor een eenvoudige Event Hub in US - west, afhankelijk van de hoeveelheid gebeurtenisgegevens. Gebruik de [Prijscalculator voor Event Hubs](https://azure.microsoft.com/pricing/details/event-hubs/) voor een schatting van het gegevensvolume dat u kunt verwachten voor uw logboeken.

**Auditlogboek met 100.000 gebruikers**

| | |
|---|---|
|Gebeurtenissen per seconde| 18|
|Gebeurtenissen per interval van vijf minuten| 5.400|
|Volume per interval| 10,8 MB|
|Berichten per interval| 43|
|Berichten per maand| 371.520|
|Geschatte kosten per maand (USD)| $ 10,83|

**Auditlogboek met 1.000 gebruikers**

| | |
|---|---|
|Gebeurtenissen per seconde|0,1 |
|Gebeurtenissen per interval van vijf minuten| 52|
|Volume per interval|104 kB |
|Berichten per interval|1 |
|Berichten per maand|8.640 |
|Geschatte kosten per maand (USD)|$ 10,80 |

### <a name="log-analytics-cost-considerations"></a>Kostenoverwegingen voor Log Analytics

Zie [Kosten beheren door gegevensvolume en retentie in Log Analytics te beheren](https://docs.microsoft.com/azure/log-analytics/log-analytics-manage-cost-storage) als u wilt kijken welke kosten gepaard gaan met het beheren van de Log Analytics-werkruimte.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

Krijg antwoorden op veelgestelde vragen en lees over eventuele bekende problemen met Intune-logboeken in Azure Monitor.

#### <a name="which-logs-are-included"></a>Welke logboeken zijn opgenomen?

Auditlogboeken en (de preview-versie van) operationele logboeken zijn beschikbaar voor routering met behulp van deze functie.

#### <a name="after-an-action-when-do-the-corresponding-logs-show-up-in-the-event-hub"></a>Wanneer worden, na een actie, de bijbehorende logboeken weergegeven in de Event Hub?

De logboeken worden meestal binnen enkele minuten nadat de actie is uitgevoerd, weergegeven in de Event Hub. [Wat is Azure Event Hubs?](https://docs.microsoft.com/azure/event-hubs/) biedt meer informatie.

#### <a name="after-an-action-when-do-the-corresponding-logs-show-up-in-the-storage-account"></a>Wanneer worden, na een actie, de bijbehorende logboeken weergegeven in het opslagaccount?

Voor Azure-opslagaccounts is de latentie ergens tussen de 5 tot 15 minuten nadat de actie is uitgevoerd.

#### <a name="what-happens-if-an-administrator-changes-the-retention-period-of-a-diagnostic-setting"></a>Wat gebeurt er als een beheerder de retentieperiode van een diagnostische instelling wijzigt?

Het nieuwe retentiebeleid wordt toegepast op de logboeken die zijn verzameld na de wijziging. Het is niet van toepassing op logboeken die zijn verzameld vóór de beleidswijziging.

#### <a name="how-much-does-it-cost-to-store-my-data"></a>Hoeveel kost het om mijn gegevens op te slaan?

De opslagkosten zijn afhankelijk van de grootte van uw logboeken en de retentieperiode die u kiest. Zie de [Opslaggrootte voor activiteitenlogboeken](#storage-size-for-activity-logs) (in dit artikel) voor een lijst met de geschatte kosten voor tenants, die afhankelijk zijn van het gegenereerde logboekvolume.

#### <a name="how-much-does-it-cost-to-stream-my-data-to-an-event-hub"></a>Hoeveel kost het om mijn gegevens naar een Event Hub te streamen?

De kosten voor streamen zijn afhankelijk van het aantal berichten dat u per minuut ontvangt. Zie [Event Hub-berichten voor activiteitenlogboeken](#event-hub-messages-for-activity-logs) (in dit artikel) voor details over hoe de kosten worden berekend en op welke manier de kostenschattingen worden gebaseerd op het aantal berichten.

#### <a name="how-do-i-integrate-intune-audit-logs-with-my-siem-system"></a>Hoe integreer ik Intune-auditlogboeken met mijn SIEM-systeem?

Gebruik Azure Monitor met Event Hubs om logboeken naar het SIEM-systeem te streamen. [Stream de logboeken eerst naar een Event Hub](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub). [Stel het SIEM-hulpprogramma vervolgens in](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub#access-data-from-your-event-hub) met de geconfigureerde Event Hub. 

#### <a name="what-siem-tools-are-currently-supported"></a>Welke SIEM-hulpprogramma’s worden momenteel ondersteund?

Azure Monitor wordt momenteel ondersteund met [Splunk](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-integrate-activity-logs-with-splunk), QRadar en [Sumo Logic](https://help.sumologic.com/Send-Data/Applications-and-Other-Data-Sources/Azure_Active_Directory) (een nieuwe website wordt geopend). Zie [Azure-bewakingsgegevens naar een Event Hub streamen voor gebruik met een extern hulpprogramma](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) voor meer informatie over de werking van connectors.

#### <a name="can-i-access-the-data-from-an-event-hub-without-using-an-external-siem-tool"></a>Heb ik toegang tot de gegevens van een Event Hub zonder een extern SIEM-hulpprogramma te gebruiken?

Ja. U kunt de [Event Hub API](https://docs.microsoft.com/azure/event-hubs/event-hubs-dotnet-standard-getstarted-receive-eph) gebruiken voor toegang tot de logboeken vanuit de aangepaste toepassing.

#### <a name="what-data-is-stored"></a>Welke gegevens worden opgeslagen?

In Intune worden geen gegevens opgeslagen die zijn verzonden via de pijplijn. In Intune worden gegevens gerouteerd naar de Azure Monitor-pijplijn, met de tenant als autoriteit. Zie [Overzicht van Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

* [Activiteitenlogboeken archiveren in een opslagaccount](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-azure-monitor-route-logs-to-storage-account)
* [Activiteitenlogboeken routeren naar een Event Hub](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub)
* [Activiteitenlogboeken integreren met Log Analytics](https://docs.microsoft.com/azure/active-directory/reports-monitoring/howto-integrate-activity-logs-with-log-analytics)
