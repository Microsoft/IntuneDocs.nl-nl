---
# required metadata

title: Wat gebeurt er als u de inschrijving van uw apparaat bij Intune ongedaan maakt? | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Wat gebeurt er als u de inschrijving van uw apparaat bij Intune ongedaan maakt?

Wanneer u de bedrijfsportal-app op uw apparaat verwijdert, wordt uw apparaat ook uitgeschreven bij Intune. Gebruik de koppeling die overeenkomt met het type apparaat dat u gebruikt, voor aanvullende informatie over wat er gebeurt.

- [Windows 10 Mobile, 8.1, Windows 8, Windows 7, Vista](#windows-10-mobile--8-1,-windows-8,-windows-7,-vista)
- [Windows 10, Windows 8.1 of Windows Phone 8](#windows-10--windows-8-1-or-windows-phone-8)
- [Windows RT met Windows 8.1 of Windows RT](#windows-rt-running-windows-8-1-or-windows-rt)


## Windows 10, Windows 8.1, Windows 8, Windows 7, Vista

-   Uw apparaat wordt niet meer weergegeven in de bedrijfsportal en u kunt geen apps meer installeren via de bedrijfsportal.

-   Als u de Intune-clientsoftware hebt geïnstalleerd, wordt deze van uw computer verwijderd.

-   De Intune Endpoint Protection-software wordt van de computer verwijderd. Als op de computer andere anti-virussoftware is geïnstalleerd en deze software is uitgeschakeld, wordt deze mogelijk weer ingeschakeld nadat Intune Endpoint Protection is verwijderd. Controleer uw computer nadat u deze van de bedrijfsportal hebt verwijderd.

    > [!IMPORTANT]
    > Als de andere anti-virussoftware niet opnieuw is ingeschakeld of als er geen andere anti-virussoftware is geïnstalleerd, is uw computer mogelijk blootgesteld aan virussen en kwaadaardige software.

-   Alle instellingen die op het apparaat zijn gewijzigd toen u dit toevoegde, bijvoorbeeld het uitschakelen van de camera, zijn niet meer van toepassing.

-   De computer ontvangt geen automatische software-updates of antivirussoftware-updates van de Intune-service meer. Afhankelijk van hoe de computer is geconfigureerd, ontvangt deze mogelijk wel nog updates van de Windows Server Update Services, Windows Update of Microsoft Update.

Bovendien geldt voor Windows 8.1 het volgende:

-   U kunt geen bedrijfs-apps en bedrijfsgegevens meer op het apparaat gebruiken.

-   Een aantal mail-apps, zoals Windows Mail, hebben geen toegang meer tot bedrijfse-mail die op het apparaat is opgeslagen.

-   Mogelijk kunt u geen verbinding met uw bedrijfsnetwerk maken met behulp van Wi-Fi of een VPN.

-   Mogelijk hebt u vanaf het apparaat geen toegang meer tot een aantal bedrijfsresources, zoals bestandsshares of interne websites.

## Windows 10 Mobile, Windows Phone 8.1 of Windows Phone 8

-   De bedrijfsportal-app wordt verwijderd van uw apparaat, wat betekent dat het apparaat niet meer in de bedrijfsportal wordt weergegeven en u geen apps vanuit de bedrijfsportal-app of vanaf de website van de bedrijfsportal kunt installeren.

-   U kunt geen bedrijfs-apps en bedrijfsgegevens meer op het apparaat gebruiken.

-   Alle instellingen die op het apparaat zijn gewijzigd toen u dit hebt toegevoegd (bijvoorbeeld het uitschakelen van de camera of een vereiste wachtwoordlengte) zijn niet meer van toepassing.

    > [!IMPORTANT]
    > De enige uitzondering hierop vormen de coderingsbeleidsregels, die van toepassing blijven. Als uw bedrijfsbeleid vereist dat de Windows Phone wordt gecodeerd, is er maar één manier om uw telefoon te decoderen: u moet de telefoon opnieuw instellen met het menu **Instellingen** op de Windows Phone.

## Windows RT met Windows 8.1 of Windows RT

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


### Zie tevens
[Uw Windows-apparaat gebruiken met Intune](using-your-windows-device-with-intune.md)

<!--HONumber=May16_HO1-->


