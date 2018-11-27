---
title: Android-kioskinstellingen weergeven in Microsoft Intune - Azure | Microsoft Docs
description: Configureer Android Enterprise-kioskapparaten.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 9/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: c4db49b6727a430696d6ade3bc8eb8f4600ebe3e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52190282"
---
# <a name="android-enterprise-kiosk-settings-in-intune"></a>Android Enterprise-kioskinstellingen in Intune

Android-kioskprofielen bieden ondersteuning voor de volgende configuratie-instellingen. Wanneer u een profiel maakt, worden deze instellingen weergegeven wanneer u **Profieltype** > **Alleen de eigenaar van het apparaat** > **Apparaatbeperkingen** selecteert. Als u deze instellingen wilt bekijken, selecteert u **Eigenschappen** in een Android Enterprise-apparaatbeperkingsprofiel en kiest u **Configureren**.

## <a name="general-settings"></a>Algemene instellingen

- **Schermopname**: kies **Blokkeren** om te voorkomen dat gebruikers schermopnamen maken van het scherm van het apparaat.
- **Camera**: kies **Blokkeren** om de camera van het apparaat uit te schakelen.
- **Standaardmachtigingsbeleid**: met deze instelling bepaalt u het standaardmachtigingsbeleid voor aanvragen betreffende runtime-machtigingen. De mogelijke waarden zijn:
    - **Standaardwaarde apparaat**: gebruik de standaardinstelling van het apparaat.
    - **Prompt**: de gebruiker wordt gevraagd de machtiging goed te keuren.
    - **Automatisch verlenen**: machtigingen worden automatisch verleend.
    - **Automatisch weigeren**: machtigingen worden automatisch geweigerd.
- **Volumewijzigingen**: kies **Blokkeren** om te voorkomen dat gebruikers het volume van het apparaat wijzigen.
- **Wissen**: kies **Blokkeren** om te voorkomen dat gebruikers het apparaat wissen.
- **Opstarten in veilige modus**: kies **Blokkeren** om te voorkomen dat gebruikers het apparaat opnieuw opstarten in de veilige modus.
- **Statusbalk**: kies **Blokkeren** om te voorkomen dat gebruikers de statusbalk openen en toegang krijgen tot bijvoorbeeld meldingen en snelle instellingen.
- **Wi-Fi-instellingswijzigingen**: kies **Blokkeren** om te voorkomen dat gebruikers Wi-Fi-configuraties wijzigingen die zijn gemaakt door de eigenaar van het apparaat. Gebruikers kunnen hun eigen Wi-Fi-configuraties maken.
- **Wi-Fi-toegangspuntconfiguratie**: kies **Blokkeren** om te voorkomen dat gebruikers Wi-Fi-configuraties maken of bewerken.
- **Foutopsporingsfuncties**: kies **Toestaan** zodat gebruikers de functies voor foutopsporing kunnen gebruiken.
- **Microfoon aanpassen**: kies **Blokkeren** om te voorkomen dat gebruikers het volume van de microfoon aanpassen of dempen.
- **E-mailadressen voor beveiliging bij wissen**: kies **E-mailadressen van Google-account** voor het definiëren van e-mailadressen (gescheiden door puntkomma’s) waarmee het apparaat kan worden ontgrendeld na wissen. Als er geen e-mailadres wordt opgegeven, kan iedereen het apparaat ontgrendelen na wissen.
- **Netwerknooduitgang**: kies **Inschakelen** zodat de functie Netwerknooduitgang wordt ingeschakeld. Als er geen netwerkverbinding kan worden gemaakt bij het opstarten, wordt de gebruiker met Netwerknooduitgang gevraagd om tijdelijk verbinding te maken met een netwerk om het apparaatbeleid te vernieuwen. Wanneer het beleid is toegepast, wordt het tijdelijke netwerk vergeten en gaat het apparaat verder met opstarten. Hierdoor wordt voorkomen dat er geen verbinding kan worden gemaakt als er in het laatste beleid geen geschikt netwerk aanwezig is en het apparaat wordt opgestart in een app in de taakvergrendelingsmodus, of als de gebruiker om een andere reden de apparaatinstellingen niet kan bereiken.
- **Installatie via onbekende bronnen toestaan**: selecteer **Toestaan** om gebruikers te laten installeren via onbekende bronnen.
- **Systeemupdate**: kies een optie om te bepalen hoe het apparaat omgaat met draadloze updates:
    - **Standaardwaarde apparaat**: gebruik de standaardinstelling van het apparaat.
    - **Automatisch**: updates worden automatisch geïnstalleerd zonder interactie van de gebruiker. Wanneer u dit beleid instelt, worden alle eventuele updates die nog niet zijn uitgevoerd, meteen geïnstalleerd.
    - **Uitgesteld**: updates worden gedurende 30 dagen uitgesteld. Na 30 dagen wordt de gebruiker gevraagd om de update te installeren. Het is mogelijk dat apparaatfabrikanten of leveranciers het uitstellen van belangrijke beveiligingsupdates voorkomen (uitzonderen). Voor een uitzonderingsupdate wordt een systeembericht weergegeven op het apparaat. 
    - **Onderhoudsperiode**: hiermee worden updates automatisch geïnstalleerd tijdens een dagelijkse onderhoudsperiode die u in Intune instelt. Er wordt 30 dagen geprobeerd de update(s) te installeren. Dit kan mislukken als er te weinig ruimte of onvoldoende accuvermogen is. Na 30 dagen wordt de gebruiker gevraagd om de update(s) te installeren. Deze periode wordt is ook gebruikt om updates voor Play-apps te installeren. Deze optie wordt aanbevolen voor specifieke apparaten, zoals kiosken, omdat kiosken met maar één app op de voorgrond kunnen worden bijgewerkt. 

## <a name="kiosk-settings"></a>Kioskinstellingen

- **Kioskmodus**: hiermee bepaalt u of op het apparaat maar één app of meerdere apps tegelijk kunnen worden uitgevoerd. Zie [Kioskinstellingen voor Android-apparaten](android-kiosk-settings.md) voor meer informatie.
    - **Kiosk voor één app**: gebruikers hebben slechts toegang tot één app.
    - **Kiosk voor meerdere apps**: gebruikers hebben toegang tot een beperkt aantal apps.

## <a name="device-password-settings"></a>Instellingen voor apparaatwachtwoord

- **Keyguard**: kies **Uitschakelen** om te voorkomen dat Keyguard op het apparaat wordt gebruikt.
- **Vereist wachtwoordtype**: bepaal welk type wachtwoord wordt vereist voor het apparaat.
- **Minimale wachtwoordlengte**: bepaal de minimale wachtwoordlengte die is vereist voor het apparaat.
- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: hiermee geeft u het aantal mislukte aanmeldingen op dat mag plaatsvinden voordat het apparaat wordt gewist.

## <a name="power-settings"></a>Energie-instellingen

- **Tijd tot het scherm wordt vergrendeld**: stel in hoeveel niet-actieve tijd er moet zijn voordat het apparaat wordt vergrendeld.
- **Scherm aan terwijl het apparaat is aangesloten**: kies bij welke energiebronnen het scherm aan blijft wanneer het apparaat is aangesloten.

## <a name="users-and-accounts-settings"></a>Gebruikers- en accountinstellingen

- **Nieuwe gebruikers toevoegen**: kies **Blokkeren** om te voorkomen dat gebruikers nieuwe gebruikers toevoegen.
- **Gebruikers verwijderen**: kies **Blokkeren** om te voorkomen dat gebruikers gebruikers verwijderen.
- **Accountwijzigingen**: kies **Blokkeren** om te voorkomen dat gebruikers accounts wijzigen.

## <a name="next-steps"></a>Volgende stappen
[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).



