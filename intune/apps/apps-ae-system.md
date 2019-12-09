---
title: Android Enterprise-systeem-apps toevoegen aan Microsoft Intune
titleSuffix: ''
description: Leer Android Enterprise-systeem-apps toevoegen aan Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
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
ms.openlocfilehash: d45455a97f8016527dce49839b5493f16b173d43
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563645"
---
# <a name="add-android-enterprise-system-apps-to-microsoft-intune"></a>Android Enterprise-systeem-apps toevoegen aan Microsoft Intune

Voordat u een app toewijst aan een apparaat of een groep gebruikers, moet u de app toevoegen aan Microsoft Intune. Systeem-apps worden ondersteund op Android Enterprise-apparaten. U kunt een systeem-app inschakelen voor [toegewezen Android Enterprise-apparaten](../enrollment/android-kiosk-enroll.md) of [volledig beheerde apparaten](../enrollment/android-fully-managed-enroll.md).

## <a name="add-the-app"></a>De app toevoegen

Met de volgende stappen kunt u een Android Enterprise-systeem-app toevoegen aan Intune via Azure Portal:

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. In het deelvenster **App toevoegen** selecteert u **Android Enterprise-systeem-app** bij de beschikbare **Overige** typen.
4. Als u de app-gegevens wilt configureren, selecteert u **Configureren** en geeft u de volgende informatie op:
    - **App-naam**: Voer de naam van de app in.
    - **Uitgever**: Voer de naam van de uitgever van de app in.  
    - **Pakketnaam**: Voer een pakketnaam in. Intune controleert of de pakketnaam geldig is.
5. Selecteer **OK**.
6. Selecteer **Toevoegen**.

> [!NOTE]
> U moet samenwerken met de OEM van uw apparaat om de pakketnaam te vinden van de app die u wilt in- of uitschakelen.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u selecteert. 

Android Enterprise-systeem-apps schakelen apps die al deel uitmaken van het platform in of uit. Als u een app wilt inschakelen, wijst u de systeem-app toe als **Vereist**. Als u een app wilt uitschakelen, wijst u de systeem-app toe als **Verwijderen**. Systeem-apps kunnen niet worden toegewezen als beschikbaar voor een gebruiker.


## <a name="next-steps"></a>Volgende stappen

- [Apps aan groepen toewijzen](apps-deploy.md)
