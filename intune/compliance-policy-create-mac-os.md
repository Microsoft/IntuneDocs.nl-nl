---
title: Een nalevingsbeleid maken voor macOS
titleSuffix: Azure portal
description: Meer informatie over het maken van nalevingsbeleid voor macOS-apparaten.
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 2/13/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a5f1caeddbd3d171092ef59cfb092404b31154f2
ms.sourcegitcommit: 754fcc31155b28d6910bba45419c6be745f8793e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/14/2018
---
# <a name="create-a-device-compliance-policy-for-macos-devices-with-intune"></a>Een apparaatnalevingsbeleid maken voor macOS-apparaten in Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="before-you-begin"></a>Voordat u begint

Voordat u begint met het maken en toewijzen van een apparaatnalevingsbeleid, leest u de concepten voor een Intune-apparaatnalevingsbeleid.

- Ga naar [Aan de slag met apparaatnalevingsbeleid](device-compliance.md) voor meer informatie over beleidsregels voor apparaatnaleving.

> [!IMPORTANT]
> U stelt voor elk platform een afzonderlijk apparaatnalevingsbeleid op. De Intune-instellingen voor apparaatnalevingsbeleid zijn afhankelijk van de mogelijkheden van het platform, dus de instellingen die beschikbaar zijn via het MDM-protocol.

In de volgende tabel wordt beschreven hoe niet-compatibele instellingen worden beheerd wanneer een nalevingsbeleid wordt gebruikt in combinatie met beleid voor voorwaardelijke toegang:


| Beleidsinstelling | macOS 10.11 of hoger |
| --- | --- |
| **Configuratie van pincode of wachtwoord** | Hersteld |   
| **Apparaatversleuteling** | Hersteld (door een pincode in te stellen) |
| **E-mailprofiel** | In quarantaine |
|**Minimale versie van het besturingssysteem** | In quarantaine |
| **Maximale versie van het besturingssysteem** | In quarantaine |  


**Hersteld** = het besturingssysteem van het apparaat dwingt naleving af. (De gebruiker wordt bijvoorbeeld gedwongen een pincode in te stellen.)

**In quarantaine** = het besturingssysteem van het apparaat dwingt geen naleving af. (Bij Android-apparaten bijvoorbeeld wordt de gebruiker niet gedwongen het apparaat te versleutelen.) Als het apparaat niet compatibel is, worden de volgende acties uitgevoerd:

- Het apparaat wordt geblokkeerd als een beleid voor voorwaardelijke toegang van toepassing is voor de gebruiker.
- De bedrijfsportal stelt de gebruiker op de hoogte van eventuele nalevingsproblemen.

## <a name="macos-compliance-policy-settings"></a>Instellingen voor macOS-nalevingsbeleid

U kunt kiezen uit verschillende categorieën met verschillende instellingen bij het maken van een nieuw apparaatnalevingsbeleid in Intune:

- Apparaatstatus

- Apparaateigenschappen

- Systeembeveiliging

### <a name="device-health"></a>Apparaatstatus

- **Beveiliging van systeemintegriteit vereisen**: stel deze optie in op **Vereist** om te controleren of beveiliging van systeemintegriteit is ingeschakeld op de macOS-apparaten.

### <a name="device-properties"></a>Apparaateigenschappen

- **Minimale versie van het besturingssysteem**: als een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt dit apparaat gerapporteerd als niet-compatibel. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De gebruiker kan kiezen om het apparaat bij te werken. Daarna zijn de bedrijfsbronnen toegankelijk.

- **Maximale versie van het besturingssysteem**: als een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die in de regel is opgegeven, wordt de toegang tot bedrijfsresources geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel die de versie van het besturingssysteem toestaat, kan dit apparaat niet worden gebruikt om toegang tot bedrijfsbronnen te krijgen.

### <a name="system-security-settings"></a>Systeembeveiligingsinstellingen

#### <a name="password"></a>Wachtwoord

- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**: stel deze optie in op **Vereist** om gebruikers een wachtwoord te laten invoeren om toegang te krijgen tot hun apparaat.

- **Eenvoudige wachtwoorden**: stel deze optie in op **Blokkeren** zodat de gebruiker geen eenvoudig wachtwoord kan maken, zoals **1234** of **1111**.

- **Minimale wachtwoordlengte**: hiermee geeft u het minimale aantal cijfers of tekens aan waaruit het wachtwoord moet bestaan.

- **Wachtwoordtype**: geef aan of de gebruiker een **alfanumeriek** of een **numeriek** wachtwoord moet maken.

- **Aantal niet-alfanumerieke tekens in wachtwoord**: als u **Vereist wachtwoordtype** instelt op **Alfanumeriek**, gebruikt u deze instelling om het minimum aantal tekens op te geven dat het wachtwoord moet bevatten. 

    > [!NOTE]
    > Als u een hogere waarde instelt, moet de gebruiker een wachtwoord maken dat complexer is.

    > [!IMPORTANT]
    > Voor macOS-apparaten verwijst deze instelling naar het aantal speciale tekens (bijvoorbeeld **!** , **#**, **&amp;**) dat in het wachtwoord moet worden opgenomen.

- **Maximum aantal minuten van inactiviteit voordat wachtwoord is vereist**: hiermee geeft u aan na hoeveel niet-actieve tijd de gebruiker het wachtwoord opnieuw moet invoeren.

- **Wachtwoord verloopt (in dagen)**: selecteer het aantal dagen (tussen 1 en 250) waarna het wachtwoord verloopt en gebruikers een nieuw wachtwoord moeten maken.

- **Aantal vorige wachtwoorden om hergebruik te voorkomen**: hiermee geeft u op hoeveel eerder gebruikte wachtwoorden niet opnieuw mogen worden gebruikt.

    > [!IMPORTANT]
    > Als de wachtwoordvereiste op een macOS-apparaat wordt gewijzigd, wordt deze vereiste pas van kracht als de gebruiker de eerstvolgende keer het wachtwoord wil wijzigen. Als u bijvoorbeeld de lengtebeperking voor het wachtwoord instelt op acht cijfers en op het macOS-apparaat nog een beperking voor zes cijfers geldt, gaat de nieuwe beperking pas in de eerstvolgende keer dat de gebruiker het wachtwoord wil bijwerken.

## <a name="to-create-a-device-compliance-policy"></a>Een nalevingsbeleid voor apparaten maken

1. Ga naar [Azure Portal](https://portal.azure.com) en meld u aan met uw Intune-referenties.

2. Nadat u zich hebt aangemeld, ziet u het **Azure-dashboard**.

3. Kies **Meer services** in het linkermenu en typ dan **Intune** in het vak tekstfilter.

4. Kies **Intune**. Vervolgens ziet u het **Intune-dashboard**.

5. Kies **Apparaatnaleving** en vervolgens **Beleid** onder **Beheren**.

6. Kies **Beleid maken**.

7. Typ een naam en beschrijving en kies het platform waarop u dit beleid wilt toepassen.

8. De blade **macOS-nalevingsbeleid** wordt geopend. Kies de instellingencategorieën **Beveiliging**, **Apparaatstatus** en **Apparaateigenschappen** om uw instellingen op te geven.

10. Wanneer u klaar bent met het kiezen van de instellingen, kiest u **OK** onder elke instellingencategorie voor apparaatnaleving.

11. Kies **OK** en vervolgens **Maken**.

## <a name="assign-user-groups"></a>Gebruikersgroepen toewijzen

Als u een nalevingsbeleid aan gebruikers wilt toewijzen, kiest u een beleid dat u hebt geconfigureerd. Bestaande beleidsregels vindt u op de blade **Nalevingsbeleid**.

1. Kies het apparaatnalevingsbeleid dat u aan gebruikers wilt toewijzen en kies **Toewijzingen**. Hiermee opent u de blade waar u **Azure Active Directory-beveiligingsgroepen** kunt selecteren en aan het beleid kunt toewijzen.

2. Kies **Groepen selecteren** om de blade met de Azure AD-beveiligingsgroepen te openen.

3. Kies **Selecteren** en vervolgens **Opslaan** om het apparaatnalevingsbeleid toe te wijzen aan Azure AD-beveiligingsgroepen.

4. Wanneer u klaar bent met het toewijzen van het apparaatnalevingsbeleid aan uw groepen, kunt u de blade **Toewijzingen** sluiten.

    > [!TIP]
    > Standaard controleren apparaten elke acht uur op naleving, maar gebruikers kunnen dit proces ook afdwingen via de Intune-bedrijfsportal-app.

## <a name="next-steps"></a>Volgende stappen

[Het nalevingsbeleid voor apparaten controleren](compliance-policy-monitor.md)
