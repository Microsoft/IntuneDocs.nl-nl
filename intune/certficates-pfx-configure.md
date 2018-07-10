---
title: PKCS-certificaten gebruiken met Microsoft Intune - Azure | Microsoft Docs
description: PKCS-certificaten (Public Key Cryptography Standards) toevoegen of maken met Microsoft Intune, inclusief de stappen om een basiscertificaat te exporteren, de certificaatsjabloon te configureren, de Microsoft Intune Certificate Connector (NDES) te downloaden en installeren, een apparaatconfiguratieprofiel te maken, een PKCS-certificaatprofiel te maken in Azure en uw certificeringsinstantie (CA).
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b3bfe76173eff76a3175952bef5c6e23ad5e429
ms.sourcegitcommit: afda8a0fc0f615e976b18ddddf81d56d7ae3566e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/20/2018
ms.locfileid: "36271538"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>PKCS-certificaten configureren en gebruiken met Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Certificaten worden gebruikt om toegang tot uw bedrijfsbronnen, zoals een VPN of uw Wi-Fi-netwerk, te verifiëren en beveiligen. In dit artikel leest u hoe u een PKCS-certificaat exporteert en hoe u vervolgens het certificaat toevoegt aan een Intune-profiel. 

## <a name="requirements"></a>Vereisten

Als u PKCS-certificaten wilt gebruiken met Intune, moet u de volgende infrastructuur hebben:

- **Active Directory-domein**: alle servers die in dit gedeelte worden genoemd, moeten lid zijn van uw Active Directory-domein.

  Zie [AD DS-ontwerp- en -planning](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning) voor meer informatie over het installeren en configureren van AD DS.

- **Certificeringsinstantie** (CA): een geconfigureerde certificeringsinstantie (CA) voor ondernemingen

  Raadpleeg [Stapsgewijze handleiding bij Active Directory Certificate Services](https://technet.microsoft.com/library/cc772393) als u meer informatie wilt over het installeren en configureren van Active Directory Certificate Services (AD CS).

  > [!WARNING]
  > Voor Intune moet u AD CS uitvoeren met een certificeringsinstantie (CA) voor ondernemingen, niet met een zelfstandige certificeringsinstantie.

- **Een client**: deze wordt gekoppeld aan de CA voor ondernemingen

- **Basiscertificaat**: een geëxporteerde kopie van uw basiscertificaat van uw CA voor ondernemingen

- **Microsoft Intune-certificaatconnector**: u kunt Azure Portal gebruiken om het installatieprogramma voor de **Certificaatconnector** (**NDESConnectorSetup.exe**) te downloaden. 

  De NDES-certificaatconnector ondersteunt ook de Federal Information Processing Standard-modus (FIPS). FIPS is niet vereist, maar u kunt certificaten uitgeven en intrekken wanneer deze modus is ingeschakeld.

- **Windows Server**: treedt als host op voor de Microsoft Intune Certificate Connector (NDESConnectorSetup.exe)

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Het basiscertificaat exporteren vanuit de CA voor ondernemingen

Voor verificatie met VPN, Wi-Fi en andere bronnen hebt u op elk apparaat een basis- of tussen-CA-certificaat nodig. In de volgende stappen wordt uitgelegd hoe u het vereiste certificaat kunt verkrijgen op basis van uw CA voor ondernemingen.

1. Meld u aan bij uw CA voor ondernemingen met een account met beheerdersbevoegdheden.
2. Open een opdrachtprompt als beheerder.
3. Exporteer het basis-CA-certificaat (.cer) naar een locatie waar u het later kunt gebruiken.

   Bijvoorbeeld:

4. Nadat de wizard is voltooid, maar voordat de wizard wordt gesloten, klikt u op **Gebruikersinterface van certificaatconnector starten**.

   `certutil -ca.cert certnew.cer`

   Zie [Certutil-taken voor het beheren van certificaten](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign) voor meer informatie.

## <a name="configure-certificate-templates-on-the-certification-authority"></a>Certificaatsjablonen configureren bij de certificeringsinstantie

1. Meld u aan bij uw CA voor ondernemingen met een account met beheerdersbevoegdheden.
2. Open de console **Certificeringsinstantie**, klik met de rechtermuisknop op **Certificaatsjablonen** en selecteer **Beheren**.
3. Zoek naar de certificaatsjabloon **Gebruiker**, klik er met de rechtermuisknop op en kies **Sjabloon dupliceren**. **Eigenschappen van nieuwe sjabloon** wordt geopend.
4. Op het tabblad **Compatibiliteit**:

  - Stel **Certificeringsinstantie (CA)** in op **Windows Server 2008 R2**
  - Stel **Ontvanger van certificaat** in op **Windows 7 / Server 2008 R2**

5. Stel op het tabblad **Algemeen** **Weergavenaam van sjabloon** in op iets dat voor u herkenbaar is.

   > [!WARNING]
   > **Sjabloonnaam** is standaard hetzelfde als **Weergavenaam van sjabloon**, maar dan *zonder spaties*. Noteer de naam van de sjabloon; deze hebt u later nodig.

6. Selecteer in **Afhandeling van aanvragen** de optie **De persoonlijke sleutel exporteerbaar maken**.
7. Bevestig in **Cryptografie** dat de **Minimale sleutelgrootte** is ingesteld op 2048.
8. Kies **Leveren met het verzoek** in **Onderwerpnaam**.
9. Bevestig in **Extensies** dat Encrypting File System, Beveiligde e-mail en Clientauthenticatie worden weergegeven onder **Toepassingsbeleid**.

    > [!IMPORTANT]
    > Ga voor iOS-certificaatsjablonen naar het tabblad **Extensies**, werk **Sleutelgebruik** bij en zorg ervoor dat **Handtekening is bewijs van authenticiteit** niet is ingeschakeld.

10. Voeg in **Beveiliging** het computeraccount toe voor de server waarop u de Microsoft Intune Certificate Connector installeert. Geef dit account machtigingen voor **Lezen** en **Registreren**.
11. Selecteer **Toepassen** en vervolgens **OK** om de certificaatsjabloon op te slaan.
12. Sluit de **console Certificaatsjablonen**.
13. Klik in de **certificeringsinstantieconsole** met de rechtermuisknop op **Certificaatsjablonen**, klik op **Nieuw** en klik vervolgens op **Te verlenen certificaatsjablonen**. Kies de sjabloon die u in de eerdere stappen hebt gemaakt en selecteer **OK**.
14. Om ervoor te zorgen dat de server certificaten beheert voor bij Intune geregistreerde apparaten en gebruikers, voert u de volgende stappen uit:

    1. Klik met de rechtermuisknop op de CA en kies **Eigenschappen**.
    2. Voeg op het tabblad Beveiliging het computeraccount toe voor de server waarop u de Microsoft Intune Certificate Connector uitvoert. Verleen de machtigingen **Certificaten verlenen en beheren** en **Certificaten aanvragen** aan het computeraccount.

15. Meld u af bij de CA voor ondernemingen.

## <a name="download-install-and-configure-the-certificate-connector"></a>De certificaatconnector downloaden, installeren en configureren

![ConnectorDownload][ConnectorDownload]

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaatconfiguratie** en vervolgens **Certificeringsinstantie**.
4. Selecteer **Toevoegen** en **Connectorbestand downloaden**. Sla het bestand op in een locatie waar u het kunt openen vanaf de server waarop u de connector gaat installeren.
5. Nadat het downloaden is voltooid, meldt u zich aan bij de server. Vervolgens:

    1. Controleer of .NET 4.5 Framework is geïnstalleerd. Dit wordt vereist door de NDES-certificaatconnector. .NET Framework 4.5 wordt automatisch geïnstalleerd met Windows Server 2012 R2 en nieuwere versies.
    2. Start het installatieprogramma (NDESConnectorSetup.exe) en accepteer de standaardlocatie. De connector wordt geïnstalleerd in `\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe`. Selecteer in de opties voor het installatieprogramma **PFX-distributie**. Ga verder en voltooi de installatie.

6. De NDES Connector opent het tabblad **Inschrijving**. Als u de verbinding met Intune wilt inschakelen, kiest u **Aanmelden** en geeft u een account met globale beheerdersmachtigingen op.
7. Op het tabblad **Geavanceerd** laat u het keuzerondje **Systeemaccount van deze computer gebruiken (standaard)** ingeschakeld.
8. **Toepassen** en vervolgens **Sluiten**.
9. Ga terug naar de Azure Portal (**Intune** > **Apparaatconfiguratie** > **Certificeringsinstantie**). Even later wordt een groen vinkje weergegeven en is de **Verbindingsstatus** **Actief**. Uw connector-server kan nu communiceren met Intune.

> [!NOTE]
> TLS 1.2-ondersteuning wordt geleverd met de NDES-certificaatconnector. Als de server met daarop de NDES-certificaatconnector TLS 1.2 ondersteunt, wordt TLS 1.2 gebruikt. Als de server TLS 1.2 niet ondersteunt, wordt TLS 1.1 gebruikt. Momenteel wordt TLS 1.1 gebruikt voor verificatie tussen de apparaten en de server.

## <a name="create-a-device-configuration-profile"></a>Een apparaatconfiguratieprofiel maken

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Ga naar **Intune** > **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.

   ![NavigateIntune][NavigateIntune]

3. Voer de volgende eigenschappen in:

  - **Naam** voor het profiel
  - Een beschrijving instellen (optioneel)
  - **Platform** waarvoor het profiel moet worden geïmplementeerd
  - Stel **Profieltype** in op **Vertrouwd certificaat**

4. Ga naar **Instellingen** en voer het eerder geëxporteerde CER-bestand van het basis-CA-certificaat in.

   > [!NOTE]
   > Afhankelijk van het platform dat u in **stap 3** kiest, hebt u al dan niet de mogelijkheid het **Doelarchief** voor het certificaat te kiezen.

   ![ProfileSettings][ProfileSettings]

5. Selecteer **OK** en vervolgens **Maken** om het profiel op te slaan.
6. Raadpleeg [Microsoft Intune-apparaatprofielen toewijzen](device-profile-assign.md) om het nieuwe profiel aan een of meer apparaten toe te wijzen.

## <a name="create-a-pkcs-certificate-profile"></a>Een PKCS-certificaatprofiel maken

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Ga naar **Intune** > **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

  - **Naam** voor het profiel
  - Een beschrijving instellen (optioneel)
  - **Platform** waarvoor het profiel moet worden geïmplementeerd
  - Stel **Profieltype** in op **PKCS-certificaat**

4. Ga naar **Instellingen** en voer de volgende eigenschappen in:

  - **Drempelwaarde voor verlenging (%)**: aanbevolen wordt 20%.
  - **Geldigheidsduur van certificaat**: als u de certificaatsjabloon niet hebt gewijzigd, kan deze optie worden ingesteld op één jaar.
  - **Certificeringsinstantie**: geeft de interne volledig gekwalificeerde domeinnaam (FQDN) van uw CA voor ondernemingen weer.
  - **Naam van certificeringsinstantie**: geeft de naam van uw CA voor ondernemingen weer en is mogelijk anders dan het vorige item.
  - **Certificaatsjabloonnaam**: de naam van de sjabloon die eerder is gemaakt. Nogmaals, **Sjabloonnaam** is standaard hetzelfde als **Weergavenaam van sjabloon**, maar dan *zonder spaties*.
  - **Indeling van de onderwerpnaam**: stel deze optie in op **Algemene naam** tenzij anders aangegeven.
  - **Alternatieve naam voor onderwerp**: stel deze optie in op **User principal name** tenzij anders aangegeven.
  - **Uitgebreide-sleutelgebruik**: wanneer u de standaardinstellingen in stap 10 in de sectie [Certificaatsjablonen configureren bij de certificeringsinstantie](#configure-certificate-templates-on-the-certification-authority) (in dit artikel) hebt gebruikt, voegt u de volgende **Vooraf gedefinieerde waarden**  uit de selectie in:
    - **Elk doeleinde**
    - **Clientauthenticatie**
    - **Beveiligde e-mail**
  - **Basiscertificaat**: (voor Android-profielen) geeft het CER-bestand weer dat werd geëxporteerd in stap 3 van de sectie [Het basiscertificaat exporteren vanuit de CA voor ondernemingen](#export-the-root-certificate-from-the-enterprise-ca) (in dit artikel).

5. Selecteer **OK** en vervolgens **Maken** om het profiel op te slaan.
6. Raadpleeg [Microsoft Intune-apparaatprofielen toewijzen](device-profile-assign.md) om het nieuwe profiel aan een of meer apparaten toe te wijzen.

## <a name="next-steps"></a>Volgende stappen
[Gebruik SCEP-certificaten](certificates-scep-configure.md) of [geef PKCS-certificaten uit van een webservice van Symantec PKI-manager](certificates-symantec-configure.md).

[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Navigeren naar Intune in Azure Portal en een nieuw profiel voor een vertrouwd certificaat maken"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Een profiel maken en een vertrouwd certificaat uploaden"
[ConnectorDownload]: ./media/certificates-download-connector.png "De certificaatconnector downloaden van Azure Portal"  
