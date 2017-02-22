---
title: Windows-apparaten inschrijven | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp wordt beschreven hoe u Mobile Device Management (MDM) in Intune voor Windows-apparaten inschakelt.'
keywords: 
author: staciebarker
manager: stabar
ms.date: 02/09/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 45c32cf08e4d6fd570af287ed64411edc9d9b394
ms.openlocfilehash: ec623e7d102e8a8ddf1cc86a750f592ca765cfce


---

# <a name="enroll-windows-devices"></a>Windows-apparaten inschrijven 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Gebruik een van de volgende methoden om inschrijving in te stellen voor Windows-apparaten:

- **[Automatische inschrijving met Azure Active Directory Premium voor Windows 10 en Windows 10 Mobile](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)** 
 -  Deze methode is alleen van toepassing op Windows 10- en Windows 10 Mobile-apparaten.
 -  Azure Active Directory Premium moet zijn geïnstalleerd als u deze methode wilt gebruiken. Anders moet u de inschrijvingsmethode voor Windows 8.1 en Windows Phone 8.1 gebruiken.
 -  Als u ervoor kiest automatische inschrijving niet in te schakelen, moet u de inschrijvingsmethode voor Windows 8.1 en Windows Phone 8.1 gebruiken.


- **[Windows 8.1- en Windows Phone 8.1-inschrijving door CNAME te configureren](#set-up-windows-8.1-and-windows-phone-8.1-enrollment-by-configuring-cname)** 
 - U moet deze methode gebruiken als u Windows 8.1- en Windows Phone 8.1-apparaten wilt registreren.


## <a name="prerequisites"></a>Vereisten

Als enkele van de volgende vereisten nog niet beschikbaar zijn in Intune Azure Preview, moet u de bijbehorende taken uitvoeren in de klassieke Intune-beheerconsole.

- [Een aangepaste domeinnaam configureren](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [De MDM-instantie (Mobile Device Management)](set-mdm-authority.md) instellen op **Microsoft Intune**
- [De bedrijfsportal-app configureren](/intune-azure/manage-apps/company-portal-app.md)
- Licenties aan gebruikers toewijzen

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname"></a>Inschrijving van Windows 8.1 en Windows Phone 8.1 door CNAME te configureren

U kunt toestaan dat gebruikers hun apparaat installeren en inschrijven met de bedrijfsportal-app van Intune. Als u DNS CNAME-bronrecords maakt, kunnen gebruikers verbinding maken met Intune en bij Intune worden ingeschreven zonder een servernaam te hoeven opgeven.

1. **CNAME-records maken** (optioneel)<br>
 Maak **CNAME**-DNS-bronrecords voor uw bedrijfsdomein. Als de website van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleidt naar enterpriseenrollment-s.manage.microsoft.com.

    Hoewel het maken van CNAME-DNS-vermeldingen optioneel is, maken CNAME-records het voor gebruikers makkelijker om zich in te schrijven. Als er geen CNAME-inschrijvingsrecord wordt gevonden, wordt gebruikers gevraagd de MDM-servernaam (enrollment.manage.microscoft.com) handmatig in te voeren.

    Als u in DNS een CNAME hebt geconfigureerd waarmee EnterpriseEnrollment.contoso.com wordt omgeleid naar manage.microsoft.com, is het raadzaam om dit te vervangen door een CNAME in DNS waarmee EnterpriseEnrollment.contoso.com wordt omgeleid naar enterpriseenrollment-s.manage.microsoft.com. Deze wijziging wordt aanbevolen, omdat het eindpunt manage.microsoft.com voor inschrijvingen in een toekomstige versie wordt afgeschaft.

    Als er meer dan één gecontroleerd domein is, maakt u een CNAME-record voor elk domein. De CNAME-resourcerecords moeten de volgende informatie bevatten:

    CNAME-bronrecords moeten de volgende informatie bevatten:

  |TYPE|Hostnaam|Verwijst naar|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.bedrijfsdomein.com|EnterpriseEnrollment-s.manage.microsoft.com |1 uur|
  |CNAME|EnterpriseRegistration.bedrijfsdomein.com|EnterpriseRegistration.windows.net|1 uur|

  `EnterpriseEnrollment-s.manage.microsoft.com`: biedt ondersteuning voor een omleiding naar de Intune-service met domeinherkenning vanuit de domeinnaam van het e-mailadres

  `EnterpriseRegistration.windows.net`: biedt ondersteuning voor Windows 8.1- en Windows 10 Mobile-apparaten die met een werk- of schoolaccount bij Azure Active Directory worden geregistreerd

  Als uw bedrijf meerdere domeinen heeft voor gebruikersreferenties, maakt u CNAME-records voor elk domein.

  Als de website van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleidt naar EnterpriseEnrollment-s.manage.microsoft.com. Het kan 72 uur duren voordat wijzigingen in DNS-records zijn doorgegeven. U kunt de DNS-wijziging in Intune pas controleren wanneer de DNS-record is doorgegeven.

2.  **CNAME controleren**<br>Kies in de [Intune-beheerconsole](http://manage.microsoft.com) de optie **Beheer** &gt; **Mobile Device Management** &gt; **Windows Phone**. Voer de URL in van het geverifieerde domein voor de bedrijfswebsite in het vak **Geef een geverifieerde domeinnaam op** en kies vervolgens **Automatische detectie testen**.

3.  **Optionele stappen**<br>De stap **Sideloadsleutels toevoegen** is niet nodig voor Windows 10. <br>De stap **Certificaat voor ondertekening van programmacode uploaden** is alleen nodig als u Line-of-Business-apps (LOB) die niet beschikbaar zijn vanuit Windows Store wilt distribueren op apparaten.

4.  **Laat uw gebruikers weten hoe ze hun apparaten kunnen inschrijven en wat ze kunnen verwachten nadat deze onder beheer zijn gebracht.**

    Zie [Uw Windows-apparaat inschrijven bij Intune](https://docs.microsoft.com/en-us/intune/enduser/enroll-your-device-in-intune-windows) voor inschrijvingsinstructies voor eindgebruikers. U kunt gebruikers ook de informatie in [What can my IT admin see on my device](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) (Wat kan de IT-beheerder op mijn apparaat zien?) laten lezen.

    Zie [Bronnen over de eindgebruikerservaring in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune) voor meer informatie over taken voor eindgebruikers.

Verder hoeft u niets te doen, tenzij u de bedrijfsportal op apparaten wilt implementeren.  Stap 2 en 3 in de beheerconsole kunnen worden genegeerd.



<!--HONumber=Feb17_HO2-->


