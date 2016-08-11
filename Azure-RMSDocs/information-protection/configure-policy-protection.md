---
title: Een label configureren om Rights Management-beveiliging toe te passen | Azure Rights Management
description: 
author: cabailey
manager: mbaldwin
ms.date: 07/29/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: df26430b-315a-4012-93b5-8f5f42e049cc
translationtype: Human Translation
ms.sourcegitcommit: 00b4cd2b1e7b1196cedd39d7052db534e781bb13
ms.openlocfilehash: 7a20b59c404959c4ec209e8c29ac61ab71233e87


---

# Een label configureren om Rights Management-beveiliging toe te passen

>*Van toepassing op: Azure Information Protection preview*

**[ Deze informatie is voorlopig en kan worden gewijzigd. ]**

U kunt uw meest gevoelige documenten en e-mailberichten beveiligen met Azure Rights Management waarbij gebruik wordt gemaakt van versleutelings, -identiteits- en autorisatiebeleid om het verlies van gegevens te voorkomen. Deze beveiliging wordt toegepast wanneer u een label voor het gebruik van een Rights Management-sjabloon configureert. 

Deze sjabloon kan een van de standaardsjablonen zijn die automatisch worden gemaakt wanneer u Azure Rights Management activeert, of een aangepaste sjabloon. Afdelingssjablonen worden ondersteund, maar hiermee wordt de beveiliging alleen toegepast wanneer de auteur van het document of e-mailbericht zich binnen het geconfigureerde bereik van de sjabloon bevindt. Wanneer de gebruiker zich niet binnen het bereik bevindt, wordt een bericht weergegeven dat het label niet door Information Protection kan worden toegepast.

## Hoe de beveiliging werkt

Wanneer een document of e-mailbericht is beveiligd door Azure Rights Management, is het versleuteld in rust en bij verzending en kan het alleen worden ontsleuteld door gemachtigde gebruikers. Deze versleuteling blijft van toepassing op het document of e-mailbericht, zelfs als de naam wordt gewijzigd. U kunt bovendien gebruiksrechten en -beperkingen configureren, zoals de volgende voorbeelden:

- Alleen gebruikers binnen uw organisatie kunnen het document of e-mailbericht openen.

- Alleen gebruikers in de marketingafdeling kunnen het document of e-mailbericht bewerken en afdrukken terwijl alle andere gebruikers in uw organisatie het document of e-mailbericht alleen kunnen bekijken.

- Gebruikers kunnen een e-mailbericht niet doorsturen.

- Documenten of e-mailberichten die worden verzonden naar zakenpartners, kunnen niet worden geopend na een opgegeven datum.

Zie [Aangepaste sjablonen configureren voor Azure Rights Management](../deploy-use/configure-custom-templates.md) voor meer informatie over de sjablonen en het configureren van deze gebruiksrechten en -beperkingen.

Zie [Wat is Azure Rights Management?](../understand-explore/what-is-azure-rms.md) voor meer informatie over Azure Rights Management en hoe het werkt.

> [!IMPORTANT]
> Als u een label voor het toepassen van Rights Management-beveiliging wilt configureren, moet de Azure Rights Management-service zijn geactiveerd voor uw organisatie. Zie [Azure Rights Management activeren](../deploy-use/activate-service.md) als u dit nog niet hebt gedaan.


## Een label configureren om Rights Management-beveiliging toe te passen

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
 
2. Klik vervolgens in het hub-menu op **Bladeren** en typ **Informatie** in het filtervak. Selecteer **Azure Information Protection**.

3. Selecteer op de blade **Azure Information Protection** het label dat u wilt configureren om Rights Management-beveiliging toe te passen.

4. Configureer op de blade **Label** in de sectie **Set RMS template for protecting documents and emails containing this label (RMS-sjabloon instellen voor het beveiligen van documenten en e-mailberichten met dit label)** het volgende:

    - Als u **RMS-sjabloon selecteren uit** ziet: selecteer **Azure RMS**. 
    
        Selecteer **AD RMS** en de bijbehorende configuratieopties niet zonder hulp van Microsoft. Als u geïnteresseerd bent in het testen van Azure Information Protection met Active Directory Rights Management Services, stuurt u een e-mailbericht naar askipteam@microsoft.com. 
    
    - Voor **RMS-sjabloon selecteren**: klik op de vervolgkeuzelijst en selecteer de sjabloon die u wilt gebruiken om documenten en e-mailberichten met dit label te beveiligen.

        > [!NOTE] Als u een nieuwe sjabloon maakt nadat u de blade **Label** hebt geopend, sluit u deze blade en gaat u terug naar stap 3, zodat uw nieuwe sjabloon voor selectie wordt opgehaald uit Azure.

5. Klik op **Opslaan**.

6. Maak de wijzigingen beschikbaar voor gebruikers door op de blade **Azure Information Protection** op **Publiceren** te klikken.

## Volgende stappen

Gebruik de koppelingen in de sectie [Het beleid van uw organisatie configureren](configure-policy.md#configuring-your-organization-s-policy) voor meer informatie over het configureren van uw Azure Information Protection-beleid.  



<!--HONumber=Jul16_HO5-->


