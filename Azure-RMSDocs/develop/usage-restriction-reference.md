---
# required metadata

title: Overzicht van gebruiksbeperkingen | Azure RMS
description: Gebruiksbeperkingen worden gedefinieerd door de constanten die in dit onderwerp worden vermeld.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 16E36039-0FD6-4A0A-82C8-2C9DB19D27DD
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Overzicht van gebruiksbeperkingen

Gebruiksbeperkingen worden gedefinieerd door de constanten die in dit onderwerp worden vermeld.

Elk gebruikersrecht (vermeld in de rechterkolom van AD RMS) heeft een beschrijving, een afdwingingspunt en aanbevolen methoden voor afdwinging.

| AD RMS-recht/-beschrijving | Hoe af te dwingen |
|--------------------------|----------------|
|**IPC_GENERIC_ALL** <br><br> Verleent alle rechten aan de gebruiker. <br><br> **Algemene afdwingingspunten**: geen |Dit recht wordt gebruikt door het systeem en hoeft over het algemeen niet rechtstreeks te worden gecontroleerd. <br><br> [**IpcAccessCheck**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcaccesscheck) gebruikt dit recht om te bepalen of er andere rechten aan de gebruiker moeten worden verleend, zoals in dit voorbeeld.<br><br> `/* fAccessGranted is set to TRUE if either the IPC_GENERIC_WRITE or the IPC_GENERIC_ALL right is granted */` <br><br> `IpcAccessCheck(hKey, IPC_GENERIC_WRITE, &fAccessGranted);`|
|**IPC_GENERIC_READ** <br><br> Het recht om de inhoud van het document te lezen. <br><br> **Algemene afdwingingspunten**: document laden|Documentinhoud niet laden of weergeven|
|**IPC_GENERIC_WRITE** <br><br> Het recht om de inhoud van het document te bewerken <br><br> **Algemene afdwingingspunten**: documentwijziging|Stel UI-besturingselementen die kunnen worden gebruikt voor het wijzigen van de inhoud van het document, in als 'niet bewerkbaar'. <br><br> Schakel menu-items uit die wijzigingen in het document activeren. **Bewerken** > **Knippen**, **Bewerken** > **Plakken** en **invoegen** zijn typische voorbeelden hiervan. <br><br>Schakel snelmenu-items uit die wijzigingen in het document activeren.|
|Geen AD RMS-recht <br><br> Geen beschrijving <br><br> **Algemene afdwingingspunten**: opslaan | Schakel het menu **Bestand** > **Opslaan** uit. <br><br> **Opmerking** Dit recht heeft geen invloed op **Bestand** > **Opslaan als** omdat dit recht geen wijziging in het originele document vertegenwoordigt.<br><br> Schakel sneltoetsen uit die kunnen worden gebruikt voor het activeren van een opslagbewerking (bijvoorbeeld Ctrl + S).<br><br> **Tip** U kunt uitvoering van uw belangrijkste code voor **Bestand** > **Opslaan** het beste laten mislukken als de gebruiker dit recht niet heeft. Dit fungeert als veiligheidsnet voor als u eventuele UX-mechanismen die kunnen worden gebruikt voor het activeren van een opslagbewerking, over het hoofd ziet. |
|**IPC_GENERIC_EXTRACT** <br><br> Het recht om inhoud op te halen uit een beveiligde indeling en deze in een niet-beveiligde indeling te plaatsen. <br><br> **Algemene afdwingingspunten**: kopiëren naar Klembord | Schakel het menu **Bewerken** > **Kopiëren** uit. Schakel het menu **Bewerken** > **Knippen** uit. <br><br>Schakel **Bewerken** en **Knippen** uit in snelmenu’s.<br><br>Schakel sneltoetsen uit die kunnen worden gebruikt voor het activeren van een kopieerbewerking (bijvoorbeeld Ctrl + C of Ctrl + X).<br><br>Werk berichtenhandlers voor vensters bij voor [**WM_CUT**](https://msdn.microsoft.com/library/windows/desktop/ms649023) om het kopiëren van gegevens te weigeren als de gebruiker dit recht niet heeft. Als het venster de standaard door Windows aangeleverde berichtenhandler gebruikt, kunt u dit venster als subklasse specificeren en uw eigen handlers opgeven voor **WM_COPY** en **WM_CUT**. |
|Geen AD RMS-recht <br><br> Geen beschrijving <br><br> **Algemene afdwingingspunten**: opslaan als |Schakel in het dialoogvenster **Opslaan als** alle bestandsindelingen uit die ertoe kunnen leiden dat het document wordt opgeslagen zonder RMS-beveiliging.|
|Geen AD RMS-recht <br><br> Geen beschrijving <br><br> **Algemene afdwingingspunten**: Alt + PrtScn|Roep [**IpcProtectWindow**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcprotectwindow) aan in alle vensters die documentinhoud weergeven.|
|**IPC_GENERIC_EXPORT** <br><br> Het recht om inhoud te extraheren uit een beveiligde indeling en deze in een andere door AD RMS beveiligde indeling te plaatsen. <br><br> **Algemene afdwingingspunten**: opslaan als|Schakel in het dialoogvenster **Opslaan als** de mogelijkheid uit om bestanden op te slaan in een andere bestandsindeling.<br><br>**Tip** U kunt uitvoering van uw belangrijkste code voor **Bestand** > **Opslaan** het beste laten mislukken als de gebruiker probeert om het bestand in een andere indeling op te slaan en dit recht niet heeft. Dit fungeert als veiligheidsnet voor als u eventuele UX-mechanismen die kunnen worden gebruikt voor het activeren van 'Opslaan als', over het hoofd ziet.|
|**IPC_GENERIC_PRINT** <br><br> Het recht om de inhoud van het document af te drukken. <br><br> **Algemene afdwingingspunten**: afdrukken|Schakel het menu **Bestand** > **Afdrukken** uit.<br><br>Schakel sneltoetsen uit die kunnen worden gebruikt voor het activeren van een afdrukbewerking (bijvoorbeeld Ctrl + P).<br><br>Schakel snelmenu-items uit die kunnen worden gebruikt voor het activeren van een afdrukbewerking.<br><br>**Tip** U kunt uitvoering van uw belangrijkste code voor **Bestand** > **Afdrukken** het beste laten mislukken als de gebruiker dit recht niet heeft. Dit fungeert als veiligheidsnet voor als u eventuele UX-mechanismen die kunnen worden gebruikt voor het activeren van een afdrukbewerking, over het hoofd ziet.|
|**IPC_GENERIC_COMMENT** <br><br> Sommige toepassingen ondersteunen de mogelijkheid opmerkingen en aantekeningen toe te voegen aan het document zonder de inhoud van het primaire document bij te werken.<br><br>Dit recht geeft de gebruiker toegang tot deze functie. <br><br> **Algemene afdwingingspunten**: <br><br> Controleren > Opmerking invoegen <br><br> Controleren > Opmerking verwijderen | Schakel alle menu-items uit die kunnen worden gebruikt voor het wijzigen van documentopmerkingen of -aantekeningen. **Controleren** > **Opmerking invoegen** en **Controleren** > **Opmerking verwijderen** zijn hier voorbeelden van. <br><br>Schakel alle sneltoetsen uit die een wijziging van documentopmerkingen kunnen activeren.<br><br>**Opmerking** Een standaardimplementatie vereist zowel **IPC_GENERIC_COMMENT** als **IPC_GENERIC_WRITE** om nieuwe opmerkingen in een bestand vast te leggen. U kunt ervoor kiezen in uw toepassing ondersteuning op te nemen voor gevallen waarin het recht **IPC_GENERIC_COMMENT** wel is verleend, maar het recht **IPC_GENERIC_WRITE** niet. In een dergelijk geval is het toegestaan om opslaan toe te staan, zolang de documentwijzigingen zijn beperkt tot opmerkingen.|
|**IPC_VIEW_RIGHTS** <br><br> Geen beschrijving <br><br> **Algemene afdwingingspunten**: niet van toepassing|Afgedwongen door het systeem. Het systeem staat niet toe dat de ontwikkelaar de [**lijst met gebruikersrechten**](/rights-management/sdk/2.1/api/win/structures#msipc_ipc_user_rights_list) van een licentie opvraagt, tenzij dit recht is verleend.
|**IPC_EDIT_RIGHTS** <br><br> Sommige toepassingen staan gebruikers toe de verzameling gebruikers en rechten voor via AD RMS-beveiligde inhoud te wijzigen.<br><br>Dit recht geeft de gebruiker toegang tot deze functie. <br><br> **Algemene afdwingingspunten**: UI-besturingselement voor het bewerken van toepassingsrechten|Schakel gebruikerstoegang uit tot elke UI die kan worden gebruikt om het RMS-beleid voor een document te bewerken.|

 

 

 


<!--HONumber=Jun16_HO2-->


