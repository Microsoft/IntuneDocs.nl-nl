---
title: Endpoint Protection in macOS toevoegen in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik Gatekeeper op macOS-apparaten om te bepalen waar apps kunnen worden geïnstalleerd, inclusief de Mac App Store. Schakel met Microsoft Intune ook een firewall in of configureer een firewall die bepaalde apps toestaat, bepaalde apps blokkeert, de verborgen modus gebruikt en zelfs bepaalde typen binnenkomende verbindingen blokkeert.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 49194d49658042802cbc1148276445008ee1b09f
ms.sourcegitcommit: c3ae3c3dc46b62d9191813d25a196874ba4927be
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/28/2018
ms.locfileid: "30254550"
---
# <a name="macos-endpoint-protection-settings-in-intune"></a>Instellingen in Intune voor Endpoint Protection in macOS

In dit artikel komt u meer te weten over de Endpoint Protection-instellingen die u kunt configureren voor apparaten met macOS. Deze instellingen omvatten Gatekeeper en firewallinstellingen op deze apparaten en kunnen worden geconfigureerd met een apparaatprofiel in Microsoft Intune.

## <a name="gatekeeper"></a>Gatekeeper

- **Allow apps downloaded from these locations**  (Apps toestaan die zijn gedownload vanaf deze locaties): hiermee beperkt u apps op basis van de locatie waarvan de apps zijn gedownload. Het doel hiervan is om de apparaten te beschermen tegen malware en alleen apps toe te staan van bronnen die u vertrouwt. De opties zijn: 
  - **Mac App Store**
  - **Mac App Store en geïdentificeerde ontwikkelaars**
  - **Overal**

- **User can override Gatekeeper**  (Gebruiker kan Gatekeeper overschrijven): hiermee voorkomt u dat gebruikers de Gatekeeper-instelling kunnen overschrijven en voorkomt u dat ze op Control kunnen klikken om een app te installeren. Wanneer dit is ingeschakeld, kunnen gebruikers op Control klikken om een app te installeren.

## <a name="firewall"></a>Firewall

Gebruik de firewall om verbindingen per toepassing te beheren, in plaats van per poort. Met de instellingen per toepassing kunt u beter profiteren van de voordelen van firewallbeveiliging. Bovendien helpt het te voorkomen dat ongewenste apps gebruikmaken van netwerkpoorten die zijn geopend voor legitieme apps.

- **Gebruik de firewall om apparaten te beschermen tegen onbevoegde netwerktoegang door verbindingen op een per-app basis te beheren.**
  - **Firewall**: schakel de firewall in om te configureren hoe binnenkomende verbindingen in uw omgeving worden verwerkt.
  - **Binnenkomende verbindingen**: hiermee kunt u alle binnenkomende verbindingen blokkeren, behalve de verbindingen die vereist zijn voor basisinternetservices, zoals DHCP, Bonjour en IPSec. Hiermee worden ook alle services voor delen (zoals delen van bestanden en delen van het scherm) geblokkeerd. Als u services voor delen gebruikt, moet u **Niet geconfigureerd** gebruiken.

- **Binnenkomende verbindingen voor specifieke apps blokkeren of toestaan**
  - **Apps toegestaan**: selecteer de apps die expliciet zijn toegestaan voor het ontvangen van binnenkomende verbindingen.
  - **Apps geblokkeerd**: selecteer de apps die binnenkomende verbindingen moeten blokkeren.
  - **Verborgen modus**: schakel deze optie in om te voorkomen dat de computer reageert op peilverzoeken. Het apparaat reageert nog wel op binnenkomende verzoeken voor toegestane apps. Onverwachte aanvragen, zoals ICMP (ping), worden genegeerd.
