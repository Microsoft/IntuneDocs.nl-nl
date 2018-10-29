---
title: 'Snelstart: een vereiste wachtwoordlengte instellen voor Android-apparaten'
titlesuffix: Microsoft Intune
description: In deze snelstart gaat u Microsoft Intune gebruiken om een wachtwoordlengte in te stellen die is vereist voor Android-apparaten.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/17/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 81b4fa08-5333-4c54-9f49-8db5f6984ed2
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f925df731c3ddd45b13d976b0686d76d941c71e6
ms.sourcegitcommit: 2e88ec7a412a2db35034d30a70d20a5014ddddee
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/17/2018
ms.locfileid: "49395276"
---
# <a name="quickstart-set-a-required-password-length-for-android-devices"></a>Snelstart: een vereiste wachtwoordlengte instellen voor Android-apparaten

In deze snelstart gaat u Microsoft Intune gebruiken om de gebruikers van Android onder uw werknemers te verplichten een wachtwoord van een voorgeschreven lengte in te voeren om toegang te krijgen tot informatie op hun Android-apparaten. 

> [!IMPORTANT]
> Naast wachtwoordinstellingen moet u ook overwegen andere systeembeveiligingsinstellingen te gebruiken om uw medewerkers te beveiligen. Zie [Systeembeveiligingsinstellingen](compliance-policy-create-android-for-work.md#system-security-settings) voor meer informatie.

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u aan bij [Intune](https://aka.ms/intuneportal) als globale beheerder of beheerder van een Intune-service. U gaat in Azure Portal naar Intune door **Alle services** > **Intune** te kiezen. Intune bevindt zich in de sectie **Controle en beheer**.

## <a name="create-a-device-compliance-policy"></a>Een nalevingsbeleid voor apparaten maken
1. Zodra u de blade **Microsoft Intune** hebt geopend, selecteert u **Apparaatnaleving** > **Beleid** > **Beleid maken**.
2. Voeg **Android-naleving** toe als **naam**. Voeg ook een **beschrijving** toe.
3. Selecteer voor **Platform** de optie **Android**. 
4. Selecteer **Instellingen** > **Systeembeveiliging** om de Android-blade **Systeembeveiliging** weer te geven.
5. In de sectie **Wachtwoord** klikt u naast **Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten** op **Vereisen**.
6. Geef naast **Minimale wachtwoordlengte** **6** op.  

    ![Schermopname van het maken van een groep in Microsoft Intune](./media/quickstart-set-password-length-android-01.png)

7. Wanneer u klaar bent, klikt u op **OK** om de blade **Systeembeveiliging** te sluiten. 
8. Klik op **OK** om de blade **Nalevingsbeleid voor Android** te sluiten. 
9. Klik op **Maken** om het beleid te maken.

Als het beleid is gemaakt, wordt dit weergegeven in de lijst **Apparaatnaleving - Beleid**. 

## <a name="next-steps"></a>Volgende stappen

In deze snelstart hebt u Intune gebruikt om een nalevingsbeleid te maken voor de Android-apparaten van uw werknemers om een wachtwoord van ten minste zes tekens lang te vereisen.

> [!div class="nextstepaction"]
> [Automatische inschrijving instellen](quickstart-setup-auto-enrollment.md)
