---
title: Apps voor Windows-pc's met de Intune-softwareclient toevoegen
titlesuffix: Microsoft Intune
description: Gebruik de informatie in dit onderwerp om te weten te komen hoe u apps voor Windows-pc’s aan Intune toevoegt voordat u ze implementeert.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 08/29/2018
ms.topic: archived
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: bc8c8be9-7f4f-4891-9224-55fc40703f0b
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7aaeabeebc636e58eac2058b0f482efef34878f0
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57460926"
---
# <a name="add-apps-for-windows-pcs-that-run-the-intune-software-client"></a>Apps voor Windows-pc's met de Intune-softwareclient toevoegen

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Gebruik de informatie in dit onderwerp om te weten te komen hoe u apps aan Intune toevoegt voordat u ze implementeert.

> [!IMPORTANT]
> De informatie in dit onderwerp kan u helpen bij het toevoegen van apps voor Windows-pc's die u met de Intune-clientsoftware beheert. Raadpleeg [Apps toevoegen aan Microsoft Intune](apps-add.md) als u apps wilt toevoegen op geregistreerde Windows-pc's en andere mobiele apparaten.

Om apps op pc's te installeren, moeten deze geschikt zijn voor achtergrondinstallatie, zonder tussenkomst van de gebruiker. Als dit niet het geval is, mislukt de installatie.

## <a name="additional-security-settings-for-windows-installer"></a>Aanvullende beveiligingsinstellingen voor Windows Installer
U kunt gebruikers toestemming geven om app-installaties te beheren. Als u deze functie is ingeschakeld, kunnen installaties worden toegestaan die anders worden gestopt vanwege een beveiligingsfout. U kunt het Windows-installatieprogramma de opdracht geven om verhoogde bevoegdheden te gebruiken wanneer een programma op een systeem wordt geïnstalleerd. Verder kunt u ingeschakelde items van Windows-gegevensbescherming laten indexeren en de metagegevens voor de items laten opslaan op een niet-versleutelde locatie. Als het beleid is uitgeschakeld, worden de items met WIP-beveiliging niet geïndexeerd en worden ze niet weergegeven in de resultaten in Cortana of Verkenner. De functionaliteit voor deze opties is standaard uitgeschakeld. 

## <a name="add-the-app"></a>De app toevoegen
U gebruikt de uitgever van Intune-software om de eigenschappen van de app te configureren en om de app te uploaden naar de cloudopslag. Volg daarvoor deze procedure:

1. Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Apps** &gt; **Apps toevoegen** om Uitgever van Intune-software te starten.

   > [!TIP]
   > Mogelijk moet u uw gebruikersnaam en wachtwoord voor Intune invoeren voordat de uitgever wordt gestart.

2. Op de pagina **Software-installatie** van de uitgever kiest u onder **Selecteren hoe deze software beschikbaar moet worden gesteld voor apparaten** de optie **Software-installatieprogramma** en geeft u het volgende op:

   - **Selecteer het bestandstype voor het software-installatieprogramma**. Dit geeft het type software aan dat u wilt implementeren. Kies voor een Windows-pc de optie **Windows Installer**.
   - **Geef de locatie op van de software-installatiebestanden**. Geef de locatie op van de installatiebestanden of kies **Bladeren** om de locatie in een lijst te selecteren.
   - **Neem aanvullende bestanden en submappen op in dezelfde map**. Sommige software die gebruikmaakt van Windows Installer vereist ondersteunende bestanden. Deze moeten zich in dezelfde map bevinden als het installatiebestand. Selecteer deze optie als u deze ondersteunende bestanden ook wilt implementeren.

   Als u bijvoorbeeld een app met de naam Application.msi wilt publiceren naar Intune, komt de pagina er als volgt uit te zien: ![Software-installatiepagina van de uitgever](media/publisher-for-pc.png)

   Dit installatietype maakt gebruik van uw opslagruimte in de cloud.

3. Configureer op de pagina **Beschrijving van software** de volgende instellingen.

   > [!NOTE]
   > Afhankelijk van het installatiebestand dat u gebruikt, zijn sommige van deze waarden mogelijk al automatisch ingevoerd of worden deze mogelijk niet weergegeven.

   - **Uitgever**. Voer de naam van de uitgever van de app in.
   - **Naam**. Voer de naam van de app in zoals deze in de bedrijfsportal zal worden weergegeven.<br />Zorg ervoor dat alle app-namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
   - **Beschrijving**. Voer een beschrijving in voor de app. Deze wordt weergegeven voor gebruikers in de bedrijfsportal.
   - **URL voor informatie over de software** (optioneel). Voer de URL in van een website die informatie over deze app bevat. Deze URL wordt weergegeven voor gebruikers in de bedrijfsportal.
   - **Privacy-URL** (optioneel). Voer de URL in van een website die privacyinformatie over deze app bevat. Deze URL wordt weergegeven voor gebruikers in de bedrijfsportal.
   - **Categorie** (optioneel). Selecteer een van de ingebouwde app-categorieën. Hierdoor kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
   - **Pictogram** (optioneel). Upload een pictogram dat aan de app wordt gekoppeld. Dit is het pictogram dat samen met de app wordt weergegeven wanneer gebruikers door de bedrijfsportal bladeren.

4. Op de pagina **Vereisten** selecteert u de vereisten waaraan moet worden voldaan voordat de app kan worden geïnstalleerd. U kunt kiezen uit:

   - **Architectuur**. Selecteer of deze app kan worden geïnstalleerd op een 32-bits of 64-bits besturingssysteem, of op beide.
   - **Besturingssysteem**. Selecteer de minimumversie van het besturingssysteem waarop deze app kan worden geïnstalleerd.

5. Op de pagina **Detectieregels** kunt u regels configureren om te detecteren of de app die u configureert al op een pc is geïnstalleerd. Of u kunt de standaarddetectieregels gebruiken als u automatisch alle eerder geïnstalleerde versies van de app wilt overschrijven. Deze optie is voor Windows Installer (alleen .exe-bestanden).

   U kunt de volgende regels configureren:
   - **Bestand bestaat al**. Geef het pad op naar het bestand dat u wilt detecteren. U kunt zoeken onder **%ProgramFiles%** (waarmee wordt gezocht binnen **Programmabestanden**\&lt;path&gt; en **Programmabestanden (x86)**\&lt;path&gt;) op de computer of **%SystemDrive%** (waarmee wordt gezocht binnen het basisstation van de pc, meestal C:).
   - **MSI-productcode bestaat al**. Kies **Bladeren** om het Windows Installer-bestand (.msi) te kiezen dat u wilt detecteren.
   - <strong>Registersleutel bestaat al</strong>. Geef een registersleutel op die begint met <strong>HKEY_LOCAL_MACHINE\</strong>. Er wordt gezocht binnen zowel 32-bits als 64-bits registerpaden. Als de door u opgegeven sleutel in één van beide locaties bestaat, wordt aan de detectieregel voldaan.

   Als de app voldoet aan één van de regels die u hebt geconfigureerd, wordt deze niet geïnstalleerd.

6. Alleen voor het bestandstype **Windows Installer** (.msi en .exe): op de pagina **Opdrachtregelargumenten** kiest u of u optionele opdrachtregelargumenten wilt opgeven voor het installatieprogramma.
   De volgende parameters worden automatisch toegevoegd door Intune:
   - Voor .exe-bestanden wordt **/install** toegevoegd.
   - Voor .msi-bestanden wordt **/quiet** toegevoegd.
   Houd er rekening mee dat deze opties alleen werken als de maker van het app-pakket deze functionaliteit heeft ingeschakeld.

7. Alleen voor het bestandstype **Windows Installer** (alleen .exe): op de pagina **Retourcodes** kunt u nieuwe foutcodes toevoegen die door Intune worden geïnterpreteerd wanneer de app wordt geïnstalleerd op een beheerde Windows-pc.

   Standaard worden door Intune retourcodes volgens de industriestandaard gebruikt om te melden dat de installatie van een app-pakket is mislukt of geslaagd: **0** (Geslaagd) of **3010** (Geslaagd en opnieuw opgestart). U kunt ook uw eigen retourcodes aan deze lijst toevoegen. Als u een lijst met retourcodes opgeeft en de installatie van de app een code retourneert die niet in de lijst voorkomt, wordt dit geïnterpreteerd als een fout.

8. Controleer op de pagina **Samenvatting** de informatie die u hebt opgegeven. Wanneer u klaar bent, kiest u **Uploaden**.

9. Kies **Sluiten** om de bewerking te voltooien.

De app wordt weergegeven op het knooppunt **Apps** van de werkruimte **Apps**.

## <a name="next-steps"></a>Volgende stappen

Nadat u een app hebt gemaakt, is de volgende stap om deze te implementeren. Zie [Apps aan groepen toewijzen met Microsoft Intune](apps-deploy.md) voor meer informatie.

Raadpleeg het blogbericht [Support Tip: Best Practices for Intune Software Distribution to PC’s](https://blogs.technet.microsoft.com/intunesupport/2016/06/13/support-tip-best-practices-for-intune-software-distribution-to-pcs/) als u meer informatie wilt over tips en trucs voor het implementeren van software op Windows-pc's.
