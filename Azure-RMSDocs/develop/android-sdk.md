---
title: Android-configuratie | Azure RMS
description: "Ontwikkelaars van Android-toepassingen kunnen gebruikmaken van de Microsoft Rights Management SDK 4.2 voor geïntegreerde gegevensbeveiliging in hun toepassingen."
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 986f6932-159b-4791-bd1a-7640a83ee792
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 79397c82d9478cbd55630a376fe2d12f3873ebc4
ms.openlocfilehash: 4ff6328c0be4cd217390ee802e53e93c90f41c99


---

# Android-configuratie

Ontwikkelaars van Android toepassingen kunnen gebruikmaken van de Microsoft Rights Management SDK 4.2 voor geïntegreerde gegevensbeveiliging in hun toepassingen met behulp van Azure Active Directory Rights Management (AAD RM).

Dit onderwerp bevat de stappen voor het instellen van uw omgeving zodat u uw eigen nieuwe apps kunt maken.

-   [Vereisten](#prerequisites)
-   [Optioneel](#optional)
-   [Uw ontwikkelomgeving configureren](#configuring-your-development-environment_)
-   [Zie ook](#see-also)

## Vereisten

We bevelen de volgende software op uw ontwikkelsysteem aan:

-   Windows- of OS X-besturingssysteem voor het uitvoeren van de [Eclipse](http://www.oracle.com/technetwork/java/javase/downloads/jre7-downloads-1880261.html)-ontwikkelomgeving.
-   In deze handleiding wordt ervan uitgegaan dat u de Eclipse SDK vanaf Eclipse Juno 4.2 gebruikt als standaardinstallatie.
-   Java vanaf Java 1.6.
-   [Invoegtoepassing Android Developer Tools (ADT)](http://developer.android.com/sdk/installing/index.html). Opmerking: u wordt mogelijk gevraagd om Eclipse opnieuw te starten om de installatie te voltooien.

     

-   MS RMS SDK 4.2-pakket voor Android. Zie [Aan de slag](get-started.md) voor meer informatie.

    Deze SDK kan worden gebruikt voor het ontwikkelen voor Android 4.0.3 (API-niveau 15) en hoger.

-   Verificatiebibliotheek: U kunt het beste de [Azure AD Authentication Library (ADAL)](https://msdn.microsoft.com/library/jj573266.aspx) gebruiken. Andere verificatie-bibliotheken die ondersteuning bieden voor OAuth 2.0, kunnen echter ook worden gebruikt.

    Zie [ADAL voor Android](https://github.com/MSOpenTech/azure-activedirectory-library-for-android) voor meer informatie

    **Opmerking**: als uw toepassing de ADAL-bibliotheek niet gebruikt als OAuth 2.0-verificatiebibliotheek, wordt u aangeraden de volgende richtlijnen te lezen: Android [Some SecureRandom Thoughts](http://android-developers.blogspot.com/2013/08/some-securerandom-thoughts.html) (Enkele ideeën over SecureRandom).

     

Lees het onderwerp [Wat is er nieuw](release-notes.md) voor informatie over de API-updates, release-opmerkingen en veelgestelde vragen (FAQ).

## Optioneel

Onze UI-bibliotheek biedt een herbruikbare UI voor gebruiks- en beveiligingsbewerkingen voor ontwikkelaars die geen eigen aangepaste UI willen maken: [UI-bibliotheek en voorbeeldapp voor Android](https://github.com/AzureAD/rms-sdk-ui-for-android).

## Uw ontwikkelomgeving configureren

**Opmerking**: MS RMS SDK 4.2 Preview Release: in deze preview-versie zijn de schermafdrukken niet bijgewerkt aan de gewijzigde naam van de paden van com/microsoft/protection in com/microsoft/rightsmanagment. De tekst is echter wel bijgewerkt.

 
-   Open de Eclipse-ontwikkelomgeving.
-   Als u een nieuw project voor een Android-toepassing wilt maken, klikt u in het menu **File** (Bestand) op **New** (Nieuw) en vervolgens op **Project**, en selecteert u **Android Application Project** (Android toepassingsproject).

    ![Een nieuwe Android-toepassing maken](../media/Android-setup-01c.png)

-   Voer de toepassingsnaam in. De projectnaam en pakketnaam worden ingevuld op basis van de naam van de toepassing.
-   Klik op **Next** (Volgende) en selecteer waar u de werkruimte wilt maken.

    ![De toepassingsnaam invoeren](../media/Android-setup-02a.jpg)

-   Klik op **Next** (Volgende) en selecteer een pictogram voor uw app.

    ![Een pictogram selecteren voor uw app](../media/Android-setup-03.png)

-   Klik op **Next** (Volgende) en selecteer **Blank Activity** (Lege activiteit) om de activiteit te maken.

    ![De activiteit maken](../media/Android-setup-04.png)

-   Klik op **Next** (Volgende) en geef een naam op voor de activiteit. U kunt *MainActivity* behouden als de standaardnaam met de lay-outnaam *activity\_main*.

    ![Een naam opgeven voor de activiteit](../media/Android-setup-05a.jpg)

-   Klik op **Voltooien**.

    ![Het maken voltooien](../media/Android-setup-06.jpg)

-   Uw project is gemaakt, samen met de belangrijkste activiteitklasse *MainActivity.java*.

**Verwijzing naar de SDK**

-   Navigeer naar de map waarin u *adrms\_android\_sdk.zip* hebt uitgepakt. Controleer in de map SDK > com > microsoft > rightsmanagement of de bestanden *.classpath*, *.project* en *project.properties* niet zijn gemarkeerd als alleen-lezen.
-   Om te verwijzen naar de SDK, moet u deze importeren naar de werkruimte.

    Klik in Eclipse op **File** (Bestand). Klik in het menu **File** (Bestand) op **Import** (Importeren). Selecteer in het dialoogvenster **Import** (Importeren) de optie **Android / Existing Android Code into Workspace** (Android / bestaande Android-code in werkruimte).

    ![Importeren in de werkruimte](../media/Android-setup-07.png)

-   Klik op **Volgende**. Navigeer om de map te selecteren waarin u *adrms\_android\_sdk.zip* hebt uitgepakt. De SDK moet in de lijst worden weergegeven als **com.microsoft.rightsmanagement**.

    ![Navigeren om de map te selecteren](../media/Android-setup-08c.jpg)

-   Wanneer u klikt op **Finish** (Voltooien), verschijnt het SDK-project op hetzelfde niveau als uw eerder gemaakte toepassing.

    ![Het SDK-project verschijnt op hetzelfde niveau als uw toepassing](../media/Android-setup-09.jpg)

-   Klik met de rechtermuisknop op het pictogram **Project** en geef de eigenschappen van het project weer.
-   Navigeer naar het tabblad **Android**.
-   Klik op **Add** (Toevoegen) en selecteer de bibliotheek *com.microsoft.rightsmanagement* vanuit de werkruimte.

    ![De bibliotheek toevoegen](../media/Android-setup-10b.jpg)

-   Klik op **OK**.

    Omdat de MS RMS SDK 4.2 verbinding maakt met AAD RM, moet de toepassing de rechten **INTERNET** en **ACCESS\_NETWORK\_STATE** krijgen. Om dit te doen, opent u het bestand *AndroidManifest.xml* in de hoofdmap van het project.

    Als u de machtigingen wilt toevoegen, klikt u op **Add** (Toevoegen) en selecteert u vervolgens **Uses Permissions** (Gebruikt machtigingen).

    ![Machtigingen toevoegen](../media/Android-setup-11d.jpg)

-   U kunt de manifeststap controleren door het manifest te bekijken in de weergave van de tekstverwerker. Controleer of de volgende regels worden weergegeven:


    <uses-sdk      android:minSdkVersion="15"      android:targetSdkVersion="19"/> <uses-permission android:name="android.permission.INTERNET"/> <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/> <uses-permission/>


**Opmerking** de SDK gebruikt *android.support.v4*

-   U bent nu klaar om uw eigen nieuwe Android-apps te maken.

### Zie ook

[Aan de slag](get-started.md)

[Wat is er nieuw?](release-notes.md)

[Termen en begrippen voor ontwikkelaars](core-concepts.md)

[Android-API-referentiemateriaal](android-namespaces.md)

 

 



<!--HONumber=Jul16_HO4-->


