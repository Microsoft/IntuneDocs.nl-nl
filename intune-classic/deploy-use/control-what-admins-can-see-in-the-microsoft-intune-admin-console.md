---
title: Consoleweergaven aanpassen voor beheerdersrollen
description: U kunt dit onderwerp gebruiken om de Intune-beheerconsoleweergave zodanig filteren dat uw beheerders alleen de items zien die ze voor hun rol nodig hebben.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0783eaa-67dc-410e-9e80-4d3aa72f36d8
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9525964117b6d7d459f5ea608a35343ab19f249f
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/15/2017
---
# <a name="customize-intune-console-views-according-to-admin-roles"></a>Intune-consoleweergaven aanpassen voor beheerdersrollen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

U kunt de Microsoft Intune-beheerconsoleweergave zodanig filteren dat uw beheerders alleen de items zien die ze voor hun rol nodig hebben. U kunt bijvoorbeeld alleen operators van de beheersconsole toestaan definities voor malware bij te werken of de wachtwoordcode op apparaten opnieuw in te stellen. U kunt dit doen door vooraf ingestelde **aanwijzingen** te gebruiken die u aan specifieke gebruikers toewijst. Wanneer deze gebruikers de beheerconsole openen, zien ze alleen de items die specifiek zijn voor wat aan hen is toegewezen.

## <a name="to-create-a-custom-view"></a>Een aangepaste weergave maken

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) **Beheer** &gt; **Servicebeheerders**.

2.  Kies in de lijst met servicebeheerders de gebruiker van wie u de aanduiding wilt wijzigen en kies vervolgens **Toegang beheren**.

3.  In het dialoogvenster **Toegang beheren** kiest u het toegangsniveau dat u aan de geselecteerde gebruiker wilt toewijzen. U kunt kiezen uit:

    -   **Volledige toegang**
    -   **Alleen-lezentoegang**
    -   **Helpdesk - knooppunt Groepen**

    Volledige toegang en Alleen-lezentoegang behoeven geen uitleg. <!--- **Helpdesk - Groups Node** allows users to choose from one of the following designations that provide custom levels of access to the Intune admin console:--->

    **Helpdesk - knooppunt groepen** beperkt wat de beheerder kan zien en doen, tot het volgende:

    -   Lijsten met gebruikers en apparaten bekijken. De beheerder kan geen filters gebruiken om de weergave te wijzigen. U kunt echter wel groepsgewijze filtering gebruiken om te wijzigen wat de beheerder kan zien. Zie [Groepen gebruiken voor het beheren van gebruikers en apparaten met Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md) voor meer informatie.

    -   De lijst met gebruikers en apparaten afdrukken

    -   De lijst met gebruikers en apparaten exporteren

    -   De eigenschappen van een gebruiker of apparaat weergeven

    -   De volgende externe taken uitvoeren:

        -   Een volledige scan op malware uitvoeren

        -   Een snelle scan op malware uitvoeren

        -   Een computer opnieuw opstarten

        -   Malware-definities bijwerken

        -   Beleid vernieuwen

        -   Inventaris vernieuwen

        -   Een apparaat op afstand vergrendelen

        -   Een wachtwoordcode opnieuw instellen

Wanneer de gebruiker die u hebt geconfigureerd, de eerstvolgende keer de Intune-beheerconsole opent, krijgt deze het toegangsniveau dat u hebt opgegeven.
