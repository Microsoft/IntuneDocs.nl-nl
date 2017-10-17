---
title: Apps implementeren
description: Gebruik de informatie in dit onderwerp om apps met Microsoft Intune te implementeren.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7e0fd24dffaf58267e492f470ee8a7861d6810aa
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2017
---
# <a name="deploy-apps-in-microsoft-intune"></a>Apps in Microsoft Intune implementeren

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Gebruik de informatie in dit onderwerp om apps met Microsoft Intune te implementeren.


## <a name="deploy-an-app"></a>Een app implementeren
In deze procedure implementeert u een app op geselecteerde apparaat- of gebruikersgroepen.

### <a name="to-deploy-an-app"></a>Een app implementeren

1. Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Apps** &gt; **Apps** om de lijst weer te geven van de apps die u beheert.

2.  Selecteer de app die u wilt implementeren en klik vervolgens op **Implementatie beheren**.

3.  Selecteer in het dialoogvenster *&lt;app-naam&gt;* op de pagina **Groepen selecteren** de gebruikers- of apparaatgroepen waarvoor u de app wilt implementeren.

4.  Configureer de volgende instellingen op de pagina **Implementatieactie**:

    - **Goedkeuring**: maak voor de implementatie een keuze uit de volgende mogelijkheden:
        - **Vereist** (verplichte installatie)
        - **Beschikbaar** (gebruikers installeren op verzoek vanuit de bedrijfsportal)
        - **Niet van toepassing** (de app wordt niet geïnstalleerd en niet weergegeven in de bedrijfsportal)
        - **Verwijderen** (de app wordt verwijderd van de betreffende apparaten)
    - **Deadline**: kies bij vereiste installaties hoe snel de app wordt geïmplementeerd. U kunt kiezen uit vooraf gedefinieerde waarden, maar u kunt ook **Aangepast** selecteren om uw eigen deadline te configureren.

5. Als de app die u wilt implementeren, kan worden geconfigureerd door Mobile Application Management-beleid, wordt de pagina **Mobile App Management** weergegeven. Op deze pagina kiest u het Mobile Application Management-beleid dat u wilt koppelen aan deze app.

    [Kijk welke Microsoft-apps compatibel zijn met de beleidsregels van Mobile Application Management.](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx)

6. Als de app die u wilt implementeren, compatibel is met Intune VPN-profielen, wordt de pagina **VPN-profiel** weergegeven. Op deze pagina kunt u iOS-apps koppelen aan een VPN-profiel dat u hebt geïmplementeerd. De VPN-verbinding wordt automatisch gemaakt wanneer de app wordt gestart. Als u een VPN-profiel beschikbaar wilt stellen, moet voor dit profiel de instelling **VPN per app** zijn ingeschakeld.
 Zie [VPN-verbindingen in Microsoft Intune](vpn-connections-in-microsoft-intune.md) voor meer informatie over het configureren van VPN-profielen, zoals informatie over het koppelen van profielen aan apps.

<!---
>[!TIP]
>If an end user previously installed an iOS app and you now deploy it with a deployment action of **Available**, Intune will automatically begin to manage that app with no further action required by you, or the end-user.
--->

## <a name="example"></a>Voorbeeld

In dit voorbeeld hebt u de app als **Beschikbaar** geïmplementeerd voor een iOS-apparaat.
De app wordt weergegeven op apparaten van gebruikers in de bedrijfsportal en gebruikers kunnen de app vanaf daar installeren.

In deze schermafbeelding is bijvoorbeeld de Bing voor iOS-app geïmplementeerd met behulp van het installatietype **Externe koppeling** met een aangepast pictogram. Daarbij is de optie **Geef deze app weer als een aanbevolen app en markeer deze in de bedrijfsportal** geselecteerd.  
![Voor iOS beschikbare app](./media/available-install-on-iOS.png)

Als u de app hebt geïmplementeerd als **Vereist**, krijgt de gebruiker een melding dat er een app gereed is om te worden geïnstalleerd. In deze schermafbeelding is bijvoorbeeld de app Werkmappen voor iOS geïmplementeerd met behulp van het installatietype **Beheerde iOS-app uit de App Store**.  
![Voor iOS vereiste app](./media/iOS-Required-install.PNG)

## <a name="next-steps"></a>Volgende stappen

Nadat u een app hebt geïmplementeerd, is het een goed idee om de voortgang ervan te controleren. Zie [Apps in Microsoft Intune controleren](monitor-apps-in-microsoft-intune.md) voor meer informatie.
