---
title: Configuratiebeleid voor Android for Work-apps | Microsoft Docs
description: Gebruik het configuratiebeleid voor mobiele apps in Intune om instellingen op te geven die mogelijk zijn vereist wanneer gebruikers een Android for Work-app uitvoeren.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 008c0d20312e90f3897c3da8ae2226e3e2595225
ms.openlocfilehash: 6cb6b4b989d88289c5dffb693f98198ba6439aae


---

# <a name="configure-android-for-work-apps-with-mobile-app-configuration-policies-in-microsoft-intune"></a>Apps configureren met configuratiebeleid voor mobiele apps in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

Gebruik het configuratiebeleid voor mobiele apps in Microsoft Intune om instellingen op te geven die mogelijk zijn vereist wanneer gebruikers een iOS-app uitvoeren. Een app kan gebruikers bijvoorbeeld verplichten het volgende op te geven:

-   Een aangepast poortnummer.

-   Taalinstellingen.

-   Huisstijlinstellingen, zoals een bedrijfslogo.

Als gebruikers deze instellingen niet correct opgeven, kan dit de werkbelasting van uw helpdesk verhogen en de acceptatie van nieuwe apps vertragen.

Configuratiebeleid voor mobiele apps kan ervoor zorgen dat deze problemen worden voorkomen doordat u deze instellingen bij gebruikers kunt implementeren voordat de gebruikers de app uitvoeren. De instellingen worden vervolgens automatisch aangeleverd, en de gebruikers hoeven geen enkele actie te ondernemen.

Voor het gebruik van configuratiebeleid voor apps moet de ontwikkelaar van de app configuraties voor bedrijfsapps beschikbaar hebben gemaakt bij het maken van de app. In Google Chrome worden bijvoorbeeld instellingen beschikbaar gemaakt waarmee u standaardbladwijzers en toegestane en geweigerde sites kunt instellen, en nog veel meer. Neem contact op met de ontwikkelaar van de app om te zien of deze instellingen worden ondersteund en hoe u deze in het beleid moet opgeven.

U implementeert het configuratiebeleid voor de app voor dezelfde gebruikers als de app die u wilt configureren. De beleidsinstellingen worden telkens gebruikt wanneer de app wordt uitgevoerd.

## <a name="configure-a-mobile-app-configuration-policy"></a>Een configuratiebeleid voor mobiele apps configureren

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Beleid** &gt; **Overzicht** &gt; **Beleid toevoegen**.

2.  Vouw in de lijst met beleidsregels **Android for Work** uit, kies **Configuratie van mobiele app (Android for Work)** en kies vervolgens **Beleid maken**.

    > [!TIP]
    > U kunt alleen aangepaste instellingen voor dit beleidstype configureren. Aanbevolen instellingen zijn niet beschikbaar.

3.  Geef in de sectie **Algemeen** op de pagina **Beleid maken** een naam en optionele beschrijving op voor het configuratiebeleid voor de mobiele app.

4. Geef de volgende informatie op in de sectie **Configuratiebeleid voor mobiele app** van de pagina:
    - **De pakket-id van de toepassing waarop deze configuratie betrekking heeft**: de pakket-id vindt u in de sectie 'id=' van de app-URL op de bijbehorende Google Play-pagina. De pakket-id van de Microsoft Excel-app is bijvoorbeeld **com.microsoft.office.excel**.
    - Voer in het tekstvak de gegevens in voor de app-instellingen die u wilt configureren. U krijgt deze instellingen van de leverancier van de app. Deze instellingen worden niet ondersteund in alle apps.
5.  Klik op **Valideren** om te controleren of de indeling van de ingevoerde gegevens geldig is voor de eigenschappenlijst.

    > [!IMPORTANT]
    > Wanneer u op **Valideren** klikt, wordt door Intune gecontroleerd of de ingevoerde configuratiegegevens een geldige indeling hebben. Er wordt niet gecontroleerd of de gegevens werken met de app waaraan deze is gekoppeld.

6.  Wanneer u alle instellingen hebt toegevoegd, klikt u op **Beleid opslaan**.

Het nieuwe beleid wordt weergegeven in het knooppunt **Configuratiebeleid** .


## <a name="deploy-the-app-configuration-policy"></a>Het configuratiebeleid voor de app implementeren
Nadat u een configuratiebeleid voor de mobiele app hebt gemaakt, moet u het implementeren voor dezelfde gebruikers als de gebruikers waarvoor u de app implementeert waarop de instellingen van toepassing zijn.

Zie [Een configuratiebeleid implementeren](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy) voor informatie over het implementeren van beleid

Zie [Android for Work-apps implementeren met Intune](android-for-work-apps.md) voor informatie over het implementeren van apps op Android for Work-apparaten.

Wanneer de geïmplementeerde app op een apparaat wordt uitgevoerd, worden de instellingen uitgevoerd die u in het configuratiebeleid voor de mobiele app hebt geconfigureerd.

> [!TIP]
> Implementeer slechts één configuratiebeleid voor apps per app voor elke gebruiker.



<!--HONumber=Jan17_HO4-->


