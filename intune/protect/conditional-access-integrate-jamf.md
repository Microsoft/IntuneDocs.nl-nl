---
title: Jamf Pro integreren met Microsoft Intune voor naleving
titleSuffix: Microsoft Intune
description: Gebruik Microsoft Intune-nalevingsbeleid met voorwaardelijke toegang voor Azure Active Directory om apparaten te integreren en te beveiligen die met Jamf worden beheerd.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 01dae8f6c90155e649211ab226cf24eeade29b42
ms.sourcegitcommit: f5108039f0ade52e95ea3ac1da1aa16d02224af3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/09/2019
ms.locfileid: "74946679"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Jamf Pro integreren met Intune in verband met nalevingsbeleid

Als uw organisatie [Jamf Pro](https://www.jamf.com) gebruikt voor het beheren van de macOS-apparaten, kunt u Microsoft Intune-nalevingsbeleid met voorwaardelijke toegang tot Azure Active Directory (Azure AD) gebruiken om ervoor te zorgen dat apparaten in uw organisatie compatibel zijn voordat ze toegang tot bedrijfsbronnen krijgen. Dit artikel is bedoeld om te helpen bij het configureren van de Jamf-integratie met Intune.

Wanneer u Jamf Pro integreert met Intune, kunt u de inventarisgegevens van macOS-apparaten synchroniseren met Intune via Azure AD. De inventarisgegevens worden vervolgens door de nalevingsengine van Intune geanalyseerd en verwerkt tot een rapport. De analyse van Intune wordt gecombineerd met informatie over de Azure AD-identiteit van de gebruiker van het apparaat om beleid voor voorwaardelijke toegang af te dwingen. Apparaten die compatibel zijn met het beleid voor voorwaardelijke toegang, kunnen toegang krijgen tot beveiligde bedrijfsbronnen.

Nadat u de integratie hebt geconfigureerd, kunt u vervolgens [Jamf en Intune configureren om naleving van voorwaardelijke toegang af te dwingen](conditional-access-assign-jamf.md) op apparaten die worden beheerd door Jamf.

## <a name="prerequisites"></a>Vereisten

### <a name="products-and-services"></a>Producten en services

U hebt het volgende nodig om voorwaardelijke toegang met Jamf Pro te configureren:

- Jamf Pro 10.1.0 of hoger
- [Bedrijfsportal-app voor macOS ](https://aka.ms/macoscompanyportal)
- macOS-apparaten met OS X 10.12 Yosemite of hoger

### <a name="network-ports"></a>Netwerkpoorten

<!-- source: https://support.microsoft.com/en-us/help/4519171/troubleshoot-problems-when-integrating-jamf-with-microsoft-intune -->
De volgende poorten moeten toegankelijk zijn voor Jamf en Intune voor een juiste integratie:

- **Intune**: Poort 443
- **Apple**: Poort 2195, 2196 en 5223 (pushmeldingen naar Intune)
- **Jamf**: Poort 80 en 5223

Als u wilt dat APNS correct functioneert in het netwerk, moet u ook uitgaande verbindingen en omleidingen inschakelen voor:

- de blokkering van Apple 17.0.0.0/8 via TCP-poort 5223 en 443 van alle clientnetwerken.
- poort 2195 en 2196 van Jamf Pro-servers.  

Zie de volgende artikelen voor meer informatie over deze poorten:

- [Netwerkconfiguratievereisten en bandbreedte voor Intune](../fundamentals/network-bandwidth-use.md).
- [Network Ports Used by Jamf Pro](https://www.jamf.com/jamf-nation/articles/34/network-ports-used-by-jamf-pro) (Netwerkpoorten die worden gebruikt door Jamf Pro) op jamf.com.
- [TCP and UDP ports used by Apple software products](https://support.apple.com/HT202944) (TCP-en UDP-poorten die worden gebruikt door softwareproducten van Apple) op support.apple.com

## <a name="connect-intune-to-jamf-pro"></a>Intune koppelen met Jamf Pro

Om Intune te verbinden met Jamf Pro:

1. Maak een nieuwe toepassing in Azure.
2. Schakel Intune-integratie met Jamf Pro in.
3. Configureer voorwaardelijke toegang in Jamf Pro.

### <a name="create-an-application-in-azure-active-directory"></a>Een toepassing maken in Azure Active Directory

1. Ga in de [Azure-portal](https://portal.azure.com) naar **Azure Active Directory** > **App-registraties** en selecteer **Nieuwe registratie**.

2. Geef op de pagina **Een toepassing registreren** de volgende gegevens op:

   - Geef bij **Naam** een betekenisvolle naam op voor de toepassing, bijvoorbeeld **Jamf Conditional Access**.
   - Selecteer **Accounts in een organisatieadreslijst** bij **Ondersteunde accounttypen**.
   - Laat bij **Omleidings-URI** de standaardwaarde Web staan en geef vervolgens de URL voor uw exemplaar van Jamf Pro op.

3. Selecteer **Registreren** om de toepassing te maken en om de pagina **Overzicht** voor de nieuwe app te openen.

4. Kopieer op de pagina **Overzicht** de waarde van **Toepassings-id (client-id)** en noteer de waarde voor later gebruik. U hebt deze waarde in latere procedures nodig.

5. Selecteer **Certificaten en geheimen** onder **Beheren**. Selecteer de knop **Nieuw clientgeheim**. Voer een waarde in voor **Beschrijving**, selecteer een optie voor **Verloopt** en kies **Toevoegen**.

   > [!IMPORTANT]
   > Voordat u deze pagina verlaat, moet u de waarde voor het clientgeheim kopiëren en bewaren voor later gebruik. U hebt deze waarde in latere procedures nodig. Deze waarde kunt u niet meer weergeven, alleen door de app opnieuw te registreren.

6. Selecteer **API-machtigingen** onder **Beheren**. 

7. Selecteer op de pagina API-machtigingen **Een machtiging toevoegen** om een nieuwe machtiging toe te voegen. Selecteer op de pagina **API-machtigingen aanvragen** de optie **Intune** en selecteer vervolgens **Toepassingsmachtigingen**. Schakel alleen het selectievakje voor **update_device_attributes** in.

8. Wacht enkele minuten zodat de nieuwe machtiging kan worden toegepast. Selecteer vervolgens **Beheertoestemming verlenen voor _\<de Tenant>_** . Verifieer uw account in het nieuwe venster en volg de aanwijzingen om toegang tot de toepassing te verlenen.  

9. Mogelijk moet u nog een paar minuten wachten zodat de beheerderstoestemming kan worden toegepast.

10. Klik op de knop **Vernieuwen** bovenaan de pagina om de pagina te vernieuwen. Bevestig dat beheerderstoestemming is verleend voor de machtiging **update_device_attributes**. 

11. Verwijder de beheerderstoestemming uit de machtiging **User.Read** door het menu **...** te selecteren en **Beheerderstoestemming intrekken** in te schakelen.

12. U moet ook de machtiging **User.Read** verwijderen. Selecteer het menu **...** voor **User.Read** en selecteer **Machtiging verwijderen**. 

8. Nadat de app is geregistreerd, mogen de API-machtigingen slechts één machtiging met de naam **update_device_attributes** bevatten. Dit moet er als volgt uitzien:

   ![Verlenen van machtigingen geslaagd](./media/conditional-access-integrate-jamf/sucessfull-app-registration.png)

   Het registratieproces voor de app in Azure AD is voltooid.

    > [!NOTE]
    > Als het clientgeheim is verlopen, moet u een nieuw clientgeheim maken in Azure en vervolgens de gegevens voor voorwaardelijke toegang in Jamf Pro bijwerken. In Azure kan zowel het oude geheim als de nieuwe sleutel actief zijn om serviceonderbrekingen te voorkomen.

### <a name="enable-intune-to-integrate-with-jamf-pro"></a>Intune instellen op integratie met Jamf Pro

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Tenantbeheer** > **Connectors en tokens** > **Apparaatbeheer partner**.

3. Schakel de *nalevingsconnector voor Jamf* in door de toepassings-id die u tijdens de vorige procedure hebt opgeslagen in het veld **Geef de Azure Active Directory-app-id voor Jamf op** te plakken.

4. Selecteer **Opslaan**.

### <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Microsoft Intune-integratie in Jamf Pro configureren

1. De verbinding in de Jamf Pro-console activeren:

   1. Open de Jamf Pro-console en navigeer naar **Global Management** > **Conditional Access**. Klik op de knop **Edit** op het tabblad **macOS Intune Integration**.
   2. Schakel het selectievakje voor **Enable Intune Integration for macOS** in.
   3. Geef de vereiste gegevens op van uw Azure-tenant, met inbegrip van **Location**, **Domain name**, plus de **Application ID** en de waarde voor het clientgeheim (*client secret*) dat u hebt opgeslagen bij het maken van de app in Azure AD.
   4. Selecteer **Opslaan**. Jamf Pro test uw instellingen en bevestigt of ze juist zijn.

   Ga terug naar de pagina **Apparaatbeheer partner** in Intune om de configuratie te voltooien.

2. Ga in Intune naar de pagina **Apparaatbeheer partner**. Onder **Connectorinstellingen** configureert u groepen om toe te wijzen:

   - Selecteer **Opnemen** en geef op welke gebruikersgroepen u wilt benaderen voor een macOS-inschrijving bij Jamf.
   - Gebruik **Uitsluiten** om gebruikersgroepen te selecteren die niet bij Jamf worden ingeschreven en die in plaats daarvan hun Macs rechtstreeks bij Intune inschrijven.

   *Uitsluiten* overschrijft *Opnemen*, wat betekent dat elk apparaat dat in beide groepen voorkomt van Jamf wordt uitgesloten en wordt omgeleid om zich bij Intune in te schrijven.

   >[!NOTE]
   > Deze methode om gebruikersgroepen op te nemen en uit te sluiten, is van invloed op de inschrijvingservaring van de gebruiker. Elke gebruiker met een Mac die al is ingeschreven in Jamf of Intune en die vervolgens wordt benaderd om zich in te schrijven bij het andere MDM, moet het apparaat uitschrijven en vervolgens opnieuw inschrijven bij het nieuwe MDM voordat het beheer van het apparaat goed werkt.

3. Selecteer **Evalueren** om te bepalen hoeveel apparaten worden ingeschreven bij Jamf op basis van uw groepsconfiguraties.

4. Selecteer **Opslaan** wanneer u klaar bent om de configuratie toe te passen.

5. Als u wilt doorgaan, moet u [Jamf gebruiken om de bedrijfsportal voor Mac te implementeren](conditional-access-assign-jamf.md#deploy-the-company-portal-app-for-macos-in-jamf-pro) zodat gebruikers hun apparaten bij Intune kunnen registreren.

## <a name="set-up-compliance-policies-and-register-devices"></a>Nalevingsbeleid instellen en apparaten registreren

Nadat u de integratie tussen Intune en Jamf hebt geconfigureerd, moet u [nalevingsbeleid toepassen op door Jamf beheerde apparaten](conditional-access-assign-jamf.md).

## <a name="disconnect-jamf-pro-and-intune"></a>Verbinding tussen Jamf Pro en Intune verbreken

Als u Jamf Pro niet meer gebruikt om Macs in uw organisatie te beheren en wilt dat gebruikers worden beheerd door Intune, moet u de verbinding tussen Jamf Pro en Intune verwijderen. Verwijder de verbinding met behulp van de Jamf Pro-console.

1. Ga in Jamf Pro naar **Global Management** > **Conditional Access**. Selecteer op het tabblad **macOS Intune Integration** de optie **Edit**.

2. Schakel het selectievakje **Enable Intune Integration for macOS** uit.

3. Selecteer **Opslaan**. Jamf Pro stuurt uw configuratie naar Intune en de integratie wordt beëindigd.

4. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

5. Selecteer **Tenantbeheer** > **Connectors en tokens** > **Apparaatbeheer partner** om te controleren of de status nu **Beëindigd** is.

   > [!NOTE]
   > De Mac-apparaten in uw organisatie worden verwijderd op de datum (3 maanden) die wordt weergegeven in uw console.

## <a name="next-steps"></a>Volgende stappen

- [Nalevingsbeleid toepassen op door Jamf beheerde apparaten](conditional-access-assign-jamf.md)
- [Gegevens die Jamf verzendt naar Intune](data-jamf-sends-to-intune.md)
