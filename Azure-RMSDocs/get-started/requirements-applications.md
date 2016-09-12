---
title: Azure RMS-vereisten&#58; toepassingen | Azure RMS
description: "In de volgende tabel ziet u de toepassingen die Azure RMS standaard ondersteunen, wat betekent dat RMS nauw is geïntegreerd in deze toepassingen met behulp van RMS API's ter ondersteuning van gebruiksbeperkingen. Deze toepassingen zijn dan voorzien van RMS-functionaliteit."
author: cabailey
manager: mbaldwin
ms.date: 08/19/2016
ms.topic: get-started-article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 7b33bcb8-63da-46be-ad56-b06de97822fa
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26b043f1f9e7a1e0cd00c2f31c28f7d6685f0232
ms.openlocfilehash: d3408f954381978287852dd74a38c5903f583dda


---


# Azure RMS-vereisten: toepassingen

>*Van toepassing op: Azure Rights Management, Office 365*


In de volgende tabel ziet u de toepassingen die Azure RMS standaard ondersteunen, wat betekent dat RMS nauw is geïntegreerd in deze toepassingen met behulp van RMS API's ter ondersteuning van gebruiksbeperkingen. Deze toepassingen zijn dan voorzien van RMS-functionaliteit.

Tenzij anders vermeld, gelden de ondersteunde functies voor Azure RMS en AD RMS. Bovendien vereist AD RMS-ondersteuning op iOS, Android, OS X en Windows Phone 8.1 de installatie van [Active Directory Rights Management Services Mobile Device Extension](https://technet.microsoft.com/library/dn673574.aspx).

Informatie over de tabelkolommen:

-   **Beveiligde PDF**: bestanden die een bestandsnaam met een .ppdf-extensie hebben en die automatisch worden gemaakt wanneer u de RMS-toepassing voor delen gebruikt om Office-bestanden en PDF-bestanden te delen per e-mail. De RMS-toepassing voor delen bevat een lezer voor beveiligde PDF-bestanden. Als u eerder PDF-bestanden hebt gemaakt die u hebt beveiligd met Azure RMS of AD RMS, kunt u deze bestanden op Windows-, iOS- en Android-apparaten blijven lezen met Foxit Reader en Nitro Pro.

-   **E-mail:** de vermelde e-mailclients kunnen het e-mailbericht zelf beveiligen. Alle bijgevoegde bestanden worden dan automatisch beveiligd. In dit scenario kan met de voorbeeldfunctie van de client beveiligde inhoud (bericht en bijlage) worden weergegeven voor geautoriseerde ontvangers Als echter alleen de bijlage is beveiligd, en het e-mailbericht zelf niet, kan met de voorbeeldfunctie van de client de beveiligde bijlage niet worden weergegeven voor geautoriseerde ontvangers.

-   **Andere bestandstypen**: tekst- en afbeeldingsbestanden die een bestandsnaamextensie hebben zoals .txt, .xml, .jpg, en jpeg. Voor deze bestanden verandert de bestandsnaamextensie nadat ze systeemeigen zijn beveiligd met RMS en worden ze alleen-lezen. Bestanden die niet systeemeigen kunnen worden beveiligd, krijgen de bestandsextensie .pfile nadat ze algemeen zijn beveiligd met RMS. Zie [Beheerdershandleiding voor de Rights Management-toepassing voor delen](../rms-client/sharing-app-admin-guide.md) voor meer informatie.


|**Besturingssysteem apparaat**|Word, Excel, PowerPoint|Beveiligde PDF|E-mail|Andere bestandstypen|
|-------------------------------|---------------------------|-----------------|---------|--------------------|
|**Windows**|Office 2010<br /><br />Office 2013<br /><br />Office 2016 <br /><br />Office Mobile-apps (alleen Azure RMS) [[1]](#footnote-1)<br /><br />Office Online [[2]](#footnote-2)|Gaaiho Doc<br /><br />GigaTrust Desktop PDF Client voor Adobe<br /><br />Foxit Reader<br /><br />Nitro PDF Reader<br /><br />RMS-app voor delen|Outlook 2010<br /><br />Outlook 2013<br /><br />Office 2016 <br /><br />Outlook Web App (OWA) [[3]](#footnote-3)<br /><br />Windows Mail [[4]](#footnote-4)|RMS-toepassing voor delen voor Windows: tekst, afbeeldingen, pfile<br /><br />Siemens JT2Go: JT-bestanden (alleen Windows 10)|
|**iOS**|Office voor iPad en iPhone [[5]](#footnote-5)<br /><br />Office Online [[2]](#footnote-2)<br /><br />TITUS Docs|Foxit Reader<br /><br />RMS-app voor delen [[1]](#footnote-1)<br /><br />TITUS Docs|Citrix WorxMail [[6]](#footnote-6)<br /><br />NitroDesk [[4]](#footnote-4)<br /><br />Outlook voor iPad en iPhone [[4]](#footnote-4)<br /><br />OWA voor iOS [[3]](#footnote-3)<br /><br />TITUS Mail|RMS-app voor delen [[1]](#footnote-1): tekst, afbeeldingen, pfile<br /><br />TITUS Docs: Pfile|
|**Android**|GigaTrust-app voor Android<br /><br />Office Online [[2]](#footnote-2)<br /><br />Office Mobile (alleen Azure RMS) [[1]](#footnote-1)|GigaTrust-app voor Android<br /><br />Foxit Reader<br /><br />RMS-app voor delen [[1]](#footnote-1)|9Folders [[4]](#footnote-4)<br /><br />GigaTrust-app voor Android [[4]](#footnote-4)<br /><br />Citrix WorxMail [[6]](#footnote-6)<br /><br />NitroDesk [[4]](#footnote-4)<br /><br />Outlook voor Android [[4]](#footnote-4)<br /><br />OWA voor Android [[3]](#footnote-3) en [[7]](#footnote-7)<br /><br />Samsung Email (S3 en later) [[7]](#footnote-7)<br /><br />TITUS Classification for Mobile|RMS-app voor delen [[1]](#footnote-1): tekst, afbeeldingen, pfile|
|**OS X**|Office 2011 (alleen AD RMS)<br /><br />Office 2016 voor Mac<br /><br />Office Online [[2]](#footnote-2)|Foxit Reader<br /><br />RMS-app voor delen [[1]](#footnote-1)|Outlook 2011 (alleen AD RMS)<br /><br />Outlook 2016 voor Mac<br /><br />Outlook voor Mac|RMS-app voor delen [[1]](#footnote-1): tekst, afbeeldingen, pfile|
|**Windows 10 Mobile**|Office Mobile-apps (alleen Azure RMS) [[1]](#footnote-1)|Niet ondersteund|Citrix WorxMail [[6]](#footnote-6)<br /><br />Outlook Mail|Niet ondersteund|
|**Windows RT**|Office 2013 RT<br /><br />Office Online [[2]](#footnote-2)|Niet ondersteund|Outlook 2013 RT<br /><br />E-mail-app voor Windows<br /><br />Windows Mail [[4]](#footnote-4)|Siemens JT2Go: JT-bestanden|
|**Windows Phone 8,1**|Office Mobile (alleen AD RMS)|RMS-app voor delen [[1]](#footnote-1)|Outlook Mobile [[4]](#footnote-4)|RMS-app voor delen [[1]](#footnote-1): tekst, afbeeldingen, pfile|
|**BlackBerry 10**|Niet ondersteund|Niet ondersteund|BlackBerry e-mail [[4]](#footnote-4)|Niet ondersteund|


###### Voetnoot 1
Ondersteunt de weergave van beveiligde inhoud.

###### Voetnoot 2 
Ondersteunt de weergave van beveiligde inhoud in SharePoint Online, OneDrive voor Bedrijven en Outlook Web Access.

###### Voetnoot 3
Als een geadresseerde een lokaal postvak op Exchange heeft en een beveiligd e-mailbericht ontvangt, kan deze inhoud alleen worden geopend in een rich e-mailclient zoals Outlook.  Deze inhoud kan niet worden geopend in Outlook Web Access.

###### Voetnoot 4
Gebruikt Exchange ActiveSync IRM, dat moet worden ingeschakeld door de Exchange-beheerder. Gebruikers kunnen alle beveiligde e-mailberichten weergeven, de e-mails beantwoorden en allen beantwoorden, maar kunnen nieuwe e-mailberichten niet zelf beveiligen.

Als een geadresseerde een on-premises postvak op Exchange heeft en een beveiligd e-mailbericht ontvangt van een andere organisatie die Exchange gebruikt, kan deze inhoud alleen worden geopend in een rich e-mailclient zoals Outlook.  Deze inhoud kan niet worden geopend op een apparaat waarop Exchange Active Sync IRM wordt gebruikt.

###### Voetnoot 5
Ondersteunt het weergeven en bewerken van beveiligde documenten. Zie voor meer informatie het volgende bericht op de Office-blog: [Azure Rights Management-ondersteuning wordt toegevoegd aan Office voor iPad en iPhone](https://blogs.office.com/2015/07/22/azure-rights-management-support-comes-to-office-for-ipad-and-iphone-2/) (Engelstalig)

###### Voetnoot 6
Zie voor meer informatie de Citrix-[productdocumentatie voor WorxMail](http://docs.citrix.com/en-us/worx-mobile-apps/10/xmob-worx-mail.html).

###### Voetnoot 7
Zie voor meer informatie het volgende bericht op de Office-blog: [OWA voor Android is nu beschikbaar op bepaalde apparaten](http://blogs.office.com/2014/06/11/owa-for-android-now-available-on-select-devices/) (Engelstalig)

## Meer informatie over Azure RMS-ondersteuning voor Office

Azure RMS is nauw geïntegreerd in de Word-, Excel-, PowerPoint- en Outlook-apps, waar deze functionaliteit wordt ook Information Rights Management (IRM) wordt genoemd. De volgende Office-clientversies bieden ondersteuning voor de beveiliging van bestanden en e-mails met Azure RMS:

- Office Professional Plus 2016

- Office Professional Plus 2013

- Office Professional Plus 2010

Alle edities van Office (met uitzondering van Office 2007) ondersteunen het gebruik van beveiligde inhoud.

Azure RMS met Office Professional Plus 2010 of Office Professional 2010:

- Vereist de Microsoft Rights Management-toepassing voor delen voor Windows

- Niet ondersteund op Windows 10


## Meer informatie over de Rights Management-toepassing voor delen

Zie de volgende bronnen voor meer informatie over de Rights Management-toepassing voor delen voor Windows:

-   [Beheerdershandleiding voor de Rights Management-toepassing voor delen](../rms-client/sharing-app-admin-guide.md)

-   [Gebruikershandleiding voor de Rights Management-toepassing voor delen](../rms-client/sharing-app-user-guide.md)

Zie de volgende bronnen voor meer informatie over de Rights Management-toepassing voor delen voor mobiele platforms:

-   Download de relevante app via de koppelingen op de [Microsoft Rights Management-pagina](http://go.microsoft.com/fwlink/?LinkId=303970)

-   Als u Microsoft Intune hebt, kunt u de app implementeren en beheren met behulp van een door beleid beheerde app: 

    -   Voor iOS- en Android-apparaten die zijn ingeschreven in Intune: [Mobile Application Management-beleid configureren en implementeren in de Microsoft Intune-console](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console)

    -   Voor Android-apparaten die niet zijn ingeschreven in Intune: [Beleid voor Mobile App Management maken en implementeren met Microsoft Intune](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)

-   [Veelgestelde vragen over de Microsoft Rights Management-toepassing voor delen voor mobiele platforms](https://technet.microsoft.com/dn451248)



## Meer informatie over overige toepassingen die Azure RMS ondersteunen

Naast de toepassingen in de tabel kunnen alle toepassingen die ondersteuning bieden voor die RMS API's, worden geïntegreerd met Azure RMS, waaronder:

- Line-of-Business-toepassingen die intern zijn ontwikkeld met behulp van de RMS SDK

- Toepassingen van softwareleveranciers die zijn ontwikkeld met behulp van de RMS SDK

Zie de [Microsoft Rights Management SDK](../develop/developers-guide.md) voor meer informatie over de SDK.

## Toepassingen die niet worden ondersteund door Azure RMS

De volgende toepassingen worden momenteel niet ondersteund door Azure RMS:

-   Microsoft Office voor Mac 2011

-   Microsoft OneDrive voor Bedrijven voor SharePoint Server 2013

-   XPS Viewer
 
De RMS-toepassing voor delen heeft bovendien de volgende beperkingen:

-   Voor Windows-computers: vereist minimaal Windows 7, Service Pack 1



## Volgende stappen
Zie [Vereisten voor Azure Rights Management](requirements-azure-rms.md) voor informatie over overige vereisten.

Zie [Hoe toepassingen ondersteuning bieden voor Azure Rights Management](../understand-explore/applications-support.md) voor meer informatie over hoe veelgebruikte toepassingen Azure RMS ondersteunen.

Zie [Toepassingen configureren voor Azure Rights Management](../deploy-use/configure-applications.md) voor meer informatie over het configureren van veelgebruikte toepassingen voor Azure RMS.


<!--HONumber=Aug16_HO4-->


