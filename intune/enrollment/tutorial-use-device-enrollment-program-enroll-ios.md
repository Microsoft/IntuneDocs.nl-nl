---
title: 'Zelfstudie: Apple Business Manager of het Device Enrollment Program gebruiken om iOS-/iPadOS-apparaten in Intune in te schrijven'
titleSuffix: Microsoft Intune
description: In deze zelfstudie gaat u de inschrijvingsfuncties voor zakelijke Apple-apparaten van ABM instellen om iOS-/iPadOS-apparaten bij Intune in te schrijven.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up the Apple's corporate device enrollment features so that corporate devices can automatically enroll in Intune.
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9aab0233c05416fc50413a7889435cb221179730
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415146"
---
# <a name="tutorial-use-apples-corporate-device-enrollment-features-in-apple-business-manager-abm-to-enroll-iosipados-devices-in-intune"></a>Zelfstudie: De inschrijvingsfuncties voor zakelijke Apple-apparaten in Apple Business Manager (ABM) gebruiken om iOS-/iPadOS-apparaten bij Intune in te schrijven
Met behulp van de functies voor apparaatinschrijving in Apple Business Manager kunt u apparaten eenvoudiger inschrijven. Intune biedt ook ondersteuning voor de oudere DEP-portal (Device Enrollment Program) van Apple, maar we raden u aan opnieuw te beginnen met Apple Business Manager. Met Microsoft Intune en Apple Corporate Device Enrollment worden apparaten automatisch veilig ingeschreven wanneer gebruikers het apparaat voor de eerste keer inschakelen. U kunt apparaten daarom naar vele gebruikers verzenden zonder elk apparaat afzonderlijk te hoeven instellen. 

In deze zelfstudie leert u het volgende:
> [!div class="checklist"]
> * Een Apple-token voor apparaatinschrijving ophalen
> * Beheerde apparaten synchroniseren met Intune
> * Een inschrijvingsprofiel maken
> * Het inschrijvingsprofiel toewijzen aan apparaten

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Vereisten
- Apparaten die zijn gekocht in [Apple Business Manager](http://deploy.apple.com) of het [Device Enrollment Program van Apple](https://business.apple.com)
- De [instantie voor het beheer van mobiele apparaten](../fundamentals/mdm-authority-set.md) instellen
- Een [Apple MDM-pushcertificaat](apple-mdm-push-certificate-get.md) ophalen

## <a name="get-an-apple-device-enrollment-token"></a>Een Apple-token voor apparaatinschrijving ophalen
Voordat u iOS-/iPadOS-apparaten inschrijft met behulp van de zakelijke inschrijvingsfuncties van Apple, hebt u een bestand met een apparaatinschrijvingstoken van Apple (.pem-bestand) nodig. Intune kan met deze token informatie synchroniseren over Apple-apparaten die het eigendom zijn van uw bedrijf. Ook kan Intune hiermee inschrijvingsprofielen naar Apple uploaden en apparaten toewijzen aan die profielen.

U maakt een apparaatinschrijvingstoken met behulp van ABM of de DEP-portal. U gebruikt de portals ook om apparaten aan Intune toe te wijzen voor beheer.

1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Tokens voor het inschrijvingsprogramma** > **Toevoegen**.

2. Geef Microsoft toestemming om gebruikers- en apparaatgegevens naar Apple te verzenden door **Ik ga akkoord** te selecteren.

   ![Schermopname van het deelvenster Token voor het inschrijvingsprogramma in de werkruimte Apple-certificaten voor het downloaden van de openbare sleutel.](./media/tutorial-use-device-enrollment-program-enroll-ios/add-enrollment-program-token-pane.png)

3. Kies **Uw openbare-sleutelcertificaat downloaden** en sla het bestand met de versleutelingssleutel (.pem) lokaal op. Het .pem-bestand wordt gebruikt om een vertrouwensrelatiecertificaat aan te vragen bij de ABM- of DEP-portal.

4. Kies **Een token voor Apple Device Enrollment Program maken** om de Deployment Program-portal van Apple te openen en meld u aan met uw Apple-id. Deze Apple-id kunt u gebruiken om uw DEP-token te verlengen.

5. Kies **Aan de slag** bij **Device Enrollment Program** in de [Deployment Programs-portal](https://deploy.apple.com) van Apple. Uw proces verloopt mogelijk iets anders dan de volgende stappen in [Apple Business Manager](https://business.apple.com).

4. Kies **MDM-server toevoegen** op de pagina **Servers beheren**.

5. Voer voor de **MDM-servernaam***TestMDMServer* in en kies vervolgens **Volgende**. De servernaam is voor eigen referentie en dient om de MDM-server te identificeren. Het is niet de naam of URL van de Microsoft Intune-server.

6. Het dialoogvenster **Voeg &lt;servernaam&gt;** wordt geopend, met de instructie dat u uw **openbare sleutel moet uploaden**. Selecteer **Bestand kiezen...** om het .pem-bestand te uploaden en kies **Volgende**.

6. Ga naar **Implementatieprogramma** > **Device Enrollment Program** > **Apparaten beheren**.
7. Kies onder **Kies apparaten op** de optie **Serienummer**. <!--ask Tiffany about this-->

8. Voor **Kies actie** kiest u **Toewijzen aan server**, kiest u de &lt;Servernaam&gt; die is opgegeven voor Microsoft Intune en kiest u vervolgens **OK**. De opgegeven apparaten worden voor beheer toegewezen aan de Intune-server en er verschijnt een melding dat de **toewijzing is voltooid**.

   Ga in de Apple-portal naar **Deployment Programs** &gt; **Device Enrollment Program** &gt; **Toewijzingsgeschiedenis weergeven** om een lijst van apparaten en hun toewijzing aan de MDM-server te bekijken.

9. Geef in Intune in Azure Portal de Apple ID op die voor het maken van deze token is gebruikt, voor toekomstige referentie.

    ![Schermopname van het invoeren van de Apple ID die is gebruikt voor het maken van het token voor het inschrijvingsprogramma en het uploaden van het token.](./media/tutorial-use-device-enrollment-program-enroll-ios/image03.png)

10. Ga in het venster **Apple-token** naar het certificaatbestand (.pem), kies **Openen** en vervolgens **Maken**. 

11. Als u bereiktags wilt toepassen om te beperken welke beheerders toegang tot dit token hebben, selecteert u bereiken.

## <a name="create-an-apple-enrollment-profile"></a>Een Apple-inschrijvingsprofiel maken
Na installatie van de token kunt u een inschrijvingsprofiel voor iOS-/iPadOS-apparaten in het eigendom van uw bedrijf maken. Met een inschrijvingsprofiel voor apparaten worden de instellingen gedefinieerd die worden toegepast op een groep apparaten tijdens de inschrijving.

1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Tokens voor het inschrijvingsprogramma**.

2. Selecteer de token die u zojuist hebt geïnstalleerd en kies **Profielen** > **Profiel maken**.

3. Voer onder **Profiel maken***TestDEPProfile* als **naam** in en geef *DEP testen voor iOS-/iPadOS-apparaten* op als **beschrijving**. Gebruikers zien deze gegevens niet.

4. Kies **iOS** onder **Platform**.

5. Bepaal of uw apparaten met of zonder **Gebruikersaffiniteit** moeten worden ingeschreven. Gebruikersaffiniteit is ontworpen voor apparaten die door specifieke gebruikers worden gebruikt. Kies **Inschrijven met gebruikersaffiniteit** als uw gebruikers de bedrijfsportal willen gebruiken voor services zoals het installeren van apps. Als uw gebruikers de bedrijfsportal niet nodig hebben of als u het apparaat voor veel gebruikers wilt inrichten, kiest u **Inschrijven zonder Gebruikersaffiniteit**.

6. Als u ervoor kiest om een apparaat met Gebruikersaffiniteit in te schrijven, moet u bepalen of u de verificatie wilt uitvoeren via de bedrijfsportal of via Apple-configuratieassistent. Als u meervoudige verificatie wilt gebruiken, gebruikers wilt toestaan om wachtwoorden te wijzigen wanneer zij zich voor het eerst aanmelden of als u gebruikers wilt vragen hun verlopen wachtwoorden opnieuw in te stellen tijdens de inschrijving, kiest u **Ja** onder **Verificatie met bedrijfsportal in plaats van Apple-configuratieassistent**. Kies **Nee** als er geen problemen mee hebt om de door Apple aangeboden HTTP-basisverificatie via de Apple-configuratieassistent te gebruiken. Als u **Ja** kiest en u wilt dat de bedrijfsportal-app automatisch wordt bijgewerkt op de apparaten van eindgebruikers, moet u de bedrijfsportal apart als een vereiste app voor deze gebruikers implementeren op basis van het Apple-volumeaankoopprogramma.

7. Als u hebt gekozen voor inschrijving met Gebruikersaffiniteit en Verificatie met bedrijfsportal, bepaalt u nu of u de bedrijfsportal wilt installeren in combinatie met het Apple Volume Purchase Program (VPP). Als u de bedrijfsportal installeert met een VPP-token, hoeven gebruikers geen Apple-id en wachtwoord in te voeren om de bedrijfsportal tijdens de inschrijving in de App Store te downloaden. Kies **Token gebruiken:** onder **Bedrijfsportal installeren met VPP** om een VPP-token te selecteren waarvoor gratis licenties van de bedrijfsportal beschikbaar zijn. Als u VPP niet wilt gebruiken om de bedrijfsportal te implementeren, kiest u **VPP niet gebruiken** onder **Bedrijfsportal installeren met VPP**. 

8. Als u de inschrijving uitvoert met Gebruikersaffiniteit, Verificatie met bedrijfsportal en Bedrijfsportal installeren met VPP, moet u bepalen of u de bedrijfsportal wilt uitvoeren in de Eén-app-modus totdat de verificatie wordt uitgevoerd. Met behulp van deze instelling kunt ervoor zorgen dat gebruikers geen toegang hebben tot andere apps, totdat ze de bedrijfsinschrijving hebben voltooid. Als u de gebruiker tot deze stroom wilt beperken totdat de inschrijving is voltooid, kiest u **Ja** onder **Bedrijfsportal tot verificatie uitvoeren in één-app-modus**. 

9. Kies **Instellingen apparaatbeheer** en kies **Ja** onder **Onder toezicht**. U krijgt de meeste beheeropties voor uw zakelijke iOS-/iPadOS-apparaten door apparaten onder toezicht te stellen.

10. Kies **Ja** onder **Vergrendelde inschrijving** om ervoor te zorgen dat gebruikers het beheer van de bedrijfsapparaten niet kunnen verwijderen. 

11. Kies een optie onder **Synchroniseren met computers** om te bepalen of de iOS-/iPadOS-apparaten met computers kunnen worden gesynchroniseerd.

12. Standaard krijgen apparaten bij Apple de naam van het apparaattype (bijv. iPad). Als u een andere naamsjabloon wilt opgeven, kiest u **Ja** onder **Sjabloon voor apparaatnamen toepassen**. Voer de naam in die u op de apparaten wilt toepassen, waarbij u de tekenreeksen *{{SERIAL}}* en *{{DEVICETYPE}}* vervangt door het serienummer en het apparaattype van elk apparaat. Anders kiest u **Nee** onder **Sjabloon voor apparaatnamen toepassen**.

13. Kies **OK**.

14. Kies **Aanpassing Configuratieassistent** en voer *Afdeling Zelfstudie* als **Afdelingsnaam** in. Dit is de tekenreeks die gebruikers zien wanneer ze tijdens het activeren van het apparaat op **Over configuratie** tikken.

15. Voer onder **Telefoonnummer afdeling** een telefoonnummer in. Dit is het nummer dat wordt weergegeven wanneer gebruikers tijdens de activering op de knop **Hulp nodig?** drukken.

16. U kunt tijdens de activering van apparaten diverse schermen **weergeven** of **verbergen**. Voor de beste inschrijvingservaring stelt u alle schermen in op **Verbergen**.

17. Kies **OK** > **Maken**.

## <a name="sync-managed-devices-to-intune"></a>Beheerde apparaten synchroniseren met Intune

Zodra u een inschrijvingsprogrammatoken hebt ingesteld via de ABM-, ASM- of DEP-portal en daar apparaten aan de MDM-server hebt toegewezen, wacht u totdat deze apparaten met de Intune-service zijn gesynchroniseerd of voert u handmatig een synchronisatie uit. Als u geen handmatige synchronisatie uitvoert, kan het tot 24 uur duren voordat apparaten in Azure Portal worden weergegeven.

1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Tokens voor het inschrijvingsprogramma** > kies een token in de lijst > **Apparaten** > **Synchroniseren**.

## <a name="assign-an-enrollment-profile-to-iosipados-devices"></a>Een inschrijvingsprofiel toewijzen aan iOS-/iPadOS-apparaten

U moet een profiel voor een inschrijvingsprogramma aan apparaten toewijzen voordat deze kunnen worden ingeschreven. Deze apparaten worden via Apple met Intune gesynchroniseerd en moeten aan de juiste MDM-servertoken in de ABM-, ASM- of DEP-portal worden toegewezen.

1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **iOS** > **iOS-inschrijving** > **Tokens voor het inschrijvingsprogramma** > kies een token in de lijst.
2. Kies **Apparaten** > kies apparaten uit de lijst > **Profiel toewijzen**.
3. Kies onder **Profiel toewijzen** een profiel voor de apparaten > **Toewijzen**.

## <a name="distribute-devices-to-users"></a>Apparaten onder gebruikers distribueren

U hebt beheer en synchronisatie tussen Apple en Intune ingesteld en een profiel toegewezen om uw DEP-apparaten te kunnen inschrijven. De apparaten kunnen nu worden uitgedeeld aan de gebruikers. Voor apparaten met gebruikersaffiniteit moet aan elke gebruiker een Intune-licentie worden toegewezen.

## <a name="next-steps"></a>Volgende stappen

Er bestaat aanvullende informatie over andere opties die voor het registreren van iOS-/iPadOS-apparaten beschikbaar zijn.

> [!div class="nextstepaction"]
> [Diepgaand artikel over iOS/iPadOS DEP-registratie](device-enrollment-program-enroll-ios.md)

<!--commenting out because inaccurate>
## Clean up resources
<!--If you don't want to use iOS/iPadOS corporate enrolled devices anymore, you can delete them.>
<!--- If the devices are enrolled in Intune, you must first [delete them from the Azure Active Directory portal](../remote-actions/devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).>
