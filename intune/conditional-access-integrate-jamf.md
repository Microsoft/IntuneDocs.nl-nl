---
title: Jamf Pro integreren met Microsoft Intune voor naleving
titleSuffix: Microsoft Intune
description: Gebruik Microsoft Intune-nalevingsbeleid met voorwaardelijke toegang van Azure Active Directory om met Jamf beheerde apparaten te beveiligen.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 57527d0b1825d0e8d3fefb63d1b960ab3fb5c676
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59569477"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Jamf Pro integreren met Intune in verband met nalevingsbeleid

Van toepassing op: Intune in Azure Portal

Als uw organisatie gebruikmaakt van [Jamf Pro](https://www.jamf.com) voor het beheren van de Macs van uw eindgebruikers, kunt u gebruikmaken van Microsoft Intune-nalevingsbeleid met voorwaardelijke toegang tot Azure Active Directory om ervoor te zorgen dat apparaten in uw organisatie compatibel zijn.

## <a name="prerequisites"></a>Vereisten

U hebt het volgende nodig om voorwaardelijke toegang met Jamf Pro te configureren:

- Jamf Pro 10.1.0 of hoger
- [Bedrijfsportal-app voor macOS ](https://aka.ms/macoscompanyportal)
- macOS-apparaten met OS X 10.11 Yosemite of hoger

## <a name="connecting-intune-to-jamf-pro"></a>Verbinding van Intune met Jamf Pro

U kunt Intune als volgt verbinden met Jamf Pro:

1. Een nieuwe toepassing maken in Azure
2. Intune instellen op integratie met Jamf Pro
3. Voorwaardelijke toegang in Jamf Pro configureren

## <a name="create-an-application-in-azure-active-directory"></a>Een toepassing maken in Azure Active Directory

1. Ga in [Azure Portal](https://portal.azure.com) naar **Azure Active Directory** > **App-registraties**.
2. Selecteer **+Nieuwe toepassing registreren**.
3. Voer een **weergavenaam** in, zoals **Voorwaardelijke toegang tot Jamf**.
4. Selecteer **Web-app/API**.
5. Geef de **aanmeldings-URL** op met behulp van de URL van uw Jamf Pro-exemplaar.
6. Selecteer **Maken**. De toepassing is gemaakt en de portal bevat de details van de toepassing.
7. Sla een kopie van de **toepassings-id** op voor de nieuwe toepassing. U moet deze later opgeven tijdens een andere procedure. Selecteer vervolgens **instellingen** en ga naar **API-toegang** > **Sleutels**.
8. Geef in het deelvenster *Sleutels* een **beschrijving** op, geef aan hoelang moet worden gewacht voordat de sleutel **verloopt** en selecteer vervolgens **Opslaan** om de toepassingssleutel (waarde) te genereren Application Key (Value).

   > [!IMPORTANT]
   > De toepassingssleutel wordt tijdens dit proces maar één keer weergegeven. Bewaar de sleutel op een locatie waar u deze eenvoudig kunt terugvinden.

8. Navigeer in het deelvenster *Instellingen* van de app naar **API-toegang** > **Vereiste machtigingen**. Selecteer de bestaande machtigingen en klik vervolgens op **Verwijderen** om alle machtigingen te verwijderen. De bestaande machtigingen moeten worden verwijderd omdat u een nieuwe machtiging toevoegt en de toepassing alleen werkt als deze ene vereiste machtiging is toegekend.  
9. Als u een nieuwe machtiging wilt toewijzen, selecteert u **+Toevoegen** > **Een API selecteren** > **Microsoft Intune-API** en klikt u vervolgens op **Selecteren**.
10. Selecteer in het deelvenster *Toegang inschakelen* de optie **Apparaatkenmerken naar Microsoft Intune verzenden** en klik achtereenvolgens op **Selecteren** en **Gereed**.
11. Selecteer in het deelvenster *Vereiste machtigingen* achtereenvolgens **Machtigingen verlenen** en **Ja** om de vereiste machtigingen op de toepassing toe te passen.

    > [!NOTE]
    > Als de toepassingssleutel is verlopen, moet u een nieuwe toepassingssleutel maken in Microsoft Azure en vervolgens de gegevens voor voorwaardelijke toegang in Jamf Pro bijwerken. U kunt in Azure zowel de oude als de nieuwe sleutel activeren om serviceonderbrekingen te voorkomen.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Intune instellen op integratie met Jamf Pro

1. Ga in [Azure Portal](https://portal.azure.com) naar **Microsoft Intune** > **Apparaatcompatibiliteit** > **Apparaatbeheer partner** .
2. Schakel de nalevingsconnector voor Jamf in door de toepassings-id die u tijdens de vorige procedure hebt opgeslagen, in het veld **Azure Active Directory-app-id voor Jamf** te plakken.
3. Selecteer **Opslaan**.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Microsoft Intune-integratie in Jamf Pro configureren

1. Navigeer in Jamf Pro naar **Global Management** > **Conditional Access**. Klik op de knop **Edit** op het tabblad **Microsoft Intune Integration**.
2. Schakel het selectievakje voor **Enable Microsoft Intune Integration** in.
3. Geef de vereiste gegevens op over uw Azure-tenant, met inbegrip van **Location**, **Domain name**, plus de **Application ID** en de **Application Key** die u in de vorige stappen hebt opgeslagen.
4. Selecteer **Opslaan**. Jamf Pro test uw instellingen en bevestigt of ze juist zijn.

## <a name="set-up-compliance-policies-and-register-devices"></a>Nalevingsbeleid instellen en apparaten registreren

Nadat u de integratie tussen Intune en Jamf hebt geconfigureerd, moet u [nalevingsbeleid toepassen op door Jamf beheerde apparaten](conditional-access-assign-jamf.md).



## <a name="next-steps"></a>Volgende stappen

- [Nalevingsbeleid toepassen op door Jamf beheerde apparaten](conditional-access-assign-jamf.md)
- [Gegevens die Jamf verzendt naar Intune](data-jamf-sends-to-intune.md)
