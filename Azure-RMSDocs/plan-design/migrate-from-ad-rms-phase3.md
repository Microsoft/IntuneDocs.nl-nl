---
title: Migreren van AD RMS naar Azure Rights Management - Stap 3 | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 8b039ad5-95a6-4c73-9c22-78c7b0e12cb7
ms.reviewer: esaggese
ms.suite: ems
ms.sourcegitcommit: f7dd88d90357c99c69fe4fdde67c1544595e02f8
ms.openlocfilehash: 75cce1d0e5a1cff0d4f6609d0f084fda1af62951


---

# Migratiestap 3: configuratie van ondersteuningsservices

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management*


Gebruik de volgende informatie voor stap 3 van de migratie van AD RMS naar Azure Rights Management (Azure RMS). Deze procedures beslaan stap 6 en 7 van [Migreren van AD RMS naar Azure Rights Management](migrate-from-ad-rms-to-azure-rms.md).


## Stap 6. IRM-integratie voor Exchange Online configureren

Als u uw TDP eerder vanuit AD RMS hebt geïmporteerd in Exchange Online, moet u deze TDP verwijderen om conflicten tussen sjablonen en beleidsregels te voorkomen nadat u bent gemigreerd naar Azure RMS. Doe dit met de cmdlet [Remove-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200720%28v=exchg.150%29.aspx) vanuit Exchange Online.

Als u de Azure RMS-tenantsleuteltopologie **Door Microsoft beheerd** kiest:

-   Zie het gedeelte [Exchange Online: IRM-configuratie](../deploy-use/configure-office365.md#exchange-online-irm-configuration) in het artikel [Office 365: configuratie voor clients en onlineservices](../deploy-use/configure-office365.md). Dit gedeelte bevat gangbare opdrachten die verbinding maken met de Exchange Online-service, de tenantsleutel importeren uit Azure RMS en IRM-functionaliteit voor Exchange Online bieden. Nadat u deze stappen hebt voltooid, hebt u volledige RMS-functionaliteit met Exchange Online.

Als u de Azure RMS-tenantsleuteltopologie **Door de klant beheerd (BYOK)** kiest:

-   Met Exchange Online beschikt u over beperkte RMS-functionaliteit, zoals wordt beschreven in het artikel [BYOK-prijzen en -beperkingen](byok-price-restrictions.md).

## Stap 7. De RMS-connector implementeren
Als u de Information Rights Management-functionaliteit (IRM) van Exchange Server of SharePoint Server met AD RMS hebt gebruikt, moet u eerst IRM uitschakelen op deze servers en de AD RMS-configuratie verwijderen. Vervolgens kunt u de Rights Management-connector (RMS) implementeren. Deze functioneert als een communicatie-interface (een relais) tussen de on-premises servers en Azure RMS.

Als u voor deze stap meerdere TPD’s hebt geïmporteerd in Azure RMS die zijn gebruikt voor het beveiligen van e-mailberichten, moet u tot slot handmatig het register bewerken op de Exchange Server-computers zodat alle URL's van TPD’s worden omgeleid naar de RMS-connector.

> [!NOTE]
> Voordat u begint, controleert u de versies van de on-premises servers die Azure RMS ondersteunt, in [On-premises servers die Azure RMS ondersteunen](../get-started/requirements-servers.md).

### IRM op Exchange Servers uitschakelen en de AD RMS-configuratie verwijderen

1.  Ga op elke Exchange-server naar de volgende map en verwijder alle vermeldingen in de map: \ProgramData\Microsoft\DRM\Server\S-1-5-18

2.  Gebruik vanaf een van de Exchange-servers de Exchange-cmdlet [Set_IRMConfiguration](http://technet.microsoft.com/library/dd979792.aspx) om eerst de IRM-functies uit te schakelen voor berichten die naar interne geadresseerden worden verzonden:

    ```
    Set-IRMConfiguration -InternalLicensingEnabled $false
    ```

3.  Gebruik vervolgens dezelfde cmdlet om de IRM-functies uit te schakelen voor berichten die worden verzonden naar externe geadresseerden:

    ```
    Set-IRMConfiguration -ExternalLicensingEnabled $false
    ```

4.  Gebruik daarna dezelfde cmdlet om IRM uit te schakelen in de Microsoft Office Outlook Web App en in Microsoft Exchange ActiveSync:

    ```
    Set-IRMConfiguration -ClientAccessServerEnabled $false
    ```

5.  Gebruik tot slot dezelfde cmdlet om alle certificaten in het cachegeheugen te wissen:

    ```
    Set-IRMConfiguration -RefreshServerCertificates
    ```

6.  Stel nu op elke Exchange-Server IIS opnieuw in, bijvoorbeeld door een opdrachtprompt als beheerder uit te voeren en **iisreset** te typen.

### IRM op SharePoint Servers uitschakelen en de AD RMS-configuratie verwijderen

1.  Zorg dat er zijn geen documenten zijn uitgecheckt uit met RMS beveiligde bibliotheken. Als er uitgecheckte documenten zijn, zijn deze na deze procedure niet meer toegankelijk.

2.  Ga naar de website Centraal beheer van SharePoint en klik in het gedeelte **Snel starten** op **Beveiliging**.

3.  Klik op de pagina **Beveiliging** in het gedeelte **Informatiebeleid** op **Information Rights Management configureren**.

4.  Selecteer op de pagina **Information Rights Management** in het gedeelte **Information Rights Management** de optie **IRM niet gebruiken op deze server** en klik vervolgens op **OK**.

5.  Verwijder op elk van de SharePoint Server-computers de inhoud van de map \ProgramData\Microsoft\MSIPC\Server\*&lt;SID van het account waarop SharePoint Server&gt;* wordt uitgevoerd.

#### De RMS-connector installeren en configureren

-   Volg de instructies in het artikel [Azure Rights Management-connector implementeren](../deploy-use/deploy-rms-connector.md).

#### Alleen voor Exchange en meerdere TPD’s: het register bewerken

-   Op elke Exchange Server moet u handmatig de volgende registersleutels toevoegen voor elk extra TPD dat u hebt geïmporteerd, om de URL's van de TPD’s om te leiden naar de RMS-connector. Deze registervermeldingen zijn specifiek bedoeld voor migratie en worden niet toegevoegd door het hulpprogramma voor serverconfiguratie voor de Microsoft RMS-connector.

    Wanneer u deze wijzigingen in het register aanbrengt, gebruikt u de volgende instructies:

    -   Vervang *ConnectorFQDN* door de naam die u voor deze connector hebt opgegeven in DNS. Bijvoorbeeld **rmsconnector.contoso.com**.

    -   Gebruik het voorvoegsel HTTP of HTTPS voor de connector-URL, afhankelijk van het feit of u de connector hebt geconfigureerd om te communiceren met uw on-premises servers via HTTP of HTTPS.

Voor Exchange 2013: registerbewerking 1:


**Registerpad:**

HKLM\SOFTWARE\Microsoft\ExchangeServer\v15\IRM\LicenseServerRedirection

**Type:**

Reg_SZ

**Waarde:**

https://<AD RMS Intranet Licensing URL>/_wmcs/licensing

**Gegevens:**

Een van de volgende, afhankelijk van het feit of u HTTP of HTTPS gebruikt van uw Exchange Server naar de RMS-connector:

- http://<connectorFQDN>/_wmcs/licensing

- https://<connectorName>/_wmcs/licensing


---

Voor Exchange 2013: registerbewerking 2:

**Registerpad:**

HKLM\SOFTWARE\Microsoft\ExchangeServer\v15\IRM\LicenseServerRedirection 


**Type:**

Reg_SZ

**Waarde:**

https://<AD RMS Extranet Licensing URL>/_wmcs/licensing


**Gegevens:**

Een van de volgende, afhankelijk van het feit of u HTTP of HTTPS gebruikt van uw Exchange Server naar de RMS-connector:

- http://<connectorFQDN>/_wmcs/licensing

- https://<connectorFQDN>/_wmcs/licensing

---

Voor Exchange 2010: registerbewerking 1:



**Registerpad:**

HKLM\SOFTWARE\Microsoft\ExchangeServer\v14\IRM\LicenseServerRedirection

**Type:**

Reg_SZ

**Waarde:**

https://<AD RMS Intranet Licensing URL>/_wmcs/licensing

**Gegevens:**

Een van de volgende, afhankelijk van het feit of u HTTP of HTTPS gebruikt van uw Exchange Server naar de RMS-connector:

- http://<connectorFQDN>/_wmcs/licensing

- https://<connectorName>/_wmcs/licensing


---

Voor Exchange 2010: registerbewerking 2:


**Registerpad:**

HKLM\SOFTWARE\Microsoft\ExchangeServer\v14\IRM\LicenseServerRedirection
 

**Type:**

Reg_SZ

**Waarde:**

https://<AD RMS Extranet Licensing URL>/_wmcs/licensing


**Gegevens:**

Een van de volgende, afhankelijk van het feit of u HTTP of HTTPS gebruikt van uw Exchange Server naar de RMS-connector:

- http://<connectorFQDN>/_wmcs/licensing

- https://<connectorFQDN>/_wmcs/licensing

---

Nadat u deze procedures hebt voltooid, leest u het gedeelte **Volgende stappen** van het artikel [De Azure Rights Management-connector implementeren](../deploy-use/deploy-rms-connector.md).

## Volgende stappen
Als u wilt doorgaan met de migratie, gaat u naar [Stap 4: taken na migratie](migrate-from-ad-rms-phase4.md).


<!--HONumber=Jul16_HO2-->


