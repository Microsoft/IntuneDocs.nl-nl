---
# required metadata

title: "Procedure: een Azure-toepassings-id ophalen | Azure RMS"
description: Als u een app met RMS-compatibiliteit wilt maken met Microsoft Rights Management SDK 4.2, moet u een overeenkomst met het RMS-team aangaan.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 0fe9dc-bc91-4018-b28d-2db293a3eaa2
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Procedure: Een Azure-toepassings-id ophalen

Als u een app met RMS-compatibiliteit wilt maken met Microsoft Rights Management SDK 4.2, moet u een overeenkomst met het RMS-team aangaan.

## Overzicht

Als u een app met RMS wilt maken en vrijgeven met behulp van MS RMS SDK 4.2, moet u ook een overeenkomst voor het gebruik van services aangaan met het RMS-team. Met deze overeenkomst, ook wel bekend als een Rights Management License Agreement (RMLA), kunt u namens de gebruiker en/of de inhoudseigenaar het contract voor inhoudsbeveiliging naleven middels het gedrag (inachtneming van bedrijfsregels) van uw app. Als maker van een app met RMS wordt uw servicecontract met het RMS-team afgedwongen door het bestaan van een Azure toepassings-id die deze overeenkomst vertegenwoordigt en waarmee uw app verbinding kan maken met de Azure AD-verificatieservice.

## Proces

Gebruik de volgende stappen om uw app-id te maken en de gebruiksovereenkomst met het RMS-team te ondertekenen.

-   Volg de instructies in het onderwerp [How to create an App ID on Azure](https://msdn.microsoft.com/en-us/library/azure/dn132599.aspx) (Een app-id op Azure maken) om uw app-id te maken.
-   Schrijf een bericht naar het RMS-team om uw RMLA-procedure te starten, en verzend hierbij uw app-id naar <askipteam@microsoft.com>.
-   Onderteken de RMLA en stuur deze terug naar het RMS-team.
-   Nu u een ondertekende RMLA hebt, moet u de toepassings-id doorgeven bij het aanroepen van de verificatiebibliotheek via de parameter *clientID*.

    Zo ziet de verificatieaanroep eruit in ons onderwerp [Voorbeelden van iOS- en OS X-code](ios-os-x-code-examples.md).


    // Token ophalen met behulp van ADAL
        [context acquireTokenWithResource:authenticationParameters.resource
                                 clientId:appClientId
                              redirectUri:redirectURI
                                   userId:authenticationParameters.userId
                          completionBlock:^(ADAuthenticationResult *result)



**Opmerking** als het RMS-team uw ondertekende RMLA niet binnen zestig dagen ontvangt, wordt uw app uitgesloten van verificatie met het Azure-verificatiesysteem.

 

 

 


<!--HONumber=Apr16_HO4-->


