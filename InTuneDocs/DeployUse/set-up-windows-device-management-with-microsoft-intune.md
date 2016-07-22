---
# required metadata

title: Windows-apparaatbeheer instellen met Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows apparaatbeheer instellen
Met Intune kunt u BYOD ('Bring Your Own Device') instellen om Windows-pc’s in te schrijven en toegang te geven tot bedrijfse-mail en apps. In combinatie met Azure Active Directory beschikt u hiermee ook over een snelle manier om nieuwe Windows 10-apparaten onder beheer te stellen en toegang te krijgen tot bronnen zonder een nieuwe installatiekopie op de computer te installeren. Na inschrijving kunnen gebruikers zich aanmelden en kunnen op hun apparaten beleid, apps en instellingen worden toegepast met behulp van de Intune-beheerconsole. Als u dit wilt, kunt u ook [Windows Phone-beheer instellen met Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md) en [computers beheren met Intune-clientsoftware](manage-windows-pcs-with-microsoft-intune.md)

Door een DNS CNAME te maken, kunnen gebruikers verbinding maken met Intune en bij Intune worden ingeschreven zonder een servernaam te hoeven opgeven.

### Windows apparaatbeheer instellen

  1.  Maak een **CNAME** DNS-bronrecord voor het domein van uw bedrijf. Als de website van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleidt naar EnterpriseEnrollment-s.manage.microsoft.com. Als er meerdere geverifieerde domeinen zijn, maakt u voor elk domein een CNAME-record. De CNAME-bronrecords moeten de volgende informatie bevatten:

  |TYPE|Hostnaam|Verwijst naar|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 uur|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 uur|

    DNS record changes might take up to 72 hours to propagate. You cannot verify the DNS change in Intune until the DNS record propagates.

    **EnterpriseEnrollment-s.manage.microsoft.com** – Supports a redirect to the Intune service with domain recognition from the email’s domain name

    **EnterpriseRegistration.windows.net** – Supports Windows 8.1 and Windows 10 Mobile devices that will register with Azure Active Directory using their work or school account

  2.  Klik in de [Intune-beheerconsole](http://manage.microsoft.com) op **Beheer** &gt; **Mobile Device Management** &gt; **Windows**.
  ![Het dialoogvenster Windows-apparaatbeheer](../media/enroll-intune-winenr.png)
  3.  Typ de URL van het geverifieerde domein voor de bedrijfswebsite in het vak onder **Geef een geverifieerde domeinnaam op** en klik vervolgens op **Automatische detectie testen**..

### Zie tevens
[Bereid u voor op het registreren van apparaten in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


