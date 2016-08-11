---
title: 'Instructies: documenttracking en intrekking van documenten inschakelen | Azure RMS'
description: Algemene richtlijnen voor de implementatie van het bijhouden van documenten
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: F5089765-9D94-452B-85E0-00D22675D847
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
experiment_id: priyamo-test-20160729
translationtype: Human Translation
ms.sourcegitcommit: fe167a6bb22c4d07847ed1bbf390dd19aaada23a
ms.openlocfilehash: d3b343b8c1b28c47bb76171e032e9fffca3844c9


---

# Instructies: het bijhouden en intrekken van documenten inschakelen

Dit onderwerp bevat de algemene richtlijnen voor de implementatie van documenttracking voor inhoud, evenals voorbeeldcode voor updates van metagegevens en voor het maken van een [**knop Gebruik bijhouden**](#add-a-track-usage-button-to-your-app) voor uw app.

## Stappen voor het implementeren van documenttracking

Met stap 1 en 2 schakelt u het document in dat u wilt bijhouden. Met stap 3 kunnen uw app-gebruikers de site voor documenttracking bereiken zodat ze de beveiligde documenten kunnen bijhouden en intrekken.

1. Voeg metagegevens voor documenttracking toe
2. Registreer het document bij de RMS-service
3. Voeg de knop Gebruik bijhouden toe aan uw app

Hieronder vindt u de implementatiedetails voor deze stappen.

## 1. Voeg metagegevens voor documenttracking toe

Het bijhouden van documenten is een functie van Rights Management. Door specifieke metagegevens toe te voegen tijdens het beveiligingsproces, kan een document worden geregistreerd bij de serviceportal voor tracering. Vervolgens beschikt u over verschillende opties om het document bij te houden.

Gebruik deze API's om een inhoudslicentie met metagegevens voor het bijhouden van documenten toe te voegen/bij te werken.


Operationeel gezien zijn voor documenttracking alleen de eigenschappen **Naam inhoud** en **Meldingstype** vereist.


- [IpcCreateLicenseMetadataHandle](/rights-management/sdk/2.1/api/win/functions#msipc_ipccreatelicensemetadatahandle)
- [IpcSetLicenseMetadataProperty](/rights-management/sdk/2.1/api/win/functions#msipc_ipcsetlicensemetadataproperty)

  We verwachten dat u alle eigenschappen voor metagegevens instelt. Deze eigenschappen staan hieronder vermeld, gerangschikt op type.

  Zie [License metadata property types](/rights-management/sdk/2.1/api/win/constants#msipc_license_metadata_property_types) (Typen eigenschappen voor licentiemetagegevens) voor meer informatie.

  - **IPC_MD_CONTENT_PATH**

    Gebruik dit om het bijgehouden document te identificeren. Als een volledig pad niet mogelijk is, geeft u alleen de bestandsnaam op.

  - **IPC_MD_CONTENT_NAME**

    Gebruik dit om de naam van het bijgehouden document te identificeren.

  - **IPC_MD_NOTIFICATION_TYPE**

    Gebruik dit om op te geven wanneer een melding wordt verzonden. Zie Notification type (Meldingstype) voor meer informatie.

  - **IPC_MD_NOTIFICATION_PREFERENCE**

    Gebruik dit om het type melding op te geven. Zie Notification preference (Meldingsvoorkeuren) voor meer informatie.

  - **IPC_MD_DATE_MODIFIED**

    Het wordt aangeraden dat u deze datum telkens instelt wanneer de gebruiker op Opslaan klikt.

  - **IPC_MD_DATE_CREATED**

    Gebruik dit voor het instellen van de oorspronkelijke datum van het bestand

- [IpcSerializeLicenseWithMetadata](/rights-management/sdk/2.1/api/win/functions#msipc_ipcserializelicensemetadata)

Gebruik een van deze API's om de metagegevens toe te voegen aan uw bestand of stroom.

- [IpcfEncryptFileWithMetadata](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfencryptfilewithmetadata)
- [IpcfEncryptFileStreamWithMetadata](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfencryptfilestreamwithmetadata)

Gebruik ten slotte deze API om uw bijgehouden document te registreren bij het traceersysteem.

- [IpcRegisterLicense](/rights-management/sdk/2.1/api/win/functions#msipc_ipcregisterlicense)


## 2. Registreer het document bij de RMS-service

Hier volgt een codefragment met een voorbeeld van het instellen van de metagegevens voor het bijhouden van documenten en de aanroep voor registratie bij het traceersysteem.

      C++
      HRESULT hr = S_OK;
      LPCWSTR wszOutputFile = NULL;
      wstring wszWorkingFile;
      IPC_LICENSE_METADATA md = {0};

      md.cbSize = sizeof(IPC_LICENSE_METADATA);
      md.dwNotificationType = IPCD_CT_NOTIFICATION_TYPE_ENABLED;
      md.dwNotificationPreference = IPCD_CT_NOTIFICATION_PREF_DIGEST;
      //file origination date, current time for this example
      md.ftDateCreated = GetCurrentTime();
      md.ftDateModified = GetCurrentTime();

      LOGSTATUS_EX(L"Encrypt file with official template...");

      hr =IpcfEncryptFileWithMetadata( wszWorkingFile.c_str(),
                               m_wszTestTemplateID.c_str(),
                               IPCF_EF_TEMPLATE_ID,
                               0,
                               NULL,
                               NULL,
                               &md,
                               &wszOutputFile);

     /* This will contain the serialized license */
     PIPC_BUFFER pSerializedLicense;

     /* the context to use for the call */
     PCIPC_PROMPT_CTX pContext;

     wstring wstrContentName(“MyDocument.txt”);
     bool sendLicenseRegistrationNotificationEmail = FALSE;

     hr = IpcRegisterLicense( pSerializedLicense,
                        0,
                        pContext,
                        wstrContentName.c_str(),
                        sendLicenseRegistrationNotificationEmail);

## Voeg een knop **Gebruik bijhouden** toe aan uw app

Het toevoegen van een UI-item **Gebruik bijhouden** is net zo eenvoudig als het gebruik van een van de volgende URL-indelingen:

- Inhoud-id gebruiken
  - Haal de inhoud-id op met [IpcGetLicenseProperty](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgetlicenseproperty) of [IpcGetSerializedLicenseProperty](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgetserializedlicenseproperty) als de licentie is geserialiseerd en gebruik de licentie-eigenschap **IPC_LI_CONTENT_ID**. Zie [License property types](/rights-management/sdk/2.1/api/win/constants#msipc_license_property_types) (Typen licentie-eigenschappen) voor meer informatie.
  - Gebruik voor de metagegevens **ContentId** en **Issuer** de volgende notatie: `https://track.azurerms.com/#/{ContentId}/{Issuer}`

    Voorbeeld: `https://track.azurerms.com/#/summary/05405df5-8ad6-4905-9f15-fc2ecbd8d0f7/janedoe@microsoft.com`

- Als u geen toegang hebt tot metagegevens (u wilt de niet-beveiligde versie van het document controleren), kunt u **Content_Name** gebruiken in de volgende notatie: `https://track.azurerms.com/#/?q={ContentName}`

  Voorbeeld: https://track.azurerms.com/#/?q=Secret!.txt

De client moet een browser openen met de juiste URL. Verificatie en eventuele omleiding worden uitgevoerd in de RMS-portal voor documenttracking.

## Verwante onderwerpen

* [Typen eigenschappen voor licentiemetagegevens](/rights-management/sdk/2.1/api/win/constants#msipc_license_metadata_property_types)
* [Meldingsvoorkeur](/rights-management/sdk/2.1/api/win/constants#msipc_notification_preference)
* [Type melding](/rights-management/sdk/2.1/api/win/constants#msipc_notification_type)
* [IpcCreateLicenseMetadataHandle](/rights-management/sdk/2.1/api/win/functions#msipc_ipccreatelicensemetadatahandle)
* [IpcSetLicenseMetadataProperty](/rights-management/sdk/2.1/api/win/functions#msipc_ipcsetlicensemetadataproperty)
* [IpcSerializeLicenseWithMetadata](/rights-management/sdk/2.1/api/win/functions#msipc_ipcserializelicensemetadata)
* [IpcfEncryptFileWithMetadata](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfencryptfilewithmetadata)
* [IpcfEncryptFileStreamWithMetadata](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfencryptfilestreamwithmetadata)
* [IpcRegisterLicense](/rights-management/sdk/2.1/api/win/functions#msipc_ipcregisterlicense)

 



<!--HONumber=Jul16_HO5-->


