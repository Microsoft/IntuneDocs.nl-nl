---
# required metadata

title: Algemene tips voor probleemoplossing | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Algemene tips voor probleemoplossing voor Microsoft Intune
Nadat u Microsoft Intune hebt geïmplementeerd, kunnen er problemen optreden met de configuratie van clients. De onderstaande resources helpen u mogelijk de oorzaak van het probleem te achterhalen, zodat u het kunt oplossen.

> [!NOTE]
> Als u een verzoek om ondersteuning wilt indienen of een bestaande aanvraag wilt weergeven, klikt u [hier](https://portal.office.com/admin/default.aspx) om naar het Office 365-beheercentrum te gaan. Zie [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md) voor meer informatie over ondersteuningsopties..
## Het probleem definiëren

-   Wat is het gedrag?

-   Wie ervaart dit gedrag, en op welke platforms en apparaten?

-   Werkte het apparaat eerder wel goed?

-   Welke wijzigingen hebt u aangebracht in de configuratie van Intune of het apparaat?

-   Ga na of er andere wijzigingen zijn aangebracht in de omgeving waarin u werkt, anders dan configuratiewijzigingen.

-   Hoe vaak treedt dit probleem op en is het sporadisch of consistent?

-   Kan de gebruiker mogelijk een verificatieprobleem ervaren? Als dit een mogelijkheid is, controleer dan of de gebruiker zich kan aanmelden bij andere services die gebruikmaken van Azure Active Directory. Controleer ook of de gebruiker zich vanaf een ander apparaat kan aanmelden.

## Beschikbare gegevens verzamelen

-   Apparaatlogboeken Meer informatie over het verzamelen van apparaatlogboeken vindt u in:
  - [Logboeken met diagnostische gegevens over Android naar de IT-beheerder verzenden via een USB-kabel](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Logboeken met diagnostische gegevens over Android naar de IT-beheerder verzenden via e-mail](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
  - [Android-inschrijvingsfouten verzenden naar de IT-beheerder](/intune/enduser/send-enrollment-errors-to-your-it-administrator-android)
  - [iOS-inschrijvingsfouten verzenden naar de IT-beheerder](/intune/enduser/send-errors-to-your-it-admin-ios.md)

-   Beheerconsolegegevens; voor problemen met implementatie van beleid moet u bijvoorbeeld het gewenste beleid en de status van dit beleid onderzoeken, zoals beschreven in [Groepen gebruiken voor het beheren van gebruikers en apparaten met Microsoft Intune](/indune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune)..

## Onderzoek doen naar de oplossing

-   Zoek op internet naar een oplossing. Als u bijvoorbeeld de fout 0x80073CF0 ontvangt, kunt u zoeken naar **technet intune 0x80073cf0** op internet en het artikel [Problemen met app-implementaties oplossen in Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md) opzoeken, dat suggesties bevat voor het aanpakken van dit probleem.

-   U kunt zoeken naar een antwoord op het [Intune TechNet-forum](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  Als het probleem niet eerder is besproken, moet u een vraag plaatsen om te zien welke suggesties de community mogelijk heeft.

-   U kunt een ondersteuningsaanvraag openen. De Intune-ondersteuning kan u beter helpen bij het oplossen van een probleem wanneer u het probleem hebt gedefinieerd en de beschikbare gegevens hebt verzameld.

    Als u een verzoek om ondersteuning wilt indienen, klikt u [hier](https://portal.office.com/admin/default.aspx) om naar het Office 365-beheercentrum te gaan. Zie [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md) voor meer informatie over ondersteuningsopties..

## Communityresources
U vindt andere nuttige informatie in de volgende communityresources:

-   De [Microsoft Intune Survival Guide](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) bevat koppelingen naar veel resources die u kunnen helpen bij het configureren, onderhouden en oplossen van problemen met Intune.

-   [De Intune-blog](http://blogs.technet.com/b/windowsintune/)

-   [Volg Intune op Twitter](https://twitter.com/MSIntune)

-   [De Intune-forums](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

## Volgende stappen
Onderstaande onderwerpen bieden probleemoplossing voor specifieke problemen. Als deze informatie geen oplossing biedt, kunt u contact opnemen met Microsoft Support zoals beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md)..

[Troubleshoot Endpoint Protection in Microsoft Intune](troubleshoot-endpoint-protection-in-microsoft-intune.md)

[Problemen bij toegang tot bedrijfsbronnen oplossen met Microsoft Intune](troubleshoot-company-resource-access-problems-with-microsoft-intune.md)

[Problemen met app-implementaties oplossen in Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md)

[Problemen bij de apparaatinschrijving oplossen](troubleshoot-device-enrollment-in-intune.md)

[Beleidsproblemen oplossen in Microsoft Intune](troubleshoot-policies-in-microsoft-intune.md)

[Problemen met de clientinstallatie oplossen in Microsoft Intune](troubleshoot-client-setup-in-microsoft-intune.md)

[Problemen met software-updates oplossen in Microsoft Intune](troubleshoot-software-updates-in-microsoft-intune.md)
g


<!--HONumber=May16_HO1-->


