---
# required metadata

title: Een aangepaste domeinnaam configureren | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Een aangepaste domeinnaam configureren

In Intune wordt standaard de domeinnaam **<domain>. onmicrosoft.com** gebruikt, die is gemaakt toen u zich abonneerde op de service. Als uw organisatie eigenaar is van een aangepast domein, kunt u Intune configureren om dat domein te gebruiken in plaats van de domeinnaam die bij uw abonnement wordt geleverd.

Voordat u nieuwe gebruikersaccounts maakt of accounts synchroniseert vanuit de on-premises Active Directory, raden we u ten zeerste aan om te bepalen of u alleen het domein .onmicrosoft.com gebruikt of dat u een of meer van uw aangepaste domeinnamen toevoegt. Het configureren van een aangepast domein vóór het toevoegen van gebruikers kan het beheer van gebruikersidentiteiten voor uw abonnement vereenvoudigen doordat de gebruikers zich kunnen aanmelden met de referenties die ze gebruiken voor toegang tot andere domeinbronnen.

Wanneer u zich op een cloudservice van Microsoft abonneert, wordt uw exemplaar van die service een [tenant van Microsoft Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), dat identiteits- en adreslijstservices voor uw cloudservice biedt. En omdat de taken voor het configureren van Intune om de aangepaste domeinnaam van uw organisatie te gebruiken, dezelfde zijn als voor andere Azure AD-tenants, kunt u de informatie en procedures uit [Uw domein toevoegen](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/) gebruiken..

> [!TIP]
> Zie [Conceptueel overzicht van aangepaste domeinnamen in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/) voor meer informatie over het gebruik van uw aangepaste domein met een cloudservice van Microsoft..

### Volgende stappen
Gefeliciteerd. U hebt zojuist stap 2 van de *Snelstartgids voor Intune* voltooid.

>[!div class="step-by-step"]

>[&larr; **Aanmelden bij Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md)     [**Gebruikers toevoegen aan Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  


<!--HONumber=May16_HO1-->


