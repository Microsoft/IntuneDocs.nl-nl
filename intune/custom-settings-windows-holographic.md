---
title: Aangepaste instellingen van Microsoft Intune voor apparaten met Windows Holographic for Business
titlesuffix: 
description: Meer informatie over de instellingen die u kunt gebruiken in een aangepast Windows Holographic for Business-profiel.
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 3/6/2018
ms.article: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b95d891d1dfaecbce182fde4a2221255a7e1eb06
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-holographic-for-business"></a>Aangepaste apparaatinstellingen voor apparaten met Windows Holographic for Business in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Gebruik het **aangepaste** profiel van Microsoft Intune voor Windows Holographic for Business om OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) te implementeren die kunnen worden gebruikt om functies op apparaten te beheren. Met behulp van Windows Holographic for Business komen veel instellingen voor configuratieserviceproviders (CSP's) ter beschikking. Zie [Inleiding tot configuratieserviceproviders (CSP's) voor IT-professionals](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) voor een overzicht van CSP’s. Zie [CSP's die worden ondersteund in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) voor specifieke CSP’s die door Windows Holographic worden ondersteund.

Als u een bepaalde instelling zoekt, moet u er rekening mee houden dat het [beperkingsprofiel voor Windows Holographic for Business-apparaten](device-restrictions-windows-holographic.md) tal van ingebouwde instellingen bevat. U hoeft voor deze instellingen geen aangepaste waarden op te geven.

1. Volg de instructies in [Aangepaste apparaatinstellingen configureren in Microsoft Intune](custom-settings-configure.md) om aan de slag te gaan.
2. In **Profiel maken** kiest u de optie **Instellingen** om een of meer OMA-URI-instellingen toe te voegen.
3. In **Aangepaste OMA-URI-instellingen** klikt u op **Toevoegen** om een nieuwe waarde toe te voegen. U kunt ook op **Exporteren** klikken om een lijst met alle geconfigureerde waarden te maken in een door komma's gescheiden bestand (.csv).
4. Voer voor elke OMA-URI-instelling die u wilt toevoegen de volgende informatie in:
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
1. Als u klaar bent, gaat u terug naar **Profiel maken** en kiest u **Maken**.
Het profiel wordt gemaakt en wordt weergegeven in de profielenlijst.

## <a name="recommended-custom-settings"></a>Aanbevolen aangepaste instellingen

De volgende instellingen zijn handig voor apparaten waarop Windows Holographic for Business wordt uitgevoerd:


|Naam van de instelling|OMA-URI|Gegevenstype  |
|---------|---------|---------|
|[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)|./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Geheel getal<br>0: niet toegestaan<br>1: toegestaan (standaard)|
|[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)|./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Geheel getal<br>0: niet toegestaan<br>1: toegestaan (standaard)|
|[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)|./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Geheel getal<br>0: updateservice niet toegestaan <br>1: updateservice toegestaan (standaard).|
|[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)|./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|Tekenreeks<br>URL: het apparaat controleert via de opgegeven URL op updates van de WSUS-server.<br>Niet geconfigureerd: het apparaat controleert op updates via Microsoft Update.|
|[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)|./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Geheel getal<br>0: niet geconfigureerd. Alle toepasselijke updates worden op het apparaat geïnstalleerd.<br>1: op het apparaat worden alleen updates geïnstalleerd die toepasselijk zijn en op de lijst Toegestane updates staan. Stel dit beleid in op 1 als de IT-afdeling controle wilt behouden over de implementatie van updates op apparaten, zoals wanneer er vóór het implementeren tests moeten worden uitgevoerd.|
|[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)|./Vendor/MSFT/Update/ApprovedUpdates<br><br>**Belangrijk**<br>U moet de bijgewerkte gebruiksrechtovereenkomsten lezen en accepteren namens uw eindgebruikers. Als u dit niet doet, is dat een schending van de juridische of contractuele verplichtingen.|Knooppunt voor update-goedkeuringen en acceptatie van gebruiksrechtovereenkomsten namens de eindgebruiker.|
[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)|./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br><br>**Belangrijk**<br>In het AppLocker CPS-artikel wordt gebruikgemaakt van XML-voorbeelden met het escape-teken. Als u de instellingen wilt configureren met aangepaste Intune-profielen, moet u gewone XML gebruiken.|Tekenreeks<br>Zie het [AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)-artikel voor meer informatie. 

## <a name="how-to-find-the-policies-you-can-configure"></a>De beleidsregels zoeken die u kunt configureren

U vindt een volledige lijst met alle configuratieserviceproviders (CSP's) die door Windows Holographic worden ondersteund in [CSP's die worden ondersteund in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens). Niet alle instellingen zijn compatibel met alle versies van Windows Holographic. In de tabel in het Windows-artikel kunt u zien welke versies voor elke CSP worden ondersteund.

Bovendien worden niet alle instellingen in het artikel door Intune ondersteund. Als u wilt weten of de gewenste instelling door Intune wordt ondersteund, opent u het artikel voor de betreffende instelling. U kunt op elke instellingenpagina zien welke bewerkingen worden ondersteund. Voor gebruik in combinatie met Intune moet de instelling de bewerking **Toevoegen** of **Vervangen** ondersteunen.
