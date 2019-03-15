---
title: 'Zelfstudie: het programma voor apparaatregistratie gebruiken om iOS-apparaten in Intune te registreren'
titleSuffix: Microsoft Intune
description: In deze zelfstudie gaat u DEP van Apple instellen om iOS-apparaten in Intune te registreren.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/30/2019
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up the Device Enrollment Program so that users can automatically enroll in Intune.
ms.collection: M365-identity-device-management
ms.openlocfilehash: 88fe825b75e7717740e5a5ca4af4c52e9bb21768
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57400395"
---
# <a name="tutorial-use-the-device-enrollment-program-to-enroll-ios-devices-in-intune"></a>Zelfstudie: iOS-apparaten in Intune registreren met het programma voor apparaatregistratie
Met DEP (het programma voor apparaatregistratie van Apple) kunt u eenvoudiger apparaten registreren. Met Microsoft Intune en DEP worden apparaten automatisch geregistreerd wanneer gebruikers het apparaat voor de eerste keer inschakelen. U kunt apparaten daarom naar vele gebruikers verzenden zonder elk apparaat afzonderlijk te hoeven instellen. 

In deze zelfstudie leert u het volgende:
> [!div class="checklist"]
> * Een Apple DEP-token ophalen
> * Een Autopilot-apparaatgroep maken
> * Een Autopilot-implementatieprofiel maken
> * Het Autopilot-implementatieprofiel toewijzen aan de apparaatgroep
> * Windows-apparaten naar gebruikers distribueren

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](free-trial-sign-up.md).

## <a name="prerequisites"></a>Vereisten
- Apparaten die zijn gekocht in het [Device Enrollment Program van Apple](http://deploy.apple.com)
- De [instantie voor het beheer van mobiele apparaten](mdm-authority-set.md) instellen
- Een [Apple MDM-pushcertificaat](apple-mdm-push-certificate-get.md) ophalen

## <a name="get-an-apple-dep-token"></a>Een Apple DEP-token ophalen
Voordat u iOS-apparaten met DEP gaat registreren, hebt u het DEP-tokenbestand (.pem) van Apple nodig. Intune kan met deze token informatie synchroniseren over DEP-apparaten die in eigendom zijn van uw bedrijf. Ook kan Intune hiermee inschrijvingsprofielen naar Apple uploaden en apparaten toewijzen aan die profielen.

U gebruikt de Apple DEP-portal om een DEP-token te maken. U gebruikt de DEP-portal ook om apparaten aan Intune toe te wijzen voor beheer.

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens inschrijvingsprogramma** > **Toevoegen**.

2. Geef Microsoft toestemming om gebruikers- en apparaatgegevens naar Apple te verzenden door **Ik ga akkoord** te selecteren.

   ![Schermopname van het deelvenster Token voor het inschrijvingsprogramma in de werkruimte Apple-certificaten voor het downloaden van de openbare sleutel.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Kies **Uw openbare-sleutelcertificaat downloaden** en sla het bestand met de versleutelingssleutel (.pem) lokaal op. Het .pem-bestand wordt gebruikt om een vertrouwensrelatiecertificaat bij de portal Apple Device Enrollment Program aan te vragen.

4. Kies **Een token voor Apple Device Enrollment Program maken** om de Deployment Program-portal van Apple te openen en meld u aan met uw Apple-id. Deze Apple-id kunt u gebruiken om uw DEP-token te verlengen.

5.  Kies **Aan de slag** bij **Device Enrollment Program** in de [Deployment Programs-portal](https://deploy.apple.com) van Apple.

4. Kies **MDM-server toevoegen** op de pagina **Servers beheren**.

5. Voer voor de **MDM-servernaam** *TestMDMServer* in en kies vervolgens **Volgende**. De servernaam is voor eigen referentie en dient om de MDM-server te identificeren. Het is niet de naam of URL van de Microsoft Intune-server.

6. Het dialoogvenster **Voeg &lt;servernaam&gt;** wordt geopend, met de instructie dat u uw **openbare sleutel moet uploaden**. Kies **Bestand selecteren...** om het .pem-bestand te uploaden en kies **Volgende**.

6. Ga naar **Implementatieprogramma** > **Device Enrollment Program** > **Apparaten beheren**.
7. Kies onder **Kies apparaten op** de optie **Serienummer**. <!--ask Tiffany about this-->

8. Voor **Kies actie** kiest u **Toewijzen aan server**, kiest u de &lt;Servernaam&gt; die is opgegeven voor Microsoft Intune en kiest u vervolgens **OK**. De opgegeven apparaten worden voor beheer toegewezen aan de Intune-server en er verschijnt een melding dat de **toewijzing is voltooid**.

   Ga in de Apple-portal **Deployment Programs** &gt; **Device Enrollment Program** &gt; **Toewijzingsgeschiedenis weergeven** om een lijst van apparaten en hun toewijzing aan de MDM-server te bekijken.

9. Geef in Intune in Azure Portal de Apple ID op die voor het maken van deze token is gebruikt, voor toekomstige referentie.

    ![Schermopname van het invoeren van de Apple ID die is gebruikt voor het maken van het token voor het inschrijvingsprogramma en het uploaden van het token.](./media/device-enrollment-program-enroll-ios/image03.png)

10. Ga in het venster **Apple-token** naar het certificaatbestand (.pem), kies **Openen** en vervolgens **Maken**. 

## <a name="create-an-apple-enrollment-profile"></a>Een Apple-inschrijvingsprofiel maken
Na installatie van de token kunt u een inschrijvingsprofiel voor DEP-apparaten maken. Met een inschrijvingsprofiel voor apparaten worden de instellingen gedefinieerd die worden toegepast op een groep apparaten tijdens de inschrijving.

1. Kies in Intune in Azure Portal **Apparaatinschrijving** > **Apple-inschrijving** > **Token voor het inschrijvingsprogramma**.

2. Selecteer de token die u zojuist hebt geïnstalleerd en kies **Profielen** > **Profiel maken**.

3. Voer onder **Profiel maken** *TestDEPProfile* als **naam** in en geef *DEP testen voor iOS-apparaten* op als **beschrijving**. Gebruikers zien deze gegevens niet.

4. Kies **Registreren met gebruikersaffiniteit** als **Gebruikersaffiniteit**. Deze optie is voor apparaten die eigendom zijn van gebruikers die de bedrijfsportal willen gebruiken voor services als het installeren van apps.

5. Kies **Nee** onder **Verifiëren met de bedrijfsportal in plaats van met de Apple-configuratieassistent**.

6. Kies **Instellingen apparaatbeheer** en kies **Nee** onder **Onder toezicht**. Apparaten die onder toezicht staan bieden u meer beheeropties, maar in deze zelfstudie gaan we deze niet gebruiken.

7. Kies **OK**.

8. Kies **Aanpassing Configuratieassistent** en voer *Afdeling Zelfstudie* als **Afdelingsnaam** in. Dit is de tekenreeks die gebruikers zien wanneer ze tijdens het activeren van het apparaat op **Over configuratie** tikken.

9. Voer onder **Telefoonnummer afdeling** een telefoonnummer in. Dit is het nummer dat wordt weergegeven wanneer gebruikers tijdens de activering op de knop **Hulp nodig?** drukken.

10. U kunt tijdens de activering van apparaten diverse schermen **weergeven** of **verbergen**. Voor deze zelfstudie stellen we **Wachtwoordcode** in op **Weergeven** en alle andere opties op **Verbergen**.

11. Kies **OK** > **Maken**.

## <a name="sync-managed-devices"></a>Beheerde apparaten synchroniseren

U ziet nu welke apparaten aan deze token zijn toegewezen.

1. Kies in Intune in Azure Portal **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor het inschrijvingsprogramma** > kies een token uit de lijst > **Apparaten** > **Synchroniseren**.

## <a name="assign-an-enrollment-profile-to-ios-devices"></a>Een inschrijvingsprofiel toewijzen aan iOS-apparaten

U moet een profiel voor een inschrijvingsprogramma aan apparaten toewijzen voordat deze kunnen worden ingeschreven.

1. Kies in Intune in Azure Portal **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor het inschrijvingsprogramma** > kies een token uit de lijst.
2. Kies **Apparaten** > kies apparaten uit de lijst > **Profiel toewijzen**.
3. Kies onder **Profiel toewijzen** een profiel voor de apparaten > **Toewijzen**.

## <a name="distribute-devices-to-users"></a>Apparaten onder gebruikers distribueren

U hebt beheer en synchronisatie tussen Apple en Intune ingesteld en een profiel toegewezen om uw DEP-apparaten te kunnen inschrijven. De apparaten kunnen nu worden uitgedeeld aan de gebruikers. Voor apparaten met gebruikersaffiniteit moet aan elke gebruiker een Intune-licentie worden toegewezen.

## <a name="clean-up-resources"></a>Resources opschonen

Als u de Autopilot-apparaten niet meer wilt gebruiken, kunt u deze verwijderen.

- Als de apparaten zijn ingeschreven bij Intune, moet u ze eerst [verwijderen uit de Azure Active Directory-portal](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

<!--ask tiffany how to do this-->

## <a name="next-steps"></a>Volgende stappen

Er bestaat aanvullende informatie over andere opties die voor het registreren van iOS-apparaten beschikbaar zijn.

> [!div class="nextstepaction"]
> [Diepgaand artikel over iOS DEP-registratie](device-enrollment-program-enroll-ios.md)
