---
# required metadata

title: Beleid maken en een app publiceren voor gebruikers van de evaluatieversie | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c3a17884-442a-44f5-bc81-4589e823f65e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Beleid maken en een app publiceren voor gebruikers van de evaluatieversie
Intune-beleid biedt u instellingen waarmee u de beveiligingsinstellingen op mobiele apparaten kunt controleren, Windows Firewall- en Endpoint Protection-instellingen voor computers kunt onderhouden en toepassingen kunt implementeren. Als u van plan bent om Intune na de evaluatie te gebruiken voor apparaten die u configureert voor gebruik in productieomgevingen, is het absoluut essentieel dat u de instructies volgt in [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) en [Help Windows-pc's beveiligen met Endpoint Protection Help voor Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)..

U kunt twee typen app-installaties uitvoeren met Intune. De eerste is een **vereiste installatie**, waarbij de app automatisch wordt geïmplementeerd op beheerde computers. Het andere type is een **beschikbare installatie**, waarbij de app, of een koppeling naar de app, wordt geïmplementeerd in de Intune-bedrijfsportal, zodat gebruikers kunnen kiezen of ze deze willen installeren op hun computers of mobiele apparaten.

Voordat u met Intune apps implementeert, moet u ervoor zorgen dat u de juiste licenties hebt om de app te publiceren, distribueren en gebruiken. In de werkruimte **Licenties** kunt u informatie beheren over licentieovereenkomsten voor apps en software die zijn aangeschaft via Microsoft-volumelicentieovereenkomsten, en voor Microsoft- en niet-Microsoft-apps die op een andere manier zijn gekocht. Vervolgens kunt u licentierapporten maken waarin gebruiksinformatie over beheerde licenties staat voor het hele bedrijf, zodat u op de hoogte kunt blijven van de gebruiksactiviteiten van licenties.

In deze stappen stelt u een configuratiebeleid voor mobiele apparaten in en configureert u een firewallbeleid voor Windows-computers. Bovendien configureert u Skype als een beschikbare installatie voor mobiele apparaten nadat deze zijn geregistreerd. Nadat u een nieuw beleid hebt toegevoegd en geïmplementeerd, geldt het basisbeleid voor alle gebruikers of apparaten in de groep waarop u het beleid hebt geïmplementeerd. U kunt de details van het beleid altijd bekijken en bewerken vanuit de werkruimte **Beleid** in de beheerconsole.

## Een configuratiebeleid voor mobiele apparaten maken en implementeren

1.  Open de [Intune-beheerconsole](https://manage.microsoft.com/)..

2.  Klik in het linkerdeelvenster op het pictogram **Beleid**.

3.  Klik in de lijst **Taken** op de pagina **Overzicht** op **Beleid toevoegen**..

4.  Vouw in de lijst met beleidsregels het platform uit waarvoor u beleid wilt maken, selecteer **Algemene configuratie**, kies **Een beleid maken en implementeren met de aanbevolen instellingen** en kies vervolgens **Beleid maken**..

5.  Als u wordt gevraagd om **de groepen te selecteren waarvoor u dit beleid wilt implementeren**, selecteert u in de lijst de optie **Mijn proefgebruikers** en kiest u **Toevoegen** &gt; **OK**..

Het beleid wordt weergegeven in de lijst met configuratiebeleidsregels en is geïmplementeerd voor de groep **Mijn proefgebruikers** . Dubbelklik op het beleid om de instellingen weer te geven.

## De app Skype voor mobiele apparaten publiceren

1.  Klik in de [Intune-beheerconsole](https://manage.microsoft.com/) op het **Apps**-pictogram en kies vervolgens **Apps** &gt; **App toevoegen**. Voer uw Intune-referenties in als u hierom wordt gevraagd.

    > [!NOTE]
    > De eerste keer dat u de **Uitgever van Microsoft Intune-software** start, treedt er een korte vertraging op wanneer de toepassing wordt geïnstalleerd.

2.  Bekijk de beveiligingswaarschuwing en kies **Uitvoeren**..

3.  Kies op de pagina **Voordat u begint** de optie **Volgende**..

4.  Selecteer **Externe koppeling** onder **Selecteren hoe deze software beschikbaar moet worden gesteld voor apparaten** op de pagina **Setup van software**..

5.  Geef onder **Geef de URL op** de externe koppeling voor de software op en klik vervolgens op **Volgende**. Zorg ervoor dat de URL begint met **https://**. Gebruik voor de app Skype de koppeling hieronder die overeenkomt met het platform van het mobiele apparaat dat u gebruikt:

    -   **iOS:** [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)

    -   **Android:** [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)

    -   **Windows Phone 8 of Windows Phone 8.1:** [http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/en-us/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)

6.  Typ op de pagina **Beschrijving van software** de informatie over de software die u voor gebruikers in de bedrijfsportal wilt weergeven en klik vervolgens op **Volgende**. De volgende instellingen zijn beschikbaar (in dit voorbeeld verwijzen we naar Skype):

    -   **Uitgever:** voer de naam van de uitgever in, bijvoorbeeld **Microsoft**

    -   **Naam:** Voer **Skype**

    -   **Beschrijving:** Voer een beschrijving voor de software in, zoals **app voor Skype-communicatie**

    -   **Categorie:** Selecteer de categorie die het beste past bij deze software, zoals **Samenwerking**

    -   **Geef deze app weer als aanbevolen app en markeer deze in de bedrijfsportal:** selecteer deze optie als u de app op mobiele apparaten duidelijk zichtbaar wilt maken in de bedrijfsportal.

    -   **Pictogram:**  (Optioneel) Kies of u een pictogram wilt koppelen aan de software. De maximale pictogramgrootte is 250 x 250 pixels, maar de aanbevolen pictogramgrootte is 32 x 32 pixels.

7.  Controleer op de pagina **Samenvatting** de informatie over de software en kies vervolgens **Uploaden**. Kies **Sluiten** om de wizard af te sluiten.

8.  Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) de optie **Apps** &gt; **Apps** &gt; **Skype** &gt; **Implementatie beheren**..

9. Selecteer op de pagina **Groepen selecteren** de optie **Mijn proefgebruikers** om de software te implementeren voor die gebruikersgroep en klik vervolgens op **Toevoegen** &gt; **Volgende**..

10. Selecteer **Beschikbare installatie** in de kolom **Goedkeuring** op de pagina **Implementatieactie** voor de groep.

11. Kies **Voltooien**..

De app Skype is nu vanuit de bedrijfsportal beschikbaar voor installatie op mobiele apparaten, maar u moet eerst Intune-software installeren op pc’s en mobiele apparaten.

### Volgende stappen
Gefeliciteerd! U hebt zojuist stap 4 van de procedure voor de *Microsoft Intune-evaluatie* voltooid.

>[!div class="step-by-step"]

>[&larr; **Groepen maken**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)     [**Apparaten inschrijven** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-5.md)  


<!--HONumber=May16_HO1-->


