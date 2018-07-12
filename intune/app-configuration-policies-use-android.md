---
title: App-configuratiebeleidsregels toevoegen voor beheerde Android-apparaten
titlesuffix: Microsoft Intune
description: Gebruik app-configuratiebeleidsregels in Microsoft Intune om instellingen te leveren wanneer gebruikers een Android-werkprofiel-app uitvoeren.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c837f9a5a2cb1a6f267f85f888453725da6acb66
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905747"
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>App-configuratiebeleidsregels toevoegen voor beheerde Android-apparaten

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Gebruik app-configuratiebeleidsregels in Microsoft Intune om instellingen te leveren aan Android-werkprofiel-apps. De ontwikkelaar van de app moet configuratie-instellingen voor beheerde Android-apps weergeven om configuratie-instellingen voor de app op te kunnen geven. Wijs het app-configuratiebeleid toe aan de gebruikersgroep waarop u de instellingen wilt toepassen.  De beleidsinstellingen worden gebruikt wanneer de app deze controleert, doorgaans bij de eerste keer dat de app wordt uitgevoerd.

> [!Note]  
> Niet elke app ondersteunt app-configuratie. Vraag aan de app-ontwikkelaar of deze de app zo heeft geconstrueerd dat deze app-configuratiebeleidsregels ondersteunt.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies de workload **Mobiele apps**.
4. Kies **App-configuratiebeleidsregels** in de groep **Beheren** en kies vervolgens **Toevoegen**.
5. Stel de volgende details in:
    - **Naam**: de naam van het profiel dat wordt weergegeven in Azure Portal.
    - **Beschrijving**: de beschrijving van het profiel dat wordt weergegeven in Azure Portal.
    - **Type apparaatregistratie**: kies **Beheerde apparaten**.
6. Selecteer **Android** voor **Platform**.
7. Selecteer **Gekoppelde app** om de app te kiezen waarvoor u een app-configuratiebeleid wilt definiëren. Selecteer in de lijst met Android-werkprofiel-apps de apps die u hebt goedgekeurd en die zijn gesynchroniseerd met Intune.
8. Selecteer **Machtigingen**. U kunt configuraties instellen door gebruik te maken van:
    - [Configuration Designer](#Use-the-configuration-designer)
    - [JSON-editor](#Enter-the-JSON-editor)
9. Kies **OK** en kies vervolgens **Toevoegen**.

## <a name="use-the-configuration-designer"></a>Configuration Designer gebruiken

U kunt de Configuration Designer gebruiken voor Android-apps die configuratie ondersteunen. Configuratie is van toepassing op apparaten die zijn ingeschreven bij Intune. Met de Designer kunt u specifieke configuratiewaarden configureren voor de instellingen die voor een app beschikbaar zijn.

Selecteer **Toevoegen** om de lijst met configuratie-instellingen te selecteren die u wilt opgeven voor de app.  
Stel voor elke sleutel en waarde in de configuratie het volgende in:

  - **Waardetype**  
    Het gegevenstype van de configuratiewaarde. Voor het waardetype Tekenreeks kunt u een variabel profiel of een certificaatprofiel als waardetype kiezen (optioneel).
  - **Configuratiewaarde**  
    De waarde voor de configuratie. Als u Variabel of Certificaat als waardetype selecteert, kunt u kiezen uit een lijst met variabelen of certificaatprofielen in de vervolgkeuzelijst met configuratiewaarden.  Als u een certificaat kiest, wordt de alias van het certificaat dat is geïmplementeerd op het apparaat tijdens runtime ingevuld.
    
### <a name="supported-variables-for-configuration-values"></a>Ondersteunde variabelen voor configuratiewaarden

U kunt de volgende opties kiezen als u Variabele als het waardetype kiest:
- User Principal Name: bijvoorbeeld **John@contoso.com**
- Mail: bijvoorbeeld **John@contoso.com**
- Partian UPN: bijvoorbeeld **Jan**
- Account-id: bijvoorbeeld **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- Apparaat-id: bijvoorbeeld **b9841cd9-9843-405f-be28-b2265c59ef97**
- Gebruikers-id: bijvoorbeeld **3ec2c00f-b125-4519-acf0-302ac3761822**
- Gebruikersnaam: bijvoorbeeld **Jan de Vries**


## <a name="enter-the-json-editor"></a>De JSON-editor invoeren

Bepaalde configuratie-instellingen voor apps (zoals de instellingen voor bundeltypen) kunnen niet worden geconfigureerd met de Configuration Designer. U moet de JSON-editor voor deze waarden gebruiken. Instellingen worden automatisch aan apps geleverd wanneer de app wordt geïnstalleerd.

1. Voor **Indeling configuratie-instellingen** selecteert u **JSON-editor invoeren**.
2. U kunt in de editor JSON-waarden definiëren voor configuratie-instellingen. U kunt **JSON-sjabloon downloaden** kiezen om een voorbeeldbestand te downloaden dat u vervolgens kunt configureren.
3. Kies **OK** en kies vervolgens **Toevoegen**.

Het beleid wordt gemaakt en wordt weergegeven op de blade met de lijst met beleidsregels.

Wanneer de toegewezen app op een apparaat wordt uitgevoerd, worden de instellingen uitgevoerd die u in het configuratiebeleid voor de app hebt geconfigureerd.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>De status van de machtigingen voor apps vooraf configureren

U kunt machtigingen voor apps ook vooraf configureren voor toegang tot Android-apparaatfuncties. Android-apps die apparaatmachtigingen vereisen, zoals voor toegang tot uw locatie of de apparaatcamera, vragen gebruikers de machtiging te accepteren of te weigeren. Als een app bijvoorbeeld gebruikmaakt van de microfoon van het apparaat, wordt de gebruiker gevraagd de app toestemming te verlenen voor het gebruik van de microfoon.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Bewaking en beheer**.
3. Kies **Mobiele apps**.
3. Kies onder **Beheren** **App-configuratiebeleidsregels** en kies vervolgens **Toevoegen**.
4. Stel de volgende details in:
    - **Naam**. De naam van het profiel die in Azure Portal wordt weergegeven.
    - **Beschrijving**. De beschrijving van het profiel die in Azure Portal wordt weergegeven.
    - **Type apparaatinschrijving**. Selecteer **Beheerde apparaten**.
    - **Platform**. Selecteer **Android**.
5. Selecteer **Gekoppelde app** om een app te kiezen waarvoor u een configuratiebeleid wilt opgeven. Selecteer in de lijst met Android-werkprofiel-apps de apps die u hebt goedgekeurd en die zijn gesynchroniseerd met Intune.
6. Selecteer **Machtigingen** en kies vervolgens **Toevoegen**.
7. Selecteer in de lijst met beschikbare app-machtigingen en kies vervolgens **OK**.
8. Selecteer een optie voor elke machtiging die aan dit beleid moet worden verleend:
    - **Vragen**. De gebruiker vragen om de machtiging te accepteren of te weigeren.
    - **Automatisch verlenen**. Automatisch goedkeuren zonder de gebruiker hiervan op de hoogte te stellen.
    - **Automatisch weigeren**. Automatisch weigeren zonder de gebruiker hiervan op de hoogte te stellen.
9. Als u het configuratiebeleid voor apps wilt toewijzen, selecteert u het, selecteert u vervolgens **Toewijzing** en selecteert u ten slotte **Groepen selecteren**.
10. Selecteer de gebruikersgroepen waaraan u het beleid wilt toewijzen en kies vervolgens **Selecteren**.
11. Kies **Opslaan** om het beleid toe te wijzen.

## <a name="next-steps"></a>Volgende stappen

Ga verder met het [toewijzen](apps-deploy.md) en [controleren](apps-monitor.md) van de app.

