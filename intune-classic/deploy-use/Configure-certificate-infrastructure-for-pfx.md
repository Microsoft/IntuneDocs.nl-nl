---
title: De certificaatinfrastructuur configureren voor PFX | Microsoft Docs
description: .PFX-certificaatprofielen maken en implementeren.
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 11/17/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c543a02-44a5-4964-8000-a45e3bf2cc69
ms.reviewer: vinaybha
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: d2e3d25111c35bff814923f4824a1c8bda3677ec
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017



---
# <a name="configure-certificate-infrastructure"></a>Certificaatinfrastructuur configureren

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In dit onderwerp wordt beschreven wat u nodig hebt om .PFX-Certificaatprofielen te maken en implementeren.

U hebt een certificeringsinstantie voor ondernemingen nodig om op certificaten gebaseerde verificatie in uw organisatie te laten werken.

Voor het gebruik van .pfx-certificaatprofielen hebt u, afgezien van een certificeringsinstantie voor ondernemingen, ook het volgende nodig:

-   Een computer die kan communiceren met de certificeringsinstantie of u kunt de computer van de certificeringsinstantie zelf gebruiken.

-  De Intune-certificaatconnector die wordt uitgevoerd op de computer die met de certificeringsinstantie kan communiceren.

## <a name="on-premises-infrastructure-description"></a>Beschrijving van de on-premises infrastructuur


-    **Active Directory-domein**: alle servers die in dit gedeelte worden genoemd (met uitzondering van de webtoepassingsproxyserver), moeten lid zijn van uw Active Directory-domein.

-  **Certificeringsinstantie**: een certificeringsinstantie (CA) voor ondernemingen die wordt uitgevoerd op een Enterprise-editie van Windows Server 2008 R2 of hoger. Een zelfstandige CA wordt niet ondersteund. Zie [Install the Certification Authority](http://technet.microsoft.com/library/jj125375.aspx)(De certificeringsinstantie installeren) voor instructies over het instellen van een certificeringsinstantie.
    Als de certificeringsinstantie werkt met Windows Server 2008 R2, moet u [de hotfix uit KB2483564 installeren](http://support.microsoft.com/kb/2483564/).

-  **Een computer die kan communiceren met de certificeringsinstantie**: of gebruik de computer van de certificeringsinstantie zelf.
-  **Microsoft Intune-certificaatconnector**: u kunt de Intune-beheerconsole gebruiken om het installatieprogramma voor de **Certificaatconnector** (**ndesconnectorssetup.exe**) te downloaden. Vervolgens kunt u **ndesconnectorssetup.exe** uitvoeren op de computer waarop u de certificaatconnector wilt installeren. Voor PFX-certificaatprofielen installeert u de certificaatconnector op de computer die communiceert met de certificeringsinstantie.
-  **Webtoepassingsproxyserver** (optioneel): u kunt een server met Windows Server 2012 R2 of hoger als webtoepassingsproxyserver (WAP-server) gebruiken. Deze configuratie:
    -  Maakt het mogelijk dat apparaten certificaten ontvangen met een internetverbinding.
    -  Is een beveiligingsaanbeveling wanneer apparaten via internet verbinding maken om certificaten te ontvangen en te verlengen.

 > [!NOTE]           
> -    De server die als host voor WAP fungeert, [moet een update installeren](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) waarmee ondersteuning wordt geboden voor de lange URL's die worden gebruikt door de Network Device Enrollment Service (NDES). Deze update is opgenomen in het [updatepakket van december 2014](http://support.microsoft.com/kb/3013769)en is afzonderlijk verkrijgbaar in [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Daarnaast moet de server waarop WAP als host optreedt, een SSL-certificaat hebben dat overeenkomt met de naam zoals die voor externe clients wordt gepubliceerd. Bovendien moet de server het SSL-certificaat vertrouwen dat op de NDES-server wordt gebruikt. De WAP-server kan met deze certificaten de SSL-verbinding van clients beëindigen en een nieuwe SSL-verbinding naar de NDES-server maken.
    Zie het gedeelte **Certificaten plannen** van [Publicatie van toepassingen met Web Application Proxy plannen](https://technet.microsoft.com/library/dn383650.aspx) voor meer informatie over certificaten voor WAP. Zie [Werken met Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx) voor algemene informatie over WAP-servers.|


### <a name="certificates-and-templates"></a>Certificaten en sjablonen

|Object|Details|
|----------|-----------|
|**Certificaatsjabloon**|U configureert deze sjabloon op uw verlenende CA.|
|**Vertrouwd basis-CA-certificaat**|U exporteert dit als een **.cer** -bestand van de verlenende CA of een ander apparaat dat de verlenende CA vertrouwt, en implementeert het naar apparaten met het profiel voor een vertrouwd CA-certificaat.<br /><br />U gebruikt één vertrouwd basis-CA-certificaat per besturingssysteemplatform en koppelt het aan elk vertrouwd basiscertificaatprofiel dat u maakt.<br /><br />U kunt extra vertrouwde basis-CA-certificaten gebruiken als dat nodig is. U kunt dit bijvoorbeeld doen om een vertrouwensrelatie met een CA te leveren die de serververificatiecertificaten voor uw Wi-Fi-toegangspunten ondertekent.|


## <a name="configure-your-infrastructure"></a>Uw infrastructuur configureren
Voordat u certificaatprofielen kunt configureren, moet u de volgende taken uitvoeren. Voor deze taken is kennis nodig van Windows Server 2012 R2 en Active Directory Certificate Services (ADCS):

- **Taak 1**: certificaatsjablonen configureren op de certificeringsinstantie.
- **Taak 2**: de Intune-certificaatconnector inschakelen, installeren en configureren.

### <a name="task-1---configure-certificate-templates-on-the-certification-authority"></a>Taak 1: Certificaatsjablonen configureren op de certificeringsinstantie
In deze taak publiceert u de certificaatsjabloon.

##### <a name="to-configure-the-certification-authority"></a>De certificeringsinstantie configureren

1.  Gebruik op de verlenende CA de module Certificaatsjablonen om een nieuwe aangepaste sjabloon te maken of een bestaande sjabloon te kopiëren en te bewerken (zoals de gebruikerssjabloon) voor gebruik met PFX.

    De sjabloon moet het volgende omvatten:

    -   Geef een gebruiksvriendelijke **weergavenaam voor de sjabloon** op.

    -   Selecteer op het tabblad **Onderwerpnaam** de optie **Met de aanvraag meeleveren**. 

    -   Zorg ervoor dat op het tabblad **Extensies** de **beschrijving van toepassingsbeleid** de optie **Clientverificatie**bevat.

        > [!IMPORTANT]
        > Bewerk voor iOS- en Mac OS X-certificaatsjablonen op het tabblad **Extensies** het **sleutelgebruik** en zorg ervoor dat **Handtekening is bewijs van authenticiteit** niet is ingeschakeld.

2.  Controleer de **geldigheidsperiode** op het tabblad **Algemeen** van de sjabloon. Standaard gebruikt Intune de waarde die is geconfigureerd in de sjabloon. U kunt de CA echter zodanig configureren dat de aanvrager een andere waarde kan opgeven, die u vervolgens vanuit de Intune-beheerconsole kunt instellen. Als u altijd de waarde in de sjabloon wilt gebruiken, slaat u de rest van deze stap over.

    > [!IMPORTANT]
    > Het iOS- en het Mac OS X-platform gebruiken altijd de waarde die in de sjabloon is ingesteld, ongeacht andere configuraties die u instelt.

    Als u de CA zo wilt configureren dat de aanvrager de geldigheidsperiode kan opgeven, voert u de volgende opdrachten uit op de CA:

    a.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**

    b.  **net stop certsvc**

    c.  **net start certsvc**

3.  Gebruik op de verlenende CA de module Certificeringsinstantie om de certificaatsjabloon te publiceren.

    a.  Selecteer het knooppunt **Certificaatsjablonen**, klik op **Actie**-&gt; **Nieuw** &gt; **Te verlenen certificaatsjablonen** en selecteer de sjabloon die u in stap 2 hebt gemaakt.

    b.  Controleer in de map **Certificaatsjablonen** of de sjabloon is gepubliceerd.

4.  Zorg er op de CA-computer voor dat de computer die de Intune-certificaatconnector host registratiemachtigingen heeft, zodat deze toegang heeft tot de sjabloon die wordt gebruikt voor het maken van het PFX-profiel. U stelt die machtiging in op het tabblad **Beveiliging** van de eigenschappen van de CA-computer.

### <a name="task-2---enable-install-and-configure-the-intune-certificate-connector"></a>Taak 2: de Intune-certificaatconnector inschakelen, installeren en configureren
In deze taak:

De certificaatconnector downloaden, installeren en configureren.

##### <a name="to-enable-support-for-the-certificate-connector"></a>Ondersteuning voor de certificaatconnector inschakelen

1.  Open de [Intune-beheerconsole](https://manage.microsoft.com) en kies **Beheer** &gt; **Certificaatconnector**.

2.  Kies **On-premises certificaatconnector configureren**.

3.  Selecteer **Certificaatconnector inschakelen**en kies **OK**.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>De certificaatconnector downloaden, installeren en configureren

1.  Open de [Intune-beheerconsole](https://manage.microsoft.com) en kies **Beheer** &gt; **Mobile Device Management** &gt; **Certificaatconnector** &gt; **Certificaatconnector downloaden**.

2.  Nadat het downloaden is voltooid, voert u het gedownloade installatieprogramma (**ndesconnectorssetup.exe**) uit.

  Voer het installatieprogramma uit op de computer die verbinding kan maken met de certificeringsinstantie. Selecteer de optie PFX-distributie en kies **Installeren**. Wanneer de installatie is voltooid, gaat u door met het maken van een certificaatprofiel, zoals beschreven in [Certificaatprofielen configureren](configure-intune-certificate-profiles.md).

   <!-- Not sure about step 3 below -->

3.  Als naar het clientcertificaat voor de certificaatconnector wordt gevraagd, kiest u **Selecteren**en selecteert u het certificaat voor **clientverificatie** dat u in Taak 3 hebt geïnstalleerd.

    Nadat u het certificaat voor clientverificatie hebt geselecteerd, keert u terug naar het oppervlak **Clientcertificaat voor Microsoft Intune-certificaatconnector** . Hoewel het geselecteerde certificaat niet wordt weergegeven, kiest u **Volgende** om de eigenschappen van dat certificaat weer te geven. Kies **Volgende** en vervolgens **Installeren**.

4.  Nadat de wizard is voltooid, maar voordat de wizard wordt gesloten, klikt u op **Gebruikersinterface van certificaatconnector starten**.

    > [!TIP]
    > Als u de wizard sluit voordat u de gebruikersinterface van de certificaatconnector start, kunt u deze opnieuw openen door de volgende opdracht uit te voeren:
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  In de gebruikersinterface van de **certificaatconnector** :

    a. Kies **Aanmelden** en voer uw Intune-servicebeheerder- of tenantbeheerderreferenties met de machtiging voor algemeen beheer in.

    b. Selecteer het tabblad **Geavanceerd** en geef vervolgens referenties op voor een account met de machtiging **Certificaten verlenen en beheren** op uw verlenende certificeringsinstantie.

    c. Kies **Toepassen**.

    U kunt nu de gebruikersinterface van de certificaatconnector sluiten.

6.  Open een opdrachtprompt en typ **services.msc**. Druk op **Enter**, klik met de rechtermuisknop op de **Intune-connectorservice** en kies **Opnieuw opstarten**.


### <a name="next-steps"></a>Volgende stappen
U bent nu klaar om certificaatprofielen te configureren, zoals beschreven in [Certificaatprofielen configureren](Configure-Intune-certificate-profiles.md).

