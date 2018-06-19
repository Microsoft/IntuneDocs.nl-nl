---
title: Uw MDM-instantie wijzigen naar Configuration Manager (hybride MDM)
description: Informatie over het wijzigen van de MDM-instantie van een zelfstandige versie van Intune naar Configuration Manager (hybride MDM).
keywords: ''
author: dougeby
manager: dougeby
ms.date: 10/04/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f1b4bce3-7932-4a0d-aa92-6dacc7060f42
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: dc73befb46f1f159d9a8c023bb5604517b9f73f4
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31028058"
---
# <a name="change-the-mdm-authority"></a>De MDM-instantie wijzigen
Vanaf Configuration Manager versie 1610 kunt u de MDM-instantie wijzigen zonder dat u contact hoeft op te nemen met Microsoft Ondersteuning en zonder dat u de inschrijving van bestaande beheerde apparaten ongedaan hoeft te maken om ze vervolgens opnieuw in te schrijven. Dit onderwerp bevat de benodigde stappen voor het wijzigen van een bestaande Microsoft Intune-tenant die is geconfigureerd in Intune en waarbij de MDM-instantie is ingesteld op **Microsoft Intune** (zelfstandige versie) naar **Configuration Manager** (hybride MDM), zonder dat u de inschrijving van bestaande beheerde apparaten ongedaan hoeft te maken om ze vervolgens opnieuw in te schrijven.

> [!Note]    
> Zie [Change the MDM authority from Configuration Manager (hybrid MDM) to Intune standalone](https://docs.microsoft.com/sccm/mdm/deploy-use/change-mdm-authority) (De MDM-instantie wijzigen van Configuration Manager (hybride MDM) naar een zelfstandige versie van Intune) als u een bestaande Microsoft Intune-tenant die is geconfigureerd in de Configuration Manager-console (hybride) en waarbij de MDM-instantie is ingesteld op **Configuration Manager** (hybride) wilt wijzigen naar een zelfstandige versie van **Microsoft Intune**. 


## <a name="key-considerations"></a>Belangrijke overwegingen
Nadat u overschakelt naar de nieuwe MDM-instantie, duurt het waarschijnlijk enige tijd (maximaal acht uur) voordat het apparaat wordt ingecheckt en synchroniseert met de service. U moet instellingen in de nieuwe MDM-instantie (hybride) configureren om ervoor te zorgen dat geregistreerde apparaten na de wijziging nog steeds worden beheerd en beschermd. 
- Apparaten moeten na de wijziging verbinding maken met de service, zodat de instellingen van de nieuwe MDM-instantie (zelfstandige versie van Intune) de huidige instellingen op het apparaat vervangen.
- Na het wijzigen van de MDM-instantie blijven sommige basisinstellingen (zoals profielen) van de vorige MDM-instantie (zelfstandige versie van Intune) maximaal zeven dagen aanwezig op het apparaat, of totdat het apparaat de eerste keer verbinding maakt met de service. Het is aan te raden om de apps en instellingen (beleid, profielen, apps enzovoort) zo snel mogelijk te configureren in de nieuwe MDM-instantie (hybride) en de instellingen te implementeren naar de gebruikersgroepen met gebruikers met bestaande geregistreerde apparaten. Zodra een apparaat verbinding maakt met de service na de wijziging van MDM-instantie, ontvangt het de nieuwe instellingen van de nieuwe MDM-instantie om te voorkomen dat het apparaat enige tijd onbeheerd en onbeschermd is.
- Wanneer dezelfde apparaatcategorieën bestaan in Intune en Configuration Manager, worden apparaatcategorietoewijzingen voor apparaten niet overgedragen nadat u naar de nieuwe MDM-instantie bent overgeschakeld. Als u apparaatcategorieën wilt blijven gebruiken, moet u gemigreerde apparaten handmatig toevoegen aan de juiste verzamelingen nadat de MDM-instantie is gewijzigd en de apparaten worden weergegeven in de Configuration Manager-console.
- Apparaten waaraan geen gebruikers zijn gekoppeld (zoals wanneer u werkt met het iOS Device Enrollment Program of scenario’s voor bulkinschrijving) worden niet gemigreerd naar de nieuwe MDM-instantie. Voor die apparaten moet u contact opnemen met ondersteuning voor hulp bij het overbrengen naar de nieuwe MDM-instantie.

## <a name="prepare-to-change-the-mdm-authority-to-configuration-manager-hybrid"></a>Voorbereiden op het wijzigen van de MDM-instantie naar Configuration Manager (hybride)
Lees de volgende informatie ter voorbereiding op het wijzigen van de MDM-instantie:
- De optie voor het wijzigen van de MDM-instantie is alleen beschikbaar in Configuration Manager versie 1610 of hoger.
- Na het overschakelen naar de nieuwe MDM-instantie kan het tot acht uur duren voordat een apparaat verbinding maakt met de service.
- Maak een Configuration Manager-gebruikersverzameling met alle gebruikers die momenteel worden beheerd door de zelfstandige versie van Intune. Deze verzameling gebruikt u bij het instellen van het Intune-abonnement in de Configuration Manager-console. Hiermee zorgt u ervoor dat er een Configuration Manager-licentie is toegewezen aan de gebruikers en hun apparaten en kunnen ze worden beheerd in de hybride omgeving na de wijziging van de MDM-instantie.
- Zorg dat de gebruikersverzameling ook de IT-beheerder omvat.  
- Voor de wijziging wordt de MDM-instantie weergegeven als **Ingesteld op Microsoft Intune** (zelfstandige versie) in de Intune-beheerconsole.
- Voorafgaand aan de wijziging van MDM-instantie moet de MDM-instantie worden weergegeven als **Ingesteld op Microsoft Intune** (zelfstandige tenant) in de Microsoft Intune-beheerconsole.
    > [!NOTE]    
    > Als de MDM-instantie wordt weergegeven als **Beheerd door Intune en Office 365** worden uw door Office 365 beheerde MDM-apparaten niet meer beheerd wanneer u de MDM-instantie wijzigt in **Configuration Manager** (hybride). We adviseren om die gebruikers te voorzien van een licentie voor Intune of Enterprise Mobility Suite voordat u de MDM-instantie wijzigt.   

- Verwijder in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) de rol Apparaatinschrijvingsmanager. Zie [Een apparaatinschrijvingsmanager uit Intune verwijderen](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune#delete-a-device-enrollment-manager-from-intune) voor meer informatie.
- Schakel eventuele groepstoewijzingen die zijn geconfigureerd uit. Zie [Apparaten categoriseren met apparaatgroeptoewijzing in Microsoft Intune](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune) voor meer informatie.
- De eindgebruikers mogen niets merken van de wijziging van MDM-instantie. Mogelijk wilt u de wijziging echter bekendmaken aan gebruikers, om ervoor te zorgen dan hun apparaten zijn ingeschakeld en dat die kort na de wijziging verbinding maken met de service. Hiermee zorgt u ervoor dat zoveel mogelijk apparaten zo snel mogelijk verbinding maken met en registeren bij de service via de nieuwe instantie.
- Als u de zelfstandige versie van Intune gebruikt om iOS-apparaten te beheren voorafgaand aan de wijziging van MDM-instantie, moet u ervoor zorgen dat hetzelfde Apple Push Notification Service-certificaat (APNs) dat werd gebruikt in Intune wordt vernieuwd en gebruikt om de tenant opnieuw in te stellen in Configuration Manager (hybride).    

    > [!IMPORTANT]  
    > Als er een ander APNs-certificaat wordt gebruikt voor hybride, worden ALLE eerder ingeschreven iOS-apparaten uitgeschreven en moet u het gehele inschrijvingsproces opnieuw doorlopen. Zorg dat u precies weet welk APNs-certificaat is gebruikt voor het beheren van iOS-apparaten in Intune voordat u de MDM-instantie wijzigt. Zoek de vermelding van dat certificaat in de Apple Push Certificates Portal (https://identity.apple.com)), zorg dat u weet wie de gebruiker is van wie de Apple ID is gebruikt om het oorspronkelijke APNs-certificaat te maken, en zorg dat die gebruiker beschikbaar is om hetzelfde APNs-certificaat te vernieuwen als onderdeel van de wijziging naar de nieuwe MDM-instantie.  

## <a name="change-the-mdm-authority-to-configuration-manager"></a>De MDM-instantie wijzigen naar Configuration Manager
Het proces voor het wijzigen van de MDM-instantie naar Configuration Manager (hybride) omvat de volgende hoofdstappen:  
- Voeg in de Configuration Manager-console het Microsoft Intune-abonnement toe.
- Configureer het Apple APNs-certificaat door hetzelfde APNs-certificaat te gebruiken dat u hebt vernieuwd.
- Configureer en implementeer de nieuwe instellingen en apps van de nieuwe MDM-instantie (hybride) in de Configuration Manager-console.
- De volgende keer dat apparaten verbinding maken met de service, worden ze gesynchroniseerd en ontvangen ze de nieuwe instellingen van de nieuwe MDM-instantie.

#### <a name="to-change-the-mdm-authority-to-configuration-manager"></a>De MDM-instantie wijzigen naar Configuration Manager
1. Ga in de Configuration Manager-console naar **Beheer** &gt; **Overzicht** &gt; **Cloudservices** &gt; **Microsoft Intune-abonnement** en selecteer de optie om een Intune-abonnement toe te voegen.
2. Meld u aan bij de Intune-tenant die u oorspronkelijk hebt gebruikt bij het instellen van de MDM-instantie in Intune en klik op **Volgende**.
3. Selecteer **Mijn MDM-instantie wijzigen naar Configuration Manager** en klik op **Volgende**.
4. Selecteer de gebruikersverzameling die alle gebruikers bevat die ook worden beheerd door de nieuwe hybride MDM-instantie.
5. Klik op **Volgende** en voltooi de wizard. De MDM-instantie is nu gewijzigd naar **Configuration Manager**.
6. Meld u aan bij de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) met dezelfde Intune-tenant om te controleren of de MDM-instantie is gewijzigd in **Ingesteld op Configuration Manager**.


## <a name="enable-ios-enrollment"></a>iOS-registratie inschakelen
Als u iOS-apparaten hebt, moet u het APNs-certificaat in Configuration Manager configureren.

#### <a name="to-enable-ios-enrollment-and-configure-the-apns-certificate"></a>iOS-inschrijving inschakelen en het APNs-certificaat configureren

1. **Een aanvraag voor certificaatondertekening downloaden**

   1. Ga in de Configuration Manager-console naar **Beheer** &gt; **Cloudservices** &gt; **Microsoft Intune-abonnementen** en selecteer **APNs-certificaataanvraag maken** om het dialoogvenster **Aanvraag voor Apple Push Notification Service-certificaatondertekening aanvragen** te openen.  
   2. **Blader** naar het pad om het nieuwe aanvraagbestand tot certificaatondertekening (.csr) op te slaan. Sla het bestand met de aanvraag voor certificaatondertekening (.csr) lokaal op.  
   3. Klik op **Downloaden**. Het nieuwe Microsoft Intune CSR-bestand wordt gedownload en door Configuration Manager opgeslagen.   

      > [!IMPORTANT]
      > U moet een nieuwe aanvraag voor certificaatondertekening downloaden. Als u een bestaand bestand gebruikt, mislukt de aanvraag.  

2. Ga naar de [Apple Push Certificates-portal](http://go.microsoft.com/fwlink/?LinkId=269844) en meld u aan met **dezelfde** Apple-id die eerder is gebruikt voor het maken en vernieuwen van het APNs-certificaat dat u gebruikte in de zelfstandige versie van Intune.

   ![Aanmeldpagina bij de Apple Push Certificates-portal](../media/mdm-change-apns-portal.png)

3. Selecteer het APNs-certificaat dat u gebruikte in de zelfstandige versie van Intune en klik op **Vernieuwen**.

    ![Dialoogvenster APNs vernieuwen](../media/mdm-change-renew-apns.png)

4. Selecteer de aanvraag voor APNs-certificaatondertekening (.csr) die u hebt gedownload en klik op **Uploaden**.

    ![Aanmeldpagina bij de Apple Push Certificates-portal](../media/mdm-change-renew-apns-upload.png)
 
5. Selecteer hetzelfde APNs en klik op **Downloaden**. Download het APNs-certificaat (.pem) en sla het bestand lokaal op.  

    ![Aanmeldpagina bij de Apple Push Certificates-portal](../media/mdm-change-renew-apns-download.png)

6. Upload het vernieuwde APNs-certificaat naar de hybride tenant met dezelfde Apple-id als de vorige keer.

    1.  Ga in de Configuration Manager-console naar **Beheer** &gt; **Cloudservices** &gt;  **Microsoft Intune-abonnement** en kies **Platforms configureren** &gt;  **iOS**.  
    2.  Selecteer in het dialoogvenster **Eigenschappen van Microsoft Intune-abonnement** het tabblad **APNs-certificaat** en klik om het selectievakje **iOS- en Mac OS X (MDM)-inschrijving inschakelen** in te schakelen.  
    3.  Klik op **Bladeren**en ga naar het APNs-certificaatbestand (.cer) dat u bij Apple hebt gedownload. Configuration Manager geeft de APNs-certificaatinformatie weer. Klik op **OK** om het APNs-certificaat op te slaan in Intune.  

        ![Pagina Eigenschappen van Intune-abonnement - iOS](../media/mdm-change-subscription-properties-ios.png)

## <a name="enable-android-enrollment"></a>Android-inschrijving inschakelen
1. Ga in de Configuration Manager-console naar **Beheer** &gt; **Cloudservices** &gt; **Microsoft Intune-abonnement** en kies **Platforms configureren** &gt; **Android**.  
2. Selecteer **Android-inschrijving inschakelen** en klik op **OK**.

### <a name="enable-windows-enrollment"></a>Windows-inschrijving inschakelen
1. Ga in de Configuration Manager-console naar **Beheer** &gt; **Cloudservices** &gt; **Microsoft Intune-abonnement** en kies **Platforms configureren** &gt; **Windows**.  
2. Selecteer **Windows-inschrijving inschakelen** en klik op **OK**.

### <a name="enable-windows-phone-enrollment"></a>Windows Phone-inschrijving inschakelen
1. Ga in de Configuration Manager-console naar **Beheer** &gt; **Cloudservices** &gt; **Microsoft Intune-abonnement** en kies **Platforms configureren** &gt; **Windows Phone**.  
2. Selecteer het platform dat u wilt inschakelen in klik op **OK**.


## <a name="next-steps"></a>Volgende stappen
Nadat de wijziging van MDM-instantie is voltooid, bekijkt u de volgende stappen:
- Wanneer via de Intune-service wordt gedetecteerd dat de MDM-instantie van een tenant is gewijzigd, wordt er een verzoek verzonden naar alle geregistreerde apparaten om in te checken bij en te synchroniseren met de service (dit staat los van het gebruikelijke geplande inchecken). Dus nadat de MDM-instantie voor de tenant is gewijzigd van de zelfstandige versie van Intune in hybride, maken alle ingeschakelde apparaten die online zijn, verbinding met de service, ontvangen deze de nieuwe MDM-instantie en worden deze voortaan beheerd door hybride. Het beheer en de beveiliging van deze apparaten worden niet onderbroken.
- Zelfs voor ingeschakelde apparaten die online zijn tijdens (of kort na) de wijziging van MDM-instantie is er een vertraging van maximaal acht uur (afhankelijk van de timing van het gebruikelijke geplande inchecken) voordat apparaten zijn geregistreerd bij de service met de nieuwe MDM-instantie.    

  > [!IMPORTANT]    
  > Gedurende de periode tussen het wijzigen van de MDM-instantie en het uploaden van het vernieuwde APNs-certificaat naar de nieuwe instantie, mislukt het inschrijven van nieuwe apparaten en inchecken van iOS-apparaten. Daarom is het belangrijk dat u het APNs-certificaat zo snel mogelijk vernieuwt en uploadt naar de nieuwe instantie na het wijzigen van de MDM-instantie.

- Gebruikers kunnen snel overschakelen naar de nieuwe MDM-instantie door handmatig in te checken bij de service met hun apparaat. Hiervoor hoeven ze slechts de bedrijfsportal-app te openen en een compatibiliteitscontrole te starten.
- Als u wilt controleren of alles goed werkt nadat apparaten zijn ingecheckt en gesynchroniseerd met de service na het wijzigen van de MDM-instantie, zoekt u de apparaten in de Configuration Manager-console. De apparaten die voorheen werden beheerd door Intune, worden nu weergegeven als beheerde apparaten in de Configuration Manager-console.    
- Er ontstaat een tijdelijke situatie als een apparaat offline is tijdens de wijziging van MDM-instantie en pas later incheckt bij de service. Om ervoor te zorgen dat het apparaat beveiligd is en blijft functioneren tijdens deze periode, blijven de volgende profielen maximaal zeven dagen beschikbaar op het apparaat (of tot het moment waarop het apparaat verbinding maakt met de nieuwe MDM-instantie en nieuwe instellingen ontvangt die de oude overschrijven):
    - E-mailprofiel
    - VPN-profiel
    - Certificaatprofiel
    - Wi-Fi-profiel
    - Configuratieprofielen
- Nadat de MDM-instantie is gewijzigd, kan het tot een week duren voordat de nalevingsgegevens in de Microsoft Intune-beheerconsole correct worden weergegeven. De nalevingsstatus in Azure Active Directory en op het apparaat is echter wel correct, zodat het apparaat nog steeds is beveiligd.
- Zorg dat de nieuwe instellingen, die de bestaande instellingen moeten overschrijven, dezelfde naam hebben als de vorige instellingen om er zeker van te zijn dat ze worden overschreven. Anders blijven er mogelijk achterhaalde profielen en beleidsregels achter op het apparaat.    

  > [!TIP]    
  > De beste methode is om alle beheerinstellingen en -configuraties en alle implementaties zo snel mogelijk te maken nadat de wijziging van MDM-instantie is voltooid. Dit zorgt ervoor dat apparaten beveiligd zijn en actief worden beheerd in de tussenperiode.

-  Nadat u de MDM-instantie wijzigt, voert u de volgende stappen uit om te controleren of nieuwe apparaten correct worden ingeschreven bij de nieuwe instantie:   
    - Een nieuw apparaat inschrijven
    - Controleer of het nieuw ingeschreven apparaat wordt weergegeven in de Configuration Manager-console.
    - Voer een actie uit op het apparaat vanaf de beheerconsole, zoals vergrendelen op afstand. Als de actie lukt, wordt het apparaat beheerd door de nieuwe MDM-instantie.
- Als er problemen optreden met specifieke apparaten, kunt u ze uitschrijven en weer inschrijven om ze verbinding te laten maken met de nieuwe instantie en zo snel mogelijk weer te kunnen beheren.