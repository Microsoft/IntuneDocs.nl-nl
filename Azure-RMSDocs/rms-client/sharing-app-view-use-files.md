---
# required metadata

title: Bestanden weergeven en gebruiken die zijn beveiligd door Rights Management | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 05/09/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: e5fa4666-6906-405a-9e0c-2c52d4cd27c8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Bestanden weergeven en gebruiken die zijn beveiligd door Rights Management

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management, Windows 10, Windows 7 met SP1, Windows 8, Windows 8.1*

Wanneer de [Rights Management-toepassing (RMS) voor delen is geïnstalleerd op uw computer](install-sharing-app.md), bekijkt u een beveiligd bestand door erop te dubbelklikken. Het bestand is mogelijk een bijlage van een e-mailbericht, of u ziet het als u de Verkenner gebruikt.

> [!NOTE]
> Voordat u het beveiligde bestand kunt weergeven, moet RMS eerst bevestigen dat u bent gemachtigd om het bestand weer te geven door uw gebruikersnaam en wachtwoord te controleren. In sommige gevallen kan dit mogelijk in de cache worden opgeslagen en wordt u niet gevraagd om uw aanmeldgegevens. In andere gevallen wordt u gevraagd uw aanmeldgegevens op te geven.
>
> Als u organisatie geen Azure Rights Management (Azure RMS) of AD RMS gebruikt, kunt u een gratis account aanvragen waarmee uw referenties worden opgenomen zodat u bestanden kunt openen die beveiligd zijn met RMS:
>
> -   Als u zich wilt aanmelden voor dit account, klikt u op de koppeling om u aan te melden voor [RMS voor personen](http://go.microsoft.com/fwlink/?LinkId=309469).
>
>     Gebruik het e-mailadres van uw bedrijf in plaats van uw persoonlijke e-mailadres als u zich aanmeldt. Als u zich aanmeldt omdat u een beveiligde bijlage hebt ontvangen, gebruik dan hetzelfde e-mailadres als waarnaar de bijlage is verzonden.
> -   Zie voor meer informatie [RMS voor personen en Azure Rights Management](../understand-explore/rms-for-individuals.md).

## Een beveiligd bestand weergeven
Dubbelklik op het beveiligde bestand via de Verkenner of het e-mailbericht met de bijlage en voer uw referenties in als u daarom wordt gevraagd.

Als er twee versies van het bestand worden weergegeven maar met verschillende bestandsnaamextensies, open dan alleen het bestand met de .ppdf bestandsnaamextensie als het andere bestand niet opent. Als u de .ppdf-versie ook niet kunt openen, installeert u eerst de [RMS-toepassing voor delen](install-sharing-app.md). Hiermee kunt u bestanden openen met de extensie .ppdf.

> [!NOTE]
> Voor meer informatie raadpleegt u [Wat is het .ppdf-bestand dat automatisch wordt gemaakt?](sharing-app-dialog-box.md#what-s-the-ppdf-file-that-s-automatically-created-)

Hoe het bestand wordt geopend is afhankelijk van hoe het is beveilig. Dat kunt u zien door naar de bestandsnaamextensie te kijken. In elk geval kan het openen van het bestand worden gecontroleerd en blijft deze controle zolang het is beveiligd. Als het bestand als e-mailbijlage is verzonden dan wordt de afzender bovendien telkens wanneer u het bestand opent per e-mail op de hoogte gesteld.

- **Het bestand heeft de bestandsextensie *.pfile***

    Het bestand is generiek beveiligd.

    Wanneer u het bestand opent, ziet u het dialoogvenster **Beveiligd bestand** van de toepassing voor delen. Hierin staat wie het bestand heeft beveiligd en dat er van u wordt verwacht dat u de machtigingen voor de mede-eigenaar in acht neemt. Klik op **Openen** om het bestand te lezen.

    ![Dialoogvenster voor een pfile dat per e-mail is gedeeld tijdens het gebruik van de RMS-toepassing voor delen](../media/ADRMS_MSRMSApp_PfilePermission.png)

- **Het bestand heeft de bestandsnaamextensie *.ppdf* of is een beveiligd tekst- of afbeeldingsbestand (zoals *.ptxt* of *.pjpg*))**

    Het bestand is systeemeigen beveiligd als een kopie voor alleen-lezen.

    Het bestand wordt geopend met de viewer die bij de RMS-toepassing voor delen wordt geïnstalleerd. Dit bestand is alleen-lezen, zelfs als u het op een andere locatie opslaat of de naam ervan wijzigt.

- **Andere bestandsnaamextensies**

    Het bestand is systeemeigen beveiligd.

    Het bestand wordt geopend met de toepassing dat is gekoppeld aan de originele bestandsnaamextensie en een beperkingsbanner wordt boven aan het bestand weergegeven. De banner bevat mogelijk de toestemmingen die van toepassing zijn op het bestand of bevat een koppeling om deze weer te geven. U ziet bijvoorbeeld mogelijk het volgende waarbij u moet klikken op **De machtigingen zijn momenteel beperkt** om de werkelijke machtigingen weer te geven die van toepassing zijn op het bestand en degenen die hier toegang toe hebben:

    ![Beperkte toegang banner wanneer het bestand is beveiligd](../media/ADRMS_MSRMSApp_RestrictedAccess.png)



Zie voor een volledige lijst met bestandnaamsextensies die door Rights Management worden ondersteund, het gedeelte [Ondersteunde bestandstypen en bestandsnaamextensies](sharing-app-admin-guide-technical.md#supported-file-types-and-file-name-extensions) in de [Beheerdershandleiding voor de Rights Management-toepassing voor delen](sharing-app-admin-guide.md). Als uw bestandsnaamextensie niet wordt vermeld, zoekt u op internet op of het een bestandsnaamextensie is die door andere toepassingen wordt ondersteund.

> [!NOTE]
> Als het bestand is beveiligd met Rights Management en niet kan worden geopend, downloadt en gebruikt u het hulpprogramma [RMS Analyzer](https://www.microsoft.com/en-us/download/details.aspx?id=46437). Volg de instructies in het hulpprogramma om te controleren of er problemen zijn op uw computer waardoor mogelijk wordt voorkomen dat een beveiligd document wordt geopend.

## Om bestanden te gebruiken die zijn beveiligd (bijvoorbeeld het bestand bewerken en afdrukken)
Als u het beveiligde bestand hebt geopend en u hier meer mee wilt doen dan lezen alleen (bijvoorbeeld bewerken, kopiëren of afdrukken), volgt u de instructies op basis van de bestandsnaamextensie:

- **Het bestand heeft de bestandsextensie *.pfile***

    Sla het geopende bestand op en geeft dit een nieuwe bestandsnaamextensie die is gekoppeld aan de toepassing die u wilt gebruiken.

    Als een bestand bijvoorbeeld is beveiligd met gebruik van de bestandsnaam document.vsdx.pfile, bekijkt u het bestand en slaat u het bestand in Verkenner op als document.vsdx.

    Het nieuwe bestand is niet langer beveiligd. Als u het wilt beveiligen, moet u dit handmatig doen. Voor instructies raadpleegt u [Het beveiligen van een bestand op een apparaat (in-place beveiligen) met behulp van de Rights Management-toepassing voor delen](sharing-app-protect-in-place.md).

- **Het bestand heeft de bestandsnaamextensie *.ppdf* of is een beveiligd tekst- of afbeeldingsbestand (zoals *.ptxt* of *.pjpg*))**

    U kunt het bestand alleen weergeven en als u het een nieuwe naam geeft of verplaatst, dan blijft het bestand beveiligd.

- **Andere bestandsnaamextensies**

    Het apparaat moet een toepassing hebben die werkt met Rights Management om deze bestanden te gebruiken. Deze toepassingen worden 'RMS-enlightened applications' (toepassingen met RMS) genoemd. Toepassingen van Office 2016, Office 2013 en Office 2010 (zoals Word, Excel, PowerPoint en Outlook) zijn voorbeelden van toepassingen die geschikt zijn voor Rights Management. Maar ook toepassingen die niet afkomstig zijn van Microsoft, zoals andere softwarebedrijven en uw eigen zakelijke toepassingen, kunnen geschikt zijn voor Rights Management.

    Toepassingen die geschikt zijn voor Rights Management kunnen bestanden openen die zijn beveiligd door andere toepassingen die voor Rights Management geschikt zijn. Ze bewaren tevens de beveiliging die op ze is toegepast, zelfs wanneer u het bestand wijzigt of opslaat onder een andere bestandsnaam of op een andere locatie. Met deze toepassingen kunt u het bestand gebruiken volgens de machtigingen die momenteel van toepassingen zijn op het bestand, zodat u het bestand kunt gebruiken als u hiervoor bent gemachtigd. U kunt bijvoorbeeld een bestand bewerken maar niet afdrukken.


## Voorbeelden en andere instructies
Voor voorbeelden over hoe u de Rights Management-toepassing voor delen kunt gebruiken en praktische instructies, zie de volgende secties van de gebruikershandleiding voor de Rights Management-toepassing voor delen:

-   [Voorbeelden voor het gebruik van de RMS-toepassing voor delen](sharing-app-user-guide.md#examples-for-using-the-rms-sharing-application)

-   [Wat wilt u doen?](sharing-app-user-guide.md#what-do-you-want-to-do-)

## Zie ook
[Gebruikershandleiding voor de Rights Management-toepassing voor delen](sharing-app-user-guide.md)


<!--HONumber=May16_HO2-->


