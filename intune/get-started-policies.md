---
title: Aan de slag met beleid in Microsoft Intune - Azure | Microsoft Docs
description: Maak beleidsregels om bedrijfsgegevens te beschermen en de apparaten te beheren die eindgebruikers gebruiken om toegang te krijgen tot bedrijfsbronnen. Wijs het beleid vervolgens toe aan groepen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d7fa1b596a1800971919cfc0ab3e94d2d16ec328
ms.sourcegitcommit: afda8a0fc0f615e976b18ddddf81d56d7ae3566e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/20/2018
ms.locfileid: "36271521"
---
# <a name="get-started-with-creating-policies"></a>Aan de slag met het maken van beleidsregels

Intune-beleidsregels zijn een uitstekende manier om apparaten in te schrijven en ervoor te zorgen dat ze voldoen aan uw bedrijfsbeleid. Nalevingsbeleid is handig om gespecialiseerde apparaattypen te beheren, zoals kiosken in bedrijfseigendom en persoonlijke apparaten (BYOD), tablets en apparaten zonder gebruiker.

![Dashboard voor compatibiliteit met weinig gegevens](/intune/media/generic-compliance-dashboard.png)

Mobiele apparaten kunnen worden beheerd met nalevingsbeleid, met inbegrip van:

* Reguleren van het aantal apparaten dat een gebruiker in Intune inschrijft
* Beheren van apparaatinstellingen, zoals versleuteling op apparaatniveau, wachtwoordlengte en cameragebruik
* Leveren van apps, e-mailprofielen, VPN-profielen en meer
* Evalueren van criteria op apparaatniveau op naleving van beveiligingsbeleid

Nalevingsbeleid wordt gemaakt voor elk platform, zoals iOS, Android, Windows en meer. Gebruik iOS voor deze oefening. De volgende beleidsregels zijn beschikbaar voor iOS-apparaten:

* Configuratie van de pincode of het wachtwoord
* Apparaatversleuteling
* Jailbreaking van apparaat
* E-mailprofiel
* Minimale versie van het besturingssysteem
* Maximale versie van het besturingssysteem

## <a name="create-a-policy"></a>Een beleid maken

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaatcompatibiliteit** > **Beleid** > **Beleid maken**.
4. Voer een **beleidsnaam** en een **beschrijving** in. 
5. Selecteer bij **Platform** de optie **iOS**.
6. Ga naar **Instellingen**, selecteer **Systeembeveiliging** en stel **Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten** in op **Vereisen**. 

    U kunt ook andere regels instellen, zoals: 
    - **Minimale wachtwoordlengte**
    - **Vereist wachtwoordtype**
    - **Het aantal niet-alfanumerieke tekens in het wachtwoord**
    
    Wanneer u klaar bent met het instellen van het beleid, selecteert u **OK**.
  
7. Ga terug naar **Beleid maken** en selecteer **Maken**. Met deze stap maakt u het beleid en geeft u dit beleid weer in **Apparaatcompatibiliteit** > **Beleid**.
8. Selecteer het nieuwe beleid en kies **Toewijzingen**. U kunt Azure Active Directory-beveiligingsgroepen (AD) opnemen of uitsluiten.
Kies Geselecteerde groepen om uw bestaande Azure AD-beveiligingsgroepen te zien. Selecteer de gebruikersgroepen waarop u dit beleid wilt toepassen en kies **Opslaan** om het beleid te implementeren op gebruikers.

Om te voldoen aan het nieuwe bedrijfsbeleid, wordt u op het ingeschreven apparaat na een paar minuten gevraagd om een bijgewerkt wachtwoord. U kunt handmatig controleren op de update in de **Bedrijfsportal-app voor iOS**. Open de Bedrijfsportal-app, selecteer de naam van het apparaat en selecteer vervolgens **Sync**.

> [!NOTE]
> Het kan maximaal acht uur duren voordat nieuw beleid dat is toegepast op een dynamische apparaatgroep wordt toegepast op alle apparaten in de groep.

## <a name="next-steps"></a>Volgende stappen

[Aan de slag met het inschrijven van apparaten](get-started-enroll.md) - Maak kennis met het inschrijvingsproces door een volledige inschrijvingsprocedure voor een iOS-apparaat te doorlopen.

## <a name="learn-more"></a>Meer informatie

* [Nalevingsbeleid voor Intune-apparaten controleren](compliance-policy-monitor.md)
* [Gebruikelijke manieren om voorwaardelijk toegangsbeleid met Intune te gebruiken](conditional-access-intune-common-ways-use.md)
