---
title: Directe registratie voor iOS-apparaten | Microsoft Intune
description: 
keywords: 
<<<<<<< HEAD
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
||||||| merged common ancestors
author: NathBarn
manager: arob98
ms.date: 07/19/2016
=======
author: staciebarker
ms.author: stabar
manager: arob98
ms.date: 07/19/2016
>>>>>>> 36752dab280937bd95c2ae9719aa3b406dcd9321
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
<<<<<<< HEAD
ms.sourcegitcommit: 1b942c7e09e59de59e3e406b84a21a712c0e973a
ms.openlocfilehash: 8fea0f7f87972bc643bbb20348095e05f701287e
||||||| merged common ancestors
ms.sourcegitcommit: aabe68a3621a02b8f3142ab3f593190cc23053dd
ms.openlocfilehash: 17836bc826bc89e3f041f7b369be09c1cce9ea4f
=======
ms.sourcegitcommit: 52069f551b73ee938818c30de664e93d1775a061
ms.openlocfilehash: 9526ac2eb902198597ba811c5d957d69e1b991c6
>>>>>>> 36752dab280937bd95c2ae9719aa3b406dcd9321


---

<<<<<<< HEAD
# iOS-apparaten direct inschrijven met behulp van Apple Configurator
Intune ondersteunt de inschrijving van iOS-apparaten die bedrijfseigendom zijn, met behulp van het hulpprogramma [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) dat wordt uitgevoerd op een Mac-computer. Met dit proces wordt het apparaat niet teruggezet op de fabrieksinstellingen en wordt het apparaat met een vooraf gedefinieerd beleid ingeschreven. Deze methode is bedoeld voor apparaten waarop **Geen relatie met gebruiker** is ingesteld. Voor deze methode is vereist dat u met het iOS-apparaat een USB-verbinding met een Mac-computer maakt om bedrijfsinschrijving in te stellen. De bedrijfsportal-app wordt niet ondersteund voor direct ingeschreven apparaten. In deze richtlijnen wordt ervan uitgegaan dat u Apple Configurator 2.0 gebruikt op een Mac-computer.
||||||| merged common ancestors
# iOS-apparaten direct inschrijven met behulp van Apple Configurator
Intune ondersteunt de inschrijving van iOS-apparaten die bedrijfseigendom zijn, met behulp van het hulpprogramma [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) dat wordt uitgevoerd op een Mac-computer. Met dit proces wordt het apparaat niet teruggezet op de fabrieksinstellingen en wordt het apparaat met een vooraf gedefinieerd beleid geregistreerd. Deze methode is bedoeld voor apparaten waarop **Geen relatie met gebruiker** is ingesteld. Voor deze methode is vereist dat u met het iOS-apparaat een USB-verbinding met een Mac-computer maakt om bedrijfsinschrijving in te stellen. Wanneer u iOS-apparaten rechtstreeks inschrijft, kunt u een apparaat inschrijven zonder het serienummer van het apparaat in te voeren. U kunt ook het apparaat een naam geven voor identificatiedoeleinden voordat Intune de naam van het apparaat vastlegt tijdens de inschrijving. De bedrijfsportal-app wordt niet ondersteund voor direct ingeschreven apparaten. In deze richtlijnen wordt ervan uitgegaan dat u Apple Configurator 2.0 gebruikt op een Mac-computer.
=======
# <a name="directly-enroll-ios-devices-by-using-apple-configurator"></a>iOS-apparaten rechtstreeks inschrijven met behulp van Apple Configurator
Intune ondersteunt het inschrijven van iOS-apparaten die bedrijfseigendom zijn, met behulp van het hulpprogramma [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) op een Mac-computer. Met dit proces wordt het apparaat niet teruggezet op de fabrieksinstellingen en wordt het apparaat met een vooraf gedefinieerd beleid geregistreerd. Deze methode is bedoeld voor apparaten waarop **Geen relatie met gebruiker** is ingesteld. Voor deze methode is vereist dat u met het iOS-apparaat een USB-verbinding met een Mac-computer maakt om bedrijfsinschrijving in te stellen.
>>>>>>> 36752dab280937bd95c2ae9719aa3b406dcd9321

Wanneer u iOS-apparaten rechtstreeks inschrijft, kunt u een apparaat inschrijven zonder het serienummer van het apparaat in te voeren. U kunt ook het apparaat een naam geven voor identificatiedoeleinden voordat Intune de naam van het apparaat vastlegt tijdens de inschrijving. De bedrijfsportal-app wordt niet ondersteund voor rechtstreeks ingeschreven apparaten. In deze richtlijnen wordt ervan uitgegaan dat u Apple Configurator 2.0 gebruikt op een Mac-computer.

<<<<<<< HEAD
    #### Een profiel maken

    1.  Ga in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) naar **Beleid** &gt; **Inschrijving van bedrijfsapparaten** en kies vervolgens **Toevoegen...**.
||||||| merged common ancestors
    1.  Ga in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) naar **Beleid** &gt; **Inschrijving van bedrijfsapparaten** en kies vervolgens **Toevoegen...**.
=======
1.  Als u dat nog niet hebt gedaan, maakt u een inschrijvingsprofiel voor iOS-apparaten die worden ingeschreven met Apple Configurator. Met een inschrijvingsprofiel voor apparaten worden de instellingen gedefinieerd die worden toegepast op apparaten.

    1.  Ga in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) naar **Beleid** &gt; **Inschrijving van bedrijfsapparaten** en kies vervolgens **Toevoegen**.
>>>>>>> 36752dab280937bd95c2ae9719aa3b406dcd9321

        ![De pagina Inschrijvingsprofiel voor apparaten maken](../media/pol-sa-corp-enroll.png)

    2.  Geef details voor de apparaatprofielen op:

        -   **Naam**: naam van het inschrijvingsprofiel voor apparaten. Niet zichtbaar voor gebruikers.

        -   **Beschrijving**: beschrijving van het inschrijvingsprofiel voor apparaten. Niet zichtbaar voor gebruikers.

        -   **Gebruikersrelatie** : geeft aan hoe apparaten worden ingeschreven. Kies **Geen relatie met gebruiker**voor directe inschrijving.

        -   **Vooraf toegewezen apparatengroep**: alle apparaten met dit profiel behoren in eerste instantie tot deze groep. U kunt apparaten na de inschrijving opnieuw toewijzen.

        >[!Important]
        >Groepstoewijzingen worden verplaatst van Intune naar Azure Active Directory. [Meer informatie](http://go.microsoft.com/fwlink/?LinkID=787064)
    3.  Kies **Profiel opslaan** om het profiel toe te voegen.

5.  Een profiel exporteren .mobileconfig voor implementatie op iOS-apparaten:

    1.   Selecteer het apparaatprofiel dat u hebt gemaakt.

    2.   Kies **Exporteren** op de taakbalk.

    3.   Kies **Profiel downloaden** en sla het gedownloade .mobileconfig-bestand op.

6.  Zet het bestand over door het gedownloade .mobileconfig-bestand naar een Mac-computer te kopiëren.
    > [!NOTE]
    > De profiel-URL voor inschrijving is na het exporteren twee weken geldig. Na twee weken moet u een nieuwe profiel-URL voor inschrijving exporteren om iOS-apparaten te registreren met Configuratieassistent.

7.  Bereid het apparaat voor met Apple Configurator. iOS-apparaten zijn verbonden met de Mac-computer en ingeschreven voor beheer van mobiele apparaten.

    1.  Open **Apple Configurator 2.0** op een Mac-computer.

    2.  Verbind het iOS-apparaat met de Mac-computer met behulp van een USB-kabel. Sluit **Foto's**, **iTunes** en andere apps die voor het apparaat worden geopend wanneer het apparaat wordt gedetecteerd.

    3.  Kies in Apple Configurator het verbonden iOS-apparaat en kies vervolgens de knop **Toevoegen**. Opties die kunnen worden toegevoegd aan het apparaat, worden weergegeven in de vervolgkeuzelijst. Kies **Profielen**.

    4.  Gebruik de bestandskiezer om het .mobileconfig-bestand te selecteren dat u uit Intune hebt geëxporteerd. Kies vervolgens **Toevoegen**. Het profiel wordt toegevoegd aan het apparaat.  Als het apparaat **Niet onder supervisie** is, vereist de installatie acceptatie op het apparaat.

8.  U bent gereed voor installatie van het profiel op het iOS-apparaat. Het apparaat moet de Configuratieassistent al hebben uitgevoerd en gereed zijn voor gebruik. Als inschrijving app-implementaties omvat, moet op het apparaat een Apple-id zijn ingesteld, omdat de app-implementaties vereisen dat u met een Apple-id bent aangemeld voor de App Store.

    ###### Profielacceptatie voltooien voor iOS-apparaten die niet onder supervisie zijn

    1.  Ontgrendel het iOS-apparaat.

    2.  Kies in het dialoogvenster **Profiel installeren** voor **Beheerprofiel** de optie **Installeren**.

    3.  Geef zo nodig een **Wachtwoordcode** of **Apple-id** op.

    4.  Accepteer de **Waarschuwing** en kies **Installeren**.

    5.  Accepteer de **Externe waarschuwing** en kies **Vertrouwen**.

    6.  Wanneer in het vak **Profiel geïnstalleerd** wordt bevestigd dat het profiel is **Geïnstalleerd**, kiest u **Gereed**.

9.  Open **Instellingen** op het iOS-apparaat en ga naar **Algemeen** &gt; **Apparaatbeheer** &gt; **Beheerprofiel**. Controleer of de profielinstallatie wordt weergegeven en controleer vervolgens de iOS-beleidsbeperkingen en geïnstalleerde apps. Het kan 10 minuten duren voordat beleidsbeperkingen en apps worden weergegeven op het apparaat.

<<<<<<< HEAD
10. **Apparaten distribueren** Het iOS-apparaat is nu geregistreerd bij Intune en wordt beheerd.


### Zie ook
[Voorbereidingen voor het inschrijven van apparaten](get-ready-to-enroll-devices-in-microsoft-intune.md)
||||||| merged common ancestors
10. **Apparaten distribueren** Het iOS-apparaat is nu geregistreerd bij Intune en wordt beheerd.
=======
10.  Apparaten distribueren. Het iOS-apparaat is nu ingeschreven bij Intune en wordt beheerd.
>>>>>>> 36752dab280937bd95c2ae9719aa3b406dcd9321



<<<<<<< HEAD
<!--HONumber=Jul16_HO1-->
||||||| merged common ancestors
<!--HONumber=Aug16_HO1-->
=======
<!--HONumber=Oct16_HO3-->
>>>>>>> 36752dab280937bd95c2ae9719aa3b406dcd9321


