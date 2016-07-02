---
title: Documenttracking gebruiken | Azure RMS
description: De documenttrackingfunctie vereist enig inzicht in het beheren van de gekoppelde metagegevens en registratie bij de service.
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 70E10936-7953-49B0-B0DC-A5E7C4772E60
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ca4982cc86d9c006486540055de7c165adca21da
ms.openlocfilehash: 9872317c2d5f5f56f28ed2683d7ebc9743041a37


---

# Procedure: documenttrackingsysteem gebruiken

Het gebruik van de documenttrackingfunctie vereist enig inzicht in het beheren van de gekoppelde metagegevens en registratie bij de service.

## Metagegevens van het documentvolgsysteem beheren

Voor elk besturingssysteem dat ondersteuning biedt voor documenttracking, gelden vergelijkbare implementaties. Deze omvatten een reeks eigenschappen (de metagegevens), een nieuwe parameter die moet worden toegevoegd aan de aanmaakmethoden voor gebruikersbeleid en een methode voor het registeren van het beleid dat u wilt volgen met de documenttrackingservice.

Operationeel gezien zijn voor documenttracking alleen de eigenschappen **Naam inhoud** en **Meldingstype** vereist.

De volgorde van de stappen die u moet volgen om documenttracking in te stellen voor inhoud, is als volgt:

-   Maak een object met **licentiemetagegevens**.

    Zie [**LicenseMetadata**](/rights-management/sdk/4.2/api/android/com.microsoft.rightsmanagement#msipcthin2_licensemetadata_interface_java) of [**MSLicenseMetadata**](/rights-management/sdk/4.2/api/iOS/mslicensemetadata#msipcthin2_mslicensemetadata_class_objc) voor meer informatie.

-   Stel **Naam inhoud** en **Meldingstype** in. Dit zijn de enige vereiste eigenschappen.

    Voor meer informatie ziet u de eigenschaptoegangsmethoden voor de klasse van licentiemetagegevens die past bij het platform: [**LicenseMetadata**](/rights-management/sdk/4.2/api/android/com.microsoft.rightsmanagement#msipcthin2_licensemetadata_interface_java) of [**MSLicenseMetadata**](/rights-management/sdk/4.2/api/iOS/mslicensemetadata#msipcthin2_mslicensemetadata_class_objc).

-   Op basis van beleidstype: sjabloon of ad hoc:

    -   Voor documenttracking op basis van een sjabloon maakt u een object voor **gebruikersbeleid**. Gebruik hierbij de metagegevens van de licentie als parameter.

        Voor meer informatie raadpleegt u [**UserPolicy.create**](/rights-management/sdk/4.2/api/android/userpolicy#msipcthin2_userpolicy_class_java) en [**MSUserPolicy.userPolicyWithTemplateDescriptor**](/rights-management/sdk/4.2/api/iOS/msuserpolicy#msipcthin2_msuserpolicy_templatedescriptor_property_objc).

    -   Voor ad-hocdocumenttracking stelt u de eigenschap **Licentiemetagegevens** in voor het object **Beleidsdescriptor**.

        Voor meer informatie raadpleegt u [**PolicyDescriptor.getLicenseMetadata**](/rights-management/sdk/4.2/api/android/policydescriptor#msipcthin2_policydescriptor_interface_java), [**PolicyDescriptor.setLicenseMetadata**](/rights-management/sdk/4.2/api/android/policydescriptor#msipcthin2_policydescriptor_setlicensemetadata_java) en [**MSPolicyDescriptor.licenseMetadata**](/rights-management/sdk/4.2/api/iOS/mspolicydescriptor#msipcthin2_mspolicydescriptor_licensemetadata_property_objc).

    **Opmerking** Het object met licentiemetagegevens kan alleen rechtstreeks worden geopend tijdens het instellen van documenttracking voor het opgegeven gebruikersbeleid. Nadat het gebruikersbeleidobject is gemaakt, kunnen de daaraan gekopppelde licentiemetagegevens niet meer worden geopend: het heeft dus geen effect als u de waarden van de licentiemetagegevens wijzigt.

     

-   Roep de platformregistratiemethode voor documenttracking aan.

    Zie [**MSUserPolicy.registerForDocTracking**](/rights-management/sdk/4.2/api/iOS/msuserpolicy#msipcthin2_msuserpolicy_registerfordoctracking_userid_authenticationcallback_completionblock_method_objc) of [**UserPolicy.registerForDocTracking**](/rights-management/sdk/4.2/api/iOS/msuserpolicy#msipcthin2_msuserpolicy_registerfordoctracking_userid_authenticationcallback_completionblock_method_objc).

 

 



<!--HONumber=Jun16_HO4-->


