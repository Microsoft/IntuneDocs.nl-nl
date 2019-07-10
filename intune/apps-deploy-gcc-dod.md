---
title: Apps voor GCC High- en DoD-omgevingen
titleSuffix: Microsoft Intune
description: Krijg meer informatie over apps die betrekking hebben om GCC High- en DoD-omgevingen met behulp van Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 29329f86-1aa5-434f-9925-8dc28bf35348
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 17d94252dd957c5699b34e0b8c2cbae2eee0b66f
ms.sourcegitcommit: 63b55e81122e5c15893302b109ae137c30855b55
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2019
ms.locfileid: "67713363"
---
# <a name="deploying-apps-using-intune-on-the-gcc-high-and-dod-environments"></a>Apps implementeren met Intune in de GCC High- en DoD-omgevingen 

Tenantbeheerders kunnen Microsoft Intune gebruiken om apps naar het personeel te distribueren. Het personeel bestaat uit de medewerkers van het bedrijf, oftewel de gebruikers van de app. Er zijn vele typen apps die via Intune naar GCC High- of DoD-omgevingen kunnen worden geïmplementeerd. Als een beheerder een Windows-app moet uploaden en distribueren die voor een GCC High- of DoD-doelgroep is bedoeld, is aangepast, door externe leveranciers is gemaakt of als offline-app is gedownload uit de [Microsoft Store voor Bedrijven](https://businessstore.microsoft.com/store), kan de beheerder ervoor kiezen deze app als [Line-Of-Business-app](apps-add.md#app-types-in-microsoft-intune) te distribueren.  

> [!NOTE]
> Voor commerciële omgevingen kan een tenantbeheerder hun Store voor Bedrijven synchroniseren met Intune. Voor GCC High- en DoD-omgevingen is deze service echter niet beschikbaar. Beheerders moeten in dit geval een app implementeren door deze rechtstreeks naar Intune te uploaden.  

## <a name="add-line-of-business-apps-using-intune"></a>Line-Of-Business-apps toevoegen met behulp van Intune 

Als u met Intune een Line-Of-Business-app wilt toevoegen die voor een GCC High- en DoD-omgeving bedoeld is, kunt u de instructies voor [Windows LOB-apps](lob-apps-windows.md) volgen. U kunt ervoor kiezen eerst de Bedrijfsportal via de Microsoft Store voor Bedrijven te implementeren. Als u eerst de Bedrijfsportal wilt gebruiken, kunt u deze handmatig installeren en implementeren. Zie [De app Microsoft Intune-bedrijfsportal configureren](company-portal-app.md) voor meer informatie. 

## <a name="distribute-offline-apps-from-the-store-for-business-using-intune"></a>Offline-apps met Intune distribueren vanuit de Store voor Bedrijven  

Als u [een offline gelicentieerde app moet downloaden](https://docs.microsoft.com/microsoft-store/distribute-offline-apps#download-an-offline-licensed-app) uit de Microsoft Store voor Bedrijven, volgt u deze stappen om de toepassing te downloaden: 

1. Meld u aan bij de [Store voor Bedrijven](https://businessstore.microsoft.com/).
2. Selecteer **Beheren** > **Instellingen**.
3. Stel **Offline apps weergeven** onder **Winkelervaring** in op **Aan**.

Als u apps wilt kopen en er een offlineversie beschikbaar is, kunt u het licentietype naar offline wijzigen. Zodra u de app hebt opgehaald, kunt u deze beheren door **Beheren** > **Producten en services** te selecteren in de [Store voor Bedrijven](https://businessstore.microsoft.com/). Daarnaast kunt u de app en de bijbehorende afhankelijkheden downloaden. Vervolgens moet u deze gedownloade app (en de bijbehorende afhankelijkheden) met Intune naar de gebruikers implementeren.  

## <a name="syncing-intune-to-the-store-for-business"></a>Intune synchroniseren met de Store voor Bedrijven 

In een commerciële omgeving (geen overheidsomgeving) kunnen beheerders Intune synchroniseren met de Microsoft Store voor Bedrijven. Deze functie is niet beschikbaar voor overheidsomgevingen. Voor meer informatie over de verschillen tussen Intune in commerciële omgevingen en Intune voor overheidsomgevingen raadpleegt u de [Beschrijving van de service Enterprise Mobility + Security for US Government](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-govt-service-description).  

Zie [Apps die u hebt aangeschaft in Microsoft Store voor Bedrijven beheren met Microsoft Intune](windows-store-for-business.md) voor het synchroniseren van Intune met uw Store voor Bedrijven-account.  

## <a name="compliance"></a>Naleving 

Controleer de privacy- en nalevingsoverzichten van apps en vergelijk ze met de nalevings-, beveiligings- en privacyvereisten van uw organisatie wanneer u beoordeelt of deze services op de juiste manier worden gebruikt.   

## <a name="next-steps"></a>Volgende stappen

Zie [Apps aan groepen toewijzen met Microsoft Intune](apps-deploy.md) voor meer informatie over het implementeren en toewijzen van apps.

 
