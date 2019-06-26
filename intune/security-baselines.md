---
title: Problemen met beveiligingsbasislijnen oplossen in Microsoft Intune - Azure | Microsoft Docs
description: Aanbevolen groepsbeveiligingsinstellingen toevoegen of configureren ter bescherming van gebruikers en gegevens op apparaten met behulp van Microsoft Intune voor Mobile Device Management. BitLocker inschakelen, Windows Defender Advanced Threat Protection configureren, Internet Explorer beheren, Smart Screen gebruiken, lokaal beveiligingsbeleid instellen, een wachtwoord vereisen, internetdownloads blokkeren en meer.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bb1ddcadcac1ec9b4730a5dcd66abca111d80196
ms.sourcegitcommit: 14f4e97de5699394684939e6f681062b5d4c1671
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2019
ms.locfileid: "67251197"
---
# <a name="create-a-windows-10-security-baseline-in-intune"></a>Een Windows 10-beveiligingsbasislijn maken in Intune

Beveiligingsbasislijnen zijn een functie in de preview-versie die beschikbaar is voor apparaten met Windows 10 en hoger. Deze functie bevat veel instellingen die door Intune worden ondersteund om uw gebruikers en apparaten te helpen beveiligen en beschermen. Deze instellingen worden ook automatisch ingesteld op waarden die zijn aanbevolen door beveiligingsteams. Door de basislijn wordt bijvoorbeeld automatisch BitLocker ingeschakeld, automatisch een wachtwoord voor het ontgrendelen van een apparaat vereist, automatisch basisverificatie uitgeschakeld, en meer.

Deze functie is van toepassing op:

- Windows 10 versie 1809 en hoger

> [!NOTE]
> Zolang de functie voor beveiligingsbasislijnen in de preview-versie is, wordt het door Microsoft niet aanbevolen profielen in een productieomgeving te gebruiken, omdat de basislijnen in de loop van de preview-versie kunnen worden gewijzigd. Wanneer beveiligingsbasislijnen algemeen beschikbaar zijn, worden bestaande profielen niet geconverteerd naar de meest recent ondersteunde profielen.

Het doel van het gebruik van beveiligingsbasislijnen is het aanbieden van een veilige end-to-end-werkstroom tijdens het werken met Microsoft 365. Enkele voordelen zijn:

- Een beveiligingsbasislijn bevat de aanbevolen procedures en aanbevelingen voor instellingen die van invloed zijn op beveiliging. Intune werkt samen met hetzelfde Windows-beveiligingsteam dat beveiligingsbasislijnen voor groepsbeleid maakt. Deze aanbevelingen zijn gebaseerd op richtlijnen en uitgebreide ervaring.
- Als u Intune voor het eerst gaat gebruiken en u niet zeker weet waar moet beginnen, bieden beveiligingsbasislijnen u een voordeel. U kunt snel een beveiligd profiel maken en implementeren, waarbij u er zeker van bent dat u de resources en de gegevens van uw organisatie helpt beschermen.
- Als u momenteel gebruikmaakt van groepsbeleid, is het met deze basislijnen veel eenvoudiger om naar Intune te migreren voor beheer. Deze basislijnen zijn standaard ingebouwd in Intune en bieden een moderne beheerervaring.

Met beveiligingsbasislijnen wordt een "configuratieprofiel" gemaakt in Intune. Dit profiel bevat alle instellingen in de basislijn. U past dit profiel vervolgens toe op uw gebruikers, groepen en apparaten.

Nadat het profiel is toegewezen, kunt u het profiel controleren en de basislijn controleren. U kunt bijvoorbeeld zien welke apparaten overeenkomen met de basislijn, of niet overeenkomen met de basislijn.

In dit artikel leest hoe u beveiligingsbasislijnen gebruikt om een profiel te maken, het profiel toe te wijzen en het profiel te controleren.

[Windows-beveiligingsbasislijnen](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) is een goede bron voor meer informatie over deze functie. [Mobile Device Management](https://docs.microsoft.com/windows/client-management/mdm/) (MDM) is een goede bron meer informatie over MDM en wat u op Windows-apparaten kunt doen.

## <a name="available-security-baselines"></a>Beschikbare beveiligingsbasislijnen  

De volgende beveiligingsbasislijnen zijn beschikbaar voor gebruik met Intune.
- **Voorbeeld: MDM-basislijn voor beveiliging voor oktober 2018**  
  [Instellingen bekijken](security-baseline-settings-windows.md)

- **PREVIEW: Windows Defender ATP-basislijn**  
  [Instellingen bekijken](security-baseline-settings-defender-atp.md)  
  *(Deze basislijn is beschikbaar als uw omgeving voldoet aan de vereisten voor het gebruik van [Microsoft Defender Advanced Threat Protection](advanced-threat-protection.md#prerequisites))* .


## <a name="prerequisites"></a>Vereisten
Als u basislijnen in Intune wilt beheren, moet de ingebouwde rol [Beleids- en profielbeheerder](role-based-access-control.md#built-in-roles) deel uitmaken van uw account.


## <a name="co-managed-devices"></a>Apparaten met co-beheer

Beveiligingsbasislijnen op met Intune-beheerde apparaten zijn vergelijkbaar met beheerde apparaten met co-beheer met Configuration Manager. Apparaten met co-beheer maken gebruik van System Center Configuration Manager en Microsoft Intune voor het tegelijkertijd beheren van de Windows 10-apparaten. Hiermee kunt u uw bestaande investering in Configuration Manager via de cloud koppelen aan de voordelen van Intune. [Overzicht van co-beheer](https://docs.microsoft.com/sccm/comanage/overview) is een goede informatiebron als u Configuration Manager gebruikt en ook wilt profiteren van de voordelen van de cloud.

Wanneer u apparaten met co-beheer gebruikt, moet u de workload **Apparaatconfiguratie** (de instellingen ervan) overschakelen naar Intune. [Workloads voor apparaatconfiguratie](https://docs.microsoft.com/sccm/comanage/workloads#device-configuration) biedt meer informatie.

## <a name="create-the-profile"></a>Het profiel maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en selecteer vervolgens **Apparaatbeveiliging** > **Beveiligingsbasislijnen (preview-versie)** . Er is een lijst van de beschikbare basislijnen beschikbaar. 

    ![Beveiligingsbasislijn selecteren om te configureren](./media/security-baselines/available-baselines.png)

   >[!TIP]  
   > De Windows Defender ATP-basislijn is beschikbaar als uw omgeving voldoet aan de vereisten voor het gebruik van [Microsoft Defender Advanced Threat Protection](advanced-threat-protection.md#prerequisites).
2. Selecteer de basislijn die u wilt gebruiken en selecteer vervolgens **Profiel maken**.  

3. Geef op het tabblad **Basisinformatie** de volgende eigenschappen op:

    - **Naam**: voer een naam in voor uw beveiligingsbasislijnprofiel. Voer bijvoorbeeld *Standaardprofiel voor Defender ATP* in
    - **Beschrijving**: voer tekst waarin wordt beschreven wat deze basislijn doet. In de beschrijving kunt u de door u gewenste tekst opgeven. Dit is optioneel, maar wordt zeker aanbevolen.

4. Selecteer het tabblad **Configuratie** om de beschikbare groepen met **instellingen** in deze basislijn weer te geven. Selecteer een groep om deze uit te vouwen en de afzonderlijke instellingen te bekijken. De instellingen hebben standaardconfiguraties voor de beveiligingsbasislijn. Pas de standaardinstellingen aan om te voldoen aan de behoeften van uw bedrijf.  

    ![Vouw een groep uit om de instellingen voor die groep weer te geven](./media/security-baselines/sample-list-of-settings.png)

5. Selecteer het tabblad **Toewijzingen** om de basislijn aan groepen toe te wijzen. Wijs de basislijn toe aan een bestaande groep, of maak een nieuwe groep met behulp van het standaardproces in de Intune-console om uw configuratie te voltooien.  

   ![Een profiel toewijzen](./media/security-baselines/assignments.png)
  
6. Wanneer u klaar bent om de basislijn te implementeren, selecteert u het tabblad **Controleren en maken** om de gegevens van de basislijn te controleren. Selecteer vervolgens **Profiel opslaan** om het profiel op te slaan en te implementeren. 

   ![De basislijn controleren](./media/security-baselines/review.png) 

   Zodra u hebt opgeslagen, wordt het profiel doorgestuurd naar apparaten wanneer deze inchecken bij Intune. Dit kan dus onmiddellijk plaatsvinden.

   > [!TIP]  
   > U kunt een profiel opslaan zonder dit eerst aan groepen toe te wijzen. U kunt het profiel later bewerken om groepen toe te voegen. 

7. Nadat u het profiel hebt maakt, kunt u het bewerken door naar **Apparaatbeveiliging** > **Beveiligingsbasislijnen** te gaan, de basislijn te selecteren die u hebt geconfigureerd en vervolgens **Profielen** te selecteren.  Selecteer het profiel en selecteer vervolgens **Eigenschappen** om de instellingen te bewerken, en selecteer **Toewijzingen** om de groepen te bewerken die deze basislijn ontvangen. 

## <a name="q--a"></a>Vragenronde

#### <a name="why-these-settings"></a>Waarom deze instellingen?

Het Microsoft-beveiligingsteam heeft jarenlang rechtstreeks met de Windows-ontwikkelaars en de beveiligingscommunity samengewerkt om deze aanbevelingen op te stellen. De instellingen in deze basislijn worden beschouwd als de meest relevante beveiligingsgerelateerde configuratieopties. In elke nieuwe build van Windows past het team de aanbevelingen aan op basis van onlangs uitgebrachte functies.

#### <a name="is-there-a-difference-in-the-recommendations-for-windows-security-baselines-for-group-policy-vs-intune"></a>Is er een verschil in de aanbevelingen voor Windows-beveiligingsbasisrichtlijnen voor groepsbeleid t.o.v. Intune?

De instellingen voor elke basislijn worden door hetzelfde beveiligingsteam van Microsoft gekozen en georganiseerd. Intune bevat alle relevante instellingen in de Intune-beveiligingsbasislijn. Er zijn enkele instellingen in de basislijn voor groepsbeleid die specifiek zijn voor een on-premises domeincontroller. Deze instellingen worden uitgesloten van de aanbevelingen voor Intune. Alle andere instellingen zijn hetzelfde.

#### <a name="are-the-intune-security-baselines-cis-or-nsit-compliant"></a>Zijn de Intune-beveiligingsbasislijnen compatibel met CIS of NSIT?

Strikt genomen niet. Het Microsoft-beveiligingsteam raadpleegt adviesorganisaties, zoals CIS, voor het opstellen van de aanbevelingen. Maar er is niet één-op-één koppeling tussen "Compatibel met CIS" en Microsoft-basislijnen.

#### <a name="what-certifications-does-microsofts-security-baselines-have"></a>Welke certificeringen hebben Microsoft-beveiligingsbasislijnen? 

- Microsoft blijft beveiligingsbasislijnen publiceren voor groepsbeleid (GPO's) en de [Security Compliance Toolkit](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10), zoals het dit al vele jaren doet. Deze basislijnen worden door veel organisaties gebruikt. De aanbevelingen in deze basislijnen zijn het gevolg van de samenwerking van het Microsoft Security-team met zakelijke klanten en externe organisaties, inclusief het Ministerie van defensie, de NIST (National Institute of Standards en Technology) en meer. We delen onze aanbevelingen en basislijnen met deze organisaties. Deze organisaties hebben ook hun eigen aanbevelingen die nauw aansluiten bij de aanbevelingen van Microsoft. Aangezien Mobile Device Management (MDM) blijft groeien in de cloud, heeft Microsoft gelijkwaardige MDM-aanbevelingen voor deze basislijnen groepsbeleid opgesteld. Deze aanvullende basislijnen zijn ingebouwd in Microsoft Intune en omvatten nalevingsrapporten voor gebruikers, groepen en apparaten die de basislijn volgen (of niet volgen).

- Veel klanten gebruiken de aanbevelingen voor Intune-basislijnen als uitgangspunt, en passen deze vervolgens aan hun eigen IT- en beveiligingsbehoeften aan. De Windows 10 RS5 **MDM-beveiligingsbasislijn** van Microsoft is de eerste basislijn die wordt uitgebracht. Deze basislijn is gebouwd als een algemene infrastructuur die klanten de mogelijkheid biedt om uiteindelijk andere beveiligingsbasislijnen op basis van CIS, NIST en andere standaarden te importeren. Deze is op dit moment beschikbaar voor Windows en zal later beschikbaar komen voor iOS en Android.

- Het migreren van on-premises Active Directory-groepsbeleid naar een zuivere cloudoplossing met behulp van Azure Active Directory (AD) met Microsoft Intune is een heel traject. Om u hierbij te helpen, zijn er aanvullende groepsbeleidsobjecten gepubliceerd voor aan hybride Microsoft Azure Active Directory en Microsoft Azure Active Directory gekoppelde apparaten. Deze apparaten kunnen, indien nodig, MDM-instellingen van de cloud (Intune) en instellingen voor groepsbeleid van on-premises domeincontrollers krijgen.

## <a name="next-steps"></a>Volgende stappen
- Bekijk de [Windows-beveiligingsbasislijninstellingen](security-baseline-settings-windows.md) die worden ondersteund door Intune.  
- De status controleren en de [basislijn en het profiel](security-baselines-monitor.md) controleren.
