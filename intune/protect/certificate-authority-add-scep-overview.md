---
title: Externe certificeringsinstanties (CA) gebruiken met SCEP in Microsoft Intune - Azure | Microsoft Docs
description: In Microsoft Intune kunt u een leverancier of externe CA (certificeringsinstantie) toevoegen om certificaten uit te geven voor mobiele apparaten met het SCEP-protocol. In dit overzicht geeft een Azure Active Directory-toepassing (Azure AD) Microsoft Intune machtigingen om certificaten te valideren. Gebruik vervolgens de toepassings-id, verificatiesleutel en tenant-id van de AAD-toepassing in de installatie van uw SCEP-server om certificaten uit te geven.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 85aac54a81d81dc138dd12612db183aae839b72b
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/25/2020
ms.locfileid: "77575976"
---
# <a name="add-partner-certification-authority-in-intune-using-scep"></a>Partnercertificeringsinstanties toevoegen in Intune met behulp van SCEP

Gebruik externe certificeringsinstanties (CA) met Intune. Externe CA's kunnen mobiele apparaten inrichten met nieuwe of vernieuwde certificaten met het Simple Certificate Enrollment Protocol (SCEP) en kunnen ondersteuning bieden voor Windows-, iOS-/iPadOS-, Android- en macOS-apparaten.

Het gebruik van deze functie bestaat uit twee delen: open-source API en de Intune-beheerderstaken.

**Deel 1: een open-source API gebruiken**  
Microsoft heeft een API gemaakt voor integratie met Intune. Via de API kunt u certificaten valideren, succes- of foutberichten verzenden en SSL gebruiken, in het bijzonder SSL socket factory, om met Intune te communiceren.

De API is beschikbaar in de [Intune SCEP API openbare GitHub-opslagplaats](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation) en kan door u worden gedownload en gebruikt in uw oplossing. Gebruik deze API met externe SCEP-servers om aangepaste aangevraagde validatie tegen Intune uit te voeren voordat SCEP een certificaat inricht op een apparaat.

In [Integreren met Intune SCEP-beheeroplossing](scep-libraries-apis.md) vindt u meer informatie over het gebruik van de API, de bijbehorende methoden en het testen van oplossing die u bouwt.

**Deel 2: de toepassing en het profiel maken**  
Met behulp van een Azure Active Directory-toepassing (Azure AD) kunt u rechten delegeren naar Intune voor het verwerken van SCEP-aanvragen die afkomstig zijn van apparaten. De Azure AD-toepassing bevat waarden voor de toepassings-id en verificatiesleutel die worden gebruikt in de API-oplossing die de ontwikkelaar maakt. Beheerders kunnen vervolgens SCEP-certificaatprofielen maken en implementeren met Intune, en rapporten over de implementatiestatus op de apparaten bekijken.

Dit artikel bevat een overzicht van deze functie vanuit het oogpunt van een beheerder, inclusief het maken van de Azure AD-toepassing.

## <a name="overview"></a>Overzicht

In de volgende stappen vindt u een overzicht van het gebruik van SCEP voor certificaten in Intune:

1. In Intune maakt een beheerder een SCEP-certificaatprofiel en richt het profiel vervolgens op gebruikers of apparaten.
2. Het apparaat wordt aangemeld bij Intune.
3. Intune maakt een unieke SCEP-vraag. Ook wordt aanvullende informatie over integriteitscontroles toegevoegd, zoals wat het verwachte onderwerp en SAN moet zijn.
4. Intune versleutelt en ondertekent zowel de vraag als de informatie over de integriteitscontrole en stuurt deze informatie vervolgens met de SCEP-aanvraag naar het apparaat.
5. Het apparaat genereert een certificaatondertekeningsaanvraag (CSR) en een paar met een openbare en een persoonlijke sleutel op het apparaat op basis van het SCEP-certificaatprofiel dat vanuit Intune wordt gepusht.
6. De CSR en de versleutelde/ondertekende vraag worden verzonden naar het externe SCEP-servereindpunt.
7. De SCEP-server verzendt de CSR en de vraag naar Intune. Intune valideert vervolgens de handtekening, ontsleutelt de payload en vergelijkt de CSR met de informatie over de integriteitscontrole.
8. Intune stuurt een antwoord terug naar de SCEP-server en vermeldt of de validatie van de vraag al dan niet is geslaagd.  
9. Als de vraag is geverifieerd, geeft de SCEP-server het certificaat uit naar het apparaat.

In het volgende diagram ziet u een gedetailleerde stroom van externe SCEP-integratie met Intune:

> [!div class="mx-imgBorder"]
> ![Integratie van SCEP van externe certificeringsinstantie met Microsoft Intune](./media/certificate-authority-add-scep-overview/scep-certificate-vendor-integration.png)

## <a name="set-up-third-party-ca-integration"></a>Externe CA-integratie instellen

### <a name="validate-third-party-certification-authority"></a>Externe certificeringsinstantie valideren

Voordat u externe certificeringsinstanties gaat integreren met Intune, moet u bevestigen dat de CA die u gebruikt Intune ondersteunt. [Externe CA-partners](#third-party-certification-authority-partners) (in dit artikel) bevat een lijst. U kunt ook de instructies van uw certificeringsinstantie controleren voor meer informatie. De CA biedt mogelijk specifieke installatie-instructies voor hun implementatie.

### <a name="authorize-communication-between-ca-and-intune"></a>Communicatie tussen de CA en Intune autoriseren

Als u wilt toestaan dat een externe SCEP-server aangepaste vragen kan valideren met Intune, moet u een app maken in Azure AD. Deze app verleent gedelegeerde rechten aan Intune om SCEP-aanvragen te valideren.

Zorg ervoor dat u over de vereiste machtigingen beschikt om een Azure AD-app te registreren. Zie [Vereiste machtigingen](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions) in de documentatie van Azure AD.

#### <a name="create-an-application-in-azure-active-directory"></a>Een toepassing maken in Azure Active Directory  

1. Ga in de [Azure-portal](https://portal.azure.com) naar **Azure Active Directory** > **App-registraties** en selecteer **Nieuwe registratie**.  

2. Geef op de pagina **Een toepassing registreren** de volgende gegevens op:  
   - Voer bij **Naam** een betekenisvolle toepassingsnaam in.  
   - Selecteer **Accounts in een organisatieadreslijst** bij **Ondersteunde accounttypen**.  
   - Laat bij **Omleidings-URI** de standaardwaarde Web staan en geef vervolgens de aanmeldings-URL voor de externe SCEP-server op.  

3. Selecteer **Registreren** om de toepassing te maken en om de pagina Overzicht voor de nieuwe app te openen.  

4. Kopieer op de pagina **Overzicht** de waarde van **Toepassings-id (client-id)** en noteer de waarde voor later gebruik. U hebt deze waarde later nog nodig.  

5. Ga in het navigatievenster van de app naar **Certificaten en geheimen** onder **Beheren**. Selecteer de knop **Nieuw clientgeheim**. Typ tekst in het vak Beschrijving, selecteer een optie voor **Verloopt op** en kies vervolgens **Toevoegen** om een *waarde* te genereren voor het clientgeheim. 
   > [!IMPORTANT]  
   > Voordat u deze pagina verlaat, moet u de waarde voor het clientgeheim kopiëren en bewaren voor later gebruik met de implementatie van uw externe certificeringsinstantie. Deze waarde wordt namelijk niet meer weergegeven. Lees de richtlijnen van de externe certificeringsinstantie, zodat u weet hoe de toepassings-id, verificatiesleutel en tenant-id moeten worden geconfigureerd.  

6. Noteer uw **tenant-id**. De tenant-id is de domeintekst na het teken @ in uw account. Als uw account bijvoorbeeld *admin@name.onmicrosoft.com* is, dan is uw tenant-id **naam.onmicrosoft.com**.  

7. Ga in het navigatievenster van de app naar **API-machtigingen** onder **Beheren** en selecteer vervolgens **Een machtiging toevoegen**.  

8. Selecteer op de pagina **API-machtigingen aanvragen** de optie **Intune** en selecteer vervolgens **Toepassingsmachtigingen**. Schakel het selectievakje voor **scep_challenge_provider** in (validatie van SCEP-challenge).  

   Selecteer **Machtigingen toevoegen** om deze configuratie op te slaan.  

9. Blijf op de pagina **API-machtigingen**, selecteer **Beheerder toestemming geven voor Microsoft** en selecteer vervolgens **Ja**.  
   
   Het registratieproces voor de app in Azure AD is voltooid.





### <a name="configure-and-deploy-a-scep-certificate-profile"></a>Een SCEP-certificaatprofiel configureren en implementeren
Als beheerder maakt u een SCEP-certificaatprofiel voor gebruikers of apparaten. Wijs vervolgens het profiel toe.

- [Een SCEP-certificaatprofiel maken](certificates-profile-scep.md#create-a-scep-certificate-profile)

- [Het certificaatprofiel toewijzen](certificates-profile-scep.md#assign-the-certificate-profile)

## <a name="removing-certificates"></a>Certificaten verwijderen

Wanneer u de registratie ongedaan maakt of het apparaat wist, worden de certificaten verwijderd. De certificaten worden niet ingetrokken.

## <a name="third-party-certification-authority-partners"></a>Partners van externe certificeringsinstanties
De volgende externe certificeringsinstanties bieden ondersteuning voor Intune:

- [Entrust Datacard](https://go.entrustdatacard.com/pki/intune/)
- [EJBCA GitHub open-sourceversie](https://github.com/agerbergt/intune-ejbca-connector)
- [EverTrust](https://evertrust.fr/en/products/)
- [GlobalSign](https://downloads.globalsign.com/acton/attachment/2674/f-6903f60b-9111-432d-b283-77823cc65500/1/-/-/-/-/globalsign-aeg-microsoft-intune-integration-guide.pdf)
- [IDnomic](https://www.idnomic.com/)
- [Sectigo](https://sectigo.com/products)
- [DigiCert](https://knowledge.digicert.com/tutorials/microsoft-intune.html)
- [Venafi](https://www.venafi.com/platform/enterprise-mobility)
- [SCEPman](https://azuremarketplace.microsoft.com/marketplace/apps/gluckkanja.scepman)

Als u een externe certificeringsinstantie bent en interesse hebt om uw product te integreren met Intune, controleert u de API-richtlijnen:

- [Intune SCEP API GitHub-opslagplaats](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Richtlijnen voor Intune SCEP-API voor externe CA's ](scep-libraries-apis.md)

## <a name="see-also"></a>Zie tevens

- [Certificaatprofielen configureren](certificates-scep-configure.md)
- [Intune SCEP API GitHub-opslagplaats](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Richtlijnen voor Intune SCEP-API voor externe CA's ](scep-libraries-apis.md)
