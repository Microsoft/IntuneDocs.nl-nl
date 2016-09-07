---
title: Azure Rights Management en AD RMS vergelijken | Azure RMS
description: "Als u Active Directory Rights Management Services (AD RMS) kent of eerder hebt geïmplementeerd, wilt u wellicht weten wat de verschillen met Azure RMS zijn op het gebied van functionaliteit en vereisten."
author: cabailey
manager: mbaldwin
ms.date: 08/25/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 8123bd62-1814-4d79-b306-e20c1a00e264
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 43429b44c019144744f39a1f92f144d315c2024c
ms.openlocfilehash: 2de89be11a45e3d1e53afc667a6cf65fcb69c690


---

# Azure Rights Management en AD RMS vergelijken

>*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management Office 365*

Als Active Directory Rights Management Services (AD RMS) kent of eerder hebt geïmplementeerd, wilt u wellicht wat de verschillen met [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] (Azure RMS) zijn op het gebied van functionaliteit en vereisten. 

Enkele van de belangrijkste verschillen voor Azure RMS:

- **Er is geen serverinfrastructuur vereist**: Voor Azure RMS zijn, in tegenstelling tot AD RMS, geen extra servers en PKI-certificaten, omdat deze al worden verzorgd door Microsoft Azure. Hierdoor is deze cloudoplossing sneller te implementeren en gemakkelijker te onderhouden.

- **Cloudverificatie**: Azure RMS gebruikt Azure AD voor de verificatie, zowel voor interne gebruikers als voor gebruikers van andere organisaties. Dit betekent dat uw mobiele gebruikers kunnen worden geverifieerd, zelfs wanneer ze niet zijn verbonden met uw interne netwerk. Bovendien is het eenvoudiger beveiligde inhoud te delen met gebruikers van andere organisaties. Veel organisaties hebben al gebruikersaccounts in Azure AD omdat ze Azure-services of Office 365 gebruiken. Maar als dit niet het geval is, kunnen gebruikers in RMS voor personen een gratis account maken. Als u met AD RMS beveiligde inhoud wilt delen met een andere organisatie, moet u expliciete vertrouwensrelaties configureren met elke organisatie.

- **Ingebouwde ondersteuning voor mobiele apparaten**: Er zijn geen implementatiewijzigingen nodig voor Azure RMS om ondersteuning te kunnen bieden voor mobiele apparaten en Mac-computers. Als u deze apparaten wilt ondersteunen met AD RMS, moet u de extensie voor mobiele apparaten installeren, AD FS voor federatie configureren en extra records maken voor uw openbare DNS-service.

- **Standaardsjablonen**: Zodra de service is geactiveerd, maakt Azure RMS twee standaardsjablonen. Hierdoor is het zeer eenvoudig om meteen te beginnen met het beveiligen van belangrijke gegevens. Er zijn geen standaardsjablonen voor AD RMS.

- **Afdelingssjablonen**: Azure RMS ondersteunt afdelingssjablonen als configuratie-instelling voor extra sjablonen die u maakt. Met deze instelling kunt u opgeven welke gebruikers de sjabloon zien in hun clienttoepassingen (zoals Office-apps), waardoor het voor hen gemakkelijker wordt om het juiste beleid te selecteren dat u hebt gedefinieerd voor verschillende groepen gebruikers. AD RMS biedt geen ondersteuning voor afdelingssjablonen.

- **Documenttracking, intrekken en e-mailmeldingen**: Azure RMS ondersteunt deze functionaliteit met de RMS-toepassing voor delen, AD RMS biedt deze ondersteuning niet.


Omdat Azure RMS bovendien een cloudservice is, kan het nieuwe functies en oplossingen sneller leveren dan een on-premises, serveroplossing. Er zijn geen nieuwe functies gepland voor AD RMS in Windows Server 2016.

Gebruik de volgende tabel met een vergelijking van de functies en voordelen van Azure RMS en AD RMS voor meer details en andere verschillen. Zie de sectie [Cryptografische besturingselementen voor ondertekening en versleuteling](compare-azure-rms-ad-rms.md#cryptographic-controls-for-signing-and-encryption) in dit artikel als u beveiligingsspecifieke vergelijkingsvragen hebt.

> [!NOTE]
> Een deel van deze informatie hier wordt herhaald uit [Vereisten voor Azure Rights Management](../get-started/requirements-azure-rms.md) om deze vergelijking eenvoudiger te maken. Gebruik deze bron voor meer gedetailleerde informatie over ondersteuning en versies voor [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)].

|Azure RMS|AD RMS|
|-----------------------------------------------------------------------------------------|--------------------------------------------------------|
|Ondersteunt mogelijkheden voor Information Rights Management (IRM) in Microsoft Online-services, zoals Exchange Online en SharePoint Online, en Office 365.<br /><br />Ondersteunt ook on-premises Microsoft Server-producten, zoals Exchange Server, SharePoint Server en bestandsservers waarop Windows Server en Infrastructuur voor bestandsclassificatie (FCI) worden uitgevoerd.|Ondersteunt on-premises Microsoft Server-producten, zoals Exchange Server, SharePoint Server en bestandsservers waarop Windows Server en Infrastructuur voor bestandsclassificatie (FCI) worden uitgevoerd.|
|Maakt impliciete vertrouwensrelatie tussen organisaties en gebruikers in elke organisatie mogelijk. Dit betekent dat beveiligde inhoud kan worden gedeeld tussen gebruikers binnen dezelfde organisatie of tussen verschillende organisaties wanneer gebruikers [!INCLUDE[o365_1](../includes/o365_1_md.md)] of [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] hebben, of gebruikers zich aanmelden voor RMS voor personen.|Vertrouwensrelaties moeten expliciet zijn gedefinieerd in een directe punt-naar-puntrelatie tussen twee organisaties met vertrouwde gebruikersdomeinen (TUD’s) of federatieve vertrouwensrelaties die u maakt met Active Directory Federation Services (AD FS).|
|Biedt twee rechtenbeleidssjablonen waarmee toegang tot inhoud tot uw eigen organisatie wordt beperkt; een sjabloon die alleen-lezenweergave van beveiligde inhoud biedt, en een andere sjabloon die machtigingen biedt voor schrijven en wijzigen voor de beveiligde inhoud.<br /><br />U kunt ook uw eigen aangepaste sjablonen maken, waaronder afdelingssjablonen die alleen zichtbaar zijn voor een gebruikerssubset. Zie [Aangepaste sjablonen configureren voor Azure Rights Management](../deploy-use/configure-custom-templates.md) voor meer informatie.<br /><br />Als de sjablonen niet voldoen aan de behoeften, kunnen gebruikers bovendien hun eigen set machtigingen definiëren.|Als er geen standaardrechtenbeleidssjablonen zijn, moet u deze maken en vervolgens distribueren. Zie [AD RMS Policy Template Considerations](http://go.microsoft.com/fwlink/?LinkId=154765) (Overwegingen voor AD RMS-beleidssjablonen) voor meer informatie.<br /><br />Als de sjablonen niet voldoen aan de behoeften, kunnen gebruikers bovendien hun eigen set machtigingen definiëren.|
|De minimaal ondersteunde versie van Microsoft Office is Office 2010. Hiervoor is de [RMS-toepassing voor delen](../rms-client/sharing-app-windows.md) vereist.<br /><br />Microsoft Office voor Mac:<br /><br />- Microsoft Office voor Mac 2016: ondersteund<br /><br />- Microsoft Office voor Mac 2011: niet ondersteund|De minimaal ondersteunde versie van Microsoft Office is Office 2007.<br /><br />Microsoft Office voor Mac:<br /><br />- Microsoft Office voor Mac 2016: ondersteund<br /><br />- Microsoft Office voor Mac 2011: ondersteund|
|Ondersteunt de [RMS-toepassing voor delen](../rms-client/sharing-app-windows.md) voor Windows, Mac-computers en mobiele apparaten.<br /><br />De RMS-toepassing voor delen ondersteunt tevens het volgende:<br /><br />- Delen met personen in een andere organisatie.<br /><br />- E-mailmeldingen waarmee de afzender wordt geïnformeerd wanneer iemand probeert een beveiligde bijlage te openen.<br /><br />- Een site voor documenttracking voor gebruikers, die de mogelijkheid bevat voor het intrekken van een document.|Ondersteunt de [RMS-toepassing voor delen](../rms-client/sharing-app-windows.md) voor Windows, Mac-computers en mobiele apparaten. Delen biedt echter geen ondersteuning voor delen met personen in een andere organisatie, e-mailmeldingen of de site voor documenttracking en de mogelijkheid voor gebruikers om documenten in te trekken.|
|Wanneer u de RMS-toepassing voor delen gebruikt, kunnen alle bestandstypen worden beveiligd met [systeemeigen of algemene beveiliging](../rms-client/sharing-app-admin-guide-technical.md#levels-of-protection-native-and-generic).<br /><br />Zie de tabel in [Azure RMS-vereisten: Toepassingen](../get-started/requirements-applications.md) voor andere toepassingen.|Wanneer u de RMS-toepassing voor delen gebruikt, kunnen alle bestandstypen worden beveiligd met [systeemeigen of algemene beveiliging](../rms-client/sharing-app-admin-guide-technical.md#levels-of-protection-native-and-generic).<br /><br />Zie de tabel in [Azure RMS-vereisten: Toepassingen](../get-started/requirements-applications.md) voor andere toepassingen.|
|De minimaal ondersteunde versie van de Windows-client is Windows 7.|De minimaal ondersteunde versie van de Windows-client is Windows Vista Service Pack 2.|
|Ondersteuning voor mobiele apparaten omvat Windows Phone, Android, iOS en Windows RT.<br /><br />E-mailondersteuning met Exchange ActiveSync IRM wordt ook ondersteund op alle platformen voor mobiele apparaten die ondersteuning bieden voor dit protocol.|Ondersteuning voor mobiele apparaten omvat Windows Phone, Android, iOS en Windows RT. Hiervoor is de [extensie voor mobiele apparaten voor Active Directory Rights Management Services](http://technet.microsoft.com/library/dn673574.aspx) vereist.<br /><br />E-mailondersteuning met Exchange ActiveSync IRM wordt ondersteund op alle platformen voor mobiele apparaten die ondersteuning bieden voor dit protocol.|
|Ondersteunt Multi-Factor Authentication (MFA) voor computers en mobiele apparaten.<br /><br />Zie [Multi-factor authentication (MFA) and Azure RMS](../get-started/requirements-azure-ad.md#multi-factor-authentication-mfa-and-azure-rms) (Multi-Factor Authentication (MFA) en Azure RMS) voor meer informatie.|Ondersteunt smartcardauthenticatie als IIS is geconfigureerd voor het aanvragen van certificaten.|
|Ondersteunt cryptografische modus 2 zonder aanvullende configuratie, voor betere beveiliging voor sleutellengten en versleutelingsalgoritmen.<br /><br />Zie de sectie [Cryptografische besturingselementen voor ondertekening en versleuteling](#cryptographic-controls-for-signing-and-encryption) in dit artikel en [AD RMS Cryptographic Modes](http://go.microsoft.com/fwlink/?LinkId=266659) (Cryptografische modi van AD RMS)voor meer informatie.|Ondersteunt standaard cryptografische modus 1. Voor ondersteuning voor cryptografische modus 2 en een betere beveiliging is aanvullende configuratie vereist.<br /><br />Zie de sectie [Cryptografische besturingselementen voor ondertekening en versleuteling](#cryptographic-controls-for-signing-and-encryption) in dit artikel en [AD RMS Cryptographic Modes](http://go.microsoft.com/fwlink/?LinkId=266659) (Cryptografische modi van AD RMS)voor meer informatie.|
|Ondersteunt de migratie van AD RMS en indien nodig, naar AD RMS:<br /><br />- [Migreren van AD RMS naar Azure Rights Management](../plan-design/migrate-from-ad-rms-to-azure-rms.md)<br /><br />- [Azure Rights Management uit bedrijf nemen en deactiveren](../deploy-use/decommission-deactivate.md)|Ondersteunt de migratie van Azure RMS en naar Azure RMS:<br /><br />- [Azure Rights Management uit bedrijf nemen en deactiveren](../deploy-use/decommission-deactivate.md)<br /><br />- [Migreren van AD RMS naar Azure Rights Management](../plan-design/migrate-from-ad-rms-to-azure-rms.md)|
|Voor het beveiligen van inhoud is een RMS-licentie vereist. Er is geen RMS-licentie vereist om inhoud te verbruiken die is beveiligd door Azure RMS (inclusief gebruikers van een andere organisatie).<br /><br />Zie [Cloud subscriptions that support Azure RMS](../get-started/requirements-subscriptions.md) (Cloudabonnementen die ondersteuning bieden voor Azure RMS) voor meer informatie.|Voor het beveiligen en het verbruiken van inhoud die is beveiligd door AD RMS is een RMS-licentie vereist.<br /><br />Zie [Client Access Licenses and Management Licenses](https://www.microsoft.com/en-us/Licensing/product-licensing/client-access-license.aspx) (Licenties voor clienttoegang en beheerlicenties) voor algemene informatie over licenties voor AD RMS, maar neem contact op met uw Microsoft-partner of Microsoft-vertegenwoordiger voor specifieke informatie.|

## Cryptografische besturingselementen voor ondertekening en versleuteling
[!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] gebruikt altijd RSA 2048 voor alle bewerkingen voor openbare-sleutelcryptografie en SHA 256 voor ondertekening. Ter vergelijking: AD RMS ondersteunt RSA 1024 en RSA 2048, en SHA 1 of SHA 256 voor ondertekening.

Voor zowel [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] als AD RMS wordt AES 128 gebruikt voor symmetrische codering.

[!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] is compatibel met FIPS 140-2 als de tenantsleutel wordt gemaakt en beheerd door Microsoft (de standaardinstelling) of als u uw eigen tenantsleutel (ook wel BYOK) beheert. Zie [Uw Azure Rights Management-tenantsleutel plannen en implementeren](../plan-design/plan-implement-tenant-key.md) voor meer informatie over het beheren van uw tenantsleutel.

## Volgende stappen
Zie [Migreren van AD RMS naar Azure Rights Management](../plan-design/migrate-from-ad-rms-to-azure-rms.md) als u wilt migreren van AD RMS naar Azure RMS





<!--HONumber=Aug16_HO4-->


