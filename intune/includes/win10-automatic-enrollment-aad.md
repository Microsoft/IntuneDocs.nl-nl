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

  - **Geen**
  - **Sommige**
  - **Alle**

   ![Schermopname van de Azure-portal](../media/auto-enroll-scope.png)

5. Gebruik de standaardwaarden voor de volgende URL's:
    - **URL voor MDM-gebruiksvoorwaarden**
    - **Detectie-URL voor MDM**
    - **URL van MDM-naleving**

    > [!IMPORTANT]
    > Als zowel **Gebruikersbereik van MAM** als automatische MDM-inschrijving (**Gebruikersbereik van MDM**) wordt ingeschakeld voor een groep, wordt alleen MAM ingeschakeld. Alleen MAM wordt toegevoegd voor gebruikers in die groep wanneer ze hun persoonlijke apparaat aan hun werkplek toevoegen. Apparaten worden niet automatisch ingeschreven voor MDM.

6. Selecteer **Opslaan**.

Tweeledige verificatie is standaard niet ingeschakeld voor de service. Tweeledige verificatie wordt echter aanbevolen bij het registreren van een apparaat. Om tweeledige verificatie in te schakelen, configureert u een provider voor tweeledige verificatie in Azure AD en configureert u uw gebruikersaccounts voor meervoudige verificatie. Zie [Aan de slag met de Azure Multi-Factor Authentication Server](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).
