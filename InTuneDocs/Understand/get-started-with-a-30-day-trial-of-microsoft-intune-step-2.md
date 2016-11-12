---
title: Gebruikers toevoegen aan uw 30-daagse evaluatieversie van Intune | Microsoft Intune
description: Zo kunt u gebruikers toevoegen, afzonderlijk of in bulk, wanneer u zich aanmeldt voor een gratis, 30-daagse evaluatieversie van Intune
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 08/09/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9e40999b-46f7-447b-8974-72af82bec7ef
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: a49e3fc392b0319d977bce8476d838172e56fe74


---

# Gebruikers toevoegen aan uw 30-daagse evaluatieversie van Microsoft Intune
Nu u uw account hebt ingesteld, kunt u met de wizard **Nieuwe gebruikers** afzonderlijke gebruikersaccounts toevoegen aan Intune, of met de wizard **Gebruikers bulksgewijs toevoegen** meerdere gebruikers tegelijk toevoegen (zie de instructies in deze sectie).  Voordat u begint, is het belangrijk dat u weet hoe Intune met beheerdersaccounts omgaat.

Een tenantbeheerder gebruikt het Office 365-beheercentrum om gebruikers toe te voegen aan de **Groep gebruikers** van Microsoft Intune. Door gebruikers toe te voegen aan de  **Groep gebruikers** worden Intune-abonnementslicenties toegewezen aan gebruikers. Dit is ook de manier waarop u ervoor dat gebruikers worden weergegeven in de Microsoft Intune-beheerconsole.

In tegenstelling tot gewone gebruikersaccounts worden beheerdersaccounts voor Intune niet gemaakt in het Office 365-beheercentrum. In plaats daarvan wijst u alleen-lezentoegang of beheerdersrechten met volledige toegang toe aan gebruikers met behulp van de beheerconsole in de werkruimte **Beheer** onder **Beheermanagement**. Servicebeheerders aan wie alleen-lezentoegang is toegewezen, kunnen de Intune-instellingen niet wijzigen, maar ze kunnen gegevens bekijken en rapporten uitvoeren. Servicebeheerders met volledige toegang hebben alle beschikbare beheerdersrechten.

U kunt informatie over tenantbeheerders weergeven met behulp van de Intune-beheerconsole, maar u kunt hier geen tenantbeheerders maken. Standaard wordt de eigenaar van het abonnement een tenantbeheerder voor uw Microsoft Intune-service en heeft deze volledige toegang tot zowel het Office 365-beheercentrum als de Intune-beheerconsole. U kunt het beste minstens één extra tenantbeheerdersaccount maken met behulp van het Office 365-beheercentrum om te helpen taken te delegeren en om te voorkomen dat u geen toegang meer hebt tot uw Intune-beheerdersaccount als u uw wachtwoord vergeet.

## Afzonderlijke gebruikersaccounts toevoegen
Voer de volgende stappen uit om extra gebruikersaccounts te maken in de evaluatieversie van uw tenant. Houd er rekening mee dat elk gebruikersaccount dat u toevoegt, telt als een van de 100 licenties die u krijgt als onderdeel van uw gratis evaluatieversie van Intune.

1.  Kies in het [Office 365-beheercentrum](http://go.microsoft.com/fwlink/?LinkID=787455) achtereenvolgens **Gebruikers toevoegen** &gt; **Nieuw**&gt; **Gebruiker** om de wizard **Nieuwe gebruikers** te starten.

2.  Vul de vereiste velden in op de pagina **Details** .

3.  Stel op de pagina **Instellingen** de **locatie** voor de gebruiker in.

4.  Kies op de pagina **Groep** de optie **Volgende** om de standaardinstelling te accepteren en een licentie voor Intune toe te wijzen aan het account van de gebruiker.

5.  Geef op de pagina **E-mail** maximaal vijf e-mailadressen op waarop u een melding van de gebruikersnaam en het tijdelijke wachtwoord voor het account wilt ontvangen. Meerdere e-mailadressen moeten worden gescheiden door puntkomma's (;). Wanneer u klaar bent, kiest u **Maken** om de gebruiker toe te voegen aan uw abonnement.

6.  Op de pagina **Resultaten** kunt u de nieuwe accountnaam en het tijdelijke wachtwoord bekijken. Intune maakt automatisch een tijdelijk wachtwoord.

7.  Wanneer de nieuwe gebruiker wordt weergegeven in het Office 365-beheercentrum, controleert u of de nieuwe gebruiker is gemaakt:

    1.  Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) de optie **Beheer**&gt;**Bedrijfsportal** en schuif vervolgens naar de onderkant van het scherm. Kopieer de URL die wordt weergegeven onder **Intune-bedrijfsportal**.

    2.  Open een nieuw browservenster in de privacymodus (kies in Internet Explorer **Extra** &gt; **InPrivate-browsing**) of open een nieuw browservenster op een ander apparaat en navigeer vervolgens naar de URL die u in de vorige stap hebt gekopieerd. Wanneer gebruikers zich voor het eerst aanmelden, moeten deze een nieuw wachtwoord opgeven voor het account.

## Gebruikers bulksgewijs toevoegen
Als u meerdere gebruikers tegelijk aan Intune wilt toevoegen, gebruikt u de wizard **Gebruikers bulksgewijs toevoegen** voor het uploaden van een bestand met door komma's gescheiden waarden (CSV) dat de gebruikersgegevens bevat. Met behulp van koppelingen in de wizard kunt u een lege sjabloon en een voorbeeld van een CSV-bestand downloaden. De eerste rij van uw CSV-bestand moet alle kolomlabels voor gebruikersgegevens, in de juiste volgorde, bevatten. Vervolgens moet u voor elke gebruiker in het CSV-bestand de **gebruikersnaam** (zoals **bob@contoso.com**) en een **weergavenaam** (zoals **Bob Kelly**) opnemen.

1.  Kies in het [Office 365-beheercentrum](http://go.microsoft.com/fwlink/?LinkID=787455) de optie **Gebruikers**&gt;**Nieuw**.

2.  Klik op **Bulktoevoeging** om de wizard Gebruikers bulksgewijs toevoegen te starten.

3.  Klik op de pagina **Bestand selecteren** op **Bladeren** om een bestaand CSV-bestand op te geven en te laden vanaf uw computer. U kunt ook een voorbeeld van een CSV-bestand of een leeg sjabloonbestand downloaden door op de koppelingen in de wizard te klikken.

4.  Bekijk op de pagina **Verificatie** de resultaten en klik vervolgens op **Weergeven** voor meer informatie.

5.  Controleer op de pagina **Instellingen** of de aanmeldingsstatus **Toegestaan** is en stel de **locatie** in. Deze instellingen zijn van toepassing op alle gebruikersaccounts die zijn toegevoegd door het CSV-bestand.

6.  Klik op de pagina **Groep** op **Volgende** om de standaardinstelling te accepteren en wijs een licentie voor Intune toe aan alle gebruikersaccounts die zijn toegevoegd door het CSV-bestand. Het selectievakje waarmee een licentie voor Intune aan elk account wordt toegewezen, is standaard ingeschakeld.

7.  Geef op de pagina **E-mail** maximaal vijf e-mailadressen op voor het ontvangen van de gebruikersnamen en tijdelijke wachtwoorden die voor elk account door Intune zijn gemaakt. Meerdere e-mailadressen moeten worden gescheiden met puntkomma's (;). Kies **Maken** om de gebruikers toe te voegen aan uw abonnement.

8.  Op de pagina **Resultaten** kunt u de accountnamen en tijdelijke wachtwoorden voor elke gebruikersaccount bekijken.

Elk gebruikersaccount dat u via importeren hebt toegevoegd, wordt nu weergegeven in het knooppunt **Gebruikers** in het Office 365-beheercentrum. Wanneer nieuwe gebruikers zich voor de eerste keer aanmelden, moeten deze een nieuw wachtwoord voor hun gebruikersaccount opgeven.

### Volgende stappen
Gefeliciteerd! U hebt zojuist stap 2 van de procedure voor de *Microsoft Intune-evaluatie* voltooid.

>[!div class="step-by-step"]

>[&larr; **Aanmelden voor een evaluatieversie**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)     [**Groepen maken** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md)  



<!--HONumber=Oct16_HO4-->


