---
title: Configuratiebeleid van Intune-apps gebruiken voor Android for Work
titlesuffix: Azure portal
description: Informatie over het gebruik van het configuratiebeleid voor apps om configuratiegegevens te bieden aan een Android for Work-app wanneer deze wordt uitgevoerd.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4b73202a1a68bd2dd3dcbfa86c21cb09ae00056c
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-android-for-work"></a>Configuratiebeleid van Microsoft Intune-apps gebruiken voor Android for Work

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gebruik het configuratiebeleid voor apps in Microsoft Intune om instellingen op te geven die mogelijk beschikbaar zijn wanneer gebruikers een Android for Work-app uitvoeren. Niet alle apps ondersteunen app-configuratie. Neem contact op met de ontwikkelaar van de app om te controleren of de app configuratiebeleid voor apps ondersteunt.

Via een configuratiebeleid voor apps kunt u vooraf beschikbare app-instellingen configureren voor uw gebruikers voordat ze de app uitvoeren. Sommige Android-apps ondersteunen beheerde configuratieopties die u kunt configureren in de Azure-portal met de [Configuration Designer](#use-configuration-designer). Bepaalde configuratie-instellingen voor apps (zoals de instellingen voor bundeltypen) kunnen niet worden geconfigureerd met de Configuration Designer.  Voor deze waarden moet u de [JSON-editor](#use-json-editor) gebruiken.   Instellingen worden automatisch aan apps geleverd wanneer de app wordt geïnstalleerd.

U wijst dit beleid niet rechtstreeks toe aan gebruikers en apparaten. In plaats daarvan koppelt u een beleid aan een app en wijst u vervolgens de app toe. De beleidsinstellingen worden gebruikt wanneer de app deze controleert (doorgaans de eerste keer dat de app wordt uitgevoerd).

## <a name="use-configuration-designer"></a>Configuration Designer gebruiken

1. Kies in de Azure-portal **Mobiele apps**. Kies onder **Beheren** **App-configuratiebeleid** en klik vervolgens op **Toevoegen**.
2. Stel de volgende details in:
    - **Naam**: de naam van het profiel dat wordt weergegeven in de Azure-portal
    - **Beschrijving**: de beschrijving van het profiel dat wordt weergegeven in de Azure-portal
    - **Platform**: selecteer **Android**
    - **Device enrollment type (Inschrijving apparaattype)** - : **Ingeschreven bij Intune** is vooraf geselecteerd.
3. Selecteer **Gekoppelde app** om een app te kiezen waarvoor u een configuratiebeleid wilt opgeven.  Selecteer in de lijst met Android Work-apps die u hebt goedgekeurd en die zijn gesynchroniseerd met Intune
4. Selecteer **Configuratie-instellingen**.
5. Voor **Indeling configuratie-instellingen** selecteert u **Gebruik Configuration Designer**.
6. Kies **Toevoegen**. Er wordt een lijst met beschikbare configuratie-instellingen weergegeven. De lijst bevat:
    - **Configuratiesleutels**: de naam van de instelling.
    - **Waardetype**: de instelling die kan worden geconfigureerd, bijvoorbeeld **Booleaans** of **Tekenreeks**.
    - **Beschrijving**: geeft de beschrijving van de configuratie-instelling weer.
7. Schakel de selectievakjes in van de instellingen die u wilt configureren met dit profiel en klik vervolgens op **OK**.
8. Er wordt een lijst met geselecteerde instellingen weergegeven met de beschikbare **Configuratiewaarde**. Geef een waarde voor elke instelling op en klik vervolgens op **OK**.

## <a name="use-json-editor"></a>De JSON-editor gebruiken

1. Kies in de Azure-portal **Mobiele apps**. Kies onder **Beheren** **App-configuratiebeleid** en klik vervolgens op **Toevoegen**.
2. Stel de volgende details in:
    - **Naam**: de naam van het profiel dat wordt weergegeven in de Azure-portal
    - **Beschrijving**: de beschrijving van het profiel dat wordt weergegeven in de Azure-portal
    - **Platform**: selecteer **Android**
    - **Device enrollment type (Inschrijving apparaattype)** - : **Ingeschreven bij Intune** is vooraf geselecteerd.
3. Selecteer **Gekoppelde app** om een app te kiezen waarvoor u een configuratiebeleid wilt opgeven.  Selecteer in de lijst met Android for Work-apps de apps die u hebt goedgekeurd en die zijn gesynchroniseerd met Intune.
5. Selecteer **Configuratie-instellingen**.
6. Voor **Indeling configuratie-instellingen** selecteert u **JSON-editor invoeren**.
7. In de editor kunt u JSON-waarden voor configuratie-instellingen opgeven. U kunt **JSON-sjabloon downloaden** kiezen om een voorbeeldbestand te downloaden dat u vervolgens kunt configureren.
8. Als u bent klaar, kiest u **OK** en klikt u vervolgens op **Toevoegen**.

Het beleid wordt gemaakt en wordt weergegeven op de blade met de lijst met configuratiebeleidsregels.



Wanneer de toegewezen app op een apparaat wordt uitgevoerd, worden de instellingen uitgevoerd die u in het configuratiebeleid voor de app hebt geconfigureerd.

## <a name="preconfigure-permissions-grant-state-for-apps"></a>De status van de machtigingen voor apps vooraf configureren

U kunt machtigingen voor apps ook vooraf configureren voor toegang tot Android-apparaatfuncties. Android-apps die apparaatmachtigingen vereisen, zoals voor toegang tot uw locatie of de apparaatcamera, vragen gebruikers de machtiging te accepteren of te weigeren. Als een app bijvoorbeeld gebruikmaakt van de microfoon van het apparaat, wordt de gebruiker gevraagd de app toestemming te verlenen voor het gebruik van de microfoon.

1. Kies in de Azure-portal **Mobiele apps**. Kies onder **Beheren** **App-configuratiebeleid** en klik vervolgens op **Toevoegen**.
2. Stel de volgende details in:
    - **Naam**: de naam van het profiel dat wordt weergegeven in de Azure-portal
    - **Beschrijving**: de beschrijving van het profiel dat wordt weergegeven in de Azure-portal
    - **Platform**: selecteer **Android**
    - **Device enrollment type (Inschrijving apparaattype)** - : **Ingeschreven bij Intune** is vooraf geselecteerd.
3. Selecteer **Gekoppelde app** om een app te kiezen waarvoor u een configuratiebeleid wilt opgeven.  Selecteer in de lijst met Android for Work-apps de apps die u hebt goedgekeurd en die zijn gesynchroniseerd met Intune.
5. Selecteer **Machtigingen** en kies vervolgens **Toevoegen**.
6. Selecteer in de lijst met beschikbare app-machtigingen en kies vervolgens **OK**.
7. Selecteer een optie voor elke machtiging die aan dit beleid moet worden verleend:
    - **Vragen**: de gebruiker vragen om de machtiging te accepteren of te weigeren.
    - **Automatisch verlenen**: automatisch goedkeuren zonder de gebruiker hiervan op de hoogte te stellen.
    - **Automatisch weigeren**: automatisch weigeren zonder de gebruiker hiervan op de hoogte te stellen.
8. Als u het configuratiebeleid voor apps wilt toewijzen, selecteert u het, selecteert u vervolgens **Toewijzing** en selecteert u ten slotte **Groepen selecteren**.
9. Selecteer de gebruikersgroepen waaraan u het beleid wilt toewijzen en kies vervolgens **Selecteren**.
10. Kies **Opslaan** om het beleid toe te wijzen.

## <a name="next-steps"></a>Volgende stappen

Ga vervolgens als gebruikelijk door met [toewijzen](apps-deploy.md) en [bewaken](apps-monitor.md) van de app.

