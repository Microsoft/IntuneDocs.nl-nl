---
title: Jamf Pro integreren met Microsoft Intune voor naleving
titleSuffix: Microsoft Intune
description: Gebruik Microsoft Intune-nalevingsbeleid met voorwaardelijke toegang van Azure Active Directory om met Jamf beheerde apparaten te beveiligen.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/16/2019
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
ms.openlocfilehash: cac92aeac895201459e692aae164f51dab10dfb0
ms.sourcegitcommit: ca0f48982e49e90bc14fac5575077445e027f728
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/16/2019
ms.locfileid: "65712623"
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

1. Ga in de [Azure-portal](https://portal.azure.com) naar **Azure Active Directory** > **App-registraties** en selecteer **Nieuwe registratie**. 

2. Geef op de pagina **Een toepassing registreren** de volgende gegevens op:
   - Geef bij **Naam** een betekenisvolle naam op voor de toepassing, bijvoorbeeld **Jamf Conditional Access**.
   - Selecteer **Accounts in een organisatieadreslijst** bij **Ondersteunde accounttypen**. 
   - Laat bij **Omleidings-URI** de standaardwaarde Web staan en geef vervolgens de URL voor uw exemplaar van Jamf Pro op.  

3. Selecteer **Registreren** om de toepassing te maken en om de pagina Overzicht voor de nieuwe app te openen.  

4. Kopieer op de pagina **Overzicht** de waarde van **Toepassings-id (client-id)** en noteer de waarde voor later gebruik. U hebt deze waarde in latere procedures nodig.  

5. Selecteer **Certificaten en geheimen** onder **Beheren**. Selecteer de knop **Nieuw clientgeheim**. Voer een waarde in voor **Beschrijving**, selecteer een optie voor **Verloopt** en kies **Toevoegen**.

   > [!IMPORTANT]  
   > Voordat u deze pagina verlaat, moet u de waarde voor het clientgeheim kopiëren en bewaren voor later gebruik. U hebt deze waarde in latere procedures nodig. Deze waarde kunt u niet meer weergeven, alleen door de app opnieuw te registreren.  

6. Selecteer **API-machtigingen** onder Beheren.  Selecteer de bestaande machtigingen en selecteer vervolgens **Machtigingen verwijderen** om deze machtigingen te verwijderen. De bestaande machtigingen moeten allemaal worden verwijderd omdat u een nieuwe machtiging toevoegt en de toepassing alleen werkt als deze ene vereiste machtiging is toegekend.  

7. Als u een nieuwe machtiging wilt toewijzen, selecteert u **Een machtiging toevoegen**. Selecteer op de pagina **API-machtigingen aanvragen** de optie **Intune** en selecteer vervolgens **Toepassingsmachtigingen**. Schakel alleen het selectievakje voor **update_device_attributes** in.  

   Selecteer **Machtiging toevoegen** om deze configuratie op te slaan.  

8. Selecteer op de pagina **API-machtigingen** de optie **Beheerder toestemming geven voor Microsoft** en selecteer vervolgens Ja.  

   Het registratieproces voor de app in Azure AD is voltooid.


    > [!NOTE]
    > Als het clientgeheim is verlopen, moet u een nieuw clientgeheim maken in Azure en vervolgens de gegevens voor voorwaardelijke toegang in Jamf Pro bijwerken. In Azure kan zowel het oude geheim als de nieuwe sleutel actief zijn om serviceonderbrekingen te voorkomen.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Intune instellen op integratie met Jamf Pro

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=20909) en ga naar **Microsoft Intune** > **Apparaatcompatibiliteit** > **Apparaatbeheer partner**.

2. Schakel de nalevingsconnector voor Jamf in door de toepassings-id die u tijdens de vorige procedure hebt opgeslagen, in het veld **Azure Active Directory-app-id voor Jamf** te plakken.

3. Selecteer **Opslaan**.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Microsoft Intune-integratie in Jamf Pro configureren

1. Navigeer in Jamf Pro naar **Global Management** > **Conditional Access**. Klik op de knop **Edit** op het tabblad **Microsoft Intune Integration**.

2. Schakel het selectievakje voor **Enable Microsoft Intune Integration** in.

3. Geef de vereiste gegevens op van uw Azure-tenant, met inbegrip van **Location**, **Domain name**, plus de **Application ID** en de waarde voor het clientgeheim (*client secret*) dat u hebt opgeslagen bij het maken van de app in Azure AD.  

4. Selecteer **Opslaan**. Jamf Pro test uw instellingen en bevestigt of ze juist zijn.

## <a name="set-up-compliance-policies-and-register-devices"></a>Nalevingsbeleid instellen en apparaten registreren

Nadat u de integratie tussen Intune en Jamf hebt geconfigureerd, moet u [nalevingsbeleid toepassen op door Jamf beheerde apparaten](conditional-access-assign-jamf.md).



## <a name="next-steps"></a>Volgende stappen

- [Nalevingsbeleid toepassen op door Jamf beheerde apparaten](conditional-access-assign-jamf.md)
- [Gegevens die Jamf verzendt naar Intune](data-jamf-sends-to-intune.md)
