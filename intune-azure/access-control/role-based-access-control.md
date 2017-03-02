---
title: Op rollen gebaseerd toegangsbeheer (RBAC) voor Microsoft Intune
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u met RBAC kunt bepalen welke personen acties kunnen uitvoeren en wijzigingen kunnen aanbrengen.'
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: f4a80949dafbd3acc0413c75bbb0b8b5f5ae5664
ms.openlocfilehash: 2507626d23beece9723134191e8747f731478ddb
ms.lasthandoff: 02/23/2017


---

# <a name="role-based-access-control-rbac-for-microsoft-intune"></a>Op rollen gebaseerd toegangsbeheer (RBAC) voor Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Eenvoudig gezegd wordt op basis van **rollen** (of RBAC) in Intune bepaald welke personen verschillende Intune-acties kunnen uitvoeren en op welke personen deze acties van toepassing zijn. U kunt de ingebouwde rollen gebruiken die voorzien in bepaalde algemene Intune-scenario's of u kunt uw eigen rollen maken.

Een rol wordt gedefinieerd op basis van het volgende:

- **Definitie**: de naam van een rol en de machtigingen die met de rol worden geconfigureerd.
- **Leden**: de gebruiker of de groep met gebruikers aan wie deze machtigingen worden verleend.
- **Bereik**: de gebruikers of apparaten die een bepaalde persoon (het lid) kan beheren.
- **Toewijzing**: als de definitie, de leden en het bereik zijn geconfigureerd, wordt de rol toegewezen.

## <a name="built-in-roles"></a>Ingebouwde rollen

De volgende rollen zijn ingebouwd in Intune. U kunt deze rollen aanpassen of deze zonder verdere configuratie aan groepen toewijzen.

- **Intune Administrator** (Intune-beheerder): heeft volledige machtigingen voor alle bewerkingen in Intune.
- **Toepassingsbeheer**: toepassingen en profielen beheren en implementeren.
- **Configuration Policy Manager**: configuratie-instellingen en -profielen beheren en implementeren.
- **Helpdesk Operator** (Helpdeskoperator) - externe taken uitvoeren en de gebruikers- en apparaatgegevens weergeven.
- **Alleen lezen-operator**: gegevens weergeven in de Intune-portal zonder de mogelijkheid wijzigingen aan te brengen.


## <a name="custom-roles"></a>Aangepaste rollen

Als geen van de ingebouwde rollen aan uw behoeften voldoet, kunt u uw eigen rol maken door instellingen te kiezen voor de verschillende mogelijkheden van Intune. Verderop in dit onderwerp ziet u een lijst met de beschikbare instellingen.

### <a name="example"></a>Voorbeeld

U stelt een nieuwe IT-beheerder aan die verantwoordelijk is voor het implementeren en beheren van apps voor gebruikers in uw kantoor in Londen. De gebruikers bevinden zich in een Azure AD-groep met de naam **Londen**. U wilt ervoor zorgen dat de IT-beheerder geen apps kan implementeren voor gebruikers in andere kantoren. U voert de volgende acties uit:

- Wijs de ingebouwde rol **Toepassingsbeheer** toe met de volgende eigenschappen:
    - **Leden**: selecteer de groep die de IT-beheerder bevat die de apps gaat implementeren.
    - **Bereik**: selecteer de Azure AD-groep **Londen**.

    >[!IMPORTANT]
    >Als u rollen wilt maken, bewerken of toewijzen, moet uw account een van de volgende machtigingen hebben in Azure AD:
    >- **Globale AAD-beheerder**
    >- **Intune-servicebeheerder**

### <a name="how-to-create-a-custom-role"></a>Een aangepaste rol maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Toegangsbeheer** op de blade **Intune**.
![Werkbelasting Toegangsbeheer](./media/axxess-control.png)
1. Kies **Aangepast toevoegen** op de blade **Rollen** van de workload **Toegangsbeheer**.
2. Voer op de blade **Aangepaste rol toevoegen** een naam en een beschrijving in voor de nieuwe rol en klik vervolgens op **Machtigingen**.
3. Kies op de blade **Machtigingen** de machtigingen die u voor deze rol wilt gebruiken. Gebruik de naslaglijst met instellingen voor aangepaste rollen verderop in dit onderwerp als hulp hierbij.
4. Wanneer u klaar bent, klikt u op **OK**.
5. Klik op de blade **Aangepaste rol toevoegen** op **Maken**.

De nieuwe rol wordt weergegeven in de lijst op de blade **Rollen**.

## <a name="how-to-assign-a-role"></a>Een rol toewijzen

1. Kies op de blade **Rollen** van de workload **Toegangsbeheer** de ingebouwde of aangepaste rol die u wilt toewijzen.
2. Kies **Beheren** > **Toewijzingen** op de blade <*rolnaam*> - **Eigenschappen**.
    >[!TIP]
    >Op deze blade kunt u ook bestaande rollen bewerken of verwijderen.
3. Kies **Toewijzen** op de volgende blade.
4. Voer op de blade **Roltoewijzingen** een **naam** en desgewenst een **beschrijving** in voor de toewijzing en kies het volgende:
    - **Leden**: selecteer de groep die de gebruiker bevat aan wie u de machtigingen wilt verlenen.
    - **Bereik**: selecteer de groep met de gebruikers die het bovenstaande lid mogen beheren.
5. Wanneer u klaar bent, klikt u op **OK**.

De nieuwe toewijzing wordt in de lijst met toewijzingen weergegeven.

## <a name="custom-role-settings-reference"></a>Naslaginformatie voor instellingen voor aangepaste rollen

Wanneer u een aangepaste rol maakt, kunt u een of meer van de volgende instellingen configureren:

### <a name="device-configurations"></a>Apparaatconfiguraties

|||
|-|-|
|**Toewijzen**|Apparaatprofielen toewijzen aan groepen.|
|**Maken**|Apparaatprofielen maken.|
|**Verwijderen**|Apparaatprofielen verwijderen.|
|**Lezen**|Apparaatprofielen en de bijbehorende eigenschappen lezen.|
|**Bijwerken**|Bestaande apparaatprofielen bijwerken.|

### <a name="managed-apps"></a>Managed apps

|||
|-|-|
|**Toewijzen**|Beheerde apps toewijzen aan groepen.|
|**Maken**|Nieuwe beheerde apps aan Intune toevoegen.|
|**Verwijderen**|Beheerde apps verwijderen.|
|**Lezen**|Beheerde apps en de bijbehorende eigenschappen lezen.|
|**Bijwerken**|Bestaande beheerde apps bijwerken.|
|**Wissen**|Beheerde apps van apparaten wissen.|

### <a name="managed-devices"></a>Beheerde apparaten

|||
|-|-|
|**Verwijderen**|Beheerde apparaten uit Intune verwijderen.|
|**Lezen**|Informatie over beheerde apparaten in de Intune-portal weergeven.|
|**Bijwerken**|Informatie over beheerde apparaten bijwerken.|

### <a name="mobile-apps"></a>Mobiele apps

|||
|-|-|
|**Toewijzen**|Mobiele apps aan groepen toewijzen.|
|**Maken**|Nieuwe mobiele apps aan Intune toevoegen.|
|**Verwijderen**|Mobiele apps verwijderen.|
|**Lezen**|Mobiele apps en de bijbehorende eigenschappen lezen.|
|**Bijwerken**|Bestaande mobiele apps bijwerken.|

### <a name="organization"></a>Organisatie

|||
|-|-|
|**Lezen**|Tenantinstellingen lezen.|
|**Bijwerken**|Tenantinstellingen bijwerken.|

### <a name="remote-tasks"></a>Externe taken

|||
|-|-|
|**Activeringsvergrendeling overslaan**|De activeringsvergrendeling van een iOS-apparaat verwijderen zonder dat u de Apple ID en het wachtwoord van de gebruiker nodig hebt. |
|**Modus Apparaat verloren uitschakelen**|De modus Apparaat verloren uitschakelen. Met deze modus kunt u een bericht en een telefoonnummer opgeven die op het vergrendelingsscherm van het apparaat worden weergeven.|
|**Modus Apparaat verloren inschakelen**|De modus Apparaat verloren inschakelen. Met deze modus kunt u een bericht en een telefoonnummer opgeven die op het vergrendelingsscherm van het apparaat worden weergeven.|
|**Apparaat zoeken**|-|
|**Nu opnieuw opstarten**|Hiermee zorgt u ervoor dat het apparaat opnieuw wordt opgestart.|
|**Vergrendelen op afstand**|Hiermee vergrendelt u een apparaat. De eigenaar van het apparaat moet de wachtwoordcode gebruiken om het apparaat te ontgrendelen.|
|**Wachtwoordcode opnieuw instellen**|Hiermee wordt een nieuwe wachtwoordcode voor het apparaat gegenereerd die wordt weergegeven op de blade Overzicht in <device name>.|
|**Buiten gebruik stellen**|Hiermee verwijdert u alleen bedrijfsgegevens die worden beheerd door Intune. Persoonlijke gegevens worden niet van het apparaat verwijderd.|
|**Wissen**|Hiermee worden de standaardinstellingen van het apparaat hersteld.|



### <a name="telecom-expenses"></a>Telecom Expense Management

|||
|-|-|
|**Lezen**|TEM-instellingen (Telecom Expense Management) lezen.|
|**Bijwerken**|TEM-instellingen (Telecom Expense Management) bijwerken.|

### <a name="terms-and-conditions"></a>Voorwaarden

|||
|-|-|
|**Toewijzen**|Voorwaarden aan groepen toewijzen.|
|**Maken**|Instellingen voor voorwaarden maken.|
|**Verwijderen**|Instellingen van voorwaarden verwijderen.|
|**Lezen**|Instellen van voorwaarden in de Microsoft Intune-portal lezen.|
|**Bijwerken**|Bestaande instellingen van voorwaarden bijwerken.|
