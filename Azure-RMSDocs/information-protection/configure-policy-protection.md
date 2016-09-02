---
title: Een label configureren om Rights Management-beveiliging toe te passen | Azure Rights Management
description: U kunt uw meest gevoelige documenten en e-mailberichten beveiligen met een Rights Management-service waarbij wordt gebruikgemaakt van versleutelings, -identiteits- en autorisatiebeleid om het verlies van gegevens te voorkomen. Deze beveiliging wordt toegepast wanneer u een label voor het gebruik van een Rights Management-sjabloon configureert.
manager: mbaldwin
ms.date: 08/15/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: df26430b-315a-4012-93b5-8f5f42e049cc
translationtype: Human Translation
ms.sourcegitcommit: c9f9211e7c1dcf293caf81475515114b5433d6a7
ms.openlocfilehash: 23e62c82a38e696b0708f3b599d24f3a0f337fd8


---

# Een label configureren om Rights Management-beveiliging toe te passen

>*Van toepassing op: Azure Information Protection preview*

**[ Deze informatie is voorlopig en kan worden gewijzigd. ]**

U kunt uw meest gevoelige documenten en e-mailberichten beveiligen met een Rights Management-service waarbij wordt gebruikgemaakt van versleutelings, -identiteits- en autorisatiebeleid om het verlies van gegevens te voorkomen. Deze beveiliging wordt toegepast wanneer u een label voor het gebruik van een Rights Management-sjabloon configureert. 

Deze sjabloon kan een van de standaardsjablonen zijn die automatisch worden gemaakt wanneer u Azure Rights Management activeert, of een aangepaste sjabloon. Azure Rights Management-afdelingssjablonen worden ondersteund, maar hiermee wordt de beveiliging alleen toegepast wanneer de auteur van het document of e-mailbericht zich binnen het geconfigureerde bereik van de sjabloon bevindt. Wanneer de gebruiker zich niet binnen het bereik bevindt, wordt een bericht weergegeven dat het label niet door Information Protection kan worden toegepast.

## Hoe de beveiliging werkt

Wanneer een document of e-mailbericht is beveiligd door Rights Management, is het versleuteld in rust en bij verzending en kan het alleen worden ontsleuteld door gemachtigde gebruikers. Deze versleuteling blijft van toepassing op het document of e-mailbericht, zelfs als de naam wordt gewijzigd. U kunt bovendien gebruiksrechten en -beperkingen configureren, zoals de volgende voorbeelden:

- Alleen gebruikers binnen uw organisatie kunnen het document of e-mailbericht met vertrouwelijke bedrijfsinformatie openen.

- Alleen gebruikers in de marketingafdeling kunnen het document of e-mailbericht voor de promotieaankondiging bewerken en afdrukken terwijl alle andere gebruikers in uw organisatie het document of e-mailbericht alleen kunnen bekijken.

- Gebruikers kunnen geen e-mailbericht doorsturen dat nieuws over een interne reorganisatie bevat.

- De huidige prijslijst die wordt verzonden naar zakenpartners, kan niet worden geopend na een opgegeven datum.

Zie [Aangepaste sjablonen configureren voor Azure Rights Management](../deploy-use/configure-custom-templates.md) voor meer informatie over Azure Rights Management-sjablonen en het configureren van deze gebruiksrechten en -beperkingen.

Zie [Wat is Azure Rights Management?](../understand-explore/what-is-azure-rms.md) voor meer informatie over Azure Rights Management en hoe het werkt.

> [!IMPORTANT]
> Als u een label voor het toepassen van Azure Rights Management-beveiliging wilt configureren, moet de Azure Rights Management-service zijn geactiveerd voor uw organisatie. Zie [Azure Rights Management activeren](../deploy-use/activate-service.md) als u dit nog niet hebt gedaan.


## Een label configureren om Rights Management-beveiliging toe te passen

1. Als u dat nog niet hebt gedaan, meldt u zich aan bij [Azure Portal](https://portal.azure.com) als globale beheerder zodat u de Azure Rights Management-sjablonen kunt ophalen. Ga vervolgens naar de blade **Azure Information Protection**. 

    Klik bijvoorbeeld in het hub-menu op **Bladeren** en begin met het typen van **Information** in het filtervak. Selecteer **Azure Information Protection**.

2. Selecteer op de blade **Azure Information Protection** het label dat u wilt configureren om Rights Management-beveiliging toe te passen.

3. Selecteer op de blade **Label** in de sectie **Set RMS template for protecting documents and emails containing this label (RMS-sjabloon instellen voor het beveiligen van documenten en e-mailberichten met dit label)** voor **Select RMS template from (RMS-sjabloon selecteren van)** de optie **Azure RMS** of **AD RMS (PREVIEW)**.
    
    In de meeste gevallen zult u **Azure RMS** selecteren. Selecteer AD RMS alleen als u de vereisten en beperkingen van deze configuratie, die ook wel *HYOK* (Hold Your Own Key) wordt genoemd, hebt gelezen en begrepen. Zie [HYOK-vereisten (Hold Your Own Key) en -beperkingen voor AD RMS-beveiliging](configure-adrms-restrictions.md) voor meer informatie.
    
4. Als u Azure RMS hebt geselecteerd: voor **RMS-sjabloon selecteren** klikt u op de vervolgkeuzelijst en selecteert u de sjabloon die u wilt gebruiken om documenten en e-mailberichten met dit label te beveiligen.

    > [!NOTE] 
    > Als u een nieuwe sjabloon maakt nadat u de blade **Label** hebt geopend, sluit u deze blade en gaat u terug naar stap 2, zodat uw nieuwe sjabloon voor selectie wordt opgehaald uit Azure.
    
    Houd rekening met het volgende als u een sjabloon voor afdelingen selecteert of als u [besturingselementen voor onboarding](../deploy-use/activate-service.md#configuring-onboarding-controls-for-a-phased-deployment) hebt geconfigureerd:
    
    - Gebruikers die zich buiten het geconfigureerde bereik van de sjabloon bevinden of gebruikers die zijn uitgesloten van Azure Rights Management-beveiliging zien het label wel, maar kunnen dit niet toepassen. Als ze het label selecteren, verschijnt het volgende bericht: **Azure Information Protection kan dit label niet toepassen. Neem contact op met uw IT-beheerder als het probleem zich blijft voordoen.**
    
5. Als u AD RMS hebt geselecteerd: geef de sjabloon-GUID en de licentieverlenings-URL van uw AD RMS-cluster op. [Meer informatie](configure-adrms-restrictions.md#locating-the-information-to-specify-ad-rms-protection-with-an-azure-information-protection-label)

6. Klik op **Opslaan**.

7. Maak de wijzigingen beschikbaar voor gebruikers door op de blade **Azure Information Protection** op **Publiceren** te klikken.

## Volgende stappen

Gebruik de koppelingen in de sectie [Het beleid van uw organisatie configureren](configure-policy.md#configuring-your-organization-s-policy) voor meer informatie over het configureren van uw Azure Information Protection-beleid.  



<!--HONumber=Aug16_HO4-->


