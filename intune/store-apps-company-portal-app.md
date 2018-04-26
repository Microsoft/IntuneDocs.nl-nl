---
title: De Windows 10-bedrijfsportal-app handmatig toevoegen
titleSuffix: Microsoft Intune
description: Meer informatie over het handmatig toevoegen van de Windows 10-bedrijfsportal-app.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bfe1a2d3-f611-4dbb-adef-c0dff4d7b810
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f2c7e449e9931bccd5e736bd09c33e0b42c623e9
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="manually-add-the-windows-10-company-portal-app-using-microsoft-intune"></a>De Windows 10-bedrijfsportal-app handmatig toevoegen met Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Eindgebruikers kunnen de bedrijfsportal-app installeren vanuit Microsoft Store voor het beheren van apparaten en installeren van apps. Als uw bedrijf echter vereist dat u de bedrijfsportal-app toewijst, kunt u de Windows 10-bedrijfsportal-app handmatig rechtstreeks toewijzen vanuit Intune, ook als u Intune niet hebt geïntegreerd met Microsoft Store voor Bedrijven.

 > [!NOTE]
 > Voor deze optie is handmatige toewijzing van updates vereist voor elke app-update.

## <a name="configure-settings-to-show-offline-apps"></a>Instellingen configureren om apps offline weer te geven
1. Ga naar de [Microsoft Store voor Bedrijven](https://www.microsoft.com/business-store) en zorg ervoor dat u bent aangemeld met uw beheerdersaccount.
2. Selecteer het tabblad **Beheren** boven in het venster.
3. Selecteer **Instellingen** in de navigatiekolom links.
4. Stel **Offline apps weergeven** in de sectie **Winkelervaring** in op **Aan**. Offline gelicentieerde apps worden nu weergegeven in de Microsoft Store voor Bedrijven.

## <a name="download-the-offline-company-portal-app"></a>De offline bedrijfsportal-app downloaden
1. Zoek en selecteer de app **Bedrijfsportal**.
2. Stel het**Licentietype** in op **Offline**.
3. Klik op **De app downloaden** om de offline bedrijfsportal-app te verkrijgen en toe te voegen aan uw inventaris.
4. Klik op **Beheren** op de pagina **Bedrijfsportal** van de app.
5. Selecteer **Windows 10 alle apparaten** als **Platform**. Klik vervolgens op de juiste **Minimumversie**, **Architectuur** en de waarden voor het downloaden van de app-metagegevens**. 
6. Klik op **Downloaden** om het bestand op te slaan op uw lokale computer.

    ![Afbeelding van Windows 10 alle apparaten en architectuur X86-pakketdetails voor downloaden](./media/Win10CP-all-devices.png)

7. Download alle pakketten onder "Vereiste frameworks". Dit moet worden uitgevoerd voor x86-, x64- en ARM-architecturen - in totaal 12 pakketten.
8. Voordat u de bedrijfsportal-app uploadt naar Intune, maakt u een map (bijvoorbeeld C:&#92;Company Portal) waarin de pakketten als volgt zijn gestructureerd:
   - Plaats het bedrijfsportalpakket in C:\Bedrijfsportal. Maak op deze locatie tevens een submap Afhankelijkheden.  

     ![Afbeelding van de map Afhankelijkheden waarin het APPXBUN-bestand is opgeslagen](./media/Win10CP-Dependencies-save.png)

   - Plaats de afhankelijkheidspakketten in de map *Afhankelijkheden*. 

     > [!NOTE]
     > Als de afhankelijkheden niet in de juiste indeling worden geplaatst, worden de bestanden niet herkend door Intune en kunnen ze niet worden geüpload tijdens de pakket-upload. Het uploaden mislukt en geeft een fout weer.

9. Keer terug naar Microsoft Intune in Azure Portal.
10. Upload de Bedrijfsportal-app als een nieuwe app. Wijs deze als vereiste app toe aan de gewenste set doelgebruikers.  

Zie [Deploying an appxbundle with dependencies via Microsoft Intune MDM](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) (Een appxbundle met afhankelijkheden implementeren via Microsoft Intune MDM) voor meer informatie over hoe Intune afhankelijkheden voor universele apps verwerkt.  

## <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Hoe kan ik de Bedrijfsportal op de apparaten van mijn gebruikers bijwerken als hierop al de oudere apps uit de Store zijn geïnstalleerd?
Als uw gebruikers de Windows 8.1- of Windows Phone 8.1-bedrijfsportal-apps al hebben geïnstalleerd vanuit de Store, moeten deze automatisch worden bijgewerkt naar de nieuwe versie, zonder dat hiervoor actie door u of uw gebruikers is vereist. Als de update niet wordt uitgevoerd, vraagt u uw gebruikers om te controleren of automatische updates voor Store-apps op hun apparaten is ingeschakeld.   

## <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Hoe ik een upgrade uitvoeren van mijn gesideloade Windows 8.1-bedrijfsportal-app naar de Windows 10-bedrijfsportal-app?
Het wordt aanbevolen de toewijzing voor de Windows 8.1-bedrijfsportal-app te verwijderen door de toewijzingsactie in te stellen op "Installatie ongedaan maken". Zodra deze instelling is geconfigureerd, kan de Windows 10-bedrijfsportal-app worden toegewezen via een van de bovenstaande opties.  

Als u de app moet sideloaden en de Windows 8.1-bedrijfsportal hebt toegewezen zonder deze te ondertekenen met het Symantec-certificaat, volgt u de stappen in de bovenstaande sectie Assign directly via Intune (Rechtstreeks toewijzen via Intune) om de upgrade te voltooien.

Als u de app moet sideloaden en de Windows 8.1-bedrijfsportal hebt ondertekend en toegewezen met het Symantec-certificaat voor ondertekening van programmacode, volgt u de stappen in de onderstaande sectie.  

## <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Hoe kan ik een upgrade uitvoeren van mijn ondertekende en gesideloade Windows Phone 8.1-bedrijfsportal-app of Windows 8.1-bedrijfsportal-app naar de Windows 10-bedrijfsportal-app?
Het wordt aanbevolen de bestaande toewijzing voor de Windows Phone 8.1-bedrijfsportal-app of de Windows 8.1-bedrijfsportal-app te verwijderen door de toewijzingsactie in te stellen op Installatie ongedaan maken. Zodra deze instelling is geconfigureerd, kan de Windows 10-bedrijfsportal-app normaal worden toegewezen.  

Anders moet de Windows 10-bedrijfsportal-app op de juiste manier worden bijgewerkt en ondertekend om ervoor te zorgen dat het upgradepad in acht wordt genomen.  

Als de Windows 10-bedrijfsportal-app op deze manier is ondertekend en toegewezen, moet u dit proces herhalen voor elke nieuwe app-update wanneer deze beschikbaar is in de Store. De app wordt niet automatisch bijgewerkt wanneer de Store wordt bijgewerkt.  

Het ondertekenen en toewijzen van de app gaat als volgt:

1. Download het ondertekeningsscript voor de Microsoft Intune Windows 10-bedrijfsportal-app van [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript).  Voor dit script moet de Windows SDK voor Windows 10 moet zijn geïnstalleerd op de hostcomputer. Ga naar [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296) om de Windows SDK voor Windows 10 te downloaden.
2. Download de Windows 10-bedrijfsportal-app vanuit Microsoft Store voor Bedrijven, zoals hierboven beschreven.  
3. Voer het script uit met de invoerparameters die zijn opgegeven in de koptekst van het script om de Windows-10-bedrijfsportal-app (hieronder uitgepakt) te ondertekenen. Afhankelijkheden hoeven niet in het script te worden doorgegeven. Deze zijn alleen vereist wanneer de app wordt geüpload naar de Intune-beheerconsole.

|       Parameter       |                                                                        Beschrijving                                                                        |
|-----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| InputWin10AppxBundle  |                                                  Het pad naar het bron-appxbundle-bestand                                                  |
| OutputWin10AppxBundle | Het uitvoerpad voor het ondertekende appxbundle-bestand.  Win81Appx Het pad naar het Windows 8.1- of Windows Phone 8.1-bedrijfsportalbestand (het APPX-bestand). |
|      PfxFilePath      |                                       Het pad naar het certificaat voor ondertekening van programmacode voor mobiele bedrijfsapparaten van Symantec (het PFX-bestand).                                        |
|      PfxPassword      |                                         Het wachtwoord voor het certificaat voor ondertekening van programmacode voor mobiele bedrijfsapparaten van Symantec.                                          |
|      PublisherId      |          De uitgevers-id van de onderneming. Als deze niet is opgegeven, wordt het veld Onderwerp van Symantec Enterprise-certificaat voor ondertekening van mobiele code gebruikt.           |
|        SdkPath        |     Het pad naar de hoofdmap van de Windows-SDK voor Windows 10. Dit argument is optioneel en wordt standaard ingesteld op ${env:ProgramFiles(x86)} \Windows Kits\10     |

Via het script wordt de ondertekende versie van de Windows 10-bedrijfsportal-app uitgevoerd wanneer het uitvoeren van de app is voltooid. Vervolgens kunt u de ondertekende versie van de app toewijzen als een LOB-app via Intune. De huidige toegewezen versies worden bijgewerkt naar deze nieuwe app.  

## <a name="next-steps"></a>Volgende stappen

- [Apps aan groepen toewijzen](apps-deploy.md)

