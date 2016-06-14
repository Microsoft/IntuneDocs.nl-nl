---
# required metadata

title: Voorbereidingen voor het inschrijven van apparaten in Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Voorbereidingen voor het inschrijven van apparaten in Microsoft Intune
U moet apparaatinschrijving inschakelen zodat werknemers mobiele apparaten (inclusief Android, iOS, Windows Phone en Windows-pc's) bij Intune kunnen inschrijven. Voor het toestaan van inschrijving moet u een instantie voor het beheer van mobiele apparaten (Mobile Device Management, MDM) instellen, de Intune-bedrijfsportal configureren, licenties toewijzen en inschrijving inschakelen voor het apparaatplatform.

## <a name="BKMK_Set_MDM_Authority"></a>Instantie voor beheer van mobiele apparaten instellen
De MDM-instantie definieert de beheerservice met een machtiging voor het beheren van een reeks apparaten. Opties voor de MDM-instantie bevatten Intune zelf en Configuration Manager met Intune. Als u Configuration Manager als beheerinstantie instelt, kunnen er geen andere services voor het beheer van mobiele apparaten worden gebruikt.

>[!IMPORTANT]
> Overweeg zorgvuldig of u mobiele apparaten wilt beheren met Intune alleen (online service) of met System Center Configuration Manager met Intune (lokale softwareoplossing in combinatie met online service). Nadat de instantie voor het beheer van mobiele apparaten is ingesteld, kan deze niet meer worden gewijzigd.



1.  Klik in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) op **Beheer** &gt; **Beheer van mobiele apparaten**.

2.  Klik in de lijst **Taken** op **Instantie voor beheer van mobiele apparaten instellen**. Het dialoogvenster **Instantie voor beheer van mobiele apparaten instellen** wordt geopend.

    ![Het dialoogvenster Instantie voor beheer van mobiele apparaten instellen](../media/intune-mdm-authority.png)

3.  Intune vraagt u te bevestigen dat u Intune wilt gebruiken als uw MDM-instantie. Schakel het selectievakje in en klik vervolgens op **Ja** als u mobiele apparaten wilt beheren met Microsoft Intune.

## De Intune bedrijfsportal configureren en licenties toewijzen
In de Intune bedrijfsportal kunnen gebruikers toegang krijgen tot bedrijfsbronnen zoals apps, helpdeskinformatie vinden en niet-ingeschreven apparaten inschrijven. Voordat u apparaten gaat inschrijven, moet u [de bedrijfsportal configureren](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-7). U moet ook [gebruikerslicenties toewijzen](/intune/get-started/get-started-with-a-paid-subscription-to-microsoft-intune-step-4) om toegang tot Intune toe te staan.

## Apparaatbeheer instellen
Na het instellen van de MDM-instantie moet u apparaatbeheer instellen voor de besturingssystemen die uw organisatie wil ondersteunen. De stappen die voor het instellen van apparaatbeheer nodig zijn, verschillen per besturingssysteem. Android OS vereist bijvoorbeeld niet dat u iets doet in de Intune-beheerconsole. Aan de andere kant vereisen Windows en iOS een vertrouwensrelatie tussen apparaten en Intune voor het toestaan van beheer.

> [!div class="op_single_selector"]
- [Android-beheer instellen met Microsoft Intune](set-up-android-management-with-microsoft-intune.md)
- [Set up iOS and Mac management with Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Windows Phone-beheer instellen met Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md)
- [Windows apparaatbeheer instellen met Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md)

U kunt ook:
 - Het account [apparaatinschrijvingsmanager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) gebruiken om meerdere apparaten in te schrijven
 - [Apparaten in bedrijfseigendom met IMEI-nummers opgeven](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) om apparaten in te schrijven en beleid te maken


<!--HONumber=May16_HO1-->


