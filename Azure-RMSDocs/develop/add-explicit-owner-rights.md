---
# required metadata

title: Expliciete eigendomsrechten toevoegen | Azure RMS
description: Uw toepassing moet expliciet 'Eigenaar'-rechten toevoegen bij het maken van een nieuwe licentie.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: EF43FAC4-ABB4-459D-B173-972B5716F816
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
** Deze SDK-inhoud is niet actueel. U kunt tijdelijk de [huidige versie](https://msdn.microsoft.com/library/windows/desktop/hh535290(v=vs.85).aspx) van de documentatie op MSDN vinden. **
# Expliciete eigendomsrechten toevoegen

Uw toepassing moet expliciet 'Eigenaar'-rechten toevoegen bij het maken van een nieuwe licentie ([**IpcCreateLicenseFromScratch**](/rights-management/sdk/2.1/api/win/functions#msipc_ipccreatelicensefromscratch)).

## Vereisten

Wanneer uw toepassing een licentie maakt met behulp van [**IpcCreateLicenseFromScratch**](/rights-management/sdk/2.1/api/win/functions#msipc_ipccreatelicensefromscratch), moet deze ook expliciet de eigenaar volledige rechten (machtigingen) toekennen.

**Opmerking** Als een gebruiker als 'eigenaar' wordt ingesteld met [**IpcSetLicenseProperty**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcsetlicenseproperty) met de eigenschap **IPC\_LI\_OWNER**, worden aan de eigenaar geen volledige machtigingen verleend.

 
## Scenario: rechten aan een licentie toewijzen

In dit C++-voorbeeld worden de benodigde rechten toegevoegd aan een licentie gemaakt met [**IpcCreateLicenseFromScratch**](/rights-management/sdk/2.1/api/win/functions#msipc_ipccreatelicensefromscratch). Het voorbeeld toont het maken van rechten en het toewijzen hiervan aan de licentie via een lijst met rechten.

Aan deze gebruikers worden de volgende twee rechten toegewezen:

-   *Lees*machtigingen worden toegewezen aan joe@contoso.com.
-   *Volledige* machtigingen worden toegewezen aan mary\_kay@contoso.com.

**OPMERKING**: dit codevoorbeeld bevat alleen de stappen die betrekking hebben op het maken van specifieke rechten en het toewijzen hiervan aan een bepaalde licentie.

    // Create User Rights structure
    IPC_USER_RIGHTS ownerRightForOwner = {0};

    // Create rights
    LPCWSTR rgwszOwnerRights[1] = {IPC_GENERIC_ALL};

    // Assign values to members of Rights structure
    ownerRightForOwner.User.dwType = IPC_USER_TYPE_IPC;
    ownerRightForOwner.User.wszID = IPC_USER_ID_OWNER;
    ownerRightForOwner.rgwszRights = rgwszOwnerRights;
    ownerRightForOwner.cRights = 1;

    // Create User Rights structure for Joe with Read permissions
    IPC_USER_RIGHTS joeReadRight = {0};
    LPCWSTR rgwszReadRights[1] = {IPC_GENERIC_READ};

    // Assign values to members of Rights structure for Joe
    joeReadRight.User.dwType = IPC_USER_TYPE_EMAIL;
    joeReadRight.User.wszID = "joe@contoso.com";
    joeReadRight.rgwszRights = rgwszReadRights;
    joeReadRight.cRights = 1;

    // Create User Rights structure for Mary Kay with Full permissions
    IPC_USER_RIGHTS mary_kayFullRight = {0};
    LPCWSTR rgwszFullRights[1] = {IPC_GENERIC_ALL};

    // Assign values to members of Rights structure for Mary Kay
    mary_kayFullRight.User.dwType = IPC_USER_TYPE_EMAIL;
    mary_kayFullRight.User.wszID = L"mary_kay@contoso.com";
    mary_kayFullRight.rgwszRights = rgwszFullRights;
    mary_kayFullRight.cRights = 1;

    // Create User Rights List and assign the above rights
    size_t uNoOfUserRights = 3;
    PIPC_USER_RIGHTS_LIST pUserRightsList = NULL;
    pUserRightsList = reinterpret_cast<PIPC_USER_RIGHTS_LIST>
    (new BYTE[ sizeof(IPC_USER_RIGHTS_LIST) + uNoOfUserRights * sizeof(IPC_USER_RIGHTS)]);

    if(pUserRightsList == NULL)
    {
      // Handle error
    }

    // Assign values to members of Rights List structure for Joe and Mary Kay
    (*pUserRightsList).cbSize = sizeof(IPC_USER_RIGHTS_LIST);
    (*pUserRightsList).cUserRights = uNoOfUserRights;
    (*pUserRightsList).rgUserRights[0] = ownerRightForOwner;
    (*pUserRightsList).rgUserRights[1] = joeReadRight;
    (*pUserRightsList).rgUserRights[2] = mary_kayFullRight;

    // Set the Rights List property on the license via its handle
    // hLicense is a license handle created with IpcCreateLicenseFromScratch
    hr = IpcSetLicenseProperty(hLicense, FALSE, IPC_LI_USER_RIGHTS_LIST, pUserRightsList);

    if(FAILED(hr))
    {
      // Handle the error
    }



## Verwante onderwerpen

* [Opmerkingen voor ontwikkelaars](developer-notes.md)
* [**IpcCreateLicenseFromScratch**](/rights-management/sdk/2.1/api/win/functions#msipc_ipccreatelicensefromscratch)
* [**IpcSetLicenseProperty**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcsetlicenseproperty)
 

 


<!--HONumber=Jun16_HO1-->


