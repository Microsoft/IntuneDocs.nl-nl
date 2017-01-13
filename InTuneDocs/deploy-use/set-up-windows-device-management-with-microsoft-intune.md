---
title: Windows-apparaatbeheer instellen met Microsoft Intune | Microsoft Docs
description: "Schakel het beheer van mobiele apparaten (MDM) in voor Windows-pc’s, waaronder Windows 10-apparaten met Microsoft Intune."
keywords: 
author: staciebarker
manager: stabar
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 31d58d9973cca4023186731a5411c9c9e830e32a
ms.openlocfilehash: e24251a066349e23beb94b75a66c5710ba7e41f1


---

# <a name="set-up-windows-device-management"></a>Windows apparaatbeheer instellen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Als Intune-beheerder kunt u de registratie en het beheer voor Windows-pc's op twee manieren inschakelen:

- **[Automatische registratie met Azure Active Directory](#azure-active-directory-enrollment)**: Windows 10- en Windows 10 Mobile-gebruikers registreren hun apparaat door een werk- of schoolaccount toe te voegen op het apparaat.

- **[Registreren via de bedrijfsportal](#set-up-company-portal-app-enrollment)**: gebruikers van Windows 8.1 en hoger kunnen hun apparaten registreren door de bedrijfsportal-app te downloaden en te installeren, en vervolgens de inloggegevens van hun werk- of schoolaccount in de app in te voeren.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-company-portal-app-enrollment"></a>Registratie via de bedrijfsportal-app instellen
U kunt toestaan dat gebruikers hun apparaat installeren en registreren met de bedrijfsportal-app van Intune. Als u DNS CNAME-bronrecords maakt, kunnen gebruikers verbinding maken met Intune en bij Intune worden ingeschreven zonder een servernaam te hoeven opgeven.

1. **Intune instellen**<br>
Als u dit nog niet hebt gedaan, moet u het beheer van mobiele apparaten voorbereiden door de [autoriteit voor het beheer voor mobiele apparaten (MDM) in te stellen](prerequisites-for-enrollment.md#step-2-set-mdm-authority) op **Microsoft Intune** en vervolgens MDM in te stellen.

2. **CNAME-records maken** (optioneel)<br>Maak **CNAME**-DNS-bronrecords voor uw bedrijfsdomein. Als de website van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleidt naar enterpriseenrollment.manage.microsoft.com.

    Als u in DNS een CNAME hebt geconfigureerd waarmee EnterpriseEnrollment.contoso.com wordt omgeleid naar manage.microsoft.com, is het raadzaam om dit te vervangen door een CNAME in DNS waarmee EnterpriseEnrollment.contoso.com wordt omgeleid naar enterpriseenrollment-s.manage.microsoft.com. Deze wijziging wordt aanbevolen, omdat het eindpunt manage.microsoft.com voor inschrijvingen in een toekomstige versie wordt afgeschaft.

    CNAME-bronrecords moeten de volgende informatie bevatten:

  |TYPE|Hostnaam|Verwijst naar|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.bedrijfsdomein.com|EnterpriseEnrollment-s.manage.microsoft.com |1 uur|
  |CNAME|EnterpriseRegistration.bedrijfsdomein.com|EnterpriseRegistration.windows.net|1 uur|

  `EnterpriseEnrollment-s.manage.microsoft.com`: biedt ondersteuning voor een omleiding naar de Intune-service met domeinherkenning vanuit de domeinnaam van het e-mailadres

  `EnterpriseRegistration.windows.net`: biedt ondersteuning voor Windows 8.1- en Windows 10 Mobile-apparaten die met een werk- of schoolaccount bij Azure Active Directory worden geregistreerd

  Als uw bedrijf meerdere domeinen heeft voor gebruikersreferenties, maakt u CNAME-records voor elk domein.

  Als de website van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleidt naar EnterpriseEnrollment-s.manage.microsoft.com. Het kan 72 uur duren voordat wijzigingen in DNS-records zijn doorgegeven. U kunt de DNS-wijziging in Intune pas controleren wanneer de DNS-record is doorgegeven.

3.  **CNAME controleren**<br>Kies in de [Intune-beheerconsole](http://manage.microsoft.com) de optie **Beheer** &gt; **Mobile Device Management**&gt;**Windows**. Voer de URL in van het geverifieerde domein voor de bedrijfswebsite in het vak **Geef een geverifieerde domeinnaam op** en kies vervolgens **Automatische detectie testen**.

4.  **Optionele stappen**<br>De stap **Sideloadsleutels toevoegen** is niet nodig voor Windows 10. De stap **Certificaat voor ondertekening van programmacode uploaden** is alleen nodig als u Line-of-Business-apps (LOB) die niet beschikbaar zijn vanuit Windows Store wilt distribueren op apparaten.

6.  **Laat uw gebruikers weten hoe ze hun apparaten kunnen registreren en wat ze kunnen verwachten nadat deze onder beheer zijn gebracht.**

    Zie [Uw Windows-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows) voor inschrijvingsinstructies voor eindgebruikers.

    Zie [Bronnen over de eindgebruikerservaring in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune) voor meer informatie over taken voor eindgebruikers.


### <a name="see-also"></a>Zie tevens
[Vereisten voor het registreren van apparaten in Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Dec16_HO3-->


