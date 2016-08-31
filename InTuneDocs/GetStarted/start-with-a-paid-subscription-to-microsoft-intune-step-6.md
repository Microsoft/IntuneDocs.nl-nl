---
title: Beleid maken en een app publiceren | Microsoft Intune
description: Uitleg over hoe u beleidsregels kunt maken en een voorbeeld van de app voor uw Intune-abonnement kunt publiceren
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6d1c7c670341692d4ea0c823e4a9a96746b83067
ms.openlocfilehash: da46c83d43f4ce4c5ae22b87638ad747a57b9e3f


---

# Beleid maken en een app publiceren
Intune-beleid biedt u instellingen waarmee u de beveiligingsinstellingen op mobiele apparaten kunt controleren, Windows Firewall- en Endpoint Protection-instellingen voor computers kunt onderhouden en toepassingen kunt implementeren. Meer informatie vindt u in [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](/Intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) en [Help Windows-pc's beveiligen met Endpoint Protection Help voor Microsoft Intune](/Intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).

U kunt twee typen app-installaties uitvoeren met Intune. De eerste is een **vereiste installatie**, waarbij de app automatisch wordt geïmplementeerd op beheerde computers. Het andere type is een **beschikbare installatie**, waarbij de app, of een koppeling naar de app, wordt geïmplementeerd in de Intune-bedrijfsportal, zodat gebruikers kunnen kiezen of ze deze willen installeren op hun computers of mobiele apparaten.

De volgende stappen helpen u bij het instellen van een configuratiebeleid voor mobiele apparaten, een firewallbeleid voor Windows-computers en de configuratie van Skype als een beschikbare installatie voor mobiele apparaten nadat deze zijn ingeschreven.

> [!TIP]
> Nadat u een nieuw beleid hebt toegevoegd en geïmplementeerd, geldt het basisbeleid voor alle gebruikers of apparaten in de groep waarop u het beleid hebt geïmplementeerd. U kunt de details van het beleid altijd bekijken en bewerken vanuit de werkruimte Beleid.


## Een configuratiebeleid voor mobiele apparaten maken en implementeren

1.  Open de [Intune-beheerconsole](https://manage.microsoft.com/).

2.  Klik in het linkerdeelvenster op het pictogram **Beleid**.

    ![beheerconsole-beleid-werkruimte](./media/policy.png)

3.  Klik in de lijst **Taken** op de pagina **Overzicht** op **Beleid toevoegen**.

4.  Vouw in de lijst met beleidsregels het platform uit waarvoor u een beleid wilt maken en selecteer **Algemene configuratie** > **Beleid met de aanbevolen instellingen maken en implementeren** > **Beleid maken**.

> [!NOTE]
> Er zijn geen aanbevolen instellingen voor het configuratiebeleid voor apparaten, omdat u uit veel opties kunt kiezen. U moet een aangepast configuratiebeleid voor het apparaat maken.


5.  Wanneer u wordt gevraagd **de groepen te selecteren waarvoor u dit beleid wilt implementeren**, kiest u een groep in de lijst met beschikbare groepen en kiest u vervolgens **Toevoegen** > **OK**.

Het beleid wordt weergegeven in de lijst met configuratiebeleidsregels en geïmplementeerd voor de groep **Intune--gebruikers**. Dubbelklik op het beleid om de instellingen weer te geven.

## De app Skype voor mobiele apparaten publiceren

1.  Klik op de [Intune-beheerconsole](https://manage.microsoft.com/) op het pictogram **Apps** en kies **Apps** > **App toevoegen**. Voer uw [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-referenties in als u hierom wordt gevraagd.

    ![beheerconsole-apps-werkruimte](./media/apps.png)

    > [!NOTE]
    > De eerste keer dat u de **Uitgever van Microsoft Intune-software** start, treedt er een korte vertraging op wanneer de toepassing wordt geïnstalleerd.

2.  Lees de beveiligingswaarschuwing en kies **Uitvoeren**.

3.  Kies op de pagina **Voordat u begint** de optie **Volgende**.

4.  Selecteer op de pagina **Setup van software** bij **Selecteer hoe deze software beschikbaar moet worden gesteld voor apparaten** de optie **Externe koppeling**.

5.  Geef in **Geef de URL op** de externe koppeling voor de software op en kies **Volgende**. Zorg ervoor dat u de URL laat beginnen met **http://**. Gebruik voor de app Skype de koppeling hieronder die overeenkomt met het platform van het mobiele apparaat dat u gebruikt:

    -   **iOS:**   [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:**  [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8 of Windows Phone 8.1:**  [http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  Typ op de pagina **Beschrijving van software** de informatie over de software die u voor gebruikers in de bedrijfsportal wilt weergeven en klik vervolgens op **Volgende**. De volgende instellingen zijn beschikbaar (in dit voorbeeld verwijzen we naar Skype):

    -   **Uitgever:** Voer de naam van de uitgever in, bijvoorbeeld 'Microsoft'

    -   **Naam:** Voer **Skype**

    -   **Beschrijving:** Voer een beschrijving voor de software in, zoals **app voor Skype-communicatie**

    -   **Categorie:** Selecteer de categorie die het beste past bij deze software, zoals **Samenwerking**

    -   **Geef deze app weer als aanbevolen app en markeer deze in de bedrijfsportal:** selecteer deze optie als u de app op mobiele apparaten duidelijk zichtbaar wilt maken in de bedrijfsportal.

    -   **Pictogram**: kies of u een pictogram wilt koppelen aan de software. De maximale grootte voor het optionele pictogram is 250 x 250 pixels en de aanbevolen grootte is 32 x 32 pixels.

7.  Controleer de software-informatie op de pagina **Samenvatting** en kies **Uploaden**. Kies **Sluiten** om de wizard af te sluiten.

8.  Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) de optie **Apps** > **Apps** > **Skype** > **Implementatie beheren**.

9. Selecteer op de pagina **Groepen selecteren** de optie **Intune-gebruikers** om de software te implementeren voor die gebruikersgroep en kies **Toevoegen** > **Volgende**.

10. Selecteer **Beschikbare installatie** in de kolom **Goedkeuring** op de pagina **Implementatieactie** voor de groep.

11. Kies **Voltooien**.

De Skype-app kan nu vanuit de bedrijfsportal op mobiele apparaten worden geïnstalleerd, maar u moet eerst [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-software installeren op computers en mobiele apparaten.


### Volgende stappen
Gefeliciteerd. U hebt zojuist stap 6 van de *Snelstartgids voor Intune* voltooid.

>[!div class="step-by-step"]

>[&larr; **Gebruikers en apparaten organiseren**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Bedrijfsportal aanpassen** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  



<!--HONumber=Aug16_HO4-->


