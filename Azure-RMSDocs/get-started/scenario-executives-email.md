---
# required metadata

title: Scenario: leidinggevenden wisselen veilig vertrouwelijke informatie uit | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: e18cf5df-859e-4028-8d19-39b0842df33d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Scenario: leidinggevenden wisselen veilig vertrouwelijke informatie uit

*Van toepassing op: Azure Rights Management, Office 365*

In dit scenario en de ondersteunende gebruikersdocumentatie wordt gebruikgemaakt van Azure Rights Management zodat leidinggevenden veilig e-mailberichten en bijlagen met elkaar kunnen uitwisselen en de toegang tot de leidinggevenden automatisch wordt beperkt door beleidsregels zonder dat daarvoor speciale actie hoeft te worden ondernomen. De e-mailberichten en bijlagen worden automatisch door Azure Rights Management beveiligd.

U kunt desgewenst in het onderwerp van het e-mailbericht een uitzondering aan de regel toevoegen, zoals de afkorting DNP (voor 'Do Not Protect' oftewel 'Niet beveiligen'). Leidinggevenden kunnen dit dan opgeven als ze een onbeveiligd e-mailbericht willen verzenden naar andere leidinggevenden zodat deze het bericht bijvoorbeeld kunnen bekijken voordat ze het naar anderen doorsturen.

De instructies zijn van toepassing op de volgende omstandigheden:

-   Leidinggevenden delen vertrouwelijke informatie met elkaar die niet met anderen mag worden gedeeld.

-   Leidinggevenden hoeven er hierbij alleen op te letten dat ze deze e-mailberichten naar een zakelijk e-mailadres verzenden en niet naar een persoonlijk e-mailadres.

-   Leidinggevenden kunnen de regel zelf uitschakelen als ze een onbeveiligd e-mailbericht naar andere leidinggevenden willen verzenden.

## Instructies voor de implementatie
![Beheerdersinstructies voor de snelle implementatie van Azure RMS](../media/AzRMS_AdminBanner.png)

Zorg ervoor dat aan de volgende vereisten is voldaan en voer vervolgens de instructies voor de ondersteunende procedures uit voordat u doorgaat met de gebruikersdocumentatie.

## Vereisten voor dit scenario
De instructies voor dit scenario gelden alleen als aan de volgende voorwaarden is voldaan:

|Vereiste|Als u meer informatie wilt|
|---------------|--------------------------------|
|U hebt voor Office 365 of Azure Active Directory accounts en groepen voorbereid:<br /><br />Een e-mailgroep met de naam **Leidinggevenden** en alle leidinggevenden zijn lid van deze groep<br /><br />Een e-mailgroep met de naam **RMS-beheerders**, en alle beheerders die Azure RMS configureren zijn lid van deze groep|[Voorbereiden voor Azure Rights Management](https://technet.microsoft.com/library/jj585029.aspx)|
|Uw Azure Rights Management-tenantsleutel wordt beheerd door Microsoft. U maakt geen gebruik van BYOK|[Uw Azure Rights Management-tenantsleutel plannen en implementeren](https://technet.microsoft.com/library/dn440580.aspx)|
|Azure Rights Management is geactiveerd|[Azure Rights Management activeren](https://technet.microsoft.com/library/jj658941.aspx)|
|Een van de volgende configuraties:<br /><br />Exchange Online is ingeschakeld voor Azure Rights Management<br /><br />De RMS-connector is geïnstalleerd en geconfigureerd voor Exchange on-premises|Voor Exchange Online: zie de sectie **Exchange Online: IRM-configuratie** in [Toepassingen configureren voor Azure Rights Management](https://technet.microsoft.com/library/jj585031.aspx).<br /><br />Voor Exchange on-premises: [De Azure Rights Management-connector implementeren](https://technet.microsoft.com/library/dn375964.aspx)|
|U hebt een aangepaste sjabloon geconfigureerd, zoals hieronder wordt beschreven|[Aangepaste sjablonen configureren voor Azure Rights Management](https://technet.microsoft.com/library/dn642472.aspx)|
|U hebt een transportbeveiligingsregel geconfigureerd voor IRM, zoals in dit artikel wordt beschreven|Voor Exchange Online: [Een transportbeveiligingsregel maken](https://technet.microsoft.com/library/dd302432.aspx)<br /><br />Voor Exchange 2013: [Een transportbeveiligingsregel maken](https://technet.microsoft.com/en-us/library/dd302432%28v=exchg.150%29.asp)<br /><br />Voor Exchange 2010: [Een transportbeveiligingsregel maken](https://technet.microsoft.com/en-us/library/dd302432%28v=exchg.141%29.aspx)|

### De aangepaste sjabloon voor leidinggevenden configureren

1.  In de klassieke Azure-portal: maak een nieuwe aangepaste sjabloon voor Azure Rights Management die de volgende waarden en instellingen bevat:

    -   Naam: **Leidinggevenden**

    -   Rechten: ken aan de e-mailgroep **Leidinggevenden** de rechten voor **Mede-eigenaar** toe

    -   Bereik: selecteer de e-mailgroep **Leidinggevenden** en de e-mailgroep **RMS-beheerders**.

2.  Publiceer de nieuwe sjabloon.

3.  Alleen voor Exchange Online: vernieuw de sjablonen met de Windows PowerShell voor Exchange Online-opdracht:

    ```
    Import-RMSTrustedPublishingDomain -Name "RMS Online -1" -RefreshTemplates -RMSOnline
    ```

### De transportregel voor IRM configureren

-   Gebruik de Exchange-documentatie waarnaar wordt verwezen in de tabel voor informatie over procedures om de transportregel te maken met de volgende instellingen:

    -   Naam: **De Leidinggevenden-sjablonen toepassen op e-mailberichten van leidinggevenden**

    -   Geef de groep **Leidinggevenden** op als de afzender en de ontvanger van de regel en aanvullende voorwaarde.

    -   Selecteer voor de actie **Rechtenbeveiliging toepassen op het bericht met** en selecteer vervolgens de **Leidinggevenden**-sjabloon die u hebt geconfigureerd.

    -   Voeg de uitzondering **DNP** (als afkorting van 'Do Not Protect' oftewel 'Niet beveiligen'), of uw eigen aanduiding voor deze uitzondering, toe aan het onderwerp van het bericht.

    -   Zorg ervoor dat de regel is geconfigureerd voor **Afdwingen**.

## Instructies voor de gebruikersdocumentatie
Tenzij u instructies wilt geven voor het opgeven van **DNP** of uw eigen aanduiding van de uitzondering in het onderwerp van het e-mailbericht, hoeven er voor dit scenario geen instructies voor de procedure worden gegeven aan de gebruikers, omdat er voor het beveiligen van e-mailberichten van en naar leidinggevenden geen speciale actie is vereist. De e-mailberichten en eventuele bijlagen worden automatisch beveiligd zodat alleen de leden van de groep Leidinggevenden hiertoe toegang hebben.

Mogelijk moet u de leidinggevenden en de helpdesk echter informeren dat deze e-mailberichten automatisch worden beveiligd en hoe dit het gebruik van deze e-mailberichten kan beperken. De e-mailberichten of bijlagen kunnen bijvoorbeeld niet worden gelezen door andere personen als deze later naar anderen worden doorgestuurd. Als u de DNP-uitzondering (of gelijksoortig) hebt geconfigureerd, moet u nagaan of de helpdesk op de hoogte is van deze configuratie zodat leidinggevenden de regel zelf, zonder tussenkomst van een Exchange-beheerder, kunnen uitschakelen.

Kopieer en plak aan de hand van de volgende sjabloon de aankondiging in een bericht voor de eindgebruikers en breng de volgende wijzigingen aan zodat de instructies van toepassing zijn op uw omgeving:

1.  Vervang de exemplaren van *&lt;organisatienaam&gt;* met de naam van uw organisatie.

2.  Als u voor een andere tekst voor de uitzondering kiest in plaats van DNP, past u deze waarde en de uitleg hiervoor aan.

3.  Vervang *&lt;e-maildomein&gt;* met de naam van het e-maildomein van uw organisatie.

4.  Vervang *&lt;contactgegevens&gt;* met instructies voor de gebruikers om contact op te nemen met de helpdesk, zoals een websitekoppeling, e-mailadres of telefoonnummer.

5.  Breng eventuele aanvullende wijzigingen aan in de aankondiging en verzend deze naar de gebruikers.

In de voorbeelddocumentatie wordt getoond hoe de aankondiging, na uw aanpassingen, voor de gebruikers kan zijn weergegeven.

![Gebruikersdocumentatiesjabloon voor de snelle implementatie van Azure RMS](../media/AzRMS_UsersBanner.png)

### IT-aankondiging: e-mailberichten voor leidinggevenden van &lt;organisatienaam&gt; worden nu automatisch beveiligd
Vanaf dit moment wordt de inhoud van de e-mailberichten en eventuele bijlagen, die u naar een andere leidinggevende van &lt;organisatienaam&gt; verzendt, automatisch beveiligd zodat alleen een andere leidinggevende in het bedrijf hiertoe toegang heeft om de informatie te lezen, af te drukken, te kopiëren, enzovoort. Deze beperking geldt ook als u het e-mailbericht naar anderen doorstuurt of de bijlagen opslaat. Met deze beveiliging wordt voorkomen dat vertrouwelijke of gevoelige informatie verloren gaat.

Als u wilt dat anderen die geen leidinggevende zijn bij &lt;organisatienaam&gt; de informatie kunnen lezen en bewerken die u in deze e-mailberichten verzendt, moet u deze afzonderlijk naar hen verzenden. Of als u de automatische beveiliging wilt uitschakelen, typt u de letters **DNP** (afkorting voor 'Do Not Protect' oftewel 'Niet beveiligen') in het onderwerp van het e-bericht.

Wanneer u vertrouwelijke bedrijfsinformatie verzendt naar een andere leidinggevende van &lt;organisatienaam&gt; moet u deze verzenden naar het zakelijke e-mailadres (*naam*@&lt;e-maildomein&gt;) en niet naar een persoonlijk e-mailadres.

**Hebt u hulp nodig?**

-   Neem contact op met de helpdesk: &lt;contactgegevens&gt;

### Voorbeeld van gebruikersdocumentatie
![Voorbeeld van gebruikersdocumentatie voor de snelle implementatie van Azure RMS](../media/AzRMS_ExampleBanner.png)

#### IT-aankondiging: e-mailberichten van leidinggevenden bij VanArsdel worden nu automatisch beveiligd
Vanaf dit moment wordt de inhoud van de e-mailberichten en eventuele bijlagen, die u naar een andere leidinggevende van VanArsdel verzendt, automatisch beveiligd zodat alleen een andere leidinggevende in het bedrijf hiertoe toegang heeft om de informatie te lezen, af te drukken, te kopiëren, enzovoort. Deze beperking geldt ook als u het e-mailbericht naar anderen doorstuurt of de bijlagen opslaat. Met deze beveiliging wordt voorkomen dat vertrouwelijke of gevoelige informatie verloren gaat.

Als u wilt dat anderen die geen leidinggevende zijn bij VanArsdel de informatie kunnen lezen en bewerken die u in deze e-mailberichten verzendt, moet u deze afzonderlijk naar hen verzenden. Of als u de automatische beveiliging wilt uitschakelen, typt u de letters **DNP** (afkorting voor 'Do Not Protect' oftewel 'Niet beveiligen') in het onderwerp van het e-bericht.

Wanneer u vertrouwelijke bedrijfsinformatie verzendt naar een andere leidinggevende van VanArsdel, moet u deze verzenden naar het zakelijke e-mailadres (*naam*@vanarsdelltd.com) en niet naar een persoonlijk e-mailadres.

**Hebt u hulp nodig?**

-   Neem contact op met de helpdesk: helpdesk@vanarsdelltd.com



<!--HONumber=May16_HO2-->


