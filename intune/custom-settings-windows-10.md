---
title: Aangepaste Intune-instellingen voor Windows 10-apparaten
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp vindt u informatie over de instellingen die u kunt gebruiken in een aangepast Windows 10-profiel.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 52ad4f141c3b2b73a400c69fb9d9beb174bbac64
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="custom-device-settings-for-windows-10-devices-in-microsoft-intune"></a>Aangepaste apparaatinstellingen voor Windows 10-apparaten in Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

 Gebruik het **aangepaste** profiel van Microsoft Intune voor Windows 10 en Windows 10 Mobile om OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) te implementeren die kunnen worden gebruikt om functies op apparaten te beheren. In Windows 10 zijn veel CSP-instellingen beschikbaar, bijvoorbeeld de [ beleids-CSP (Policy Configuration Service Provider)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
Als u een bepaalde instelling zoekt, moet u er rekening mee houden dat het [beperkingsprofiel voor Windows 10-apparaten](device-restrictions-windows-10.md) tal van instellingen bevat die zijn ingebouwd in Intune. U hoeft voor deze instellingen geen aangepaste waarden op te geven.

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

## <a name="example"></a>Voorbeeld
In de schermopname hieronder is de instelling **Conectivity/AllowVPNOverCellular** ingeschakeld. Hiermee kan met een Windows-10-apparaat een VPN-verbinding worden gemaakt in een mobiel netwerk.

> ![Voorbeeld van een aangepast beleid met VPN-instellingen](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a>De beleidsregels zoeken die u kunt configureren

Een complete lijst met configuratieserviceproviders (CSP's) die door Windows 10 worden ondersteund, vindt u in het artikel [Configuration service provider reference (Referentie voor Configuration Service Providers) ](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) in de documentatiebibliotheek van Windows.

Niet alle instellingen zijn compatibele met alle versies van Windows 10. In de tabel in het Windows-onderwerp kunt u zien welk versie voor elke CSP worden ondersteund.

Bovendien worden niet alle instellingen in het onderwerp door Intune ondersteund. Als u wilt weten of de gewenste instelling door Intune wordt ondersteund, opent u het onderwerp voor de betreffende instelling. U kunt op elke instellingenpagina zien welke bewerkingen worden ondersteund. Voor gebruik in combinatie met Intune moet de instelling de bewerking **Toevoegen** of **Vervangen** ondersteunen.



