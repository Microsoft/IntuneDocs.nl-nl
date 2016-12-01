---
title: Een aangepaste domeinnaam configureren | Microsoft Intune
description: Een aangepaste domeinnaam voor uw Intune-abonnement toevoegen
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: 9fe78bca15ffee1e5e0e7e3758ff70b6bc92b619


---


# <a name="configure-a-custom-domain-name"></a>Een aangepaste domeinnaam configureren

Wanneer uw organisatie zich registreert voor een cloudservice van Microsoft, zoals Intune, krijgt u een initiële domeinnaam die wordt gehost in Azure Active Directory (AD) en er ongeveer als volgt uitziet: **uwdomein.onmicrosoft.com**. In dit voorbeeld is **uwdomein** de domeinnaam die u hebt gekozen toen u zich registreerde, en is **onmicrosoft.com** het achtervoegsel dat wordt toegewezen aan de accounts die u aan uw abonnement toevoegt. Als uw organisatie eigenaar is van een aangepast domein, kunt u Intune configureren om dat domein te gebruiken in plaats van de domeinnaam die bij uw abonnement wordt geleverd.

Voordat u gebruikersaccounts maakt of de on-premises Active Directory synchroniseert, wordt ten zeerste aangeraden om te bepalen of u alleen het domein .onmicrosoft.com gebruikt of dat u een of meer van uw aangepaste domeinnamen toevoegt. Het configureren van een aangepast domein vóór het toevoegen van gebruikers kan het beheer van gebruikersidentiteiten voor uw abonnement vereenvoudigen doordat de gebruikers zich kunnen aanmelden met de referenties die ze gebruiken voor toegang tot andere domeinbronnen.

Wanneer u zich op een cloudservice van Microsoft abonneert, wordt uw exemplaar van die service een [tenant van Microsoft Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), dat identiteits- en adreslijstservices voor uw cloudservice biedt. En omdat de taken voor het configureren van Intune om de aangepaste domeinnaam van uw organisatie te gebruiken, dezelfde zijn als voor andere Azure AD-tenants, kunt u de informatie en procedures uit [Uw domein toevoegen](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/) gebruiken.

> [!TIP]
> Zie [Conceptueel overzicht van aangepaste domeinnamen in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/) voor meer informatie over het gebruik van uw aangepaste domein met een cloudservice van Microsoft.

U kunt die initiële domeinnaam niet wijzigen of verwijderen. U kunt echter wel uw eigen aangepaste domeinnamen voor gebruik met Intune toevoegen, controleren of verwijderen, wat handig is als u uw bedrijfsidentiteit wilt behouden.

## <a name="to-add-and-verify-your-custom-domain"></a>Aangepaste domeinen toevoegen en controleren

1. Ga naar [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx) en meld u aan bij uw beheerdersaccount.

2. Kies in het navigatievenster **Instellingen** &gt; **Domeinen**.

3. Kies **Domein toevoegen** en typ uw aangepaste domeinnaam.

4. Het weergegeven dialoogvenster **Domein controleren** bevat de waarden die u nodig hebt om de TXT-record in uw DNS-hostingprovider te maken.
    - **GoDaddy-gebruikers**: u wordt vanuit de Office 365-beheerportal doorgestuurd naar de aanmeldingspagina van GoDaddy. Nadat u uw referenties hebt ingevoerd en de overeenkomst hebt geaccepteerd waarmee u toestemming voor het wijzigen van het domein geeft, wordt de TXT-record automatisch aangemaakt. U kunt ook de [TXT-record aanmaken](https://support.office.com/en-us/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a?ui=en-US&rs=en-US&ad=US).
    - **Register.com-gebruikers**: volg de [stapsgewijze instructies](https://support.office.com/en-us/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e?ui=en-US&rs=en-US&ad=US#BKMK_verify) om de TXT-record te maken.

    > [!TIP]
    > Zorg ervoor dat u voor [het inschrijven van Windows-apparaten](/Intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) een DNS-alias (CNAME) maakt en dat u wijzigingen in uw DNS-hostingprovider aanbrengt.

De stappen voor het toevoegen en controleren van een aangepast domein kunnen ook worden [uitgevoerd in Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-add-domain/).

Bij hybride clouds kunt u na het toevoegen van uw aangepaste domeinnaam en de controle of deze eigendom is van uw organisatie gebruikersaccounts in uw on-premises Active Directory blijven beheren en deze vervolgens synchroniseren met Azure AD.

## <a name="to-synchronize-on-premises-users-with-azure-ad"></a>On-premises gebruikers synchroniseren met Azure AD##

1. [Voeg het UPN-achtervoegsel](https://technet.microsoft.com/en-us/library/cc772007.aspx) toe voor uw aangepaste domein in uw on-premises Active Directory.
2. Stel het nieuwe UPN-achtervoegsel in voor de on-premises gebruikers die u van plan bent te importeren.
3. Voer [Azure AD Connect-synchronisatie](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) uit om uw on-premises gebruikers te integreren met Azure AD.
4. Als de accountgegevens van de gebruikers zijn gesynchroniseerd, kunt u vervolgens Microsoft Intune-licenties toewijzen via de [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx).

### <a name="see-also"></a>Zie tevens

[Over uw initiële onmicrosoft.com-domein in Office 365](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US)

[Wat u moet weten voordat u met Microsoft Intune aan de slag gaat](what-to-know-before-you-start-microsoft-intune.md)
### <a name="next-steps"></a>Volgende stappen
Gefeliciteerd. U hebt zojuist stap 2 van de *Snelstartgids voor Intune* voltooid.

>[!div class="step-by-step"]

>[&larr; **Aanmelden bij Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md)     [**Gebruikers toevoegen aan Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  



<!--HONumber=Nov16_HO4-->


