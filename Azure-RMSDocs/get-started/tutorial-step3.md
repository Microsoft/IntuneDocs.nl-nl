---
# required metadata

title: Zelfstudie voor snel aan de slag met Azure RMS, stap 3 | Azure RMS
description: De derde stap van een zelfstudie voor het snel uitproberen van Microsoft Azure Rights Management voor uw organisatie, met slechts 5 stappen die u in minder dan 15 minuten kunt uitvoeren.
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: c604e749-8918-40e8-8148-6bd000cb2be2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Snel aan de slag met Azure RMS, stap 3: e-mail het document dat u wilt beveiligen

*Van toepassing op: Azure Rights Management, Office 365*


Ga naar: 
> [!div class="op_single_selector"]
- [Inleiding](quick-start-tutorial.md)
- [Stap 1: activeer Azure RMS](tutorial-step1.md)
- [Stap 2: installeer RMS-app voor delen](tutorial-step2.md)
- [Stap 3: e-mail het vertrouwelijke document](tutorial-step3.md)
- [Stap 4: de ontvanger leest het document](tutorial-step4.md)
- [Stap 5: houd uw document bij](tutorial-step5.md)


Voor deze stap maakt u eerst in Word een document dat u wilt beveiligen. Sla het op met de naam **Confidential.docx**. Voor deze zelfstudie maakt het niet uit welke tekst het bevat, maar u wilt waarschijnlijk dat er wat tekst in staat, zodat u gemakkelijker kunt controleren of de bevoegde ontvanger het kan lezen. Typ bijvoorbeeld: **Als u dit kunt lezen vanuit uw e-mailbijlage, heeft de afzender een bestand gedeeld dat is beveiligd met Azure RMS.**

U kunt dit document vervolgens veilig delen per e-mail.

![Stap 3 van de zelfstudie voor snel starten met Azure RM](../media/AzRMS_Tutorial_3_Screenshots.png)

### Uw document veilig delen per e-mail

1.  Maak met Outlook een nieuw bericht en koppel het bestand dat u zojuist hebt gemaakt.

2.  Typ in het vak **Aan** een of meer zakelijke e-mailadressen. Zorg dat u een zakelijk e-mailadres opgeeft, zoals **janetm@contoso.com** of **p.dover@fabrikam.com** omdat Azure Rights Management op dit moment geen ondersteuning biedt voor persoonlijke e-mailadressen die u bijvoorbeeld thuis gebruikt via uw internetprovider. Maakt u zich geen zorgen of de geadresseerde Azure Rights Management heeft of niet.

3.  Typ een onderwerp, zoals **Vertrouwelijke documenten** en typ een kort bericht voor de e-mail, zoals **Lees dit vertrouwelijke document en deel het niet met anderen.**

4.  Klik vervolgens op het tabblad **Bericht** in de groep **RMS** op **Beveiligd delen** en klik vervolgens nogmaals op **Beveiligd delen**:

5.  In het dialoogvenster **Beveiligd delen**:

    1.  Selecteer **Lezer: Alleen weergeven**.

        Dit betekent dat onze ontvangers het document kunnen weergeven, maar niet bewerken of afdrukken.

    2.  Selecteer **Mij e-mailen wanneer iemand deze documenten probeert te openen**.

        U krijgt telkens een e-mailmelding wanneer de ontvangers proberen de bijlage te openen en ook als iemand anders probeert deze te openen, bijvoorbeeld wanneer de ontvanger het e-mailbericht aan een collega verzendt. In dit laatste scenario ziet u dat de toegang is geweigerd en op basis van de gebruikersgegevens kunt u beslissen of u deze persoon een kopie van het document wilt verzenden die hij/zij kan openen.

    3.  Selecteer **Mij toestaan direct de toegang tot deze documenten in te trekken**.

        Voor deze optie is vereist dat de ontvangers een internetverbinding hebben telkens wanneer ze de bijlage openen. Deze optie heeft als voordeel dat als u het document later intrekt, de gebruikers de bijlage de volgende keer niet meer kunnen openen. Als u deze optie niet selecteert, kunnen de ontvangers de bijlage mogelijk zelfs zonder internetverbinding openen. Deze optie heeft als nadeel dat als u het document later intrekt, dit mogelijk gebeurt met enige vertraging.

    4.  Klik op **Nu verzenden**.

        Het e-mailbericht met bijlage wordt verzonden naar de e-mailadressen die u hebt opgegeven. Naast uw e-mailbericht zien ze instructies over het lezen van het bijgevoegde document dat is beveiligd met Azure Rights Management.

Nu u het beveiligde document hebt verzonden, kunt u uw ontvangers vragen om hierop te wachten en het vervolgens te openen. Sluit Outlook niet, omdat we het opnieuw gebruiken in onze laatste stap, voor het bijhouden van de bijlage.

|Als u meer informatie wilt|Aanvullende informatie|
|--------------------------------|--------------------------|
|Volledige instructies en alternatieve methoden voor het beveiligen van bestanden die u via e-mail deelt|[Een bestand beveiligen dat u per e-mail deelt met de Rights Management-toepassing voor delen.](../rms-client/sharing-app-protect-by-email.md)|
|Informatie over de opties in het dialoogvenster **Beveiligd delen**|[De opties in het dialoogvenster voor de Rights Management-toepassing voor delen](../rms-client/sharing-app-dialog-box.md)|


>[!div class="step-by-step"] [« Stap 2](tutorial-step2.md)
[Stap 4 »](tutorial-step4.md)

<!--HONumber=May16_HO2-->


