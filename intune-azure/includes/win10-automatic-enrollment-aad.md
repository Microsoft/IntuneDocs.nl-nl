## <a name="enable-windows-10-automatic-enrollment"></a>Automatische inschrijving voor Windows 10 inschakelen

Met automatische registratie kunnen gebruikers Windows 10-pc’s en Windows 10 Mobile-apparaten van het bedrijf of van henzelf in Intune registreren door werk- of schoolaccount toe te voegen en akkoord te gaan met het beheer. Zo simpel is het. Het apparaat van de gebruiker wordt op de achtergrond geregistreerd en aangesloten bij Azure Active Directory. Wanneer het apparaat is geregistreerd, wordt het met Intune beheerd.

**Vereisten**
- Azure Active Directory Premium-abonnement ([proefabonnement](http://go.microsoft.com/fwlink/?LinkID=816845))
- Microsoft Intune-abonnement


### <a name="configure-automatic-mdm-enrollment"></a>Automatische MDM-registratie configureren

1. Meld u aan bij de [Azure AD-beheerportal](https://portal.azure.com) (https://manage.windowsazure.com) en selecteer **Azure Active Directory**.

  ![Schermopname van de Azure-portal](../media/auto-enroll-azure-main.png)

2. Selecteer **Mobiliteit (MDM en MAM)**.

  ![Schermopname van de Azure-portal](../media/auto-enroll-mdm.png)

3. Selecteer **Microsoft Intune**.

  ![Schermopname van de Azure-portal](../media/auto-enroll-intune.png)

4. Configureer welke gebruikers automatisch moeten worden ingeschreven.

  ![Schermopname van de Azure-portal](../media/auto-enroll-scope.png)

  Gebruik de standaardwaarden voor de volgende URL’s:
  - **MDM-inschrijving**
  - **MDM-gebruiksvoorwaarden**
  - **MDM-naleving**

5. Geef op van welke gebruikers apparaten moeten worden beheerd met Microsoft Intune. De Windows 10-apparaten van deze gebruikers worden automatisch geregistreerd voor beheer met Microsoft Intune.

  - **Alle**
  - **GROEPEN**
  - **Geen**

6. Selecteer **Opslaan**.
