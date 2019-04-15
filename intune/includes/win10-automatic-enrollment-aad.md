---
ms.openlocfilehash: 04afc9c44bc1c4898950e6f3aff5dac7cb93370f
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "56323381"
---
## <a name="enable-windows-10-automatic-enrollment"></a>Automatische inschrijving voor Windows 10 inschakelen

Met automatische inschrijving kunnen gebruikers hun Windows 10-apparaten inschrijven in Intune. Voor inschrijving voegen gebruikers hun werkaccount toe aan hun apparaten die persoonlijk eigendom zijn, of koppelen ze apparaten die bedrijfseigendom zijn aan Azure Active Directory. Het apparaat wordt op de achtergrond geregistreerd en aangesloten bij Azure Active Directory. Wanneer het apparaat is geregistreerd, wordt het met Intune beheerd.

**Vereisten**
- Azure Active Directory Premium-abonnement ([proefabonnement](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune-abonnement


### <a name="configure-automatic-mdm-enrollment"></a>Automatische MDM-registratie configureren

1. Meld u aan bij de [Azure-portal](https://portal.azure.com) en selecteer **Azure Active Directory**.

   ![Schermopname van de Azure-portal](../media/auto-enroll-azure-main.png)

2. Selecteer **Mobiliteit (MDM en MAM)**.

   ![Schermopname van de Azure-portal](../media/auto-enroll-mdm.png)

3. Selecteer **Microsoft Intune**.

   ![Schermopname van de Azure-portal](../media/auto-enroll-intune.png)

4. **Gebruikersbereik van MDM** configureren. Geef op van welke gebruikers apparaten moeten worden beheerd met Microsoft Intune. Deze Windows 10-apparaten kunnen automatisch worden ingeschreven voor beheer met Microsoft Intune.

   - **Geen** - Automatische inschrijving voor MDM uitgeschakeld
   - **Sommige** - Selecteer **Groepen** die automatisch hun Windows 10-apparaten kunnen inschrijven
   - **Alle** - Alle gebruikers kunnen automatisch hun Windows 10-apparaten inschrijven

      > [!IMPORTANT]
      > Voor BYOD-apparaten krijgt het MAM-gebruikersbereik voorrang als zowel het MAM-gebruikersbereik als het MDM-gebruikersbereik (automatische MDM-registratie) zijn ingeschakeld voor alle gebruikers (of dezelfde groepen of gebruikers). Het apparaat wordt niet via MDM geregistreerd, maar gebruikt WIP-beleid (Windows Information Protection) (als u dit hebt geconfigureerd).
      >
      > Voor zakelijke apparaten krijgt het MDM-gebruikersbereik voorrang als beide bereiken zijn ingeschakeld. De apparaten worden via MDM geregistreerd.

   > [!NOTE]
   > Het gebruikersbereik van MAM moet worden ingesteld op een gebruikersgroep of -verzameling.

   ![Schermopname van de Azure-portal](../media/auto-enroll-scope.png)

5. Gebruik de standaardwaarden voor de volgende URL's:
    - **URL voor MDM-gebruiksvoorwaarden**
    - **Detectie-URL voor MDM**
    - **URL van MDM-naleving**

6. Selecteer **Opslaan**.

Tweeledige verificatie is standaard niet ingeschakeld voor de service. Tweeledige verificatie wordt echter aanbevolen bij het registreren van een apparaat. Om tweeledige verificatie in te schakelen, configureert u een provider voor tweeledige verificatie in Azure AD en configureert u uw gebruikersaccounts voor meervoudige verificatie. Zie [Aan de slag met de Azure Multi-Factor Authentication Server](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).
