---
title: Toegang tot zakelijke e-mail via e-mailprofielen | Microsoft Intune
description: Er kunnen e-mailprofielinstellingen worden gebruikt om e-mailtoegangsinstellingen te configureren voor specifieke e-mailclients op mobiele apparaten.
keywords: 
author: Nbigman
manager: angrobe
ms.date: 07/021/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 10f0cd61-e514-4e44-b13e-aeb85a8e53ae
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: 878172811c7899237b5ebf5db9a443f10fea42dd


---

# De toegang tot zakelijke e-mail configureren met e-mailprofielen bij Microsoft Intune
Veel mobiele platforms hebben een *systeemeigen* e-mailclient die wordt meegeleverd als onderdeel van het besturingssysteem.  Sommige van deze clients kunnen worden geconfigureerd aan de hand van e-mailprofielen, zoals in dit onderwerp wordt beschreven.

Als u extra gegevensverlies wilt voorkomen (DLP), kiest u [Voorwaardelijke toegang](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), waarmee de toegang tot het postvak van een gebruiker voor een e-mailclient wordt beheerd, inclusief systeemeigen e-mailclients.

Er kunnen e-mailprofielinstellingen worden gebruikt om e-mailtoegangsinstellingen te configureren voor specifieke e-mailclients op mobiele apparaten. De meeste mobiele platforms hebben een *systeemeigen* e-mailclient die wordt meegeleverd als onderdeel van het besturingssysteem.  Op de ondersteunde platforms kunnen de systeemeigen e-mailclients door Microsoft Intune worden geconfigureerd, zodat gebruikers op hun eigen apparaten toegang krijgen tot hun zakelijke e-mail zonder een aanvullende installatie te hoeven doorlopen.  

IT-beheerders of gebruikers kunnen er ook voor kiezen om alternatieve e-mailclients te installeren, zoals Microsoft Outlook voor Android of iOS.  Deze e-mailclients bieden mogelijk geen ondersteuning voor e-mailprofielen en kunnen niet worden geconfigureerd met Microsoft Intune-e-mailprofielen.  

U kunt e-mailprofielen gebruiken om de systeemeigen e-mailclient te configureren op de volgende apparaattypen:
-   Windows Phone 8 en hoger
-   Windows 10 Desktop en hoger en Windows 10 Mobile en hoger
-   iOS 7.1 en hoger
-   Samsung KNOX Standard (4.0 of hoger)


Naast het e-mailaccount op het apparaat kunt u ook synchronisatie-instellingen configureren, zoals de hoeveelheid e-mail die u wilt synchroniseren, en afhankelijk van het apparaattype, de inhoudstypen die u wilt synchroniseren.

## Beveiligde e-mailprofielen
U kunt e-mailprofielen beveiligd met een van de twee methoden:

### Certificaten
Wanneer u het e-mailprofiel maakt, kiest u een certificaatprofiel dat u eerder hebt gemaakt in Intune. Dit wordt het identiteitscertificaat genoemd en wordt gebruikt voor verificatie aan de hand van een vertrouwd-certificaatprofiel (of een basiscertificaat) om te bepalen of het apparaat van de gebruiker verbinding mag maken. Het vertrouwde certificaat wordt geïmplementeerd op de computer die de e-mailverbinding verifieert, meestal de systeemeigen e-mailserver.

Zie [Secure resource access with certificate profiles](secure-resource-access-with-certificate-profiles.md) (Toegang tot beveiligde bronnen met certificaatprofielen) voor meer informatie over het gebruiken en maken van certificaatprofielen in Intune.

### Gebruikersnaam en wachtwoord
De gebruiker wordt geverifieerd op de systeemeigen mailserver door zijn gebruikersnaam en wachtwoord op te geven.

Het wachtwoord is niet opgenomen in het e-mailprofiel. De gebruiker moet dit opgeven wanneer hij de e-mailverbinding tot stand brengt.

### Een e-mailprofiel maken

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Beleid** &gt; **Beleid toevoegen**.

2.  Configureer een van de volgende beleidstypen:

    -   **E-mailprofiel voor Samsung KNOX Standard (4.0 of hoger)**

    -   **E-mailprofiel (iOS 7.1 en hoger)**

    -   **E-mailprofiel (Windows Phone 8 en hoger)**

    -   **E-mailprofiel (Windows 10 Desktop en Mobile en hoger)**

    U kunt alleen een aangepast e-mailprofielbeleid maken en implementeren. Aanbevolen instellingen zijn niet beschikbaar.

3.  Gebruik de volgende tabel als referentie voor de configuratie van e-mailprofielinstellingen:
    |Naam van de instelling|Meer informatie|
    |----------------|-----------------------------------------------------------------------------|
    |**Naam**|Unieke naam van het e-mailprofiel.|
    |**Beschrijving**|Een beschrijving op basis waarvan u het profiel kunt identificeren.|
    |**Host**|De hostnaam van de bedrijfsserver die als host fungeert voor uw systeemeigen e-mailservice.|
    |**Accountnaam**|De naam van het e-mailaccount die wordt weergegeven op de apparaten van de gebruikers.|
    |**Gebruikersnaam**|De manier waarop de gebruikersnaam voor het e-mailaccount wordt verkregen. Selecteer **Gebruikersnaam** voor een on-premises Exchange-server of selecteer **User Principal Name** voor Office 365.|
    |**E-mailadres**|Hoe het e-mailadres voor de gebruiker op elk apparaat wordt gegenereerd. Selecteer **Primaire SMTP-adres** om het primaire SMTP-adres te gebruiken voor aanmelding bij Exchange of gebruik **User Principal Name** om de volledige User Principal Name te gebruiken als het e-mailadres.|
    |**Verificatiemethode** (Samsung KNOX en iOS)|Selecteer **Gebruikersnaam en wachtwoord** of **Certificaten** als verificatiemethode voor het e-mailprofiel.|
    |**Selecteer een clientcertificaat voor clientverificatie (identiteitscertificaat)** (Samsung KNOX en iOS)|Selecteer het SCEP-clientcertificaat dat u eerder hebt gemaakt en dat wordt gebruikt voor verificatie van de Exchange-verbinding. Zie [Custom configurations for VPN profiles](secure-resource-access-with-certificate-profiles.md) (Toegang tot beveiligde bronnen met certificaatprofielen) voor meer informatie over het gebruik van certificaatprofielen in Intune.<br /><br />Deze optie wordt alleen weergegeven als **Certificaten** is geselecteerd als verificatiemethode.|
    |**S/MIME gebruiken** (Samsung KNOX en iOS)|Verzend uitgaande e-mail met S/MIME-versleuteling.|
    |**Handtekeningcertificaat** (Samsung KNOX en iOS)|Selecteer het handtekeningcertificaat dat wordt gebruikt om uitgaande e-mail te ondertekenen.<br /><br />Deze optie wordt alleen weergegeven als u het selectievakje bij **S/MIME gebruiken** hebt ingeschakeld.|
    |**Aantal dagen e-mail voor synchronisatie**|De periode waarvoor u e-mail wilt synchroniseren, of selecteer **Onbeperkt** om alle beschikbare e-mail te synchroniseren.|
    |**Synchronisatieschema** (Samsung KNOX, Windows Phone 8 en hoger, Windows 10)|Selecteer het schema op basis waarvan apparaten gegevens synchroniseren met de Exchange-server. Selecteer **Wanneer berichten binnenkomen** als u gegevens meteen wilt synchroniseren wanneer ze worden ontvangen of selecteer **Handmatig** als u wilt dat de gebruiker van het apparaat de synchronisatie zelf uitvoert.|
    |**SSL gebruiken**|Gebruik Secure Sockets Layer-communicatie (SSL) wanneer u e-mailberichten verzendt, e-mailberichten ontvangt en communiceert met de Exchange-server.<br /><br />Voor apparaten met Samsung KNOX 4.0 of hoger moet u het SSL-certificaat van uw Exchange-server exporteren en als Android Trusted Certificate Profile implementeren in Intune. Intune biedt geen ondersteuning voor toegang tot dit certificaat als het op een andere manier is geïnstalleerd op de Exchange-server.|
    |**Inhoudtype voor synchronisatie**|Selecteer de inhoudstypen die u wilt synchroniseren met apparaten.|
    |**Toestaan dat e-mails worden verzonden vanuit toepassingen van derden** (alleen iOS)|Sta de gebruiker toe dit profiel te selecteren als het standaardaccount voor het verzenden van e-mail en sta toepassingen van derden toe e-mail te openen in de systeemeigen e-mail-app (bijvoorbeeld om bestanden aan e-mail toe te voegen).|

    > [!IMPORTANT]
    > Als u een e-mailprofiel hebt geïmplementeerd en vervolgens de waarde van **Host** of **E-mailadres** wilt wijzigen, moet u het bestaande e-mailprofiel verwijderen en een nieuw e-mailprofiel met de vereiste waarden maken.

4.  Wanneer u klaar bent, klikt u op **Beleid opslaan**.

Het nieuwe beleid wordt weergegeven in het knooppunt **Configuratiebeleid** van de werkruimte **Beleid** .

## Het beleid implementeren

1.  Selecteer het beleid dat u wilt implementeren in de werkruimte **Beleid** en klik vervolgens op **Implementatie beheren**.

2.  In het dialoogvenster **Implementatie beheren** :

    -   **Het beleid implementeren**: selecteer een of meer groepen waarvoor u het beleid wilt implementeren en klik vervolgens op **Toevoegen** &gt; **OK**.

    -   **Het dialoogvenster sluiten zonder het beleid te implementeren**: klik op **Annuleren**.

Een statusoverzicht en waarschuwingen op de pagina **Overzicht** van de werkruimte **Beleid** identificeren beleidsproblemen die uw aandacht nodig hebben. Bovendien wordt er een statusoverzicht weergegeven in de werkruimte Dashboard.

> [!NOTE]
> Als u een e-mailprofiel van een apparaat wilt verwijderen, bewerkt u de implementatie en verwijdert u groepen waarvan het apparaat lid is.



<!--HONumber=Jul16_HO4-->


