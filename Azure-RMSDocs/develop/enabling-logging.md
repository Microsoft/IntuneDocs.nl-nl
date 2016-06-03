---
# required metadata

title: Procedure: fout- en prestatieregistratie inschakelen | Azure RMS
description: De Microsoft Rights Management SDK 4.2 beheert de upload van diagnose- en prestatielogboeken via één apparaateigenschap.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: F5AD3826-2292-4A25-AF5C-D17D083F5742
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Procedure: fout- en prestatieregistratie inschakelen
De Microsoft Rights Management SDK 4.2 beheert de upload van diagnose- en prestatielogboeken via één apparaateigenschap.

## Overzicht ##
U kunt de gebruikerservaring van uw gebruikers verbeteren en problemen oplossen door het uploaden van automatische diagnoses en prestatieregistratie naar Microsoft in te schakelen. Om de privacy van gebruikers te garanderen, moet u als de app-ontwikkelaar de gebruiker om toestemming vragen voordat u de automatische logboekregistratie inschakelt.

U beheert de logboekregistratie via twee eigenschappen.

-   Schakel logboekregistratie in via de eigenschap **IpcCustomerExperienceDataCollectionEnabled**. De instelling is permanent, ook als het apparaat opnieuw wordt ingesteld.
-   U beheert het registratieniveau via de eigenschap **IpcLogLevel** met de volgende instellingen.

    * 1 - Uitgebreid
    * 2 - Informatief
    * 3 - Waarschuwing
    * 4 - Fout
    * 5 - Kritiek

In elk van de volgende voorbeelden van codefragmenten kan de aanroepende toepassing de eigenschap instellen of opvragen.

### Android ###
Automatische logboekregistratie inschakelen

    SharedPreferences preferences = PreferenceManager.getDefaultSharedPreferences(context);
    SharedPreferences.Editor editor = preferences.edit();
    editor.putBoolean(&quot;IpcCustomerExperienceDataCollectionEnabled&quot;, true);
    editor.commit();

Instelling voor huidige logboekregistratievlag ophalen

    SharedPreferences preferences = PreferenceManager.getDefaultSharedPreferences(context);
    Boolean isLogUploadEnabled = preferences.getBoolean(&quot;IpcCustomerExperienceDataCollectionEnabled&quot;, false);

## iOS ##
Automatische logboekregistratie inschakelen

    NSUserDefaults \*prefs = [NSUserDefaults standardUserDefaults];
        [prefs setBool:FALSE forKey:@&quot;IpcCustomerExperienceDataCollectionEnabled”];
        [[NSUserDefaults standardUserDefaults] synchronize];

Instelling voor huidige logboekregistratievlag ophalen

    [[NSUserDefaults standardUserDefaults] boolForKey:@&quot;IpcCustomerExperienceDataCollectionEnabled&quot;];

Niveau van logboekbeheer instellen

    NSUserDefaults \*prefs = [NSUserDefaults standardUserDefaults];
      [prefs setInteger:1 forKey:@&quot;IpcLogLevel”];
      [[NSUserDefaults standardUserDefaults] synchronize];

Beheerinstellingen voor het logboekregistratieniveau ophalen

    [[NSUserDefaults standardUserDefaults] boolForKey:@&quot;IpcLogLevel&quot;];
 

## Windows ##
Automatische logboekregistratie inschakelen

    CustomerExperienceConfiguration::Option = CustomerExperienceOptions::LoggingEnabledNow;

Zie [CustomerExperienceOptions](/rights-management/sdk/4.2/api/winrt/Microsoft.RightsManagement#msipcthin2_customerexperienceoptions) voor meer informatie over optionele instellingen.

Instelling voor huidige logboekregistratievlag ophalen

    CustomerExperienceOptions loggingOption = CustomerExperienceConfiguration::Option;


**Opmerking**: bovenstaande Windows-codefragmenten zijn in C++. Voor C\ #, werkt u de syntaxis bij met '.' in plaats van '::'.

**Linux / C++**: deze SDK heeft een basislogboekregistratie die niet zo uitgebreid is als die van de andere platforms. Zie voor meer informatie de sectie **Probleemoplossing** van de 'README.md' in [RMS SDK voor draagbare C++](https://github.com/AzureAD/rms-sdk-for-cpp#troubleshooting).

 

 


<!--HONumber=Apr16_HO4-->


