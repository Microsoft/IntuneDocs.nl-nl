---
# required metadata

title: Een toepassing met rechten testen | Azure RMS
description: Hier worden de stappen beschreven die u moet voltooien om een RMS SDK 2.1-toepassing met rechten te testen.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 834B7242-31D3-4275-A892-CFE95A61E29E
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Een toepassing met rechten testen

In dit onderwerp worden de stappen beschreven die u moet voltooien om een Rights Management Services SDK 2.1-toepassing met rechten te testen.

Een RMS-toepassing (Rights Management Services) maakt gebruik van verschillende typen certificaten en licenties voor het publiceren en gebruiken van beveiligde inhoud. Elk van deze certificaten en licenties bestaat uit een certificaatketen die afkomstig is uit een Microsoft-certificeringsinstantie. Microsoft biedt de volgende hiërarchieën:

-   De hiërarchie Preproductie kan worden gebruikt om toepassingen te ontwikkelen en te testen.
-   De hiërarchie Productie moet worden gebruikt voor vrijgegeven toepassingen

U wordt aangeraden om bij het ontwikkelen van een toepassing de hiërarchie Preproductie te gebruiken. Als u dit doet, kunt u werken zonder een productiegebruiksrechtovereenkomst met Microsoft te ondertekenen.

> [!IMPORTANT]
> Het is een aanbevolen procedure om een RMS SDK 2.1-toepassing eerst te testen in de RMS-preproductieomgeving op een RMS-server. Hierna kunt u, als u wilt dat de klant de mogelijkheid heeft om de toepassing te gebruiken met de Azure RMS-service, tests in die omgeving uitvoeren. Zie [Ervoor zorgen dat uw servicetoepassing werkt met RMS in de cloud](how-to-use-file-api-with-aadrm-cloud.md) (Engelstalig) voor meer informatie.

 

### Vereisten

-   Een installatie van een RMS SDK 2.1-ontwikkelomgeving. Zie [De ontwikkelomgeving voor preproductie instellen](how-to-set-up-the-pre-production-development-environment.md) (Engelstalig) voor meer informatie.
-   Zie [IPCHelloWorld - een voorbeeldtoepassing](how-to-build-your-first-application.md) (Engelstalig) voor een voorbeeldtoepassing.

Instructies

### Stap 1:

een toepassing met rechten maken en bouwen. Zie de sectie Vereisten hierboven voor opties.

### Stap 2: een toepassingsmanifest genereren met behulp van de preproductiecertificaatketen

U moet een manifest genereren voor de toepassing voordat u deze uitvoert.

**Opmerking**  Als de toepassing gebruikmaakt van server-API-modus(**IPC\_API\_MODE\_SERVER**), hoeft u geen toepassingsmanifest te gebruiken. U kunt de toepassing testen op een AD RMS-productieserver en u hoeft geen productielicentie te verkrijgen wanneer u overschakelt naar de productieomgeving. Zie [Toepassingstypen](application-types.md) voor meer informatie over servermodustoepassingen.

 

Dit proces staat ook bekend als het ondertekenen van de toepassing. U kunt het manifest genereren met behulp van een productiecertificaatketen of de preproductiecertificaatketen die is geïnstalleerd met de SDK. Tijdens de ontwikkeling wordt u aangeraden om de preproductiecertificaatketen te gebruiken.

Zie [Certificaatketens begrijpen](understanding-certificate-chains.md) voor meer informatie over sleutels en certificaatketens.

Zie [Overschakelen naar de productieomgeving](switching-to-the-production-environment.md) voor meer informatie over het ondertekenen van een toepassing met een productiecertificaatketen.

Als u het toepassingsmanifest wilt genereren met behulp van de preproductiecertificaatketen, voert u deze stappen uit op de ontwikkelcomputer:

1.  Kopieer de volgende bestanden in de installatiemappen naar dezelfde map als de toepassing.

    %MSIPCSdkDir%\\Tools\\Genmanifest.exe

    %MSIPCSdkDir%\\bin\\Isvtier5appsigningprivkey.dat

    %MSIPCSdkDir%\\bin\\Isvtier5appsigningpubkey.dat

    %MSIPCSdkDir%\\bin\\Isvtier5appsignsdk\_client.xml

    %MSIPCSdkDir%\\bin\\YourAppName.isv.mcf

2.  Wijzig in de toepassingsmap de naam van het manifestconfiguratiebestand, YourAppName.isv.mcf, in de naam van de toepassing eindigend op de bestandsnaamextensie .mcf. Als de naam van de toepassing bijvoorbeeld MyApp.exe is, wijzigt u YourAppName.isv.mcf in MyApp.exe.mcf.

3.  Gebruik een teksteditor om de toepassing toe te voegen aan het manifestconfiguratiebestand. Vervang hiervoor de tijdelijke aanduiding voor tekst &lt;YourAppName&gt;.exe in de modulelijst in het MCF-bestand door de naam van uw toepassing, bijvoorbeeld MyApp.exe.

    Er wordt tijdens het ondertekenen een fout gegenereerd wanneer u het MCF-bestand gebruikt zonder dat het is aangepast.

4.  Voer Genmanifest.exe uit om het toepassingsmanifest te genereren. Dit wordt ook wel het ondertekenen van de toepassing genoemd. De uitvoer van deze bewerking moet een MAN-bestand zijn. Als de toepassing bijvoorbeeld MyApp.exe heet en het manifestconfiguratiebestand heet MyApp.exe.mcf, voert u de volgende opdracht uit:

    **genmanifest.exe -chain isvtier5appsignsdk\_client.xml MyApp.exe.mcf MyApp.exe.man**

### Stap 3: de toepassing uitvoeren

U kunt de toepassing uitvoeren vanuit elke gewenste map, maar het toepassingsmanifest (MyApp.exe.man) moet zich in dezelfde map bevinden als het uitvoerbare bestand (MyApp.exe).

-   **De RMS 1-box-omgeving gebruiken**

    Als u de RMS 1-box-omgeving gebruikt om de toepassing te testen, kopieert u het uitvoerbare bestand voor de toepassing en het toepassingsmanifest in een willekeurige map in de 1-box-omgeving. Vervolgens voert u de toepassing uit.

    Zie [De testomgeving instellen](how-to-set-up-your-test-environment.md) voor meer informatie over de RMS 1-box-omgeving.

-   **Een preproductieserverconfiguratie gebruiken**

    Als u de toepassing test op een RMS-server die is geconfigureerd voor preproductie, moet de Active Directory Rights Management Services Client 2.1 zijn geconfigureerd op de computer waarop u de toepassing gaat uitvoeren, bijvoorbeeld de ontwikkelcomputer. Zorg er vervolgens voor dat zowel het uitvoerbare bestand voor de toepassing als het toepassingsmanifest zich in dezelfde map op deze computer bevindt en voer de toepassing uit.

    Zie [Client configureren](how-to-configure-the-ad-rms-client-2-0.md) voor meer informatie over het configureren van de client op uw computer. Zie [De server installeren en configureren](how-to-install-and-configure-an-rms-server.md) voor meer informatie over het installeren van een RMS-server.

## Verwante onderwerpen

* [Gebruik](how-to-use-msipc.md)
* [De client configureren](how-to-configure-the-ad-rms-client-2-0.md)
* [De server installeren en configureren](how-to-install-and-configure-an-rms-server.md)
* [IPCHelloWorld - een voorbeeldtoepassing](how-to-build-your-first-application.md)
* [De ontwikkelomgeving voor preproductie instellen](how-to-set-up-the-pre-production-development-environment.md)
* [Overschakelen naar de productieomgeving](switching-to-the-production-environment.md)
* [De testomgeving instellen](how-to-set-up-your-test-environment.md)
* [Certificaatketens begrijpen](understanding-certificate-chains.md)
 

 





<!--HONumber=Apr16_HO4-->


