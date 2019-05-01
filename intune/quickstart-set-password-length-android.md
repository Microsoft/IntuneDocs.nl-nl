---
title: 'Snelstart: Beleid voor wachtwoordcompatibiliteit voor Android-apparaten'
titleSuffix: Microsoft Intune
description: In deze snelstartgids gaat u Microsoft Intune gebruiken om de wachtwoordlengte in te stellen die is vereist voor Android-apparaten.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/15/2019
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 81b4fa08-5333-4c54-9f49-8db5f6984ed2
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e71a9a69cfc474f311bc6acd9e8f24c776a44476
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61512776"
---
# <a name="quickstart-create-a-password-compliance-policy-for-android-devices"></a>Quickstart: Een beleid voor wachtwoordcompatibiliteit maken voor Android-apparaten

In deze snelstart gaat u Microsoft Intune gebruiken om de gebruikers van Android onder uw werknemers te verplichten een wachtwoord van een voorgeschreven lengte in te voeren om toegang te krijgen tot informatie op hun Android-apparaten. 

Een Intune-beleid voor apparaatcompatibiliteit bepaalt de regels en instellingen waaraan apparaten moeten voldoen om als compatibel te worden beschouwd. U kunt compatibiliteitsbeleid met voorwaardelijke toegang gebruiken om toegang tot bedrijfsresources toe te staan of te blokkeren. U kunt ook apparaatrapporten krijgen en maatregelen nemen voor niet-naleving.

> [!IMPORTANT]
> Naast wachtwoordinstellingen moet u ook overwegen andere systeembeveiligingsinstellingen te gebruiken om uw medewerkers te beveiligen. Zie [Systeembeveiligingsinstellingen](compliance-policy-create-android-for-work.md) voor meer informatie.

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u aan bij [Intune](https://aka.ms/intuneportal) als globale beheerder of beheerder van een Intune-service. 

## <a name="create-a-device-compliance-policy"></a>Een nalevingsbeleid voor apparaten maken

Voor deze snelstartgids gaat u Intune gebruiken om de gebruikers van Android onder uw werknemers te verplichten een wachtwoord van een voorgeschreven lengte in te voeren om toegang te krijgen tot informatie op hun Android-apparaten.

1. In Intune selecteert u **Apparaatconformiteit** > **Beleid** > **Beleid maken**.
2. Voeg **Android-naleving** toe als **naam**. Voeg ook een **beschrijving** toe.
3. Selecteer voor **Platform** de optie **Android**. 
4. Selecteer **Instellingen** > **Systeembeveiliging** om de Android-blade **Systeembeveiliging** weer te geven.
5. Klik op **Vereisen** naast **Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**.
6. Selecteer **Ten minste numeriek** naast **Vereist wachtwoordtype**.
7. Voer **6** in naast **Minimale wachtwoordlengte**. 

    ![Schermopname van het maken van een groep in Microsoft Intune](media/quickstart-set-password-length-android/quickstart-set-password-length-android-01.png)

7. Wanneer u klaar bent, klikt u op **OK** > **OK** > **Maken** om het beleid te maken.

Als het beleid is gemaakt, wordt dit weergegeven in de lijst van compatibiliteitsbeleid voor apparaten. 

## <a name="clean-up-resources"></a>Resources opschonen

Als u het beleid niet meer nodig hebt, kunt u het verwijderen. Hiervoor selecteert u het compatibiliteitsbeleid en klikt u op **Verwijderen**.

## <a name="next-steps"></a>Volgende stappen

In deze snelstart hebt u Intune gebruikt om een nalevingsbeleid te maken voor de Android-apparaten van uw werknemers om een wachtwoord van ten minste zes tekens lang te vereisen. Zie [Aan de slag met compatibiliteitsbeleid voor apparaten in Intune](device-compliance-get-started.md) voor meer informatie over het maken van compatibiliteitsbeleid voor apparaten.

Als u deze reeks snelstartgidsen voor Intune wilt volgen, kunt u doorgaan met de volgende snelstartgids.

> [!div class="nextstepaction"]
> [Quickstart: Meldingen verzenden naar niet-compatibele apparaten](quickstart-send-notification.md)
