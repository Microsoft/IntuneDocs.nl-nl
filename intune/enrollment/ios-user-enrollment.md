---
title: iOS-apparaten inschrijven - Gebruikersinschrijving
titleSuffix: Microsoft Intune
description: Hier vindt u meer informatie over het instellen van gebruikersinschrijving voor iOS en iPadOS.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/2/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 57162664d6ca3a35696e56088c4e86acadf45371
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/04/2019
ms.locfileid: "71955324"
---
# <a name="set-up-ios-and-ipados-user-enrollment-preview"></a>Gebruikersinschrijving voor iOS en iPadOS instellen (preview)

U kunt Intune instellen om iOS- en iPadOS-apparaten in te schrijven met het gebruikersinschrijvingsproces van Apple. Gebruikersinschrijving biedt beheerders een gestroomlijnde subset van beheeropties vergeleken met andere inschrijvingsmethoden.

Zie de [ondersteunde acties, wachtwoorden en andere opties voor gebruikersinschrijving](ios-user-enrollment-supported-actions.md) voor meer informatie over de beschikbare opties bij gebruikersinschrijving.

> [!NOTE]
> Ondersteuning voor het proces van Apple voor gebruikersinschrijving in Intune is momenteel als preview-versie beschikbaar.

## <a name="prerequisites"></a>Vereisten
- [Mobile Device Management-autoriteit (MDM)](../fundamentals/mdm-authority-set.md)
- [Apple MDM-pushcertificaat](apple-mdm-push-certificate-get.md)
- [Beheerde Apple-id's](https://support.apple.com/guide/apple-business-manager/mdm1c9622977/web).

## <a name="create-a-user-enrollment-profile-in-intune"></a>Een gebruikersinschrijvingsprofiel maken in Intune

Met een inschrijvingsprofiel worden de instellingen gedefinieerd die worden toegepast op een groep apparaten tijdens de inschrijving. 

1. Kies in de Intune-portal **Apparaatinschrijving** > **Apple-inschrijving** > **Inschrijvingstypen (preview)**  > **Profiel maken** > **iOS**. In dit profiel bepaalt u de inschrijvingservaring voor uw iOS- en iPadOS-eind gebruikers op apparaten die niet zijn ingeschreven via een bedrijfsmethode van Apple. Als u wijzigingen wilt aanbrengen, kunt u dit profiel bewerken nadat u het hebt gemaakt.

    ![Apple-inschrijvingsprofiel maken](./media/ios-user-enrollment/create-profile.png)

2. Voer op de pagina **Basisinformatie** een **Naam** en een **Beschrijving** voor het profiel in voor administratieve doeleinden. Gebruikers zien deze gegevens niet. U kunt dit veld **Naam** gebruiken om een dynamische groep te maken in Azure Active Directory. Gebruik de profielnaam om de parameter enrollmentProfileName te definiëren om apparaten aan dit inschrijvingsprofiel toe te wijzen. Meer informatie over [Azure Active Directory dynamic groups](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#rules-for-devices) (dynamische Azure Active Directory-groepen).

    ![Pagina Basisinformatie](./media/ios-user-enrollment/basics-page.png)


3. Selecteer **Volgende**.

4. Op de pagina **Instellingen** kunt u ervoor kiezen om gebruikers de keuze te geven welk inschrijvingstype ze willen gebruiken. U kunt ook een standaardwaarde instellen.

    ![Pagina Instellingen](./media/ios-user-enrollment/settings-page.png)

    - Als u wilt dat alle gebruikers in dit profiel gebruikersinschrijving gebruiken, voert u de volgende stappen uit:
        1. Selecteer **Niet geconfigureerd** bij **De gebruiker moet het apparaattype selecteren**.
        2. Selecteer **Gebruikersinschrijving** bij **Standaardinschrijving**.
    - Als u wilt dat alle gebruikers in dit profiel apparaatinschrijving gebruiken, voert u de volgende stappen uit:
        1. Selecteer **Niet geconfigureerd** bij **De gebruiker moet het apparaattype selecteren**.
        2. Selecteer **Apparaatinschrijving** bij **Standaardinschrijving**.
    - Als u wilt dat alle gebruikers in deze groep kunnen kiezen welk inschrijvingstype ze willen gebruiken, selecteert u **De gebruiker moet het apparaattype kiezen** bij **Vereist**. Wanneer gebruikers hun apparaten inschrijven, krijgen ze de mogelijkheid om te kiezen tussen **Ik ben eigenaar van dit apparaat** en **(Bedrijf) is eigenaar van dit apparaat**. Als ze de eerste optie selecteren, wordt het apparaat ingeschreven via gebruikersinschrijving. Als ze de laatste optie selecteren, wordt het apparaat ingeschreven via apparaatinschrijving. Als gebruikers **Ik ben eigenaar dit apparaat** kiezen, wordt een andere optie weergegeven om te kiezen of ze het hele apparaat of alleen aan werk gerelateerde apps en gegevens willen beveiligen. De keuze van eindgebruikers of ze de eigenaar van het apparaat zijn, bepaalt alleen welk inschrijvingstype op hun apparaat wordt geïmplementeerd. Deze gebruikerskeuze wordt niet weergegeven in het kenmerk Apparaateigendom in Intune. Zie [Toegang tot uw bedrijfsbronnen instellen voor uw iOS-apparaat](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) voor meer informatie over de gebruikerservaring.
    
    > [!NOTE]
    > De volgende kennisgeving is onjuist en wordt verwijderd uit de gebruikersinterface.
    > 'Voor voorwaardelijke toegang om te werken op apparaten die zijn getarget met gebruikersinschrijving, moet u de Azure Authenticator-app pushen als vereiste app voor deze gebruikersgroep om eenmalige aanmelding en Workplace Join in te schakelen.'
    > Als beheerder hoeft u geen actie te ondernemen om de Authenticator-app naar uw gebruikers te pushen. Uw gebruikers krijgen in de bedrijfsportal opdracht de Authenticator-app te installeren om het gebruikersinschrijvingsproces te voltooien om ervoor te zorgen dat deze scenario's goed functioneren.

5. Selecteer **Volgende**.

6. Kies op de pagina **Toewijzingen** de gebruikersgroepen waaraan u dit profiel wilt toewijzen. U kunt ervoor kiezen het profiel toe te wijzen aan alle gebruikers of aan specifieke groepen. Alle gebruikers in de geselecteerde groepen gebruiken het hierboven gekozen inschrijvingstype. Apparaatgroepen worden niet ondersteund voor inschrijvingsscenario's voor gebruikers, omdat die functie is gebaseerd op gebruikers-id's in plaats van op apparaten. U kunt ervoor kiezen het profiel toe te wijzen aan alle gebruikers of aan specifieke groepen.

    ![Pagina Toewijzingen](./media/ios-user-enrollment/assignments-page.png)

7. Selecteer **Volgende**.

8. Op de pagina **Controleren en maken** controleert u uw keuzes en selecteert u vervolgens **Maken** om het profiel aan de gebruikers toe te wijzen.

    ![Pagina Toewijzingen](./media/ios-user-enrollment/assignments-page.png)


## <a name="profile-priority"></a>Prioriteit van profiel

Als u meerdere typen inschrijvingsprofielen hebt gemaakt, is het mogelijk de volgorde waarin ze worden toegepast te wijzigen.

1. Kies in Intune in Azure Portal de optie **Apparaatinschrijving** > **Apple-inschrijving** > **Inschrijvingstypen (preview)** .
2. Sleep de profielen in de lijst en zet deze neer in de volgorde waarin u deze wilt toepassen.

Als er conflicten tussen profielen voor een gebruiker optreden, wordt het profiel met de hoogste prioriteit toegepast voor de gebruiker.


