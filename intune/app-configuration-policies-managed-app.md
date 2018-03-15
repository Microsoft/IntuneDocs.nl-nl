---
title: Configuratiebeleidsregels toevoegen voor beheerde apps zonder apparaatinschrijving
titlesuffix: Microsoft Intune
description: Meer informatie over het configureren van beleidsregels voor beheerde apps zonder apparaatinschrijving.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 384804029ecbf403f526144136dc187212e6cf4a
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a>App-configuratiebeleidsregels toevoegen voor beheerde apps zonder apparaatinschrijving

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

U kunt app-configuratiebeleidsregels gebruiken voor beheerde apps die de Intune App SDK ondersteunen, zelfs op apparaten die niet zijn ingeschreven. 

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies de workload **Mobiele apps**.
4. Kies **App-configuratiebeleidsregels** in de groep **Beheren** en kies vervolgens **Toevoegen**.
5. Stel de volgende details in:
    - **Naam**  
      De naam van het profiel die in Azure Portal wordt weergegeven.
    - **Beschrijving**  
      De beschrijving van het profiel die in Azure Portal wordt weergegeven.
    - **Type apparaatinschrijving**  
      Kies **apps beheren**.
6. Selecteer **Gekoppelde app** om de app te kiezen die u gaat configureren. Selecteer de app in de lijst met apps die u hebt goedgekeurd en die zijn gesynchroniseerd met Intune.
7. Voor elk door de app ondersteunde configuratie-instelling typt u de **naam** en **waarde** en kiest u het weglatingsteken (**...** ).  
    Als u een configuratie wilt verwijderen, kiest u het weglatingsteken (**...**) en selecteert u **Verwijderen**.  
    
Voor Intune App SDK-functionaliteit geschikte apps ondersteunen configuraties in sleutel-waardeparen. Raadpleeg de documentatie van elke app voor meer informatie over welke sleutel-waardeconfiguraties worden ondersteund. Houd er rekening mee dat u tokens kunt gebruiken die dynamisch worden gevuld met gegevens die zijn gegenereerd door de app. Ga voor meer informatie over app-configuratiebeleidsinstellingen van Outlook voor iOS naar [App-configuratie van Outlook voor iOS beheren met Microsoft Intune](https://technet.microsoft.com/en-us/library/mt813789(v=exchg.150).aspx).

## <a name="configuration-values-for-using-tokens"></a>Configuratiewaarden voor het gebruik van tokens

Intune kan bepaalde tokens genereren en deze verzenden naar de beheerde toepassing. Als bijvoorbeeld uw app-configuratie een e-mailinstelling kan gebruiken, kunt u een dynamische e-mail toevoegen met behulp van een token. Typ de naam die door de app wordt verwacht in het veld **Naam** en typ vervolgens `\{\{mail\}\}` in het veld **Waarde**.

Intune ondersteunt de volgende tokentypen in de configuratie-instellingen:

- \{\{userprincipalname\}\}- bijvoorbeeld **John@contoso.com**
- \{\{mail\}\}- bijvoorbeeld **John@contoso.com**
- \{\{partialupn\}\} - bijvoorbeeld**Jan**
- \{\{accountid\}\} - bijvoorbeeld **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- \{\{userid\}\} - bijvoorbeeld **3ec2c00f-b125-4519-acf0-302ac3761822**
- \{\{username\}\} - bijvoorbeeld **Jan de Vries**
- \{\{PrimarySMTPAddress\}\}- bijvoorbeeld **testuser@ad.domain.com** 


> [!Note]  
> De tekens \{\{ en \}\} worden alleen gebruikt door tokentypen en mogen niet worden gebruikt voor andere doeleinden.

## <a name="next-steps"></a>Volgende stappen

Ga vervolgens als gebruikelijk door met [toewijzen](apps-deploy.md) en [bewaken](apps-monitor.md) van de app.
