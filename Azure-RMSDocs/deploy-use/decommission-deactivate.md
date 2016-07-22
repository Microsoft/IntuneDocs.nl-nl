---
title: Azure Rights Management uit bedrijf nemen en deactiveren | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 0b1c2064-0d01-45ae-a541-cebd7fd762ad
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0f355da35dff62ecee111737eb1793ae286dc93e
ms.openlocfilehash: 8c114336551417fdbf1503ffc8350e3fc28e9c95


---

# Azure Rights Management uit bedrijf nemen en deactiveren

*Van toepassing op: Azure Rights Management, Office 365*

U bepaalt altijd zelf of uw organisatie inhoud beveiligt door [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] (Azure RMS), en als u besluit deze oplossing voor gegevensbeveiliging niet meer te gebruiken, hebt u de zekerheid dat u inhoud die eerder beveiligd was toegankelijk blijft. Als u geen toegang meer hoeft te hebben tot eerder beveiligde inhoud, kunt u de service eenvoudig deactiveren en uw abonnement voor Azure Rights Management laten verlopen. Dit zou bijvoorbeeld het geval kunnen zijn wanneer u klaar bent met testen [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] voordat u de oplossing in een productieomgeving implementeert.

Als u [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] echter hebt geïmplementeerd in een productieomgeving, zorgt u ervoor dat u een kopie van uw Azure Rights Management-tenantsleutel hebt voordat u de service deactiveert en dat u dit doet voordat het abonnement is verlopen. Zo weet u zeker dat u toegang houdt tot inhoud die is beveiligd door Azure Rights Management nadat de service is gedeactiveerd. Als u de bring your own key-oplossing (BYOK) hebt gebruikt, waarin u zelf sleutels genereert en beheert in een HSM, hebt u uw Azure Rights Management-tenantsleutel al. Maar als de sleutels zijn beheerd door Microsoft (de standaardinstelling), raadpleegt u de instructies over het exporteren van uw tenantsleutel in het artikel [Operations for your Azure Rights Management tenant key](operations-tenant-key.md) (Bewerkingen voor de Azure Rights Management-tenantsleutel).

> [!TIP]
> Zelfs nadat het abonnement is verlopen, blijft uw Azure Rights Management-tenant gedurende een langere periode beschikbaar voor gebruik van inhoud. U kunt uw tenantsleutel echter niet meer exporteren.

Wanneer u uw Azure Rights Management-tenantsleutel hebt, kunt u Rights Management on-premises (AD RMS) implementeren en uw tenantsleutel importeren als een Trusted Publishing Domain (TPD). U hebt de volgende mogelijkheden voor het uit bedrijf nemen van uw Azure Rights Management-implementatie:

|Als dit voor u van toepassing is ...|… Actie:|
|----------------------------|--------------|
|U wilt dat alle gebruikers Rights Management blijven gebruiken, maar dat ze hiervoor een on-premises oplossing gebruiken in plaats van Azure RMS    →|Gebruik de cmdlet [Set-AadrmMigrationUrl](https://msdn.microsoft.com/library/azure/dn629429.aspx) om bestaande gebruikers naar uw on-premises implementatie te leiden wanneer ze na deze wijziging beveiligde inhoud verbruiken. Gebruikers gebruiken automatisch de AD RMS-installatie om de beveiligde inhoud verbruiken.<br /><br />Als gebruikers inhoud willen gebruiken die is beveiligd voordat deze wijziging werd doorgevoerd, leidt u uw clients om naar de on-premises implementatie met de registersleutel **LicensingRedirection** voor Office 2016 of Office 2013, zoals beschreven in de [sectie servicedetectie](../rms-client/client-deployment-notes.md) in de notities van de RMS-clientimplementatie, en de registersleutel **LicenseServerRedirection** voor Office 2010, zoals beschreven in [Registerinstellingen van Office](https://technet.microsoft.com/library/dd772637%28v=ws.10%29.aspx).|
|U wilt helemaal stoppen met het gebruik van Rights Management-technologieën    →|Verleen een aangewezen beheerder [rechten als supergebruiker](../deploy-use/configure-super-users.md) en geef deze persoon de [RMS-beveiligingshulpprogramma](http://www.microsoft.com/en-us/download/details.aspx?id=47256).<br /><br />Deze beheerder kan vervolgens het hulpprogramma gebruiken voor het bulksgewijs ontsleutelen van bestanden in mappen die zijn beveiligd door Azure Rights Management, zodat de bestanden niet meer beveiligd zijn en dus kunnen worden gelezen zonder een Rights Management-technologie zoals Azure RMS of AD RMS. Dit hulpprogramma kan worden gebruikt met Azure RMS en AD RMS, zodat u de keuze hebt uit het decoderen van bestanden voor- of nadat u Azure RMS deactiveert, of een combinatie hiervan.|
|U kunt niet alle bestanden identificeren die zijn beveiligd door Azure RMS of u wilt dat alle gebruikers beveiligde bestanden die zijn overgeslagen automatisch kunnen lezen    →|Implementeer een registerinstelling op alle clientcomputers met de registersleutel **LicensingRedirection** voor Office 2016 of Office 2013, zoals beschreven in de [sectie servicedetectie](../rms-client/client-deployment-notes.md) in de notities van de RMS-clientimplementatie, en de registersleutel **LicenseServerRedirection** voor Office 2010, zoals beschreven in [Registerinstellingen van Office](https://technet.microsoft.com/library/dd772637%28v=ws.10%29.aspx).<br /><br />Implementeer bovendien een andere registerinstelling om te voorkomen dat gebruikers nieuwe bestanden beveiligen door **DisableCreation** in te stellen op **1**, zoals beschreven in [Registerinstellingen van Office](https://technet.microsoft.com/library/dd772637%28v=ws.10%29.aspx).|
|U wilt een gecontroleerde, handmatige herstelservice voor bestanden die zijn overgeslagen    →|Verleen aangewezen gebruikers in een groep voor gegevensherstel [rechten als supergebruiker](../deploy-use/configure-super-users.md) en geef hen het [RMS-beveiligingshulpprogramma](http://www.microsoft.com/en-us/download/details.aspx?id=47256) zodat ze kunnen de beveiliging van bestanden kunnen opheffen wanneer dit wordt gevraagd door standaardgebruikers.<br /><br />Implementeer op alle computers de registerinstelling om te voorkomen dat gebruikers nieuwe bestanden beveiligen door **DisableCreation** in te stellen op **1**, zoals beschreven in [Registerinstellingen van Office](https://technet.microsoft.com/library/dd772637%28v=ws.10%29.aspx).|
Zie de volgende resources voor meer informatie over procedures in deze tabel:

-   Zie [Overzicht van Active Directory Rights Management Services](https://technet.microsoft.com/library/hh831364.aspx) voor informatie over AD RMS en implementatieverwijzingen.

-   Zie [Een vertrouwd uitgiftedomein toevoegen](https://technet.microsoft.com/library/cc771460.aspx) voor instructies over het importeren van de Azure RMS-tenantsleutel als TPD-bestand.

-   Zie [Windows PowerShell voor Azure Rights Management installeren](install-powershell.md) als u de Windows PowerShell-module voor Azure RMS wilt installeren om de migratie-URL in te stellen.

Gebruik de volgende instructies wanneer u klaar bent voor het deactiveren van de Azure RMS-service voor uw organisatie.

## Rights Management uitschakelen
Gebruik een van de volgende procedures voor het deactiveren van [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)].

> [!TIP]
> U kunt ook de Windows PowerShell-cmdlet [Disable-Aadrm](http://msdn.microsoft.com/library/windowsazure/dn629422.aspx) gebruiken voor het deactiveren van [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)].

#### Rights Management deactiveren vanuit het Office 365-beheercentrum

1.  [Meld u aan bij Office 365 met het werk- of schoolaccount](https://portal.office.com/) van een beheerder van uw Office 365-implementatie.

2.  Als het Office 365-beheercentrum niet automatisch wordt weergegeven, selecteert u het pictogram voor het starten van de app linksboven en kiest u **Admin**. De tegel **Beheer** wordt alleen weergegeven voor Office 365-beheerders.

    > [!TIP]
    > Zie [Over het Office 365-beheercentrum - Help voor beheerders](https://support.office.com/article/About-the-Office-365-admin-center-Admin-Help-58537702-d421-4d02-8141-e128e3703547) voor hulp bij het beheercentrum.

3.  Vouw in het linkerdeelvenster **SERVICE-INSTELLINGEN** uit.

4.  Klik op **Rights Management**.

5.  Klik op de pagina **RIGHTS MANAGEMENT** op **Beheren**.

6.  Klik op de pagina **rights management** op **Deactiveren**.

7.  Als u wordt gevraagd **Do you want to deactivate Rights Management?** (Wilt u Rights Management deactiveren?), klikt u op **Deactiveren**.

U ziet nu **Rights Management is not activated** (Rights Management is niet geactiveerd) en de mogelijkheid om te activeren.

#### Rights Management deactiveren vanuit de klassieke Azure-portal

1.  Meld u aan bij de [klassieke Azure-portal](http://go.microsoft.com/fwlink/p/?LinkID=275081).

2.  Klik in het linkerdeelvenster op **ACTIVE DIRECTORY**.

3.  Klik op de pagina **Active directory** op **RIGHTS MANAGEMENT**.

4.  Selecteer de map die u beheren voor [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)], klik op **DEACTIVEREN** en bevestig vervolgens de actie.

Voor de **RIGHTS MANAGEMENT STATUS** wordt nu **Inactief** weergegeven en de optie **DEACTIVEREN** is vervangen door **ACTIVEREN**.






<!--HONumber=Jul16_HO3-->


