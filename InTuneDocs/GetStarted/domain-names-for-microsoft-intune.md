---
title: Domeinnamen voor Microsoft Intune | Microsoft Intune
description: domeinnaam voor Intune toevoegen
keywords: 
author: andredm7
manager: swadhwa
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 38159f6dbcae2eeb4dca47141e60eed12cd7f6ee
ms.openlocfilehash: abcf37e7ec3150b5a2fe4cda910631f83d4c510a


---



# Aangepaste domeinnamen met Microsoft Intune

Wanneer uw organisatie zich registreert voor een cloudservice van Microsoft, zoals Intune, krijgt u een initiële domeinnaam die wordt gehost in Azure Active Directory en er ongeveer als volgt uitziet: **uwdomein.onmicrosoft.com**. In dit voorbeeld is **uwdomein** de domeinnaam die u hebt gekozen toen u zich registreerde, en is **onmicrosoft.com** het achtervoegsel dat wordt toegewezen aan de accounts die u aan uw abonnement toevoegt.

U kunt die initiële domeinnaam niet wijzigen of verwijderen. U kunt echter wel uw eigen aangepaste domeinnamen voor gebruik met Intune toevoegen, controleren of verwijderen, wat handig is als u uw bedrijfsidentiteit wilt behouden.

## Aangepaste domeinen toevoegen en controleren 

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

## On-premises gebruikers synchroniseren met Azure AD##

1. [Voeg het UPN-achtervoegsel](https://technet.microsoft.com/en-us/library/cc772007.aspx) toe voor uw aangepaste domein in uw on-premises Active Directory.
2. Stel het nieuwe UPN-achtervoegsel in voor de on-premises gebruikers die u van plan bent te importeren.
3. Voer [Azure AD Connect-synchronisatie](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) uit om uw on-premises gebruikers te integreren met Azure AD.
4. Als de accountgegevens van de gebruikers zijn gesynchroniseerd, kunt u vervolgens Microsoft Intune-licenties toewijzen via de [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx).

### Zie tevens

[Over uw initiële onmicrosoft.com-domein in Office 365](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US)

[Wat u moet weten voordat u met Microsoft Intune aan de slag gaat](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Oct16_HO2-->


