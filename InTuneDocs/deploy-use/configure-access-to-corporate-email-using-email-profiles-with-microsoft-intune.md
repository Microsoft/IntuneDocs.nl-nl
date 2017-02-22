---
title: Toegang tot zakelijke e-mail via e-mailprofielen | Microsoft Docs
description: Er kunnen e-mailprofielinstellingen worden gebruikt om e-mailtoegangsinstellingen te configureren voor specifieke e-mailclients op mobiele apparaten.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 10f0cd61-e514-4e44-b13e-aeb85a8e53ae
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 3ee87c8f6104b06c8a9492566ff160540624f17e
ms.openlocfilehash: 8f35cf70d0c97afc88eba38b1eaff5e2e38425d0


---

# <a name="configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune"></a>De toegang tot zakelijke e-mail configureren met e-mailprofielen bij Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Veel mobiele platforms hebben een systeemeigen e-mailclient die wordt meegeleverd als onderdeel van het besturingssysteem. Sommige van deze clients kunnen worden ingesteld met behulp van e-mailprofielen, zoals in dit onderwerp wordt beschreven.

De e-mailprofielinstellingen kunnen worden gebruikt om e-mailtoegangsinstellingen te configureren voor specifieke e-mailclients op mobiele apparaten. Op de ondersteunde platforms kunnen de systeemeigen e-mailclients met Microsoft Intune zo worden ingesteld dat gebruikers op hun eigen apparaten toegang kunnen krijgen tot hun zakelijke e-mail zonder dat ze extra instellingen hoeven te configureren.

Als u extra maatregelen wilt nemen om gegevensverlies te voorkomen, gebruikt u [Voorwaardelijke toegang](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), waarmee de toegang tot het postvak van de gebruiker wordt beheerd voor alle e-mailclients, inclusief de systeemeigen e-mailclients.

IT-beheerders of gebruikers kunnen er ook voor kiezen om alternatieve e-mailclients te installeren (zoals Microsoft Outlook voor Android of iOS). Deze e-mailclients bieden mogelijk geen ondersteuning voor e-mailprofielen en kunnen niet worden ingesteld met behulp van Intune-e-mailprofielen.  

U kunt e-mailprofielen gebruiken om de systeemeigen e-mailclient te configureren op de volgende apparaattypen:
-    Windows Phone 8.1 en hoger
-    Windows 10 (voor de desktop), Windows 10 Mobile en hoger
-    iOS 8.0 en hoger
-    Samsung KNOX Standard (4.0 of hoger)
-    Android for Work

>[!NOTE]
>Intune bevat twee e-mailprofielen voor Android for Work, een voor de e-mail-app van Gmail en een voor de e-mail-app van Nine Work. Deze apps zijn beschikbaar in de Google Play-store en bieden ondersteuning voor verbindingen met Exchange. Als u de connectiviteit voor e-mail wilt inschakelen, implementeert u een van deze e-mail-apps op apparaten van uw gebruikers, en maakt en implementeert u vervolgens het juiste profiel.

U kunt een e-mailaccount instellen op het apparaat en daarnaast ook bepalen hoeveel e-mail er moet worden gesynchroniseerd en, afhankelijk van het apparaattype, welke inhoudstypen uw wilt synchroniseren.

>[!NOTE]
>
>Als de gebruiker al een e-mailprofiel heeft geïnstalleerd voordat er een profiel wordt geïnstalleerd door Intune, is het resultaat van de implementatie van het Intune-e-mailprofiel afhankelijk van het apparaatplatform:

>**iOS**: het e-mailprofiel bestaat al en dit duplicaat is gedetecteerd op basis van hostnaam en e-mailadres. Het duplicaat van het e-mailprofiel dat is gemaakt door de gebruiker, blokkeert de implementatie van een Intune-profiel dat door een beheerder is gemaakt. Dit is een veelvoorkomend probleem, omdat iOS-gebruikers vaak zelf een e-mailprofiel maken en het apparaat vervolgens inschrijven. De bedrijfsportal deelt de gebruiker mee dat deze niet voldoet aan de eisen vanwege het handmatig geconfigureerde e-mailprofiel en vraagt de gebruiker dit profiel te verwijderen. De gebruiker moet het e-mailprofiel verwijderen, zodat het Intune-profiel kan worden geïnstalleerd. Als u dit probleem wilt voorkomen, vertelt u gebruikers dat ze het apparaat eerst moeten inschrijven voordat ze een e-mailprofiel installeren, zodat Intune het profiel kan installeren.

>**Windows**: er bestaat al een e-mailprofiel en dit duplicaat is gedetecteerd op basis van hostnaam en e-mailadres. Intune overschrijft het bestaande e-mailprofiel dat is gemaakt door de gebruiker.

>**Samsung KNOX**: er bestaat al een e-mailprofiel en dit duplicaat is gedetecteerd op basis van het e-mailadres. Het bestaande e-mailprofiel wordt overschreven door het Intune-profiel. Als de gebruiker dat account instelt, wordt het e-mailprofiel opnieuw overschreven door het Intune-profiel. Houd er rekening mee dat dit tot verwarring kan leiden bij de gebruiker.

>Omdat Samsung KNOX geen hostnaam gebruikt om een profiel te identificeren, wordt afgeraden om voor hetzelfde e-mailadres meerdere e-mailprofielen te maken op verschillende hosts, aangezien deze profielen elkaar overschrijven.

>**Android for Work**: het Intune-profiel wordt alleen toegepast op specifieke e-mail-apps in het werkprofiel van het apparaat en heeft geen invloed op de e-mailconfiguratie voor het gebruikersprofiel van het apparaat.


## <a name="secure-email-profiles"></a>Beveiligde e-mailprofielen
U kunt e-mailprofielen op twee manieren beveiligen: met een certificaat of met een wachtwoord.

### <a name="certificates"></a>Certificaten
Wanneer u het e-mailprofiel maakt, kiest u een certificaatprofiel dat u eerder hebt gemaakt in Intune. Dit wordt het identiteitscertificaat genoemd en wordt gebruikt voor verificatie aan de hand van een vertrouwd-certificaatprofiel (of basiscertificaat) om te bepalen of het apparaat van de gebruiker verbinding mag maken. Het vertrouwde certificaat wordt geïmplementeerd op de computer die de e-mailverbinding verifieert, meestal de systeemeigen e-mailserver.

Zie [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Toegang tot beveiligde bronnen met certificaatprofielen) voor meer informatie over het gebruiken en maken van certificaatprofielen in Intune.

### <a name="user-name-and-password"></a>Gebruikersnaam en wachtwoord
De gebruiker wordt geverifieerd op de systeemeigen mailserver door zijn gebruikersnaam en wachtwoord op te geven.

Het wachtwoord is niet opgenomen in het e-mailprofiel, dus de gebruiker moet dit opgeven wanneer deze de e-mailverbinding tot stand brengt.

### <a name="create-an-email-profile"></a>Een e-mailprofiel maken

1.  Ga naar de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) en kies**Beleid** &gt; **Beleid toevoegen**.

2.  Stel een van de volgende beleidstypen in:

    -   **E-mailprofiel voor Samsung KNOX Standard (4.0 en hoger)**

    -   **E-mailprofiel (iOS 8.0 en hoger)**

    -   **E-mailprofiel (Windows Phone 8.1 en hoger)**

    -   **E-mailprofiel (Windows 10 Desktop en Mobile en hoger)**

    -   **E-mailprofiel (Android for Work - Gmail)**

    -    **E-mailprofiel (Android for Work - Nine Work)**

    U kunt alleen een aangepast e-mailprofielbeleid maken en implementeren. Aanbevolen instellingen zijn niet beschikbaar.

3.  Gebruik de volgende tabel als referentie voor het configureren van e-mailprofielinstellingen:

|Naam van de instelling | Meer informatie|
| ----------- | --------------- |
    |**Naam**|Unieke naam van het e-mailprofiel.|
    |**Beschrijving**|Een beschrijving die u helpt om dit profiel te herkennen.|
    |**Host**|De hostnaam van uw bedrijfsserver die als host fungeert voor uw systeemeigen e-mailservice.|
    |**Accountnaam**|De naam van het e-mailaccount die wordt weergegeven op de apparaten van de gebruikers.|
    |**Gebruikersnaam**|Dit is het kenmerk in Active Directory (AD) of Azure AD, dat wordt gebruikt voor het genereren van de gebruikersnaam voor dit e-mailprofiel. Selecteer het primaire SMTP-adres, zoals *user1@contoso.com*, of de UPN-naam, zoals *gebruiker1* of *user1@contoso.com*.|
    |**E-mailadres**|Hoe het e-mailadres voor de gebruiker op elk apparaat wordt gegenereerd. Selecteer **Primaire SMTP-adres** om het primaire SMTP-adres te gebruiken voor aanmelding bij Exchange of gebruik **User Principal Name** om de volledige User Principal Name te gebruiken als het e-mailadres.|
    |**Verificatiemethode** (Android for Work, Samsung KNOX en iOS)|Selecteer **Gebruikersnaam en wachtwoord** of **Certificaten** als verificatiemethode voor het e-mailprofiel.|
    |**Selecteer een clientcertificaat voor clientverificatie (identiteitscertificaat)** (Android for Work, Samsung KNOX en iOS)|Selecteer het SCEP-clientcertificaat dat u eerder hebt gemaakt en dat wordt gebruikt voor verificatie van de Exchange-verbinding. Zie [Custom configurations for VPN profiles](secure-resource-access-with-certificate-profiles.md) (Toegang tot beveiligde bronnen met certificaatprofielen) voor meer informatie over het gebruik van certificaatprofielen in Intune. Deze optie wordt alleen weergegeven als **Certificaten** is geselecteerd als verificatiemethode.|
    |**S/MIME gebruiken** (Samsung KNOX en iOS)|Verzend uitgaande e-mail met S/MIME-versleuteling.|
    |**Handtekeningcertificaat** (Samsung KNOX en iOS)|Selecteer het handtekeningcertificaat dat wordt gebruikt om uitgaande e-mail te ondertekenen. Deze optie wordt alleen weergegeven als u het selectievakje bij **S/MIME gebruiken** hebt ingeschakeld.|
    |**Aantal dagen e-mail voor synchronisatie**|Geef op voor hoeveel dagen u e-mail wilt synchroniseren of selecteer **Onbeperkt** om alle beschikbare e-mails te synchroniseren.|
    |**Synchronisatieschema** (Android for Work, Samsung KNOX, Windows Phone 8 en hoger, Windows 10)|Selecteer het schema op basis waarvan apparaten gegevens synchroniseren met de Exchange-server. U kunt ook **Wanneer berichten binnenkomen** selecteren als u wilt dat de berichten meteen worden gesynchroniseerd wanneer ze binnenkomen of **Handmatig** selecteren als u wilt dat de gebruiker van het apparaat de synchronisatie zelf uitvoert.|
    |**SSL gebruiken**|Gebruik SSL-communicatie (Secure Sockets Layer) wanneer u e-mailberichten verzendt, e-mailberichten ontvangt en communiceert met de Exchange-server. Voor apparaten met Samsung KNOX 4.0 of hoger moet u het SSL-certificaat van uw Exchange-server exporteren en als Android Trusted Certificate Profile implementeren in Intune. Intune biedt geen ondersteuning voor toegang tot dit certificaat als het op een andere manier is geïnstalleerd op de Exchange-server.|
    |**Inhoudtype voor synchronisatie** (alle platforms met uitzondering van Android for Work - Gmail)|Selecteer de inhoudstypen die u wilt synchroniseren met apparaten.|
    |**Toestaan dat e-mails worden verzonden vanuit toepassingen van derden** (alleen iOS)|Sta de gebruiker toe dit profiel te selecteren als het standaardaccount voor het verzenden van e-mail en sta toepassingen van derden toe e-mail te openen in de systeemeigen e-mail-app, om bijvoorbeeld bestanden als bijlagen aan e-mail toe te voegen.|

> [!IMPORTANT]
>
> Als u een e-mailprofiel hebt geïmplementeerd en vervolgens de waarde van **Host** of **E-mailadres** wilt wijzigen, moet u het bestaande e-mailprofiel verwijderen en een nieuw e-mailprofiel met de vereiste waarden maken.

4.  Wanneer u klaar bent, klikt u op **Beleid opslaan**.

Het nieuwe beleid wordt weergegeven in het knooppunt **Configuratiebeleid** van de werkruimte **Beleid** .

## <a name="deploy-the-policy"></a>Het beleid implementeren

1.  Selecteer in de werkruimte **Beleid** het beleid dat u wilt implementeren en kies vervolgens **Implementatie beheren**.

2.  In het dialoogvenster **Implementatie beheren** :

    -   **Het beleid implementeren**: selecteer een of meer groepen waarvoor u het beleid wilt implementeren en kies vervolgens **Toevoegen**&gt; **OK**.

    -   **Het dialoogvenster sluiten zonder het beleid te implementeren**: kies **Annuleren**.

Een statusoverzicht en waarschuwingen op de pagina **Overzicht** van de werkruimte **Beleid** identificeren beleidsproblemen die uw aandacht nodig hebben. Bovendien wordt er een statusoverzicht weergegeven in de werkruimte Dashboard.

> [!NOTE]
> - Implementeer voor Android for Work naast het juiste e-mailprofiel ook de Gmail- of Nine Work-app.
> - Als u een e-mailprofiel van een apparaat wilt verwijderen, bewerkt u de implementatie en verwijdert u groepen waarvan het apparaat lid is. U kunt een e-mailprofiel niet op deze manier verwijderen als dit het enige e-mailprofiel op een apparaat is.



<!--HONumber=Feb17_HO2-->


