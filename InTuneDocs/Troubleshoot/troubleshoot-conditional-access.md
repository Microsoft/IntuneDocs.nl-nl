---
title: Problemen met voorwaardelijke toegang oplossen | Microsoft Intune
description: Dit kunt u doen wanneer uw gebruikers geen toegang krijgen tot bedrijfsbronnen via de voorwaardelijke toegang van Intune.
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 433fc32c-ca9c-4bad-9616-852c72faf996
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c1e215320168c659d5f838355f6350111d6979b0
ms.openlocfilehash: 21ae91f0d2866b621d9353929bab6d41d95dc8cc


---

# Problemen met voorwaardelijke toegang oplossen

In dit onderwerp wordt beschreven wat u moet doen wanneer uw gebruikers geen toegang krijgen tot resources met de voorwaardelijke toegang van Intune. 

### De basis voor succesvol gebruik van voorwaardelijke toegang

Als u met voorwaardelijke toegang aan de slag wilt, moet aan de volgende voorwaarden worden voldaan:

-   Het apparaat moet worden beheerd door Intune.
-   De gebruiker moet zijn geregistreerd bij Azure Active Directory (ADD)
-   Het apparaat moet voldoen aan het nalevingsbeleid dat u hebt geconfigureerd in Intune. 
-   EAS moet worden geactiveerd op het apparaat als de gebruiker e-mail ophaalt via de systeemeigen e-mailclient van het apparaat in plaats van Outlook.

De voorwaarden die voor elk apparaat gelden, zijn terug te vinden in Azure Management Portal en in het inventarisrapport van het apparaat.





Normaal gesproken ontvangt een gebruiker die e-mails probeert te openen of die SharePoint opent de vraag om zich in te schrijven. Als de gebruiker zich besluit in te schrijven, wordt deze naar de bedrijfsportal geleid. Hieronder volgen mogelijke oorzaken van dit gedrag, en aanbevolen oplossingen:

## Moderne verificatiescenario's

### Problemen bij het inschrijven

 -  Het apparaat is niet ingeschreven, dus het probleem kan worden opgelost door het apparaat in te schrijven.
 -  De gebruiker heeft het apparaat ingeschreven, maar het toevoegen aan de werkplek is mislukt. De gebruiker moet de inschrijving via de bedrijfsportal bijwerken. 
 
### Problemen met naleving

 -  Het apparaat is niet compatibel met het Intune-beleid. Veelvoorkomende problemen zijn problemen met de versleutelings- en wachtwoordvereisten. De gebruiker wordt omgeleid naar de bedrijfsportal, waar deze het apparaat zodanig kan configureren dat er aan de voorwaarden wordt voldaan.
 -  Als gebruikers op een iOS-apparaat een bestaand, zelfgemaakt e-mailprofiel gebruiken, wordt het implementeren van een compatibel profiel (gemaakt door de Intune-beheerder) geblokkeerd. Dit is een veelvoorkomend probleem omdat iOS-gebruikers vaak zelf een e-mailprofiel maken en zich vervolgens inschrijven. In de bedrijfsportal ziet de gebruiker dat deze niet voldoet aan de voorwaarden wegens het handmatig geconfigureerde e-mailprofiel. De gebruiker wordt gevraagd dat profiel te verwijderen. Het e-mailprofiel moet worden verwijderd zodat het Intune-profiel kan worden geïmplementeerd. Als u het probleem wilt voorkomen, vertelt u gebruikers om zich in te schrijven zonder een e-mailprofiel te installeren zodat Intune het profiel kan implementeren.  
 -  Het kan even duren om de nalevingsinformatie te registreren voor een apparaat. Wacht een paar minuten en probeer het opnieuw.

### Beleidsproblemen

Wanneer u een nalevingsbeleid maakt en dit koppelt aan een e-mailbeleid, moeten beide soorten beleid voor dezelfde gebruiker worden geïmplementeerd. Ga dus zorgvuldig te werk tijdens het plannen van welk beleid voor welke groepen moet worden geïmplementeerd. Gebruikers waarvoor slechts één beleid is toegepast, zullen merken dat hun apparaat niet compatibel is.


## Exchange Active Sync-scenario’s


- Op een Android-apparaat dat is ingeschreven en voldoet, kan alsnog een quarantainemelding worden weergegeven wanneer een gebruiker probeert bedrijfsresources te openen. Voordat de gebruiker de koppeling **Begin** selecteert, moet deze controleren of de bedrijfsportal gesloten was tijdens het openen van de resources. De gebruikers moeten de bedrijfsportal sluiten, opnieuw proberen de resources te openen en vervolgens de koppeling **Begin** selecteren.

- Op een apparaat dat buiten gebruik is gesteld, kan mogelijk nog enkele uren toegang worden verkregen. Dit komt doordat Exchange de toegangsrechten gedurende zes uur in het cachegeheugen opslaat. Overweeg andere manieren om gegevens op buiten gebruik gestelde apparaten te beveiligen in dit scenario.
- Mogelijk probleem, kan de EASID niet patchen voor AAD. Een veelvoorkomende oorzaak van dit probleem is beperking, dus wacht een paar minuten en probeer het opnieuw. 

## OWA-postvaklogboeken verzamelen

Als uw Exchange-verbindingsproblemen zich blijven voordoen nadat u de problemen met uw implementatie hebt opgelost, verzamelt u de OWA-postvaklogboeken voordat u contact opneemt met Microsoft Ondersteuning, zoals wordt beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).

1. Meld u aan via OWA en kies het instellingensymbool (tandwielpictogram) naast uw naam in de rechterbovenhoek. 
2. Kies **Opties**
3. Kies **Telefoon** (er staat mogelijk **Mobiele apparaten**) in de kolom aan de linkerkant.
4. Kies in het menu bovenaan de optie **Mobiele apparaten**. 
5. Kies uw apparaat in de lijst en kies vervolgens **Vastleggen starten**. 
6. Wanneer u een vraag wordt gesteld, kiest u **Ja** in het pop-updialoogvenster. 
7. Voer de actie uit waardoor het probleem is veroorzaakt, zodat u het probleem opnieuw produceert. 
8. Wacht 1-2 minuten en ga dan terug naar de telefoonlijst in OWA (zorg ervoor dat uw telefoon is geselecteerd in de lijst). Kies **Logboek ophalen** in het menu bovenaan. 
9. U hebt nu een e-mailbericht van uzelf ontvangen met een bijlage. Wanneer u een ondersteuningsticket opent, kopieert u de inhoud van de e-mail en stuurt u deze naar Microsoft Ondersteuning.


### Volgende stappen
Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).



<!--HONumber=Jul16_HO3-->


