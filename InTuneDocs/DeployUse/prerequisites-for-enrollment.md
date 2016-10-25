---
title: Vereisten voor registratie van mobiele apparaten | Microsoft Intune
description: Mobile Device Management (MDM)-vereisten instellen en voorbereidingen treffen voor het inschrijven van verschillende besturingssystemen.
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44fd4af0-f9b0-493a-b590-7825139d9d40
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 77c8df8f1886786a2e772429d93b034798b22a66
ms.openlocfilehash: 8c500a5bfd59f801d1177a681fa9d55d1aa1ee0e


---

# Vereisten voor Mobile Device Management in Intune
Als u wilt dat uw medewerkers hun mobiele apparaten kunnen inschrijven bij Intune, zijn de volgende stappen vereist. Dezelfde stappen zijn vereist voor het beheren van apparaten die eigendom zijn van het bedrijf.

|Stappen|Details|  
|-----------|-------------|  
|**Stap 1:** [Afhankelijkheden van apparaatinschrijving](#step-1-device-enrollment-dependencies)|Zorg ervoor dat uw aangepaste domeinnaam is geconfigureerd en dat de netwerkcommunicatie gereed is|  
|**Stap 2:** [De instantie voor beheer van mobiele apparaten instellen](#step-2-set-mobile-device-management-authority)|De instantie voor beheer van mobiele apparaten definieert de service die wordt toegewezen aan uw apparaten|
|**Stap 3:** [De Intune-bedrijfsportal configureren](#step-3-configure-the-intune-company-portal)|Configureer gebruikersgerichte instellingen voor de bedrijfsportalapp|  
|**Stap 4:** [Intune-gebruikerslicenties toewijzen](#step-4-assign-intune-user-licenses)|Wijs Intune-licenties toe aan gebruikers zodat ze apparaten kunnen inschrijven|
|**Stap 5:** [Apparaatbeheer instellen](#step-5-set-up-device-management)|Schakel platformspecifieke instellingen in voor iOS- en Windows-beheer. Android-apparaten vereisen geen aanvullende configuratie.|

Zoekt u Intune met Configuration Manager?
> [!div class="button"]
[SCCM-documenten weergeven >](https://docs.microsoft.com/sccm/mdm/deploy-use/setup-hybrid-mdm)

## Stap 1: Afhankelijkheden van apparaatinschrijving

Voordat u het inschrijven van mobiele apparaten inschakelt, moet u ervoor zorgen dat u:
- [De vereiste netwerk-URL's en -poorten hebt gecontroleerd](../get-started/network-infrastructure-requirements-for-microsoft-intune)
- [Uw domeinnaam hebt toegevoegd en gecontroleerd](../get-started/domain-names-for-microsoft-intune)

## Stap 2: De instantie voor beheer van mobiele apparaten instellen
De MDM-instantie definieert de beheerservice die gemachtigd is voor het beheren van een reeks apparaten. De opties voor de MDM-instantie bevatten Intune zelf en Configuration Manager met Intune. Als u Configuration Manager als beheerinstantie instelt, kunnen er geen andere services voor het Mobile Device Management worden gebruikt.

>[!IMPORTANT]
> Overweeg zorgvuldig of u mobiele apparaten wilt beheren met Intune alleen (onlineservice) of met System Center Configuration Manager met Intune (on-premises softwareoplossing in combinatie met de onlineservice). Nadat de instantie voor het Mobile Device Management is ingesteld, kan deze niet meer worden gewijzigd.



1.  Kies in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) de optie **Beheer** &gt; **Mobile Device Management**.

2.  Klik in de lijst **Taken** op **Instantie voor beheer van mobiele apparaten instellen**. Het dialoogvenster **Instantie voor beheer van mobiele apparaten instellen** wordt geopend.

    ![Het dialoogvenster Instantie voor Mobile Device Management instellen](../media/intune-mdm-authority.png)

3.  Intune vraagt u te bevestigen dat u Intune wilt gebruiken als uw MDM-instantie. Schakel het selectievakje in en kies vervolgens **Ja** als u mobiele apparaten wilt beheren met Microsoft Intune.

## Stap 3: De Intune-bedrijfsportal configureren

De Intune-bedrijfsportal is de plaats waar gebruikers toegang hebben tot bedrijfsgegevens en algemene taken kunnen uitvoeren, zoals apparaten registreren, apps installeren en naar ondersteuningsinformatie van uw IT-afdeling zoeken.

> [!TIP]
> Wanneer u de bedrijfsportal aanpast, zijn de configuraties zowel van toepassing op de website als op de apps van de bedrijfsportal.

Een aangepaste bedrijfsportal geeft uw eindgebruikers een vertrouwde en efficiënte ervaring. Hiervoor hoeft u zich enkel als tenant of servicebeheerder aan te melden bij de [Microsoft Intune-beheerconsole](https://manage.microsoft.com), **Beheerder**&gt;**Bedrijfsportal** te kiezen en de instellingen van de bedrijfsportal te configureren.

![beheerconsole-beheerder-werkruimte-comp-portalinstellingen](../media/cp_sa_cpsetup.PNG)

### Contactgegevens en privacyverklaring van bedrijf

De bedrijfsnaam wordt weergegeven als de titel van de bedrijfsportal. Gebruikers zien de contactgegevens en details in het scherm Contact opnemen met IT van de bedrijfsportal. Wanneer een gebruiker op de privacykoppeling klikt, wordt de privacyverklaring weergegeven.

|Veldnaam|Max. lengte|Meer informatie|
    |----------|------------------------|----------------|
    |Bedrijfsnaam|40|Deze naam wordt weergegeven als de titel van de bedrijfsportal. **Opmerking**: Uitsluitend alfanumerieke tekens. Dit veld ondersteunt geen speciale tekens.|
    |Naam van contactpersoon IT-afdeling|40|Deze naam wordt weergegeven op de pagina **Contact opnemen met IT**.|
    |Telefoonnummer IT-afdeling|20|Dit contacttelefoonnummer wordt weergegeven op de pagina **Contact opnemen met IT**.|
    |E-mailadres IT-afdeling|40|Dit contactadres wordt weergegeven op de pagina **Contact opnemen met IT**. U moet een geldig e-mailadres invoeren in de notatie **alias@domeinnaam.com**.|
    |Aanvullende informatie|120|Deze informatie wordt weergegeven op de pagina **Contact opnemen met IT**.|
    |URL van privacyverklaring van bedrijf|79|U kunt de privacyverklaring van uw eigen bedrijf opgeven. Deze wordt dan weergegeven wanneer gebruikers in de bedrijfsportal op de privacykoppelingen klikken. U moet een geldige URL opgeven in de notatie https://www.contoso.com.|

### Contactpersonen voor ondersteuning
Aan gebruikers in de bedrijfsportal wordt de ondersteuningswebsite weergegeven voor toegang tot onlineondersteuning.

|Veldnaam|Max. lengte|Meer informatie|
    |----------|------------------------|----------------|
    |URL van ondersteuningswebsite|150|Als u over een ondersteuningswebsite voor uw gebruikers beschikt, kunt u hier de URL opgeven. De URL moet in de notatie https://www.contoso.com worden opgegeven. Als u geen URL opgeeft, wordt op de pagina **Contact opnemen met IT** in de bedrijfsportal niets weergegeven voor de ondersteuningswebsite.|
    |Naam website|40|Deze naam is de beschrijvende naam die wordt weergegeven voor de URL naar de ondersteuningswebsite. Als u een URL van een ondersteuningswebsite en geen beschrijvende naam opgeeft, wordt in de bedrijfsportal **Ga naar de website van IT** weergegeven op de pagina **Contact opnemen met IT**.|


### Aanpassing bedrijfshuisstijl

U kunt uw bedrijfsportal aanpassen met uw bedrijfslogo, bedrijfsnaam, themakleur en achtergrond.

|Veldnaam|Meer informatie|
    |----------|----------------|
    |Themakleur|Selecteer een themakleur die u wilt toepassen op de bedrijfsportal.|
    |Bedrijfslogo opnemen|Als u deze optie inschakelt, kunt u het bedrijfslogo uploaden dat u in uw bedrijfsportal wilt weergeven. U kunt twee logo's uploaden: één dat wordt weergegeven wanneer de achtergrond van de bedrijfsportal wit is en één dat wordt weergegeven wanneer de achtergrond van de bedrijfsportal de door u geselecteerde themakleur heeft. Beide logo’s moeten png- of jpg-bestanden zijn met een resolutie van maximaal 400 x 100 pixels en een grootte van maximaal 750 kB.|
    |Een achtergrond kiezen voor de bedrijfsportalapp|Deze instelling beïnvloedt alleen de achtergrond voor de bedrijfsportalapp.|


Nadat u uw wijzigingen hebt opgeslagen, kunt u de koppelingen onder aan de pagina **Bedrijfsportal** van de beheerconsole gebruiken om de bedrijfsportalwebsite weer te geven. Deze koppelingen kunnen niet worden gewijzigd. Wanneer een gebruiker zich aanmeldt, worden via deze koppelingen uw abonnementen weergegeven in de bedrijfsportal.

## Stap 4: Intune-gebruikerslicenties toewijzen

U gebruikt de **Office 365-beheerportal** om handmatig cloudgebruikers toe te voegen en licenties toe te wijzen aan zowel cloudgebruikersaccounts als accounts die vanuit uw on-premises Active Directory zijn gesynchroniseerd met Azure Active Directory (Azure AD). U kunt [on-premises gebruikers synchroniseren met Azure AD](../get-started/domain-names-for-microsoft-intune#to-synchronize-on-premises-users-with-azure-ad.md).

1.  Meld u met uw tenantbeheerdersreferenties aan bij de [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx).

2.  Selecteer het gebruikersaccount waaraan u een Intune-gebruikerslicentie wilt toewijzen en selecteer vervolgens **Microsoft Intune** voor de eigenschappen van het gebruikersaccount.

3.  Het gebruikersaccount wordt nu toegevoegd aan de Microsoft Intune-gebruikersgroep die de gebruikersmachtigingen voor het gebruik van de service toekent en de apparaten inschrijft voor beheer.

### On-premises gebruikers synchroniseren met Azure AD

1. [Voeg het UPN-achtervoegsel](https://technet.microsoft.com/en-us/library/cc772007.aspx) toe voor uw aangepaste domein in uw on-premises Active Directory.
2. Stel het nieuwe UPN-achtervoegsel in voor de on-premises gebruikers die u van plan bent te importeren.
3. Voer [Azure AD Connect-synchronisatie](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) uit om uw on-premises gebruikers te integreren met Azure AD.
4. Als de accountgegevens van de gebruikers zijn gesynchroniseerd, kunt u vervolgens Microsoft Intune-licenties toewijzen via de [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx).

## Stap 5: Apparaatbeheer instellen
Na het instellen van de MDM-instantie moet u apparaatbeheer instellen voor de besturingssystemen die uw organisatie wil ondersteunen. De stappen die voor het instellen van apparaatbeheer nodig zijn, verschillen per besturingssysteem. Android OS vereist bijvoorbeeld niet dat u iets doet in de Intune-beheerconsole. Aan de andere kant vereisen Windows en iOS een vertrouwensrelatie tussen apparaten en Intune voor het toestaan van beheer.

Stel het beheer in voor de volgende platformen:
- [Android](set-up-android-management-with-microsoft-intune.md)
- [iOS en Mac](set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Windows-pc’s en -laptops](set-up-windows-device-management-with-microsoft-intune.md)
- [Windows 10 Mobile en Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md)

U kunt ook:
 - Het [beheerdersaccount voor apparaatinschrijving](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) gebruiken om meerdere apparaten in te schrijven.
 - [Apparaten in bedrijfseigendom met IMEI-nummers opgeven](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) om apparaten in te schrijven en beleid te maken.



<!--HONumber=Oct16_HO2-->


