---
# required metadata

title: Welk probleem wordt opgelost met Azure RMS | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 06/02/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: b551c62d-5ac6-4359-85b3-90693e77b37f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Welke problemen worden opgelost met Azure RMS?

*Van toepassing op: Azure Rights Management, Office 365*

Gebruik de volgende tabel om bedrijfsvereisten of problemen te identificeren die uw organisatie mogelijk heeft, en hoe Azure RMS deze kunt oplossen.

|Vereiste of probleem|Opgelost door Azure RMS|
|--------------------------|-----------------------|
|Alle bestandstypen beveiligen|√ In de vorige implementatie van Rights Management konden alleen Office bestanden worden beveiligd, met systeemeigen beveiliging. Nu betekent [algemene beveiliging](../rms-client/sharing-app-dialog-box.md#what-s-the-difference-between-generic-protection-and-built-in-native-protection-) dat alle bestandstypen worden ondersteund.|
|Overal bestanden beveiligen|√ Wanneer een bestand wordt opgeslagen naar een locatie ([in-place beveiligen](../rms-client/sharing-app-protect-in-place.md)), blijft de beveiliging van toepassing op het bestand, zelfs als dit wordt gekopieerd naar opslag die niet onder het beheer staat van IT, zoals een cloudopslagservice.|
|Veilig bestanden delen via e-mail|√ Wanneer een bestand wordt gedeeld via e-mail ([beveiligd delen](../rms-client/sharing-app-protect-by-email.md)), wordt het bestand beveiligd als bijlage bij een e-mailbericht en worden instructies meegeleverd voor het openen van de beveiligde bijlage. De tekst van het e-mailbericht wordt niet versleuteld, zodat de ontvanger deze instructies altijd kan lezen. Het bijgevoegde document is echter beveiligd en alleen geautoriseerde gebruikers kunnen dit openen, zelfs als het e-mailbericht of het document wordt doorgestuurd naar anderen.|
|Controleren en bewaken|√ U kunt van uw beveiligde bestanden [het gebruik controleren en bewaken](../deploy-use/log-analyze-usage.md), zelfs nadat deze bestanden de grenzen van uw organisatie verlaten.<br /><br />U werkt bijvoorbeeld voor het bedrijf Contoso, Ltd. U werkt met drie personen van het bedrijf Fabrikam, Inc. aan een gezamenlijk project. U e-mailt deze drie personen een document dat u beveiligt en beperkt tot alleen-lezen. Controle van Azure RMS kan de volgende informatie leveren:<br /><br />- Of de mensen die u hebt opgegeven bij Fabrikam het document hebben geopend en wanneer.<br /><br />- Of personen die u niet hebt opgegeven, (vergeefs) hebben geprobeerd het document te openen, mogelijk omdat het document is doorgestuurd of opgeslagen op een gedeelde locatie waartoe anderen toegang hebben.<br /><br />- Of een van de opgegeven personen (vergeefs) heeft geprobeerd het document af te drukken of te wijzigen.|
|Ondersteuning voor alle gebruikte apparaten, niet alleen Windows-computers|√ [Ondersteunde apparaten](../get-started/requirements-client-devices.md) omvatten:<br /><br />- Windows-computers en -telefoons<br /><br />- Mac-computers<br /><br />- iOS-tablets en -telefoons<br /><br />- Android-tablets en -telefoons|
|Ondersteuning voor business-to-business-samenwerking|√ Omdat Azure RMS een cloudservice is, hoeft u niet expliciet vertrouwensrelaties met andere organisaties te configureren voordat u beveiligde inhoud met hen kunt delen. Als ze al een Office 365- of een Azure AD-adreslijst hebben, wordt samenwerking tussen verschillende organisaties automatisch ondersteund. Als ze nog geen adreslijst hebben, kunnen gebruikers zich aanmelden voor het gratis abonnement voor [RMS voor personen](rms-for-individuals.md).|
|Ondersteuning voor on-premises services en Office 365|√ Azure RMS werkt niet alleen [naadloos met Office 365](office-apps-services-support.md), u kunt de oplossing ook gebruiken met de volgende on-premises services wanneer u de [RMS-connector](../deploy-use/deploy-rms-connector.md) implementeert:<br /><br />- Exchange Server<br /><br />- SharePoint Server<br /><br />- Windows Server met infrastructuur voor bestandsclassificatie|
|Eenvoudige activering|√ Voor het [activeren van de Rights Management-service](../deploy-use/activate-service.md) voor gebruikers zijn slechts een paar muisklikken in de klassieke Azure-portal vereist.|
|Mogelijkheid om naar behoefte te schalen in uw organisatie|√ Omdat Azure RMS wordt uitgevoerd als een cloudservice met de Azure-elasticiteit voor schalen, hoeft u geen extra on-premises servers in te richten of te implementeren.|
|Mogelijkheid om eenvoudig en flexibel beleidsregels maken|√ [Aangepaste sjablonen voor rechtenbeleid](../deploy-use/configure-custom-templates.md) bieden een snelle en eenvoudige oplossing voor beheerders om beleidsregels toe te passen en voor gebruikers om juiste beveiligingsniveau voor elk document toe te passen en de toegang te beperken tot personen binnen uw organisatie.<br /><br />Als u bijvoorbeeld een bedrijfsbreed, strategisch document wilt delen met alle medewerkers, kunt u een alleen-lezenbeleid toepassen voor alle interne werknemers. Voor een gevoeliger document, zoals een financieel rapport, kunt u vervolgens de toegang beperken tot alleen leidinggevenden.|
|Brede ondersteuning voor toepassingen|√ Azure RMS heeft een nauwe integratie met Microsoft Office-toepassingen en -services en breidt de ondersteuning uit voor andere toepassingen met de RMS-toepassing voor delen.<br /><br />√ De [Microsoft Rights Management SDK](../develop/developers-guide.md#software-development-kits) biedt uw interne ontwikkelaars en softwareleveranciers API's voor het schrijven van aangepaste toepassingen die Azure RMS ondersteunen.<br /><br />Zie [Other applications that support the RMS APIs](api-support.md) (Andere toepassingen die ondersteuning bieden voor de RMS API's) voor meer informatie.|
|IT moet controle houden over gegevens|√ Organisaties kunnen ervoor kiezen om hun eigen tenantsleutel te beheren en de oplossing '[Bring Your Own Key](../plan-design/plan-implement-tenant-key.md)' (BYOK) en de tenantsleutel op te slaan in Hardware Security Modules (HSM's).<br /><br />√ Ondersteuning voor controle en [logboekregistratie van het gebruik](../deploy-use/log-analyze-usage.md) zodat u voor zakelijke inzichten kunt analyseren, op misbruik kunt controleren en (als u een informatielek hebt) een forensische analyse uitvoeren.<br /><br />√ Gedelegeerde toegang met de [functie supergebruiker](../deploy-use/configure-super-users.md) zorgt ervoor dat IT altijd toegang heeft tot beveiligde inhoud, zelfs als een document is beveiligd door een werknemer die vervolgens de organisatie verlaat. Ter vergelijking, met oplossingen voor peer-to-peer-versleuteling bestaat het risico dat toegang tot bedrijfsgegevens verloren gaat.<br /><br />√ Synchroniseer [alleen de mapkenmerken die Azure RMS nodig heeft](/active-directory/active-directory-aadconnectsync-attributes-synchronized#azure-rms) ter ondersteuning van een algemene identiteit voor uw on-premises Active Directory-accounts met een [hulpprogramma voor adreslijstsynchronisatie](/active-directory/active-directory-hybrid-identity-design-considerations-tools-comparison), zoals Azure AD Connect.<br /><br />√ Schakel eenmalige aanmelding in zonder dat wachtwoorden worden gerepliceerd naar de cloud, met AD FS.<br /><br />√ Organisaties kunnen altijd stoppen met Azure RMS zonder de toegang te verliezen tot inhoud die eerder is beveiligd door Azure RMS. Zie [Azure Rights Management uit bedrijf nemen en deactiveren](../deploy-use/decommission-deactivate.md) voor meer informatie over het uit bedrijf nemen van opties. Organisaties die Active Directory Rights Management Services (AD RMS) hebben geïmplementeerd, kunnen bovendien [migreren naar Azure RMS](../plan-design/migrate-from-ad-rms-to-azure-rms.md) zonder toegang tot gegevens te verliezen die eerder is beveiligd door AD RMS.|
> [!TIP] Als u bekend bent met de lokale versie van Rights Management, Active Directory Rights Management Services (AD RMS), bent u mogelijk geïnteresseerd in de vergelijkingstabel in [Azure Rights Management en AD RMS vergelijken](compare-azure-rms-ad-rms.md).

## Vereisten voor beveiliging, naleving en regelgeving
Azure RMS ondersteunt de volgende vereisten voor beveiliging, naleving en regelgeving:

√ Gebruik van cryptografie volgens de industrienorm en ondersteunt FIPS 140-2. Zie [Cryptografische besturingselementen die worden gebruikt door Azure RMS: algoritmen en sleutellengten](how-does-it-work.md#cryptographic-controls-used-by-azure-rms-algorithms-and-key-lengths) voor meer informatie.

√ Ondersteuning voor Thales Hardware Security Modules (HSM's) voor het opslaan van uw tenantsleutel in Microsoft Azure-datacentra. Azure RMS gebruikt afzonderlijke beveiligingswerelden voor de datacentra in Noord-Amerika, EMEA (Europa, Midden-Oosten en Afrika) en Azië, zodat uw sleutels alleen kunnen worden gebruikt in uw regio.

√ Gecertificeerd voor:

-   ISO/IEC 27001:2013 (omvat [ISO/IEC 27018](http://azure.microsoft.com/blog/2015/02/16/azure-first-cloud-computing-platform-to-conform-to-isoiec-27018-only-international-set-of-privacy-controls-in-the-cloud/))

-   SOC 2 SSAE 16/ISAE 3402-verklaringen

-   HIPAA BAA

-   Modelclausules van de EU

-   FedRAMP als onderdeel van Azure Active Directory in Office 365-certificering, uitgegeven door FedRAMP Agency Authority voor bewerking door HHS

-   PCI DSS-niveau 1

Zie het [Vertrouwenscentrum van Azure](http://azure.microsoft.com/support/trust-center/compliance/) voor meer informatie over deze externe certificeringen.

## Volgende stappen

Zie [Azure RMS in action](what-admins-users-see.md) (Azure RMS in actie) om te zien hoe Azure RMS eruitziet voor beheerders en voor gebruikers.

Zie [Hoe werkt Azure RMS?](how-does-it-work.md) als u meer technische informatie wilt over hoe Azure RMS werkt 

<!--HONumber=Jun16_HO1-->


