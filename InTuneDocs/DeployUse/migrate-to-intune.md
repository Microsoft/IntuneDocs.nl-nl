---
# required metadata

title: Migreren naar Intune | Microsoft Intune
description:
keywords:
author: jeffgilb
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 88936b8a-7453-4410-b6db-29f636ba3e72

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Migreren naar Intune


Voor de migratie naar Intune vanuit uw bestaande oplossing voor het beheer van bedrijfsmobiliteit kunt u de onderstaande algemene volgorde van stappen volgen:

![Migratiestappen voor Intune](./media/migrate-intune-steps.png)

## Gebruikers op de hoogte stellen

Wanneer u zeker weet dat de Intune-pilotimplementatie aan uw vereisten voldoet, kunt u uw gebruikers op de hoogte stellen van de aanstaande migratie van hun apparaten naar Intune. Via e-mailberichten, [instructies](http://www.microsoft.com/en-us/download/details.aspx?id=46398) en [posters](https://gallery.technet.microsoft.com/Intune-End-User-Enrollment-3a0c9b0c?WT.mc_id=Blog_Intune_General_PCIT) kunt u gebruikers duidelijk maken wat er gaat veranderen en informatie bieden over de inschrijving. Zo weten gebruikers wat ze moeten doen om toegang te houden tot bedrijfsbronnen en -toepassingen. Zorg ervoor dat het ondersteuningsteam gereed is om gebruikers te helpen met het migratieproces.

## Uw bestaande oplossing voor het beheer van bedrijfsmobiliteit wijzigen

Afhankelijk van hoe u van plan bent om beleidsregels voor voorwaardelijke toegang af te handelen tussen uw bestaande oplossing voor het beheer van bedrijfsmobiliteit en Intune, moet u mogelijk uw bestaande beleidsregels voor voorwaardelijke toegang uitschakelen. U moet uw bestaande beleidsregels voor voorwaardelijke toegang uitschakelen OF het bereik van de bestaande beleidsregels voor voorwaardelijke toegang zo instellen dat deze geen gebruikers/apparaten omvatten die op het punt staan naar Intune te worden gemigreerd.  Zorg ervoor dat niet zowel Intune als uw bestaande oplossing voor het beheer van bedrijfsmobiliteit op dezelfde gebruikers/apparaten beleid voor voorwaardelijke toegang toepast.

## Intune-beleid voor voorwaardelijke toegang inschakelen (optioneel)

Als u hebt besloten om het beleid voor voorwaardelijke toegang onmiddellijk af te dwingen zonder een respijtperiode voor het migreren van apparaten, schakelt u in deze stap het beleid voor voorwaardelijke toegang in Intune in.  Zorg ervoor dat deze beslissing goed wordt gecommuniceerd met uw gebruikers en het helpdeskteam.  Als apparaten niet worden ingeschreven bij Intune en niet compatibel zijn met Intune-beleid, kunnen gebruikers pas toegang krijgen tot bedrijfsbronnen als ze zijn ingeschreven bij Intune en de apparaten compatibel zijn met het Intune-beleid.

## Apparaten uitschrijven bij uw bestaande oplossing voor het beheer van bedrijfsmobiliteit

Apparaten moeten worden uitgeschreven uit uw bestaande oplossing voor het beheer van bedrijfsmobiliteit voordat ze kunnen worden ingeschreven bij Intune. Voor de beste gebruikerservaring bevelen we aan dat gebruikers hun apparaten zelf uitschrijven.  Het is belangrijk dat de richtlijnen voor uitschrijven van de aanbieder van de oplossing worden gevolgd. Zo zorgt u ervoor dat gebruikers en apparaten correct van het platform worden verwijderd en de onderbreking voor uw eindgebruikers zo kort mogelijk is.

## Apparaten inschrijven bij Intune

Gebruikers die zijn aangewezen voor migratie, moeten zich direct inschrijven bij Intune om verlies van toegang tot bedrijfsbronnen, e-mail en toepassingen te voorkomen of om weer toegang tot bedrijfsbronnen, e-mail en toepassingen te krijgen. Als u voorwaardelijke toegang hebt geconfigureerd en gebruikers verbinding met hun e-mailaccount proberen te maken voordat ze bij Intune zijn ingeschreven, wordt hun toegang geblokkeerd en ontvangen ze een inschrijvingse-mail. Deze e-mail bevat stappen waarmee ze hun apparaat bij Intune kunnen inschrijven.  Gebruikers kunnen zich ook inschrijven bij Intune via de Intune-bedrijfsportal-app of via het besturingssysteem (Windows 8.1 en Windows 10 Mobile). Raadpleeg [Wat u uw eindgebruikers vertelt over het gebruik van Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md) voor verdere platformspecifieke richtlijnen voor inschrijving.

## Intune-beleid voor voorwaardelijke toegang configureren (optioneel)

Als u een respijtperiode voor afdwinging van voorwaardelijke toegang hebt ingesteld, schakelt u het beleid voor voorwaardelijke toegang in Intune in om afdwinging te starten wanneer de respijtperiode die u hebt doorgegeven aan uw eindgebruikers, is beëindigd. Vanaf dat moment moeten alle apparaten onmiddellijk voldoen aan de vereisten van het Intune-beleid voor voorwaardelijke toegang.

## Resterende apparaten en gebruikers inschrijven

Nu u voorwaardelijke toegang hebt ingeschakeld, moeten alle gebruikers zich inschrijven bij Intune en voldoen aan het nalevingsbeleid van uw organisatie om toegang te krijgen tot bedrijfsbronnen. Als u uw gebruikers via gefaseerde inschrijving (niet alle gebruikers tegelijk) migreert, herhaalt u bovenstaande stappen totdat alle apparaten en gebruikers zijn ingeschreven bij en worden beheerd door Intune.

## De vorige oplossing voor het beheer van bedrijfsmobiliteit buiten gebruik stellen

Nadat u alle gebruikers en apparaten naar Intune hebt gemigreerd en hebt gecontroleerd of de migratie succesvol is verlopen, kunt u de vorige oplossing voor het beheer van bedrijfsmobiliteit buiten gebruik stellen en/of uw abonnement op de betreffende service beëindigen. Het is belangrijk dat u de instructies van de aanbieder van de oplossing volgt om ervoor te zorgen dat u eventuele overbodige infrastructuurvereisten correct verwijdert en alle abonnementen/licenties annuleert.

## Aanvullende bronnen voor migratie

Hebt u extra hulp nodig met de migratie naar Intune? We bieden deskundige ondersteuningsopties om ervoor te zorgen dat de migratie probleemloos verloopt:

<!--- - [Microsoft Intune Onboarding](/em/solutions/fasttrack-center-benefit-for-enterprise-mobility-suite-ems)--->
- [Ondersteuningsdiensten van Microsoft](https://www.microsoft.com/en-us/microsoftservices/default.aspx)
- [Technische en niet-technische ondersteuning voor Intune](/intune/troubleshoot/how-to-get-support-for-microsoft-intune)
- [Microsoft Intune TechNet-forum](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

## Download deze handleiding

Ga naar de [TechNet-galerie](https://gallery.technet.microsoft.com/Migrating-to-Intune-ea439387) als u een exemplaar van deze volledige handleiding wilt downloaden..


<!--HONumber=May16_HO1-->


