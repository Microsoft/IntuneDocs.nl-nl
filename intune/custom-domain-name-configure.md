---
title: Een aangepaste domeinnaam configureren
titleSuffix: Microsoft Intune
description: Een aangepaste domeinnaam voor uw Microsoft Intune-abonnement toevoegen
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4d0c3d11eb3a031f34704dcd9ecf16f3312ac818
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2019
ms.locfileid: "59567241"
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

1. Ga naar het [Microsoft 365-beheercentrum](https://admin.microsoft.com/) en meld u aan bij uw beheerdersaccount.

2. Kies in het navigatievenster **Configuratie** &gt; **Domeinen**.

3. Kies **Domein toevoegen** en typ uw aangepaste domeinnaam. Selecteer **Volgende**.
   ![Schermafbeelding van Microsoft 365-beheercentrum met Instellingen > Domeinen geselecteerd, en waar een nieuwe domeinnaam wordt toegevoegd](./media/domain-custom-add.png)
4. Het weergegeven dialoogvenster **Domein controleren** bevat de waarden die u nodig hebt om de TXT-record in uw DNS-hostingprovider te maken.
    - **GoDaddy-gebruikers**: In het Microsoft 365-beheercentrum wordt u naar de aanmeldingspagina van GoDaddy geleid. Nadat u uw referenties hebt ingevoerd en de overeenkomst hebt geaccepteerd waarmee u toestemming voor het wijzigen van het domein geeft, wordt de TXT-record automatisch aangemaakt. U kunt ook de [TXT-record aanmaken](https://support.office.com/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a).
    - **Register.com-gebruikers**: Volg de [stapsgewijze instructies](https://support.office.com/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e#BKMK_verify) om de TXT-record te maken.

De stappen voor het toevoegen en controleren van een aangepast domein kunnen ook worden [uitgevoerd in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

Meer informatie [over uw initiële onmicrosoft.com-domein in Office 365](https://support.office.com/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A)
