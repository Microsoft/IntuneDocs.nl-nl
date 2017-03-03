---
title: Algemene tips voor probleemoplossing | Microsoft Docs
description: Algemene bronnen voor hulp bij het oplossen van problemen met Intune.
keywords: 
author: staciebarker
manager: angrobe
ms.date: 12/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: d05c9d7a78474c19e142bca94e232289fbfba1d9
ms.openlocfilehash: ef6c482a45a7c759cec1062b129d2644562d0da2
ms.lasthandoff: 01/10/2017


---

# <a name="general-troubleshooting-tips-for-microsoft-intune"></a>Algemene tips voor probleemoplossing voor Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Nadat u Microsoft Intune hebt geïmplementeerd, kunnen er problemen optreden met de configuratie van clientapparaten. Gebruik de volgende resources om de oorzaak van het probleem te achterhalen zodat u het kunt oplossen.

> [!NOTE]
> Als u een ondersteuningsaanvraag wilt indienen of een bestaande aanvraag wilt bekijken, kunt u [het Office 365-beheercentrum bezoeken](https://portal.office.com/admin/default.aspx). Zie [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md) voor meer informatie over ondersteuningsopties.

## <a name="define-the-problem"></a>Het probleem definiëren

-   Wat is het gedrag?

-   Wie ervaart dit gedrag, en op welke platformen en apparaten?

-   Werkte het apparaat eerder wel goed?

-   Welke wijzigingen hebt u aangebracht in de configuratie van Intune of het apparaat?

-   Zijn er nog andere wijzigingen dan configuratiewijzigingen aangebracht in de omgeving waarin u werkt?

-   Hoe vaak treedt dit probleem op en is het sporadisch of consistent?

-   Kan de gebruiker mogelijk een verificatieprobleem ervaren? Als dit een mogelijkheid is, controleert u of de gebruiker zich kan aanmelden bij andere services die gebruikmaken van Azure Active Directory. Controleer ook of de gebruiker zich vanaf een ander apparaat kan aanmelden.

-   Hebt u de status van de service gecontroleerd? U kunt de servicestatus van Intune bewaken in de [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx). Kies **Servicestatus** in het linkerdeelvenster.

## <a name="collect-available-data"></a>Beschikbare gegevens verzamelen

-   De volgende resources bevatten meer informatie over het verzamelen van logboeken van apparaten:
  - [Logboeken met diagnostische gegevens over Android naar de IT-beheerder verzenden via een USB-kabel](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Logboeken met diagnostische gegevens over Android naar de IT-beheerder verzenden via e-mail](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
  - [Android-registratiefouten verzenden naar de IT-beheerder](/intune/enduser/send-enrollment-errors-to-your-it-administrator-android)
  - [iOS-registratiefouten verzenden naar de IT-beheerder](/intune/enduser/send-errors-to-your-it-admin-ios)

-   Met beheerconsolegegevens (bijvoorbeeld voor problemen met de implementatie van beleid) kunt u het gewenste beleid en de status van dit beleid onderzoeken, zoals beschreven in [Groepen gebruiken voor het beheren van gebruikers en apparaten met Microsoft Intune](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

## <a name="research-the-solution"></a>Onderzoek doen naar de oplossing

-   Zoek op internet naar een oplossing. Als u bijvoorbeeld de fout 0x80073CF0 ontvangt en op internet zoekt op **technet intune 0x80073cf0**, vindt u het artikel [Problemen met app-implementaties oplossen in Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md). Dit artikel bevat suggesties voor het verhelpen van deze fout.

-   Zoek een antwoord op het [Intune TechNet-forum](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  Als het probleem niet eerder is besproken, kunt u een vraag plaatsen om te zien welke suggesties de community mogelijk heeft.

-   Open een ondersteuningsaanvraag openen. De Intune-ondersteuning kan u beter helpen bij het oplossen van een probleem wanneer u het probleem hebt gedefinieerd en de beschikbare gegevens hebt verzameld.

    Als u een ondersteuningsaanvraag wilt maken, [bezoekt u het Office 365-beheercentrum](https://portal.office.com/admin/default.aspx). Zie [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md) voor meer informatie over ondersteuningsopties.

## <a name="find-community-resources"></a>Communityresources zoeken
U vindt andere nuttige informatie in de volgende communityresources:

-   De [Microsoft Intune Survival Guide](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) bevat koppelingen naar veel resources die u kunnen helpen bij het configureren, onderhouden en oplossen van problemen met Intune.

-   [De Intune-blog](http://blogs.technet.com/b/windowsintune/)

-   [Volg Intune op Twitter](https://twitter.com/MSIntune)

-   [De Intune-forums](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

### <a name="next-steps"></a>Volgende stappen
De volgende onderwerpen bieden mogelijke oplossingen voor specifieke problemen. Als deze informatie geen oplossing biedt, kunt u contact opnemen met Microsoft Support zoals beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).

[Troubleshoot Endpoint Protection in Microsoft Intune](troubleshoot-endpoint-protection-in-microsoft-intune.md) (Engelstalig)

[Problemen bij toegang tot bedrijfsbronnen oplossen met Microsoft Intune](troubleshoot-company-resource-access-problems-with-microsoft-intune.md)

[Problemen met app-implementaties oplossen in Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md)

[Problemen bij de apparaatinschrijving oplossen](troubleshoot-device-enrollment-in-intune.md)

[Beleidsproblemen oplossen in Microsoft Intune](troubleshoot-policies-in-microsoft-intune.md)

[Problemen met de clientinstallatie oplossen in Microsoft Intune](troubleshoot-client-setup-in-microsoft-intune.md)

[Problemen met software-updates oplossen in Microsoft Intune](troubleshoot-software-updates-in-microsoft-intune.md)

