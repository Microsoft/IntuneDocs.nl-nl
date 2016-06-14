---
# required metadata

title: Uw computer is al ingeschreven | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8d3a40f5-99e9-48dc-9706-f7a3a23e5704

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Uw computer is al geregistreerd
U ziet deze pagina omdat u Setup voor de Intune-clientsoftware hebt gestart. De software is echter al op uw computer geïnstalleerd en Setup kan niet worden voortgezet.

Dit kan de volgende redenen hebben:

-   De clientsoftware is eerder geïnstalleerd en Setup is opnieuw gestart.

-   Setup is uitgevoerd op de computer nadat een IT-beheerder uw apparaat uit Intune heeft teruggetrokken. Het kan dan enkele uren duren voordat de clientsoftware van uw computer is verwijderd.

-   Setup heeft een onlangs mislukte installatie of verwijdering van de clientsoftware ontdekt.

## Wat Setup op uw computer installeert
Setup installeert de Intune-client. Nadat Setup is voltooid, blijft de clientsoftware actief op de achtergrond waar uw computer wordt geconfigureerd voor gebruik met Intune. Dit proces kan even duren en er vindt het volgende plaats:

-   Uw computer wordt ingeschreven bij Intune

-   De inventarisatie over de computerhardware en de geïnstalleerde software wordt ingediend

-   Het Intune-beleid wordt geconfigureerd, inclusief de installatie van Endpoint Protection (indien geconfigureerd)

-   Intune Center installeren

Nadat Intune Center is geïnstalleerd, kunt u hiermee toegang tot de bedrijfsportal krijgen, waar u uw computer kunt koppelen aan uw werkaccount.

## Microsoft Intune Center
Het Intune Center wordt als een app op uw computer geïnstalleerd nadat de clientsoftware is geïnstalleerd en uw computer bij Intune is ingeschreven. U kunt Intune Center voor het volgende gebruiken:

-   **Toepassingen downloaden van de bedrijfsportal**: apps zoeken en installeren die door uw IT-beheerder zijn geïmplementeerd. Als u zich voor de eerste keer aanmeldt bij de bedrijfsportal op een onlangs ingeschreven computer, krijgt u de mogelijkheid om uw werkaccount aan die computer te koppelen.

-   **Controleren op software-updates**: software-updates zoeken die door uw Intune-beheerder zijn geïmplementeerd.

-   **Een Endpoint Protection-scan van uw computer starten**: u kunt een scan op schadelijke software op uw computer starten.

-   **Hulp op afstand vragen**: deze optie is alleen beschikbaar als hulp op afstand wordt ondersteund door het besturingssysteem van de computer.

## Controleren of de clientsoftware is geïnstalleerd of verwijderd
**Controleer of de client is geïnstalleerd:**
De Intune-clientinstallatie is voltooid als de volgende apps op de computer beschikbaar zijn:

-   **Intune Center**

-   **Intune Endpoint Protection** (als Endpoint Protection is ingeschakeld door de IT-beheerder)

Als u vertrouwd bent met het gebruik van Taakbeheer, kunt u zoeken naar de Intune-clientservice, die moet worden uitgevoerd:

-   **OmcSvc**

**Controleer of de client is verwijderd:**
Nadat de Intune-client van een computer is verwijderd, zijn ook de apps verwijderd die met de client zijn geïnstalleerd (waaronder Intune Center).

De Intune-clientservice **OmcSvc** wordt verwijderd.

## De clientsoftware van de computer verwijderen
Nadat de IT-beheerder uw computer uit de Intune-beheerconsole heeft gehaald, is de Intune-clientsoftware standaard enkele uren later verwijderd.

Als u de Intune-clientsoftware handmatig van een computer wilt verwijderen, kunt u de volgende stappen gebruiken om het verwijderen af te dwingen:

1.  Open in de beheerdersmodus een opdrachtprompt op de computer.

2.  Ga naar de map **%programfiles%\Microsoft\OnlineManagement\Common**

3.  Voer de volgende opdracht uit: **ProvisioningUtil.exe /UninstallAgents /MicrosoftIntune**

Hiermee wordt het verwijderen van de clientsoftware gepland.



<!--HONumber=May16_HO1-->


