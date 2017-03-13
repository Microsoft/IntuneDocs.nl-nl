---
title: De Intune-certificaatinfrastructuur configureren voor PKCS
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u uw infrastructuur kunt configureren voor het gebruik van PKCS-certificaten in Intune.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e189ebd1-6ca1-4365-9d5d-fab313b7e979
ms.reviewer: vinaybha
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 74899f8d9721ff3a6ddbdd0716fb935c937a5a55
ms.lasthandoff: 02/18/2017



---
# <a name="configure-your-microsoft-intune-certificate-infrastructure-for-pkcs"></a>De Microsoft Intune-certificaatinfrastructuur configureren voor PKCS
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

In dit onderwerp wordt beschreven wat u nodig hebt om PKCS-certificaatprofielen te maken en implementeren met Intune.

U hebt een certificeringsinstantie voor ondernemingen nodig om op certificaten gebaseerde verificatie in uw organisatie te laten werken.

Voor het gebruik van PKCS-certificaatprofielen hebt u, afgezien van een certificeringsinstantie voor ondernemingen, ook het volgende nodig:

-   Een computer die kan communiceren met de certificeringsinstantie of u kunt de computer van de certificeringsinstantie zelf gebruiken.

-  De Intune-certificaatconnector die wordt uitgevoerd op de computer die met de certificeringsinstantie kan communiceren.

## <a name="important-terms"></a>Belangrijke termen


-    **Active Directory-domein**: alle servers die in dit gedeelte worden genoemd (met uitzondering van de webtoepassingsproxyserver), moeten lid zijn van uw Active Directory-domein.

-  **Certificeringsinstantie**: een certificeringsinstantie (CA) voor ondernemingen die wordt uitgevoerd op een Enterprise-editie van Windows Server 2008 R2 of hoger. Een zelfstandige CA wordt niet ondersteund. Zie [Install the Certification Authority](http://technet.microsoft.com/library/jj125375.aspx)(De certificeringsinstantie installeren) voor instructies over het instellen van een certificeringsinstantie.
    Als de certificeringsinstantie werkt met Windows Server 2008 R2, moet u [de hotfix uit KB2483564 installeren](http://support.microsoft.com/kb/2483564/).

-  **Een computer die kan communiceren met de certificeringsinstantie**: of gebruik de computer van de certificeringsinstantie zelf.
-  **Microsoft Intune-certificaatconnector**: via Azure Portal downloadt u het installatieprogramma voor de **certificaatconnector** (**ndesconnectorssetup.exe**). Vervolgens kunt u **ndesconnectorssetup.exe** uitvoeren op de computer waarop u de certificaatconnector wilt installeren. Voor PKCS-certificaatprofielen installeert u de certificaatconnector op de computer die communiceert met de certificeringsinstantie.
-  **Webtoepassingsproxyserver** (optioneel): u kunt een server met Windows Server 2012 R2 of hoger als webtoepassingsproxyserver (WAP-server) gebruiken. Deze configuratie:
    -  Maakt het mogelijk dat apparaten certificaten ontvangen met een internetverbinding.
    -  Is een beveiligingsaanbeveling wanneer apparaten via internet verbinding maken om certificaten te ontvangen en te verlengen.

 > [!NOTE]           
> -    De server die als host voor WAP fungeert, [moet een update installeren](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) waarmee ondersteuning wordt geboden voor de lange URL's die worden gebruikt door de Network Device Enrollment Service (NDES). Deze update is opgenomen in het [updatepakket van december 2014](http://support.microsoft.com/kb/3013769)en is afzonderlijk verkrijgbaar in [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Daarnaast moet de server waarop WAP als host optreedt, een SSL-certificaat hebben dat overeenkomt met de naam zoals die voor externe clients wordt gepubliceerd. Bovendien moet de server het SSL-certificaat vertrouwen dat op de NDES-server wordt gebruikt. De WAP-server kan met deze certificaten de SSL-verbinding van clients beëindigen en een nieuwe SSL-verbinding naar de NDES-server maken.
    Zie het gedeelte **Certificaten plannen** van [Publicatie van toepassingen met Web Application Proxy plannen](https://technet.microsoft.com/library/dn383650.aspx) voor meer informatie over certificaten voor WAP. Zie [Werken met Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx) voor algemene informatie over WAP-servers.|


## <a name="certificates-and-templates"></a>Certificaten en sjablonen

|Object|Details|
|----------|-----------|
|**Certificaatsjabloon**|U configureert deze sjabloon op uw verlenende CA.|
|**Vertrouwd basis-CA-certificaat**|U exporteert dit als een **.cer** -bestand van de verlenende CA of een ander apparaat dat de verlenende CA vertrouwt, en implementeert het naar apparaten met het profiel voor een vertrouwd CA-certificaat.<br /><br />U gebruikt één vertrouwd basis-CA-certificaat per besturingssysteemplatform en koppelt het aan elk vertrouwd basiscertificaatprofiel dat u maakt.<br /><br />U kunt extra vertrouwde basis-CA-certificaten gebruiken als dat nodig is. U kunt dit bijvoorbeeld doen om een vertrouwensrelatie met een CA te leveren die de serververificatiecertificaten voor uw Wi-Fi-toegangspunten ondertekent.|


## <a name="configure-your-infrastructure"></a>Uw infrastructuur configureren
Voordat u certificaatprofielen kunt configureren, moet u de volgende taken uitvoeren. Voor deze taken is kennis nodig van Windows Server 2012 R2 en Active Directory Certificate Services (ADCS):

- **Taak 1**: certificaatsjablonen configureren op de certificeringsinstantie.
- **Taak 2**: de Intune-certificaatconnector inschakelen, installeren en configureren.

## <a name="task-1---configure-certificate-templates-on-the-certification-authority"></a>Taak 1: Certificaatsjablonen configureren op de certificeringsinstantie
In deze taak publiceert u de certificaatsjabloon.

### <a name="to-configure-the-certification-authority"></a>De certificeringsinstantie configureren

1.  Gebruik op de verlenende CA de module Certificaatsjablonen om een nieuwe aangepaste sjabloon te maken of een bestaande sjabloon te kopiëren en te bewerken (zoals de gebruikerssjabloon) voor gebruik met PKCS.

    De sjabloon moet het volgende omvatten:

    -   Geef een gebruiksvriendelijke **weergavenaam voor de sjabloon** op.

    -   Selecteer op het tabblad **Onderwerpnaam** de optie **Met de aanvraag meeleveren**. (Beveiliging wordt afgedwongen door de Intune-beleidsmodule voor NDES.)

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

4.  Zorg er op de CA-computer voor dat de computer die de Intune-certificaatconnector host inschrijvingsmachtigingen heeft, zodat deze toegang heeft tot de sjabloon die wordt gebruikt voor het maken van het PKCS-certificaatprofiel. U stelt die machtiging in op het tabblad **Beveiliging** van de eigenschappen van de CA-computer.

## <a name="task-2---enable-install-and-configure-the-intune-certificate-connector"></a>Taak 2: de Intune-certificaatconnector inschakelen, installeren en configureren
In deze taak:

De certificaatconnector downloaden, installeren en configureren.

### <a name="to-enable-support-for-the-certificate-connector"></a>Ondersteuning voor de certificaatconnector inschakelen

1.  Meld u aan bij Azure Portal.
2.  Kies **Meer services** > **Overige** > **Intune**.
3.  Kies **Apparaten configureren** op de blade **Intune**.
2.  Kies **Instellen** > **Certificeringsinstantie** op de blade **Apparaatconfiguratie**.
2.  Kies **Inschakelen** onder **Stap 1**.

### <a name="to-download-install-and-configure-the-certificate-connector"></a>De certificaatconnector downloaden, installeren en configureren

1.  Kies **Instellen** > **Certificeringsinstantie** op de blade **Apparaten configureren**.
2.  Kies **De certificaatconnector downloaden**.
2.  Nadat het downloaden is voltooid, voert u het gedownloade installatieprogramma (**ndesconnectorssetup.exe**) uit.
  Voer het installatieprogramma uit op de computer die verbinding kan maken met de certificeringsinstantie. Kies de optie PKCS-distributie en kies **Installeren**. Wanneer de installatie is voltooid, gaat u door met het maken van een certificaatprofiel, zoals beschreven in [Certificaatprofielen configureren](how-to-configure-certificates.md).

3.  Als naar het clientcertificaat voor de certificaatconnector wordt gevraagd, kiest u **Selecteren**en selecteert u het certificaat voor **clientverificatie** dat u hebt geïnstalleerd.

    Nadat u het certificaat voor clientverificatie hebt geselecteerd, keert u terug naar het oppervlak **Clientcertificaat voor Microsoft Intune-certificaatconnector** . Hoewel het geselecteerde certificaat niet wordt weergegeven, kiest u **Volgende** om de eigenschappen van dat certificaat weer te geven. Kies **Volgende** en vervolgens **Installeren**.

4.  Nadat de wizard is voltooid, maar voordat de wizard wordt gesloten, klikt u op **Gebruikersinterface van certificaatconnector starten**.

    > [!TIP]
    > Als u de wizard sluit voordat u de gebruikersinterface van de certificaatconnector start, kunt u deze opnieuw openen door de volgende opdracht uit te voeren:
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  In de gebruikersinterface van de **certificaatconnector** :

    a. Kies **Aanmelden** en voer uw Intune-servicebeheerder- of tenantbeheerderreferenties met de machtiging voor algemeen beheer in.

  <!--  If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.-->

    b. Selecteer het tabblad **Geavanceerd** en geef vervolgens referenties op voor een account met de machtiging **Certificaten verlenen en beheren** op uw verlenende certificeringsinstantie.

    c. Kies **Toepassen**.

    U kunt nu de gebruikersinterface van de certificaatconnector sluiten.

6.  Open een opdrachtprompt en typ **services.msc**. Druk op **Enter**, klik met de rechtermuisknop op de **Intune-connectorservice** en kies **Opnieuw opstarten**.

Controleer of de service wordt uitgevoerd door een browser te openen en de volgende URL in te voeren. Hierop moet een **403** -fout worden geretourneerd:

**http:// &lt;FQDN_van_uw_NDES-server&gt;/certsrv/mscep/mscep.dll**

### <a name="next-steps"></a>Volgende stappen
U bent nu klaar om certificaatprofielen in te stellen, zoals beschreven in [How to configure certificates with Intune](how-to-configure-certificates.md) (Certificaten configureren met Intune).

