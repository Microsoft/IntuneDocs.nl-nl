---
title: Wat gebeurt er als u de registratie van uw Windows-apparaat ongedaan maakt? | Microsoft Docs
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c
searchScope:
- User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3de9589c46250727b1994381c24c68e6e2b90da2
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---


# <a name="what-happens-if-you-unenroll-your-windows-device-from-intune"></a>Wat gebeurt er als u de registratie van uw Windows-apparaat bij Intune ongedaan maakt?

Met de koppelingen aan de rechterkant van de pagina, onder **In dit artikel**, kunt u zoeken naar informatie over het type apparaat dat u gebruikt.


## <a name="windows-10-windows-81-windows-8-windows-7-windows-vista"></a>Windows 10, Windows 8.1, Windows 8, Windows 7, Windows Vista

-   Uw apparaat wordt niet meer weergegeven in de bedrijfsportal en u kunt geen apps meer installeren via de bedrijfsportal.

-   Als u de Intune-clientsoftware hebt geïnstalleerd, wordt deze van uw computer verwijderd.

-   De Intune Endpoint Protection-software wordt van de computer verwijderd. Als op de computer andere anti-virussoftware is geïnstalleerd en deze software is uitgeschakeld, kan de software weer worden ingeschakeld nadat Intune Endpoint Protection is verwijderd. Controleer uw computer nadat u deze van de bedrijfsportal hebt verwijderd.

    > [!IMPORTANT]
    > Als de andere anti-virussoftware niet opnieuw is ingeschakeld of als er geen andere anti-virussoftware is geïnstalleerd, is uw computer mogelijk blootgesteld aan virussen en kwaadaardige software.

-   Alle instellingen die op het apparaat zijn gewijzigd toen u dit toevoegde (zoals het uitschakelen van de camera) zijn niet meer van toepassing.

-   De computer ontvangt geen automatische software-updates of antivirussoftware-updates van de Intune-service meer. Afhankelijk van hoe de computer is geconfigureerd, ontvangt deze mogelijk wel nog updates van de Windows Server Update Services, Windows Update of Microsoft Update.

Bovendien geldt voor Windows 8.1 het volgende:

-   U kunt geen bedrijfs-apps en bedrijfsgegevens meer op het apparaat gebruiken.

-   Enkele mail-apps, zoals Windows Mail, hebben geen toegang meer tot bedrijfse-mail die op het apparaat is opgeslagen.

-   Mogelijk kunt u geen verbinding met uw bedrijfsnetwerk maken met behulp van Wi-Fi of een VPN.

-   Mogelijk hebt u vanaf het apparaat geen toegang meer tot een aantal bedrijfsresources, zoals bestandsshares of interne websites.

## <a name="windows-10-mobile-and-windows-phone-81"></a>Windows 10 Mobile en Windows Phone 8.1

-   De bedrijfsportal-app wordt van uw apparaat verwijderd. Dit betekent dat uw apparaat niet meer wordt weergegeven in de bedrijfsportal en u geen apps meer kunt installeren via de bedrijfsportal-app of de bedrijfsportal-website.

-   U kunt geen bedrijfs-apps en bedrijfsgegevens meer op het apparaat gebruiken.

-   Instellingen die op het apparaat zijn gewijzigd toen u dit hebt toegevoegd (bijvoorbeeld het uitschakelen van de camera of een vereiste wachtwoordlengte), zijn niet meer van toepassing.

    > [!IMPORTANT]
    > De enige uitzondering hierop vormen de coderingsbeleidsregels, die gewoon van toepassing blijven. Als uw bedrijfsbeleid vereist dat u uw Windows Phone codeert, kunt u uw telefoon alleen decoderen door de telefoon opnieuw in te stellen met het menu **Instellingen**.

## <a name="windows-rt-running-windows-81"></a>Windows RT met Windows 8.1

-   De bedrijfsportal-app wordt van uw apparaat verwijderd. Dit betekent dat uw apparaat niet meer wordt weergegeven in de bedrijfsportal en dat u geen apps kunt installeren via de bedrijfsportal.

-   U kunt geen bedrijfs-apps en bedrijfsgegevens meer op het apparaat gebruiken.

-   Instellingen die op het apparaat zijn gewijzigd toen u dit hebt toegevoegd (bijvoorbeeld het uitschakelen van de camera of een vereiste wachtwoordlengte), zijn niet meer van toepassing.

-   Mogelijk kunt u geen verbinding meer met uw bedrijfsnetwerk maken met behulp van Wi-Fi of een VPN.

-   Mogelijk hebt u vanaf het apparaat geen toegang meer tot een aantal bedrijfsresources, zoals bestandsshares of interne websites.

-   Enkele mail-apps, zoals Windows Mail, hebben geen toegang meer tot bedrijfse-mail die op het apparaat is opgeslagen.

Wanneer u een Windows RT-apparaat verwijdert, gebeurt het volgende:

-   De bedrijfsportal-app wordt van uw apparaat verwijderd. Dit betekent dat uw apparaat niet meer wordt weergegeven in de bedrijfsportal en dat u geen apps kunt installeren via de bedrijfsportal.

-   U kunt geen bedrijfs-apps en bedrijfsgegevens meer op het apparaat gebruiken.

-   Instellingen die op het apparaat zijn gewijzigd toen u dit hebt toegevoegd (bijvoorbeeld het uitschakelen van de camera of een vereiste wachtwoordlengte), zijn niet meer van toepassing.

Neem contact op met uw IT-beheerder als u vragen hebt. Controleer of de contactgegevens beschikbaar zijn op de [bedrjifsportalwebsite](http://portal.manage.microsoft.com).

