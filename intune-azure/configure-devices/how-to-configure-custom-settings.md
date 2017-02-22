---
title: Aangepaste apparaatinstellingen in Intune configureren | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u Intune kunt gebruiken voor het configureren van aangepaste instellingen op de apparaten die u beheert.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/23/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: b404df57e94afe7b80dd39163ed72a24d8b05508


---

# <a name="how-to-configure-custom-device-settings"></a>Aangepaste apparaatinstellingen configureren

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="when-to-use-custom-settings"></a>Wanneer u aangepaste instellingen moet gebruiken

Het kan handig zijn aangepaste apparaatinstellingen te gebruiken wanneer de instellingen die u wilt configureren, niet in Intune zijn ingebouwd, en beschikbaar zijn via andere apparaatprofielen.
Aangepaste instellingen worden voor elk platform anders geconfigureerd. Voor Android- en Windows-apparaten kunt u bijvoorbeeld OMA-URI-waarden (Open Mobile Alliance Uniform Resource Identifier) opgeven voor het beheren van functies op apparaten. Voor Apple-apparaten kunt u een bestand importeren dat u met [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) hebt gemaakt.

Gebruik de informatie in dit onderwerp voor meer informatie over de basisbeginselen voor het configureren van profielen met aangepaste instellingen en lees vervolgens de aanvullende onderwerpen voor elk platform voor meer apparaatspecifieke informatie.

## <a name="create-a-device-profile-containing-custom-settings"></a>Een apparaatprofiel met aangepaste instellingen maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Apparaten configureren** op de blade **Intune**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
3. Kies **Profiel maken** op de blade Profielen.
4. Voer op de blade **Profiel maken** een **naam** en een **beschrijving** in voor het aangepaste profiel.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de aangepaste instellingen wilt toepassen. Op dit moment kunt u een van de volgende platformen kiezen voor aangepaste apparaatinstellingen:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 10 en hoger**
6. Kies **Aangepast** in de vervolgkeuzelijst **Profieltype**.
7. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u hebt gekozen. Raadpleeg een van de volgende onderwerpen voor gedetailleerde instellingen voor elk platform:
    - [Android-instellingen](custom-for-android.md)
    - [iOS-instellingen](custom-for-ios.md)
    - [macOS-instellingen](custom-for-macos.md)
    - [Windows Phone 8.1-instellingen](custom-for-windows-phone-8-1.md)
    - [Windows 10-instellingen](custom-for-windows-10.md)
8. Als u klaar bent, gaat u terug naar de blade **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.
Zie [How to assign device profiles](how-to-assign-device-profiles.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.




<!--HONumber=Feb17_HO1-->


