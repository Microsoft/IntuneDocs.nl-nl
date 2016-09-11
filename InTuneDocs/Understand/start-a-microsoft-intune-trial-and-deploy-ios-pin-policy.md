---
title: Een proefversie van Intune in gebruik nemen en een iOS-pincodebeleid implementeren | Microsoft Intune
description: iOS-pincodebeleid in Intune implementeren
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 06cb9a73-0f17-44b3-b334-86c98020316e
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 60ee39a7eeeb9068a7350ec87f60e7148ccb7826
ms.openlocfilehash: a4c38659c87c651678ee30134d50fb74f35fc388


---

# Een proefversie van Microsoft Intune in gebruik nemen en een iOS-pincodebeleid implementeren
Deze stapsgewijze instructies helpen u bij het instellen van een Intune-proefabonnement en de configuratie van een pincodebeleid voor iOS-apparaten. Zie [Algemene Microsoft Intune-evaluatietaken](common-microsoft-intune-evaluation-tasks.md) voor een lijst met algemene Intune-evaluatietaken die u kunt uitvoeren.



## Vereisten voor deze taak controleren

-   Een Windows-pc met Internet Explorer voor het uitvoeren van beheertaken

-   Een apparaat met iOS 7.1 of hoger om de validatie van het gebruikersbeleid te testen

-   Een telefoon om uzelf te verifiëren tijdens uw aanmelding voor het proefabonnement

## Een gratis proefaccount bij Intune maken
> [!NOTE]
> Als u al een Intune-abonnement hebt, kunt u deze sectie overslaan en naar de volgende sectie gaan.

1.  Klik op een Windows-pc met de rechtermuisknop op **Internet Explorer** (IE) en selecteer **InPrivate-browsing**.

    ![InPrivate-navigatie starten](../media/30-day-trial-walkthrus/30day-start-trial-1-InPrivate.png)

2.  Ga naar de [portal om u aan te melden bij Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1), voer de vereiste gegevens in en klik op **Volgende**.

    ![Registreren voor een account](../media/30-day-trial-walkthrus/30day-start-trial-2-abt-you.png)

3.  Voer een gebruikers-id en wachtwoord in voor uw beheerdersaccount en klik op **Volgende**. U gebruikt deze id wanneer u zich aanmeldt bij de Intune-portal om beheertaken uit te voeren.

    ![Een id maken](../media/30-day-trial-walkthrus/30day-start-trial-3-createID.png)

4.  Voer uw mobiele telefoonnummer in en klik op **Stuur me een SMS** om uw nummer te valideren.

    ![Uw gegevens valideren](../media/30-day-trial-walkthrus/30day-start-trial-4-textme.png)

5.  Sla de gegevens die op het scherm worden weergegeven, op en klik op **U bent klaar om aan de slag te gaan...**.

    ![Klaar om aan de slag te gaan](../media/30-day-trial-walkthrus/30day-start-trial-5-ReadyToGo.png)

## Een testgebruiker maken

1.  Klik op een Windows-pc op **Start** om naar de pagina voor gebruikersbeheer te gaan.

    ![Naar de pagina Gebruikersbeheer gaan](../media/30-day-trial-walkthrus/30day-crt-user-6-click-start.png)

2.  Klik op de knop **+** om een gebruiker toe te voegen.

    ![Een gebruiker toevoegen](../media/30-day-trial-walkthrus/30day-crt-user-7-click-plus.png)

3.  Ga als volgt te werk op de pagina **Nieuw gebruikersaccount maken**:

    1.  Geef de gegevens voor de testgebruiker op.

    2.  Selecteer de optie **Geef het wachtwoord op**.

    3.  Schakel het selectievakje **Vraag deze persoon zijn wachtwoord te wijzigen bij volgende aanmelding** uit.

    4.  Klik op **Maken**.

    ![Een nieuw gebruikersaccount maken](../media/30-day-trial-walkthrus/30day-crt-user-8-add-user-info.png)

4.  Klik op de bevestigingspagina voor het maken van een gebruiker op **Sluiten**.

    ![Bevestigingspagina voor het maken van een gebruiker](../media/30-day-trial-walkthrus/30day-crt-user-9-close-confirm.png)

5.  Klik op de knop **Vernieuwen** om de zojuist gemaakte testgebruiker weer te geven.

    ![Accountbevestiging](../media/30-day-trial-walkthrus/30day-crt-user-10-refresh-user.png)

## Een iOS-pincodebeleid voor de testgebruiker configureren

1.  Met een Windows-pc stelt u als volgt de MDM-instantie in op Intune:

    1.  Ga naar de [Intune-beheerconsole](http://manage.microsoft.com/), meld u aan met uw beheerdersaccount en klik op **Beheer van mobiele apparaten starten**. De pagina Instantie voor beheer van mobiele apparaten wordt geopend

        ![Aan de slag in de Intune-console](../media/30-day-trial-walkthrus/30day-cfg-pol-11-start-mg-mobl-dev.png)

    2.  Klik op de koppeling **Instantie voor beheer van mobiele apparaten instellen**.

        ![De instantie voor het beheer van mobiele apparaten instellen](../media/30-day-trial-walkthrus/30day-cfg-pol-12-link-set-mdm.png)

2.  Schakel iOS-apparaten in voor inschrijving. Met dit proces wordt een vertrouwd certificaat ingesteld tussen de Apple Push Notification Service (APNs) en uw Intune-abonnement.

    1.  Klik op **Het iOS- en Mac OS X-platform inschakelen**.

        ![iOS- en Mac OS X-inschrijving inschakelen](../media/30-day-trial-walkthrus/30day-cfg-pol-13-enbl-ios-plat.png)

    2.  Klik op **De APNs-certificaataanvraag downloaden**.

        ![Het APNs-certificaat downloaden](../media/30-day-trial-walkthrus/30day-cfg-pol-14-dwnld-cert-reqst.png)

    3.  Geef een bestandsnaam en locatie op voor uw CSR (Certificate Signing Request) en klik op **Opslaan**. Dit bestand bevat de openbare sleutel die overeenkomt met een persoonlijke sleutel die is opgeslagen in uw Intune-abonnement.

        ![Een aanvraag voor certificaatondertekening opgeven](../media/30-day-trial-walkthrus/30day-cfg-pol-15-cert-name-loc.png)

    4.  Klik op **Apple Push Certificates-portal** om een nieuw tabblad te openen.

        ![Naar de pagina APNs-certificaten gaan](../media/30-day-trial-walkthrus/30day-cfg-pol-16-cert-portl-link.png)

    5.  Voer uw Apple-id en -wachtwoord in en klik op **Aanmelden**. Dit kan de id zijn die op uw iOS-apparaat wordt gebruikt om apps op te halen uit de iOS App Store.

        ![Aanmelden bij de Apple Push Certificates-portal](../media/30-day-trial-walkthrus/30day-cfg-pol-17-id-passw-signin.png)

    6.  Klik op **Een certificaat maken**.

        ![Een APNs-certificaat maken](../media/30-day-trial-walkthrus/30day-cfg-pol-18-create-cert.png)

    7.  Lees de gebruiksvoorwaarden van Apple, schakel het selectievakje in en klik op **Accepteren**.

        ![De gebruiksvoorwaarden accepteren](../media/30-day-trial-walkthrus/30day-cfg-pol-19-TOU.png)

    8.  Klik op **Bladeren**.

        ![Bladeren naar de locatie waar u het certificaat hebt opgeslagen](../media/30-day-trial-walkthrus/30day-cfg-pol-20-browse.png)

    9. Selecteer het CSR-bestand dat u eerder hebt opgeslagen en klik op **Openen**.

        ![Het certificaat openen](../media/30-day-trial-walkthrus/30day-cfg-pol-21-CSRfile-open.png)

    10. Klik op de knop **Uploaden**.

        ![Het certificaat uploaden](../media/30-day-trial-walkthrus/30day-cfg-pol-22-upld-reqst.png)

    11. Wanneer u wordt gevraagd een JSON-bestand te downloaden, klikt u op **Opslaan als**.

        ![Het JSON-bestand opslaan](../media/30-day-trial-walkthrus/30day-cfg-pol-23-json-saveas.png)

    12. Geef een locatie voor uw JSON-bestand op en klik op **Opslaan**.

        ![Opgeven waar u het JSON-bestand wilt opslaan](../media/30-day-trial-walkthrus/30day-cfg-pol-24-json-save-loc.png)

        Als de pagina na enkele seconden niet automatisch wordt omgeleid, klikt u op **Annuleren**.

        ![Annuleren als de pagina niet wordt omgeleid](../media/30-day-trial-walkthrus/30day-cfg-pol-25-json-pg-cancel.png)

    13. Klik op **Downloaden** als u het zojuist gemaakte certificaatbestand wilt ophalen.

        ![Het certificaat downloaden](../media/30-day-trial-walkthrus/30day-cfg-pol-26-dwnld-retrv-cert.png)

    14. Wanneer u wordt gevraagd een PEM-bestand te downloaden, klikt u op **Opslaan als**.

        ![Het PEM-bestand downloaden](../media/30-day-trial-walkthrus/30day-cfg-pol-27-pem-saveas.png)

    15. Geef een locatie voor uw PEM-bestand op en klik op **Opslaan**.

        ![Het PEM-bestand opslaan](../media/30-day-trial-walkthrus/30day-cfg-pol-28-pem-save-loc.png)

    16. Ga terug naar het tabblad Intune-beheerconsole en klik op **Het APNs-certificaat uploaden**.

        ![Het APNs-certificaat uploaden](../media/30-day-trial-walkthrus/30day-cfg-pol-29-upld-cert.png)

    17. Voer uw Apple-id in en klik op **Bladeren**.

        ![Uw Apple-id invoeren](../media/30-day-trial-walkthrus/30day-cfg-pol-30-app-id-browse.png)

    18. Selecteer het PEM-bestand dat u zojuist hebt opgeslagen en klik op **Openen**.

        ![Het PEM-bestand openen](../media/30-day-trial-walkthrus/30day-cfg-pol-31-sel-pem-open.png)

    19. Klik op **Uploaden**.

        ![Het PEM-bestand uploaden](../media/30-day-trial-walkthrus/30day-cfg-pol-32-pem-upload.png)

        Uw APNs-certificaat is nu geconfigureerd.

        ![Configuratie van APNs-certificaat gereed](../media/30-day-trial-walkthrus/30day-cfg-pol-33-apns-confgd.png)

3.  Ga als volgt te werk om een testgebruikersgroep te maken waarmee u het beleid wilt testen:

    1.  Klik in het linkerdeelvenster op **Groepen**.

        ![Groepen openen](../media/30-day-trial-walkthrus/30day-cfg-pol-34-clk-groups.png)

    2.  Klik helemaal rechts op **Groep maken**.

        ![Een groep maken](../media/30-day-trial-walkthrus/30day-cfg-pol-35-crt-group.png)

    3.  Geef een groepsnaam op, selecteer **Alle gebruikers** als bovenliggende groep en klik op **Volgende**.

        ![Alle gebruikers selecteren als bovenliggende groep](../media/30-day-trial-walkthrus/30day-cfg-pol-36-name-group.png)

    4.  Selecteer in het veld **Groepslidmaatschap starten met:** de optie **Alle gebruikers in de bovenliggende groep** en klik op **Voltooien**.

        ![Groepslidmaatschap starten met de bovenliggende groep](../media/30-day-trial-walkthrus/30day-cfg-pol-37-all-users-group.png)

4.  Ga als volgt te werk om een iOS-pincodebeleid te maken en dit in te stellen voor de testgebruikersgroep:

    1.  Klik in het linkerdeelvenster op **Beleid**.

        ![De werkruimte Beleid openen](../media/30-day-trial-walkthrus/30day-cfg-pol-38-clk-policy.png)

    2.  Klik helemaal rechts op **Beleid toevoegen**.

        ![Beleid toevoegen](../media/30-day-trial-walkthrus/30day-cfg-pol-39-add-policy.png)

    3.  Vouw het knooppunt iOS uit, selecteer de rij **Algemene configuratie** en klik op **Beleid maken**.

        ![Een algemeen configuratiebeleid voor iOS maken](../media/30-day-trial-walkthrus/30day-cfg-pol-40-gen_cfg_pol.png)

    4.  Typ een naam voor het beleid, schakel de optie **Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten** in en stel de **Minimale wachtwoordlengte** in op **4**.

        ![Wachtwoordinstellingen configureren](../media/30-day-trial-walkthrus/30day-cfg-pol-41-name-policy.png)

    5.  Klik op **Ja** om het beleid te implementeren.

        ![Beleid implementeren](../media/30-day-trial-walkthrus/30day-cfg-pol-42-yes-deploy-pol.png)

    6.  Klik op de gebruikersgroep die u eerder hebt gemaakt. Klik vervolgens op **Toevoegen** en daarna op **OK**.

        ![Groep voor beleid selecteren](../media/30-day-trial-walkthrus/30day-cfg-pol-43-add-pol-to-grp.png)

        U hebt nu een iOS-pincodebeleid gemaakt dat is gericht op uw testgebruikersgroep.

        ![Configuratie van beleid is voltooid](../media/30-day-trial-walkthrus/30day-cfg-pol-44-policy-applied.png)

## Controleren of het beleid wordt toegepast op een iOS-apparaat

1.  Start de iOS App Store op een iPad, installeer de gratis app **Microsoft Intune-bedrijfsportal** en open deze.

    ![Bedrijfsportal installeren](../media/30-day-trial-walkthrus/30day-cfg-pol-45-cportal-installed.png)

2.  Voer de naam en het wachtwoord van uw testgebruikersaccount in en tik op **Aanmelden**.

    ![Uw referenties opgeven](../media/30-day-trial-walkthrus/30day-cfg-pol-46-cportal-signin.png)

3.  Tik op **Inschrijven** om de inschrijving van het apparaat in Intune te starten.

    ![Inschrijving starten](../media/30-day-trial-walkthrus/30day-cfg-pol-47-tap-enroll.jpg)

4.  Tik in het scherm **Profiel installeren** op **Installeren**.

    ![Een profiel installeren](../media/30-day-trial-walkthrus/30day-cfg-pol-48-profile-install-1.jpg)

5.  Tik in het dialoogvenster **Profiel installeren** op **Installeren**.

    ![Installatie van profiel voortzetten](../media/30-day-trial-walkthrus/30day-cfg-pol-49-profile-install-2.jpg)

6.  Tik in het scherm **Waarschuwing** op **Installeren**.

    ![Accepteer het waarschuwingsbericht](../media/30-day-trial-walkthrus/30day-cfg-pol-50-warning-install-3.png)

7.  Tik in het dialoogvenster **Extern beheer** op **Vertrouwen**.

    ![Extern beheer vertrouwen](../media/30-day-trial-walkthrus/30day-cfg-pol-51-remt-mgmt-trust.jpg)

8.  Tik op **Gereed** wanneer de installatie van het beheerprofiel is voltooid. De inschrijving is nu voltooid.

    ![Inschrijving voltooid](../media/30-day-trial-walkthrus/30day-cfg-pol-52-profile-done.jpg)

9. Wanneer de inschrijving is voltooid, tikt u op **OK** en sluit u de bedrijfsportal-app.

    ![Op OK tikken om de bedrijfsportal-app te sluiten](../media/30-day-trial-walkthrus/30day-cfg-pol-53-devc-enrolled-ok.png)

10. Tik op **Doorgaan** wanneer u wordt gevraagd een wachtwoordcode te configureren.

    ![Prompt accepteren om wachtwoordcode te configureren](../media/30-day-trial-walkthrus/30day-cfg-pol-54-passcode-req-cont.png)

11. Voer uw wachtwoordcode in, tik op **Doorgaan**, voer uw wachtwoordcode nogmaals in en tik op **Opslaan**.

    ![Een wachtwoordcode opgeven](../media/30-day-trial-walkthrus/30day-cfg-pol-55-passcode-enter.jpg)

12. Druk op de aan/uit-knop om uw iPad te vergrendelen. Wanneer u de schuifknop omzet om de iPad te ontgrendelen, ziet u dat u nu uw wachtwoordcode moet invoeren om het apparaat te ontgrendelen.

### Zie tevens
[Intune-evaluatiehandleiding](get-started-with-a-30-day-trial-of-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


