---
title: Inschrijving voor Windows-apparaten instellen met Microsoft Intune
titlesuffix: ''
description: Stel inschrijving in voor Windows-apparaten.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 3c100ef3e598bf377f0464bfba161d4ad689ba98
ms.sourcegitcommit: 9a1924ba2372904eb4a8a1894973e6f2be84129d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2018
ms.locfileid: "53626033"
---
# <a name="set-up-enrollment-for-windows-devices"></a>Inschrijving voor Windows-apparaten instellen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met de informatie in dit artikel kunnen IT-beheerders de inschrijving van Windows-apparaten vereenvoudigen voor hun gebruikers. Zodra u [Intune hebt ingesteld](setup-steps.md), kunnen gebruikers Windows-apparaten registreren door zich [aan te melden](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows) met hun werk- of schoolaccount.  

Als Intune-beheerder kunt u de registratie op de volgende manieren vereenvoudigen:
- [Automatische registratie inschakelen](#enable-windows-10-automatic-enrollment) (vereist Azure AD Premium)
- [CNAME-registratie](#simplify-windows-enrollment-without-azure-ad-premium)
- [Bulkinschrijving inschakelen](windows-bulk-enroll.md) (vereist Azure AD Premium en Windows Configuration Designer)

Vereenvoudiging van Windows-apparaatregistratie is afhankelijk van twee factoren:

- **Gebruikt u Azure Active Directory Premium?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) is opgenomen in Enterprise Mobility + Security en andere licentieplannen.
- **Welke versies van Windows-clients worden er geregistreerd door gebruikers?** <br>Windows 10-apparaten kunnen automatisch worden ingeschreven door het toevoegen van een werk- of schoolaccount. Eerdere versies moeten worden ingeschreven met de bedrijfsportal-app.

||**Azure AD Premium**|**Overige AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Automatische inschrijving](#enable-windows-10-automatic-enrollment) |[Gebruikersinschrijving](#enable-windows-enrollment-without-azure-ad-premium)|
|**Eerdere Windows-versies**|[Gebruikersinschrijving](#enable-windows-enrollment-without-azure-ad-premium)|[Gebruikersinschrijving](#enable-windows-enrollment-without-azure-ad-premium)|

Organisaties die gebruik kunnen maken van automatische registratie kunnen ook instellen dat [apparaten bulksgewijs worden geregistreerd](windows-bulk-enroll.md) via de Windows Configuration Designer-app.

## <a name="multi-user-support"></a>Ondersteuning voor meerdere gebruikers

Intune biedt ondersteuning voor multi-beheer voor apparaten waarop de Windows 10-makersupdate wordt uitgevoerd en die zijn toegevoegd aan een Azure Active Directory-domein. Als standaardgebruikers zich aanmelden met hun Azure AD-referenties, krijgen ze apps en beleidsregels die zijn toegewezen aan hun gebruikersnaam. Gebruikers kunnen de bedrijfsportal op dit moment niet gebruiken voor selfservice scenario's zoals het installeren van apps.

[!INCLUDE [AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="simplify-windows-enrollment-without-azure-ad-premium"></a>Windows-inschrijving vereenvoudigen zonder Azure AD Premium
Om de inschrijving te vereenvoudigen, maakt u een DNS-alias (domeinnaamserver) (CNAME-recordtype) waardoor inschrijvingsaanvragen worden doorgestuurd naar Intune-servers. Anders moeten gebruikers die verbinding met Intune proberen te maken, tijdens de inschrijving de naam van de Intune-server invoeren.

**Stap 1: CNAME maken** (optioneel)<br>
Maak CNAME-DNS-bronrecords voor uw bedrijfsdomein. Als de website van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleidt naar enterpriseenrollment-s.manage.microsoft.com.

Hoewel het maken van CNAME-DNS-vermeldingen optioneel is, maken CNAME-records het voor gebruikers makkelijker om zich in te schrijven. Als er geen CNAME-inschrijvingsrecord wordt gevonden, wordt gebruikers gevraagd de MDM-servernaam (enrollment.manage.microscoft.com) handmatig in te voeren.

|Type|Hostnaam|Verwijst naar|TTL|
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.bedrijfsdomein.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 uur|
|CNAME|EnterpriseRegistration.bedrijfsdomein.com|EnterpriseRegistration.windows.net|1 uur|

Als het bedrijf meer dan één UPN-achtervoegsel gebruikt, moet u een CNAME maken voor elke domeinnaam en die allemaal laten verwijzen naar EnterpriseEnrollment-s.manage.microsoft.com. Gebruikers van Contoso gebruiken bijvoorbeeld de volgende indelingen voor hun e-mail/UPN:

- name@contoso.com
- name@us.contoso.com
- name@eu.contoso.com

De Contoso DNS-beheerder moet de volgende CNAME’s maken:

|Type|Hostnaam|Verwijst naar|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 uur|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 uur|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 uur|

`EnterpriseEnrollment-s.manage.microsoft.com`: biedt ondersteuning voor een omleiding naar de Intune-service met domeinherkenning vanuit de domeinnaam van het e-mailadres

Het kan 72 uur duren voordat wijzigingen in DNS-records zijn doorgegeven. U kunt de DNS-wijziging in Intune pas controleren wanneer de DNS-record is doorgegeven.

**Stap 2: CNAME controleren** (optioneel)<br>
1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Windows-inschrijving** > **CNAME-validatie**.
2. Voer in het vak **Domein** de bedrijfswebsite in en kies **Testen**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Gebruikers uitleggen hoe ze Windows-apparaten inschrijven
Laat uw gebruikers weten hoe ze hun Windows-apparaten kunnen inschrijven en wat ze kunnen verwachten nadat deze onder beheer zijn gebracht.

> [!NOTE]
> Eindgebruikers moeten toegang hebben tot de bedrijfsportalwebsite via Microsoft Edge om Windows-apps te bekijken die u hebt toegewezen voor specifieke versies van Windows. Andere browsers, zoals Google Chrome, Mozilla Firefox en Internet Explorer bieden geen ondersteuning voor deze manier van filteren.

Zie [Uw Windows-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows) voor inschrijvingsinstructies voor eindgebruikers. U kunt gebruikers ook verwijzen naar het artikel [Welke gegevens kan mijn bedrijf zien wanneer ik mijn apparaat inschrijf in Intune?](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows)

>[!IMPORTANT]
> Als u automatische MDM-inschrijving niet hebt ingeschakeld maar Windows 10-apparaten hebt die zijn samengevoegd in Azure AD, worden na de inschrijving twee records weergegeven in de Intune-console. U kunt dit gedrag beëindigen. Hiervoor moeten gebruikers met samengevoegde apparaten in Azure AD met hetzelfde account naar **Accounts** > **Toegang tot werk- of schoolaccount** en **Verbinden** gaan. 

Zie [Bronnen over de eindgebruikerservaring in Microsoft Intune](end-user-educate.md) voor meer informatie over taken voor eindgebruikers.

## <a name="next-steps"></a>Volgende stappen

- [Overwegingen bij het beheren van Windows-apparaten met Intune in Azure](intune-legacy-pc-client.md).
