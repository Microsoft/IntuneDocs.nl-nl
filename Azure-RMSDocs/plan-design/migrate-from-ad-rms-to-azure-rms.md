---
title: Migreren van AD RMS naar Azure Rights Management | Azure RMS
description: Voer de volgende instructies uit om uw Active Directory Rights Management Services (AD RMS)-implementatie te migreren naar Azure Rights Management (Azure RMS). Na de migratie hebben gebruikers nog steeds toegang tot documenten en e-mailberichten die uw organisatie heeft beveiligd met AD RMS, terwijl voor nieuw beveiligde inhoud Azure RMS wordt gebruikt.
author: cabailey
manager: mbaldwin
ms.date: 08/17/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 828cf1f7-d0e7-4edf-8525-91896dbe3172
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26b043f1f9e7a1e0cd00c2f31c28f7d6685f0232
ms.openlocfilehash: bead12db04e6fcf2f9e4af5148d3f8a4ef4089da


---

# Migreren van AD RMS naar Azure Rights Management

>*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management*

Voer de volgende instructies uit om uw Active Directory Rights Management Services (AD RMS)-implementatie te migreren naar Azure Rights Management (Azure RMS). Na de migratie hebben gebruikers nog steeds toegang tot documenten en e-mailberichten die uw organisatie heeft beveiligd met AD RMS, terwijl voor nieuw beveiligde inhoud Azure RMS wordt gebruikt.

Weet u niet zeker of deze AD RMS-migratie geschikt is voor uw organisatie?

-   Zie [Wat is Azure Rights Management?](../understand-explore/what-is-azure-rms.md) voor een inleiding tot Azure RMS, de zakelijke problemen die ermee kunnen worden opgelost, hoe het eruitziet voor beheerders en gebruikers, en hoe het werkt.

-   Zie [Azure Rights Management en AD RMS vergelijken](../understand-explore/compare-azure-rms-ad-rms.md) voor een vergelijking van Azure RMS en AD RMS.

## Vereisten om te migreren van AD RMS naar Azure RMS
Voordat u begint aan de migratie naar Azure RMS, moet u ervoor zorgen dat aan de volgende vereisten is voldaan en dat u eventuele beperkingen begrijpt.


- **Een ondersteunde RMS-implementatie:**
    
    - De volgende versies van AD RMS ondersteunen een migratie naar Azure RMS:
    
        - Windows Server 2008 R2 (x64)
        
        - Windows Server 2012 (x64)
        
        - Windows Server 2012 R2 (x64)
        
    - Cryptografische modus 2:
    
        - Uw AD RMS-servers en -clients moeten worden uitgevoerd in de cryptografische modus 2 voordat u de migratie naar Azure RMS start. Zie [AD RMS Cryptographic Modes (Cryptografische modi van AD RMS)](https://technet.microsoft.com/library/hh867439(v=ws.10).aspx) voor meer informatie.
        
    - Alle geldige AD RMS-topologieën worden ondersteund:
    
        - Eén forest, één RMS-cluster
        
        - Eén forest, meerdere RMS-clusters met alleen licentieverlening
        
        - Meerdere forests, meerdere RMS clusters
        
    Opmerking: Standaard migreren meerdere RMS-clusters naar één Azure RMS-tenant. Als u afzonderlijke Azure RMS-tenants wilt hebben, moet u ze behandelen als verschillende migraties. Een sleutel van één RMS-cluster kan niet worden geïmporteerd in meer dan één Azure RMS-tenant.

- **Alle vereisten voor het uitvoeren van Azure RMS, met inbegrip van een Azure RMS-tenant (niet geactiveerd):**

    Zie [Vereisten voor Azure Rights Management](../get-started/requirements-azure-rms.md).

    Hoewel u een Azure RMS-tenant moet hebben voordat u vanuit AD RMS kunt migreren, raden we af de Rights Management-service vóór de migratie te activeren. Het migratieproces omvat deze stap nadat u sleutels en sjablonen hebt geëxporteerd vanuit AD RMS en deze hebt geïmporteerd in Azure RMS. Als Azure RMS echter al is geactiveerd, kunt u nog steeds migreren vanuit AD RMS.


- **Voorbereiding voor Azure RMS:**

    - Mapsynchronisatie tussen uw lokale map en Azure Active Directory

    - Groepen met e-mail in Azure Active Directory

    Zie [Voorbereiden voor Azure Rights Management](prepare.md).


- **Als u de functie Information Rights Management (IRM) van Exchange Server** (bijvoorbeeld transportregels en Outlook Web Access) of SharePoint Server met AD RMS hebt gebruikt:

    - Houd rekening met een korte periode waarin IRM niet beschikbaar is op deze servers
 
    U kunt IRM na de migratie blijven gebruiken op deze servers met Azure RMS. Een van de migratiestappen is echter de IRM-service tijdelijk te deactiveren, een connector te installeren en te configureren, de servers opnieuw te configureren en vervolgens IRM opnieuw in te schakelen.

    Dit is de enige serviceonderbreking tijdens het migratieproces.

- **Als u uw eigen Azure RMS-tenantsleutel wilt beheren met een met HSM beveiligde sleutel**:

    - Voor deze optionele configuratie moet u Azure Key Vault en een Azure-abonnement hebben dat ondersteuning biedt voor Key Vault met HSM beveiligde sleutels. Zie de [pagina met prijzen van Azure Key Vault](https://azure.microsoft.com/en-us/pricing/details/key-vault/) voor meer informatie. 


Beperkingen:

-   Hoewel het migratieproces de migratie van uw SLC-sleutel (serverlicentiecertificaat) naar een HSM (Hardware Security Module) voor Azure RMS-server ondersteunt, biedt Exchange Online momenteel geen ondersteuning voor deze configuratie. Als u na de migratie naar Azure RMS wilt beschikken over de volledige functionaliteit van IRM met Exchange Online, moet uw Azure RMS-tenantsleutel worden [beheerd door Microsoft](../plan-design/plan-implement-tenant-key.md#choose-your-tenant-key-topology-managed-by-microsoft-the-default-or-managed-by-you-byok). U kunt IRM ook uitvoeren met een beperkte functionaliteit van Exchange Online wanneer uw Azure RMS-tenant wordt beheerd door uzelf (BYOK). Meer informatie over het gebruik van Exchange Online met Azure RMS vindt u in [Stap 6. Configureer IRM-integratie voor Exchange Online](migrate-from-ad-rms-phase3.md#step-6-configure-irm-integration-for-exchange-online) met deze migratie-instructies.

-   Als u software en clients hebt die niet worden ondersteund door Azure RMS, kunnen deze geen inhoud beveiligen of gebruiken die wordt beveiligd met Azure RMS. Controleer het gedeelte over ondersteunde toepassingen en clients in het artikel [Vereisten voor Azure Rights Management](../get-started/requirements-azure-rms.md).

-   Als u uw lokale sleutel naar Azure RMS importeert als gearchiveerd (u stelt de TPD niet in als actief tijdens het importeren) en u gebruikers in batches migreert voor een gefaseerde migratie, is inhoud die nieuw is beveiligd door de gemigreerde gebruikers, niet toegankelijk voor gebruikers die op AD RMS blijven. Zorg binnen dit scenario zo mogelijk voor een korte migratietijd en migreer gebruikers in logische batches, zodat ze samen worden gemigreerd als ze met elkaar samenwerken.

    Deze beperking geldt niet wanneer u de TPD tijdens het importproces op actief zet, omdat alle gebruikers inhoud zullen beschermen met dezelfde sleutel. We raden deze configuratie aan omdat u hiermee alle gebruikers onafhankelijk en in uw eigen tempo kunt migreren.

-   Als u samenwerkt met externe partners (bijvoorbeeld via vertrouwde gebruikersdomeinen of federatie), moeten zij ook migreren naar Azure RMS op hetzelfde moment als u dat doet of anders zo spoedig mogelijk daarna. Om toegang te blijven houden tot inhoud die uw organisatie voorheen beveiligde met AD RMS, moeten zij clientconfiguratiewijzigingen aanbrengen die vergelijkbaar zijn met de uwe en die worden vermeld in dit document.

    Vanwege de mogelijke configuratieverschillen bij uw partners vallen de exacte instructies voor deze herconfiguratie buiten het bereik van dit document. [Neem contact op met Microsoft Ondersteuning](../get-started/information-support.md#support-options-and-community-resources) als u hulp nodig hebt.

## Overzicht van de stappen voor het migreren van AD RMS naar Azure RMS


De migratiestappen kunnen worden onderverdeeld in vier fasen die kunnen worden uitgevoerd op verschillende tijdstippen en door verschillende beheerders.

[**FASE 1: CONFIGURATIE AAN SERVERZIJDE VOOR AD RMS**](migrate-from-ad-rms-phase1.md)

- **Stap 1. De Azure RMS Management Administration Tools downloaden**

    Voor het migratieproces moet u een of meer van de Windows PowerShell-cmdlets uitvoeren vanuit de Azure RMS-module die is geïnstalleerd met de Azure RMS Management Administration Tool.

- **Stap 2. De configuratiegegevens vanuit AD RMS exporteren en in Azure RMS importeren**

    U exporteert de configuratiegegevens (sleutels, sjablonen, URL's) vanuit AD RMS naar een XML-bestand en uploadt dit bestand vervolgens met de Windows PowerShell-cmdlet Import-AadrmTpd naar Azure RMS. Afhankelijk van de configuratie van uw AD RMS-sleutel kunnen er extra stappen nodig zijn:

    - **Migratie van met software beschermde sleutel naar met software beschermde sleutel**:

        Centraal beheerde sleutels op basis van wachtwoorden in AD RMS naar door Microsoft beheerde Azure RMS-tenantsleutel. Dit is het eenvoudigste migratiepad waarvoor geen extra stappen zijn vereist.

    - **Migratie van met HSM beschermde sleutel naar met HSM beschermde sleutel**:

        Sleutels die zijn opgeslagen door een HSM voor AD RMS naar door de klant beheerde Azure RMS-tenantsleutel (BYOK-scenario (Bring Your Own Key)). Hierbij zijn extra stappen vereist om de sleutel van uw on-premises Thales HSM over te dragen naar Azure Key Vault en Azure RMS toestemming te geven om deze sleutel te gebruiken. Uw bestaande, met HSM beveiligde sleutel moet modulair beveiligd zijn. Met OCS beveiligde sleutels worden niet ondersteund door de Rights Management-services.

    - **Migratie van met software beschermde sleutel naar met HSM beschermde sleutel**:

        Centraal beheerde sleutels op basis van wachtwoorden in AD RMS naar door de klant beheerde Azure RMS-tenantsleutel (BYOK-scenario (Bring Your Own Key)). Dit vereist de meest intensieve configuratie, omdat u eerst uw softwaresleutel moet ophalen en importeren naar een on-premises HSM. Vervolgens moet u extra stappen uitvoeren om de sleutel van uw on-premises Thales HSM over te dragen naar een Azure Key Vault HSM en Azure RMS toestemming te geven om de sleutelkluis te gebruiken waarin de sleutel is opgeslagen.

- **Stap 3. Uw Azure RMS-tenant activeren**

    Voer deze stap zo mogelijk uit na het importproces en niet ervoor.

- **Stap 4. Geïmporteerde sjablonen configureren**

    Wanneer u uw rechtenbeleidssjablonen importeert, wordt de status ervan gearchiveerd. Als u wilt dat gebruikers de sjablonen kunnen zien en gebruiken, moet u de sjabloonstatus in de klassieke Azure-portal wijzigen in Gepubliceerd.


[**FASE 2: CONFIGURATIE AAN CLIENTZIJDE**](migrate-from-ad-rms-phase2.md)


- **Stap 5. Clients opnieuw configureren voor het gebruik van Azure RMS**

    Bestaande Windows-computers moeten opnieuw worden geconfigureerd om de Azure RMS-service te gebruiken in plaats van AD RMS. Deze stap is van toepassing op computers in uw organisatie en op computers in partnerorganisaties als u hiermee hebt samengewerkt terwijl u AD RMS uitvoerde.

    Als u de [extensies voor mobiele apparaten](http://technet.microsoft.com/library/dn673574.aspx) hebt geïmplementeerd ter ondersteuning van mobiele apparaten, zoals iOS-telefoons en iPads, Android-telefoons en -tablets, Windows-telefoons en Mac-computers, moet u ook de SRV-records in DNS verwijderen waarmee deze clients werden omgeleid om AD RMS te gebruiken.


[**FASE 3: CONFIGURATIE VAN ONDERSTEUNENDE SERVICES**](migrate-from-ad-rms-phase3.md)


- **Stap 6. IRM-integratie met Exchange Online configureren**

    Deze stap is vereist als u Exchange Online wilt gebruiken met Azure RMS.


- **Stap 7. De RMS-connector implementeren**

    Deze stap is vereist als u een of meer van de volgende lokale services met Azure RMS wilt gebruiken:

    - Exchange Server (bijvoorbeeld transportregels en Outlook Web Access)

    - SharePoint Server

    - Windows Server met infrastructuur voor bestandsclassificatie (FCI)


[**FASE 4: TAKEN NA MIGRATIE**](migrate-from-ad-rms-phase4.md )

- **Stap 8. AD RMS uit bedrijf nemen**

    Nadat u hebt gecontroleerd of alle clients Azure RMS gebruiken en niet langer toegang hebben tot de AD RMS-servers, kunt u uw AD RMS-implementatie uit bedrijf nemen.


- **Stap 9. Uw Azure RMS-tenantsleutel opnieuw versleutelen**

    Deze stap is optioneel, maar aanbevolen als u door Microsoft beheerd hebt ingesteld als de topologie van uw Azure RMS-tenantsleutel in stap 2. Deze stap is niet van toepassing als u door de klant beheerd (BYOK) hebt ingesteld als de topologie van de Azure RMS-tenantsleutel.


## Volgende stappen
Voor het starten van de migratie gaat u naar [Fase 1 - configuratie aan serverzijde](migrate-from-ad-rms-phase1.md).




<!--HONumber=Aug16_HO4-->


