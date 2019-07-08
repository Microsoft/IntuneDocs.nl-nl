---
title: Bulkinschrijving voor Windows 10
titleSuffix: Microsoft Intune
description: Een bulkregistratiepakket voor Microsoft Intune maken
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/21/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: damionw
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 996380a4938ca73bbf5f71c82e99814f772001a4
ms.sourcegitcommit: 256952cac44bc6289156489b6622fdc1a3c9c889
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2019
ms.locfileid: "67403464"
---
# <a name="bulk-enrollment-for-windows-devices"></a>Bulkregistratie voor Windows-apparaten

Als beheerder kunt u grote aantallen nieuwe Windows-apparaten toevoegen aan Azure Active Directory en Intune. Voor bulkregistratie van apparaten voor uw Azure AD-tenant, maakt u een inrichtingspakket met de app Windows Configuration Designer (WCD). Als u het inrichtingspakket toepast op apparaten die bedrijfseigendom zijn, worden de apparaten toegevoegd aan uw Azure AD-tenant en geregistreerd voor het beheer van Intune. Nadat het pakket is toegepast, kunnen uw Azure AD-gebruikers zich hierbij aanmelden.

Azure AD-gebruikers zijn standaardgebruikers op deze apparaten en ontvangen toegewezen Intune-beleid en de vereiste apps. Windows-apparaten die zijn geregistreerd bij Intune via Windows-bulkinschrijving, kunnen de bedrijfsportal-app gebruiken voor het installeren van beschikbare apps. 

## <a name="prerequisites-for-windows-devices-bulk-enrollment"></a>Vereisten voor bulkregistratie van Windows-apparaten

- Apparaten met een Windows 10 Creator-update (build 1703) of later
- [Automatische inschrijving bij Windows](windows-enroll.md#enable-windows-10-automatic-enrollment)

## <a name="create-a-provisioning-package"></a>Een inrichtingspakket maken

1. Download [Windows Configuration Designer (WCD)](https://www.microsoft.com/store/apps/9nblggh4tx22) vanuit Microsoft Store.
   ![Schermafbeelding van de App Store Windows Configuration Designer](media/bulk-enroll-store.png)

2. Open de app **Windows Configuration Designer** en selecteer **Desktopapparaten inrichten**.
   ![Schermafbeelding van het selecteren van Desktopapparaten inrichten in de app Windows Configuration Designer](media/bulk-enroll-select.png)

3. Het venster **Nieuw project** verschijnt, waarin u de volgende gegevens invoert:
   - **Naam**: een naam voor uw project
   - **Projectmap**: opslaglocatie voor het project
   - **Beschrijving**: een optionele beschrijving van het project ![Schermafbeelding van het opgeven van de naam, projectmap en beschrijving in de app Windows Configuration Designer](media/bulk-enroll-name.png)

4. Voer een unieke naam in voor uw apparaten. Namen kunnen een serienummer (%SERIAL%) of een willekeurig aantal tekens bevatten. U kunt eventueel ook een productcode invoeren als u de editie van Windows bijwerkt, u kunt het apparaat configureren voor gedeeld gebruik en u kunt vooraf geïnstalleerde software verwijderen.
   
   ![Schermafbeelding van het opgeven van de naam en productsleutel in de app Windows Configuration Designer](media/bulk-enroll-device.png)

5. U kunt eventueel instellen met welk het Wi-Fi-netwerk apparaten verbinding maken wanneer ze de eerste keer worden gestart.  Als de netwerkapparaten niet zijn geconfigureerd, is een bekabelde netwerkverbinding vereist wanneer het apparaat voor de eerste keer wordt gestart.
   ![Schermafbeelding van het inschakelen van Wi-Fi met de opties Netwerk-SSID en Netwerktype in de app Windows Configuration Designer](media/bulk-enroll-network.png)

6. Selecteer **Enroll in Azure AD**, voer een datum van **Bulk Token Expiry** in en selecteer vervolgens **Get Bulk Token**.
   ![Schermafbeelding van accountbeheer in de app Windows Configuration Designer](media/bulk-enroll-account.png)

7. Geef uw Azure AD-referenties op om een bulk-token op te halen.
   ![Schermafbeelding van aanmelding bij de app Windows Configuration Designer](media/bulk-enroll-cred.png)

8. Klik op **Volgende** wanneer de **Bulk Token** is opgehaald.

9. U kunt eventueel **toepassingen toevoegen** en **certificaten toevoegen**. Deze apps en certificaten worden ingericht op het apparaat.

10. U kunt eventueel uw inrichtingspakket beveiligen met een wachtwoord.  Klik op **Maken**.
    ![Schermafbeelding van pakketbeveiliging in de app Windows Configuration Designer](media/bulk-enroll-create.png)

## <a name="provision-devices"></a>Apparaten inrichten

1. Open het inrichtingspakket in de opgegeven locatie in de **projectmap** die is opgegeven in de app.

2. Kies hoe u het inrichtingspakket wilt toepassen op het apparaat.  U kunt een inrichtingspakket op een van de volgende manieren toepassen op een apparaat:
   - Plaats het inrichtingspakket op een USB-station, plaats het USB-station in het apparaat dat u bulksgewijs wilt registreren en pas het toe tijdens de eerste configuratie
   - Plaats het inrichtingspakket in een netwerkmap en pas het toe op het apparaat dat u bulksgewijs wilt registreren na de eerste configuratie

   Zie [Een inrichtingspakket toepassen](https://technet.microsoft.com/itpro/windows/configure/provisioning-apply-package) voor stapsgewijze instructies over het toepassen van een inrichtingspakket.

3. Nadat u het pakket hebt toegepast, wordt het apparaat na 1 minuut automatisch opnieuw opgestart.
   ![Schermafbeelding van het opgeven van de naam, projectmap en beschrijving in de app Windows Configuration Designer](media/bulk-enroll-add.png)

4. Wanneer het apparaat opnieuw opstart, maakt het verbinding met de Azure Active Directory en registreert het zich bij Microsoft Intune.

## <a name="troubleshooting-windows-bulk-enrollment"></a>Problemen met bulksgewijze registratie bij Windows oplossen

### <a name="provisioning-issues"></a>Inrichtingsproblemen
Inrichten is bedoeld om te gebruiken op nieuwe Windows-apparaten. Bij inrichtingsfouten is het mogelijk vereist dat het apparaat wordt gewist of dat het apparaat wordt gestart vanaf een opstartinstallatiekopie. Deze voorbeelden bevatten enkele redenen voor inrichtingsfouten:

- Als een inrichtingspakket probeert lid te worden van een Active Directory-domein of Azure Active Directory-tenant en er hierbij geen lokaal account wordt gemaakt, kan het apparaat onbereikbaar worden als het lid worden van het domein mislukt omdat er geen netwerkverbinding is.
- Scripts van het inrichtingspakket worden uitgevoerd binnen de systeemcontext. De scripts kunnen willekeurige wijzigingen aanbrengen in het bestandssysteem en configuraties van het apparaat. Door een schadelijk of fout script kan het apparaat in een status komen die alleen kan worden beëindigd door een installatiekopie terug te zetten op het apparaat of het apparaat te wissen.

### <a name="bulk-enrollment-with-wi-fi"></a>Bulkregistratie met Wi-Fi 

Voor in bulk geregistreerde apparaten kunnen geen op gebruikers gerichte certificaten en Wi-Fi-implementatie worden gebruikt. U moet [certificaten op apparaatniveau](certificates-configure.md) gebruiken voor het beheren van deze verbindingen. 

### <a name="conditional-access"></a>Voorwaardelijke toegang
Voorwaardelijke toegang is niet beschikbaar voor Windows-apparaten die zijn geregistreerd via bulkinschrijving.
