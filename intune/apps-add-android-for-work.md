---
title: Apps toewijzen aan Android for Work-apparaten | Microsoft Docs
titleSuffix: Intune Azure preview
description: 'Intune Azure (preview-versie): gebruik dit onderwerp om te synchroniseren en vervolgens apps uit de Google Play for Work Store aan Android for Work toe te wijzen.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 49e86ab665d9022739c0330092734ba897ea3b02
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a>Apps aan Android for Work-apparaten toewijzen met Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

U wijst apps aan Android for Work-apparaten op een andere manier toe dan aan standaard-Android-apparaten. Alle apps die u installeert voor Android for Work, zijn afkomstig uit de Google Play for Work-store. U meldt zich aan bij de store, bladert naar de gewenste apps en keurt deze goed.
De app wordt vervolgens weergegeven in het knooppunt **Apps met licentie** van de Intune-portal. Hier kunt u de toewijzing van de app op dezelfde manier beheren als toewijzingen van andere apps.

Als u uw eigen LOB-apps (Line-Of-Business) hebt gemaakt, kunt u deze ook toewijzen. Hiertoe moet u zich aanmelden voor een Google-ontwikkelaarsaccount zodat u apps kunt publiceren naar een privégebied in de Google Play-store en deze vervolgens te synchroniseren met Intune.

## <a name="before-you-start"></a>Voordat u begint

Zorg ervoor dat u Intune en Android for Work hebt geconfigureerd voor samenwerking in de workload **Apparaatinschrijving** van de Intune-portal.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Een app uit de Google Play for Work-store synchroniseren


1. Ga naar de [Google Play for Work-store](https://play.google.com/work). Meld u aan met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android for Work te configureren.
2. Zoek in de store naar de app die u wilt toewijzen met Intune.
3. Kies **Goedkeuren** op de pagina voor de app die u hebt gekozen. In dit voorbeeld hebt u de app Microsoft Excel gekozen.<br>
  ![Voorbeeld van het goedkeuren van een app](media/approve.png)
4. Er wordt een venster voor de app geopend, waarin u om toestemming wordt gevraagd voor het uitvoeren van verschillende bewerkingen door de app. U moet **Goedkeuren** kiezen om door te gaan.<br>
  ![Voorbeeld van het goedkeuren van app-machtigingen](media/approve-app-permissions.png)
5. Kort daarna ziet u een bevestigingsbericht dat de app is goedgekeurd en beschikbaar is in uw IT-beheerconsole.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Een Line-Of-Business-app uit de Google Play for Work-store publiceren en synchroniseren

1. Ga naar de Google Play-ontwikkelaarsconsole, [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Meld u aan met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android for Work te configureren. Als u zich voor het eerst aanmeldt, moet u zich registreren en betalen om lid te worden van het Google-ontwikkelaarsprogramma.
3. Kies in de console **Nieuwe toepassing toevoegen**.
4. U uploadt en verstrekt informatie over uw app op dezelfde manier als bij het publiceren van een app naar de Google Play store. U moet echter wel de instelling **Deze toepassing alleen beschikbaar maken voor mijn organisatie (<*organisatienaam*>)** selecteren, zoals hieronder weergegeven.<br>
  ![Optie om de app alleen beschikbaar voor uw organisatie te maken](media/restrict.png)<br>
Dit zorgt ervoor dat de app alleen beschikbaar is voor uw organisatie en niet in de openbare Google Play-store.
Zie de [Help bij de Google-ontwikkelaarsconsole](https://support.google.com/googleplay/android-developer/answer/113469) voor meer informatie over het uploaden en publiceren van Android-apps.
5. Nadat u de app hebt gepubliceerd, gaat u naar de [Google Play for Work-store](https://play.google.com/work). Meld u aan met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android for Work te configureren.
6. Controleer in het knooppunt **Apps** van de store of u de door u gepubliceerde app ziet. Houd er rekening mee dat de app automatisch is goedgekeurd om te worden gesynchroniseerd met Intune.

## <a name="assign-an-android-for-work-app"></a>Een Android for Work-app toewijzen

Als u een app uit de store hebt goedgekeurd maar deze nog niet wordt weergegeven in het knooppunt **Apps met licentie** van de workload **Mobiele apps**, kunt u als volgt een onmiddellijke synchronisatie afdwingen:

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Mobiele apps** op de blade **Intune**.
4. Kies in de workload **Mobiele apps** achtereenvolgens **Instellen** > **Android for Work**.
5. Kies op de blade Android for Work de optie **Nu synchroniseren**.
6. Op de pagina ziet u ook de tijd en status van de laatste synchronisatie.

Als de app wordt weergegeven in het knooppunt **Apps met licentie** van de workload **Mobiele apps**, kunt u de app [toewijzen als alle andere apps](/intune-azure/manage-apps/deploy-apps). U kunt de app alleen toewijzen aan groepen gebruikers.

Nadat u de app hebt toegewezen, wordt deze geïnstalleerd op de doel-apparaten. De gebruiker van het apparaat wordt geen toestemming voor de installatie gevraagd.

## <a name="manage-app-permissions"></a>App-machtigingen beheren
Bij Android for Work moet u apps goedkeuren in de door Google beheerde Play-webconsole voordat u ze synchroniseert met Intune en ze toewijst aan uw gebruikers.  Met Android for Work kunt u de apps op de achtergrond en automatisch naar de apparaten van gebruikers pushen en daarom moet u de machtigingen voor de app namens al uw gebruikers accepteren.  Eindgebruikers krijgen geen app-machtigingen te zien wanneer ze de installatie uitvoeren, dus het is belangrijk dat u de informatie over de machtigingen leest en dat u ze begrijpt.

Wanneer een app-ontwikkelaar een nieuwe versie van de app publiceert met bijgewerkte machtigingen, worden de machtigingen niet automatisch geaccepteerd, zelfs niet wanneer u de vorige machtigingen ook al had goedgekeurd. Apparaten waarop de oude versie van de app wordt uitgevoerd, kunnen de app nog wel gebruiken. De app wordt pas geüpgraded wanneer de nieuwe machtigingen zijn goedgekeurd. Op apparaten waar de app niet op is geïnstalleerd, kan deze pas worden geïnstalleerd wanneer de nieuwe machtigingen voor de app zijn goedgekeurd.

### <a name="how-to-update-app-permissions"></a>App-machtigingen bijwerken

Ga met enige regelmaat naar de beheerde Google Play-console om te controleren op nieuwe machtigingen. Als u een app toewijst en u ziet dat deze niet is geïnstalleerd op apparaten, controleert u aan de hand van de volgende stappen op nieuwe machtigingen:

1. Ga naar http://play.google.com/work
2. Meld u aan met het Google-account dat u gebruikt om apps te publiceren en goed te keuren.
3. Ga naar het tabblad **Updates** tabblad om te bekijken of er apps zijn die moeten worden bijgewerkt.  Voor alle vermelde apps zijn nieuwe machtigingen vereist. De apps worden pas toegewezen wanneer de machtigingen zijn toegepast.  

