---
# required metadata

title: AD RMS Server | Azure RMS
description: Het serveronderdeel van Rights Management Services (RMS) wordt geïmplementeerd met een reeks webservices die worden uitgevoerd op Microsoft Internet Information Services.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 17B05780-B0EF-4805-8304-52DCDEB3AADB
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# AD RMS Server

Dit onderwerp bevat informatie over het doel en de functies van RMS Server.

Het serveronderdeel van Rights Management Services (RMS) wordt geïmplementeerd met een reeks webservices die worden uitgevoerd op [Microsoft Internet Information Services](http://www.iis.net/overview) (IIS). U kunt ook de cloudimplementatie gebruiken via RMS in Azure. Zie [Ervoor zorgen dat uw servicetoepassing werkt met RMS in de cloud](how-to-use-file-api-with-aadrm-cloud.md) voor meer informatie over het gebruik van de Azure Rights Management-service.

Voor lokale servers kunt u vanaf Windows Server 2008 de RMS-service installeren en configureren door deze toe te voegen als een rol. Voor het installeren van de service op eerdere besturingssystemen downloadt u deze vanuit het Microsoft Downloadcentrum op [Microsoft Windows Rights Management Services met Service Pack 2](http://www.microsoft.com/download/en/details.aspx?id=4909).

Van de vele geïnstalleerde webservices zijn de volgende belangrijk voor toepassingsontwikkeling.

**Beheer**: fungeert als host voor de beheerwebsite waarmee u RMS kunt beheren. De service wordt uitgevoerd op basiscertificeringsservers en licentieservers. U kunt de [Active Directory Rights Management Services Scripting API](https://msdn.microsoft.com/library/Bb968797) gebruiken om beheerscripts schrijven.

**Accountcertificering**: maakt computercertificaten ter identificatie van computers in de hiërarchie van RMS-certificaten en accountcertificaten voor rechten waarmee gebruikers aan specifieke computers worden gekoppeld. Zie [Een gebruiker activeren](https://msdn.microsoft.com/library/Cc530378) voor meer informatie.

Deze service wordt uitgevoerd op de basiscertificeringsserver.

**Licentieverlening**: verleent een eindgebruikerslicentie waarmee eindgebruikers beveiligde inhoud kunnen gebruiken. De service wordt uitgevoerd op basiscertificeringsservers en licentieservers.

**Publiceren**: maakt een [uitgiftelicentie](https://msdn.microsoft.com/library/Aa362355). De service wordt uitgevoerd op basiscertificeringsservers en licentieservers.

**Pre-certificering**: hiermee kan een server een rechtenaccountcertificaat (RAC) aanvragen namens een gebruiker. Een RAC maakt gebruik van het computercertificaat van de RMS-activering om gebruikersaccounts te koppelen aan specifieke computers of groepen van computers, en wordt gebruikt om het voor consumenten mogelijk te maken om beveiligde inhoud te gebruiken. De service wordt uitgevoerd op basiscertificeringsservers en licentieservers.

**Servicelocator**: geeft de URL van de services voor accountcertificering, licentieverlening en publicatie door aan Active Directory, zodat deze te vinden zijn door RMS-clients. De service wordt uitgevoerd op basiscertificeringsservers en licentieservers.

 

## Verwante onderwerpen ##
* [Overzicht](ad-rms-overview.md)
* [Microsoft Internet Information Services](http://www.iis.net/overview)
* [Ervoor zorgen dat uw servicetoepassing werkt met RMS in de cloud](how-to-use-file-api-with-aadrm-cloud.md)
* [Microsoft Windows Rights Management Services met servicepack 2](http://www.microsoft.com/download/en/details.aspx?id=4909)
* [Active Directory Rights Management Services Scripting API](https://msdn.microsoft.com/library/Bb968797)
* [Een computer activeren](https://msdn.microsoft.com/library/Cc530377)
* [Een gebruiker activeren](https://msdn.microsoft.com/library/Cc530378)
* [Een uitgiftelicentie maken](https://msdn.microsoft.com/library/Aa362355)

 

 


<!--HONumber=Apr16_HO4-->


