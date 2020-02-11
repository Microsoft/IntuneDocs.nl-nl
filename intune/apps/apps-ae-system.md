---
title: Android Enterprise-systeem-apps toevoegen aan Microsoft Intune
titleSuffix: ''
description: Leer Android Enterprise-systeem-apps toevoegen aan Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 613369070d847265f371a7b228a2b6d81bf813fe
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755252"
---
# <a name="add-android-enterprise-system-apps-to-microsoft-intune"></a>Android Enterprise-systeem-apps toevoegen aan Microsoft Intune

Voordat u een app toewijst aan een apparaat of een groep gebruikers, moet u de app toevoegen aan Microsoft Intune. Systeem-apps worden ondersteund op Android Enterprise-apparaten. U kunt een systeem-app inschakelen voor [toegewezen Android Enterprise-apparaten](../enrollment/android-kiosk-enroll.md) of [volledig beheerde apparaten](../enrollment/android-fully-managed-enroll.md).

## <a name="add-the-app"></a>De app toevoegen

Met de volgende stappen kunt u een Android Enterprise-systeem-app toevoegen aan Intune via Azure Portal:

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. In het deelvenster **Een app-type selecteren** selecteert u **Android Enterprise-systeem-app** bij de beschikbare **Overige** typen.
4. Klik op **Selecteren**. De stappen **App toevoegen** worden weergegeven.
Voeg in het deelvenster **App-gegevens** de app-gegevens toe:
    - **App-naam**: Voer de naam van de app in.
    - **Uitgever**: Voer de naam van de uitgever van de app in.  
    - **Pakketnaam**: Voer een pakketnaam in. Intune controleert of de pakketnaam geldig is.
5. Klik op **Volgende** om de pagina **Bereiktags** weer te geven.
8. Klik op **Bereiktags selecteren** om desgewenst bereiktags toe te voegen voor de app. Zie [Op rollen gebaseerd toegangsbeheer (RBAC) en bereiktags gebruiken voor gedistribueerde IT](~/fundamentals/scope-tags.md) voor meer informatie.
9. Klik op **Volgende** om de pagina **Toewijzingen** weer te geven.
10. Selecteer de groepstoewijzingen voor de app. Zie [Groepen toevoegen om gebruikers en apparaten te organiseren](~/fundamentals/groups-add.md) voor meer informatie. 
11. Klik op **Volgende** om naar de pagina **Controleren en maken** weer te geven. Controleer de waarden en instellingen die u hebt ingevoerd voor de app.
12. Klik als u klaar bent op **Maken** om de app toe te voegen aan Intune.

De blade **Overzicht** van de app die u hebt gemaakt, wordt weergegeven.

> [!NOTE]
> U moet samenwerken met de OEM van uw apparaat om de pakketnaam te vinden van de app die u wilt in- of uitschakelen.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u selecteert. 

Android Enterprise-systeem-apps schakelen apps die al deel uitmaken van het platform in of uit. Als u een app wilt inschakelen, wijst u de systeem-app toe als **Vereist**. Als u een app wilt uitschakelen, wijst u de systeem-app toe als **Verwijderen**. Systeem-apps kunnen niet worden toegewezen als beschikbaar voor een gebruiker.


## <a name="next-steps"></a>Volgende stappen

- [Apps aan groepen toewijzen](apps-deploy.md)
