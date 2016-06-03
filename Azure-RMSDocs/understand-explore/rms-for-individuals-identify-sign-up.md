---
# required metadata

title: Nagaan of uw gebruikers zich hebben geregistreerd voor RMS voor personen | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: a36c3d99-a794-4f7a-aafb-64a950f1fcf9

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Nagaan of uw gebruikers zich hebben geregistreerd voor RMS voor personen

*Van toepassing op: Azure Rights Management*

Hoe weet u als beheerder of gebruikers zich hebben geregistreerd voor RMS voor personen? U kunt een of een combinatie van de volgende methoden gebruiken:

-   Vraag gebruikers hoe zij zeer vertrouwelijke bestanden beveiligen, met name wanneer ze samenwerken met personen buiten de organisatie.

-   Als u een Azure-abonnement hebt voor uw organisatie, gebruikt u de [Get-MsolAccountSku](https://msdn.microsoft.com/library/azure/dn194118.aspx)-cmdlet om te controleren of **RIGHTSMANAGEMENT_ADHOC** wordt geretourneerd als een van de abonnementen. Als dit het geval is, is dit het RMS voor personen-abonnement dat is verleend aan de organisatie, met een groep actieve eenheden die beschikbaar zijn voor gebruikers voor gebruik van het selfserviceregistratieproces.

-   Gebruik een oplossing voor systeembeheer, zoals System Center Configuration Manager, om een inventaris te maken van geïnstalleerde en gebruikte software. De Rights Management-toepassing voor delen wordt uitgevoerd met behulp van het programma **ipviewer.exe**. U kunt [de toepassing gratis downloaden en installeren](http://go.microsoft.com/fwlink/?LinkId=303970) om andere kenmerken van deze toepassing te identificeren die u vervolgens kunt gebruiken om een inventaris te maken van de software.

-   Zoek naar bestandsnaamextensies die zijn gemaakt met de Rights Management-toepassing voor delen. De bestandsnaamextensies .pfile en .ppdf zijn de meest voor de hand liggende voorbeelden, maar er zijn andere bestanden waarvan de bestandsnaamextensie wordt gewijzigd wanneer ze systeemeigen zijn beveiligd met Rights Management. Zie de sectie [Ondersteunde bestandstypen en bestandsnaamextensies](../rms-client/sharing-app-admin-guide-technical.md#supported-file-types-and-file-name-extensions) in de [Beheerdershandleiding voor de Rights Management-toepassing voor delen](http://technet.microsoft.com/library/dn339003.aspx) voor meer informatie..



<!--HONumber=Apr16_HO4-->


