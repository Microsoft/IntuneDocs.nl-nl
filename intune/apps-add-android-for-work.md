---
title: Apps aan Android for Work-apparaten toewijzen
titleSuffix: Intune on Azure
description: Dit onderwerp bevat procedures voor het synchroniseren en toewijzen van apps op Android for Work-apparaten uit de Google Play for Work-store.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 94394a889d97b4d1bdf09303b11cdc3688e4f55a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a>Apps aan Android for Work-apparaten toewijzen met Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

U wijst apps aan Android for Work-apparaten op een andere manier toe dan aan standaard-Android-apparaten. Alle apps die u installeert voor Android for Work, zijn afkomstig uit de Google Play for Work-store. U meldt zich aan bij de store, bladert naar de gewenste apps en keurt deze goed.
De app wordt vervolgens weergegeven in het knooppunt **Apps met licentie** van de Intune-portal. Hier kunt u de toewijzing van de app op dezelfde manier beheren als toewijzingen van andere apps.

Als u uw eigen LOB-apps (Line-Of-Business) hebt gemaakt, kunt u deze als volgt toewijzen:
- Meld u aan voor een Google-ontwikkelaarsaccount, zodat u apps kunt publiceren naar een privégebied in de Google Play-store.
- Synchroniseer de apps met Intune.

## <a name="before-you-start"></a>Voordat u begint

Zorg ervoor dat u Intune en Android for Work hebt geconfigureerd voor samenwerking in de workload **Apparaatinschrijving** van de Intune-portal.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Een app uit de Google Play for Work-store synchroniseren

1. Ga naar de [Google Play for Work-store](https://play.google.com/work). Meld u aan met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android for Work te configureren.
2. Zoek in de store naar de app die u wilt toewijzen met Intune.
3. Kies **Goedkeuren** op de pagina voor de app die u hebt gekozen. In dit voorbeeld hebt u de app Microsoft Excel gekozen.<br>
  ![Voorbeeld van het goedkeuren van een app](media/approve.png)
4. Er wordt een venster voor de app geopend, waarin u om toestemming wordt gevraagd voor het uitvoeren van verschillende bewerkingen door de app. Kies **Goedkeuren** om door te gaan.<br>
  ![Voorbeeld van het goedkeuren van app-machtigingen](media/approve-app-permissions.png)
5. De app is goedgekeurd en wordt weergegeven in uw IT-beheerconsole.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Een Line-Of-Business-app uit de Google Play for Work-store publiceren en vervolgens synchroniseren

1. Ga naar de Google Play-ontwikkelaarsconsole, [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Meld u aan met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android for Work te configureren. Als u zich voor het eerst aanmeldt, moet u zich registreren en betalen om lid te worden van het Google-ontwikkelaarsprogramma.
3. Kies in de console **Nieuwe toepassing toevoegen**.
4. U uploadt en verstrekt informatie over uw app op dezelfde manier als bij het publiceren van een app naar de Google Play store. U moet echter wel de instelling **Deze toepassing alleen beschikbaar maken voor mijn organisatie (<*organisatienaam*>)** selecteren:<br>
  ![Optie om de app alleen beschikbaar voor uw organisatie te maken](media/restrict.png)<br>
Deze bewerking zorgt ervoor dat de app alleen beschikbaar is voor uw organisatie en niet in de openbare Google Play-store.
Zie de [Help bij de Google-ontwikkelaarsconsole](https://support.google.com/googleplay/android-developer/answer/113469) voor meer informatie over het uploaden en publiceren van Android-apps.
5. Nadat u de app hebt gepubliceerd, gaat u naar de [Google Play for Work-store](https://play.google.com/work). Meld u aan met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android for Work te configureren.
6. Controleer in het knooppunt **Apps** van de store of u de door u gepubliceerde app ziet. De app is automatisch goedgekeurd om te worden gesynchroniseerd met Intune.

## <a name="assign-an-android-for-work-app"></a>Een Android for Work-app toewijzen

Als u een app uit de store hebt goedgekeurd maar deze nog niet wordt weergegeven in het knooppunt **Apps met licentie** van de workload **Mobiele apps**, dwingt u als volgt een onmiddellijke synchronisatie af:

1. Meld u aan bij Azure Portal.
2. Kies **Mobiele apps** op de blade **Intune**.
3. Kies in de workload **Mobiele apps** achtereenvolgens **Instellen** > **Android for Work**.
4. Kies op de blade Android for Work de optie **Nu synchroniseren**.
5. Op de pagina ziet u ook de tijd en status van de laatste synchronisatie.

Als de app wordt weergegeven in het knooppunt **Apps met licentie** van de workload **Mobiele apps**, kunt u de app [toewijzen als alle andere apps](/intune-azure/manage-apps/deploy-apps). U kunt de app alleen toewijzen aan groepen gebruikers.

Nadat u de app hebt toegewezen, wordt deze geïnstalleerd op de doel-apparaten. De gebruiker van het apparaat wordt geen toestemming voor de installatie gevraagd.

## <a name="manage-android-for-work-app-permissions"></a>App-machtigingen voor Android voor Work beheren
Bij Android for Work moet u apps goedkeuren in de door Google beheerde Play-webconsole voordat u ze synchroniseert met Intune en ze toewijst aan uw gebruikers.  Met Android for Work kunt u de apps op de achtergrond en automatisch naar de apparaten van gebruikers pushen en daarom moet u de machtigingen voor de app namens al uw gebruikers accepteren.  Eindgebruikers krijgen geen app-machtigingen te zien wanneer ze de installatie uitvoeren. Het is dus belangrijk dat u de informatie over de machtigingen leest en begrijpt.

Wanneer een app-ontwikkelaar een nieuwe versie van de app publiceert met bijgewerkte machtigingen, worden de machtigingen niet automatisch geaccepteerd, zelfs niet wanneer u de vorige machtigingen ook al had goedgekeurd. Apparaten met de oude versie van de app kunnen deze nog steeds gebruiken. De app is echter niet bijgewerkt tot de nieuwe machtigingen zijn goedgekeurd. Op apparaten waar de app niet op is geïnstalleerd, worden deze pas geïnstalleerd wanneer de nieuwe machtigingen voor de app zijn goedgekeurd.

### <a name="how-to-update-app-permissions"></a>App-machtigingen bijwerken

Bezoek met enige regelmaat de beheerde Google Play-console om te controleren op nieuwe machtigingen. U kunt de Google Play zodanig configureren dat u of anderen een e-mailbericht ontvangen wanneer nieuwe machtigingen voor een goedgekeurde app zijn vereist. Als u een app toewijst en u ziet dat deze niet is geïnstalleerd op apparaten, controleert u aan de hand van de volgende stappen op nieuwe machtigingen:

1. Ga naar http://play.google.com/work
2. Meld u aan met het Google-account dat u gebruikt om apps te publiceren en goed te keuren.
3. Ga naar het tabblad **Updates** tabblad om te bekijken of er apps zijn die moeten worden bijgewerkt.  Voor alle vermelde apps zijn nieuwe machtigingen vereist. De apps worden pas toegewezen wanneer de machtigingen zijn toegepast.  

U kunt Google Play eventueel ook zodanig configureren dat de app-machtigingen per app automatisch opnieuw worden goedgekeurd. 



