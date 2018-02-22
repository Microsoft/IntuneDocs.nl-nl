---
title: Aangepaste instellingen van Intune voor apparaten met Windows Holographic for Business
titlesuffix: Azure portal
description: Meer informatie over de instellingen die u kunt gebruiken in een aangepast Windows Holographic for Business-profiel.
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 1/24/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ae46aef10ca294637a4d433ce273d3c53e695d64
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/01/2018
---
# <a name="custom-device-settings-for-windows-holographic-for-business-devices-in-microsoft-intune"></a>Aangepaste apparaatinstellingen voor apparaten met Windows Holographic for Business in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Gebruik het **aangepaste** profiel van Microsoft Intune voor Windows Holographic for Business om OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) te implementeren die kunnen worden gebruikt om functies op apparaten te beheren. Met behulp van Windows Holographic for Business komen veel instellingen voor configuratieserviceproviders (CSP's) ter beschikking. Zie [Inleiding tot configuratieserviceproviders (CSP's) voor IT-professionals](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) voor een overzicht van CSP’s. Zie [CSP's die worden ondersteund in Windows Holographic](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens) voor specifieke CSP’s die door Windows Holographic worden ondersteund.

Als u een bepaalde instelling zoekt, moet u er rekening mee houden dat het [beperkingsprofiel voor Windows Holographic for Business-apparaten](device-restrictions-windows-holographic.md) tal van ingebouwde instellingen bevat. U hoeft voor deze instellingen geen aangepaste waarden op te geven.

1. Volg de instructies in [Aangepaste apparaatinstellingen configureren in Microsoft Intune](custom-settings-configure.md) om aan de slag te gaan.
2. Kies op de blade **Profiel maken** de optie **Instellingen** om een of meer OMA-URI-instellingen toe te voegen.
3. Klik op de blade **Aangepaste OMA-URI-instellingen** op **Toevoegen** om een nieuwe waarde toe te voegen. U kunt ook op **Exporteren** klikken om een lijst met alle geconfigureerde waarden te maken in een door komma's gescheiden bestand (.csv).
4. Voer voor elke OMA-URI-instelling die u wilt toevoegen de volgende informatie in. Gebruik de lijst in dit onderwerp voor meer informatie over de instellingen die u kunt gebruiken:
    - **Naam van de instelling**: voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.
    - **Beschrijving van de instelling:** voer eventueel een beschrijving in voor de instelling.
    - **Gegevenstype**: kies uit:
        - **Tekenreeks**
        - **Tekenreeks (XML)**
        - **Datum en tijd**
        - **Geheel getal**
        - **Drijvende komma**
        - **Booleaanse waarde**
    - **OMA-URI (hoofdlettergevoelig)**: geef aan voor welke OMA-URI u een instelling wilt opgeven.
    - **Waarde**: geef de waarde op die moet worden gekoppeld aan de OMA-URI die u hebt opgegeven.
5. Als u klaar bent, gaat u terug naar de blade **Profiel maken** en kiest u **Maken**.
Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.

## <a name="supported-custom-settings"></a>Ondersteunde aangepaste instellingen

De volgende aangepaste instellingen worden in Windows Holographic for Business ondersteund:


|Naam van de instelling|OMA-URI|Gegevenstype  |
|---------|---------|---------|
|AllowFastReconnect     |./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Geheel getal (0 - niet toegestaan, 1 - toegestaan)|
|AllowVPN     |./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Geheel getal (0 - niet toegestaan, 1 - toegestaan)|



## <a name="how-to-find-the-policies-you-can-configure"></a>De beleidsregels zoeken die u kunt configureren

U vindt een volledige lijst met alle configuratieserviceproviders (CSP's) die door Windows Holographic worden ondersteund in [CSP's die worden ondersteund in Windows Holographic](https://docs.microsoft.com/en-us/windows/client-management/mdm/configuration-service-provider-reference#hololens). Niet alle instellingen zijn compatibel met alle versies van Windows Holographic. In de tabel in het Windows-onderwerp kunt u zien welk versie voor elke CSP worden ondersteund.

Bovendien worden niet alle instellingen in het onderwerp door Intune ondersteund. Als u wilt weten of de gewenste instelling door Intune wordt ondersteund, opent u het onderwerp voor de betreffende instelling. U kunt op elke instellingenpagina zien welke bewerkingen worden ondersteund. Voor gebruik in combinatie met Intune moet de instelling de bewerking **Toevoegen** of **Vervangen** ondersteunen.


