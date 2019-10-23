---
title: Problemen met Microsoft Intune Certificate Connector en gebeurtenis-id's oplossen | Microsoft Docs
titleSuffix: Microsoft Intune
description: Los problemen met Microsoft Intune Certificate Connector op door gebeurtenis-id's en beschrijvingen te controleren en controleer diagnostische codes voor de Intune-connectorservice.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/01/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2d9556cc0357e76ee617ac0770a3efc2e3a1957f
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72508883"
---
# <a name="intune-certificate-connector-events-and-diagnostic-codes"></a>Gebeurtenissen en diagnostische codes van Intune Certificate Connector

Vanaf versie 6.1806.x.x legt de Intune-connectorservice gebeurtenissen vast in de **Logboeken** (**Logboeken voor toepassingen en services** > **Microsoft Intune-connector**). Gebruik deze gebeurtenissen om potentiële problemen in de configuratie van de Intune-connector op te lossen. Deze gebeurtenissen leggen de successen en mislukkingen van een bewerking vast, en bevatten ook diagnostische codes met berichten zodat de IT-beheerder problemen kan oplossen.

> [!TIP]  
> Zie [Scriptvoorbeelden certificeringsinstantie](https://aka.ms/intuneconnectorverificationscript) om problemen op te lossen en de configuratie van de Intune-connector te controleren.

## <a name="event-ids-and-descriptions"></a>Gebeurtenis-id's en beschrijvingen

| Gebeurtenis-id      | Gebeurtenisnaam    | Gebeurtenisbeschrijving | Verwante diagnostische codes |
| ------------- | ------------- | -------------     | -------------            |
| 10010 | StartedConnectorService  | Connectorservice gestart | 0x00000000, 0x0FFFFFFF |
| 10020 | StoppedConnectorService  | Connectorservice gestopt | 0x00000000, 0x0FFFFFFF |
| 10100 | CertificateRenewal_Success  | Connector-inschrijvingscertificaat vernieuwd | 0x00000000, 0x0FFFFFFF |
| 10102 | CertificateRenewal_Failure  | Connector-inschrijvingscertificaat niet vernieuwd. Installeer de connector opnieuw. | 0x00000000, 0x00000405, 0x0FFFFFFF |
| 10302 | RetrieveCertificate_Error  | Ophalen van het connector-inschrijvingscertificaat uit het register is mislukt. Bekijk de gebeurtenisdetails voor de vingerafdruk van het certificaat die betrekking heeft op deze gebeurtenis. | 0x00000000, 0x00000404, 0x0FFFFFFF |
| 10301 | RetrieveCertificate_Warning  | Controleer de diagnostische gegevens in de details van gebeurtenis. | 0x00000000, 0x00000403, 0x0FFFFFFF |
| 20100 | PkcsCertIssue_Success  | Een PKCS-certificaat is uitgegeven. Bekijk de gebeurtenisdetails voor de apparaat-id, de gebruikers-id, CA-naam, certificaatsjabloonnaam en certificaatvingerafdruk die betrekking hebben op deze gebeurtenis. | 0x00000000, 0x0FFFFFFF |
| 20102 | PkcsCertIssue_Failure  | Uitgifte van een PKCS-certificaat is mislukt. Bekijk de gebeurtenisdetails voor de apparaat-id, gebruikers-id, CA-naam, certificaatsjabloonnaam en certificaatvingerafdruk die betrekking hebben op deze gebeurtenis. | 0x00000000, 0x00000400, 0x00000401, 0x0FFFFFFF |
| 20200 | RevokeCert_Success  | Het certificaat is ingetrokken. Bekijk de gebeurtenisdetails voor de apparaat-id, gebruikers-id, CA-naam en certificaatserienummer die betrekking hebben op deze gebeurtenis. | 0x00000000, 0x0FFFFFFF |
| 20202 | RevokeCert_Failure | Kan het certificaat niet verwijderen. Bekijk de gebeurtenisdetails voor de apparaat-id, gebruikers-id, CA-naam en certificaatserienummer die betrekking hebben op deze gebeurtenis. Zie de NDES SVC-logboeken voor meer informatie.   | 0x00000000, 0x00000402, 0x0FFFFFFF |
| 20300 | Upload_Success | De aanvraag- of intrekkingsgegevens van het certificaat zijn geüpload. Bekijk de gebeurtenisdetails voor de uploaddetails. | 0x00000000, 0x0FFFFFFF |
| 20302 | Upload_Failure | De aanvraag- of intrekkingsgegevens van het certificaat zijn niet geüpload. Bekijk de gebeurtenisdetails > Uploadstatus om de fout te bepalen.| 0x00000000, 0x0FFFFFFF |
| 20400 | Download_Success | Aanvraag om een certificaat te ondertekenen, een clientcertificaat te downloaden of een certificaat in te trekken, is gedownload. Bekijk de gebeurtenisdetails voor de downloaddetails.  | 0x00000000, 0x0FFFFFFF |
| 20402 | Download_Failure | Aanvraag om een certificaat te ondertekenen, een clientcertificaat te downloaden of een certificaat in te trekken, is niet gedownload. Bekijk de gebeurtenisdetails voor de downloaddetails. | 0x00000000, 0x0FFFFFFF |
| 20500 | CRPVerifyMetric_Success  | Certificaatregistratiepunt heeft een clientverificatievraag geverifieerd | 0x00000000, 0x0FFFFFFF |
| 20501 | CRPVerifyMetric_Warning  | Certificaatregistratiepunt heeft de aanvraag voltooid maar geweigerd. Zie de diagnostische code en het bericht voor meer informatie. | 0x00000000, 0x00000411, 0x0FFFFFFF |
| 20502 | CRPVerifyMetric_Failure  | Certificaatregistratiepunt heeft een clientverificatievraag niet geverifieerd. Zie de diagnostische code en het bericht voor meer informatie. Zie de details van het gebeurtenisbericht voor de apparaat-id die overeenkomt met de verificatievraag. | 0x00000000, 0x00000408, 0x00000409, 0x00000410, 0x0FFFFFFF |
| 20600 | CRPNotifyMetric_Success  | Certificaatregistratiepunt heeft de procesmelding voltooid en heeft het certificaat verzonden naar het clientapparaat. | 0x00000000, 0x0FFFFFFF |
| 20602 | CRPNotifyMetric_Failure  | Certificaatregistratiepunt heeft de procesmelding niet voltooid. Zie de details van het gebeurtenisbericht voor meer informatie over de aanvraag. Controleer de verbinding tussen de NDES-server en de CA. | 0x00000000, 0x0FFFFFFF |

## <a name="diagnostic-codes"></a>Diagnostische codes

| Diagnostische code | Naam diagnostische test | Diagnostisch bericht |
| -------------   | -------------   | -------------      |
| 0x00000000 | Geslaagd  | Geslaagd |
| 0x00000400 | PKCS_Issue_CA_Unavailable  | Certificeringsinstantie is niet geldig of is niet bereikbaar. Controleer of de certificeringsinstantie beschikbaar is en of uw server ermee kan communiceren. |
| 0x00000401 | Symantec_ClientAuthCertNotFound  | Client-Auth Symantec-certificaat is niet gevonden in het lokale certificaatarchief. Zie het artikel [Het Symantec-certificaat voor registratie-autorisatie installeren](certificates-digicert-configure.md#install-the-digicert-ra-certificate) voor meer informatie.  |
| 0x00000402 | RevokeCert_AccessDenied  | Het opgegeven account heeft geen machtigingen om een certificaat van CA in te trekken. Zie het veld CA-naam in de berichtdetails van de gebeurtenis om de verlenende CA te bepalen.  |
| 0x00000403 | CertThumbprint_NotFound  | Kan geen certificaat vinden dat overeenkomt met uw invoer. Registreer de certificaatconnector en probeer het opnieuw. |
| 0x00000404 | Certificate_NotFound  | Kan geen certificaat vinden dat overeenkomt met de opgegeven invoer. Registreer de certificaatconnector nogmaals en probeer het opnieuw. |
| 0x00000405 | Certificate_Expired  | Een certificaat is verlopen. Registreer de certificaatconnector nogmaals om het certificaat te vernieuwen en probeer het opnieuw. |
| 0x00000408 | CRPSCEPCert_NotFound  | CRP-versleutelingscertificaat kan niet worden gevonden. Controleer of NDES en de Intune-connector correct zijn ingesteld. |
| 0x00000409 | CRPSCEPSigningCert_NotFound  | Handtekeningcertificaat kan niet worden opgehaald. Controleer of de Intune-connectorservice correct is geconfigureerd en of de Intune-connectorservice wordt uitgevoerd. Controleer ook of de downloadgebeurtenissen voor het certificaat zijn gelukt. |
| 0x00000410 | CRPSCEPDeserialize_Failed  | Het deserialiseren van de SCEP-verificatie-aanvraag is mislukt. Controleer of NDES en de Intune-connector correct zijn ingesteld. |
| 0x00000411 | CRPSCEPChallenge_Expired  | De aanvraag is geweigerd vanwege een verlopen certificaatverificatievraag. Het clientapparaat kan het opnieuw proberen nadat een nieuwe verificatievraag van de beheerserver is verkregen. |
| 0x0FFFFFFFF | Unknown_Error  | Uw aanvraag kan niet worden voltooid omdat aan serverzijde een fout is opgetreden. Probeer het opnieuw. |


## <a name="next-steps"></a>Volgende stappen
Gebruik de handleiding [Problemen oplossen met de implementatie van het SCEP-certificaatprofiel in Microsoft Intune](https://support.microsoft.com/help/4457481/troubleshooting-scep-certificate-profile-deployment-in-intune) voor meer hulp.
