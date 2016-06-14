---
# required metadata

title: Kiezen hoe u apparaten beheert met Microsoft Intune | Microsoft Intune
description:
keywords:
author: jeffgilb
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Kiezen hoe u apparaten beheert
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Hiermee kunt u vele apparaten beheren door ze *in te schrijven* bij de service. Gebruikers kunnen vervolgens een *bedrijfsportal* gebruiken om verschillende bewerkingen uit te voeren, zoals het inschrijven van hun apparaat, zoeken naar en installeren van apps, ervoor zorgen dat het apparaat voldoet aan het bedrijfsbeleid en contact opnemen met de IT-ondersteuning.

## Manieren waarop u mobiele apparaten kunt beheren
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kan de volgende apparaatplatforms beheren:

- Apple iOS 7.1 en hoger
- Google Android 4.0 en hoger (inclusief Samsung KNOX)
- Windows Phone 8.0 en hoger
- Windows RT en Windows 8.1 RT
- Computers met Windows 8.1 en hoger
- Mac OS X 10.9 en hoger

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> Tip</h5>
  <p>Als u al eerder apparaten met een oudere versie van iOS dan de ondersteunde versie hebt ingeschreven, blijven deze ingeschreven. Raadpleeg echter de documentatie van elk [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] om te controleren of die iOS-versie wordt ondersteund door de functie.</p>
</div>

[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kan apparaten van gebruikers beheren. Dit wordt ook wel BYOD ('bring your own device' of 'neem je eigen apparaat mee') genoemd. Het kan ook apparaten beheren die eigendom zijn van het bedrijf, waaronder scenario’s waarin het bedrijf een lijst met apparaten biedt waaruit gebruikers kunnen kiezen. Dit wordt ook wel CYOD ('choose your own device' of 'kies je eigen apparaat').

### Apparaten inschrijven voor beheer
Als u mobiele apparaten hebt met het besturingssysteem iOS, Android of Windows Phone, moet u deze altijd inschrijven. Hoe u apparaten moet inschrijven, hangt echter af van de behoeften van uw organisatie:

|Inschrijvingstype|BYOD|CYOD|Gedeeld apparaat met manageraccount|Gedeeld apparaat zonder gebruikersaccount|
|-------------------|--------|--------|--------------------------------------|----------------------------------------|
|**Beschrijving**|Persoonlijk apparaat is ingeschreven met Microsoft Intune|Apparaat in bedrijfseigendom voor één gebruiker|Apparaat in bedrijfseigendom beheerd met een manageraccount gedeeld door veel gebruikers|Apparaat in bedrijfseigendom zonder specifieke gebruiker dat wordt gebruikt door veel gebruikers.|
|**Gebruiker van het apparaat**|Eigenaar|Toegewezen gebruiker|Er is geen gebruikersspecifiek account|Er is geen specifieke gebruiker|
|**Wie schrijft apparaten in?**|Eigenaar|Beheerder|Apparaatmanager|Iedereen|
|**Wie schrijft apparaten uit?**|Eigenaar of beheerder|Beheerder|Beheerder|Beheerder|
|**Wie stelt apparaten opnieuw in?**|Eigenaar of beheerder|Beheerder|Beheerder|Beheerder|

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> Tip</h5>
  <p>Zie [Beheermogelijkheden voor mobiele apparaten](mobile-device-management-capabilities-in-microsoft-intune.md) voor een volledige lijst van de mogelijkheden waarover u beschikt als u apparaten inschrijft.</p>
</div>



## Manieren waarop u Windows-pc’s kunt beheren
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kan Windows Vista en nieuwere Windows-pc's beheren met behulp van de Intune-computerclient. Bij Windows-pc's kunt u ervoor kiezen of u ze inschrijft of dat u de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-pc-clientsoftware installeert, waardoor u profiteert van enkele mogelijkheden die niet beschikbaar zijn als u apparaten inschrijft. In de meeste gevallen schrijft u uw Windows-apparaat bij Intune, waardoor u over meer mogelijkheden beschikt dan via de computerclient.

Overweeg de Intune-computerclient te gebruiken als u de volgende zaken wilt doen:
<ul>
<li>Een van de mogelijkheden van de Microsoft Intune-computerclient gebruiken om uw Windows-pc’s te beheren.</li>
<li>Een Windows-pc beheren met een besturingssysteem dat niet wordt ondersteund voor inschrijving.</li>
</ul>

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> Tip</h5>
  <p>Zie [Beheermogelijkheden voor Windows-pc’s](windows-pc-management-capabilities-in-microsoft-intune.md) voor een volledige lijst van de mogelijkheden waarover u beschikt als u de Intune-computerclient installeert op een ondersteunde Windows-pc.</p>
</div>

## Exchange ActiveSync-beheer
U kunt apparaten ook beheren met behulp van Exchange ActiveSync. Hiervoor moet u de lokale connector installeren of de ingebouwde Service-to-Service-connector gebruiken om verbinding te maken met uw Exchange-server.

Zie [Vereisten voor de lokale connector](/Intune/network-infrastructure-requirements-for-microsoft-intune.md) voor meer informatie over de hardware- en softwarevereisten om de lokale connector te installeren..

Zie [Mobile Device Management met Exchange ActiveSync en Microsoft Intune](/Intune/get-started/mobile-device-management-with-exchange-activesync-and-microsoft-intune.md) voor meer informatie over het gebruik van de lokale connector of de Service-to-Service-connector.



## Volgende stappen
Nu u enkele van de mogelijkheden hebt ontdekt die u kunt gebruiken wanneer u uw apparaten inschrijft bij [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], moet u [zich voorbereiden op het inschrijven van uw apparaten](/Intune/get-started/get-ready-to-enroll-devices-in-microsoft-intune.md). Nadat u uw apparaten hebt ingeschreven, kunt u profiteren van alle mogelijkheden waarover u hebt gelezen in dit onderwerp. <!--lindavr: There's a logical flaw in our "get to know/get started" content. You can take the path in this topic or you can take the path in the What to know before your get started topic. And they don't cover the same ground. -->


<!--HONumber=May16_HO1-->


