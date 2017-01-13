---
title: MAM-beleidsinstellingen voor iOS | Microsoft Docs
description: Dit onderwerp beschrijft de beleidsinstellingen voor het beheren van mobiele apps voor iOS-apparaten.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 673ff872-943c-4076-931c-0be90363aea9
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d80f548f0c1382e1bd024bd31078d2a4e6366656
ms.openlocfilehash: a2130fa76f66528f6e77c720bc93286e0d01aba2


---

#  <a name="ios-mobile-app-management-policy-settings"></a>Mobile Application Management-beleidsinstellingen voor iOS

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

De in dit onderwerp beschreven beleidsinstellingen kunnen worden [geconfigureerd](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) voor een Mobile App Management-beleid (MAM) op het tabblad **Instellingen** in de Azure-portal.

Er zijn twee soorten beleidsinstellingen, namelijk instellingen voor herlocatie van gegevens en instellingen voor toegang. In dit onderwerp verwijst de term _**Door beleid beheerde apps**_ naar apps die zijn geconfigureerd met MAM-beleid.

##  <a name="data-relocation-settings"></a>Instellingen voor herlocatie van gegevens

| Instelling | Gebruik | Standaardwaarde |
|------|------|------|
| **Back-ups van iTunes en iCloud voorkomen** | Kies **Ja** om te voorkomen dat deze app back-ups maakt van gegevens voor werk of school op iTunes en iCloud. Kies **Nee** om toe te staan dat deze app back-ups maakt van gegevens voor werk of school op iTunes en iCloud.| Ja |
| **App mag gegevens overdragen naar ander apps** | Geef aan welke apps gegevens uit deze app kunnen ontvangen: <ul><li> **Door beleid beheerde apps**: overdracht alleen toestaan naar andere door beleid beheerde apps.</li> <li>**Alle apps**: overdracht naar alle apps toestaan. </li> <li>**Geen**: geen gegevensoverdracht naar apps toestaan, met inbegrip van andere door beleid beheerde apps.</li></ul> Als u deze optie daarnaast instelt op **Door beleid beheerde apps** of **Geen**, wordt de iOS 9-functie waarmee Spotlight Search naar gegevens in apps kan zoeken, geblokkeerd. <br><br> | Alle apps |
| **App mag gegevens ontvangen van andere apps** | Geef aan welke apps gegevens naar deze app kunnen overdragen: <ul><li>**Door beleid beheerde apps**: overdracht alleen toestaan vanuit andere door beleid beheerde apps.</li><li>**Alle apps**: gegevensoverdracht vanuit alle apps toestaan.</li><li>**Geen**: geen gegevensoverdracht vanuit apps toestaan, met inbegrip van andere door beleid beheerde apps. | Alle apps |
| **'Opslaan als' voorkomen** | Kies **Ja** als u het gebruik van de optie Opslaan als wilt uitschakelen in deze app. Selecteer **Nee** als u het gebruik van de optie Opslaan als wilt toestaan. | Nee |
| **Knippen, kopiëren en plakken met andere apps beperken** | Geef op wanneer knip-, kopieer- en plakbewerkingen voor deze app kunnen worden gebruikt. U kunt kiezen uit: <ul><li>**Geblokkeerd**: geen knip-, kopieer- en plakbewerkingen toestaan tussen deze app en andere apps.</li><li>**Door beleid beheerde apps**: alleen knip-, kopieer- en plakbewerkingen toestaan tussen deze app en andere door beleid beheerde apps.</li><li>**Door beleid beheerde apps met Plakken in**: knippen en kopiëren toestaan tussen deze app en andere door beleid beheerde apps. Gegevens uit alle apps mogen in deze app worden geplakt.</li><li>**Elke app**: geen beperkingen voor knip-, kopieer- en plakbewerkingen vanuit en naar deze app. | Elke app |
|**Weergave van webinhoud beperken tot beheerde browser** | Kies **Ja** om af te dwingen dat webkoppelingen in de app worden geopend in de Managed Browser-app. <br><br> Voor apparaten die niet zijn geregistreerd bij Intune, kunnen de webkoppelingen in door beleid beheerde apps alleen worden geopend in de Managed Browser-app. <br><br> Als u Intune gebruikt voor het beheer van uw apparaten, raadpleegt u [Internettoegang beheren met beheerde-browserbeleid met Microsoft Intune](manage-internet-access-using-managed-browser-policies.md). | Nee |
| **Appgegevens versleutelen** | Voor door beleid beheerde apps worden gegevens versleuteld met behulp van het door iOS geleverde versleutelingsschema op apparaatniveau. Als een pincode is vereist, worden de gegevens versleuteld volgens de instellingen in het beleid voor app-beveiliging. <br><br> Ga naar de officiële Apple-documentatie [hier](https://support.apple.com/HT202739) om te zien welke iOS-versleutelingsmodules FIPS 140-2 gecertificeerd zijn of waarvoor FIPS 140-2-certificering nog in behandeling is. <br><br> Geef aan wanneer werk- of schoolgegevens in deze app worden versleuteld. U kunt kiezen uit: <ul><li>**Wanneer het apparaat is vergrendeld:** alle app-gegevens die aan dit beleid zijn gekoppeld, worden versleuteld terwijl het apparaat is vergrendeld.</li><li>**Wanneer het apparaat is vergrendeld en er geopende bestanden zijn:** alle app-gegevens die aan dit beleid zijn gekoppeld, worden versleuteld wanneer het apparaat is vergrendeld, met uitzondering van gegevens in de bestanden die momenteel in de app zijn geopend.</li><li>**Na opnieuw opstarten van apparaat:** alle app-gegevens die aan dit beleid zijn gekoppeld, worden versleuteld wanneer het apparaat opnieuw wordt opgestart, totdat het apparaat voor de eerste keer wordt ontgrendeld.</li><li>**Apparaatinstellingen gebruiken:** app-gegevens worden versleuteld op basis van de standaardinstellingen op het apparaat. <br><br> Wanneer u deze instelling inschakelt, moet de gebruiker een pincode instellen en gebruiken voor toegang tot het apparaat.  Als er geen pincode wordt ingesteld, worden de apps niet geopend en wordt de gebruiker gevraagd om een pincode in te stellen. Dit gebeurt met het bericht 'Uw organisatie vereist dat u eerst een pincode voor het apparaat inschakelt voor toegang tot deze app.' </li></ul> | Wanneer apparaat is vergrendeld |
| **Synchroniseren van contactpersonen uitschakelen** | Kies **Ja** om te voorkomen dat de app gegevens opslaat in de systeemeigen Contactpersonen-app op het apparaat. Kies **Nee** om ervoor te zorgen dat de app gegevens kan opslaan in de systeemeigen Contactpersonen-app op het apparaat. <br><br>Als u selectief wilt wissen om werk- of schoolgegevens uit de app te verwijderen, worden contactpersonen verwijderd die rechtstreeks vanuit de app met de systeemeigen Contactpersonen-app worden gesynchroniseerd. Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. Dit is momenteel alleen van toepassing op de Microsoft Outlook-app. | Nee |
| **Afdrukken uitschakelen** | Kies **Ja** om te voorkomen dat de app werk- of schoolgegevens afdrukt. | Nee |


> [!NOTE]
> Geen van de instellingen voor gegevensverplaatsing beheert de door Apple beheerde functie Open in op iOS-apparaten. Zie [Gegevensoverdracht beheren tussen iOS-apps met Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md) voor informatie over het beheer van de functie Open in.


## <a name="access-settings"></a>Toegangsinstellingen

| Instelling | Gebruik | Standaardwaarde |
|------|------|------|
| **Pincode is vereist voor toegang** | Kies **Ja** om een pincode te vereisen voor gebruik van deze app. De eerste keer dat de gebruiker de app uitvoert in een aan werk of school gerelateerde context, wordt de gebruiker gevraagd deze pincode in te stellen. Standaardwaarde = **Ja**.<br><br> Configureer de volgende instellingen voor pincodesterkte: <ul><li>**Aantal pogingen voordat pincode opnieuw wordt ingesteld**: geef het aantal pogingen voor de gebruiker op om de pincode in te voeren voordat de gebruik deze opnieuw moet instellen. Standaardwaarde = **5**.</li><li> **Eenvoudige pincode toestaan:** kies **Ja** als gebruikers eenvoudige pincodes mogen gebruiken, zoals 1234 of 1111. Kies **Nee** als ze geen eenvoudige tekenreeksen mogen gebruiken. Standaardwaarde = **Ja**. </li><li> **Lengte van de pincode:** geef het minimale aantal cijfers op waaruit een pincode moet bestaan. Standaardwaarde = **4**. </li><li> **Vingerafdruk in plaats van pincode toestaan (iOS 8.0+)**: selecteer **Ja** als de gebruiker in plaats van een pincode [Touch ID](https://support.apple.com/en-us/HT201371) mag gebruiken voor toegang tot apps. Standaardwaarde = **Ja**.<br><br> Op iOS-apparaten kunt u gebruikers hun identiteit laten aantonen met behulp van [Touch ID](https://support.apple.com/en-us/HT201371) in plaats van een pincode. Wanneer gebruikers deze app proberen te gebruiken via hun werk- of schoolaccount, moeten ze hun vingerafdruk in plaats van een pincode gebruiken. </li></ul>| Pincode vereisen: Ja <br><br> Pogingen om pincode opnieuw in te stellen: 5 <br><br> Eenvoudige pincode toestaan: Ja <br><br> Lengte pincode: 4 <br><br> Vingerafdruk toestaan: Ja |
| **Bedrijfsreferenties vereisen voor toegang** | Kies **Ja** om te vereisen dat gebruikers zich aanmelden met hun werk- of schoolaccount in plaats van een pincode voor toegang tot apps. Als u deze waarde op **Ja** instelt, overschrijft dit de vereisten voor de pincode of Touch ID.  | Nee |
| **De uitvoering blokkeren van beheerde apps die op jailbroken of geroote apparaten worden uitgevoerd** |  Kies **Ja** om te voorkomen dat deze app wordt uitgevoerd op jailbroken of geroote apparaten. De gebruiker kan deze app nog steeds gebruiken voor privétaken maar moet voor het openen van werk- of schoolgegevens in deze app een ander apparaat gebruiken. | Ja |
| **Toegangsvereisten opnieuw controleren na (minuten)** | Configureer de volgende instellingen: <ul><li>**Time-out**: geef de periode (in minuten) op waarna de toegangsvereisten voor de app opnieuw worden gecontroleerd. Standaardwaarde = **30** minuten.</li><li>**Offline respijtperiode**: als het apparaat offline is, geeft u de periode (in minuten) op waarna de toegangsvereisten voor de app opnieuw worden gecontroleerd. Standaardwaarde = **720** minuten (12 uur).</li></ul>| Time-out: 30 <br><br> Offline: 720 |
| **Offline interval (in dagen) voordat app-gegevens worden gewist** | Werk- of schoolgegevens in deze app kunnen worden gewist als een apparaat langer dan een bepaalde periode offline is. Geef het aantal dagen op dat een apparaat offline mag zijn voordat de werk- of schoolgegevens van het apparaat worden verwijderd. <br><br> | 90 dagen |



<!--HONumber=Dec16_HO3-->


