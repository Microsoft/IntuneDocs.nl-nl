---
title: De bedrijfsportal-app van Windows 10 toevoegen en toewijzen voor apparaten die met Autopilot zijn ingericht
titleSuffix: Microsoft Intune
description: De bedrijfsportal-app van Windows 10 toevoegen en toewijzen aan Intune voor apparaten die met Autopilot zijn ingericht.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/21/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c13d8d774037f0d2db5832af7f39c864330fef30
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/25/2020
ms.locfileid: "77577282"
---
# <a name="add-and-assign-the-windows-10-company-portal-app-for-autopilot-provisioned-devices"></a>De bedrijfsportal-app van Windows 10 toevoegen en toewijzen voor apparaten die met Autopilot zijn ingericht

Uw gebruikers kunnen de bedrijfsportal-app gebruiken om apparaten te beheren en apps te installeren. U kunt de bedrijfsportal-app van Windows 10 rechtstreeks toewijzen vanuit Intune. 

## <a name="prerequisites"></a>Vereisten

Voor apparaten die met Windows 10 Autopilot zijn ingericht, kunt u het beste uw Microsoft Store voor Business-account koppelen aan Intune. Zie [In volume aangeschafte apps beheren vanuit de Microsoft Store voor Bedrijven met Microsoft Intune](~/apps/windows-store-for-business.md) voor meer informatie.

Bedrijfsportal (offline) is geselecteerd om te worden geïnstalleerd met behulp van de onderstaande stappen. De bedrijfsportal-app wordt in de apparaatcontext geïnstalleerd wanneer deze aan de Autopilot-groep is toegewezen en wordt op het apparaat geïnstalleerd vóór de gebruiker zich aanmeldt. 

## <a name="configure-settings-to-show-offline-apps"></a>Instellingen configureren om apps offline weer te geven
1. Meld u met uw beheerdersaccount aan bij [Microsoft Store voor Bedrijven](https://www.microsoft.com/business-store).
2. Selecteer het tabblad **Beheren** boven in het venster.
3. Selecteer **Instellingen** in het linkerdeelvenster.
4. Stel **Offline apps weergeven** onder **Winkelervaring** in op **Aan**.  
    De offline gelicentieerde apps worde weergegeven.

## <a name="get-the-offline-company-portal-app"></a>De offline bedrijfsportal-app downloaden
1. Zoek en selecteer de app **Bedrijfsportal**.
2. Stel het**Licentietype** in op **Offline**.
3. Selecteer **De app downloaden** om de offline bedrijfsportal-app te verkrijgen en toe te voegen aan uw inventaris.

## <a name="assign-the-company-portal-app"></a>De bedrijfsportal-app toewijzen
1. Meld u met uw beheerdersaccount aan bij het  [Beheercentrum voor Microsoft Eindpuntbeheer](https://go.microsoft.com/fwlink/?linkid=2109431) . 
2. Selecteer het tabblad  **Apps**  in het rechterdeelvenster. 
3. Onder  **Per platform** selecteert u **Windows**. 
4. Selecteer  **Bedrijfsportal (offline)** .   
5. Wacht tot de synchronisatieplanning is voltooid of voer een handmatige synchronisatie uit vanuit het Beheercentrum voor Microsoft Eindpuntbeheer.
6. Wijs de bedrijfsportal-app, indien nodig, toe als vereiste app aan geselecteerde groepen met Autopilot-apparaten.

## <a name="next-steps"></a>Volgende stappen

- Zie [Apps aan groepen toewijzen](apps-deploy.md) voor meer informatie over het toewijzen van apps.

