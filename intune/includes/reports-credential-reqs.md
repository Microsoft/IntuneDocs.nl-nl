<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Azure AD en Intune-referentievereisten

Verificatie en autorisatie zijn gebaseerd op Azure AD-referenties en Intune RBAC (Role-Based Access Control, op rollen gebaseerd toegangsbeheer). Alle globale beheerders en Intune-servicebeheerders voor uw tenant hebben standaard toegang tot het datawarehouse. Gebruik Intune-rollen om toegang te bieden voor meer gebruikers door hen toegang tot de **rapportageresource** te verlenen.

De vereisten voor toegang tot het Intune-datawarehouse (inclusief de API) zijn:

  -  Er moet een Intune-licentie zijn toegewezen aan de gebruiker
  -  Gebruiker moet een van de volgende zijn:
      -  Globale Azure AD-beheerder
      -  Een Intune-servicebeheerder
      -  Gebruiker met op rollen gebaseerde toegang tot de **rapporten**resource