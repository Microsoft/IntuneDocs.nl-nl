---
title: Zelfstudie voor snel starten met Azure Information Protection - Stap 4 | Azure Rights Management
description: Stap 4 in de introductiezelfstudie om Microsoft Azure Information Protection snel uit te proberen voor uw organisatie, met slechts 4 stappen die minder dan 15 minuten duren.
author: cabailey
manager: mbaldwin
ms.date: 08/10/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 468748c1-49d6-4c3e-a612-9c584acdc782
translationtype: Human Translation
ms.sourcegitcommit: d17bacf8e148622db0e2393f40d3fd37c8f086eb
ms.openlocfilehash: a36433167462275e91059f9eb3a2141ffa2797d5


---

# Stap 4: Zie classificatie, labels en beveiliging in actie 

>*Van toepassing op: Azure Information Protection preview*

**[ Deze informatie is voorlopig en kan worden gewijzigd. ]**

Nu u een geopend Word-document hebt en de Azure Information Protection-client is geïnstalleerd, kunt u zien hoe eenvoudig het is om het document te labellen en te beveiligen met het beleid dat we hebben geconfigureerd.

De classificatie en beveiliging vinden plaats als u het document bewaart, maar eerst gebruiken we het niet-bewaarde document om te laten zien hoe eenvoudig u labels kunt toepassen en wijzigen.

### Ons standaardlabel handmatig wijzigen:

- Selecteer op de Information Protection-balk het label **Persoonlijk**. U wordt gevraagd waarom u het classificatieniveau wilt verlagen. Selecteer **Voor dit bestand is deze classificatie niet meer vereist** en klik op **Bevestigen**.  

    De waarde **Gevoeligheid** wijzigt in **Persoonlijk**.

    ![Stap 4 - Zelfstudie voor snel starten met Azure Information Protection - vraag om bevestiging om te verlagen](../media/confirm-lowering.png)

### De classificatie geheel verwijderen:

- Klik op de Information Protection-balk op het pictogram **Label bewerken** naast **Persoonlijk**. Hiermee worden de beschikbare labels weergegeven. In plaats van een van de labels te kiezen, klikt u op het pictogram **Label verwijderen**. Klik op **OK** om te bevestigen en geef vervolgens de reden voor deze actie op.  

    U ziet dat de waarde voor **Gevoeligheid** wordt ingesteld op **Niet ingesteld**. Dit is wat gebruikers in eerste instantie zien als u geen standaardlabel instelt.

    ![Zelfstudie voor snel starten met Azure Information Protection Stap 4- classificatie verwijderen](../media/sensitivity-not-set.png)


### Als u een aanbevelingsvraag voor het labellen en automatische bescherming wilt:

1. Typ in het Word-document een geldig creditcardnummer, bijvoorbeeld: **4242 4242-4242 4242**. 

2. Bewaar het document (gebruik een bestandsnaam of een locatie). 

3. De volgende prompt verschijnt: **Het wordt aanbevolen dit bestand als Vertrouwelijk te markeren**. Klik op **Nu wijzigen**.

    ![Zelfstudie voor snel starten met Azure Information Protection Stap 4- prompt aanbevelen](../media/change-now.png)

    U ziet direct het watermerk van de naam van uw organisatie op de pagina en de voettekst met de tekst **Gevoeligheid: vertrouwelijk**. 

    Als u ervoor hebt gekozen om een RMS-sjabloon te gebruiken, is het bestand ook beveiligd met het Azure Rights Management-sjabloon dat u hebt opgegeven. U kunt dit bevestigen door op het tabblad **Bestand** te klikken en de gegevens voor **Document beveiligen** weer te geven. Als u de standaard vertrouwelijke sjabloon gebruikt, ziet u dat het document is beperkt tot interne gebruikers is (gebruikers buiten uw organisatie kunnen het document niet openen) en de inhoud kan niet worden gekopieerd of afgedrukt. Als de eigenaar van het document bent, kunt u het kopiëren en afdrukken, maar als u het document aan andere gebruikers in uw organisatie per e-mail verzendt, kunnen zij deze acties mogelijk niet uitvoeren.

> [!NOTE]
>Als u problemen hebt met het uitvoeren van deze stappen klikt u op het tabblad **Start** in de groep **Beveiliging** op **Beveiligen** en klikt u vervolgens op **Help en feedback**. 
>
>In het dialoogvenster **Microsoft Azure Information Protection** klikt u op **Feedback verzenden**. Hiermee wordt een e-mail verzonden aan het Information Protection-team en worden logbestanden van uw pc toegevoegd om vast te stellen wat het probleem is.

##  Volgende stappen

Nu u het standaard beveiligingsbeleid van Azure Information Protection hebt gezien en weet hoe het labelen van Word-documenten werkt, kunt u een aantal andere instellingen uitproberen en zien hoe deze werken in andere Office-toepassingen die Azure Information Protection ondersteunen, zoals Excel, PowerPoint en Outlook. Als deze toepassingen geopend waren toen u de Azure Information Protection-client installeerde, sluit u de toepassingen en opent u ze opnieuw voordat u ze met Azure Information Protection gebruikt.

U kunt bijvoorbeeld de standaardtitel **Gevoeligheid** op de menubalk van de Information Protection-balk wijzigen in een andere titel. U kunt de knopinfo, de labelkleuren, de volgorde van de labels en hun namen wijzigen. U kunt nieuwe labels maken en uw eigen automatische regels definiëren. U kunt uw watermerken opschonen door de grootte en de kleur te wijzigen en het watermerk horizontaal plaatsen in plaats van diagonaal.

Houd er rekening mee dat als u watermerken met Excel gebruikt, dat deze alleen zichtbaar zijn in de modus voor de pagina-indeling en de afdrukvoorbeeldmodus en wanneer het document wordt afgedrukt.

Telkens wanneer u in Azure Portal instellingen voor het Information Protection-beleid, moet u de wijzigingen **opslaan** en vervolgens **publiceren**. Omdat u op meerdere blades wijzigingen kunt aanbrengen, is het verstandig om te controleren of niet op alle blades de knop **Opslaan** is ingeschakeld, waarmee wordt aangegeven dat bepaalde wijzigingen niet zijn opgeslagen. Als uw Office-toepassing open stond tijden het publiceren van nieuwe wijzigingen sluit u de toepassing en opent u deze opnieuw om het nieuwste beleid te downloaden.

Als u klaar bent met uitproberen, is het wellicht handig de [veelgestelde vragen voor Azure Information Protection](faq.md) te bekijken.




<!--HONumber=Aug16_HO2-->


