---
title: Bedrijfsportal-appberichten die gebruikers kunnen zien | Microsoft Intune
description: Bedrijfsportal-appberichten die Intune-eindgebruikers kunnen zien
keywords: 
author: staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 60ee39a7eeeb9068a7350ec87f60e7148ccb7826
ms.openlocfilehash: 7cd6c67d875f9d8fcc1e6774b84afc2c526511a9


---

# Eindgebruikers helpen bij het begrijpen van berichten van de bedrijfsportal-app

De volgende informatie is alleen van toepassing op apparaten met Android 6.0 en hoger. Tijdens de registratie van apparaten zien eindgebruikers twee berichten die tijdens het registratieproces verschijnen:

- De bedrijfsportal toestaan telefoongesprekken uit te voeren en beheren?
- De bedrijfsportal toegang verlenen tot foto's, media en bestanden op uw apparaat?

Zie de volgende paragrafen voor meer informatie over deze berichten en voor informatie die u hierover aan uw eindgebruikers kunt verstrekken.

## De bedrijfsportal toestaan telefoongesprekken uit te voeren en beheren?

### De berichttekst en waar deze wordt weergegeven
De berichttekst is **De bedrijfsportal toestaan om telefoongesprekken uit te voeren en te beheren?** en deze wordt weergegeven wanneer gebruikers zich voor het eerst bij de bedrijfsportal-app aanmelden om hun apparaat te registreren.

### Wat het bericht betekent
In het bericht wordt aan gebruikers gevraagd toe te staan dat het telefoonnummer en het IMEI-nummer van het apparaat naar de Intune-service worden verzonden en in de beheerconsole op de pagina Hardware worden weergegeven.

> [!NOTE]
> **De bedrijfsportal-app voert nooit telefoongesprekken uit en beheert deze niet.** De berichttekst wordt beheerd door Google en kan niet worden gewijzigd.

Als u de pagina **Hardware** wilt weergeven, gaat u naar **Groepen** > **Alle mobiele apparaten** > **Apparaten**. Selecteer het apparaat van de gebruiker en ga naar **Eigenschappen weergeven** > **Hardware**.

### Wat er gebeurt als gebruikers toegang toestaan of weigeren
Als gebruikers toegang toestaan, worden het telefoonnummer en het IMEI-nummer van het apparaat weergegeven op de pagina Hardware in de beheerconsole.

Als gebruikers toegang weigeren, kunnen gebruikers de bedrijfsportal-app blijven gebruiken en hun apparaten registreren, maar het telefoonnummer en het IMEI-nummer van het apparaat van de gebruikers zijn leeg op de pagina Hardware in de beheerconsole. De tweede keer dat gebruikers zich aanmelden bij de bedrijfsportal-app nadat ze toegang hebben geweigerd, wordt in het bericht een selectievakje bij **Niet opnieuw vragen** weergegeven dat gebruikers kunnen inschakelen zodat het bericht nooit meer wordt weergegeven.

Als gebruikers toegang verlenen en deze later weer intrekken, wordt het bericht de volgende keer dat gebruikers zich bij de bedrijfsportal-app aanmelden, weergegeven na de registratie.</br></br>Als gebruikers later alsnog besluiten om toegang te verlenen, kunnen ze naar **Instellingen** > **Apps** > **Bedrijfsportal** > **Machtigingen** > **Telefoon** gaan en de machtiging instellen.

### Waar uw gebruikers meer informatie kunnen vinden
Stap 5 in [Uw Android-apparaat registreren bij Intune](/Intune/EndUser/enroll-your-device-in-intune-android)

## De bedrijfsportal toegang verlenen tot foto's, media en bestanden op uw apparaat?

### De berichttekst en waar deze wordt weergegeven
De berichttekst is **De bedrijfsportal toegang verlenen tot foto's, media en bestanden op uw apparaat?**, en deze wordt weergegeven wanneer gebruikers op **Gegevens verzenden** tikken om hun gegevenslogboeken te verzenden naar hun IT-beheerder.

### Wat het bericht betekent
In het bericht wordt gebruikers gevraagd om hun apparaat toe te staan gegevenslogboeken te schrijven naar de SD-geheugenkaart van het apparaat en toe te staan dat deze logboeken worden verzonden via een USB-kabel.   

> [!NOTE]
> **De bedrijfsportal-app gebruikt nooit foto's, media en bestanden van de gebruiker.** De berichttekst wordt beheerd door Google en kan niet worden gewijzigd.

### Wat er gebeurt als gebruikers toegang toestaan of weigeren
Als gebruikers toegang toestaan, worden de logboeken gekopieerd naar de SD-kaart.

Als gebruikers toegang weigeren, kunnen ze nog steeds gegevenslogboeken verzenden, maar de logboeken worden niet gekopieerd naar de SD-kaart van het apparaat.

De tweede keer dat gebruikers zich aanmelden bij de bedrijfsportal-app nadat ze toegang hebben geweigerd, wordt in het bericht een selectievakje bij **Niet opnieuw vragen** weergegeven dat gebruikers kunnen inschakelen zodat het bericht nooit meer wordt weergegeven. Als gebruikers toegang verlenen en deze later weer intrekken, wordt het bericht de volgende keer dat ze logboeken verzenden, weergegeven. Als gebruikers later alsnog besluiten om toegang te verlenen, kunnen ze naar **Instellingen** > **Apps** > **Bedrijfsportal** > **Machtigingen** > **Opslag** gaan en de machtiging instellen.

### Waar uw gebruikers meer informatie kunnen vinden
[Logboeken met diagnostische gegevens naar de IT-beheerder verzenden via e-mail](/Intune/EndUser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)


### Zie ook
[Wat u uw eindgebruikers vertelt over het gebruik van Intune](/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)



<!--HONumber=Jul16_HO4-->


