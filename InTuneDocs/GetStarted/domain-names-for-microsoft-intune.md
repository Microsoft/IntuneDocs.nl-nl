---
# required metadata

title: Domeinnamen voor Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---



# Domeinnamen voor Microsoft Intune

Lees dit onderwerp en andere vereisten in [Wat u moet weten voor u met Microsoft Intune begint](what-to-know-before-you-start-microsoft-intune.md) voordat u Microsoft Intune instelt..

Wanneer uw organisatie zich registreert voor een cloudservice van Microsoft, zoals Intune, krijgt u een initiële domeinnaam die er ongeveer als volgt uitziet: **contoso.onmicrosoft.com**. In dit voorbeeld is **contoso** de domeinnaam die u hebt gekozen toen u zich registreerde, en is **onmicrosoft.com** het achtervoegsel dat wordt toegewezen aan accounts die u aan uw abonnement toevoegt. Nadat u het registratieproces hebt voltooid, kunt u die domeinnaam niet wijzigen. Als algemeen beheerder kunt u echter uw eigen aangepaste domeinnamen voor uw organisatie met de service gebruiken of domeinen verwijderen die u eerder hebt toegevoegd.

Wanneer u het domein onmicrosoft gebruikt, ontvangt elke gebruiker die u importeert, standaard het achtervoegsel **onmicrosoft.com** voor zijn UPN (User Principal Name).

Als u een domeinnaam wilt gebruiken waarvan u eigenaar bent, in plaats van de naam die u bij de registratie hebt gekregen, kunt u de domeinnaam aan Azure Active Directory toevoegen. Nadat u het domein hebt toegevoegd en is gecontroleerd dat u de eigenaar bent, kunt u accounts en groepen maken die de domeinnaam bevatten door DNS-resourcerecords op uw DNS-hostprovider te wijzigen. U vereenvoudigt het beheer van gebruikersaccounts wanneer u een aangepast domein wilt gaan gebruiken, door een aangepaste domeinnaam voor uw abonnement te configureren voordat u gebruikers van uw lokale Active Directory synchroniseert.

Het configureren van domeinnamen en DNS-bronrecords voor Intune is hetzelfde als voor andere Azure Active Directory-tenants. Zie [Uw aangepaste domeinnaam toevoegen om aanmelden met Azure Active Directory te vereenvoudigen](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/) voor instructies.

### Zie tevens
[Wat u moet weten voordat u met Microsoft Intune begint](what-to-know-before-you-start-microsoft-intune.md)


<!--HONumber=May16_HO1-->


