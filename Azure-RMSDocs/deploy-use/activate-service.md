---
# required metadata

title: Azure Rights Management activeren | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 05/16/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: f8707e01-b239-4d1a-a1ea-0d1cf9a8d214

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Azure Rights Management activeren

*Van toepassing op: Azure Rights Management, Office 365*

Wanneer u [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] (Azure RMS) activeert, kan uw organisatie beginnen met het beveiligen van belangrijke gegevens met behulp van toepassingen en services die ondersteuning bieden voor deze oplossing voor gegevensbeveiliging. Beheerders kunnen ook beveiligde bestanden en e-mailberichten die eigendom zijn van uw organisatie, beheren en controleren. U moet [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)] inschakelen voordat u gebruik kunt gaan maken van de functies van Information Rights Management (IRM) in Office SharePoint en Exchange, en gevoelige of vertrouwelijke bestanden kunt gaan beveiligen.

Als u meer informatie over Azure Rights Management wilt voordat u de service activeert, bijvoorbeeld welke bedrijfsproblemen het oplost, gangbare gebruiksdoeleinden en hoe het werkt, raadpleegt u [Wat is Azure Rights Management?](../understand-explore/what-is-azure-rms.md)

> [!IMPORTANT]
> Zorg er vóór activering voor dat [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)]uw organisatie beschikt over een service-abonnement met [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)]-services. Als dat niet het geval is, kunt u Azure RMS niet activeren.
>
> Zie [Cloud subscriptions that support Azure RMS](../get-started/requirements-subscriptions.md) (Cloudabonnementen die Azure RMS ondersteunen)voor meer informatie.

Nadat u Azure RMS hebt geactiveerd, kunnen alle gebruikers in uw organisatie gegevensbeveiliging op hun bestanden toepassen en kunnen alle gebruikers bestanden openen (gebruiken) die door Azure RMS worden beveiligd. Voor een gefaseerde implementatie kunt u desgewenst echter beperken wie er gegevensbeveiliging kan toepassen. Dit doet u met behulp van besturingselementen voor onboarding. Zie voor meer informatie de sectie [Controlemiddelen voor onboarding configureren voor een gefaseerde implementatie](#configuring-onboarding-controls-for-a-phased-deployment) in dit artikel.

Voor instructies over het activeren van Rights Management vanuit de beheerportal selecteert u of u het Office 365-beheercentrum (preview of klassiek) of de klassieke Azure-beheerportal gaat gebruiken:


- [Office 365-beheercentrum - preview](activate-office365-preview.md)
- [Office 365-beheercentrum - klassiek](activate-office365-classic.md)
- [Klassieke Azure-portal](activate-azure-classic.md)

U kunt ook Windows PowerShell gebruiken om [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)] te activeren:

1. Installeer het beheerprogramma voor Azure Rights Management. Hiermee wordt de Azure Rights Management-beheermodule geïnstalleerd. Zie [Installing Windows PowerShell for Azure Rights Management](../deploy-use/install-powershell.md) (Windows PowerShell voor Azure Rights Management installeren) voor instructies.

2. Voer vanuit een Windows PowerShell-sessie [Connect-AadrmService](https://msdn.microsoft.com/library/windowsazure/dn629415.aspx) uit, en geef als hierom wordt gevraagd de accountgegevens op van de algemene beheerder voor uw Azure RMS-tenant.

3. Voer [Enable-Aadrm](http://msdn.microsoft.com/library/windowsazure/dn629412.aspx) uit. Hiermee wordt de Azure RMS-service geactiveerd.

## Besturingselementen voor onboarding configureren voor een gefaseerde implementatie
Als u niet wilt dat alle gebruikers direct bestanden kunnen beveiligen met Azure RMS, kunt u voor gebruikers besturingselementen voor onboarding configureren. Dit doet u met behulp van de Windows PowerShell-opdracht [Set AadrmOnboardingControlPolicy](http://msdn.microsoft.com/library/azure/dn857521.aspx). U kunt deze opdracht uitvoeren voordat u Azure RMS activeert, maar ook daarna.

> [!IMPORTANT] Voor het gebruik van deze opdracht moet u ten minste over versie **2.1.0.0** van de [Azure RMS-module voor Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=257721) beschikken.
>
> Om te controleren welke versie er is geïnstalleerd, voert u **(Get-Module aadrm –ListAvailable).Version** uit.

Als u in eerste instantie bijvoorbeeld alleen beheerders in de groep 'IT-afdeling' (met de object-id fbb99ded-32a0-45f1-b038-38b519009503) in staat wilt stellen om voor testdoeleinden inhoud te beveiligen, gebruikt u de volgende opdracht:

```
Set-AadrmOnboardingControlPolicy – SecurityGroupObjectId fbb99ded-32a0-45f1-b038-38b519009503
```
Houd er rekening mee dat u voor deze configuratieoptie een groep moet opgeven; u kunt geen individuele gebruikers opgeven.

Als u ervoor wilt zorgen dat alleen gebruikers met de juiste licentie om Azure RMS te gebruiken, inhoud kunnen beveiligen, gebruikt u deze opdracht:

```
Set-AadrmOnboardingControlPolicy -UseRmsUserLicense $true
```
Wanneer u deze besturingselementen voor onboarding gebruikt, kunnen alle gebruikers in de organisatie altijd beveiligde inhoud gebruiken die is beveiligd door uw subset van gebruikers, maar kunnen ze zelf geen gegevensbeveiliging toepassen vanuit clienttoepassingen. In hun Office-clients zien ze bijvoorbeeld niet de standaardsjablonen die automatisch worden gepubliceerd als Azure RMS wordt geactiveerd, evenmin als aangepaste sjablonen die u mogelijk hebt geconfigureerd.  In toepassingen aan de serverzijde, zoals Exchange, kunnen voor de RMS-integratie eigen besturingselementen op gebruikersbasis worden geïmplementeerd. Dit levert hetzelfde resultaat op.


## Volgende stappen
Nu u [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] hebt geactiveerd voor uw organisatie, kunt u het [Azure Rights Management-implementatieschema](../plan-design/deployment-roadmap.md) gebruiken om na te gaan of er nog andere configuratiestappen zijn die u moet uitvoeren voordat u [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] implementeert voor gebruikers en beheerders. 

Misschien wilt u bijvoorbeeld [aangepaste sjablonen](configure-custom-templates.md) gebruiken om het gebruikers gemakkelijker te maken gegevensbeveiliging toe te passen op bestanden, uw lokale servers geschikt maken voor het gebruik van [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] door de [RMS-connector](deploy-rms-connector.md) te installeren, of de [Rights Management-toepassing voor delen](../rms-client/sharing-app-windows.md) installeren, die beveiliging van alle bestandstypen op alle apparaten ondersteunt. 

Office-services, zoals Exchange Online en SharePoint Online, vereisen aanvullende configuratie voordat u de Information Rights Management-functies (IRM-functies) kunt gebruiken. Zie [How applications support Azure Rights Management](../understand-explore/applications-support.md) (Hoe toepassingen ondersteuning bieden voor Azure Rights Management) voor meer informatie over hoe uw toepassingen werken met [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)].



<!--HONumber=May16_HO3-->


