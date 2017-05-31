---
title: Windows-apparaatbeheer instellen met Microsoft Intune | Microsoft Docs
description: Het beheer van mobiele apparaten (MDM) inschakelen voor Windows-apparaten met Microsoft Intune.
keywords: 
author: NathBarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: be2587f8ccb43632d861012416bbbca720698bb1
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="set-up-windows-device-management"></a>Windows apparaatbeheer instellen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Met de informatie in dit onderwerp kunnen IT-beheerders de inschrijving van Windows-apparaten vereenvoudigen voor hun gebruikers.  Windows-apparaten kunnen zonder extra stappen worden ingeschreven, maar u kunt het gemakkelijker maken voor uw gebruikers.

Vereenvoudiging van Windows-apparaatregistratie is afhankelijk van twee factoren:
- **Gebruikt u Azure Active Directory Premium?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) is opgenomen in Enterprise Mobility + Security en andere licentieplannen.
- **Welke versie van Windows-clients wordt ingeschreven?** <br>Windows 10-apparaten kunnen automatisch worden ingeschreven door het toevoegen van een werk- of schoolaccount. Eerdere versies moeten worden ingeschreven met de bedrijfsportal-app.

||**Azure AD Premium**|**Overige AD**|
|----------|---------------|---------------|  
|**Windows 10**|[Automatische inschrijving](#enable-windows-10-automatic-enrollment) |[Gebruikersinschrijving](#enable-windows-enrollment-without-azure-ad-premium)|
|**Eerdere Windows-versies**|[Gebruikersinschrijving](#enable-windows-enrollment-without-azure-ad-premium)|[Gebruikersinschrijving](#enable-windows-enrollment-without-azure-ad-premium)|

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-automatic-enrollment"></a>Windows-inschrijving zonder automatische inschrijving inschakelen
U kunt gebruikers zelf hun apparaten laten inschrijven, zonder automatische Azure AD Premium-inschrijving. Als u licenties hebt toegewezen, kunnen gebruikers zich registreren nadat ze hun werkaccount hebben toegevoegd aan apparaten die hun persoonlijke eigendom zijn of nadat ze hun apparaten die bedrijfseigendom zijn hebben toegevoegd aan uw Azure AD. Door een DNS-alias (CNAME-recordtype) te maken, kunnen gebruikers hun apparaten eenvoudiger inschrijven. Als u DNS CNAME-bronrecords maakt, kunnen gebruikers verbinding maken met Intune en bij Intune worden ingeschreven zonder een Intune-servernaam te hoeven opgeven.

**Stap 1: CNAME’s maken** (optioneel)<br>
Maak CNAME-DNS-bronrecords voor uw bedrijfsdomein. Als de website van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleidt naar enterpriseenrollment-s.manage.microsoft.com.

Hoewel het maken van CNAME-DNS-vermeldingen optioneel is, maken CNAME-records het voor gebruikers makkelijker om zich in te schrijven. Als er geen CNAME-inschrijvingsrecord wordt gevonden, wordt gebruikers gevraagd de MDM-servernaam (enrollment.manage.microscoft.com) handmatig in te voeren.

Als er meer dan één gecontroleerd domein is, maakt u een CNAME-record voor elk domein. De CNAME-resourcerecords moeten de volgende informatie bevatten:

CNAME-bronrecords moeten de volgende informatie bevatten:

|TYPE|Hostnaam|Verwijst naar|TTL|
|--------|-------------|-------------|-------|
|CNAME|EnterpriseEnrollment.bedrijfsdomein.com|EnterpriseEnrollment-s.manage.microsoft.com |1 uur|
|CNAME|EnterpriseRegistration.bedrijfsdomein.com|EnterpriseRegistration.windows.net|1 uur|

`EnterpriseEnrollment-s.manage.microsoft.com`: biedt ondersteuning voor een omleiding naar de Intune-service met domeinherkenning vanuit de domeinnaam van het e-mailadres

Als uw bedrijf meerdere domeinen heeft voor gebruikersreferenties, maakt u CNAME-records voor elk domein.

Als de website van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleidt naar EnterpriseEnrollment-s.manage.microsoft.com. Het kan 72 uur duren voordat wijzigingen in DNS-records zijn doorgegeven. U kunt de DNS-wijziging in Intune pas controleren wanneer de DNS-record is doorgegeven.

**Stap 2: CNAME controleren** (optioneel)<br>
Kies in de [Intune-beheerconsole](https://manage.microsoft.com) de optie **Beheer** &gt; **Mobile Device Management**&gt;**Windows**. Voer de URL in van het geverifieerde domein voor de bedrijfswebsite in het vak **Geef een geverifieerde domeinnaam op** en kies vervolgens **Automatische detectie testen**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Gebruikers uitleggen hoe ze Windows-apparaten inschrijven
Laat uw gebruikers weten hoe ze hun Windows-apparaten kunnen inschrijven en wat ze kunnen verwachten nadat deze onder beheer zijn gebracht.
Zie [Uw Windows-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows) voor inschrijvingsinstructies voor eindgebruikers. U kunt gebruikers ook de informatie in [What can my IT admin see on my device](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) (Wat kan de IT-beheerder op mijn apparaat zien?) laten lezen.

Zie [Bronnen over de eindgebruikerservaring in Microsoft Intune](/intune-classic/deploy-use/how-to-educate-your-end-users-about-microsoft-intune) voor meer informatie over taken voor eindgebruikers.

### <a name="see-also"></a>Zie tevens
[Vereisten voor het registreren van apparaten in Microsoft Intune](prerequisites-for-enrollment.md)

