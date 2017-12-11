---
title: Jamf Pro integreren met Intune in verband met nalevingsbeleid
titlesuffix: Azure portal
description: Gebruik nalevingsbeleid voor het beveiligen van apparaten die door Jamf worden beheerd.
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 87ddb1a5f6ca5cc9be2815aacc9c1570a51e792f
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2017
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Jamf Pro integreren met Intune in verband met nalevingsbeleid

|Van toepassing op: Intune in Azure Portal |
|--|
|Op zoek naar documentatie over Intune in de klassieke portal? Klik [hier](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

|Momenteel alleen als beperkte preview|
|--|
|De functies die in dit onderwerp worden beschreven, zijn alleen beschikbaar voor klanten die momenteel over de beperkte preview-versie beschikken. Dit bericht wordt verwijderd wanneer de functies voor alle klanten zijn vrijgegeven.|
| |

Als uw organisatie gebruikmaakt van [Jamf Pro](https://www.jamf.com) voor het beheren van de Macs van uw eindgebruikers, kunt u gebruikmaken van Microsoft Intune-nalevingsbeleid met voorwaardelijke toegang tot Azure Active Directory om ervoor te zorgen dat apparaten in uw organisatie compatibel zijn.

## <a name="prerequisites"></a>Vereisten

U hebt het volgende nodig om voorwaardelijke toegang met Jamf Pro te configureren:

- Toegang tot de Intune Private Preview voor voorwaardelijke toegang tot macOS
- Jamf Pro 10.1.0 of hoger
- [Bedrijfsportal-app voor macOS ](https://aka.ms/macoscompanyportal)
- macOS-apparaten met OS X 10.11 Yosemite of hoger

## <a name="connecting-intune-to-jamf-pro"></a>Verbinding van Intune met Jamf Pro

U kunt Intune als volgt verbinden met Jamf Pro:

1. Een nieuwe toepassing maken in Azure
2. Intune instellen op integratie met Jamf Pro
3. Voorwaardelijke toegang in Jamf Pro configureren

## <a name="create-a-new-application-in-azure-active-directory"></a>Een nieuwe toepassing maken in Azure Active Directory

1. Open **Azure Active Directory** > **App-registratie**.
2. Klik op **+Nieuwe toepassing registreren**.
3. Voer een **weergavenaam** in, zoals **Voorwaardelijke toegang tot Jamf**.
4. Selecteer **Web-app/API**.
5. Geef de **aanmeldings-URL** op met behulp van de URL van uw Jamf Pro-exemplaar.
6. Klik op **Toepassing maken**.
7. Sla de zojuist gemaakte **Toepassings-id** op, open **Instellingen** en navigeer naar **API-toegang** > **Sleutels** om een nieuwe toepassingssleutel te maken. Voer een **beschrijving** in en de tijd waarna de toepassingssleutel **verloopt**, en sla de toepassingssleutel vervolgens op. 

  > [!IMPORTANT]
  > De toepassingssleutel wordt tijdens dit proces maar één keer weergegeven. Bewaar de sleutel op een locatie waar u deze eenvoudig kunt terugvinden.

8. Open **Instellingen**, navigeer naar **API-toegang** > **Vereiste machtigingen** en verwijder alle machtigingen.

  > [!NOTE]
  > Voeg een nieuwe vereiste machtiging toe. De toepassing kan alleen juist werken als die ene vereiste machtiging is ingesteld.

9.  Selecteer **Microsoft Intune API** en klik op **Selecteren**.
10. Kies **Apparaatkenmerken verzenden naar Microsoft Intune** en klik op **Selecteren**.
11. Klik op de knop **Machtigingen verlenen** nadat de vereiste machtigingen voor de toepassing zijn opgeslagen.

  > [!NOTE]
  > Als de toepassingssleutel is verlopen, moet u een nieuwe toepassingssleutel maken in Microsoft Azure en vervolgens de gegevens voor voorwaardelijke toegang in Jamf Pro bijwerken. U kunt in Azure zowel de oude als de nieuwe sleutel activeren om serviceonderbrekingen te voorkomen.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Intune instellen op integratie met Jamf Pro

1. In Microsoft Azure Portal opent u **Microsoft Intune** > **Apparaatcompatibiliteit** > **Partnerapparaatbeheer**.
2. Schakel de Nalevingsconnector voor Jamf in door de toepassings-id te plakken in het veld **Azure Active Directory-app-id**.
3. Klik op **Opslaan**.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Microsoft Intune-integratie in Jamf Pro configureren

1. Navigeer in Jamf Pro naar **Global Management** > **Conditional Access**. Klik op de knop **Edit** op het tabblad **Microsoft Intune Integration**.
2. Schakel het selectievakje voor **Enable Microsoft Intune Integration** in.
3. Geef de vereiste gegevens op over uw Azure-tenant, met inbegrip van **Location**, **Domain name**, plus de **Application ID** en de **Application Key** die u in de vorige stappen hebt opgeslagen.
4. Klik op **Opslaan**. Jamf Pro test uw instellingen en bevestigt of ze juist zijn.

## <a name="set-up-compliance-policies-and-register-devices"></a>Nalevingsbeleid instellen en apparaten registreren

Nadat u de integratie tussen Intune en Jamf hebt geconfigureerd, moet u [nalevingsbeleid toepassen op door Jamf beheerde apparaten](conditional-access-assign-jamf.md).

## <a name="information-shared-from-jamf-pro-to-intune"></a>Informatie die door Jamf Pro wordt gedeeld met Intune

Jamf Pro legt inventarisinformatie vast over beheerde macOS-apparaten. Jamf Pro geeft de volgende informatie door aan Intune:

* Id Azure AD-apparaat
* Status van de JAMF-inventaris (inventarisstatus van een computer die tijdens de afgelopen 24 uur is ingecheckt bij Jamf Pro)
* Versie besturingssysteem
* Id Azure AD-gebruiker
* Versleuteld (FileVault 2)
* Poortwachterstatus
* Wachtwoord: minimum aantal tekensets
* Verlopen van wachtwoorden (dagen)
* Type wachtwoord: eenvoudig, alfanumeriek of onbekend
* Automatische aanmelding voorkomen
* Vereiste lengte van de wachtwoordcode
* Wachtwoord: aantal eerdere wachtwoorden dat niet opnieuw mag worden gebruikt
* Beveiliging systeemintegriteit
* Tijd laatste check-in
* Type architectuur
* Beschikbare RAM-sleuven
* Capaciteit van de accu
* Opstart-ROM
* Bussnelheid
* Cachegrootte
* Apparaatnaam
* Lid van domein
* Jamf-id
* MAC-adres
* Merk
* Model
* Model-id
* NIC-snelheid
* Aantal kernen
* Aantal processors
* Besturingssysteem
* Platform
* Processorsnelheid
* Type processor
* Secundair MAC-adres
* Serienummer
* SMC-versie
* Totaal RAM
* udid
* E-mailadres gebruiker

## <a name="next-steps"></a>Volgende stappen

- [Nalevingsbeleid toepassen op door Jamf beheerde apparaten](conditional-access-assign-jamf.md)
