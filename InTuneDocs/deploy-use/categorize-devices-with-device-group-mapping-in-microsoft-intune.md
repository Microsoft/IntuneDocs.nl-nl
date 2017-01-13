---
title: Apparaten categoriseren met apparaatgroeptoewijzing | Microsoft Docs
description: "Gebruik apparaatgroeptoewijzing van Microsoft Intune om apparaten te groeperen in categorieën die u definieert, zodat het voor u eenvoudiger wordt om die apparaten te beheren."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 28af253b0a0fe174478961810a26b45d8ac3d959

---

# <a name="categorize-devices-with-device-group-mapping-in-microsoft-intune"></a>Apparaten categoriseren met apparaatgroeptoewijzing in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Gebruik **apparaatgroeptoewijzing** van Microsoft Intune om apparaten automatisch aan groepen toe te voegen op basis van categorieën die u definieert, zodat het voor u eenvoudiger wordt om die apparaten te beheren. 

Voor apparaatgroeptoewijzing wordt gebruikgemaakt van de volgende werkstroom:
1. Categorieën maken die gebruikers kunnen kiezen bij het registreren van hun apparaat
2. U maakt nieuwe groepen of gebruikt bestaande groepen voor elke categorie die u wilt gebruiken. Afhankelijk van de versie van Intune die u gebruikt, zijn dit Intune-groepen of Azure Active Directory-beveiligingsgroepen.
2. U configureert regels waarmee de categorie die u kiest, wordt toegewezen aan de gemaakte apparaatgroep.
3. Wanneer eindgebruikers hun apparaat registreren, moeten ze een categorie kiezen uit de lijst met categorieën die u hebt geconfigureerd. Wanneer ze een keuze hebben gemaakt, wordt hun apparaat automatisch toegevoegd aan de bijbehorende apparaatgroep die u hebt gemaakt. Als een apparaat al is geregistreerd, wordt de eindgebruiker gevraagd een categorie te selecteren wanneer hij of zij de bedrijfsportal-app opnieuw opent.
4. Vervolgens kunt u beleidsregels en apps implementeren naar deze groepen.

U kunt alle apparaatcategorieën maken die u maar wilt, bijvoorbeeld:
* Verkooppuntapparaat
* Demonstratieapparaat
* Sales
* Boekhouding
* Manager

## <a name="important-information-about-a-change-in-group-management-for-intune"></a>Belangrijke informatie over een wijziging in groepsbeheer voor Intune

Naar aanleiding van uw feedback is Microsoft bezig het aantal verschillende methoden terug te brengen tot één methode voor groeperen en toepassen in Enterprise Mobility + Security. Daarom zetten we Intune-groepen binnenkort om in Azure Active Directory-beveiligingsgroepen. Na deze wijziging kunt u geen groepen meer maken met Intune. In plaats daarvan maakt u deze in de Azure-portal. Deze wijziging wordt stapsgewijs doorgevoerd. Zie [dit onderwerp](use-groups-to-manage-users-and-devices-with-microsoft-intune.md) voor de volledige informatie over deze wijziging en de bijbehorende tijdlijn.

### <a name="which-procedure-in-this-topic-should-you-use-to-configure-device-group-mapping"></a>Welke procedure in dit onderwerp moet u gebruiken voor het configureren van apparaatgroeptoewijzing?

Vanwege de gefaseerde implementatie van beveiliging op basis van Azure Active Directory-groepen, moet u de werkruimte **Groepen** in de [Intune-beheerconsole](https://manage.microsoft.com) openen om te bepalen welke procedure u moet gebruiken:

-  Als u een koppeling naar de Azure-portal ziet, gebruikt u geen Intune-groepen meer. Volg de onderstaande procedure [Apparaatgroeptoewijzing configureren voor Azure Active Directory-groepen](/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-azure-active-directory-groups).
-  Als u geen koppeling naar de Azure-portal ziet, gebruikt u nog Intune-groepen. Volg de onderstaande procedure [Apparaatgroeptoewijzing configureren voor Intune-groepen](/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-intune-groups).

## <a name="how-to-configure-device-group-mapping-for-intune-groups"></a>Apparaatgroeptoewijzing configureren voor Intune-groepen
1. Maak een Intune-apparaatgroep of kies een bestaande groep voor elke apparaatcategorie die u wilt gebruiken. Zie [Groepen gebruiken voor het beheren van gebruikers en apparaten met Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md) voor informatie over het maken van groepen.
2. Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Beheer**.
3. In de werkruimte **Beheer** vouwt u **Mobile Device Management** uit en kiest u vervolgens **Apparaatgroeptoewijzing**.
4. Op de pagina **Apparaatgroeptoewijzing** schakelt u apparaatgroeptoewijzing in.
5. Kies **Toevoegen** om een nieuwe toewijzingsregel te maken.
6. In het dialoogvenster **Regel voor apparaatgroeptoewijzing toevoegen** voert u de naam in van de categorie die u wilt maken. Kies daarna uit de vervolgkeuzelijst de apparaatverzameling waar u deze categorie aan wilt toewijzen. Kies **Toevoegen** wanneer u klaar bent.
7. Wanneer u de categorieën en groepen hebt toegevoegd, kiest u **Opslaan**.



## <a name="how-to-configure-device-group-mapping-for-azure-active-directory-groups"></a>Apparaatgroeptoewijzing configureren voor Azure Active Directory-groepen

### <a name="step-1---create-device-categories-in-the-intune-administration-console"></a>Stap 1: apparaatcategorieën maken in de Intune-beheerconsole
1. Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Beheer**.
3. In de werkruimte **Beheer** vouwt u **Mobile Device Management** uit en kiest u vervolgens **Apparaatcategorieën**.
4. Op de pagina **Apparaatcategorieën** ziet u een lijst waar u apparaatcategorieën kunt configureren: 
- U kunt een nieuwe apparaatcategorie toevoegen door een naam in te voeren en op **Toevoegen** te klikken.
- U kunt ook een categorie selecteren en deze vervolgens verwijderen door op **Verwijderen** te klikken.

Als u Azure Active Directory-beveiligingsgroepen maakt in stap 2, gebruikt u de naam van de apparaatcategorie.

### <a name="step-2---create-azure-active-directory-security-groups"></a>Stap 2: Active Directory-beveiligingsgroepen maken

In deze stap maakt u dynamische groepen in de Azure-portal op basis van de apparaatcategorie en de naam van de apparaatcategorie.

Zie het onderwerp [Geavanceerde regels maken met kenmerken](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) in de documentatie van Azure Active Directory om door te gaan.
Gebruik de informatie in dit onderwerp om een apparaatgroep met een geavanceerde regel te maken op basis van het kenmerk **deviceCategory** (apparaatcategorie).
Voorbeeld: (**device.deviceCategory -eq** "<*de naam van de apparaatcategorie in de Intune-beheerconsole*>")


## <a name="after-you-configure-device-groups"></a>Na het configureren van apparaatgroepen

Wanneer gebruikers hun apparaat registreren, krijgen ze een lijst te zien van de categorieën die u hebt geconfigureerd. Wanneer ze een categorie hebben gekozen en de registratie voltooien, wordt hun apparaat toegevoegd aan de Intune-apparaatgroep of Active Directory-beveiligingsgroep die overeenkomt met de gekozen categorie.

### <a name="see-also"></a>Zie tevens
[Groepen gebruiken voor het beheren van gebruikers en apparaten met Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


