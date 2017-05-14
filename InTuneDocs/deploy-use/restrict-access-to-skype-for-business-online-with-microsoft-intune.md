---
title: Skype voor Bedrijven Online beveiligen | Microsoft Docs
description: Toegang tot Skype voor Business Online beschermen en beheren door gebruik te maken van voorwaardelijke toegang.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1b2d7125-f63f-43cf-ac1e-94fbedf2a7e8
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 33febef8787887401960592d95356347f6917681
ms.openlocfilehash: 5888ffa6f16e9a9807ce1f9a9eb0594ed31b5b18
ms.contentlocale: nl-nl
ms.lasthandoff: 05/04/2017


---

# <a name="protect-access-to-skype-for-business-online-with-microsoft-intune"></a>Toegang tot Skype voor Bedrijven Online beveiligen met Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

U kunt beleid voor voorwaardelijke toegang voor **Skype voor Bedrijven Online** gebruiken om toegang tot Skype voor Bedrijven Online te beheren.
Voorwaardelijke toegang bestaat uit twee onderdelen:
- Een nalevingsbeleid voor apparaten waaraan het apparaat moet voldoen om te worden beschouwd als een apparaat dat het beleid naleeft.
- Een beleid voor voorwaardelijke toegang waarin u de voorwaarden opgeeft waaraan het apparaat moet voldoen om toegang tot de service te krijgen.
Zie het artikel [Toegang tot e-mail en O365-services beveiligen](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) voor meer informatie over hoe voorwaardelijke toegang werkt.

Wanneer een gebruiker in de doelgroep Skype voor Bedrijven Online op zijn apparaat probeert te gebruiken, wordt de volgende evaluatie uitgevoerd:

![Diagram met de beslissingspunten die worden gebruikt om te bepalen of een apparaat toegang tot Skype voor Bedrijven Online heeft of wordt geblokkeerd](../media/ConditionalAccess_SkypeforBusiness.png)

**Voordat** u beleid voor voorwaardelijke toegang voor Skype voor Bedrijven Online configureert, moet u:
- Een **Skype voor Bedrijven Online-abonnement** hebben en de Skype voor Bedrijven Online-licentie toewijzen aan gebruikers.
- Een **EMS-abonnement (Enterprise Mobility + Security)** of een **Azure AD Premium-abonnement (Azure Active Directory)** hebben, en moeten de gebruikers een licentie hebben voor EMS of Azure AD. Zie [Prijzen van Enterprise Mobility ](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) of [Prijzen van Azure Active Directory ](https://azure.microsoft.com/pricing/details/active-directory/) voor meer informatie.

-   [Moderne verificatie inschakelen](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune) voor Skype voor Bedrijven Online.
-  Zorg dat al uw gebruikers **Skype voor Bedrijven Online** gebruiken. Als u een implementatie van zowel Skype voor Bedrijven Online als een lokale Skype voor Bedrijven hebt, wordt het beleid voor voorwaardelijke toegang niet toegepast op gebruikers.

Het apparaat waarvoor toegang tot Skype voor Bedrijven Online nodig is, moet:

-   Een **Android**- of **iOS**-apparaat zijn.

-   **Geregistreerd** zijn bij Intune.

-   **Voldoen** aan geïmplementeerd Intune-nalevingsbeleid.


De apparaatstatus wordt opgeslagen in Azure Active Directory, waarmee toegang wordt verleend of geblokkeerd op basis van de voorwaarden die u opgeeft.

Als niet aan een voorwaarde wordt voldaan, krijgt de gebruiker een van de volgende berichten te zien tijdens het aanmelden:

-   Als het apparaat niet is geregistreerd bij Intune of Azure Active Directory, wordt een bericht weergegeven met instructies over het installeren van de bedrijfsportal-app en het registreren.

-   Als het apparaat niet aan het beleid voldoet, wordt er een bericht weergegeven waarin de gebruiker naar de website van de Intune-bedrijfsportal of de bedrijfsportal-app wordt verwezen. Hier staat informatie over het probleem en hoe het kan worden opgelost.

## <a name="configure-conditional-access-for-skype-for-business-online"></a>Beleid voor voorwaardelijke toegang configureren voor Skype voor Bedrijven Online

### <a name="step-1-configure-azure-active-directory-security-groups"></a>Stap 1: Azure Active Directory-beveiligingsgroepen configureren
Voordat u begint, moet u Azure Active Directory-beveiligingsgroepen configureren voor het beleid voor voorwaardelijke toegang. U kunt deze groepen configureren in het **Office 365-beheercentrum**. Deze groepen worden gebruikt om het beleid toe te passen op gebruikers of om gebruikers uit te sluiten van het beleid. Wanneer een gebruiker deel uitmaakt van de doelgroep voor het beleid, moet elk apparaat dat hij of zij gebruikt, aan het beleid voldoen om toegang te krijgen tot resources.

U kunt twee soorten groepen opgeven die u voor het beleid voor Skype voor Bedrijven kunt gebruiken:

-   **Doelgroepen**: bevat groepen gebruikers waarop het beleid van toepassing is.

-   **Uitgesloten groepen**: bevat groepen gebruikers waarop het beleid niet van toepassing is.

Als een gebruiker zich in beide groepen bevindt, wordt het beleid niet op de gebruiker toegepast.

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a>Stap 2: Nalevingsbeleid configureren en implementeren
[Maak](create-a-device-compliance-policy-in-microsoft-intune.md) en [implementeer](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) nalevingsbeleid op alle apparaten die door het beleid worden beïnvloed. Dit zijn alle apparaten die door de gebruikers in de **doelgroepen** worden gebruikt.

> [!NOTE]
> Terwijl nalevingsbeleid wordt geïmplementeerd voor Intune-groepen, is beleid voor voorwaardelijke toegang gericht op Azure Active Directory-beveiligingsgroepen.


> [!IMPORTANT]
> Als u geen nalevingsbeleid hebt geïmplementeerd, worden de apparaten beschouwd als apparaten die het beleid naleven.

Wanneer u klaar bent, gaat u door naar **Stap 3**.

### <a name="step-3-configure-the-skype-for-business-online-policy"></a>Stap 3: Het beleid voor Skype voor Bedrijven Online configureren
Configureer vervolgens het beleid om ervoor te zorgen dat alleen beheerde apparaten en apparaten die aan het beleid voldoen, toegang hebben tot Skype voor Bedrijven Online. Dit beleid wordt opgeslagen in Azure Active Directory.

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) achtereenvolgens **Beleid** > **Voorwaardelijke toegang** > **Skype voor Bedrijven Online**.

  ![Schermafbeelding van de pagina met voorwaardelijk beleid voor Skype voor Bedrijven Online](./media/conditional_access_SFBPolicy.png)

2.  Kies **Beleid voor voorwaardelijke toegang inschakelen**.

3.  Onder **Toegang voor toepassingen**kunt u beleid voor voorwaardelijke toegang toepassen:

    -   **iOS**

    -   **Android**

4.  Selecteer bij **Doelgroepen** de optie **Wijzigen** om de Active Directory-beveiligingsgroepen te selecteren waarop het beleid van toepassing moet zijn. U kunt ervoor kiezen dit op alle gebruikers of alleen op een bepaalde groep gebruikers toe te passen.

5.  Selecteer desgewenst onder **Uitgesloten groepen** de optie **Wijzigen** om de Active Directory-beveiligingsgroepen te selecteren waarop dit beleid niet van toepassing is.

6.  Als u klaar bent, kiest u **Opslaan**.

U hebt nu voorwaardelijke toegang voor Skype voor Bedrijven Online geconfigureerd. U hoeft het beleid voor voorwaardelijke toegang niet te implementeren. Het wordt direct van kracht.


## <a name="monitor-the-compliance-and-conditional-access-policies"></a>De compatibiliteit en het beleid voor voorwaardelijke toegang bewaken
In de werkruimte **Groepen** kunt u de status voor voorwaardelijke toegang van uw apparaten bekijken.

Selecteer een groep mobiele apparaten. Kies op het tabblad **Apparaten** vervolgens een van de volgende **Filters**:

* **Apparaten die niet zijn geregistreerd bij AAD**: voor deze apparaten is de toegang tot Skype voor Bedrijven Online geblokkeerd.

* **Apparaten die niet voldoen aan het beleid**: voor deze apparaten is de toegang tot Skype voor Bedrijven Online geblokkeerd.

* **Apparaten die zijn geregistreerd bij AAD en voldoen aan het beleid**: deze apparaten hebben toegang tot Skype voor Bedrijven Online.

