---
title: Wat kunnen beheerders en gebruikers zien? | Azure RMS
description: In dit artikel worden enkele typische voorbeelden beschreven hoe beheerders en gebruikers Azure Rights Management (Azure RMS) zien en kunnen gebruiken om gevoelige of vertrouwelijke gegevens te beschermen.
author: cabailey
manager: mbaldwin
ms.date: 06/28/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 013e0eb4-49a7-4e81-9e4d-f56c0ceb017f
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26b043f1f9e7a1e0cd00c2f31c28f7d6685f0232
ms.openlocfilehash: 4a2f473c657b7fe27e2a6d42000fd540c49e8895


---


# Azure RMS in actie: wat beheerders en gebruikers zien

>*Van toepassing op: Azure Rights Management, Office 365*

In dit artikel worden enkele typische voorbeelden beschreven hoe beheerders en gebruikers Azure Rights Management (Azure RMS) zien en kunnen gebruiken om gevoelige of vertrouwelijke gegevens te beschermen.

> [!NOTE]
> In al deze voorbeelden waarin Azure RMS gegevens beveiligt, houdt de eigenaar van de inhoud volledige toegang tot de gegevens (bestand of e-mail), zelfs als de met de toegepaste beveiliging machtigingen worden verleent aan een groep waarvan de eigenaar geen lid is of zelfs als de toegepaste beveiliging een vervaldatum omvat.
>
> Ook heeft IT via de functie supergebruiker van Rights Management, waarmee gedelegeerde toegang wordt verleend aan gebruikers of services die u opgeeft, altijd onbeperkte toegang tot de beveiligde gegevens. Bovendien kan IT het gebruik van de beveiligde gegevens volgen en controleren, bijvoorbeeld wie de gegevens heeft geopend en wanneer.

Voor andere schermafbeeldingen en video's over RMS in actie, kunt u een kijkje nemen in het [Enterprise Mobility and Security-blog](https://blogs.technet.microsoft.com/enterprisemobility/?product=azure-rights-management-services).

## Rights Management activeren en configureren
Hoewel u Windows PowerShell kunt gebruiken om Azure RMS te activeren en configureren, kan dit het gemakkelijkst worden gedaan vanuit de beheerportal. Zodra de service is geactiveerd, hebt u twee standaardsjablonen die beheerders en gebruikers kunnen selecteren om snel en eenvoudig gegevensbeveiliging op bestanden toe te passen. Maar u kunt ook uw eigen aangepaste sjablonen maken voor extra opties en instellingen.

![WAT BEHEERDERS ZIEN IN STAP 1](../media/AzRMS_StoryboardActivate_small1.png)


**WAT BEHEERDERS ZIEN IN STAP 1:** u kunt het Office 365-beheercentrum (eerste afbeelding) of de klassieke Azure-portal (tweede afbeelding) gebruiken om RMS te activeren.<br /><br />Met slechts één klik om te activeren en nog een klik om te bevestigen is gegevensbeveiliging ingeschakeld voor beheerders en gebruikers in uw organisatie.

---

![WAT BEHEERDERS ZIEN IN STAP 2](../media/AzRMS_TemplatesPortal_small.png)

**WAT BEHEERDERS ZIEN IN STAP 2:** na de activering zijn twee rechtenbeleidssjablonen automatisch beschikbaar voor uw organisatie. De ene sjabloon is voor alleen-lezentoegang (de naam bevat **Confidential View Only**) en de andere sjabloon is voor lees- en wijzigingstoegang (**Confidential**).

Wanneer deze sjablonen worden toegepast op alle bestanden en e-mailberichten, wordt hiermee de toegang beperkt tot gebruikers in uw organisatie. Dit is een zeer snelle en eenvoudige manier om te voorkomen dat uw bedrijfsgegevens naar mensen buiten uw organisatie lekken.

> [!TIP]
> U kunt deze standaardsjablonen gemakkelijk herkennen, doordat de naam van uw organisatie automatisch als voorvoegsel wordt toegevoegd. In ons voorbeeld: **VanArsdel, Ltd**

Als u niet wilt dat gebruikers deze sjablonen kunnen zien, of als u uw eigen sjablonen wilt maken, kunt u dit doen in de klassieke Azure-portal. Zoals weergegeven in deze afbeelding, doorloopt u via een wizard het proces voor het maken van aangepaste sjablonen.

---

![WAT BEHEERDERS ZIEN IN STAP 3](../media/AzRMS_TemplatesSettings3.png)

**WAT BEHEERDERS ZIEN IN STAP 3:** enkele van de configuratie-instellingen die beschikbaar zijn als u besluit om uw eigen sjablonen te maken, zijn offlinetoegang, instellingen voor verlooptijd en of de sjabloon onmiddellijk wordt gepubliceerd (zichtbaar gemaakt in toepassingen die ondersteuning bieden voor Rights Management).

---

![WAT BEHEERDERS ZIEN IN STAP 4](../media/AzRMS_TemplatesPortal_ExplorerWord3.png)

**WAT BEHEERDERS ZIEN IN STAP 4:** doordat sjablonen zijn gepubliceerd, kunnen gebruikers deze nu selecteren in toepassingen als Bestandenverkenner en Microsoft Word:

- Een gebruiker kan de standaardsjabloon **VanArsdel, Ltd – vertrouwelijk** kiezen. Alleen werknemers van de organisatie VanArsdel kunnen dit document openen en gebruiken, zelfs als dit vervolgens wordt ge-e-maild naar iemand buiten de organisatie of wordt opgeslagen op een openbaar toegankelijke locatie.

- Een gebruiker kan de aangepaste sjabloon die door de beheerder is gemaakt, **Verkoop en marketing – alleen lezen en afdrukken**, kiezen. Het bestand is dan niet alleen beveiligd tegen mensen buiten de organisatie, maar ook beperkt tot werknemers van de afdeling Verkoop en marketing. Bovendien beschikken deze werknemers niet over volledige rechten voor het document, maar kunnen ze het alleen lezen en afdrukken. Ze kunnen het document bijvoorbeeld niet wijzigen of eruit kopiëren.

---

**Meer informatie over dit scenario:**

- Zie [Activating Azure Rights Management](../deploy-use/activate-service.md) (Azure Rights Management activeren) [Configuring custom templates for Azure Rights Management](../deploy-use/configure-custom-templates.md) (Aangepaste sjablonen configureren voor Azure Rights Management) voor stapsgewijze instructies.

- Zie [Helping users to protect files by using Azure Rights Management](../deploy-use/help-users.md) (Gebruikers helpen om bestanden te beveiligen met Azure Rights Management) om gebruikers te helpen bij het beveiligen van belangrijke bedrijfsbestanden.

Hieronder staan enkele voorbeelden van hoe beheerders de sjablonen kunnen gebruiken om gegevensbeveiliging voor bestanden en e-mailberichten automatisch te configureren.

## Bestanden op bestandsservers met Windows Server en Infrastructuur voor bestandsclassificatie automatisch beveiligen

Dit voorbeeld toont hoe u Azure RMS kunt gebruiken om bestanden automatisch te beveiligen op bestandsservers met Windows Server 2012 of hoger en die zijn geconfigureerd voor het gebruik van Infrastructuur voor bestandsclassificatie.

Classificatiewaarden kunnen op veel manieren worden toegepast op bestanden. U kunt bijvoorbeeld de inhoud van bestanden controleren en dienovereenkomstig ingebouwde classificaties toepassen, zoals Vertrouwelijkheid en Persoonlijke gegevens. In dit voorbeeld maakt een beheerder een aangepaste classificatie van **Marketing** die automatisch wordt toegepast op alle gebruikersdocumentatie die is opgeslagen in de map **Marketingaanbiedingen**. Hoewel deze map wordt beveiligd met NTFS-machtigingen, waarmee de toegang wordt beperkt tot leden van de groep Marketing, weet de beheerder dat deze machtigingen verloren kunnen gaan als iemand uit die groep de bestanden verplaatst of e-mailt. Vervolgens hebben onbevoegde gebruikers toegang tot de informatie in de bestanden.

![WAT BEHEERDERS ZIEN IN STAP 1](../media/AzRMS_FCI_ConnectorSmall.png)

**WAT BEHEERDERS ZIEN IN STAP 1:** de beheerder installeert en configureert de Rights Management-connector (RMS) die als een relay fungeert tussen lokale servers en Azure RMS.

---

![WAT BEHEERDERS ZIEN IN STAP 2](../media/AzRMS_ExampleFCI_ConfigurationSmall.png)

**WAT BEHEERDERS ZIEN IN STAP 2:** op de bestandsserver configureert de beheerder de classificatieregels en -taken zodat alle bestanden in de map **Marketingaanbiedingen** automatisch worden geclassificeerd als **Marketing** en beveiligd met RMS-versleuteling.

Ze selecteert de aangepaste RMS-sjabloon die is gemaakt in het eerste voorbeeld en waarmee de toegang wordt beperkt tot leden van de verkoop- en marketingafdeling: **Verkoop en marketing – alleen lezen en afdrukken**.

Hierdoor worden alle documenten in die map automatisch geconfigureerd met de classificatie Marketing en beveiligd door de RMS-sjabloon Verkoop en Marketing.

---

![WAT BEHEERDERS ZIEN IN STAP 3](../media/AzRMS_FCI_EmailSmall.png)

**WAT BEHEERDERS ZIEN IN STAP 3:** hoe RMS voorkomt dat gegevens lekken naar mensen die geen toegang mogen hebben tot gevoelige of vertrouwelijke informatie:

- Janet, van Marketing, e-mailt een vertrouwelijk rapport uit de map Marketingaanbiedingen. Dit rapport bevat nieuwe productfuncties en advertentieplannen en is aangevraagd door een collega die momenteel op zakenreis is. Janet e-mailt het rapport echter per ongeluk naar de verkeerde persoon: ze ziet niet dat ze per ongeluk een ontvanger met een vergelijkbare naam bij een ander bedrijf heeft geselecteerd.<br><br>
De ontvanger kan het vertrouwelijke rapport niet lezen omdat hij geen lid is van de groep Verkoop en Marketing.

---

**Meer informatie over dit scenario:**

- Zie [Deploying the Azure Rights Management connector](../deploy-use/deploy-rms-connector.md) (De Azure Rights Management-connector implementeren) voor stapsgewijze instructies.

## Automatisch e-mailberichten beveiligen met Exchange Online en beleid om gegevensverlies te voorkomen

Uit het vorige voorbeeld blijkt hoe u automatisch bestanden kunt beveiligen die gevoelige of vertrouwelijke informatie bevatten. Maar wat nu als de gegevens niet in een bestand staan, maar in een e-mailbericht? Hier komen Exchange Online en het beleid om gegevensverlies te voorkomen (DLP) om de hoek kijken. Hiermee wordt aan gebruikers gevraagd gegevensbeveiliging toe te passen (met beleidstips) of wordt deze beveiliging automatisch voor hen toegepast (met transportregels).

In dit voorbeeld configureert de beheerder een beleid om ervoor te zorgen dat de organisatie de voorschriften voor het beveiligen van persoonlijke gegevens naleeft, maar regels kunnen ook worden geconfigureerd voor naleving van andere nalevingsreglementen of aangepaste regels die u definieert.

![WAT BEHEERDERS ZIEN IN STAP 1](../media/AzRMS_DLPExample1.png)

**WAT BEHEERDERS ZIEN IN STAP 1:** in het Exchange-beheercentrum gebruikt de beheerder de Exchange-sjabloon met de naam ** Informatie waarmee de identiteit van de afnemer kan worden vastgesteld (PII)** om een nieuw DLP-beleid te maken en configureren. Met deze sjabloon wordt in e-mailberichten gezocht naar gegevens als burgerservicenummers en rijbewijsnummers.

De regels worden zodanig geconfigureerd dat op e-mailberichten die deze gegevens bevatten en die worden verzonden naar een adres buiten de organisatie, automatisch rechtenbescherming wordt toegepast met een RMS-sjabloon waarmee de toegang wordt beperkt tot werknemers van het bedrijf.

Hier is de regel geconfigureerd voor het gebruik van een van de standaardsjablonen, **VanArsdel, Ltd – vertrouwelijk**, uit ons eerste voorbeeld. Maar u ziet ook dat u tevens kunt kiezen uit de aangepaste sjablonen die u wellicht hebt gemaakt, en de optie **Niet doorsturen** die specifiek is voor Exchange.

> [!NOTE]
> Als de configuratieopties die u ziet enigszins afwijken van de afbeelding, moet u wellicht eerst **Meer opties** selecteren wanneer u de regel configureert. Vervolgens kunt u **De berichtbeveiliging wijzigen** > **Bescherming van rechten toepassen** selecteren en de RMS-sjabloon selecteren.

---

![WAT BEHEERDERS ZIEN IN STAP 2](../media/AzRMS_DLPUnprotectedEmail_small.png)

**WAT BEHEERDERS ZIEN IN STAP 2:** een aanstellend manager schrijft een e-mailbericht met hierin het burgerservicenummer van een onlangs aangenomen werknemer. Hij verzendt dit e-mailbericht naar Sherrie van de afdeling Personeelszaken.

---

![WAT BEHEERDERS ZIEN IN STAP 3](../media/AzRMS_DLPProtectedEmail_small.png)

**WAT BEHEERDERS ZIEN IN STAP 3:** als dit e-mailbericht wordt verzonden of doorgestuurd naar iemand buiten de organisatie, wordt met de DLP-regel automatisch rechtenbescherming toegepast.

Het e-mailbericht wordt versleuteld wanneer het de infrastructuur van de organisatie verlaat, zodat het burgerservicenummer in het e-mailbericht niet kan worden gelezen gedurende de overdracht of in het postvak IN van de geadresseerde. De ontvanger kan het bericht niet lezen, tenzij hij of zij een werknemer is van VanArsdel.

---

**Meer informatie over dit scenario:**

-   Zie de sectie [Exchange Online en Exchange Server](office-apps-services-support.md#exchange-online-and-exchange-server) in [Hoe toepassingen ondersteuning bieden voor Azure Rights Management](applications-support.md) voor meer informatie over hoe Azure RMS werkt met Exchange Online.

-   Zie [Exchange Online: IRM-configuratie](../deploy-use/configure-office365.md#exchange-online-irm-configuration) in [Toepassingen configureren voor Azure Rights Management](../deploy-use/configure-applications.md) voor stapsgewijze instructies voor het configureren van Exchange Online voor Azure RMS.

## Bestanden automatisch beveiligen met SharePoint Online en beveiligde bibliotheken

Deze sectie toont hoe u documenten eenvoudig kunt beschermen wanneer u SharePoint Online en beveiligde bibliotheken gebruikt.

In dit voorbeeld heeft de SharePoint-beheerder voor Contoso een bibliotheek gemaakt voor elke afdeling. De afdelingen gebruiken deze bibliotheken voor het centraal opslaan en controleren van documenten voor bewerking en versiecontrole. Er is bijvoorbeeld een bibliotheek voor Verkoop, voor Marketing, voor Personeelszaken, enzovoort. Wanneer een nieuw document wordt geüpload naar of gemaakt in een van deze beveiligde bibliotheken, neemt dat document de beveiliging over van de bibliotheek (hiervoor hoeft geen rechtenbeleidssjabloon te worden geselecteerd) en wordt dat document automatisch beveiligd en blijft het beveiligd, zelfs als dit wordt verplaatst naar buiten de SharePoint-bibliotheek.

![WAT BEHEERDERS ZIEN IN STAP 1](../media/AzRMS_StoryboardSPO_small1.png)

**WAT BEHEERDERS ZIEN IN STAP 1:** de beheerder schakelt Information Rights Management in voor de SharePoint-site.

---

![WAT BEHEERDERS ZIEN IN STAP 2](../media/AzRMS_StoryboardSPO_small2.png)

**WAT BEHEERDERS ZIEN IN STAP 2:** vervolgens schakelt ze Rights Management in voor een bibliotheek. Er zijn nog extra opties, maar deze eenvoudige instelling is vaak al voldoende.

Wanneer documenten nu worden gedownload uit deze bibliotheek, worden ze automatisch beveiligd door Rights Management en nemen ze de beveiliging over die is geconfigureerd voor de bibliotheek.

---

![WAT BEHEERDERS ZIEN IN STAP 3](../media/AzRMS_StoryboardSPO_small3.png)

**WAT BEHEERDERS ZIEN IN STAP 3:** als werknemers van de verkoopafdeling dit verkooprapport uit de bibliotheek bekijken, zien ze duidelijk aan de informatiebanner bovenaan dat het een beveiligd document met beperkte toegang betreft.

Het document blijft beveiligd, zelfs als de gebruiker de naam wijzigt, het document op een andere locatie opslaat of per e-mail deelt. Ongeacht wat de naam van bestand is, waar het wordt opgeslagen en of het wordt gedeeld via e-mail, het bestand kan alleen worden gelezen door leden van de verkoopafdeling.

---

**Meer informatie over dit scenario:**

-   Zie de sectie [SharePoint Online en SharePoint Server](office-apps-services-support.md#sharepoint-online-and-sharepoint-server) in [Hoe toepassingen ondersteuning bieden voor Azure Rights Management](applications-support.md) voor meer informatie over hoe Azure RMS werkt met SharePoint.

-   Zie de sectie [SharePoint Online en OneDrive voor Bedrijven: IRM-configuratie](../deploy-use/configure-office365.md#sharepoint-online-and-onedrive-for-business-irm-configuration) in [Toepassingen configureren voor Azure Rights Management](../deploy-use/configure-applications.md) voor stapsgewijze instructies voor het configureren SharePoint voor Azure RMS.

## Gebruikers delen bijlagen veilig met mobiele gebruikers

De voorgaande voorbeelden toonden hoe beheerders automatisch gegevensbeveiliging kunnen toepassen op gevoelige en vertrouwelijke gegevens. Maar in sommige gevallen moet de gebruikers deze beveiliging mogelijk zelf toepassen. Wanneer ze bijvoorbeeld samenwerken met partners in een andere organisatie, hebben ze aangepaste machtigingen of instellingen nodig die niet zijn gedefinieerd in sjablonen, voor ad-hocsituaties waarop de eerdere voorbeelden niet van toepassing zijn. In deze omstandigheden kunnen gebruikers de RMS-sjablonen zelf toepassen of aangepaste machtigingen configureren.

Dit voorbeeld toont hoe gebruikers eenvoudig een document kunnen delen met een werknemer van een ander bedrijf waarmee ze samenwerken, maar nog steeds een document kunnen beveiligen en er zeker van kunnen zijn dat de ontvanger het kan lezen, zelfs met een populair mobiel apparaat. In dit scenario wordt gebruik gemaakt van de Rights Management-toepassing voor delen, die u automatisch kunt implementeren naar Windows-computers in uw organisatie. Gebruikers de toepassing ook zelf installeren.

In dit voorbeeld e-mailt Alice van Contoso een vertrouwelijk Word-document naar Bob bij Fabrikam. Hij leest het document op zijn iPad, maar kan hij het net zo gemakkelijk lezen op een iPhone, een Android-tablet of -telefoon, een Mac-computer, of een Windows-phone of -computer.

![WAT GEBRUIKERS ZIEN IN STAP 1](../media/AzRMS_StoryboardEmail_small1.png)

**WAT GEBRUIKERS ZIEN IN STAP 1:** Alice maakt op haar Windows-PC een standaard e-mailbericht en voegt een document toe als bijlage.

Ze klikt op **Beveiligd delen** op het lint, waardoor het dialoogvenster **Beveiligd delen** van de RMS-toepassing voor delen wordt geladen.

Alice wil de rechten voor Bob beperken, zodat hij het document alleen kan weergeven en bewerken, maar niet kan kopiëren of afdrukken. Daarom selecteert ze **REVISOR: weergeven en bewerken**. Ze wil ook een e-mailbericht ontvangen als iemand het document probeert te openen, en ze wil de mogelijkheid hebben om het document indien nodig later in te trekken en weten dat het intrekken onmiddellijk van kracht wordt.

---

![WAT GEBRUIKERS ZIEN IN STAP 2](../media/AzRMS_StoryboardEmail_small2.png)

**WAT GEBRUIKERS ZIEN IN STAP 2:** Bob ziet het e-mailbericht op zijn iPad.

De e-mail bevat niet alleen het bericht en de bijlage van Alice, maar ook instructies die hij volgt om zich aan te melden en de RMS sharing-app op zijn iPad te installeren.

---

![WAT GEBRUIKERS ZIEN IN STAP 3](../media/AzRMS_StoryboardEmail_small3.png)

**WAT GEBRUIKERS ZIEN IN STAP 3:** Bob kan nu de bijlage openen. Hij moet zich eerst aanmelden om te bevestigen dat hij de beoogde ontvanger.

Als Bob het document bekijkt, ziet hij in de beperkte-toegangsinformatie dat hij het document kan weergeven en bewerken, maar niet kan kopiëren of afdrukken.

---

![WAT GEBRUIKERS ZIEN IN STAP 4](../media/AzRMS_StoryboardEmail_small4.png)

**WAT GEBRUIKERS ZIEN IN STAP 4:** Alice ontvangt een e-mailbericht waaruit blijkt dat Bob het door haar verzonden document heeft geopend en wanneer hij dit heeft gedaan.

Als Bob zijn e-mailbericht met de bijlage doorstuurt of opslaat op een locatie waar anderen er toegang toe hebben, of als het document op het netwerk wordt onderschept, kunnen andere gebruikers het document niet lezen.

---

**Meer informatie over dit scenario:**

- Zie [Een bestand beveiligen dat u per e-mail deelt](../rms-client/sharing-app-protect-by-email.md) en [Weergeven en gebruiken van bestanden die zijn beveiligd](../rms-client/sharing-app-view-use-files.md) in de [gebruikershandleiding voor de Rights Management-toepassing voor delen](../rms-client/sharing-app-user-guide.md) voor stapsgewijze instructies.

- De [zelfstudie voor snel starten met Azure Rights Management](../get-started/quick-start-tutorial.md) bevat stapsgewijze instructies voor dit scenario.

## Volgende stappen

Nu u met enkele voorbeelden hebt gezien wat Azure RMS kan doen, bent u mogelijk geïnteresseerd in het programma dit doet. Zie [Hoe werkt Azure RMS?](how-does-it-work.md) voor technische informatie over hoe Azure RMS werkt



<!--HONumber=Aug16_HO4-->


