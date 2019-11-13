---
title: De Windows 10-bedrijfsportal-app handmatig toevoegen
titleSuffix: Microsoft Intune
description: Informatie over hoe uw werknemers handmatig de Windows 10-bedrijfsportal-app kunnen toevoegen uit de Microsoft Store.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/06/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: bfe1a2d3-f611-4dbb-adef-c0dff4d7b810
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 93570bc9dab20801ea6681f6a142de62990a1c57
ms.sourcegitcommit: 28622c5455adfbce25a404de4d0437fa2b5370be
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2019
ms.locfileid: "73712955"
---
# <a name="manually-add-the-windows-10-company-portal-app-by-using-microsoft-intune"></a>De Windows 10-bedrijfsportal-app handmatig toevoegen met Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Uw gebruikers kunnen de bedrijfsportal-app zelf installeren vanuit Microsoft Store voor het beheren van apparaten en het installeren van apps. Als uw bedrijf echter vereist dat u de bedrijfsportal-app aan ze toewijst, kunt u de Windows 10-bedrijfsportal-app handmatig rechtstreeks toewijzen vanuit Intune. U kunt dit zelfs doen als u Intune niet met de Microsoft Store voor Bedrijven hebt geïntegreerd.

 > [!NOTE]
 > Voor de optie die in dit artikel wordt beschreven, moet u updates telkens handmatig toewijzen wanneer een app-update wordt uitgebracht.

## <a name="configure-settings-to-show-offline-apps"></a>Instellingen configureren om apps offline weer te geven
1. Meld u met uw beheerdersaccount aan bij [Microsoft Store voor Bedrijven](https://www.microsoft.com/business-store).
2. Selecteer het tabblad **Beheren** boven in het venster.
3. Selecteer **Instellingen** in het linkerdeelvenster.
4. Stel **Offline apps weergeven** onder **Winkelervaring** in op **Aan**.  
    De offline gelicentieerde apps worde weergegeven.

## <a name="download-the-offline-company-portal-app"></a>De offline bedrijfsportal-app downloaden
1. Zoek en selecteer de app **Bedrijfsportal**.
2. Stel het**Licentietype** in op **Offline**.
3. Selecteer **De app downloaden** om de offline bedrijfsportal-app te verkrijgen en toe te voegen aan uw inventaris.
4. Klik op **Beheren** op de pagina **Bedrijfsportal** van de app.
5. Selecteer voor **Platform** de optie **Windows 10 alle apparaten**. Selecteer vervolgens de juiste **Minimumversie**, **Architectuur** en de waarden voor **het downloaden van de app-metagegevens**. 
6. Selecteer **Downloaden** onder **Pakketgegevens** om het bestand op te slaan op de lokale computer.

    ![Windows 10-apparaten waarbij gebruik wordt gemaakt van X86-architectuur worden geselecteerd](./media/app-sideload-windows/Win10CP-all-devices.png)

7. Download alle pakketten onder ‘Vereiste frameworks’ door **Downloaden** te selecteren.  

    Deze actie moet worden uitgevoerd voor x86-, x64- en ARM-architecturen:<br> 
    *Er zijn 9 Framework-pakketten vereist wanneer u 1507 selecteert als de minimale besturingssysteemversie, 12 pakketten als u 1511 selecteert, en 15 pakketten bij 1607.*

8. In Microsoft Intune in Azure Portal moet u Bedrijfsportal-app als nieuwe app uploaden. U voegt de toepassing toe door in het deelvenster **App toevoegen** de optie Line-of-Business-app te kiezen als het **App-type**. U selecteert vervolgens het app-pakketbestand (met de extensie .AppxBundle).

9. Selecteer onder **Afhankelijkheidsapp-bestanden selecteren** met behulp van Shift+klikken alle afhankelijkheden die u hebt gedownload in stap 7, en controleer of in de kolom **Toegevoegd** bij de gewenste architecturen **Ja** staat.

     > [!NOTE]
     > Als de afhankelijkheden niet zijn toegevoegd, kan de app mogelijk niet worden geïnstalleerd op de opgegeven apparaattypen.

10. Klik op **OK**, voer eventuele gewenste **App-gegevens** in, en klik op **Toevoegen**.

11. Wijs de Bedrijfsportal-app, indien nodig, toe als vereiste app voor een geselecteerde set gebruikers- of apparaatgroepen.  

Zie [Deploying an appxbundle with dependencies via Microsoft Intune MDM](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) (Een appxbundle met afhankelijkheden implementeren via Microsoft Intune MDM) voor meer informatie over hoe Intune afhankelijkheden voor universele apps verwerkt.  

## <a name="frequently-asked-questions"></a>Veelgestelde vragen 
### <a name="how-do-i-update-the-company-portal-app-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Hoe kan ik de Bedrijfsportal-app op de apparaten van mijn gebruikers bijwerken als hierop al de oudere apps uit de Store zijn geïnstalleerd?
Als uw gebruikers de Windows 8.1- of Windows Phone 8.1-bedrijfsportal-apps al hebben geïnstalleerd vanuit de Microsoft Store, moeten hun apps automatisch worden bijgewerkt naar de nieuwste versie, zonder dat hiervoor actie door u of uw gebruikers is vereist. Als de update niet wordt uitgevoerd, vraagt u uw gebruikers om te bevestigen dat automatische updates voor Store-apps op hun apparaten is ingeschakeld.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Hoe ik een upgrade uitvoeren van mijn gesideloade Windows 8.1-bedrijfsportal-app naar de Windows 10-bedrijfsportal-app?
Het wordt aanbevolen de toewijzing voor de Windows 8.1-bedrijfsportal-app te verwijderen door de toewijzingsactie in te stellen op **Installatie ongedaan maken**. Als u deze instelling selecteert, kunt u de Windows 10 Bedrijfsportal-app toewijzen aan de hand van eender welke van de besproken opties.  

Als u de app moet sideloaden en de Windows 8.1-bedrijfsportal hebt toegewezen zonder deze te ondertekenen met het Symantec-certificaat, volgt u de stappen in de vorige secties van dit artikel om de upgrade te voltooien.

Als u de app moet sideloaden en de Windows 8.1-bedrijfsportal-app hebt ondertekend en toegewezen met het Symantec-certificaat voor de ondertekening van programmacode, volgt u de stappen in de volgende sectie.

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Hoe kan ik een upgrade uitvoeren van mijn ondertekende en gesideloade Windows Phone 8.1-bedrijfsportal-app of Windows 8.1-bedrijfsportal-app naar de Windows 10-bedrijfsportal-app?
Het wordt aanbevolen de bestaande toewijzing voor de Windows Phone 8.1-bedrijfsportal-app of de Windows 8.1-bedrijfsportal-app te verwijderen door de toewijzingsactie in te stellen op **Installatie ongedaan maken**. Als u deze instelling selecteert, kunt u de Windows 10 Bedrijfsportal-app zoals gebruikelijk toewijzen.  

Anders moet de Windows 10-bedrijfsportal-app op de juiste manier worden bijgewerkt en ondertekend om ervoor te zorgen dat het upgradepad in acht wordt genomen.  

Als u de Windows 10-bedrijfsportal-app op deze manier ondertekent en toewijst, moet u dit proces herhalen voor elke nieuwe app-update wanneer deze beschikbaar is in de Store. De app wordt niet automatisch bijgewerkt wanneer de Store wordt bijgewerkt.  

Het ondertekenen en toewijzen van de app gaat als volgt:

1. Download het [ondertekeningsscript voor de Microsoft Intune Windows 10-bedrijfsportal-app](https://aka.ms/win10cpscript).  
    Voor dit script moet de Windows SDK voor Windows 10 moet zijn geïnstalleerd op de hostcomputer. [Download de Windows-SDK voor Windows 10](https://go.microsoft.com/fwlink/?LinkId=619296).
2. Download de Windows 10-bedrijfsportal-app vanuit Microsoft Store voor Bedrijven, zoals hierboven is beschreven.  
3. Voer het script uit met de invoerparameters die zijn opgegeven in de koptekst van het script om de Windows-10-bedrijfsportal-app te ondertekenen (zie de volgende tabel).  
    Afhankelijkheden hoeven niet in het script te worden doorgegeven. Deze zijn alleen vereist wanneer de app wordt geüpload naar de Intune-beheerconsole.

| Parameter |  Beschrijving  |
|---|---|
| InputWin10AppxBundle  |  Het pad naar het bron-appxbundle-bestand. |
| OutputWin10AppxBundle | Het uitvoerpad voor het ondertekende appxbundle-bestand. 
| Win81Appx  | Het pad naar het Windows 8.1- of Windows Phone 8.1-bedrijfsportalbestand (het appx-bestand). |
| PfxFilePath  |  Het pad naar het certificaat voor ondertekening van programmacode voor mobiele bedrijfsapparaten van Symantec (het PFX-bestand).  |
| PfxPassword  | Het wachtwoord voor het certificaat voor ondertekening van programmacode voor mobiele bedrijfsapparaten van Symantec. |
| PublisherId | De uitgevers-id van de onderneming. Als deze niet is opgegeven, wordt het veld Onderwerp van Symantec Enterprise-certificaat voor ondertekening van mobiele code gebruikt. |
| SdkPath | Het pad naar de hoofdmap van de Windows-SDK voor Windows 10. Dit argument is optioneel en wordt standaard ingesteld op ${env:ProgramFiles(x86)} \Windows Kits\10.  |

Zodra het script is uitgevoerd, wordt de ondertekende versie van de Windows 10-bedrijfsportal-app uitgevoerd. Vervolgens kunt u de ondertekende versie van de app toewijzen als een Line-Of-Business-app (LOB) via Intune. De huidige toegewezen versies worden bijgewerkt naar deze nieuwe app.  

## <a name="next-steps"></a>Volgende stappen

- [Apps aan groepen toewijzen](apps-deploy.md)

