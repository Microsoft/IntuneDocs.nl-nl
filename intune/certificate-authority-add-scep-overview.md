---
title: Externe CA gebruiken met SCEP in Microsoft Intune - Azure | Microsoft Docs
description: In Microsoft Intune kunt u een leverancier of externe CA (certificeringsinstantie) toevoegen om certificaten uit te geven voor mobiele apparaten met het SCEP-protocol. In dit overzicht geeft een Azure Active Directory-toepassing (Azure AD) Microsoft Intune machtigingen om certificaten te valideren. Gebruik vervolgens de toepassings-id, verificatiesleutel en tenant-id van de AAD-toepassing in de installatie van uw SCEP-server om certificaten uit te geven.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 772c800e75f52d9826992bf0adfbfdcf3faba107
ms.sourcegitcommit: a13d1eafc979a9cfeb4adbdea861e2784c2b1068
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/19/2018
ms.locfileid: "46329977"
---
# <a name="add-partner-certification-authority-in-intune-using-scep"></a>Partnercertificeringsinstanties toevoegen in Intune met behulp van SCEP

In Microsoft Intune kunnen externe certificeringsinstanties (CA) worden toegevoegd. Deze CA’s kunnen certificaten leveren aan mobiele apparaten met behulp van het Simple Certificate Enrollment Protocol (SCEP). Met deze functie kunnen nieuwe certificaten worden uitgegeven en certificaten worden vernieuwd op Windows-, iOS-, Android- en macOS-apparaten.

Het gebruik van deze functie bestaat uit twee delen: open-source API en de Intune-beheerderstaken.

**Deel 1: een open-source API gebruiken**  
Microsoft heeft een API gemaakt die kan worden geïntegreerd met Intune om certificaten te valideren, meldingen over geslaagde of mislukte acties te verzenden en SSL te gebruiken, met name SSL socket factory, om met Intune te communiceren.

De API is beschikbaar in de [Intune SCEP API openbare GitHub-opslagplaats](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation) en kan door u worden gedownload en gebruikt in uw oplossing. Gebruik deze API met externe SCEP-servers om aangepaste aangevraagde validatie tegen Intune uit te voeren voordat u een certificaat naar een apparaat levert.

In [Integreren met Intune SCEP-beheeroplossing](scep-libraries-apis.md) vindt u meer informatie over het gebruik van de API, de bijbehorende methoden en het testen van oplossing die u bouwt.

**Deel 2: de toepassing en het profiel maken**  
Met behulp van een Azure Active Directory-toepassing (Azure AD) kunt u rechten delegeren naar Intune voor het verwerken van SCEP-aanvragen die afkomstig zijn van apparaten. De Azure AD-toepassing bevat waarden voor de toepassings-id en verificatiesleutel die worden gebruikt in de API-oplossing die de ontwikkelaar maakt. Beheerders kunnen vervolgens profielen voor SCEP-certificaten maken en implementeren met behulp van Intune. Ook kunt u rapporten over de implementatiestatus bekijken op de apparaten.

Dit artikel bevat een overzicht van deze functie vanuit het oogpunt van een beheerder, inclusief het maken van de Azure AD-toepassing.

## <a name="overview"></a>Overzicht

In de volgende stappen vindt u een overzicht van het uitgeven van SCEP-certificaten in Intune:

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

![Integratie van SCEP van externe certificeringsinstantie met Microsoft Intune](./media/scep-certificate-vendor-integration.png)

## <a name="set-up-third-party-ca-integration"></a>Externe CA-integratie instellen

### <a name="validate-third-party-certification-authority"></a>Externe certificeringsinstantie valideren

Voordat u externe certificeringsinstanties gaat integreren met Intune, moet u bevestigen dat de CA die u gebruikt Intune ondersteunt. [Externe CA-partners](#third-party-certification-authority-partners) (in dit artikel) bevat een lijst. U kunt ook de instructies van uw certificeringsinstantie controleren voor meer informatie. De CA biedt mogelijk specifieke installatie-instructies voor hun implementatie.

### <a name="authorize-communication-between-ca-and-intune"></a>Communicatie tussen de CA en Intune autoriseren

Als u wilt toestaan dat een externe SCEP-server aangepaste vragen kan valideren met Intune, moet u een app maken in Azure AD. Deze app verleent gedelegeerde rechten aan Intune om SCEP-aanvragen te valideren.

Zorg ervoor dat u over de vereiste machtigingen beschikt om een Azure AD-app te registreren. Bij [Vereiste machtigingen](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions) worden de stappen vermeld.

**Stap 1: een Azure AD-toepassing maken**

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Azure Active Directory** > **App-registraties** > **Nieuwe toepassing registreren**.
3. Voer een naam en aanmeldings-URL in. Selecteer **Web-app/API** als het toepassingstype.
4. Selecteer **Maken**.

[Toepassingen integreren met Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications) bevat een aantal richtlijnen voor het maken van een app, waaronder tips voor de URL en de naam.

**Stap 2: machtigingen afgeven**

Na het maken van uw toepassing geeft u de Microsoft Intune-API de vereiste machtigingen:

1. Open **Instellingen** > **Vereiste machtigingen** in uw Azure AD-app.  
2. Selecteer **Toevoegen** > **Een API selecteren** > selecteer **Microsoft Intune-API** > **Selecteren**.
3. Bij **Machtigingen selecteren** kiest u **SCEP-vraagvalidatie** > **Selecteren**.
4. Selecteer **OK** om uw wijzigingen op te slaan.

**Stap 3: de toepassings-id en verificatiesleutel ophalen**

Vervolgens moet u de id- en sleutelwaarden van uw Azure AD-toepassing ophalen. De volgende waarden zijn vereist:

- Toepassings-id
- Verificatiesleutel
- Tenant-id

**U kunt als volgt de toepassings-id en verificatiesleutel ophalen**:

1. Selecteer uw nieuwe toepassing in Azure AD (**App-registraties**).
2. Kopieer de **toepassings-id** en sla deze id op in de code van uw toepassing.
3. Genereer nu een verificatiesleutel. Open **Instellingen** > **Sleutels** in uw Azure AD-app.
4. Voer bij **Wachtwoorden** een beschrijving in en kies de duur van de sleutel. U moet vervolgens de wijzigingen **Opslaan**. Kopieer de getoonde waarde en sla deze op.

    > [!IMPORTANT]
    > Kopieer en bewaar deze sleutel onmiddellijk, aangezien deze niet opnieuw wordt weergegeven. De waarde van deze sleutel is nodig voor de implementatie van de externe CA. Lees hun richtlijnen door over de manier waarop zij de toepassings-id, verificatiesleutel en tenant-id geconfigureerd willen hebben.

De **Tenant-id** is de domeintekst na het @-teken in uw account. Als uw account bijvoorbeeld `admin@name.onmicrosoft.com` is, dan is uw tenant-id **naam.onmicrosoft.com**.

Bij [Toepassings-id en verificatiesleutel ophalen](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal#get-application-id-and-authentication-key) wordt een lijst weergegeven met de stappen om deze waarden op te halen, en wordt meer informatie gegeven over Azure AD-apps.

### <a name="configure-and-deploy-a-scep-certificate-profile"></a>Een SCEP-certificaatprofiel configureren en implementeren
Als beheerder maakt u een SCEP-certificaatprofiel voor gebruikers of apparaten. Wijs vervolgens het profiel toe.

- [Een SCEP-certificaatprofiel maken](certificates-scep-configure.md#create-a-scep-certificate-profile)

- [Het certificaatprofiel toewijzen](certificates-scep-configure.md#assign-the-certificate-profile)

## <a name="removing-certificates"></a>Certificaten verwijderen

Wanneer u de registratie ongedaan maakt of het apparaat wist, worden de certificaten verwijderd. De certificaten worden niet ingetrokken.

## <a name="third-party-certification-authority-partners"></a>Partners van externe certificeringsinstanties
De volgende externe certificeringsinstanties bieden ondersteuning voor Intune:

- [Entrust Datacard](http://www.entrustdatacard.com/resource-center/documents/documentation)
- [EJBCA GitHub open-sourceversie](https://github.com/agerbergt/intune-ejbca-connector)

Als u een externe certificeringsinstantie bent en interesse hebt om uw product te integreren met Intune, controleert u de API-richtlijnen:

- [Intune SCEP API GitHub-opslagplaats](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Richtlijnen voor Intune SCEP-API voor externe CA's ](scep-libraries-apis.md)

## <a name="see-also"></a>Zie ook

- [Certificaatprofielen configureren](certificates-scep-configure.md)
- [Intune SCEP API GitHub-opslagplaats](http://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
- [Richtlijnen voor Intune SCEP-API voor externe CA's ](scep-libraries-apis.md)
