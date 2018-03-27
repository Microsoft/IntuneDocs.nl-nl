---
title: Bulkinschrijving voor Windows 10
description: Een bulkregistratiepakket voor Microsoft Intune maken
keywords: ''
author: NathBarn
ms.author: NathBarn
manager: dougeby
ms.date: 03/18/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0053e37a-f26e-452f-9524-5039a635b52e
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.custom: intune-classic
ms.openlocfilehash: 3660255503c0dc7faa8d41b698f3d5fd9e4c330f
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="bulk-enrollment-for-windows-devices"></a>Bulkregistratie voor Windows-apparaten

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Als beheerder kunt u grote aantallen nieuwe Windows-apparaten toevoegen aan Azure Active Directory en Intune. Voor bulkregistratie van apparaten voor uw Azure AD-tenant, maakt u een inrichtingspakket met de app Windows Configuration Designer (WCD). Als u het inrichtingspakket toepast op apparaten die bedrijfseigendom zijn, worden de apparaten toegevoegd aan uw Azure AD-tenant en geregistreerd voor het beheer van Intune. Zodra het pakket is toegepast, kunnen uw Azure AD-gebruikers zich hierbij aanmelden.

Azure AD-gebruikers zijn standaardgebruikers op deze apparaten en ontvangen toegewezen Intune-beleid en de vereiste apps. Scenario's voor Selfservice portal en bedrijfsportal worden momenteel niet ondersteund.

## <a name="prerequisites-for-windows-devices-bulk-enrollment"></a>Vereisten voor bulkregistratie van Windows-apparaten

Voor bulkregistratie van Windows-apparaten is het volgende nodig:

- Apparaten met een Windows 10 Creator-update of later
- [Automatische inschrijving bij Windows](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)

## <a name="create-a-provisioning-package"></a>Een inrichtingspakket maken

1. Download [Windows Configuration Designer (WCD)](https://www.microsoft.com/store/apps/9nblggh4tx22) vanuit Microsoft Store.
![Schermafbeelding van de app Windows Configuration Designer en de beschrijving](../media/bulk-enroll-store.png)

2. Open de app **Windows Configuration Designer** en selecteer **Desktopapparaten inrichten**.
![Schermafbeelding van het selecteren van Desktopapparaten inrichten in de app Windows Configuration Designer](../media/bulk-enroll-select.png)

3. Het venster **Nieuw project** verschijnt, waarin u het volgende kunt opgeven:
  - **Naam**: een naam voor uw project
  - **Projectmap**: de map waar het nieuwe project wordt opgeslagen
  - **Beschrijving**: een optionele beschrijving van het project ![Schermafbeelding van het opgeven van de naam, projectmap en beschrijving in de app Windows Configuration Designer](../media/bulk-enroll-name.png)

4.  Voer een unieke naam in voor uw apparaten. Namen kunnen een serienummer (%%SERIAL%%) of een willekeurig aantal tekens bevatten. U kunt eventueel ook een productcode invoeren als u de editie van Windows bijwerkt, u kunt het apparaat configureren voor gedeeld gebruik en u kunt vooraf geïnstalleerde software verwijderen.<BR>
![Schermafbeelding van het opgeven van de naam, projectmap en beschrijving in de app Windows Configuration Designer](../media/bulk-enroll-device.png)

5.  U kunt eventueel instellen met welk het Wi-Fi-netwerk apparaten verbinding maken wanneer ze de eerste keer worden gestart.  Als dit niet is geconfigureerd, is een bekabelde netwerkverbinding vereist wanneer het apparaat voor de eerste keer wordt gestart.
![Schermafbeelding van het inschakelen van Wi-Fi met de opties Netwerk-SSID en Netwerktype in de app Windows Configuration Designer](../media/bulk-enroll-network.png)

6.  Selecteer **Enroll in Azure AD**, voer een datum van **Bulk Token Expiry** in en selecteer vervolgens **Get Bulk Token**.
![Schermafbeelding van het opgeven van de naam, projectmap en beschrijving in de app Windows Configuration Designer](../media/bulk-enroll-account.png)

7. Geef uw Azure AD-referenties op om een bulk-token op te halen.
![Schermafbeelding van het opgeven van de naam, projectmap en beschrijving in de app Windows Configuration Designer](../media/bulk-enroll-cred.png)

8.  Klik op **Volgende** wanneer de **Bulk Token** is opgehaald.

9. U kunt eventueel **toepassingen toevoegen** en **certificaten toevoegen**. Deze apps en certificaten worden ingericht op het apparaat.

10. U kunt eventueel uw inrichtingspakket beveiligen met een wachtwoord.  Klik op **Maken**.
![Schermafbeelding van het opgeven van de naam, projectmap en beschrijving in de app Windows Configuration Designer](../media/bulk-enroll-create.png)

## <a name="provision-devices"></a>Apparaten inrichten

1. Open het inrichtingspakket in de opgegeven locatie in de **projectmap** die is opgegeven in de app.

2. Kies hoe u het inrichtingspakket wilt toepassen op het apparaat.  U kunt een inrichtingspakket op een van de volgende manieren toepassen op een apparaat:
 - Plaats het inrichtingspakket op een USB-station, plaats het USB-station in het apparaat dat u bulksgewijs wilt registreren en pas het toe tijdens de eerste configuratie
 - Plaats het inrichtingspakket in een netwerkmap en pas het toe op het apparaat dat u bulksgewijs wilt registreren na de eerste configuratie

 Zie [Een inrichtingspakket toepassen](https://technet.microsoft.com/itpro/windows/configure/provisioning-apply-package) voor stapsgewijze instructies over het toepassen van een inrichtingspakket.

3. Nadat u het pakket hebt toegepast, wordt het apparaat na 1 minuut automatisch opnieuw opgestart.
 ![Schermafbeelding van het opgeven van de naam, projectmap en beschrijving in de app Windows Configuration Designer](../media/bulk-enroll-add.png)

4. Wanneer het apparaat opnieuw opstart, maakt het verbinding met de Azure Active Directory en registreert het zich bij Microsoft Intune.

## <a name="troubleshooting-windows-bulk-enrollment"></a>Problemen met bulksgewijze registratie bij Windows oplossen

Inrichten is bedoeld om te gebruiken op nieuwe Windows-apparaten. Bij inrichtingsfouten is het mogelijk vereist dat de fabrieksinstellingen van het apparaat worden hersteld of dat het apparaat wordt gestart vanaf een opstartinstallatiekopie. Deze voorbeelden bevatten enkele redenen voor inrichtingsfouten:

- Als een inrichtingspakket probeert lid te worden van een Active Directory-domein of Azure Active Directory-tenant en er hierbij geen lokaal account wordt gemaakt, kan het apparaat onbereikbaar worden als het lid worden van het domein mislukt omdat er geen netwerkverbinding is.
- Scripts die worden uitgevoerd door het inrichtingspakket, worden uitgevoerd in de systeemcontext en hiermee kunnen willekeurige wijzigingen worden aangebracht aan het bestandssysteem en de configuraties van het apparaat. Door een schadelijk of fout script kan het apparaat in een status komen die alleen kan worden beëindigd door een installatiekopie terug te zetten op het apparaat of het apparaat terug te zetten op de fabrieksinstellingen.
