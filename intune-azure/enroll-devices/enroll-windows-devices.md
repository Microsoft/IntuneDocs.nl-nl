---
title: Windows-apparaten inschrijven
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp wordt beschreven hoe u Mobile Device Management (MDM) in Intune voor Windows-apparaten inschakelt.'
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 03/15/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: a95aca706a4996d40e268a80c7c334ebb9854df5
ms.openlocfilehash: 6cbaf8414452f11f0aa97616bbed2cf164b49ac0
ms.lasthandoff: 03/15/2017


---

# <a name="enroll-windows-devices"></a>Windows-apparaten inschrijven

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Gebruik een van de volgende methoden om inschrijving in te stellen voor Windows-apparaten:

- [**Automatische inschrijving met Azure Active Directory Premium voor Windows 10 en Windows 10 Mobile**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Deze methode is alleen van toepassing op Windows 10- en Windows 10 Mobile-apparaten.
 -  Azure Active Directory Premium moet zijn geïnstalleerd als u deze methode wilt gebruiken. Anders moet u de inschrijvingsmethode voor Windows 8.1 en Windows Phone 8.1 gebruiken.
 -  Als u ervoor kiest automatische inschrijving niet in te schakelen, moet u de inschrijvingsmethode voor Windows 8.1 en Windows Phone 8.1 gebruiken.

- [**Windows 8.1- en Windows Phone 8.1-inschrijving door CNAME te configureren**](#simplify-enrollment-by-configuring-cname)
 - U moet deze methode gebruiken als u Windows 8.1- en Windows Phone 8.1-apparaten wilt registreren.
 - U kunt deze methode ook gebruiken als u geen Azure Active Directory (AD) Premium hebt.


## <a name="prerequisites"></a>Vereisten

Als enkele van de volgende vereisten nog niet beschikbaar zijn in Intune Azure Preview, moet u de bijbehorende taken uitvoeren in de klassieke Intune-beheerconsole.

- [Een aangepaste domeinnaam configureren](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [De MDM-instantie (Mobile Device Management)](set-mdm-authority.md) instellen op **Microsoft Intune**
- [De bedrijfsportal-app configureren](/intune-azure/manage-apps/company-portal-app.md)
- Licenties aan gebruikers toewijzen

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-workplace-enrollment"></a>Inschrijving van Windows-werkplek inschakelen

U kunt gebruikers zelf het installeren en inschrijven van hun apparaten laten uitvoeren zonder automatische Azure AD Premium-inschrijving. Als u DNS CNAME-bronrecords maakt, kunnen gebruikers verbinding maken met Intune en bij Intune worden ingeschreven zonder een servernaam te hoeven opgeven.

1. **CNAME-records maken** (optioneel)<br>
 Maak **CNAME**-DNS-bronrecords voor uw bedrijfsdomein. Als de website van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleidt naar enterpriseenrollment-s.manage.microsoft.com.

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

2.  **CNAME controleren**<br>Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**. Kies **Apparaten inschrijven** > **Windows-inschrijving** op de blade Intune. Voer de URL in van het geverifieerde domein voor de bedrijfswebsite in het vak **Geef een geverifieerde domeinnaam op** en kies vervolgens **Automatische detectie testen**.

3.  **Laat uw gebruikers weten hoe ze hun apparaten kunnen inschrijven en wat ze kunnen verwachten nadat deze onder beheer zijn gebracht.**

    Zie [Uw Windows-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows) voor inschrijvingsinstructies voor eindgebruikers. U kunt gebruikers ook de informatie in [What can my IT admin see on my device](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) (Wat kan de IT-beheerder op mijn apparaat zien?) laten lezen.

    Zie [Bronnen over de eindgebruikerservaring in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune) voor meer informatie over taken voor eindgebruikers.

Verder hoeft u niets te doen, tenzij u de bedrijfsportal op apparaten wilt implementeren.  Stap 2 en 3 in de beheerconsole kunnen worden genegeerd.

