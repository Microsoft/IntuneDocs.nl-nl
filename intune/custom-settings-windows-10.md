---
title: Aangepaste Microsoft Intune-instellingen voor apparaten met Windows 10
titlesuffix: 
description: Meer informatie over de aangepaste instellingen die u kunt configureren in een aangepast Windows 10-profiel.
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4bb86d0f80a4d337e0ab63ae7f90d6c3541462d9
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-10"></a>Aangepaste Microsoft Intune-apparaatinstellingen voor apparaten met Windows 10

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Gebruik het **aangepaste** profiel van Microsoft Intune voor Windows 10 en Windows 10 Mobile om OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) te implementeren die kunnen worden gebruikt om functies op apparaten te beheren. In Windows 10 zijn veel CSP-instellingen beschikbaar, zoals de [ beleids-CSP (Policy Configuration Service Provider)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
Als u een bepaalde instelling zoekt, moet u er rekening mee houden dat het [beperkingsprofiel voor Windows 10-apparaten](device-restrictions-windows-10.md) tal van instellingen bevat die zijn ingebouwd in Intune. U hoeft voor deze instellingen geen aangepaste waarden op te geven.

## <a name="configure-custom-settings"></a>Aangepaste instellingen configureren

1. Volg de instructies in [Aangepaste apparaatinstellingen configureren in Microsoft Intune](custom-settings-configure.md) om aan de slag te gaan.
1. Klik in het deelvenster **Aangepaste OMA-URI-instellingen** op **Toevoegen** om een nieuwe waarde toe te voegen. U kunt ook op **Exporteren** klikken om een lijst met alle geconfigureerde waarden te maken in een door komma's gescheiden bestand (.csv).
1. Voer voor elke OMA-URI-instelling die u wilt toevoegen de volgende informatie in. Gebruik de lijst in dit artikel voor meer informatie over de instellingen die u kunt gebruiken:
    - **Naam**: voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.
    - **Beschrijving**: voer eventueel een beschrijving in voor de instelling.
    - **OMA-URI (hoofdlettergevoelig)**: geef aan voor welke OMA-URI u een instelling wilt opgeven.
    - **Gegevenstype**: kies uit:
        - **Tekenreeks**
        - **Tekenreeks (XML)**
        - **Datum en tijd**
        - **Geheel getal**
        - **Drijvende komma**
        - **Booleaanse waarde**
        - **Base64**
    - **Waarde**: geef een waarde of bestand op om te koppelen aan de OMA-URI die u hebt opgegeven.
1. Als u klaar bent, kiest u **OK**, gaat u terug naar het deelvenster **Profiel maken** en kiest u **Maken**.
Het profiel wordt gemaakt en wordt weergegeven in het deelvenster met de profielenlijst.

## <a name="example"></a>Voorbeeld
In de volgende schermopname is de instelling **Connectivity/AllowVPNOverCellular** ingeschakeld. Hiermee kan met een Windows-10-apparaat een VPN-verbinding worden gemaakt in een mobiel netwerk.

> ![Voorbeeld van een aangepast beleid met VPN-instellingen](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a>De beleidsregels zoeken die u kunt configureren

Een complete lijst met configuratieserviceproviders (CSP's) die door Windows 10 worden ondersteund, vindt u in het artikel [Configuration service provider reference (Referentie voor Configuration Service Providers) ](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) in de documentatiebibliotheek van Windows.

Niet alle instellingen zijn compatibele met alle versies van Windows 10. In de tabel in het Windows-artikel kunt u zien welke versies voor elke CSP worden ondersteund.

Bovendien worden niet alle instellingen in het artikel door Intune ondersteund. Als u wilt weten of de gewenste instelling door Intune wordt ondersteund, opent u het artikel voor de betreffende instelling. U kunt op elke instellingenpagina zien welke bewerkingen worden ondersteund. Voor gebruik in combinatie met Intune moet de instelling de bewerking **Toevoegen** of **Vervangen** ondersteunen.
