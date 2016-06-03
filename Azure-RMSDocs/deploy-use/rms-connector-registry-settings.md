---
# required metadata

title: Registerinstellingen voor de RMS-connector | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: ed3e9a3d-0f7c-4abc-9d0b-aa3b18403d39

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Registerinstelling voor de Rights Management-connector

*Van toepassing op: Azure Rights Management, Office 365*


Gebruik de tabellen in de volgende secties alleen als u handmatig registerinstellingen wilt toevoegen of controleren op de servers met Exchange, SharePoint of Windows Server, waardoor u de servers configureert voor gebruik van de [RMS-connector](deploy-rms-connector.md). Voor de configuratie van deze servers wordt aanbevolen om het hulpprogramma voor serverconfiguratie voor Microsoft RMS-connector te gebruiken.

Instructies voor het gebruik van deze instellingen:

-   *MicrosoftRMSURL* is de Microsoft RMS-service-URL van uw organisatie. Deze waarde zoeken:

    1.  Voer de cmdlet [Get-AadrmConfiguration](http://msdn.microsoft.com/library/windowsazure/dn629410.aspx) voor Azure RMS uit. Zie [Windows PowerShell voor Azure Rights Management installeren](install-powershell.md) als u de Windows PowerShell-module voor Azure RMS nog niet hebt geïnstalleerd..

    2.  Identificeer op grond van de uitvoer de waarde van **LicensingIntranetDistributionPointUrl**.

        Bijvoorbeeld: **LicensingIntranetDistributionPointUrl: https://5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com/_wmcs/licensing**

    3.  Verwijder in de waarde **/_wmcs/licensing** uit deze tekenreeks. De resterende tekenreeks is de URL voor Microsoft RMS. In ons voorbeeld zou de Microsoft RMS-URL de volgende waarde zijn:

        **https://5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com**

-   *ConnectorFQDN* is de naam van de taakverdeling die u voor deze connector hebt opgegeven in DNS. Bijvoorbeeld **rmsconnector.contoso.com**.

-   Gebruik het voorvoegsel HTTPS voor de connector-URL als u de connector hebt geconfigureerd om via HTTPS te communiceren met uw lokale servers. Zie voor meer informatie de sectie [De RMS-connector configureren voor gebruik van HTTPS](deploy-rms-connector.md#BKMK_ConfiguringHTTPS) in dit onderwerp. De Microsoft RMS-URL's maken altijd gebruik van HTTPS.


## Registerinstellingen voor Exchange 2016 of Exchange 2013

**Registerpad:** HKEY_LOCAL_MACHINE\Software\Microsoft\MSDRM\ServiceLocation\Activation

**Type:** REG_SZ

**Waarde:** standaard

**Gegevens:** https://*MicrosoftRMSURL*/_wmcs/certification

---

**Registerpad:** HKEY_LOCAL_MACHINE\Software\Microsoft\MSDRM\ServiceLocation\EnterprisePublishing

**Type:** REG_SZ

**Waarde:** standaard

**Gegevens:** https://*MicrosoftRMSURL*/_wmcs/Licensing

---

**Registerpad:** HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExchangeServer\v15\IRM\CertificationServerRedirection

**Type:** REG_SZ

**Waarde:** https://*MicrosoftRMSURL*


**Gegevens:** een van de volgende, afhankelijk van het feit of u HTTP of HTTPS gebruikt van uw Exchange-server naar de RMS-connector:

- http://*ConnectorFQDN*

- https://*ConnectorFQDN*

---

**Registerpad:** HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExchangeServer\v15\IRM\LicenseServerRedirection

**Type:** REG_SZ

**Waarde:** https://*MicrosoftRMSURL*


**Gegevens:** een van de volgende, afhankelijk van het feit of u HTTP of HTTPS gebruikt van uw Exchange-server naar de RMS-connector:

- http://*ConnectorFQDN*

- https://*ConnectorFQDN*


## Registerinstellingen voor Exchange 2010

**Registerpad:** HKEY_LOCAL_MACHINE\Software\Microsoft\MSDRM\ServiceLocation\Activation

**Type:** REG_SZ

**Waarde:** standaard

**Gegevens:** https://*MicrosoftRMSURL*/_wmcs/certification

---

**Registerpad:** HKEY_LOCAL_MACHINE\Software\Microsoft\MSDRM\ServiceLocation\EnterprisePublishing

**Type:** REG_SZ

**Waarde:** standaard

**Gegevens:** https://*MicrosoftRMSURL*/_wmcs/Licensing

---

**Registerpad:** HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExchangeServer\v14\IRM\CertificationServerRedirection

**Type:** REG_SZ

**Waarde:** https://*MicrosoftRMSURL*

**Gegevens:** een van de volgende, afhankelijk van het feit of u HTTP of HTTPS gebruikt van uw Exchange-server naar de RMS-connector:

- http://*ConnectorFQDN*

- https://*ConnectorFQDN*

---

**Registerpad:** HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ExchangeServer\v14\IRM\LicenseServerRedirection

**Type:** REG_SZ

**Waarde:** https://*MicrosoftRMSURL*

**Gegevens:** een van de volgende, afhankelijk van het feit of u HTTP of HTTPS gebruikt van uw Exchange-server naar de RMS-connector:

- http://*ConnectorFQDN*

- https://*ConnectorFQDN*


## Registerinstellingen voor SharePoint 2016 of SharePoint 2013

**Registerpad:** HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\LicensingRedirection

**Type:** REG_SZ

**Waarde:** https://*MicrosoftRMSURL*/_wmcs/licensing


**Gegevens:** een van de volgende, afhankelijk van het feit of u HTTP of HTTPS gebruikt van uw SharePoint-server naar de RMS-connector:

- http://*ConnectorFQDN*/_wmcs/licensing

- https://*ConnectorFQDN*/_wmcs/licensing

---

**Registerpad:** HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\EnterpriseCertification

**Type:** REG_SZ

**Waarde:** standaard

**Gegevens:** een van de volgende, afhankelijk van het feit of u HTTP of HTTPS gebruikt van uw SharePoint-server naar de RMS-connector:

- http://*ConnectorFQDN*/_wmcs/certification

- https://*ConnectorFQDN*/_wmcs/certification

---

**Registerpad:** HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\EnterprisePublishing

**Type:** REG_SZ

**Waarde:** standaard


**Gegevens:** een van de volgende, afhankelijk van het feit of u HTTP of HTTPS gebruikt van uw SharePoint-server naar de RMS-connector:

- http://*ConnectorFQDN*/_wmcs/licensing

- https://*ConnectorFQDN*/_wmcs/licensing




## Registerinstellingen voor Bestandsserver en Infrastructuur voor Bestandsclassificering

**Registerpad:** HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\ServiceLocation\EnterprisePublishing

**Type:** REG_SZ

**Waarde:** standaard

**Gegevens:** http://*ConnectorFQDN*/_wmcs/licensing

---

**Registerpad:** HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSDRM\ServiceLocation\Activation

**Type:** REG_SZ

**Waarde:** standaard

**Gegevens:** http://*ConnectorFQDN*/_wmcs/certification


Terug naar [De Azure Rights Management-connector implementeren](deploy-rms-connector.md)

<!--HONumber=Apr16_HO4-->


