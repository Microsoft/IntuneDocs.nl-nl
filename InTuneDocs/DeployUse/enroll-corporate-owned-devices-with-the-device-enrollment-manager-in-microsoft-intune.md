---
# required metadata

title: Apparaten in bedrijfseigendom inschrijven met de Apparaatinschrijvingsbeheerder in Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Apparaten in bedrijfseigendom inschrijven met de apparaatinschrijvingsbeheerder in Microsoft Intune
Organisaties kunnen Intune gebruiken voor het beheren van een groot aantal mobiele apparaten met één gebruikersaccount. De account *apparaatinschrijvingsbeheerder* is een speciale Intune-account met machtigingen om meer dan vijf apparaten in te schrijven. U kunt een gebruikersaccount voor een winkelmanager of supervisor, bijvoorbeeld een apparaatinschrijvingsbeheerder, toewijzen om het volgende te kunnen uitvoeren:

-   Apparaten in Intune inschrijven

-   Aanmelden bij de bedrijfsportal om bedrijfsapps op te halen

-   Software installeren en verwijderen

-   Toegang tot bedrijfsgegevens configureren

Gebruik het apparaatbeheeraccount alleen voor apparaten die geen e-mail ontvangen of waarbij u zich als een specifieke gebruiker aanmeldt. Apparaten die worden beheerd met een apparaatbeheeraccount, kunnen niet worden geconfigureerd met voorwaardelijke toegang omdat hiervoor ook scenario’s per gebruiker gelden. De winkelmanager kan het apparaat niet opnieuw instellen via de bedrijfsportal.

**Voorbeelden van scenario voor apparaatinschrijvingsbeheerder:**
Een restaurant wil tablets inzetten op verkooppunten voor zijn bedienend personeel en bestellingen controleren voor het keukenpersoneel. De werknemers hebben geen toegang tot bedrijfsgegevens nodig en hoeven zich niet aan te melden als gebruiker. De Intune-beheerder maakt een apparaatinschrijvingsbeheerder-account en schrijft de bedrijfsapparaten in met behulp van dat account. De beheerder kan de referenties voor de apparaatinschrijvingsbeheerder ook aan een restaurantmanager geven, zodat hij of zij de apparaten kan inschrijven en beheren.

De beheerder of de manager kan rolspecifieke apps op de restaurantapparaten implementeren. Een beheerder het apparaat ook selecteren in de Intune-console en het apparaat onttrekken aan het beheer van mobiele apparaten met behulp van de beheerconsole.

> [!NOTE]
> Gebruikersaccounts voor de apparaatinschrijvingsbeheerder met meer dan 20 ingeschreven apparaten hebben wellicht problemen met het gebruik van de bedrijfsportal-app. Om bedrijfs-apps te implementeren op apparaten die worden beheerd met de apparaatinschrijvingsbeheerder, moet u de bedrijfsportal-app als een **Vereiste installatie** implementeren naar het gebruikersaccount voor de apparaatinschrijvingsbeheerder.

## Apparaatinschrijvingsbeheerder-accounts maken
Apparaatinschrijvingsbeheerder-accounts zijn gebruikersaccounts met een machtiging voor het inschrijven van grote aantallen apparaten in bedrijfseigendom. Alleen gebruikers in de Intune-console kunnen apparaatinschrijvingsbeheerders zijn.

#### Een apparaatinschrijvingsbeheerder toevoegen aan Intune

1.  Ga naar de [Microsoft Intune-accountportal](http://go.microsoft.com/fwlink/?LinkId=698854) en meld u aan bij uw beheerdersaccount.

2.  Klik op **Gebruiker toevoegen**..

3.  Controleer of het gebruikersaccount dat een apparaatinschrijvingsbeheerder moet worden, wordt vermeld. Als dat niet het geval is, voegt u de gebruiker toe door op **Nieuw** te klikken en de procedure voor het toevoegen van de gebruiker te voltooien. Er is een abonnementslicentie vereist voor elke gebruiker die toegang de service heeft en de *apparaatinschrijvingsbeheerder* mag geen Intune-beheerder zijn. Bepaal of u meer licenties moet toevoegen voordat u deze functie gebruikt.

4.  Meld u aan bij de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) met uw beheerdersaanmelding.

5.  Klik in het navigatiedeelvenster op **Admin**, ga naar **Administratorbeheer** en selecteer **Apparaatinschrijvingsbeheerder**. De pagina Apparaatinschrijvingsbeheerders wordt geopend.

6.  Klik op **Toevoegen...**. Het dialoogvenster **Apparaatinschrijvingsbeheerder toevoegen** wordt geopend.

7.  Voer de **Gebruikers-id** van de Intune-account in en klik vervolgens op **OK**. De apparaatinschrijvingsbeheerder-gebruiker mag geen Intune-beheerder zijn.

8.  De apparaatinschrijvingsbeheerder kan nu mobiele apparaten inschrijven met behulp van dezelfde procedure die een eindgebruiker gebruikt voor een BYOD-scenario in de bedrijfsportal.

## Een apparaatinschrijvingsbeheerder uit Intune verwijderen

1.  Meld u aan bij de [Microsoft Intune-accountportal](http://manage.microsoft.com) met uw beheerdersaanmelding.

2.  Klik in het navigatiedeelvenster op **Admin** , ga naar **Administratorbeheer** en selecteer **Apparaatinschrijvingsbeheerder**. De pagina Apparaatinschrijvingsbeheerders wordt geopend.

3.  Selecteer de apparaatinschrijvingsbeheerder- **Gebruiker** die u wilt verwijderen, en klik vervolgens op **Verwijderen**. Deze gebruiker wordt niet uit Intune verwijderd en de apparaten die deze gebruiker beheert, blijven ingeschreven in Intune. Het verwijderen van een apparaatinschrijvingsbeheerder verhindert dat de betreffende gebruiker meer apparaten in Intune inschrijft.

4.  Klik op **Ja** om te bevestigen dat u de apparaatinschrijvingsbeheerder wilt verwijderen.

Het verwijderen van een apparaatinschrijvingsbeheerder heeft geen invloed op ingeschreven apparaten. Wanneer een apparaatinschrijvingsbeheerder wordt verwijderd:

-   heeft dat geen invloed op ingeschreven apparaten;

-   blijven ingeschreven apparaten volledig beheerd;

-   blijven de accountreferenties van de verwijderde apparaatinschrijvingsbeheerder geldig voor aanmelding bij de bedrijfsportal om toegang tot apps te krijgen;

-   kunnen apparaten nog steeds niet worden gewist of buiten gebruik worden gesteld met de accountreferenties van de verwijderde apparaatinschrijvingsbeheerder;

-   blijft de account van de verwijderde apparaatinschrijvingsbeheerder gerelateerd aan ingeschreven apparaten, maar kunnen er geen extra apparaten worden ingeschreven.


<!--HONumber=May16_HO1-->


