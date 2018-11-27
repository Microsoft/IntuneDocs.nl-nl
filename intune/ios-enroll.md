---
title: Kiezen hoe u iOS-apparaten registreert in Intune
titlesuffix: Microsoft Intune
description: Het registreren van iOS-apparaten in Microsoft Intune instellen.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: bc1ae3f545f840f9ebfa1b7b75b56862691d900e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52182734"
---
# <a name="enroll-ios-devices-in-intune"></a>iOS-apparaten registreren bij Intune

Intune maakt Mobile Device Management (MDM) mogelijk voor iPads en iPhones en geeft gebruikers toegang tot zakelijke e-mail en apps.

Als Intune-beheerder kunt u registratie inschakelen voor iOS-apparaten. U kunt gebruikers toestaan persoonlijke apparaten in te schrijven. Dit wordt ook wel BYOD-inschrijving (Bring Your Own Device) genoemd. U kunt ook de registratie van apparaten in bedrijfseigendom inschakelen.

## <a name="prerequisites-for-ios-enrollment"></a>Vereisten voor iOS-registratie
Voordat u de registratie van iOS-apparaten kunt inschakelen, moet u de volgende stappen uitvoeren:
- [Intune instellen](setup-steps.md): hiermee stelt u de Intune-infrastructuur in. Voor apparaatinschrijving is met name het [instellen van uw MDM-instantie](mdm-authority-set.md) van belang.
- [Een Apple MDM-pushcertificaat ophalen](apple-mdm-push-certificate-get.md): Apple vereist een certificaat voor het inschakelen van het beheer van iOS- en macOS-apparaten.

## <a name="user-owned-ios-devices-byod"></a>iOS-apparaten die het eigendom van gebruikers zijn (BYOD)

U kunt gebruikers hun persoonlijke apparaten laten inschrijven voor Intune-beheer, wat 'Bring Your Own Device' of BYOD wordt genoemd. Zodra u aan de vereisten hebt voldaan en gebruikerslicenties hebt toegewezen, kunnen ze in de App Store de Intune-bedrijfsportal-app downloaden en in de app de inschrijvingsinstructies volgen.

## <a name="company-owned-ios-devices"></a>iOS-apparaten die bedrijfseigendom zijn
Voor organisaties die apparaten voor hun gebruikers aanschaffen, ondersteunt Intune de volgende inschrijvingsmethoden voor iOS-apparaten die bedrijfseigendom zijn:

- Device Enrollment Program (DEP) van Apple
- Apple School Manager
- Inschrijving via Apple Configurator Setup Assistant
- Directe inschrijving via Apple Configurator

U kunt iOS-apparaten die bedrijfseigendom zijn ook inschrijven met een [Apparaatinschrijvingsmanager](device-enrollment-manager-enroll.md)-account.

## <a name="device-enrollment-program"></a>Programma voor apparaatinschrijving
Organisaties kunnen nu iOS-apparaten aanschaffen via het Device Enrollment Program (DEP) van Apple. Met DEP kunt u een registratieprofiel draadloos implementeren om apparaten voor beheer in te schrijven. Meer informatie over het [Device Enrollment Program](device-enrollment-program-enroll-ios.md).

## <a name="apple-school-manager"></a>Apple School Manager
Apple School Manager is een programma voor het aanschaffen en inschrijven van apparaten voor scholen. Net zoals bij DEP kunt u een profiel implementeren om apparaten in te schrijven voor beheer. Meer informatie over [Apple School Manager](apple-school-manager-set-up-ios.md).

## <a name="apple-configurator"></a>Apple Configurator
U kunt iOS-apparaten inschrijven met Apple Configurator op een Mac-computer. Ter voorbereiding daarop sluit u de apparaten aan via USB en installeert u een inschrijvingsprofiel. U kunt apparaten op twee manieren inschrijven met Apple Configurator:
- Registratie met Configuratieassistent: met dit proces wordt het apparaat gewist, wordt het apparaat voorbereid voor uitvoering van Configuratieassistent en worden de bedrijfsbeleidsregels voor de nieuwe gebruiker van het apparaat geïnstalleerd.
- Directe registratie: met dit proces wordt het apparaat niet gewist en wordt het apparaat met een vooraf gedefinieerd beleid geregistreerd. Deze methode is geschikt voor apparaten zonder gebruikersaffiniteit.

Meer informatie over [Apple Configurator-inschrijving](apple-configurator-setup-assistant-enroll-ios.md).

## <a name="use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices"></a>Apparaten die zijn geregistreerd via de bedrijfsportal op DEP of Apple Configurator gebruiken

Op apparaten die zijn geconfigureerd met gebruikersaffiniteit kan de bedrijfsportal-app worden geïnstalleerd en uitgevoerd om apps te downloaden en apparaten te beheren. Nadat gebruikers hun apparaten hebben ontvangen, moeten zij een aantal extra stappen uitvoeren om de Configuratieassistent te voltooien en de bedrijfsportal-app te installeren.

Gebruikersaffiniteit is vereist voor de ondersteuning van het volgende:
  - MAM-apps (Mobile Application Management)
  - Voorwaardelijke toegang tot e-mail en bedrijfsgegevens
  - Bedrijfsportal-app

**iOS-apparaten in bedrijfseigendom inschrijven met gebruikersaffiniteit**
1. Wanneer gebruikers hun apparaat inschakelen, wordt ze gevraagd de Configuratieassistent te voltooien. 
2. Na het voltooien van de installatie wordt er naar de Apple ID van de gebruikers gevraagd. Er moet een Apple ID worden opgegeven zodat de bedrijfsportal op het apparaat kan worden geïnstalleerd. 
3. Op het iOS-apparaat wordt de bedrijfsportal-app automatisch via de App Store geïnstalleerd.
4. Gebruikers moeten de bedrijfsportal-app openen en zich aanmelden met de referenties (zoals hun unieke gebruikersnaam of UPN) die zijn gekoppeld aan hun abonnement in Intune. 
5. Na het aanmelden is de inschrijving voltooid. Gebruikers kunnen dit apparaat nu gebruiken met de volledige set mogelijkheden.

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a>Over beheerde bedrijfsapparaten zonder gebruikersaffiniteit

Apparaten die zijn geconfigureerd zonder gebruikersaffiniteit bieden geen ondersteuning voor de bedrijfsportal. De app moet niet op deze apparaten worden geïnstalleerd. De bedrijfsportal is bedoeld voor gebruikers met zakelijke referenties die toegang tot persoonlijke bedrijfsresources (bijvoorbeeld e-mail) nodig hebben. Apparaten die zijn ingeschreven zonder gebruikersaffiniteit zijn niet bedoeld voor gebruik met een specifieke gebruikersaanmelding. Kiosks, verkooppunten (POS) of apparaten met gedeelde hulpmiddelen zijn typische gebruiksvoorbeelden van apparaten die zonder gebruikersaffiniteit worden ingeschreven.

Als gebruikersaffiniteit vereist is, moet **Gebruikersaffiniteit** in het inschrijvingsprofiel van het apparaat zijn geselecteerd voordat het apparaat wordt ingeschreven. Als u de status van de affiniteit op een apparaat wilt wijzigen, moet u het apparaat buiten gebruik stellen en opnieuw inschrijven.

