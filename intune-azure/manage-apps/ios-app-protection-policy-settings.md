---
title: Beveiligingsbeleidsinstellingen voor iOS-apps
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp worden de beveiligingsbeleidsinstellingen voor iOS-apparaten beschreven.'
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f8b08f2-504c-4b38-bea2-b8a4ef0526b8
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: b68c731d48551db8fc7d7f0acad766ff4fc5a1e1
ms.contentlocale: nl-nl
ms.lasthandoff: 05/10/2017


---

#  <a name="ios-app-protection-policy-settings"></a>Beveiligingsbeleidsinstellingen voor iOS-apps
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

De in dit onderwerp beschreven beleidsinstellingen kunnen worden [geconfigureerd](app-protection-policies.md) voor een app-beveiligingsbeleid op het tabblad **Instellingen** in Azure Portal.

Er zijn twee soorten beleidsinstellingen, namelijk instellingen voor herlocatie van gegevens en instellingen voor toegang. In dit onderwerp verwijst de term ***door beleid beheerde apps*** naar apps die zijn geconfigureerd met een app-beveiligingsbeleid.

##  <a name="data-relocation-settings"></a>Instellingen voor herlocatie van gegevens

| Instelling | Gebruik | Standaardwaarde(n) |
|------|------|------|
| **Back-ups van iTunes en iCloud voorkomen** | Kies **Ja** om te voorkomen dat deze app back-ups maakt van gegevens voor werk of school op iTunes en iCloud. Kies **Nee** om toe te staan dat deze app back-ups maakt van gegevens voor werk of school op iTunes en iCloud.| Ja |
| **App mag gegevens overdragen naar ander apps** | Geef aan welke apps gegevens uit deze app kunnen ontvangen: <ul><li> **Door beleid beheerde apps**: overdracht alleen toestaan naar andere door beleid beheerde apps.</li> <li>**Alle apps**: overdracht naar alle apps toestaan. </li> <li>**Geen**: geen gegevensoverdracht naar apps toestaan, met inbegrip van andere door beleid beheerde apps.</li></ul> Als u deze optie daarnaast instelt op **Door beleid beheerde apps** of **Geen**, wordt de iOS 9-functie waarmee Spotlight Search naar gegevens in apps kan zoeken, geblokkeerd. <br><br> Er zijn enkele uitzonderingsapps en -services waar Intune gegevens naar mag overbrengen. Zie [Uitzonderingen voor gegevensoverdracht](#Data-transfer-exemptions) voor een volledige lijst met apps en services. | Alle apps |
| **App mag gegevens ontvangen van andere apps** | Geef aan welke apps gegevens naar deze app kunnen overdragen: <ul><li>**Door beleid beheerde apps**: overdracht alleen toestaan vanuit andere door beleid beheerde apps.</li><li>**Alle apps**: gegevensoverdracht vanuit alle apps toestaan.</li><li>**Geen**: geen gegevensoverdracht vanuit apps toestaan, met inbegrip van andere door beleid beheerde apps. </li></ul> <p>  Er zijn enkele uitzonderingsapps en -services van waaruit Intune gegevensoverdracht mag toestaan. Zie [Uitzonderingen voor gegevensoverdracht](#Data-transfer-exemptions) voor een volledige lijst met apps en services. | Alle apps |
| **'Opslaan als' voorkomen** | Kies **Ja** als u het gebruik van de optie Opslaan als wilt uitschakelen in deze app. Selecteer **Nee** als u het gebruik van de optie Opslaan als wilt toestaan. | Nee |
| **Knippen, kopiëren en plakken met andere apps beperken** | Geef op wanneer knip-, kopieer- en plakbewerkingen voor deze app kunnen worden gebruikt. U kunt kiezen uit: <ul><li>**Geblokkeerd**: geen knip-, kopieer- en plakbewerkingen toestaan tussen deze app en andere apps.</li><li>**Door beleid beheerde apps**: alleen knip-, kopieer- en plakbewerkingen toestaan tussen deze app en andere door beleid beheerde apps.</li><li>**Door beleid beheerde apps met Plakken in**: knippen en kopiëren toestaan tussen deze app en andere door beleid beheerde apps. Gegevens uit alle apps mogen in deze app worden geplakt.</li><li>**Elke app**: geen beperkingen voor knip-, kopieer- en plakbewerkingen vanuit en naar deze app. | Elke app |
|**Weergave van webinhoud beperken tot beheerde browser** | Kies **Ja** om af te dwingen dat webkoppelingen in de app worden geopend in de Managed Browser-app. <br><br> Voor apparaten die niet zijn geregistreerd bij Intune, kunnen de webkoppelingen in door beleid beheerde apps alleen worden geopend in de Managed Browser-app. <br><br> Als u Intune gebruikt voor het beheer van uw apparaten, raadpleegt u [Internettoegang beheren met beheerde-browserbeleid met Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/manage-internet-access-using-managed-browser-policies). | Nee |
| **Appgegevens versleutelen** | Voor door beleid beheerde apps worden gegevens versleuteld met behulp van het door iOS geleverde versleutelingsschema op apparaatniveau. Als een pincode is vereist, worden de gegevens versleuteld volgens de instellingen in het beleid voor app-beveiliging. <br><br> Ga naar de officiële Apple-documentatie [hier](https://support.apple.com/HT202739) om te zien welke iOS-versleutelingsmodules FIPS 140-2 gecertificeerd zijn of waarvoor FIPS 140-2-certificering nog in behandeling is. <br><br> Geef aan wanneer werk- of schoolgegevens in deze app worden versleuteld. U kunt kiezen uit: <ul><li>**Wanneer het apparaat is vergrendeld:** alle app-gegevens die aan dit beleid zijn gekoppeld, worden versleuteld terwijl het apparaat is vergrendeld.</li><li>**Wanneer het apparaat is vergrendeld en er geopende bestanden zijn:** alle app-gegevens die aan dit beleid zijn gekoppeld, worden versleuteld wanneer het apparaat is vergrendeld, met uitzondering van gegevens in de bestanden die momenteel in de app zijn geopend.</li><li>**Na opnieuw opstarten van apparaat:** alle app-gegevens die aan dit beleid zijn gekoppeld, worden versleuteld wanneer het apparaat opnieuw wordt opgestart, totdat het apparaat voor de eerste keer wordt ontgrendeld.</li><li>**Apparaatinstellingen gebruiken:** app-gegevens worden versleuteld op basis van de standaardinstellingen op het apparaat. Wanneer u deze instelling inschakelt, moet de gebruiker een pincode instellen en gebruiken voor toegang tot het apparaat.  Als er geen pincode wordt ingesteld, worden de apps niet geopend en wordt de gebruiker gevraagd om een pincode in te stellen. Dit gebeurt met het bericht 'Uw organisatie vereist dat u eerst een pincode voor het apparaat inschakelt voor toegang tot deze app.' </li></ul> | Wanneer apparaat is vergrendeld |
| **Synchroniseren van contactpersonen uitschakelen** | Kies **Ja** om te voorkomen dat de app gegevens opslaat in de systeemeigen Contactpersonen-app op het apparaat. Kies **Nee** om ervoor te zorgen dat de app gegevens kan opslaan in de systeemeigen Contactpersonen-app op het apparaat. <br><br>Als u selectief wilt wissen om werk- of schoolgegevens uit de app te verwijderen, worden contactpersonen verwijderd die rechtstreeks vanuit de app met de systeemeigen Contactpersonen-app worden gesynchroniseerd. Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. Dit is momenteel alleen van toepassing op de Microsoft Outlook-app. | Nee |
| **Afdrukken uitschakelen** | Kies **Ja** om te voorkomen dat de app werk- of schoolgegevens afdrukt. | Nee |


> [!NOTE]
> Geen van de instellingen voor gegevensverplaatsing beheert de door Apple beheerde functie Open in op iOS-apparaten. Zie [Gegevensoverdracht beheren tussen iOS-apps met Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md) voor informatie over het beheer van de functie Open in.

## <a name="data-transfer-exemptions"></a>Uitzonderingen voor gegevensoverdracht

Er zijn een aantal uitzonderingsapps en -platformservices waar het Intune-beveiligingsbeleid voor apps in bepaalde scenario’s gegevensoverdracht naar en van kan toestaan. Deze lijst kan worden gewijzigd en reflecteert de services en apps die als nuttig voor beveiligde productiviteit worden beschouwd.

| Naam van app/service | Beschrijving |
| ---- | --- |
|tel; telprompt | Systeemeigen phone-app |
| skype | Skype |
| app-settings | Apparaatinstellingen |
| itms; itmss; itms-apps; itms-appss; itms-services | App Store |
| calshow | Systeemeigen kalender |


## <a name="access-settings"></a>Toegangsinstellingen

| Instelling | Gebruik | Standaardwaarde(n) |
|------|------|------|
| **Pincode is vereist voor toegang** | Kies **Ja** om een pincode te vereisen voor gebruik van deze app. De eerste keer dat de gebruiker de app uitvoert in een aan werk of school gerelateerde context, wordt de gebruiker gevraagd deze pincode in te stellen. Standaardwaarde = **Ja**.<br><br> Configureer de volgende instellingen voor pincodesterkte: <ul><li>**Aantal pogingen voordat pincode opnieuw wordt ingesteld**: geef het aantal pogingen voor de gebruiker op om de pincode in te voeren voordat de gebruik deze opnieuw moet instellen. Standaardwaarde = **5**.</li><li> **Eenvoudige pincode toestaan:** kies **Ja** als gebruikers eenvoudige pincodes mogen gebruiken, zoals 1234 of 1111. Kies **Nee** als ze geen eenvoudige tekenreeksen mogen gebruiken. Standaardwaarde = **Ja**. </li><li> **Lengte van de pincode:** geef het minimale aantal cijfers op waaruit een pincode moet bestaan. Standaardwaarde = **4**. </li><li> **Vingerafdruk in plaats van pincode toestaan (iOS 8.0+)**: selecteer **Ja** als de gebruiker in plaats van een pincode [Touch ID](https://support.apple.com/en-us/HT201371) mag gebruiken voor toegang tot apps. Standaardwaarde = **Ja**.</li></ul> Op iOS-apparaten kunt u gebruikers hun identiteit laten aantonen met behulp van [Touch ID](https://support.apple.com/en-us/HT201371) in plaats van een pincode. Wanneer gebruikers deze app proberen te gebruiken via hun werk- of schoolaccount, moeten ze hun vingerafdruk in plaats van een pincode gebruiken. </li></ul>| Pincode vereisen: Ja <br><br> Pogingen om pincode opnieuw in te stellen: 5 <br><br> Eenvoudige pincode toestaan: Ja <br><br> Lengte pincode: 4 <br><br> Vingerafdruk toestaan: Ja |
| **Bedrijfsreferenties vereisen voor toegang** | Kies **Ja** om te vereisen dat gebruikers zich aanmelden met hun werk- of schoolaccount in plaats van een pincode voor toegang tot apps. Als u deze waarde op **Ja** instelt, overschrijft dit de vereisten voor de pincode of Touch-ID.  | Nee |
| **De uitvoering blokkeren van beheerde apps die op jailbroken of geroote apparaten worden uitgevoerd** |  Kies **Ja** om te voorkomen dat deze app wordt uitgevoerd op jailbroken of geroote apparaten. De gebruiker kan deze app nog steeds gebruiken voor privétaken maar moet voor het openen van werk- of schoolgegevens in deze app een ander apparaat gebruiken. | Yes |
| **Toegangsvereisten opnieuw controleren na (minuten)** | Configureer de volgende instellingen: <ul><li>**Time-out**: geef de periode (in minuten) op waarna de toegangsvereisten voor de app opnieuw worden gecontroleerd. Standaardwaarde = **30** minuten.</li><li>**Offline respijtperiode**: als het apparaat offline is, geeft u de periode (in minuten) op waarna de toegangsvereisten voor de app opnieuw worden gecontroleerd. Standaardwaarde = **720** minuten (12 uur).</li></ul>| Time-out: 30 <br><br> Offline: 720 |
| **Offline interval (in dagen) voordat app-gegevens worden gewist** | Werk- of schoolgegevens in deze app kunnen worden gewist als een apparaat langer dan een bepaalde periode offline is. Geef het aantal dagen op dat een apparaat offline mag zijn voordat de werk- of schoolgegevens van het apparaat worden verwijderd. <br><br> | 90 dagen |
| **Minimumversie van het iOS-besturingssysteem vereisen** | Kies **Ja** om een minimumversie van het iOS-besturingssysteem te vereisen voor gebruik van deze app. Toegang door de gebruiker wordt geblokkeerd als de iOS-versie op het apparaat niet aan de vereiste voldoet. <br><br> | Nee |
| **Minimumversie van het iOS-besturingssysteem vereisen (alleen waarschuwing)** | Kies **Ja** om een minimaal iOS-besturingssysteem aan te bevelen bij gebruik van deze app. De gebruiker ziet een melding als de iOS-versie op het apparaat niet aan de vereiste voldoet. De gebruiker kan deze melding negeren. <br><br> | Nee |
| **Minimumversie van app vereisen** | Kies **Ja** om een minimumversie van de app te vereisen voor gebruik van de app. Toegang door de gebruiker wordt geblokkeerd als de app-versie op het apparaat niet aan de vereiste voldoet.<br><br>Wanneer u apps als doel selecteert, is het versieschema tussen de apps vaak afwijkend.<br><br> | Nee |
| **Minimumversie van app vereisen (alleen waarschuwing)** | Kies **Ja** om een minimale app-versie aan te bevelen bij gebruik van de app. De gebruiker ziet een melding als de app-versie op het apparaat niet aan de vereiste voldoet. De gebruiker kan deze melding negeren.<br><br>Wanneer u apps als doel selecteert, is het versieschema tussen de apps vaak afwijkend.<br><br> | Nee |
| **Minimumversie van SDK voor het beleid voor app-beveiliging van Intune vereisen** | Kies **Ja** om een minimumversie van de SDK voor het beleid voor app-beveiliging van Intune te vereisen die wordt gebruikt in de app. Toegang door de gebruiker wordt geblokkeerd als de SDK-versie voor Intune-appbeveiligingsbeleid op het apparaat niet aan de vereiste voldoet. <br> <br> Zie [Overzicht van de Intune App SDK](https://docs.microsoft.com/intune/develop/intune-app-sdk) voor meer informatie over de SDK voor Intune-appbeveiligingsbeleid <br><br> | Nee |

##  <a name="add-ins-for-outlook-app"></a>Invoegtoepassingen voor Outlook-app

Outlook heeft onlangs invoegtoepassingen in Outlook voor iOS geïntroduceerd waarmee u populaire apps met de e-mailclient kunt integreren. Invoegtoepassingen voor Outlook zijn beschikbaar op het web en in Windows, Mac en Outlook voor iOS. Aangezien invoegtoepassingen worden beheerd via Microsoft Exchange, kunnen gebruikers gegevens en berichten delen tussen Outlook en niet-beheerde invoegtoepassingen, tenzij invoegtoepassingen in Exchange zijn uitgeschakeld voor de gebruiker.

Als u wilt dat uw eindgebruikers geen Outlook-invoegtoepassingen meer kunnen benaderen en installeren (dit geldt dan voor alle Outlook-clients), moet u de volgende wijzigingen aanbrengen in rollen in het Exchange-beheercentrum:

- Als u wilt voorkomen dat gebruikers Office Store-invoegtoepassingen installeren, verwijdert u de My Marketplace-rol.
- Als u wilt voorkomen dat gebruikers sideloading uitvoeren voor invoegtoepassingen, verwijdert u de My Custom Apps-rol.
- Als u wilt voorkomen dat gebruikers sowieso een invoegtoepassing kunnen installeren, verwijdert u zowel de My Custom Apps-rol als de My Marketplace-rol.

Deze instructies zijn van toepassing op Office 365, Exchange 2016, Exchange 2013 via Outlook op het web, Windows, Mac en mobiele apparaten.

- Meer informatie over [invoegtoepassingen voor Outlook](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx).
- Meer informatie over [het opgeven van de beheerders en gebruikers die invoegtoepassingen voor de Outlook-app kunnen installeren en beheren](https://technet.microsoft.com/library/jj943754(v=exchg.150).aspx).

