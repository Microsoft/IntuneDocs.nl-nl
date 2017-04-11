---
title: Certificaten configureren met Intune
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: meer informatie over het gebruik van Intune om certificaten te maken en toe te wijzen die u helpen Wi-Fi-, VPN- en andere verbindingen te beveiligen.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: d1c1833ea7fe9e794a70b2b2536f44801b68fa7e
ms.lasthandoff: 03/17/2017


---

# <a name="how-to-configure-certificates-in-microsoft-intune"></a>Certificaten configureren in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Wanneer u gebruikers toegang verleent tot bedrijfsresources via een VPN-, Wi-Fi- of e-mailprofiel, kunt u deze toegang beveiligen met een certificaat dat op elk gebruikersapparaat wordt geïnstalleerd. De basiswerkstroom ziet er als volgt uit:

1. Zorg ervoor dat er aan de vereisten voor de certificaatinfrastructuur is voldaan. U kunt [SCEP-certificaten](configure-certificate-infrastructure-for-scep.md) en [PKCS-certificaten](configure-certificate-infrastructure-for-pfx.md) gebruiken.
2. Installeer op elk apparaat een basiscertificaat (of het tussenliggende CA-certificaat), zodat het apparaat de geldigheid van uw certificeringsinstantie (CA) erkent. Hiervoor maakt u een **vertrouwd certificaatprofiel** en wijst u het profiel toe. Wanneer u dit profiel toewijst, zullen de apparaten die u met Intune beheert, het basiscertificaat aanvragen en ontvangen. U moet voor elk platform een afzonderlijk profiel maken. Vertrouwde certificaatprofielen zijn beschikbaar voor de volgende platformen:
    - iOS 8.0 en hoger
    - macOS 10.9 of hoger
    - Android 4.0 en hoger<!--Android for Work --->
    - Windows 8.1 en hoger
    - Windows Phone 8.1 en hoger
    - Windows 10 en hoger
3. Maak certificaatprofielen zodat apparaten een certificaat aanvragen ten behoeve van verificatie van toegang per e-mail, VPN en Wi-F. U kunt een **PKCS-** of **SCEP**-certificaatprofiel maken en implementeren voor apparaten op de volgende platformen:
    - iOS 8.0 en hoger
    - Android 4.0 en hoger
    - Android for Work
    - Windows 10 (Desktop en Mobile) en hoger

    U kunt alleen een SCEP-certificaatprofiel gebruiken voor de volgende platformen:

-     macOS 10.9 of hoger
-     Windows Phone 8.1 en hoger

U moet voor elk apparaatplatform een afzonderlijk profiel maken. Wanneer u het profiel maakt, koppelt u dit aan het vertrouwde basiscertificaatprofiel dat u al hebt gemaakt.

### <a name="further-considerations"></a>Verdere overwegingen

- Als u geen bedrijfscertificeringsinstantie hebt, moet u er een maken.
- Als u op basis van uw apparaatplatformen besluit het SCEP-profiel (Simplified Certificate Enrollment Protocol) te gebruiken, moet u ook een NDES-server (Network Device Enrollment Service) configureren.
- Bovendien moet u de Microsoft Intune-certificaatconnector downloaden en configureren, ongeacht of u SCEP-profielen of PKCS-profielen wilt gebruiken.

## <a name="before-you-start"></a>Voordat u begint


### <a name="if-you-want-to-use-scep-certificates"></a>Als u SCEP-certificaten wilt gebruiken

Zorg ervoor dat aan de vereisten in [De certificaatinfrastructuur voor SCEP](/intune-azure/configure-devices/configure-certificate-infrastructure-for-scep) wordt voldaan.

### <a name="if-you-want-to-use-pkcs-certificates"></a>Als u PKCS-certificaten wilt gebruiken

Zorg ervoor dat aan de vereisten in [De certificaatinfrastructuur voor PKCS](/intune-azure/configure-devices/configure-certificate-infrastructure-for-pfx) wordt voldaan.

## <a name="task-1-export-the-trusted-root-ca-certificate"></a>Taak 1: het vertrouwde basis-CA-certificaat exporteren
Exporteer het certificaat van vertrouwde basiscertificeringsinstanties (CA) als een **.cer** -bestand van de verlenende CA of van een apparaat dat uw verlenende CA vertrouwt. Exporteer de persoonlijke sleutel niet.

U importeert dit certificaat wanneer u een vertrouwd certificaatprofiel instelt.

## <a name="task-2-create-trusted-certificate-profiles"></a>Taak 2: vertrouwde certificaatprofielen maken
U moet een profiel voor een vertrouwd certificaat maken voordat u een SCEP- of PKCS-certificaatprofiel kunt maken. U hebt een vertrouwd certificaatprofiel en een SCEP- of PKCS-profiel nodig voor elk apparaatplatform.

### <a name="to-create-a-trusted-certificate-profile"></a>Een vertrouwd certificaatprofiel maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies op de blade **Intune** de optie **Apparaatconfiguratie**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
3. Kies **Profiel maken** op de blade Profielen.
4. Voer op de blade **Profiel maken** een **naam** en een **beschrijving** in voor het vertrouwde certificaatprofiel.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform voor dit vertrouwde certificaat. Op dit moment kunt u een van de volgende platformen kiezen voor certificaatinstellingen:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 en hoger**
    - **Windows 10 en hoger**
6. Kies in de vervolgkeuzelijst **Profieltype** de optie **Vertrouwd certificaat**.
7. Blader naar het certificaat dat u in taak 1 hebt opgeslagen, en klik vervolgens op **OK**.
8. Voor Windows 8.1- en Windows 10-apparaten selecteert u het **doelarchief** voor het vertrouwde certificaat vanuit:
    - **Certificaatarchief van de computer – basis**
    - **Certificaatarchief van de computer – tijdelijk**
    - **Certificaatarchief van de gebruiker – tijdelijk**
8. Als u klaar bent, kiest u **OK**, gaat u terug naar de blade **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.
Zie [How to assign device profiles](how-to-assign-device-profiles.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.


> [!Note]
> Android-apparaten geven een melding weer dat een derde partij een vertrouwd certificaat heeft geïnstalleerd.

## <a name="task-3-create-scep-or-pkcs-certificate-profiles"></a>Taak 3: SCEP- of PKCS-certificaatprofielen maken
Nadat u een vertrouwd certificaatprofiel hebt gemaakt, maakt u SCEP- of PKCS-certificaatprofielen voor elk platform dat u wilt gebruiken. Wanneer u een SCEP-certificaatprofiel maakt, moet u een profiel voor een vertrouwd certificaat voor datzelfde platform opgeven. Hierdoor worden de twee certificaatprofielen gekoppeld. U moet nog wel elk profiel afzonderlijk toewijzen.

### <a name="to-create-an-scep-certificate-profile"></a>Een SCEP-certificaatprofiel maken

1. Selecteer in Azure Portal de workload **Apparaten configureren**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
3. Kies **Profiel maken** op de blade Profielen.
4. Voer op de blade **Profiel maken** een **naam** en een **beschrijving** in voor het SCEP-certificaatprofiel.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform voor dit SCEP-certificaat. Op dit moment kunt u een van de volgende platformen kiezen voor apparaatbeperkingsinstellingen:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 en hoger**
    - **Windows 10 en hoger**
6. Kies in de vervolgkeuzelijst **Profieltype** de optie **SCEP-certificaat**.
7. Configureer op de blade **SCEP-certificaat** de volgende instellingen:
    - **Geldigheidsduur van certificaat**: als u de opdracht **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** hebt uitgevoerd voor de verlenende CA, waarmee een aangepaste geldigheidsperiode mogelijk is, kunt u opgeven hoe lang het certificaat geldig blijft.<br>U kunt een waarde opgeven die lager is dan de geldigheidsperiode in het opgegeven certificaatsjabloon, maar niet hoger. Als de geldigheidsperiode van het certificaat in het certificaatsjabloon bijvoorbeeld twee jaar is, kunt u wel één jaar, maar niet vijf jaar opgeven. De waarde moet ook lager zijn dan de resterende geldigheidsperiode van het certificaat van de verlenende CA. 
    - **Sleutelarchiefprovider (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10): geef op waar de sleutel voor het certificaat wordt opgeslagen. Kies een van de volgende waarden:
        - **Registeren in de sleutelarchiefprovider voor TPM (Trusted Platform Module) indien TPM aanwezig is, anders registreren in de sleutelarchiefprovider voor software**
        - **Registreren in de sleutelarchiefprovider voor TPM (Trusted Platform Module), anders mislukt**
        - **Registreren bij Passport, anders niet uitvoeren (Windows 10 en hoger)**
        - **Registreren in sleutelarchiefprovider voor software**
    - **Indeling van de onderwerpnaam**: selecteer in de lijst hoe de onderwerpnaam in de certificaataanvraag automatisch wordt gemaakt met Intune. Als het certificaat voor een gebruiker is, kunt u ook het e-mailadres van de gebruiker in de onderwerpnaam opnemen. U kunt kiezen uit:
        - **Niet geconfigureerd**
        - **Algemene naam**
        - **Algemene naam en e-mailadres**
        - **Algemene naam als e-mailadres**
    - **Alternatieve onderwerpnaam**: geef op hoe de waarden voor de alternatieve naam van het onderwerp (SAN) in de certificaataanvraag automatisch worden gemaakt met Intune. Als u bijvoorbeeld een gebruikerscertificaattype selecteerde, kunt u de User Principal Name (UPN) gebruiken in de alternatieve naam van het onderwerp. Als het clientcertificaat zal worden gebruikt om een Network Policy Server te verifiëren, dient u de alternatieve naam van het onderwerp op de UPN in te stellen. 
    - **Sleutelgebruik**: geef opties voor sleutelgebruik voor het certificaat op. U kunt kiezen uit de volgende opties: 
        - **Sleutelcodering**: sta alleen sleuteluitwisseling toe als de sleutel is gecodeerd. 
        - **Digitale handtekening**: sta alleen sleuteluitwisseling toe als een digitale handtekening de sleutel helpt beveiligen. 
    - **Sleutelgrootte (bits)**: selecteer het aantal bits in de sleutel. 
    - **Hash-algoritme** (Android, Windows Phone 8.1, Windows 8.1, Windows 10): selecteer een van de beschikbare typen hash-algoritme om met dit certificaat te gebruiken. Selecteer het sterkste beveiligingsniveau dat door de verbindende apparaten wordt ondersteund. 
    - **Basiscertificaat**: kies een basis-CA-certificaatprofiel dat u eerder hebt geconfigureerd en aan de gebruiker of het apparaat hebt toegewezen. Dit CA-certificaat moet het basiscertificaat zijn voor de CA die het certificaat verleent dat u in dit certificaatprofiel gaat configureren. 
    - **Uitgebreide-sleutelgebruik**: kies **Toevoegen** om waarden voor het beoogde gebruik van het certificaat toe te voegen. In de meeste gevallen vereist het certificaat **Clientverificatie** zodat de gebruiker of het apparaat bij een server kan worden geverifieerd. U kunt echter zo nodig andere sleutelgebruiken toevoegen. 
    - **Registratie-instellingen**
        - **Drempelwaarde voor verlenging (%)**: geef het percentage van de levensduur van het certificaat op dat resteert voordat het apparaat verlenging van het certificaat aanvraagt.
        - **URL's van SCEP-server**: geef een of meer URL's op voor de NDES-servers die certificaten via SCEP verlenen. 
8. Als u klaar bent, gaat u terug naar de blade **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.

Volg de instructies op de profielconfiguratiepagina om de instellingen voor het SCEP-certificaatprofiel te configureren.
>[!Note]
> Alleen voor iOS-apparaten: selecteer onder Indeling van onderwerpnaam de optie Aangepast om een aangepaste indeling voor de onderwerpnaam in te voeren.
> De twee variabelen die momenteel worden ondersteund voor de aangepaste indeling zijn **Algemene naam (CN)** en **E-mail (E)**. Met behulp van een combinatie van deze variabelen en statische tekenreeksen kunt u een aangepaste indeling voor de onderwerpnaam maken, zoals: **CN={{UserName}},E={{EmailAddress}},OU=Mobiel,O=Financiële groep,L=Redmond,ST=Washington,C=VS** In dit voorbeeld hebt u een indeling voor een onderwerpnaam gemaakt die naast de CN- en E-variabelen tekenreeksen voor de waarden van de organisatie-eenheid, de organisatie, de locatie, de staat en het land gebruikt. [In dit onderwerp](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) worden de functie **CertStrToName** en de ondersteunde tekenreeksen gedemonstreerd.


### <a name="to-create-a-pkcs-certificate-profile"></a>Een PKCS-certificaatprofiel maken

Selecteer in Azure Portal de workload **Apparaten configureren**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
3. Klik op **Profiel maken** op de blade Profielen.
4. Voer op de blade **Profiel maken** een **naam** en een **beschrijving** in voor het PKCS-certificaatprofiel.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform voor dit PKCS-certificaat. U kunt kiezen uit:
    - **Android**
    - **iOS**
    - **Windows 10 en hoger**
6. Kies in de vervolgkeuzelijst **Profieltype** de optie **PKCS-certificaat**.
7. Configureer op de blade **PKCS-certificaat** de volgende instellingen:
    - **Drempelwaarde voor verlenging (%)**: geef het percentage van de levensduur van het certificaat op dat resteert voordat het apparaat verlenging van het certificaat aanvraagt.
    - **Geldigheidsduur van certificaat**: als u de opdracht **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** hebt uitgevoerd voor de verlenende CA, waarmee een aangepaste geldigheidsperiode mogelijk is, kunt u opgeven hoe lang het certificaat geldig blijft.<br>U kunt een waarde opgeven die lager is dan de geldigheidsperiode in het opgegeven certificaatsjabloon, maar niet hoger. Als de geldigheidsperiode van het certificaat in het certificaatsjabloon bijvoorbeeld twee jaar is, kunt u wel één jaar, maar niet vijf jaar opgeven. De waarde moet ook lager zijn dan de resterende geldigheidsperiode van het certificaat van de verlenende CA.
    - **Sleutelarchiefprovider (KSP)** (Windows 10) -
    - **Certificeringsinstantie** -
    - **Naam van certificeringsinstantie** -
    - **Certificaatsjabloonnaam**: voer de naam in van een certificaatsjabloon die is geconfigureerd om door de registratieservice van het netwerkapparaat te worden gebruikt en die is toegevoegd aan een verlenende CA.
    Zorg ervoor dat de naam exact overeenkomt met een van de certificaatsjablonen die zijn vermeld in het register van de server waarop de registratieservice van netwerkapparaten wordt uitgevoerd. Zorg ervoor dat u de naam opgeeft van het certificaatsjabloon en niet de weergavenaam van het certificaatsjabloon. 
    Blader naar de volgende sleutel om de namen te vinden van certificaatsjablonen: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP. De certificaatsjablonen worden hier vermeld als de waarden voor **EncryptionTemplate**, **GeneralPurposeTemplate**en **SignatureTemplate**. Standaard is IPSECIntermediateOffline de waarde voor deze drie certificaatsjablonen. Dit verwijst naar de sjabloonweergavenaam **IPSec (Offline-aanvraag)**. 
    - **Indeling van de onderwerpnaam**: selecteer in de lijst hoe de onderwerpnaam in de certificaataanvraag automatisch wordt gemaakt met Intune. Als het certificaat voor een gebruiker is, kunt u ook het e-mailadres van de gebruiker in de onderwerpnaam opnemen. U kunt kiezen uit:
        - **Niet geconfigureerd**
        - **Algemene naam**
        - **Algemene naam en e-mailadres**
        - **Algemene naam als e-mailadres**
    - **Alternatieve onderwerpnaam**: geef op hoe de waarden voor de alternatieve naam van het onderwerp (SAN) in de certificaataanvraag automatisch worden gemaakt met Intune. Als u bijvoorbeeld een gebruikerscertificaattype selecteerde, kunt u de User Principal Name (UPN) gebruiken in de alternatieve naam van het onderwerp. Als het clientcertificaat zal worden gebruikt om een Network Policy Server te verifiëren, dient u de alternatieve naam van het onderwerp op de UPN in te stellen.
    - **Uitgebreide-sleutelgebruik** (Android): kies **Toevoegen** om waarden voor het beoogde gebruik van het certificaat toe te voegen. In de meeste gevallen vereist het certificaat **Clientverificatie** zodat de gebruiker of het apparaat bij een server kan worden geverifieerd. U kunt echter zo nodig andere sleutelgebruiken toevoegen. 
    - **Basiscertificaat** (Android): kies een basis-CA-certificaatprofiel dat u eerder hebt geconfigureerd en aan de gebruiker of het apparaat hebt toegewezen. Dit CA-certificaat moet het basiscertificaat zijn voor de CA die het certificaat verleent dat u in dit certificaatprofiel gaat configureren.
8. Als u klaar bent, gaat u terug naar de blade **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.

## <a name="task-4-assign-certificate-profiles"></a>Taak 4: certificaatprofielen toewijzen

Overweeg het volgende voordat u certificaatprofielen aan groepen toewijst:

- Wanneer u certificaatprofielen aan groepen toewijst, wordt het certificaatbestand van het vertrouwde CA-certificaatprofiel op het apparaat geïnstalleerd. Het apparaat gebruikt het SCEP- of PKCS-certificaatprofiel om een certificaataanvraag te maken.
- Certificaatprofielen worden alleen geïnstalleerd op apparaten met het platform dat u gebruikt wanneer u het profiel maakt.
- U kunt certificaatprofielen implementeren voor gebruikersverzamelingen of voor apparaatverzamelingen.
- Als u een certificaat snel naar een apparaat wilt publiceren nadat het apparaat is geregistreerd, implementeert u het certificaatprofiel voor een gebruikersgroep en niet voor een apparaatgroep. Als u voor een apparaatgroep implementeert, is een volledige apparaatregistratie vereist voordat het apparaat beleid ontvangt.
- Hoewel u elk profiel afzonderlijk implementeert, moet u ook het vertrouwde basis-CA- en het SCEP- of PKCS-profiel implementeren. Anders mislukt het SCEP- of PKCS-certificaatbeleid.

## <a name="next-steps"></a>Volgende stappen
Zie [Apparaatprofielen toewijzen](how-to-assign-device-profiles.md) voor algemene informatie over het toewijzen van apparaatprofielen.

