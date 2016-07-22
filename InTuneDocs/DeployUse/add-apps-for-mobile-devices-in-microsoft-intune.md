---
# required metadata

title: Apps toevoegen voor mobiele apparaten | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f5b1f1ae-f177-450a-9af9-936a02d052e3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Apps voor mobiele apparaten toevoegen in Microsoft Intune

Gebruik de informatie in dit onderwerp om te weten te komen hoe u apps aan Intune toevoegt voordat u ze implementeert.


> [!IMPORTANT]
> Met behulp van de informatie in dit onderwerp kunt u apps toevoegen die u wilt implementeren op ingeschreven apparaten en ingeschreven Windows-pc’s. Raadpleeg [Apps voor Windows-pc’s toevoegen aan Microsoft Intune](add-apps-for-windows-pcs-in-microsoft-intune.md) als u apps voor Windows-pc’s wilt toevoegen die u beheert met de Intune-clientsoftware..

## De app toevoegen
U gebruikt de uitgever van Intune-software om de eigenschappen van de app te configureren en om, indien van toepassing, de app te uploaden naar de cloudopslag. Volg daarvoor deze procedure:

1.  Klik in de [Microsoft Intune-beheerdersconsole](https://manage.microsoft.com) op **Apps** &gt; **Apps toevoegen** om de uitgever van Intune-software te starten.

    > [!TIP]
    > Mogelijk moet u uw gebruikersnaam en wachtwoord voor Intune invoeren voordat de uitgever wordt gestart.

2.  Op de pagina **Software-installatie** van de software-uitgever kiest u een van de volgende opties voor **Selecteren hoe deze software beschikbaar moet worden gesteld voor apparaten**:
    - **Software-installatieprogramma**, voor apps met de extensie **.msi** of **.exe**. Geef het volgende op:
        - **Het bestandstype voor het software-installatieprogramma selecteren**: dit geeft het type software aan dat u wilt implementeren. Als u bijvoorbeeld een iOS-app wilt installeren, kiest u **App-pakket voor iOS (&#42;.ipa-bestand)**.
        - **De locatie opgeven van de software-installatiebestanden**: geef de locatie van de installatiebestanden op of klik op **Bladeren** om de locatie in een lijst te selecteren.
        - **Aanvullende bestanden en submappen uit dezelfde map opnemen**: alleen voor het bestandstype voor **Windows Installer**.<br>Voor sommige software die gebruikmaakt van Windows Installer, zijn ondersteunende bestanden vereist die gewoonlijk in dezelfde map zijn opgeslagen als de installatiebestanden. Selecteer deze optie als u deze bestanden ook wilt implementeren.<br>Dit installatietype maakt gebruik van uw opslagruimte in de cloud.

  -   **Externe koppeling**, voor apps die u wilt maken door een koppeling op te geven naar een app store. Geef het volgende op:

        - **De URL opgeven**: geef de URL op van een van de volgende zaken:
            - De app store-URL naar app die u wilt installeren. Als u bijvoorbeeld de Microsoft-app Extern bureaublad voor Android wilt implementeren, geeft u **https://play.google.com/store/apps/details?id=com.microsoft.rdc.android** op. Zoek met een zoekprogramma de pagina van de app in de App Store om de URL van de app te vinden. Als u bijvoorbeeld de app Extern bureaublad zoekt, kunt u als zoekterm **Microsoft Extern bureaublad Android** gebruiken.
            - Een website. Intune implementeert een snelkoppelingspictogram naar de site op het apparaat (ook wel een webclip genoemd).
            - Een app op internet. Intune implementeert een snelkoppelingspictogram naar de app op het apparaat.
        - **Een beheerde browser vereisen om deze koppeling te openen (alleen Android en iOS)**: wanneer u een koppeling naar een website of webtoepassing implementeert voor gebruikers, kunnen ze deze alleen openen in de door Intune beheerder browser die op hun apparaat moet worden geïnstalleerd.<br>Voor meer informatie over de beheerde browser, gaat u naar [Internettoegang beheren met beheerde-browserbeleid met Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).<br>Dit installatietype maakt geen gebruik van uw opslagruimte in de cloud.

  -   **Beheerde iOS-app uit de App Store**: voor gratis apps uit de iTunes Store die u wilt beheren met MAM-beleid. Geef het volgende op:

        - **De URL opgeven**: voer voor de app die u wilt implementeren de URL naar de App Store in. Als u bijvoorbeeld de Microsoft-app Werkmappen wilt implementeren, geeft u **https://itunes.apple.com/us/app/work-folders/id950878067?mt=8** op.<br>Dit installatietype maakt geen gebruik van uw opslagruimte in de cloud.

        Als u bijvoorbeeld de Microsoft Word-app uit de iTunes Store wilt implementeren op apparaten, ziet de pagina er als volgt uit:
        
        ![Uitgever van Microsoft Intune-software](./media/publisher-for-mobile.png)

3.  Configureer op de pagina **Beschrijving van software** de volgende instellingen:

    > [!TIP]
    > Afhankelijk van het installatietype dat u gebruikt, zijn sommige van deze waarden mogelijk al automatisch ingevoerd of worden deze mogelijk niet weergegeven.

    - **Uitgever**: voer de naam van de uitgever of de app in.
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal zal worden weergegeven.<br>Zorg ervoor dat alle app-namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving**: voer een beschrijving in voor de app. Deze wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **URL voor informatie over de software**: alleen beschikbaar als u **Software-installatieprogramma** hebt geselecteerd. (optioneel) Voer de URL in van een website die informatie over deze app bevat. Deze URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: alleen beschikbaar als u **Software-installatieprogramma** hebt geselecteerd. (optioneel) Voer de URL in van een website die privacyinformatie over deze app bevat. Deze URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Categorie**: (optioneel) selecteer een van de ingebouwde app-categorieën. Hierdoor kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Geef deze app weer als aanbevolen app en markeer deze in de bedrijfsportal:** hiermee wordt de app duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Pictogram**: (optioneel) upload een pictogram dat aan de app wordt gekoppeld. Dit is het pictogram dat samen met de app wordt weergegeven wanneer gebruikers door de bedrijfsportal bladeren.

        In dit voorbeeld hebt u een beschrijving geconfigureerd voor de Microsoft Word-app voor iOS:

        ![Voorbeeld van een softwarebeschrijving](./media/ios-software-description.png)

4.  Op de pagina **Vereisten** selecteert u de vereisten waaraan moet worden voldaan voordat de app op een apparaat kan worden geïnstalleerd. Voor een app-pakket voor iOS kunt u de minimale iOS-versie selecteren die vereist is en aangeven dat het type apparaat een iPhone of een iPad moet zijn.

    > [!TIP]
    > De pagina **Vereisten** wordt niet voor alle typen apps weergegeven.

5.  Als u het bestandstype **Windows Installer** selecteert, worden aanvullende wizardpagina’s weergeven. Dit bestandstype wordt gebruikt wanneer u software implementeert op computers met Windows 10 of hoger die zijn ingeschreven bij Intune.

6.  Controleer op de pagina **Samenvatting** de informatie die u hebt opgegeven. Wanneer u klaar bent, klikt u op **Uploaden**.

7.  Klik op **Sluiten** om de bewerking te voltooien.

De app wordt weergegeven op het knooppunt **Apps** van de werkruimte **Apps**.


## Volgende stappen

Wanneer u een app hebt gemaakt, is de volgende stap deze te implementeren. Zie [Apps in Microsoft Intune implementeren](deploy-apps.md) voor meer informatie





<!--HONumber=May16_HO1-->


