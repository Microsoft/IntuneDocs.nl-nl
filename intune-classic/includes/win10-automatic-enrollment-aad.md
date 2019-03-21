---
ms.openlocfilehash: fbfff91d2993becc99e2132285bef78d245ff50e
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "35289269"
---
## <a name="enable-windows-10-automatic-enrollment"></a>Automatische inschrijving voor Windows 10 inschakelen

Bij automatische registratie kunnen gebruikers hun Windows 10-apparaten registreren bij Intune wanneer ze hun werkaccount toevoegen aan hun apparaten die persoonlijk eigendom zijn of wanneer ze hun apparaten die bedrijfseigendom zijn toevoegen aan uw Azure Active Directory. Het apparaat van de gebruiker wordt op de achtergrond geregistreerd en aangesloten bij Azure Active Directory. Wanneer het apparaat is geregistreerd, wordt het met Intune beheerd.

**Vereisten**
- Azure Active Directory Premium-abonnement ([proefabonnement](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune-abonnement


### <a name="configure-automatic-mdm-enrollment"></a>Automatische MDM-registratie configureren

1. Meld u aan bij de [Azure-beheerportal](https://portal.azure.com) (https://manage.windowsazure.com)) en selecteer **Azure Active Directory**.

   ![Schermopname van de Azure-portal](../media/auto-enroll-azure-main.png)

2. Selecteer **Mobiliteit (MDM en MAM)**.

   ![Schermopname van de Azure-portal](../media/auto-enroll-mdm.png)

3. Selecteer **Microsoft Intune**.

   ![Schermopname van de Azure-portal](../media/auto-enroll-intune.png)

4. **Gebruikersbereik van MDM** configureren. Geef op van welke gebruikers apparaten moeten worden beheerd met Microsoft Intune. De Windows 10-apparaten van deze gebruikers worden automatisch geregistreerd voor beheer met Microsoft Intune.

   - **Geen**
   - **Sommige**
   - **Alle**

   ![Schermopname van de Azure-portal](../media/auto-enroll-scope.png)

5. Gebruik de standaardwaarden voor de volgende URL's:
   - **URL voor MDM-gebruiksvoorwaarden**
   - **Detectie-URL voor MDM**
   - **URL van MDM-naleving**

6. Selecteer **Opslaan**.

Tweeledige verificatie is standaard niet ingeschakeld voor de service. Tweeledige verificatie wordt echter aanbevolen bij het registreren van een apparaat. Voordat u tweeledige verificatie vereist voor deze service, moet u een provider voor tweeledige verificatie configureren in Azure Active Directory en uw gebruikersaccounts voor meervoudige verificatie configureren. Zie [Aan de slag met de Azure Multi-Factor Authentication Server](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).
