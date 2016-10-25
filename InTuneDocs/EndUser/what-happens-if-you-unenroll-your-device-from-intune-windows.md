---
title: Wat gebeurt er als u de registratie van uw Windows-apparaat bij Intune ongedaan maakt? | Microsoft Intune
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08f31db90f324ef5f93076c4e13bfa5328a15adc
ms.openlocfilehash: ebd1300c490f3d69110a5f1920fd25d1dc5cb850


---


# Wat gebeurt er als u de registratie van uw Windows-apparaat bij Intune ongedaan maakt?

Met de koppelingen aan de rechterkant van de pagina, onder 'In dit artikel', kunt u zoeken naar informatie over het type apparaat dat u gebruikt.


## Windows 10, Windows 8.1, Windows 8, Windows 7, Vista

-   Uw apparaat wordt niet meer weergegeven in de bedrijfsportal en u kunt geen apps meer installeren via de bedrijfsportal.

-   Als u de Intune-clientsoftware hebt geïnstalleerd, wordt deze van uw computer verwijderd.

-   De Intune Endpoint Protection-software wordt van de computer verwijderd. Als op de computer andere anti-virussoftware is geïnstalleerd en deze software is uitgeschakeld, wordt deze mogelijk weer geregistreerd nadat Intune Endpoint Protection is verwijderd. Controleer uw computer nadat u deze van de bedrijfsportal hebt verwijderd.

    > [!IMPORTANT]
    > Als de andere anti-virussoftware niet opnieuw is ingeschakeld of als er geen andere anti-virussoftware is geïnstalleerd, is uw computer mogelijk blootgesteld aan virussen en kwaadaardige software.

-   Alle instellingen die op het apparaat zijn gewijzigd toen u dit toevoegde, bijvoorbeeld het uitschakelen van de camera, zijn niet meer van toepassing.

-   De computer ontvangt geen automatische software-updates of antivirussoftware-updates van de Intune-service meer. Afhankelijk van hoe de computer is geconfigureerd, ontvangt deze mogelijk wel nog updates van de Windows Server Update Services, Windows Update of Microsoft Update.

Bovendien geldt voor Windows 8.1 het volgende:

-   U kunt geen bedrijfs-apps en bedrijfsgegevens meer op het apparaat gebruiken.

-   Een aantal mail-apps, zoals Windows Mail, hebben geen toegang meer tot bedrijfse-mail die op het apparaat is opgeslagen.

-   Mogelijk kunt u geen verbinding met uw bedrijfsnetwerk maken met behulp van Wi-Fi of een VPN.

-   Mogelijk hebt u vanaf het apparaat geen toegang meer tot een aantal bedrijfsresources, zoals bestandsshares of interne websites.

## Windows 10 Mobile en Windows Phone 8.1

-   De bedrijfsportal-app wordt verwijderd van uw apparaat, wat betekent dat het apparaat niet meer in de bedrijfsportal wordt weergegeven en u geen apps vanuit de bedrijfsportal-app of vanaf de website van de bedrijfsportal kunt installeren.

-   U kunt geen bedrijfs-apps en bedrijfsgegevens meer op het apparaat gebruiken.

-   Alle instellingen die op het apparaat zijn gewijzigd toen u dit hebt toegevoegd (bijvoorbeeld het uitschakelen van de camera of een vereiste wachtwoordlengte) zijn niet meer van toepassing.

    > [!IMPORTANT]
    > De enige uitzondering hierop vormen de coderingsbeleidsregels, die van toepassing blijven. Als uw bedrijfsbeleid vereist dat de Windows Phone wordt gecodeerd, is er maar één manier om uw telefoon te decoderen: u moet de telefoon opnieuw instellen met het menu **Instellingen** op de Windows Phone.

## Windows RT met Windows 8.1

-   De bedrijfsportal-app wordt verwijderd van uw apparaat, wat betekent dat het apparaat niet meer in de bedrijfsportal wordt weergegeven en u geen apps vanuit de bedrijfsportal kunt installeren.

-   U kunt geen bedrijfs-apps en bedrijfsgegevens meer op het apparaat gebruiken.

-   Alle instellingen die op het apparaat zijn gewijzigd toen u dit hebt toegevoegd (bijvoorbeeld het uitschakelen van de camera of een vereiste wachtwoordlengte) zijn niet meer van toepassing.

-   Mogelijk kunt u geen verbinding meer met uw bedrijfsnetwerk maken met behulp van Wi-Fi of een VPN.

-   Mogelijk hebt u vanaf het apparaat geen toegang meer tot een aantal bedrijfsresources, zoals bestandsshares of interne websites.

-   Een aantal mail-apps, zoals Windows Mail, hebben geen toegang meer tot bedrijfse-mail die op het apparaat is opgeslagen.

Wanneer u een Windows RT-apparaat verwijdert, gebeurt het volgende:

-   De bedrijfsportal-app wordt verwijderd van uw apparaat, wat betekent dat het apparaat niet meer in de bedrijfsportal wordt weergegeven en u geen apps vanuit de bedrijfsportal kunt installeren.

-   U kunt geen bedrijfs-apps en bedrijfsgegevens meer op het apparaat gebruiken.

-   Alle instellingen die op het apparaat zijn gewijzigd toen u dit hebt toegevoegd (bijvoorbeeld het uitschakelen van de camera of een vereiste wachtwoordlengte) zijn niet meer van toepassing.

Neem contact op met de IT-beheerder als u vragen hebt. Ga naar de [bedrijfsportalwebsite](http://portal.manage.microsoft.com) voor de betreffende contactgegevens.




<!--HONumber=Oct16_HO2-->


