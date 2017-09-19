---
title: Apps implementeren op Android for Work-apparaten
description: Dit onderwerp bevat procedures voor het synchroniseren en het vervolgens implementeren van apps op Android for Work-apparaten uit de Google Play for Work-store.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd0bbd90-d3fe-4efc-83fd-d1f3f86800d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0a00c3dd1f6b6b8066a568c87f304a4da374f4d7
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/15/2017
---
# <a name="how-to-deploy-apps-to-android-for-work-devices-with-intune"></a>Apps implementeren op Android for Work-apparaten met Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

U implementeert apps op Android for Work-apparaten op een andere manier dan op standaard-Android-apparaten. Alle apps die u installeert voor Android for Work, zijn afkomstig uit de Google Play for Work-store. U meldt zich aan bij de store, bladert naar de gewenste apps en keurt deze goed.
De app wordt dan weergegeven in het knooppunt **Apps die zijn gekocht via het volume-aankoopprogramma** van de Intune-console. Hier kunt u de implementatie van de app beheren op dezelfde manier als implementaties van andere apps.

Als u uw eigen LOB-apps (Line-Of-Business) hebt gemaakt, kunt u deze als volgt implementeren:
- Meld u aan voor een Google-ontwikkelaarsaccount, zodat u apps kunt publiceren naar een privégebied in de Google Play-store.
- Synchroniseer de apps met Intune.

## <a name="before-you-start"></a>Voordat u begint

Zorg ervoor dat u Intune en Android for Work hebt geconfigureerd voor samenwerking op het tabblad **Beheer** van de Intune-console.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Een app uit de Google Play for Work-store synchroniseren


1. Ga naar de [Google Play for Work-store](https://play.google.com/work). Meld u aan met hetzelfde account dat u hebt gebruikt om de verbinding tussen Intune en Android for Work te configureren.
2. Zoek in de store naar de app die u wilt implementeren met Intune.
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
6. Controleer in het knooppunt **Apps** van de store of u de door u gepubliceerde app ziet. De app wordt automatisch goedgekeurd voor de synchronisatie met Intune.

## <a name="deploy-an-android-for-work-app"></a>Een Android for Work-app implementeren

Als u een app uit de store hebt goedgekeurd maar deze niet wordt weergegeven in het knooppunt **Apps die zijn gekocht via het volume-aankoopprogramma** van de werkruimte **Apps**, kunt u als volgt een onmiddellijke synchronisatie afdwingen:

1. Kies in de [Intune-beheerdersconsole](https://manage.microsoft.com) de optie **Beheer** > **Beheer van mobiele apparaten** > **Android for Work**.
2. Kies op de pagina **Instellingen voor beheer van mobiele apparaten voor Android for Work** de optie **Nu synchroniseren**.
3. Op de pagina ziet u ook de tijd en status van de laatste synchronisatie.

Wanneer de app wordt weergegeven in het knooppunt **Apps die zijn gekocht via het volume-aankoopprogramma** van de werkruimte **Apps**, kunt u [deze implementeren zoals elke andere app](deploy-apps-in-microsoft-intune.md). U kunt de app implementeren voor groepen of specifieke gebruikers. Op dit moment kunt u alleen de acties **Vereist** en **Verwijderen** selecteren.

Bij de mogelijkheid om een app als **Beschikbaar** te implementeren, wordt de nieuwe groeperings- en targetingervaring toegepast. Nieuw ingerichte Intune-serviceaccounts kunnen deze functie gebruiken na de introductie. Bestaande Intune-klanten kunnen deze functie gebruiken zodra de tenant is gemigreerd naar de Intune Azure Portal. Bestaande klanten kunnen een Intune-proefaccount maken om deze functie te plannen en te testen tot hun tenant is gemigreerd.

Nadat u de app hebt geïmplementeerd, wordt deze geïnstalleerd op de opgegeven apparaten. De gebruiker van het apparaat wordt hiervoor niet om toestemming gevraagd.

## <a name="manage-app-permissions"></a>App-machtigingen beheren
Bij Android for Work moet u apps goedkeuren in de door Google beheerde Play-webconsole voordat u ze synchroniseert met Intune en ze implementeert voor uw gebruikers.  Met Android for Work kunt u de apps op de achtergrond en automatisch naar de apparaten van gebruikers pushen en daarom moet u de machtigingen voor de app namens al uw gebruikers accepteren.  Eindgebruikers krijgen geen app-machtigingen te zien wanneer ze de installatie uitvoeren. Het is dus belangrijk dat u de informatie over de machtigingen leest en begrijpt.

Wanneer een app-ontwikkelaar een nieuwe versie van de app publiceert met bijgewerkte machtigingen, worden de machtigingen niet automatisch geaccepteerd, zelfs niet wanneer u de vorige machtigingen ook al had goedgekeurd. Apparaten waarop de oude versie van de app wordt uitgevoerd, kunnen de app nog wel gebruiken. Er wordt pas een upgrade voor de app uitgevoerd wanneer de nieuwe machtigingen zijn goedgekeurd. Op apparaten waar de app niet op is geïnstalleerd, kan deze pas worden geïnstalleerd wanneer de nieuwe machtigingen voor de app zijn goedgekeurd.

### <a name="how-to-update-app-permissions"></a>App-machtigingen bijwerken

Bezoek met enige regelmaat de beheerde Google Play-console om te controleren op nieuwe machtigingen. U kunt de Google Play zodanig configureren dat u of anderen een e-mailbericht ontvangen wanneer nieuwe machtigingen voor een goedgekeurde app zijn vereist. Als u een app toewijst en u ziet dat deze niet is geïnstalleerd op apparaten, controleert u aan de hand van de volgende stappen op nieuwe machtigingen:

1. Ga naar http://play.google.com/work
2. Meld u aan met het Google-account dat u gebruikt om apps te publiceren en goed te keuren.
3. Ga naar het tabblad **Updates** tabblad om te bekijken of er apps zijn die moeten worden bijgewerkt.  Voor alle vermelde apps zijn nieuwe machtigingen vereist. De apps worden pas toegewezen wanneer de machtigingen zijn toegepast.  

U kunt Google Play eventueel ook zodanig configureren dat de app-machtigingen per app automatisch opnieuw worden goedgekeurd. 
