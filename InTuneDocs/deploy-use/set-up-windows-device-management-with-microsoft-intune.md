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
translationtype: Human Translation
ms.sourcegitcommit: 771aed4e1c57171183b9a9ea7d9e0f702dc1859c
ms.openlocfilehash: f6014c5500b05762d123b2285ef859d67382e402
ms.lasthandoff: 04/06/2017


---

# <a name="set-up-windows-device-management"></a>Windows apparaatbeheer instellen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Gebruik een van de volgende methoden om inschrijving in te stellen voor Windows-apparaten:

- [**Automatische inschrijving met Azure Active Directory Premium voor Windows 10**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Deze methode is alleen beschikbaar voor Windows 10-apparaten.
 -  Azure Active Directory Premium moet zijn geïnstalleerd als u deze methode wilt gebruiken.
 -  Als u ervoor kiest automatische inschrijving niet in te schakelen, moet u de inschrijvingsmethode voor Windows 8.1 en Windows Phone 8.1 gebruiken.

- [**Inschrijving zonder de automatische inschrijving van Azure AD Premium**](#enable-windows-enrollment-without-azure-ad-premium)
 - U moet deze methode gebruiken als u Windows 8.1- en Windows Phone 8.1-apparaten wilt registreren.
 - U kunt deze methode voor apparaten met Windows 8.1 en hoger gebruiken, als u geen gebruik wilt maken van Azure Active Directory (AD) Premium.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-automatic-enrollment"></a>Windows-inschrijving zonder automatische inschrijving inschakelen
U kunt gebruikers zelf het installeren en inschrijven van hun apparaten laten uitvoeren zonder automatische Azure AD Premium-inschrijving. Nadat u een licentie hebt toegewezen aan een gebruikersaccount, kan die gebruiker het account toevoegen aan een Windows-apparaat en akkoord gaan met de inschrijving van het apparaat voor beheer. Als u DNS CNAME-bronrecords maakt, kunnen gebruikers verbinding maken met Intune en bij Intune worden ingeschreven zonder een servernaam te hoeven opgeven.

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
Kies in de [Intune-beheerconsole](http://manage.microsoft.com) de optie **Beheer** &gt; **Mobile Device Management**&gt;**Windows**. Voer de URL in van het geverifieerde domein voor de bedrijfswebsite in het vak **Geef een geverifieerde domeinnaam op** en kies vervolgens **Automatische detectie testen**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Gebruikers uitleggen hoe ze Windows-apparaten inschrijven
Laat uw gebruikers weten hoe ze hun Windows-apparaten kunnen inschrijven en wat ze kunnen verwachten nadat deze onder beheer zijn gebracht.
Zie [Uw Windows-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows) voor inschrijvingsinstructies voor eindgebruikers. U kunt gebruikers ook de informatie in [What can my IT admin see on my device](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) (Wat kan de IT-beheerder op mijn apparaat zien?) laten lezen.

Zie [Bronnen over de eindgebruikerservaring in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune) voor meer informatie over taken voor eindgebruikers.

### <a name="see-also"></a>Zie tevens
[Vereisten voor het registreren van apparaten in Microsoft Intune](prerequisites-for-enrollment.md)

