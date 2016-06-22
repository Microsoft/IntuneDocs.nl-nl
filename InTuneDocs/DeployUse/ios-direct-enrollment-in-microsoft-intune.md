---
# required metadata

title: Directe registratie voor iOS-apparaten | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: dagerrit
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# iOS-apparaten direct inschrijven met behulp van Apple Configurator
Intune ondersteunt de inschrijving van iOS-apparaten die bedrijfseigendom zijn, met behulp van het hulpprogramma [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) dat wordt uitgevoerd op een Mac-computer. Met dit proces wordt het apparaat niet teruggezet op de fabrieksinstellingen en wordt het apparaat met een vooraf gedefinieerd beleid ingeschreven. Deze methode is bedoeld voor apparaten waarop **Geen relatie met gebruiker** is ingesteld. Voor deze methode is vereist dat u met het iOS-apparaat een USB-verbinding met een Mac-computer maakt om bedrijfsinschrijving in te stellen. De bedrijfsportal-app wordt niet ondersteund voor direct ingeschreven apparaten. In deze richtlijnen wordt ervan uitgegaan dat u Apple Configurator 2.0 gebruikt op een Mac-computer.

1.  **Een profiel maken voor apparaten** Met een registratieprofiel voor apparaten worden de instellingen gedefinieerd die worden toegepast op apparaten. Als u dit nog niet hebt gedaan, maakt u een inschrijvingsprofiel voor iOS-apparaten die worden ingeschreven met Apple Configurator.

    #### Een profiel maken

    1.  Ga in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) naar **Beleid** &gt; **Inschrijving van bedrijfsapparaten** en kies vervolgens **Toevoegen...**.

        ![De pagina Inschrijvingsprofiel voor apparaten maken](../media/pol-sa-corp-enroll.png)

    2.  Geef details voor de apparaatprofielen op:

        -   **Naam**: naam van het inschrijvingsprofiel voor apparaten. Niet zichtbaar voor gebruikers.

        -   **Beschrijving**: beschrijving van het inschrijvingsprofiel voor apparaten. Niet zichtbaar voor gebruikers.

        -   **Gebruikersrelatie** : geeft aan hoe apparaten worden ingeschreven. Selecteer **Geen relatie met gebruiker**voor directe inschrijving.

        -   **Vooraf toegewezen apparatengroep**: alle apparaten waarvoor dit profiel wordt geïmplementeerd, behoren in eerste instantie tot deze groep. U kunt apparaten na de inschrijving opnieuw toewijzen.

    3.  Kies **Profiel opslaan** om het profiel toe te voegen.

5.  **Een profiel exporteren als .mobileconfig om het te implementeren op iOS-apparaten** Selecteer het apparaatprofiel dat u hebt gemaakt. Kies **Exporteren...** in de taakbalk. Kies **Profiel downloaden** en sla het gedownloade .mobileconfig-bestand op.

6.  **Het bestand overzetten** Kopieer het gedownloade .mobileconfig-bestand naar een Mac-computer.
    > [!NOTE]
    > De profiel-URL voor inschrijving is na het exporteren twee weken geldig. Na twee weken moet u een nieuwe profiel-URL voor inschrijving exporteren om iOS-apparaten te registreren met Configuratieassistent.
7.  **Het apparaat voorbereiden met Apple Configurator** iOS-apparaten zijn verbonden met de Mac-computer en geregistreerd voor beheer van mobiele apparaten.

    1.  Start **Apple Configurator 2.0** op een Mac-computer.

    2.  Verbind het iOS-apparaat met de Mac-computer met behulp van een USB-kabel. Sluit **Foto's**, **iTunes** en andere apps die voor het apparaat worden geopend wanneer het apparaat wordt gedetecteerd.

    3.  Klik in Apple Configurator één keer op het verbonden iOS-apparaat en selecteer vervolgens de knop **Toevoegen**. Opties die kunnen worden toegevoegd aan het apparaat, worden weergegeven in de vervolgkeuzelijst. Kies **Profielen**.

    4.  Gebruik de bestandskiezer om het .mobileconfig-bestand te selecteren dat u uit Intune hebt geëxporteerd. Kies vervolgens **Toevoegen**. Het profiel wordt toegevoegd aan het apparaat.  Als het apparaat **Niet onder supervisie** is, vereist de installatie acceptatie op het apparaat.

8.  **Het profiel installeren** U bent gereed voor de installatie van het profiel op het iOS-apparaat. Het apparaat moet de Configuratieassistent al hebben uitgevoerd en gereed zijn voor gebruik.  Als inschrijving app-implementaties omvat, moet op het apparaat een Apple-id zijn ingesteld, omdat de app-implementaties vereisen dat u met een Apple-id bent aangemeld voor de App Store.

    ###### Profielacceptatie voltooien voor iOS-apparaten die niet onder supervisie zijn

    1.  Ontgrendel het iOS-apparaat.

    2.  Tik in het dialoogvenster **Profiel installeren** voor **Beheerprofiel** op **Installeren**.

    3.  Geef zo nodig een **Wachtwoordcode** of **Apple-id** op.

    4.  Accepteer de **Waarschuwing** en tik op **Installeren**.

    5.  Accepteer de **Externe waarschuwing** en tik op **Vertrouwen**.

    6.  Wanneer in het vak **Profiel geïnstalleerd** wordt bevestigd dat het profiel is **Geïnstalleerd**, kiest u **Gereed**.

9. **Profiel verifiëren**
    Open op het iOS-apparaat **Instellingen**, ga naar **Algemeen** &gt; **Apparaatbeheer** &gt; **Beheerprofiel** &gt; en controleer of de profielinstallatie wordt vermeld. Controleer de geïnstalleerde apps en de beperkingen van het iOS-beleid. Het kan 10 minuten duren voordat beleidsbeperkingen en apps worden weergegeven op het apparaat.

10. **Apparaten distribueren** Het iOS-apparaat is nu geregistreerd bij Intune en wordt beheerd.


### Zie ook
[Voorbereidingen voor het inschrijven van apparaten](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=Jun16_HO3-->


