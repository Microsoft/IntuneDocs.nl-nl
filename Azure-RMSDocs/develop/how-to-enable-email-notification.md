---
# required metadata

title: E-mailmeldingen inschakelen | Azure RMS
description: Met e-mailmeldingen kunt u de eigenaar van beveiligde inhoud informeren wanneer zijn of haar inhoud wordt geopend.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 5FB975EE-E4E5-4089-B8E1-CAFD5B9B34EC
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# E-mailmeldingen inschakelen

Met e-mailmeldingen kunt u de eigenaar van beveiligde inhoud informeren wanneer zijn of haar inhoud wordt geopend.

Als u een e-mailmelding wilt instellen voor een bepaalde licentie, gebruikt u [**IpcSetLicenseProperty**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcsetlicenseproperty) met de parameter van het type eigenschap *dwPropID* als [**IPC\_LI\_APP\_SPECIFIC\_DATA**](/rights-management/sdk/2.1/api/win/License%20property%20types#msipc_license_property_types_IPC_LI_APP_SPECIFIC_DATA) en de toepassingsgegevensvelden opgemaakt als een [**IPC\_NAME\_VALUE\_LIST**](/rights-management/sdk/2.1/api/win/structures#msipc_ipc_name_value_list).

## C++

    ...
    int numDataPairs = 3;

    IPC_NAME_VALUE propertyValuePairs [numDataPairs];

    // lcid field set to 0 causes the default lcid to be used

    propertyValuePairs[0] = {&quot;MS.Conetent.Name&quot;, 0, &quot;FinancialReport.docx&quot;};
    propertyValuePairs[1] = {&quot;MS.Notify.Enabled&quot;,0 , &quot;true&quot;};
    propertyValuePairs[2] = {&quot;MS.Notify.Culture&quot;,0 , “en-US”};

    IPC_NAME_VALUE_LIST emailNotificationAppData = {numDataPairs, propertyValuePairs};

    result = IpcSetLicenseProperty( licenseHandle, FALSE, IPC_LI_APP_SPECIFIC_DATA, emailNotificationAppData);
    ...    

De volgende tabel bevat de toepassingsgegevensvelden, de eigenschapsnaam en de waardeparen voor RMS-e-mailmeldingen.


|Naam eigenschap | Gegevenstype | Voorbeeldwaarde | Opmerkingen |
|--------------|-----------|---------------|-------|
|MS.Content.Name|string|“FinancialReport.docx”|Dit is een id die is gekoppeld aan de beveiligde inhoud.<br><br> Deze waarde moet voor beveiligde bestanden de naam zijn van het bestand zonder padinformatie.<br><br> Voor andere typen inhoud, zoals een e-mailbericht, kan dit het onderwerp van het e-mailbericht zijn, of de waarde blijft leeg.|
|MS.Notify.Enabled|string|“true” &#124; “false”|Als deze waarde is ingesteld op "true", wordt er een meldingse-mail verzonden naar de eigenaar van de publicatielicentie wanneer iemand probeert deze te gebruiken om een licentie voor eindgebruikers te verkrijgen.|
|MS.Notify.Culture|string|“en-US”| **Bron:** System.Globalization.CultureInfo.CurrentUICulture.Name <br><br>Deze waarde wordt gebruikt om te bepalen in welke taal de meldingse-mail wordt opgesteld. De bijbehorende datum, tijd en nummering moeten dan worden gebruikt in het bericht.<br><br>Deze waarde moet worden ingesteld op basis van de gebruikersinstellingen van de machine waarop de publicatielicentie is gemaakt, of op basis van de voorkeurscultuur van de eigenaar van de publicatielicentie.|
|MS.Notify.TZID|string|“Pacific Standard Time”|**Bron:** TimeZoneInfo.Local.Id - Windows-tijdzone-id.<br><br>Deze waarde is de tijdzone-id van het Microsoft Windows-besturingssysteem. Hiermee wordt verwezen naar een bepaalde tijdzone en de bijbehorende kenmerken.|
|MS.Notify.TZO|string|“-480”|Dit is het tijdzoneverschil dat bestaat tussen de tijdzone van de publicatielicentie en de UTC-tijd in minuten.<br><br>Als er een geldige TZID-waarde wordt opgegeven, wordt het tijdzoneverschil dat hierdoor wordt gespecificeerd, gebruikt en wordt deze waarde genegeerd.<br><br>Deze waarde wordt waarschijnlijk gebruikt door publicatieplatforms die niet op Windows zijn gebaseerd en geen toegang hebben tot de lijst Windows-tijdzone-id’s.<br><br>Als er geen TZID-waarde is opgegeven, wordt deze waarde gebruikt om het tijdzoneverschil in meldingen te berekenen en wordt TZSN gebruikt (ongeacht de tijdzonewaarde) om de naam van de tijdzone op te geven. Hierdoor ligt de tijdzone vast en wordt er geen wijziging doorgevoerd voor zomer- en wintertijd.<br><br>Bijvoorbeeld:<br><br>Als TXID leeg is, TZ0 is ingesteld op "-420" en TZSN is ingesteld op "Pacific Daylight Time", worden alle waarden die in de e-mailmelding worden weergegeven, aangepast aan "Pacific Daylight Time" en als zodanig weergegeven, zelfs als het op dat moment geen zomertijd is.<br><br>Is er daarentegen zowel een TZID-waarde als een TZSN- en een TZDN-waarde opgegeven, dan worden de in de e-mailmelding vermelde tijden aangepast en weergegeven op basis van de zomer- of wintertijd.|
|MS.Notify.TZSN|string|“Pacific Standard Time”|**Bron:** TimeZoneInfo.Local.StandardName - standaardtijdzonenaam.<br><br>Dit moet de gelokaliseerde versie zijn van de standaardtijdzonenaam van de tijdzone.|
|MS.Notify.TZDN|string|“Pacific Daylight Time”|**Bron:** TimeZoneInfo.Local.DaylightName - tijdzonenaam bij zomertijd.<br><br>Dit moet de gelokaliseerde versie zijn van de tijdzonenaam van de tijdzone bij zomertijd. Als er in de tijdzone geen sprake is van een zomer- en wintertijd, kan deze kan hetzelfde zijn als de standaardnaam.|

## Verwante onderwerpen

* [**IpcSetLicenseProperty**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcsetlicenseproperty)
* [**IPC\_LI\_APP\_SPECIFIC\_DATA**](/rights-management/sdk/2.1/api/win/License%20property%20types#msipc_license_property_types_IPC_LI_APP_SPECIFIC_DATA)
* [**IPC\_NAME\_VALUE\_LIST**](/rights-management/sdk/2.1/api/win/structures#msipc_ipc_name_value_list)
 

 


<!--HONumber=Apr16_HO4-->


