---
title: Configuratiebeleidsregels toevoegen voor beheerde apps zonder apparaatinschrijving
titleSuffix: Microsoft Intune
description: Meer informatie over het configureren van beleidsregels voor beheerde apps zonder apparaatinschrijving.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ddb9ec795b9cc8842cbc6c9d33897b5e0f45e88
ms.sourcegitcommit: 23e9c48348a6eba494d072a2665b7481e5b5c84e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/26/2019
ms.locfileid: "74547996"
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>App-configuratiebeleidsregels toevoegen voor beheerde apps zonder apparaatinschrijving

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

U kunt app-configuratiebeleidsregels gebruiken voor beheerde apps die de Intune App SDK ondersteunen, zelfs op apparaten die niet zijn ingeschreven. 

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Kies de workload **Client-apps**.
4. Kies **App-configuratiebeleidsregels** in de groep **Beheren** en kies vervolgens **Toevoegen**.
5. Stel de volgende details in:
    - **Naam**  
      De naam van het profiel die in Azure Portal wordt weergegeven.
    - **Beschrijving**  
      De beschrijving van het profiel die in Azure Portal wordt weergegeven.
    - **Type apparaatinschrijving**  
      Kies **apps beheren**.
6. Selecteer **Gekoppelde app** om de app te kiezen die u gaat configureren. Selecteer de app in de lijst met apps die u hebt goedgekeurd en die zijn gesynchroniseerd met Intune.
7. Voor elk door de app ondersteunde configuratie-instelling typt u de **naam** en **waarde** en kiest u het weglatingsteken ( **...** ).  
    Als u een configuratie wilt verwijderen, kiest u het weglatingsteken ( **...** ) en selecteert u **Verwijderen**.  
    
Voor Intune App SDK-functionaliteit geschikte apps ondersteunen configuraties in sleutel-waardeparen. Raadpleeg de documentatie van elke app voor meer informatie over welke sleutel-waardeconfiguraties worden ondersteund. Houd er rekening mee dat u tokens kunt gebruiken die dynamisch worden gevuld met gegevens die zijn gegenereerd door de app. Ga voor meer informatie over app-configuratiebeleidsinstellingen van Outlook voor iOS naar [App-configuratie van Outlook voor iOS beheren met Microsoft Intune](https://technet.microsoft.com/library/mt813789(v=exchg.150).aspx).

## <a name="configuration-values-for-using-tokens"></a>Configuratiewaarden voor het gebruik van tokens

Intune kan bepaalde tokens genereren en deze verzenden naar de beheerde toepassing. Als bijvoorbeeld uw app-configuratie een e-mailinstelling kan gebruiken, kunt u een dynamische e-mail toevoegen met behulp van een token. Typ de naam die door de app wordt verwacht in het veld **Naam** en typ vervolgens `\{\{mail\}\}` in het veld **Waarde**.

Intune ondersteunt de volgende tokentypen in de configuratie-instellingen. Andere aangepaste sleutel-/waardeparen worden niet ondersteund.

- \{\{userprincipalname\}\}- bijvoorbeeld John@contoso.com
- \{\{mail\}\}- bijvoorbeeld John@contoso.com
- \{\{partialupn\}\} - bijvoorbeeld Jan
- \{\{accountid\}\} - bijvoorbeeld fc0dc142-71d8-4b12-bbea-bae2a8514c81
- \{\{userid\}\} - bijvoorbeeld 3ec2c00f-b125-4519-acf0-302ac3761822
- \{\{username\}\} - bijvoorbeeld Jan de Vries
- \{\{PrimarySMTPAddress\}\}- bijvoorbeeld testuser@ad.domain.com


> [!Note]  
> De tekens \{\{ en \}\} worden alleen gebruikt door tokentypen en mogen niet worden gebruikt voor andere doeleinden.

## <a name="next-steps"></a>Volgende stappen

Ga vervolgens als gebruikelijk door met [toewijzen](apps-deploy.md) en [bewaken](apps-monitor.md) van de app.
