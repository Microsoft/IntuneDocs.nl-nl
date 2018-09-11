---
title: Inleiding tot Intune in de Azure-portal
titlesuffix: ''
description: Microsoft Intune is beschikbaar in Azure Portal. Kom meer te weten over Intune in Azure Portal.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/28/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: get-started
ms.openlocfilehash: 3f8f0dce416c943dbc244d0e2a4366b12b305708
ms.sourcegitcommit: 18f51ae8291b57562921e40fc364a5a60a59b139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2018
ms.locfileid: "44253779"
---
# <a name="introduction-to-microsoft-intune-in-the-azure-portal"></a>Inleiding op Microsoft Intune in Azure Portal


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Net als andere Azure-services is Microsoft Intune beschikbaar in Azure Portal. Als u **Intune** selecteert in Azure Portal, kunt u de mobiele apparaten, pc's en apps van uw organisatie beheren.

> [!NOTE]
> Als u een eerdere versie van Microsoft Intune hebt gebruikt, is de volgende informatie mogelijk nuttig voor u:
>     * In [Waar is de functie die ik zoek gebleven in Azure?](ui-changes.md) kunt u nazoeken welke specifieke werkstromen en gebruiksinterfaces zijn veranderd bij de overgang naar Azure.
>     * In [Klassieke Intune-groepen in Azure Portal](groups-get-started.md) worden de gevolgen uitgelegd van de overstap naar Azure Active Directory-beveiligingsgroepen voor groepsbeheer.

Belangrijke functies van de Microsoft Intune-ervaring in Azure Portal zijn onder andere:

- Een geïntegreerde console voor al uw Enterprise Mobility + Security-onderdelen (EMS)
- Een console op basis van HTML die is gebouwd op webstandaarden
- Ondersteuning van Microsoft Graph API om veel acties te automatiseren
- Azure Active Directory-groepen (AD) voor compatibiliteit voor al uw Azure-toepassingen
- Ondersteuning voor de meeste moderne webbrowsers

## <a name="before-you-start"></a>Voordat u begint

U moet een Intune-beheerder- en tenant-account hebben voor het gebruik van Intune in de Azure Portal. [Meld u aan voor een account](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) als u er nog geen hebt.

## <a name="supported-web-browsers-for-the-azure-portal"></a>Ondersteunde webbrowsers voor de Azure Portal

Azure Portal is geschikt voor de meeste moderne pc's, Macs en tablets. Mobiele telefoons worden niet ondersteund.
Momenteel worden de volgende webbrowsers ondersteund:

- Microsoft Edge (meest recente versie)
- Microsoft Internet Explorer 11
- Safari (meest recente versie, alleen Mac)
- Chrome (meest recente versie)
- Firefox (meest recente versie)

Controleer [Azure Portal](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices) voor de meest recente informatie over ondersteunde browsers.

## <a name="microsoft-intune-in-the-azure-portal"></a>Microsoft Intune in Azure Portal

U vindt de Microsoft Intune-service in [Azure Portal](https://portal.azure.com). Er zijn meerdere services beschikbaar in Azure, waarvan u een aantal wellicht niet regelmatig gebruikt. Zie [Aan de slag met Intune in Azure Portal](get-started-azure.md) voor een korte handleiding voor het aanpassen van uw portal-ervaring.

## <a name="the-microsoft-intune-documentation"></a>Documentatie voor Microsoft Intune

Dit onderwerp wordt net als de gehele Microsoft Intune-documentatieset voortdurend bijgewerkt. Als u suggesties hebt, kunt u feedback geven in de opmerkingen bij onderwerpen. We graag horen van u.

De documentatie volgt de indeling van Microsoft Intune in Azure Portal (zie hieronder), zodat u snel de gewenste informatie vindt.

![Workloads in de Azure Portal](./media/azure-portal-workloads.png)

### <a name="documentation-guide"></a>Documentatiehandleiding

Gebruik de volgende tabel om snel de belangrijkste gedeelten van Microsoft Intune te vinden en te begrijpen.

| Sectie                                                      | Description                                                                                                                                                                                                                                                                                      |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Inleiding en aan de slag](introduction-intune.md)       | Inzicht in de basisbeginselen van Intune, waaronder:<br /> - Algemene oplossingen<br /> - De manier waarop Microsoft Intune werkt<br /> - Apparaatbeheer in Intune<br /> - App-beheer in Intune<br /> - Enterprise Mobility Management (EMM) met en zonder apparaatinschrijving                                                         |
| [Plannen en ontwerpen](planning-guide.md)                         | Richtlijnen om uw Microsoft Intune-omgeving te plannen en te ontwerpen.                                                                                                                                                                                                             |
| [Apparaatinschrijving](device-enrollment.md)                    | Informatie over hoe u met Microsoft Intune de apparaten van uw werknemers kunt beheren door de apparaten te registreren voor de Intune-service. Er zijn verschillende methoden om de apparaten van uw werknemers te registreren.                                                                                                         |
| [Apparaatnaleving](device-compliance.md)                    | Het Intune-apparaatnalevingsbeleid bevat de regels en instellingen waaraan een apparaat moet voldoen om ook te voldoen aan het beleid van Microsoft Intune. Voorbeelden van naleving zijn een wachtwoord vereisen voor toegang tot een apparaat, apparaten versleutelen en een minimale versie van het besturingssysteem vereisen. |
| [Apparaatconfiguratie](device-profiles.md)                   | U kunt de instellingen en functies configureren op alle apparaten die u beheert met Microsoft Intune door apparaatprofielen te maken. U kunt bijvoorbeeld mogelijkheden configureren als meldingen, gegevensdeling, e-mailondersteuning, Wi-Fi-connectiviteit, certificaten en beveiliging van eindpunten.              |
| [Apparaten](device-management.md)                              | U kunt ervoor zorgen dat apparaten die u beheert de bronnen leveren waarmee uw eindgebruikers hun werk kunnen doen, terwijl u de gegevens van uw bedrijf beveiligt tegen risico's. U kunt apparaten beheren door de apparaatinventarisatie van de werknemers te controleren en externe apparaatacties uit te voeren.                                                      |
| [Mobiele apps](app-management.md)                             | Begrijpen hoe u apps kunt toevoegen, implementeren, bewaken, configureren en beveiligen.                                                                                                                                                                                                                             |
| [Voorwaardelijke toegang](conditional-access.md)                  | U kunt op apparaten en apps gebaseerde voorwaarden opgeven die de toegang tot uw bedrijfsgegevens beperken.                                                                                                                                                                                                            |
| [Gebruikers](users-add.md)                                        | Informatie over het toevoegen van gebruikers van apparaten en apps die u beheert.                                                                                                                                                                                                                                           |
| [Groepen](groups-get-started.md)                              | Meer informatie over het maken en beheren van groepen met Intune. Met behulp van groepen kunt u snel configuratie- en beveiligingsbeleid voor apparaten en apps toewijzen.                                                                                                                                             |
| [Intune-rollen](role-based-access-control.md)                 | Meer informatie over hoe u kunt bepalen welke personen verschillende Intune-acties kunnen uitvoeren en op welke personen deze acties van toepassing zijn. U kunt de ingebouwde rollen gebruiken die voorzien in bepaalde algemene Intune-scenario's of u kunt uw eigen rollen maken.                                                                                 |
| [Software-updates](windows-update-for-business-configure.md) | Meer informatie over de configuratie van software-updates voor Windows 10-apparaten.                                                                                                                                                                                                                                  |

## <a name="whats-new"></a>Wat is er nieuw?

Zie [Wat is er nieuw](whats-new.md) voor meer informatie over de nieuwste mogelijkheden met Microsoft Intune.
