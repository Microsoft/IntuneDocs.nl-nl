---
title: Windows 10-apparaten met Microsoft Intune opnieuw instellen - Azure | Microsoft Docs
description: Gebruik Nieuwe start om apps op Windows 10-pc's te verwijderen met behulp van Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/27/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8e48b7dac5064f9daeb62e141a4c1b2a4adf11b7
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77782198"
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Nieuwe start gebruiken om Windows 10-apparaten opnieuw in te stellen met Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Met de apparaatactie **Nieuwe start** worden alle apps verwijderd die zijn geïnstalleerd op Windows 10-pc's, versie 1703 of later. Met Nieuwe start worden vooraf geïnstalleerde apps (OEM-apps) verwijderd die doorgaans op nieuwe pc's staan. 

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) en selecteer **Apparaten** > **Alle apparaten**.
2. Kies in de lijst met apparaten die u beheert een Windows 10-desktopapparaat.
3. Klik op **Nieuwe start**. 
4. Selecteer **Gebruikersgegevens op dit apparaat behouden** om:
   * Het apparaat toegevoegd te houden aan Azure AD
   * Het apparaat wordt opnieuw ingeschreven bij Mobile Device Management wanneer een gebruiker voor wie Azure Active Directory is ingeschakeld zich bij het apparaat aanmeldt.
   * De inhoud uit de basismap van de gebruiker te behouden en alleen apps en instellingen te verwijderen

  > [!IMPORTANT]
 > Als u gebruikersgegevens niet behoudt, wordt het apparaat teruggezet naar de toestand van de voltooide OOBE (Out-Of-Box Experience), met behoud van de ingebouwde beheerdersaccount.
 > BYOD-apparaten worden uitgeschreven bij Azure AD en Mobile Device Management.
 > Aan Azure AD gekoppelde apparaten worden opnieuw bij mobiel apparaatbeheer geregistreerd wanneer een gebruiker voor wie Azure Active Directory is ingeschakeld zich bij het apparaat aanmeldt.
 
5. Klik op **OK**.   
6. Als u de status van deze actie wilt bekijken, gaat u terug naar **Apparaten** en klikt u op **Apparaatacties**.  
7. Het apparaat wordt teruggezet naar het eerste aanmeldingsscherm.
