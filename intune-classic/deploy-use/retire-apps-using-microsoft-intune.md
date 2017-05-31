---
title: Apps buiten gebruik stellen | Microsoft Docs
description: Informatie over het buiten gebruik stellen of verwijderen van apps met behulp van Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6fbf0805-1144-4e08-bafd-4f181d932bf2
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 670e108fc4f672b4900f7cfb4e0127e16a377fa7
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="retire-apps-using-microsoft-intune"></a>Apps buiten gebruik stellen met Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Als u een app buiten gebruik wilt stellen, hoeft u de app alleen maar te verwijderen. Als u een app implementeert en beheert met Intune, kunt u deze app op mobiele apparaten op dezelfde manier verwijderen als op Windows-pc’s. Voor deze procedure moet de app de verwijderingsprocedure ondersteunen om te kunnen worden verwijderd.

## <a name="uninstall-an-app"></a>Een app verwijderen

1.  Kies **Apps** &gt; **Apps** in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com).

2.  Selecteer de app die u wilt verwijderen (een eerder geïmplementeerde app) en kies vervolgens **Implementatie beheren**.

3.  Op de pagina **Implementatieactie** selecteert u **Verwijderen** uit de kolom **Goedkeuring** .

Wanneer het apparaat of de computer de volgende keer naar updates zoekt, wordt de app verwijderd.

### <a name="see-also"></a>Zie tevens
[Apps toevoegen in Microsoft Intune](add-apps.md)

