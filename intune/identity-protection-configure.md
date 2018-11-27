---
title: Instellingen voor identiteitsbescherming configureren in Microsoft Intune - Azure | Microsoft Docs
description: Een apparaatprofiel toevoegen om voor Windows 10-apparaten instellingen voor Windows Hello voor Bedrijven te configureren in Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: f9d0db8e15e6de1241984f98bf651fcff1578033
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52188628"
---
# <a name="configure-identity-protection-settings-in-microsoft-intune"></a>Instellingen voor identiteitsbescherming configureren in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Profielen voor identiteitsbescherming regelen de inrichting en configuratie van Windows Hello voor Bedrijven op beheerde Windows 10-apparaten. Maak dit profiel om het volgende te configureren:  
* Beschikbaarheid van Windows Hello voor Bedrijven voor apparaten en gebruikers.
* Vereisten voor pincode van apparaten.
* Gebaren die gebruikers wel en niet kunnen gebruiken om zich aan te melden bij hun apparaten.  

 U kunt dit profiel toewijzen om groepen gebruikers en apparaten te selecteren, of het aan alle gebruikers en alle apparaten toewijzen. Groepen ontvangen het profiel voor identiteitsbescherming wanneer ze inchecken bij Intune.    

Gebruik de informatie in dit artikel om een profiel voor identiteitsbescherming te maken. Wijs vervolgens [uw profiel toe](device-profile-assign.md) aan gebruikers- en apparaatgroepen.

Deze functie is van toepassing op apparaten met:  
- Windows 10 en hoger
- Windows Holographic for Business  

## <a name="create-a-device-profile-with-identity-protection-settings"></a>Een apparaatprofiel maken met instellingen voor identiteitsbescherming

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
4. Geef een **naam** en **beschrijving** op voor het profiel voor identiteitsbescherming.
5. Selecteer in de vervolgkeuzelijst **Platform** de optie **Windows 10 en hoger**. Windows Hello voor Bedrijven wordt alleen ondersteund op apparaten met Windows 10 en hoger.
6. Kies **Identiteitsbescherming** in de vervolgkeuzelijst **Profieltype**.
7. Kies in het deelvenster Windows Hello voor Bedrijven uit een van de volgende opties voor Windows Hello voor Bedrijven configureren:
    * Uitgeschakeld. Als u Windows Hello voor Bedrijven niet wilt gebruiken, selecteert u deze instelling. Alle andere instellingen op het scherm zijn niet beschikbaar.
    * Ingeschakeld. Selecteer deze instelling als u instellingen voor Windows Hello voor Business wilt configureren.  

8. Als u in de vorige stap **Ingeschakeld** hebt geselecteerd, configureert u de vereiste instellingen die worden toegepast op alle beoogde, geregistreerde Windows 10- en Windows 10 Mobile-apparaten en gebruikers.

> [!NOTE]
> Bij het toewijzen van profielen voor identiteitsbescherming voor alleen gebruikers wordt de apparaatcontext standaard ingesteld op **Niet geconfigureerd**.  

   - **Minimumlengte voor pincode**/**Maximumlengte voor pincode**. Hiermee configureert u apparaten om de opgegeven minimum- en maximumlengte van de pincode te gebruiken voor het beveiligen van de aanmelding. De standaardwaarde voor de pincode is zes tekens, maar u kunt een minimumlengte van vier tekens afdwingen. De maximumlengte voor de pincode is 127 tekens.  

   - **Kleine letters in pincode**/**Hoofdletters in pincode**/**Speciale tekens in pincode**. U kunt zorgen voor sterkere pincodes door het gebruik van kleine letters, hoofdletters en speciale tekens voor de pincode af te dwingen. U kunt kiezen uit:

     - **Toegestaan**. Gebruikers kunnen het tekentype gebruiken in hun pincode, maar dit is niet verplicht.

     - **Vereist**. Gebruikers moeten ten minste een van de tekentypen in hun pincode opnemen. Het is bijvoorbeeld gebruikelijk om ten minste één hoofdletter en één speciaal teken verplicht te stellen.

     - **Niet toegestaan** (standaardinstelling). Gebruikers mogen deze tekentypen niet in hun pincode gebruiken. (Dit gedrag treedt ook op als de instelling niet is geconfigureerd.)<br>Tot de speciale tekens behoren: **! " # $ % &amp; ' ( ) &#42; + , - . / : ; &lt; = &gt; ? @ [ \ ] ^ _ &#96; { &#124; } ~**

   - **Verlooptijd pincode (dagen)**. Het is raadzaam om een verloopperiode voor een pincode op te geven, waarna gebruikers deze moeten wijzigen. De standaardwaarde is 41 dagen.

   - **Pincodegeschiedenis onthouden**. Beperkt het hergebruik van eerder gebruikte pincodes. Standaard kunnen de laatste 5 gebruikte pincodes niet opnieuw worden gebruikt.  
   - **Herstel van de pincode inschakelen**: hiermee kan de gebruiker de pincode wijzigen met behulp van de pincodeherstelservice van Windows Hello voor Bedrijven. 
       - **Inschakelen**. De cloudservice versleutelt een geheim voor pincodeherstel dat op het apparaat wordt opgeslagen. De gebruiker kan de pincode wijzigen, indien nodig.  
       - **Niet geconfigureerd** (standaard). Er is geen geheim voor pincodeherstel gemaakt of opgeslagen. Als u de pincode van de gebruiker bent vergeten, kunt u alleen een nieuwe pincode verkrijgen door de bestaande pincode te verwijderen en een nieuwe te maken. De gebruiker moet zich opnieuw registreren voor de services waarvoor u met de oude pincode toegang had.  
   
   - **Een Trusted Platform Module (TPM) gebruiken**. Een TPM-chip biedt een extra laag gegevensbeveiliging. Kies een van de volgende waarden:  
     - **Inschakelen**. Alleen apparaten met een toegankelijke TPM kunnen Windows Hello voor Bedrijven inrichten.
     - **Niet geconfigureerd**. Alle apparaten kunnen Windows Hello voor Bedrijven inrichten, zelfs als er geen bruikbare TPM is. Apparaten proberen eerst gebruik te maken van een TPM, maar als er geen beschikbaar is, kunnen apparaten gebruik maken van softwareversleuteling.  

   - **Biometrische verificatie toestaan**. Hiermee kunt u biometrische verificatie, zoals gezichtsherkenning of een vingerafdruk, inschakelen als alternatief voor een pincode voor Windows Hello voor Bedrijven. Gebruikers moeten toch een pincode voor Passport for Work configureren voor het geval dat biometrische verificatie mislukt. U kunt kiezen uit:

     - **Inschakelen**. Windows Hello voor bedrijven staat biometrische verificatie toe.
     - **Niet geconfigureerd** (standaard). Windows Hello voor Bedrijven staat biometrische verificatie niet toe (voor alle typen accounts).

   - **Verbeterde anti-adresvervalsing gebruiken, indien beschikbaar**. Hiermee configureert u of de functies voor anti-adresvervalsing van Windows Hello worden gebruikt op apparaten die deze functie ondersteunen (bijvoorbeeld een foto van een gezicht in plaats van een echt gezicht detecteren).
       - **Inschakelen**. Windows verplicht alle gebruikers om een anti-adresvervalsing te gebruiken voor gezichtskenmerken, indien dit wordt ondersteund.  
       - **Niet geconfigureerd** (standaard). Windows houdt zich aan de anti-adresvervalsingsconfiguraties van het apparaat.

   - **Certificaat voor on-premises resources**. 
       - **Inschakelen**. Hiermee staat u Windows Hello voor Bedrijven toe certificaten te gebruiken voor verificatie bij on-premises resources.
       - **Niet geconfigureerd** (standaard). Hiermee voorkomt u dat Windows Hello voor Bedrijven certificaten gebruikt voor verificatie bij on-premises resources.  
9. Klik op **OK** om uw profiel op te slaan.  

Het profiel is gemaakt en wordt weergegeven in de lijst **Apparaatconfiguratie - profielen**. Zie [Apparaatprofielen toewijzen](device-profile-assign.md) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.  

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
