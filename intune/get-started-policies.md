---
title: Aan de slag met beleidsregels in Microsoft Intune
titlesuffix: ''
description: Maak beleidsregels om bedrijfsgegevens te beschermen en de apparaten te beheren die eindgebruikers gebruiken om toegang te krijgen tot bedrijfsbronnen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b8bffd0435988cc59c5c0e4d754b861729d466ae
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-with-creating-policies"></a>Aan de slag met het maken van beleidsregels

Eén van de belangrijkste doelen wanneer u aan de slag gaat met Intune is de registratie van apparaten, om ervoor te zorgen dat deze voldoen aan het bedrijfsbeleid. Nalevingsbeleid is niet alleen handig bij het beheren van gespecialiseerde apparaattypen, zoals kiosken in bedrijfseigendom, maar ook van persoonlijke apparaten (BYOD), tablets en apparaten zonder gebruiker.

![Dashboard voor compatibiliteit met weinig gegevens](/intune/media/generic-compliance-dashboard.png)

Beheer mobiele apparaten in de volgende gebieden met nalevingsbeleid:

* Reguleren van het aantal apparaten dat een gebruiker inschrijft
* Apparaatinstellingen beheren (zoals versleuteling op apparaatniveau, wachtwoordlengte en cameragebruik)
* Het leveren van apps, e-mailprofielen, VPN-profielen, enzovoort.
* Evalueren van criteria op apparaatniveau op naleving van beveiligingsbeleid

U stelt voor elk platform afzonderlijk nalevingsbeleid op. In dit voorbeeld hebben we gekozen voor iOS. De volgende beleidsregels zijn beschikbaar voor iOS-apparaten:

* Configuratie van de pincode of het wachtwoord
* Apparaatversleuteling
* Jailbreaking van apparaat
* E-mailprofiel
* Minimale versie van het besturingssysteem
* Maximale versie van het besturingssysteem

__Hoe maak ik een beleid?__

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer **Apparaatnaleving**.
4. Selecteer **Beleidsregels** in het deelvenster **Apparaatnaleving**.
5. Selecteer **Beleid maken** en geef de details op, zoals waarden voor **Naam** en **Beschrijving**. 
6. Kies **iOS** bij **Platform**.
6. Ga naar **Instellingen**, selecteer **Systeembeveiliging** en zet **Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten** op **Vereisen**. U kunt ook andere regels instellen, zoals **Minimale wachtwoordlengte**, **Vereist wachtwoordtype** en **Het minimumaantal niet-alfanumerieke tekens in een wachtwoord**. Als u tevreden bent over het beleid, selecteert u **OK**.
7. Ga terug naar het deelvenster **Beleid maken** en selecteer **Maken**.
8. Als het beleid is gemaakt, selecteert u **Toewijzingen** om het beleid toe te wijzen aan uw testgroep. Selecteer de testgroep (deze moet uw testgebruiker bevatten) en wijs het beleid toe aan die groep door op **Opslaan** te klikken.
9. Als het goed is, verschijnt er na een paar minuten een bericht met het verzoek om een nieuw wachtwoord in te stellen voor het apparaat om te blijven voldoen aan het bedrijfsbeleid. U kunt dit ook handmatig controleren in de **bedrijfsportal-app voor iOS** door op de naam van het apparaat te tikken en vervolgens op de knop **Synchroniseren**.

## <a name="next-steps"></a>Volgende stappen

[Aan de slag met het inschrijven van apparaten](get-started-enroll.md) - Maak kennis met het inschrijvingsproces door een volledige inschrijvingsprocedure voor een iOS-apparaat te doorlopen.

## <a name="learn-more"></a>Meer informatie

* [Nalevingsbeleid voor Intune-apparaten controleren](compliance-policy-monitor.md)
* [Gebruikelijke manieren om voorwaardelijk toegangsbeleid met Intune te gebruiken](conditional-access-intune-common-ways-use.md)
