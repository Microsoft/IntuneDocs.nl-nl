---
title: Windows 10-apparaten met Microsoft Intune opnieuw instellen - Azure | Microsoft Docs
description: Gebruik Nieuwe start om apps op Windows 10-pc's te verwijderen met behulp van Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/09/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 230c328c14f0da39db34c8b91ac30fe05f9b05ca
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57388196"
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Nieuwe start gebruiken om Windows 10-apparaten opnieuw in te stellen met Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met de apparaatactie **Nieuwe start** worden alle apps verwijderd die zijn geïnstalleerd op Windows 10-pc's, versie 1703 of later. Met Nieuwe start worden vooraf geïnstalleerde apps (OEM-apps) verwijderd die doorgaans op nieuwe pc's staan.  

1. Meld u aan bij [Azure Portal](https://portal.azure.com) en ga naar > **Microsoft Intune** > **Apparaten** > **Alle apparaten**.
2. Kies in de lijst met apparaten die u beheert een Windows 10-desktopapparaat.
3. Klik op **Nieuwe start**. 
4. Selecteer **Gebruikersgegevens op dit apparaat behouden** om:
   * Het apparaat toegevoegd te houden aan Azure AD
    * Het apparaat wordt opnieuw bij mobiel apparaatbeheer geregistreerd wanneer een gebruiker voor wie Azure Active Directory is ingeschakeld zich bij het apparaat aanmeldt.
    * De inhoud uit de basismap van de gebruiker te behouden en alleen apps en instellingen te verwijderen  
  > [!IMPORTANT]
 > Als u de gebruikersgegevens niet behoudt, wordt het apparaat hersteld naar de standaardinstellingen. BYOD-apparaten worden uitgeschreven bij Azure AD en Mobile Device Management.
 > Aan Azure AD gekoppelde apparaten worden opnieuw bij mobiel apparaatbeheer geregistreerd wanneer een gebruiker voor wie Azure Active Directory is ingeschakeld zich bij het apparaat aanmeldt.
 
5. Klik op **OK**.   
6. Als u de status van deze actie wilt bekijken, gaat u terug naar **Apparaten** en klikt u op **Apparaatacties**.  
