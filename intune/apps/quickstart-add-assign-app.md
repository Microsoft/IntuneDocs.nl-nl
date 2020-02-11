---
title: 'Snelstartgids: Een client-app toevoegen en toewijzen'
titleSuffix: Microsoft Intune
description: In deze snelstartgids gaat u met Microsoft Intune een client-app toevoegen en toewijzen.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dab6f5c8-1ebb-42c4-a7a7-7af001f94e15
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 40337b3c45885dacf486173814044a27b7f3f6cc
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755065"
---
# <a name="quickstart-add-and-assign-a-client-app"></a>Quickstart: Een client-app toevoegen en toewijzen

In deze snelstartgids gaat u met behulp van Microsoft Intune een client-app toevoegen en toewijzen aan de werknemers van uw bedrijf. Een van de prioriteiten van een beheerder is om ervoor te zorgen dat eindgebruikers toegang hebben tot de apps die ze nodig hebben voor hun werk. 

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Vereisten

- Als u deze snelstartgids wilt uitvoeren, moet u [een gebruiker maken](../fundamentals/quickstart-create-user.md), [een groep maken](../fundamentals/quickstart-create-group.md) en [een apparaat inschrijven](../quickstart-setup-auto-enrollment.md).

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u aan bij [Intune](https://aka.ms/intuneportal) als [globale beheerder of beheerder van een Intune-service](../fundamentals/users-add.md#types-of-administrators). Als u een Intune-proefabonnement hebt gemaakt, is het account waarmee u het abonnement hebt gemaakt de globale beheerder.

## <a name="add-the-client-app-to-intune"></a>De client-app toevoegen aan Intune

U kunt een app opnemen zodat u met Intune aspecten van de app kunt beheren. 

Gebruik de volgende stappen om een app aan Intune toe te voegen:
1. Selecteer in [Intune](https://aka.ms/intuneportal) de opties **Apps** > **Alle apps** > **Toevoegen**. 
2. Selecteer **Windows 10** in het gedeelte **Office 365-suite** van het deelvenster **Een app-type selecteren**.
3. Klik op **Selecteren**. De stappen **App toevoegen** worden weergegeven.
4. Bevestig de standaardgegevens op de pagina **Gegevens over de app-suite**.
5. Klik op **Volgende** om de pagina **App-suite configureren** weer te geven.
6. Selecteer naast **Updatekanaal** de optie **Maandelijks** in de vervolgkeuzelijst.
7. Bevestig de overige standaardgegevens op de pagina ***App-suite configureren**.
8. Klik op **Volgende** om de pagina **Bereiktags** weer te geven.
9. Klik op **Bereiktags selecteren** om desgewenst bereiktags toe te voegen voor de app. Zie [Op rollen gebaseerd toegangsbeheer (RBAC) en bereiktags gebruiken voor gedistribueerde IT](~/fundamentals/scope-tags.md) voor meer informatie.
10. Klik op **Volgende** om de pagina **Toewijzingen** weer te geven.
11. Selecteer de groepstoewijzingen voor de app. Zie [Groepen toevoegen om gebruikers en apparaten te organiseren](~/fundamentals/groups-add.md) voor meer informatie. 
12. Klik op **Volgende** om naar de pagina **Controleren en maken** weer te geven. Controleer de waarden en instellingen die u hebt ingevoerd voor de app.
13. Klik als u klaar bent op **Maken** om de app toe te voegen aan Intune.

## <a name="assign-the-app-to-a-group"></a>De app toewijzen aan een groep

Wanneer u een app aan Microsoft Intune hebt toegevoegd, kunt u de app toewijzen aan groepen gebruikers en apparaten.

> [!NOTE]
> Deze quickstart bouwt voort op eerdere quickstarts in deze reeks. Raadpleeg [Vereisten](quickstart-add-assign-app.md#prerequisites) in deze snelstartgids voor meer informatie.

Gebruik de volgende stappen om een app aan een groep toe te voegen:
1. Selecteer in [Intune](https://aka.ms/intuneportal) de opties **Apps** > **Alle apps**. 
2. Selecteer de app die u aan een groep wilt toewijzen.
3. Klik op **Toewijzingen** > **Groep toevoegen** om het deelvenster **Groep toevoegen** weer te geven.
4. Selecteer **Beschikbaar voor ingeschreven apparaten** in de vervolgkeuzelijst **Toewijzingstype**. 
5. Kies **Opgenomen groepen** > **Op te nemen groepen selecteren** > **Contoso-testers**.
6. Klik op **Selecteren** > **OK** > **OK** > **Opslaan** om de groep toe te wijzen.

U hebt nu de app aan de groep **Contoso Testers** toegewezen.

## <a name="install-the-app-on-the-enrolled-device"></a>De app op het ingeschreven apparaat installeren

U moet de bedrijfsportal-app installeren en gebruiken voor het installeren van de app **Contoso-takenlijst** die beschikbaar is gesteld door Intune. Gebruik de volgende stappen om te controleren of de app beschikbaar is voor de gebruiker van het ingeschreven apparaat.

1. Meld u aan bij uw ingeschreven Windows 10 Desktop-apparaat.

    > [!IMPORTANT]
    > Het apparaat moet [bij Intune zijn ingeschreven](../quickstart-enroll-windows-device.md). U moet zich ook aanmelden bij het apparaat met een account at is opgenomen in de groep die u aan de app hebt toegewezen.

2. Open vanuit het menu **Start** **Microsoft Store**. Zoek vervolgens de app **Bedrijfsportal** en installeer deze.
3. Start de app **Bedrijfsportal**.
4. Klik op de app die u met behulp van Intune hebt toegevoegd. In deze snelstartgis hebt u de app **Suite Microsoft Office 365-apps** toegevoegd.

    > [!NOTE]
    > Als u geen apps aan de Intune-gebruiker hebt kunnen toewijzen, ziet u het volgende bericht: *Uw IT-beheerder heeft geen apps beschikbaar gemaakt voor u.*

5. Klik op **Installeren**.

Als uw bedrijf vereist dat u de bedrijfsportal-app aan uw werknemers toewijst, kunt u de Windows 10-bedrijfsportal-app handmatig rechtstreeks toewijzen vanuit Intune. Zie [De Windows 10-bedrijfsportal-app handmatig toevoegen met Microsoft Intune](../company-portal-app.md) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

In deze snelstartgids hebt u apps aan Intune toegevoegd, de apps aan een groep toegewezen en de apps op het ingeschreven Windows 10 Desktop-apparaat geïnstalleerd. Zie [Wat is Microsoft Intune-appbeheer?](app-management.md) voor meer informatie over het beheren van apps in Intune.

Als u deze reeks snelstartgidsen voor Intune wilt volgen, kunt u doorgaan met de volgende snelstartgids.

> [!div class="nextstepaction"]
> [Quickstart: Een beveiligingsbeleid voor apps maken en toewijzen](quickstart-create-assign-app-policy.md)
