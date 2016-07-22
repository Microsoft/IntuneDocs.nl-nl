---
# required metadata

title: Consoleweergaven aanpassen voor beheerdersrollen | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e0783eaa-67dc-410e-9e80-4d3aa72f36d8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Intune-consoleweergaven aanpassen voor beheerdersrollen
U kunt de Microsoft Intune-beheerconsoleweergave zodanig filteren dat uw beheerders alleen de items zien die ze voor hun rol nodig hebben. U kunt bijvoorbeeld alleen operators van de beheersconsole toestaan definities voor malware bij te werken of de wachtwoordcode op apparaten opnieuw in te stellen. U kunt dit doen door vooraf ingestelde **aanwijzingen** te gebruiken die u aan specifieke gebruikers toewijst. Wanneer deze gebruikers de beheerconsole openen, zien ze alleen de items die specifiek zijn voor hun aanduiding.

## Een aangepaste weergave maken

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) achtereenvolgens **Beheer** &gt; **Servicebeheerders**.

2.  Kies in de lijst met servicebeheerders de gebruiker van wie u de aanduiding wilt wijzigen en kies vervolgens **Toegang beheren**..

3.  In het dialoogvenster **Toegang beheren** kiest u het toegangsniveau dat u aan de geselecteerde gebruiker wilt toewijzen. U kunt kiezen uit:

    -   **Volledige toegang**
    -   **Alleen-lezentoegang**
    -   **Helpdesk - knooppunt Groepen**

    Volledige toegang en Alleen-lezentoegang behoeven geen uitleg. <!--- **Helpdesk - Groups Node** allows users to choose from one of the following designations that provide custom levels of access to the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] admin console:--->

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

        -   Een apparaat vergrendelen op afstand

        -   Wachtwoordcode opnieuw instellen

Wanneer de gebruiker die u hebt geconfigureerd, de eerstvolgende keer de Intune-beheerconsole opent, krijgt deze het toegangsniveau dat u hebt opgegeven.


<!--HONumber=May16_HO1-->


