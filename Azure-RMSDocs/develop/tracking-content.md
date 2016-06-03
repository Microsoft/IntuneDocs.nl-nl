---
# required metadata

title: Inhoud bijhouden | Azure RMS
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
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Inhoud bijhouden

Dit onderwerp bevat algemene richtlijnen voor de implementatie van het bijhouden van inhoud die is beveiligd met Rights Management Services SDK 2.1.

Het bijhouden van documenten is een functie van Rights Management. Door specifieke metagegevens toe te voegen tijdens het beveiligingsproces, kan een document worden geregistreerd bij de serviceportal voor tracering. Vervolgens beschikt u over verschillende opties om het document bij te houden.

Gebruik deze API's om een inhoudslicentie met metagegevens voor het bijhouden van documenten toe te voegen/bij te werken.

-   [**IpcCreateLicenseMetadataHandle**](/rights-management/sdk/2.1/api/win/functions#msipc_ipccreatelicensemetadatahandle)
-   [**IpcSetLicenseMetadataProperty**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcsetlicensemetadataproperty)

    We verwachten dat u alle eigenschappen voor metagegevens instelt. Deze eigenschappen staan hieronder vermeld, gerangschikt op type.

    Zie [**Typen eigenschappen voor licentiemetagegevens**](/rights-management/sdk/2.1/api/win/license%20metadata%20property%20types#msipc_license_metadata_property_types) voor meer informatie.

    -   **IPC\_MD\_CONTENT\_PATH**

        Gebruik dit om het bijgehouden document te identificeren. Als een volledig pad niet mogelijk is, geeft u alleen de bestandsnaam op.

    -   **IPC\_MD\_CONTENT\_NAME**

        Gebruik dit om de naam van het bijgehouden document te identificeren.

    -   **IPC\_MD\_NOTIFICATION\_TYPE**

        Gebruik dit om op te geven wanneer een melding wordt verzonden. Zie [**Type melding**](/rights-management/sdk/2.1/api/win/notification%20type#msipc_notification_type) voor meer informatie.

    -   **IPC\_MD\_NOTIFICATION\_PREFERENCE**

        Gebruik dit om het type melding op te geven. Zie [**Meldingsvoorkeuren**](/rights-management/sdk/2.1/api/win/constants#msipc_notification_preference) voor meer informatie.

    -   **IPC\_MD\_DATE\_MODIFIED**

        We raden aan dat u deze datum instelt telkens wanneer de gebruiker op **Opslaan** klikt.

    -   **IPC\_MD\_DATE\_CREATED**

        De oorspronkelijke datum van het bestand.

-   [**IpcSerializeLicenseWithMetadata**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcserializelicensemetadata)

Gebruik een van deze API's om de metagegevens toe te voegen aan uw bestand of stroom.

-   [**IpcfEncryptFileWithMetadata**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfencryptfilewithmetadata)
-   [**IpcfEncryptFileStreamWithMetadata**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfencryptfilestreamwithmetadata)

Gebruik ten slotte deze API om uw bijgehouden document te registreren bij het traceersysteem.

-   [**IpcRegisterLicense**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcregisterlicense)

Hier volgt een codefragment met een voorbeeld van het instellen van de metagegevens voor het bijhouden van documenten en de aanroep voor registratie bij het traceersysteem.



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

    LOGSTATUS_EX(L&quot;Encrypt file with official template...&quot;);

    hr =IpcfEncryptFileWithMetadata(  wszWorkingFile.c_str(),
                                       m_wszTestTemplateID.c_str(),
                                       IPCF_EF_TEMPLATE_ID,
                                       0,
                                       NULL,
                                       NULL,
                                       &amp;md,
                                       &amp;wszOutputFile);

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


## Verwante onderwerpen


* [**Typen eigenschappen voor licentiemetagegevens**](/rights-management/sdk/2.1/api/win/license%20metadata%20property%20types#msipc_license_metadata_property_types)
* [**Meldingsvoorkeur**](/rights-management/sdk/2.1/api/win/constants#msipc_notification_preference)
* [**Type melding**](/rights-management/sdk/2.1/api/win/notification%20type#msipc_notification_type)
* [**IpcCreateLicenseMetadataHandle**](/rights-management/sdk/2.1/api/win/functions#msipc_ipccreatelicensemetadatahandle)
* [**IpcSetLicenseMetadataProperty**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcsetlicensemetadataproperty)
* [**IpcSerializeLicenseWithMetadata**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcserializelicensemetadata)
* [**IpcfEncryptFileWithMetadata**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfencryptfilewithmetadata)
* [**IpcfEncryptFileStreamWithMetadata**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfencryptfilestreamwithmetadata)
* [**IpcRegisterLicense**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcregisterlicense)
 

 


<!--HONumber=May16_HO2-->


