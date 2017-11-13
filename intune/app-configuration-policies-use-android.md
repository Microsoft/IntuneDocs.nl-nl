---
title: App-configuratiebeleidsregels voor beheerde Android-apparaten | Microsoft Docs
titlesuffix: Azure portal
description: Informatie over het gebruik van het configuratiebeleid voor apps om configuratiegegevens te bieden aan een Android for Work-app wanneer deze wordt uitgevoerd.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e56aff30b353a2c98eb7effbec3e02bde066804f
ms.sourcegitcommit: 67c037af31c1f167ec9b4f4baa754631c817e7d1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/01/2017
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>App-configuratiebeleidsregels toevoegen voor beheerde Android-apparaten

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

App-configuratiebeleidsregels gebruiken in Microsoft Intune om instellingen te leveren wanneer gebruikers een Android for Work-app uitvoeren. U wijst dit beleid niet rechtstreeks toe aan gebruikers en apparaten. In plaats daarvan koppelt u een beleid aan een app en wijst u vervolgens de app toe. De beleidsinstellingen worden gebruikt wanneer de app deze controleert, doorgaans bij de eerste keer dat de app wordt uitgevoerd.

> [!Note]  
> Niet elke app ondersteunt app-configuratie. Vraag aan de app-ontwikkelaar of deze de app zo heeft geconstrueerd dat deze app-configuratiebeleidsregels ondersteunt.

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** + **Intune**.
3. Kies de workload **Mobiele apps**.
4. Klik op **App-configuratiebeleidsregels** in de groep **Beheren** en klik vervolgens op **Toevoegen**.
5. Stel de volgende details in:
    - **Naam**  
      De naam van het profiel die in Azure Portal wordt weergegeven.
    - **Beschrijving**  
      De beschrijving van het profiel die in Azure Portal wordt weergegeven.
    - **Type apparaatinschrijving**  
      Kies **Beheerde apparaten**.
6. Selecteer **Android** voor het **Platform**.
7. Selecteer **Gekoppelde app** om de app te kiezen waarvoor u een app-configuratiebeleid wilt definiëren.  Selecteer in de lijst met Android for Work-apps de apps die u hebt goedgekeurd en die zijn gesynchroniseerd met Intune.
8. Selecteer **Configuratie-instellingen**. U kunt configuraties instellen door gebruik te maken van:
    - [Configuration Designer](#Use-the-configuration-designer)
    - [De JSON-editor invoeren](#Use-the-JSON-editor)
9. Klik op **OK** en op **Toevoegen**.

## <a name="use-the-configuration-designer"></a>Configuration Designer gebruiken

U kunt Configuration Designer gebruiken voor apps op apparaten, ongeacht of deze zijn ingeschreven bij Intune. Met de ontwerper kunt u specifieke configuratiesleutels en -waarden instellen. U kunt tevens het gegevenstype voor elke waarde opgeven.

Stel voor elke sleutel en waarde in de configuratie het volgende in:

  - **Configuratiesleutel**  
     Hiermee wordt de specifieke instellingsconfiguratie uniek geïdentificeerd.
  - **Waardetype**  
    Het gegevenstype van de configuratiewaarde. Typen zijn onder meer geheel getal, reëel, tekenreeks of booleaans.
  - **Configuratiewaarde**  
    De waarde voor de configuratie. 

## <a name="enter-the-json-editor"></a>De JSON-editor invoeren

Bepaalde configuratie-instellingen voor apps (zoals de instellingen voor bundeltypen) kunnen niet worden geconfigureerd met de Configuration Designer.  U moet de JSON-editor voor deze waarden gebruiken. Instellingen worden automatisch aan apps geleverd wanneer de app wordt geïnstalleerd.

1. Voor **Indeling configuratie-instellingen** selecteert u **JSON-editor invoeren**.
2. U kunt in de editor JSON-waarden definiëren voor configuratie-instellingen. U kunt **JSON-sjabloon downloaden** kiezen om een voorbeeldbestand te downloaden dat u vervolgens kunt configureren.
3. Als u bent klaar, kiest u **OK** en klikt u vervolgens op **Toevoegen**.

Het beleid wordt gemaakt en wordt weergegeven op de blade met de lijst met beleidsregels.

Wanneer de toegewezen app op een apparaat wordt uitgevoerd, worden de instellingen uitgevoerd die u in het configuratiebeleid voor de app hebt geconfigureerd.

## <a name="preconfigure-permissions-grant-state-for-apps"></a>De status van de machtigingen voor apps vooraf configureren

U kunt machtigingen voor apps ook vooraf configureren voor toegang tot Android-apparaatfuncties. Android-apps die apparaatmachtigingen vereisen, zoals voor toegang tot uw locatie of de apparaatcamera, vragen gebruikers de machtiging te accepteren of te weigeren. Als een app bijvoorbeeld gebruikmaakt van de microfoon van het apparaat, wordt de gebruiker gevraagd de app toestemming te verlenen voor het gebruik van de microfoon.

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** + **Intune**.
3. Kies **Mobiele apps**. Kies onder **Beheren** App-configuratiebeleidsregels en klik vervolgens op **Toevoegen**.
4. Stel de volgende details in:
    - **Naam**: de naam van het profiel dat wordt weergegeven in de Azure-portal
    - **Beschrijving**: de beschrijving van het profiel dat wordt weergegeven in de Azure-portal
    - **Platform**: selecteer **Android**
    - **Type apparaatinschrijving** - *Beheerde apparaten** is vooraf voor u geselecteerd.
5. Selecteer **Gekoppelde app** om een app te kiezen waarvoor u een configuratiebeleid wilt opgeven.  Selecteer in de lijst met Android for Work-apps de apps die u hebt goedgekeurd en die zijn gesynchroniseerd met Intune.
6. Selecteer **Machtigingen** en kies vervolgens **Toevoegen**.
7. Selecteer in de lijst met beschikbare app-machtigingen en kies vervolgens **OK**.
8. Selecteer een optie voor elke machtiging die aan dit beleid moet worden verleend:
    - **Vragen**: de gebruiker vragen om de machtiging te accepteren of te weigeren.
    - **Automatisch verlenen**: automatisch goedkeuren zonder de gebruiker hiervan op de hoogte te stellen.
    - **Automatisch weigeren**: automatisch weigeren zonder de gebruiker hiervan op de hoogte te stellen.
9. Als u het configuratiebeleid voor apps wilt toewijzen, selecteert u het, selecteert u vervolgens **Toewijzing** en selecteert u ten slotte **Groepen selecteren**.
10. Selecteer de gebruikersgroepen waaraan u het beleid wilt toewijzen en kies vervolgens **Selecteren**.
11. Kies **Opslaan** om het beleid toe te wijzen.

## <a name="next-steps"></a>Volgende stappen

Ga verder met het [toewijzen](apps-deploy.md) en [controleren](apps-monitor.md) van de app.

