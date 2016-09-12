![](../media/AzRMS_QuickStartSteps3.PNG)

Voor deze stap maakt u eerst in Word een document dat u wilt beveiligen. Sla het op onder de naam **Confidential.docx**. Voor deze zelfstudie maakt het niet uit welke tekst het document bevat, maar het is wel belangrijk dat er wat tekst in staat, zodat u gemakkelijker kunt controleren of de bevoegde ontvanger het document kan lezen. Typ bijvoorbeeld: **Als u dit kunt lezen vanuit de e-mailbijlage, heeft de afzender een bestand gedeeld dat is beveiligd met Azure RMS.**

U kunt dit document vervolgens veilig delen per e-mail.

![Schermafbeeldingen: Azure RMS-bestanden delen per e-mail](../media/AzRMS_Tutorial_3_Screenshots.png)

#### Uw document veilig delen per e-mail

1.  Maak met Outlook een nieuw bericht en voeg het bestand dat u zojuist hebt gemaakt, als bijlage toe.

2.  Typ in het vak **Aan** een of meer zakelijke e-mailadressen. Zorg ervoor dat u een zakelijk e-mailadres opgeeft, zoals **janetm@contoso.com** of **p.dover@fabrikam.com**, omdat Azure Rights Management op dit moment geen ondersteuning biedt voor persoonlijke e-mailadressen die u mogelijk thuis gebruikt via uw internetprovider. U hoeft niet uit te zoeken of degene aan wie u het bericht verzendt, ook Azure Rights Management heeft.

3.  Typ een onderwerp, zoals  **Vertrouwelijke documenten**, en typ een kort bericht in de e-mail, zoals **Lees dit vertrouwelijke document en deel het niet met anderen.**

4.  Klik daarna op het tabblad **Bericht** in de groep **RMS**. Klik vervolgens op **Beveiligd delen** en nogmaals op **Beveiligd delen**:

5.  In het dialoogvenster **Beveiligd delen**:

    1.  Selecteer **Lezer: Alleen weergeven**.

        Dit betekent dat ontvangers het document wel kunnen bekijken, maar niet kunnen bewerken of afdrukken.

    2.  Selecteer **Mij e-mailen wanneer iemand deze documenten probeert te openen**.

        U krijgt een e-mailmelding telkens wanneer ontvangers proberen de bijlage te openen en ook als iemand anders probeert deze te openen, bijvoorbeeld wanneer de ontvanger het e-mailbericht aan een collega doorstuurt. In dit laatste scenario ziet u dat de toegang is geweigerd. Op basis van de gebruikersgegevens kunt u vervolgens beslissen of u deze persoon een kopie van het document wilt verzenden dat hij/zij kan openen.

    3.  Selecteer **Mij toestaan direct de toegang tot deze documenten in te trekken**.

        Voor deze optie is vereist dat ontvangers telkens wanneer ze de bijlage openen, verbinding hebben met internet. Deze optie heeft als voordeel dat als u het document later intrekt, gebruikers de bijlage de volgende keer niet meer kunnen openen. Als u deze optie niet selecteert, kunnen ontvangers de bijlage mogelijk ook zonder internetverbinding openen. Deze optie heeft als nadeel dat als u het document later intrekt, dit wellicht gebeurt met enige vertraging.

    4.  Klik op **Nu verzenden**.

        Het e-mailbericht met bijlage wordt verzonden naar de e-mailadressen die u hebt opgegeven. Naast uw e-mailbericht zien ontvangers instructies over het lezen van het bijgevoegde document dat is beveiligd met Azure Rights Management.

Nu u het beveiligde document hebt verzonden, kunt u de ontvangers vragen om te kijken of het document is aangekomen en het vervolgens te openen. Sluit Outlook niet, omdat we het opnieuw gebruiken in onze laatste stap, voor het bijhouden van de bijlage.

|Als u meer informatie wilt|Aanvullende informatie|
|--------------------------------|--------------------------|
|Volledige instructies en alternatieve methoden voor het beveiligen van bestanden die u via e-mail deelt   →|[Een bestand beveiligen dat u per e-mail deelt met de Rights Management-toepassing voor delen.](../rms-client/sharing-app-protect-by-email.md)|
|Informatie over de opties in het dialoogvenster **Beveiligd delen**   →|[De opties in het dialoogvenster voor de Rights Management-toepassing voor delen](../rms-client/sharing-app-dialog-box.md)|


<!--HONumber=Jun16_HO4-->


