---
# vereiste metagegevens

titel: Instructies: de API-beveiligingsmodus instellen | Beschrijving Azure RMS: kiezen in welke beveiligingsmodus uw bestands-API wordt uitgevoerd.
trefwoorden: auteur: bruceperlerms manager: mbaldwin ms.date: 28-04-2016 ms.topic: artikel ms.prod: azure ms.service: rights-management ms.technology: techgroepidentiteit ms.assetid: 3B088F14-81C5-4C78-8DED-F5F153353EE0
# optionele metagegevens

#ROBOTS:
doelgroep: ontwikkelaar
#ms.devlang:
ms.reviewer: shubhamp ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Instructies: de API-beveiligingsmodus instellen

U kunt kiezen in welke beveiligingsmodus uw toepassing met de bestands-API moet worden uitgevoerd, met behulp van de functie [**IpcSetGlobalProperty**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcsetglobalproperty).

Als u uw toepassing zodanig wilt initialiseren dat deze wordt uitgevoerd in de *servermodus*, roept u de functie [**IpcSetGlobalProperty**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcsetglobalproperty) aan en stelt u de beveiligingsmodus in op [**IPC\_API\_MODE\_SERVER**](/rights-management/sdk/2.1/api/win/api%20mode%20values#msipc_api_mode_values_IPC_API_MODE_SERVER). Uw toepassing wordt standaard uitgevoerd in de *clientmodus*: **IPC\_API\_MODE\_CLIENT**.

Voor meer informatie over de *servermodus* raadpleegt u [Toepassingstypen](application-types.md).

**Belangrijk:** de beveiligingsmodus moet worden ingesteld voordat andere Rights Management Services SDK 2.1-functies worden aangeroepen. Wanneer de beveiligingsmodus is ingesteld, kan deze niet meer worden gewijzigd voor het huidige proces.

## Verwante onderwerpen

* [Soorten toepassingen](application-types.md)
* [**Waarden voor API-modi**](/rights-management/sdk/2.1/api/win/api%20mode%20values#msipc_api_mode_values_IPC_API_MODE_SERVER)
* [**IpcSetGlobalProperty**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcsetglobalproperty)
 

 


<!--HONumber=Jun16_HO2-->


