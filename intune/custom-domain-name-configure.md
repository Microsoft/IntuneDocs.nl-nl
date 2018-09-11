---
title: Een aangepaste domeinnaam configureren
titlesuffix: Microsoft Intune
description: Een aangepaste domeinnaam voor uw Microsoft Intune-abonnement toevoegen
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-classic; get-started
ms.openlocfilehash: cbefc5ae5ef159c3c58a475f01a1513abb46ee90
ms.sourcegitcommit: 18f51ae8291b57562921e40fc364a5a60a59b139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2018
ms.locfileid: "44254068"
---
# <a name="configure-a-custom-domain-name"></a>Een aangepaste domeinnaam configureren

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

In dit onderwerp wordt aan beheerders uitgelegd hoe ze een DNS CNAME kunnen maken om hun aanmeldervaring met Microsoft Intune te vereenvoudigen en aan te passen.

Wanneer uw organisatie zich registreert voor een cloudservice van Microsoft, zoals Intune, krijgt u een initiële domeinnaam die wordt gehost in Azure Active Directory (AD) en er ongeveer als volgt uitziet: **uwdomein.onmicrosoft.com**. In dit voorbeeld is **uwdomein**de domeinnaam die u hebt gekozen toen u zich registreerde. **onmicrosoft.com** is het achtervoegsel dat wordt toegewezen aan accounts die u aan uw abonnement toevoegt. U kunt het aangepaste domein van uw bedrijf configureren om Intune te gebruiken in plaats van de domeinnaam die bij uw abonnement wordt geleverd.

Voordat u gebruikersaccounts maakt of de on-premises Active Directory synchroniseert, wordt ten zeerste aangeraden om te bepalen of u alleen het domein .onmicrosoft.com gebruikt of dat u een of meer van uw aangepaste domeinnamen toevoegt. Stel een aangepast domein in voordat u gebruikers toevoegt om het gebruikersbeheer te vereenvoudigen. Hiermee kunnen gebruikers zich aanmelden met de referenties die ze gebruiken voor toegang tot andere domeinbronnen.

Wanneer u zich op een cloudservice van Microsoft abonneert, wordt uw exemplaar van die service een [tenant van Microsoft Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), dat identiteits- en adreslijstservices voor uw cloudservice biedt. En omdat de taken voor het configureren van Intune om de aangepaste domeinnaam van uw organisatie te gebruiken, dezelfde zijn als voor andere Azure AD-tenants, kunt u de informatie en procedures uit [Uw domein toevoegen](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/) gebruiken.

> [!TIP]
> Zie voor meer informatie over aangepaste domeinen, [Conceptual overview of custom domain names in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/) (conceptueel overzicht van aangepaste domeinnamen in Azure Active Directory).

U kunt de initiële domeinnaam onmicrosoft.com niet wijzigen of verwijderen. U kunt aangepaste domeinnamen toevoegen, controleren of verwijderen met Intune om uw bedrijfsidentiteit helder te houden.

## <a name="to-add-and-verify-your-custom-domain"></a>Aangepaste domeinen toevoegen en controleren

1. Ga naar [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx) en meld u aan bij uw beheerdersaccount.

2. Kies in het navigatievenster **Configuratie** &gt; **Domeinen**.

3. Kies **Domein toevoegen** en typ uw aangepaste domeinnaam. Selecteer **Volgende**.
   ![Schermafbeelding van Office 365-beheercentrum met Instellingen > Domeinen geselecteerd en een nieuwe domeinnaam die wordt toegevoegd](./media/domain-custom-add.png)
4. Het weergegeven dialoogvenster **Domein controleren** bevat de waarden die u nodig hebt om de TXT-record in uw DNS-hostingprovider te maken.
    - **GoDaddy-gebruikers**: u wordt vanuit de Office 365-beheerportal doorgestuurd naar de aanmeldingspagina van GoDaddy. Nadat u uw referenties hebt ingevoerd en de overeenkomst hebt geaccepteerd waarmee u toestemming voor het wijzigen van het domein geeft, wordt de TXT-record automatisch aangemaakt. U kunt ook de [TXT-record aanmaken](https://support.office.com/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a).
    - **Register.com-gebruikers**: volg de [stapsgewijze instructies](https://support.office.com/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e#BKMK_verify) om de TXT-record te maken.

De stappen voor het toevoegen en controleren van een aangepast domein kunnen ook worden [uitgevoerd in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

Meer informatie [over uw initiële onmicrosoft.com-domein in Office 365](https://support.office.com/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A)
