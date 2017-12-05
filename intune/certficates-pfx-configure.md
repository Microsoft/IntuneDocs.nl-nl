---
title: PKCS-certificaten configureren en beheren met Intune
titleSuffix: Intune on Azure
description: PKCS-certificaten maken en toewijzen met Intune."
keywords: 
author: MicrosoftGuyJFlo
ms.author: joflore
manager: angrobe
ms.date: 11/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 105b5fc73bc537eaca67a0e6943701ba25a53972
ms.sourcegitcommit: 2b35c99ca7d3dbafe2dfe1e0b9de29573db403b9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/16/2017
---
# <a name="configure-and-manage-pkcs-certificates-with-intune"></a>PKCS-certificaten configureren en beheren met Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="requirements"></a>Vereisten

Als u PKCS-certificaten wilt gebruiken met Intune, is de volgende infrastructuur nodig:

* Een geconfigureerd, bestaand AD DS-domein (Active Directory Domain Services).
 
  Raadpleeg het artikel [AD DS-ontwerp en plannen](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning) voor meer informatie over het installeren en configureren van AD DS.

* Een geconfigureerde, bestaande certificeringsinstantie (CA) voor ondernemingen.

  Raadpleeg het artikel [Stapsgewijze handleiding bij Active Directory Certificate](https://technet.microsoft.com/library/cc772393) als u meer informatie wilt over het installeren en configureren van Active Directory Certificate Services (AD CS).

  > [!WARNING]
  > Voor Intune moet u AD CS uitvoeren met een certificeringsinstantie (CA) voor ondernemingen, niet met een zelfstandige certificeringsinstantie.

* Een client die verbonden is met de CA voor ondernemingen.
* Een geëxporteerde kopie van uw basiscertificaat van uw CA voor ondernemingen.
* De Microsoft Intune Certificate Connector (NDESConnectorSetup.exe) gedownload vanaf de Intune-portal.
* Een Windows Server beschikbaar voor het hosten van de Microsoft Intune Certificate Connector (NDESConnectorSetup.exe).

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Het basiscertificaat exporteren vanuit de CA voor ondernemingen

U hebt op elk apparaat een basis- of tussen-CA-certificaat nodig voor verificatie met VPN, Wi-Fi en andere bronnen. In de volgende stappen wordt uitgelegd hoe u het vereiste certificaat kunt verkrijgen op basis van uw CA voor ondernemingen.

1. Meld u aan bij uw CA voor ondernemingen met een account met beheerdersbevoegdheden.
2. Open een opdrachtprompt als beheerder.
3. Exporteer het basis-CA-certificaat naar een locatie waar u het later kunt gebruiken.

   Bijvoorbeeld:

   `certutil -ca.cert certnew.cer`

   Zie [Certutil-taken voor het beheren van certificaten](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign) voor meer informatie.


## <a name="configure-certificate-templates-on-the-certification-authority"></a>Certificaatsjablonen configureren bij de certificeringsinstantie

1. Meld u aan bij uw CA voor ondernemingen met een account met beheerdersbevoegdheden.
2. Open de console **Certificeringsinstantie**.
3. Klik met de rechtermuisknop op **Certificaatsjablonen** en kies **Beheren**.
4. Zoek naar de certificaatsjabloon **Gebruiker**, klik er met de rechtermuisknop op en kies **Sjabloon dupliceren**. Het venster **Eigenschappen van nieuwe sjabloon** wordt geopend.
5. Op het tabblad **Compatibiliteit**
   * Stel **Certificeringsinstantie (CA)** in op **Windows Server 2008 R2**
   * Stel **Ontvanger van certificaat** in op **Windows 7 / Server 2008 R2**
6. Op het tabblad **Algemeen**:
   * Stel **Weergavenaam van sjabloon** in op iets dat voor u herkenbaar is.

   > [!WARNING]
   > **Sjabloonnaam** is standaard hetzelfde als **Weergavenaam van sjabloon**, maar dan *zonder spaties*. Noteer de sjabloonnaam voor later gebruik.

7. Schakel op het tabblad **Afhandeling van aanvragen** het selectievakje **De persoonlijke sleutel exporteerbaar maken** in.
8. Bevestig op het tabblad **Cryptografie** dat de **Minimale sleutelgrootte** is ingesteld op 2048.
9. Kies op het tabblad **Onderwerpnaam** het keuzerondje **Met de aanvraag meeleveren**.
10. Bevestig op het tabblad **Extensies** dat Encrypting File System, Beveiligde e-mail en Clientauthenticatie worden weergegeven onder **Toepassingsbeleid**.
    
      > [!IMPORTANT]
      > Bewerk voor iOS- en macOS-certificaatsjablonen op het tabblad **Extensies** het **sleutelgebruik** en zorg ervoor dat **Handtekening is bewijs van authenticiteit** niet is ingeschakeld.

11. Voeg op het tabblad **Beveiliging** het computeraccount toe voor de server waarop u de Microsoft Intune Certificate Connector installeert.
    * Geef dit account machtigingen voor **Lezen** en **Registreren**.
12. Klik op **Toepassen** en klik op **OK** om de certificaatsjabloon op te slaan.
13. Sluit de **console Certificaatsjablonen**.
14. Klik in de **certificeringsinstantieconsole** met de rechtermuisknop op **Certificaatsjablonen**, klik op **Nieuw** en klik vervolgens op **Te verlenen certificaatsjablonen**.
    * Kies de sjabloon die u in de voorgaande stappen hebt gemaakt en klik op **OK**.
15. Om ervoor te zorgen dat de server certificaten beheert voor bij Intune geregistreerde apparaten en gebruikers, voert u de volgende stappen uit:

    a. Klik met de rechtermuisknop op de CA en kies **Eigenschappen**.

    b. Voeg op het tabblad Beveiliging het computeraccount toe voor de server waarop u de Microsoft Intune Certificate Connector uitvoert.
      * Verleen de machtigingen **Certificaten verlenen en beheren** en **Certificaten aanvragen** aan het computeraccount.
16. Meld u af bij de CA voor ondernemingen.

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>De Microsoft Intune Certificate Connector downloaden, installeren en configureren

![ConnectorDownload][ConnectorDownload]

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Navigeer naar **Intune**, **Apparaatconfiguratie**, **Certificeringsinstantie** en klik op **De certificaatconnector downloaden**.
   * Sla het bestand op in een locatie waar u het kunt openen vanaf de server waarop u de certificaatconnector gaat installeren.
3. Meld u aan bij de server waarop u de Microsoft Intune Certificate Connector gaat installeren.
4. Start het installatieprogramma en accepteer de standaardlocatie. De certificaatconnector wordt geïnstalleerd op C:\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe.

      a. Op de pagina Opties voor installatieprogramma kiest u **PFX-distributie**. Klik op **Volgende**.

   b. Klik op **Installeren** en wacht tot de installatie is voltooid.

   c. Schakel op de voltooiingspagina het selectievakje **Intune-connector starten** in en klik op **Voltooien**.

5. Het venster NDES-connector wordt nu geopend met het tabblad **Inschrijving**. Om de verbinding met Intune in te schakelen, klikt u op **Aanmelden** en geeft u een account met beheerdersmachtigingen op.
6. Op het tabblad **Geavanceerd** kunt u het keuzerondje **Systeemaccount van deze computer gebruiken (standaard)** ingeschakeld laten.
7. Klik op **Toepassen** en op **Sluiten**.
8. Ga nu terug naar Azure Portal. Onder **Intune**, **Apparaatconfiguratie**, **Certificeringsinstantie** ziet u na enkele minuten een groen vinkje en het woord **Actief** onder **Verbindingsstatus**. Dit is een bevestiging dat uw connectorserver kan communiceren met Intune.

## <a name="create-a-device-configuration-profile"></a>Een apparaatconfiguratieprofiel maken

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Navigeer naar **Intune**, **Apparaatconfiguratie**, **Profielen** en klik op **Profiel maken**.

   ![NavigateIntune][NavigateIntune]

3. Geef de volgende informatie op:
   * **Naam** voor het profiel
   * Een beschrijving instellen (optioneel)
   * **Platform** waarvoor het profiel moet worden geïmplementeerd
   * Stel **Profieltype** in op **Vertrouwd certificaat**
4. Navigeer naar **Instellingen** en geef het eerder geëxporteerde CER-bestand van het basis-CA-certificaat op.

   > [!NOTE]
   > Afhankelijk van het platform dat u kiest in **stap 3** hebt u al dan niet de mogelijkheid het **Doelarchief** voor het certificaat te kiezen.

   ![ProfileSettings][ProfileSettings]

5. Klik op **OK** en op **Maken** om het profiel op te slaan.
6. Raadpleeg [Microsoft Intune-apparaatprofielen toewijzen](device-profile-assign.md) om het nieuwe profiel aan een of meer apparaten toe te wijzen.

## <a name="create-a-pkcs-certificate-profile"></a>Een PKCS-certificaatprofiel maken

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Navigeer naar **Intune**, **Apparaatconfiguratie**, **Profielen** en klik op **Profiel maken**.
3. Geef de volgende informatie op:
   * **Naam** voor het profiel
   * Een beschrijving instellen (optioneel)
   * **Platform** waarvoor het profiel moet worden geïmplementeerd
   * Stel **Profieltype** in op **PKCS-certificaat**
4. Navigeer naar **Instellingen** en geef de volgende informatie op:
   * **Drempelwaarde voor verlenging (%)**: aanbevolen wordt 20%.
   * **Geldigheidsduur van certificaat**: als u de certificaatsjabloon niet hebt gewijzigd, moet deze optie worden ingesteld op één jaar.
   * **Certificeringsinstantie**: deze optie is de interne volledig gekwalificeerde domeinnaam (FQDN) van uw CA voor ondernemingen.
   * **Naam van certificeringsinstantie**: deze optie is de naam van uw CA voor ondernemingen en is mogelijk anders dan het vorige item.
   * **Certificaatsjabloonnaam**: deze optie is de naam van de sjabloon die eerder is gemaakt. Nogmaals, **Sjabloonnaam** is standaard hetzelfde als **Weergavenaam van sjabloon**, maar dan *zonder spaties*.
   * **Indeling van de onderwerpnaam**: stel deze optie in op **Algemene naam** tenzij anders aangegeven.
   * **Alternatieve naam voor onderwerp**: stel deze optie in op **User principal name** tenzij anders aangegeven.
   * **Uitgebreide-sleutelgebruik**: wanneer u de standaardinstellingen in stap 10 in de vorige sectie **Certificaatsjablonen configureren bij de certificeringsinstantie** hebt gebruikt, voegt u de volgende **Vooraf gedefinieerde waarden**  via het selectievakje in:
      * **Elk doeleinde**
      * **Clientauthenticatie**
      * **Beveiligde e-mail**
   * **Basiscertificaat**: (voor Android-profielen) deze optie is het CER-bestand dat werd geëxporteerd in stap 3 van de vorige sectie [Het basiscertificaat exporteren vanuit de CA voor ondernemingen](#export-the-root-certificate-from-the-enterprise-ca).

5. Klik op **OK** en op **Maken** om het profiel op te slaan.
6. Raadpleeg het artikel [Microsoft Intune-apparaatprofielen toewijzen](device-profile-assign.md) om het nieuwe profiel aan een of meer apparaten toe te wijzen.


[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Navigeren naar Intune in Azure Portal en een nieuw profiel voor een vertrouwd certificaat maken"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Een profiel maken en een vertrouwd certificaat uploaden"
[ConnectorDownload]: ./media/certificates-pfx-configure-connector-download.png "De certificaatconnector downloaden van Azure Portal"
