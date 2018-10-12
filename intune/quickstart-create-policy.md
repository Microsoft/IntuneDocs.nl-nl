---
title: 'Snelstart: een apparaatnalevingsbeleid maken voor een Windows 10-apparaat'
description: Gebruik deze snelstart om beleidsregels te maken om bedrijfsgegevens te beschermen en de apparaten te beheren die eindgebruikers gebruiken om toegang te krijgen tot bedrijfsresources. Wijs het beleid vervolgens toe aan groepen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/21/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 73e1e0a27d128d567a924e6f2b343026b11f1a44
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581579"
---
# <a name="quickstart-add-a-device-compliance-policy-for-a-windows-10-device"></a>Snelstart: een apparaatnalevingsbeleid maken voor een Windows 10-apparaat
Een Intune-apparaatnalevingsbeleid voor Windows bepaalt de regels en instellingen waaraan een Windows-apparaat moet voldoen om te voldoen aan het beleid. U kunt dit beleid met [voorwaardelijke toegang](https://docs.microsoft.com/intune/conditional-access) gebruiken om toegang tot bedrijfsresources toe te staan of te blokkeren. U kunt ook apparaatrapporten krijgen en maatregelen nemen voor niet-naleving.

In deze snelstart maakt u een apparaatnalevingsbeleid voor een Windows 10-apparaat en wijst u een apparaatgroep aan het beleid toe.

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](free-trial-sign-up.md).

## <a name="prerequisites"></a>Vereisten
- Als u de stappen in deze snelstart wilt uitvoeren, moet u eerst [een gebruiker maken](quickstart-create-user.md) en [een groep maken](quickstart-create-group.md).


## <a name="sign-in-to-intune"></a>Aanmelden bij Intune
Meld u aan bij [Intune](https://aka.ms/intuneportal) als globale beheerder of beheerder van een Intune-service.

## <a name="create-a-device-compliance-policy"></a>Een nalevingsbeleid voor apparaten maken
1. Selecteer **Apparaatcompatibiliteit** > **Beleid** > **Beleid maken**.
2. Voer **Windows 10-naleving** in het vak **Naam** in en typ **Voorbeeld van een nalevingsbeleid voor Windows 10** in het vak **Beschrijving**.
3. Bij **Platform** selecteert u **Windows 10 en hoger**.
4. Ga naar **Instellingen**, selecteer **Systeembeveiliging** en stel **Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten** in op **Vereisen**. Wanneer u klaar bent met het instellen van het beleid, selecteert u **OK**.
   ![Nalevingsbeleid](/intune/media/quickstart-create-policy/compliance-policy.png)
5. Sluit het deelvenster **Nalevingsbeleid van Windows 10**. 
6. In het deelvenster **Beleid maken** selecteert u **Maken**. Met deze stap maakt u het beleid en geeft u dit beleid weer in **Apparaatcompatibiliteit** > **Beleid**.
7. Selecteer het nieuwe beleid en kies **Toewijzingen**. U kunt Azure Active Directory-beveiligingsgroepen (AD) opnemen of uitsluiten.
8. Kies **Geselecteerde groepen** om uw bestaande Azure AD-beveiligingsgroepen te bekijken. Selecteer **Contoso Testers** en kies **Opslaan** om het beleid te implementeren voor gebruikers in de groep. Als u deze groep niet hebt gemaakt bij [Een groep maken](quickstart-create-group.md), kunt u zelf een groep kiezen. 

## <a name="clean-up-resources"></a>Resources opschonen
Als u het beleid niet meer nodig hebt, kunt u het verwijderen. Hiervoor selecteert u het beleid **Windows 10-naleving** en klikt u op **Verwijderen**. 

## <a name="next-steps"></a>Volgende stappen
In deze snelstart hebt u een eenvoudig apparaatnalevingsbeleid gemaakt en toegewezen. Ga naar de snelstart voor het instellen van automatische inschrijving als u graag een Windows 10-apparaat wilt inschrijven om beleid aan toe te wijzen. 
 
> [!div class="nextstepaction"]
> [Automatische inschrijving instellen](quickstart-setup-auto-enrollment.md)