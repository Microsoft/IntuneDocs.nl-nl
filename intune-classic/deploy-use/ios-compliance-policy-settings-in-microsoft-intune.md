---
title: Instelling voor nalevingsbeleid voor iOS-apparaten
description: Dit onderwerp heeft betrekking op de regels en instellingen die u kunt definiëren in het nalevingsbeleid voor iOS-apparaten.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 12/15/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7973dd757c69bc0a63f1ff5d24973acb6086d8a4
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="compliance-policy-settings-for-ios-devices-in-microsoft-intune"></a>Instellingen voor nalevingsbeleid voor iOS-apparaten in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

De beleidsinstellingen die in dit onderwerp worden beschreven, zijn van toepassing op apparaten met iOS 8.0 en hoger.

Als u op zoek bent naar informatie over andere platforms, selecteert u een van de volgende opties:
> [!div class="op_single_selector"]
- [Instellingen voor nalevingsbeleid voor Android-apparaten](android-compliance-policy-settings-in-microsoft-intune.md)
- [Instellingen voor nalevingsbeleid voor Android for Work](afw-compliance-policy-settings-in-microsoft-intune.md)
- [Instellingen voor nalevingsbeleid voor Windows-apparaten](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>Systeembeveiligingsinstellingen
### <a name="password"></a>Wachtwoord
- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten:** stel deze optie in op **Ja** als u de gebruiker wilt verplichten een wachtwoord in te voeren om toegang te krijgen tot hun apparaat. iOS-apparaten die gebruikmaken van een wachtwoord, zijn versleuteld.

- **Eenvoudige wachtwoorden toestaan:** stel deze optie in op **Ja** zodat de gebruiker een eenvoudig wachtwoord kan maken, zoals **1234** of **1111**.

-  **Minimale wachtwoordlengte**: hiermee geeft u het minimale aantal cijfers of tekens aan waaruit het wachtwoord van de gebruiker moet bestaan.

- **Vereist wachtwoordtype**: geef aan of de gebruiker een **alfanumeriek** of een **numeriek** wachtwoord moet maken.

- **Minimum aantal tekensets**: als u **Vereist wachtwoordtype** instelt op **Alfanumeriek**, gebruikt u deze instelling om het minimum aantal tekensets op te geven dat het wachtwoord moet bevatten. De vier tekensets zijn:
  -   Kleine letters
  -   Hoofdletters
  -   Symbolen
  -   Getallen

  Als u een hogere waarde instelt, moet de gebruiker een wachtwoord maken dat complexer is.

  Voor iOS-apparaten verwijst deze instelling naar het aantal speciale tekens (bijvoorbeeld **!**, **#**, **&amp;**) dat in het wachtwoord moet worden opgenomen.

- **Minuten van inactiviteit voordat wachtwoord vereist is**: hiermee geeft u aan na hoeveel niet-actieve tijd gebruikers hun wachtwoord opnieuw moeten invoeren.

- **Wachtwoord verloopt (in dagen):** selecteer het aantal dagen waarna het wachtwoord van gebruikers verloopt en ze een nieuw wachtwoord moeten maken.

- **Wachtwoordgeschiedenis onthouden**: gebruik deze instelling in combinatie met **Wachtwoorden niet opnieuw gebruiken** om te voorkomen dat gebruikers eerder gebruikte wachtwoorden opnieuw gebruiken.

- **Wachtwoorden niet opnieuw gebruiken:** als u **Wachtwoordgeschiedenis onthouden** hebt geselecteerd, geeft u het aantal eerder gebruikte wachtwoorden op dat niet opnieuw kan worden gebruikt.

- **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status**: gebruik deze instelling samen met de instelling **Minuten van inactiviteit voordat wachtwoord vereist is**. De gebruiker wordt gevraagd een wachtwoord op te geven om toegang te krijgen tot een apparaat dat inactief is geweest gedurende de tijd die is opgegeven bij de instelling **Minuten van inactiviteit voordat wachtwoord vereist is**.

### <a name="email-profile"></a>E-mailprofiel
- **E-mailaccount moet worden beheerd door Intune**: wanneer deze optie is ingesteld op **Ja**, moet het e-mailprofiel worden gebruikt dat is geïmplementeerd op het apparaat. Het apparaat wordt in de volgende situaties beschouwd als niet compatibel:
  - Het e-mailprofiel is geïmplementeerd voor een andere gebruikersgroep dan de gebruikersgroep waarvoor het nalevingsbeleid is bedoeld.
  - De gebruiker heeft al een e-mailaccount op het apparaat ingesteld dat overeenkomt met het Intune-e-mailprofiel dat op het apparaat is geïmplementeerd. Intune kan het door de gebruiker ingerichte profiel niet overschrijven en kan het daarom niet beheren. Om naleving te garanderen, moet de gebruiker de bestaande e-mailinstellingen verwijderen. Daarna kan Intune het beheerde e-mailprofiel installeren.

- **Selecteer het e-mailprofiel dat moet worden beheerd door Intune**: als de instelling **E-mailaccount moet worden beheerd door Intune** is geselecteerd, kiest u **Selecteren** om het e-mailprofiel voor Intune op te geven. Het e-mailprofiel moet aanwezig zijn op het apparaat.

     Zie [De toegang tot zakelijke e-mail configureren met e-mailprofielen bij Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) voor meer informatie over e-mailprofielen.

## <a name="device-health-settings"></a>Instellingen voor de status van het apparaat

- **Apparaat mag niet zijn opengebroken of geroot**: als u deze instelling inschakelt, zijn apparaten die zijn opengebroken, niet compatibel.

##  <a name="device-properties"></a>Apparaateigenschappen
- **Minimale versie van het besturingssysteem die is vereist**: wanneer een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt het apparaat gerapporteerd als niet-compatibel.
Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De gebruiker kan kiezen om het apparaat bij te werken. Daarna zijn de bedrijfsbronnen toegankelijk.

- **Maximale versie van het besturingssysteem die is toegestaan:** wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die in de regel is opgegeven, wordt de toegang tot bedrijfsresources geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel die de versie van het besturingssysteem toestaat, kan dit apparaat niet worden gebruikt om toegang tot bedrijfsbronnen te krijgen.
