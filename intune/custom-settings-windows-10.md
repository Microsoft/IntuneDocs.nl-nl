---
title: Aangepaste instellingen toevoegen voor Windows 10-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Configureer aangepaste OMA-URI-instellingen op apparaten met Windows 10 met een aangepast profiel in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bdbb6643a4ee8aace0db22cd7f9189f7ac6445f0
ms.sourcegitcommit: ada99fefe9a612ed753420116f8c801ac4bf0934
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2018
ms.locfileid: "36232823"
---
# <a name="custom-oma-uri-settings-for-windows-10-devices---intune"></a>Aangepaste OMA-URI-instellingen voor Windows-10-apparaten - Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Gebruik het **aangepaste** profiel van Microsoft Intune voor Windows 10 en Windows 10 Mobile om OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) te implementeren. Deze instellingen worden gebruikt om functies op apparaten te beheren. In Windows 10 zijn veel CSP-instellingen (Configuration Service Provider) beschikbaar, zoals de [beleids-CSP (Policy Configuration Service Provider)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).

Als u een specifieke instelling zoekt, moet u er rekening mee houden dat het [beperkingsprofiel voor Windows 10-apparaten](device-restrictions-windows-10.md) tal van instellingen bevat die zijn ingebouwd in Intune en waarvoor geen aangepaste waarden vereist zijn.

## <a name="configure-custom-settings"></a>Aangepaste instellingen configureren

1. Maak een nieuw configuratieprofiel met het **aangepaste** profieltype. In [Aangepaste apparaatinstellingen configureren](custom-settings-configure.md) worden de stappen beschreven.
2. Selecteer in **Aangepaste OMA-URI-instellingen** de optie **Toevoegen** om een nieuwe instelling te maken. U kunt ook op **Exporteren** klikken om een lijst met alle geconfigureerde waarden te maken in een door komma's gescheiden bestand (.csv).
3. Voer voor elke OMA-URI-instelling die u wilt toevoegen de volgende informatie in:

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
- **Waarde**: voer de waarde in die, of het bestand dat, moet worden gekoppeld aan de OMA-URI die u hebt ingevoerd.

4. Wanneer u bent klaar, selecteert u **OK**. In **Profiel maken** selecteert u vervolgens **Maken**. Het profiel wordt gemaakt en wordt weergegeven in de lijst met profielen.

## <a name="example"></a>Voorbeeld
In het volgende voorbeeld wordt de instelling **Connectivity/AllowVPNOverCellular** ingeschakeld. Met deze instelling kan met een Windows-10-apparaat een VPN-verbinding worden gemaakt in een mobiel netwerk.

![Voorbeeld van een aangepast beleid met VPN-instellingen](./media/custom-policy-example.png)

## <a name="find-the-policies-you-can-configure"></a>De beleidsregels zoeken die u kunt configureren

Een complete lijst met CSP's (configuratieserviceproviders) die door Windows 10 worden ondersteund, vindt u in het artikel [Referentie voor Configuration Service Providers](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference).

Niet alle instellingen zijn compatibele met alle versies van Windows 10. In [Referentie voor Configuration Service Providers](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) leest u welke versies worden ondersteund voor elke CSP.

Bovendien worden niet alle genoemde instellingen door Intune ondersteund. Als u wilt weten of de gewenste instelling door Intune wordt ondersteund, opent u het artikel voor de betreffende instelling. U kunt op elke instellingenpagina zien welke bewerkingen worden ondersteund. Voor gebruik in combinatie met Intune moet de instelling de bewerking **Toevoegen** of **Vervangen** ondersteunen.
