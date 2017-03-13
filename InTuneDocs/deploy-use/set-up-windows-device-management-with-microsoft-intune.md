---
title: Windows-apparaatbeheer instellen met Microsoft Intune | Microsoft Docs
description: Het beheer van mobiele apparaten (MDM) inschakelen voor Windows-apparaten met Microsoft Intune.
keywords: 
author: NathBarn
manager: angrobe
ms.date: 02/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 255c3e47464ac7670a971881cf399e8e2bb17044
ms.openlocfilehash: 4acbae2aba4cff21286d45cb7cb1691864c281dc
ms.lasthandoff: 02/28/2017


---

# <a name="set-up-windows-device-management"></a>Windows apparaatbeheer instellen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Gebruik een van de volgende methoden om inschrijving in te stellen voor Windows-apparaten:

- [**Automatische inschrijving met Azure Active Directory Premium voor Windows 10 en Windows 10 Mobile**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Deze methode is alleen van toepassing op Windows 10- en Windows 10 Mobile-apparaten.
 -  Azure Active Directory Premium moet zijn geïnstalleerd als u deze methode wilt gebruiken. Anders moet u de inschrijvingsmethode voor Windows 8.1 en Windows Phone 8.1 gebruiken.
 -  Als u ervoor kiest automatische inschrijving niet in te schakelen, moet u de inschrijvingsmethode voor Windows 8.1 en Windows Phone 8.1 gebruiken.


- [**Windows 8.1- en Windows Phone 8.1-inschrijving door CNAME te configureren**](#set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname)
 - U moet deze methode gebruiken als u Windows 8.1- en Windows Phone 8.1-apparaten wilt registreren.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname"></a>Inschrijving van Windows 8.1 en Windows Phone 8.1 door CNAME te configureren
U kunt toestaan dat gebruikers hun apparaat installeren en inschrijven met de bedrijfsportal-app van Intune. Als u DNS CNAME-bronrecords maakt, kunnen gebruikers verbinding maken met Intune en bij Intune worden ingeschreven zonder een servernaam te hoeven opgeven.

### <a name="step-1-set-up-intune"></a>Stap 1: Intune instellen

Als u dit nog niet hebt gedaan, moet u het beheer van mobiele apparaten voorbereiden door de [autoriteit voor het beheer voor mobiele apparaten (MDM) in te stellen](prerequisites-for-enrollment.md#step-2-set-mdm-authority) op **Microsoft Intune** en vervolgens MDM in te stellen.

### <a name="step-2-create-cnames-optional"></a>Stap 2: CNAME-records maken (optioneel)

Maak **CNAME**-DNS-bronrecords voor uw bedrijfsdomein. Als de website van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleidt naar enterpriseenrollment-s.manage.microsoft.com.


   Hoewel het maken van CNAME-DNS-vermeldingen optioneel is, maken CNAME-records het voor gebruikers makkelijker om zich in te schrijven. Als er geen CNAME-inschrijvingsrecord wordt gevonden, wordt gebruikers gevraagd de MDM-servernaam (enrollment.manage.microscoft.com) handmatig in te voeren.

   CNAME-bronrecords moeten de volgende informatie bevatten:

  |TYPE|Hostnaam|Verwijst naar|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.bedrijfsdomein.com|EnterpriseEnrollment-s.manage.microsoft.com |1 uur|
  |CNAME|EnterpriseRegistration.bedrijfsdomein.com|EnterpriseRegistration.windows.net|1 uur|

  `EnterpriseEnrollment-s.manage.microsoft.com`: biedt ondersteuning voor een omleiding naar de Intune-service met domeinherkenning vanuit de domeinnaam van het e-mailadres

  `EnterpriseRegistration.windows.net`: biedt ondersteuning voor Windows 8.1- en Windows 10 Mobile-apparaten die met een werk- of schoolaccount bij Azure Active Directory worden geregistreerd

  Als uw bedrijf meerdere domeinen heeft voor gebruikersreferenties, maakt u CNAME-records voor elk domein.

  Als de website van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleidt naar EnterpriseEnrollment-s.manage.microsoft.com. Het kan 72 uur duren voordat wijzigingen in DNS-records zijn doorgegeven. U kunt de DNS-wijziging in Intune pas controleren wanneer de DNS-record is doorgegeven.

### <a name="step-3-verify-cname"></a>Stap 3: CNAME controleren

Kies in de [Intune-beheerconsole](http://manage.microsoft.com) de optie **Beheer** &gt; **Mobile Device Management**&gt;**Windows**. Voer de URL in van het geverifieerde domein voor de bedrijfswebsite in het vak **Geef een geverifieerde domeinnaam op** en kies vervolgens **Automatische detectie testen**.

### <a name="step-4-tell-your-users-how-to-enroll-their-devices-and-what-to-expect-after-theyre-brought-into-management"></a>Stap 4: Laat uw gebruikers weten hoe ze hun apparaten kunnen registreren en wat ze kunnen verwachten nadat deze onder beheer zijn gebracht.

   Zie [Uw Windows-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows) voor inschrijvingsinstructies voor eindgebruikers.

   Zie [Eindgebruikers instructies geven over Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune) en [Richtlijnen voor eindgebruikers van Windows-apparaten](../enduser/using-your-windows-device-with-intune.md) voor meer informatie over taken voor eindgebruikers.

### <a name="see-also"></a>Zie tevens
[Vereisten voor het registreren van apparaten in Microsoft Intune](prerequisites-for-enrollment.md)

