---
title: Beleid voor voorwaardelijke toegang op basis van apparaten instellen met behulp van Intune
titleSuffix: Microsoft Intune
description: Hier vindt u meer informatie over het maken van beleid voor voorwaardelijke toegang op basis van apparaten met behulp van apparaatnalevingsbeleid van Microsoft Intune en Mobile Application Management (MAM).
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aaf9b82bc810dd3a616eb25f39f4b5830b1c3e6f
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61508654"
---
# <a name="create-a-device-based-conditional-access-policy"></a>Beleid maken voor voorwaardelijke toegang op basis van apparaten

Met Intune kunt u de voorwaardelijke toegang in Azure Active Directory verbeteren door nalevingsbeleid voor mobiele apparaten toe te voegen aan het toegangsbeheer. Zodra u een nalevingsbeleid in Intune hebt gemaakt waarin de nalevingsvereisten voor apparaten zijn vastgelegd, kunt u de nalevingsstatus van een apparaat gebruiken om de toegang tot uw apps en services toe te staan of te blokkeren. U kunt dit doen door beleid voor voorwaardelijke toegang te maken dat gebruikmaakt van de instelling **Vereisen dat het apparaat als compatibel is gemarkeerd**.  

Beleid voor voorwaardelijke toegang specificeert de app of services die u wilt beveiligen, de voorwaarden waaronder de apps of services toegankelijk zijn, en de gebruikers op wie het beleid van toepassing is. Voorwaardelijke toegang is een Azure AD premium-functie die configureerbaar is in Azure Active Directory, maar u kunt hetzelfde beleid ook instellen in de Intune-portal. Het knooppunt voor voorwaardelijke toegang dat via *Intune* wordt geopend, is hetzelfde als het knooppunt dat u opent via *Azure AD*.  

> [!IMPORTANT]
> Voordat u het beleid voor voorwaardelijke toegang instelt, moet u apparaatnalevingsbeleid in Intune instellen om apparaten te evalueren op basis van de vraag of ze aan specifieke vereisten voldoen. Zie [Aan de slag met apparaatnalevingsbeleid in Intune](device-compliance-get-started.md).

## <a name="create-conditional-access-policy"></a>Beleid voor voorwaardelijke toegang maken

1.  In de Intune-portal selecteert u **Voorwaardelijke toegang** > **Beleid** > **Nieuw beleid**.
   
    ![Nieuw beleid voor voorwaardelijke toegang maken](media/create-conditional-access-intune/create-ca.png)
 
2.  Onder **Toewijzingen** selecteert u **Gebruikers en groepen**. 
3.  Op het tabblad **Opnemen** identificeert u de gebruikers of groepen waarop u dit beleid voor voorwaardelijke toegang wilt toepassen. Nadat u hebt gekozen wie u wilt opnemen, kunt u het tabblad **Uitsluiten** gebruiken indien er gebruikers, rollen of groepen zijn die u wilt uitsluiten van dit beleid.  
    - **Alle gebruikers**: selecteer deze optie om het beleid toe te passen op alle gebruikers en groepen, inclusief interne en gastgebruikers.
  
    - **Gebruikers en groepen selecteren**: selecteer deze optie en geef een of meer van de volgende opties op:
  
      a. **Alle gastgebruikers**: selecteer deze optie om externe gastgebruikers (bijvoorbeeld partners, externe medewerkers) op te nemen of uit te sluiten
       
      b. **Directory-rollen**: selecteer een of meer Azure AD-rollen om gebruikers aan wie deze rollen zijn toegewezen, op te nemen of uit te sluiten.
      
      c. **Gebruikers en groepen**: selecteer deze optie om individuele gebruikers of groepen te zoeken en te selecteren die u wilt opnemen of uitsluiten.
     
       > [!TIP]  
       > Test het beleid uit op een kleinere groep gebruikers om er zeker van te zijn dat het naar verwachting werkt.
4.  Selecteer **Voltooid**.
5.  Onder **Toewijzingen** selecteert u **Cloud-apps**. 
6.  Identificeer op het tabblad **Opnemen** de apps en services die u wilt beveiligen met dit beleid voor voorwaardelijke toegang. Vervolgens kunt u het tabblad **Uitsluiten** gebruiken als er apps of services zijn die u wilt uitsluiten van dit beleid.
    - **Alle cloud-apps**: selecteer deze optie om het beleid op alle apps toe te passen.
      > [!IMPORTANT]  
      > De Microsoft Azure Management-app voor toegang tot de Azure-portal is in deze lijst opgenomen. Zorg ervoor dat u het tabblad **Uitsluiten** hier of in de opties **Gebruikers en groepen** gebruikt om ervoor te zorgen dat u (of de gebruikers of groepen die u aanwijst) zich kunt aanmelden op de Azure-portal. 

    - **Apps selecteren**: selecteer deze optie, kies **Selecteren** en gebruik vervolgens de lijst met toepassingen om de toepassingen of services te zoeken en te selecteren die u wilt beveiligen.
    
      ![Nieuw beleid voor voorwaardelijke toegang maken](media/create-conditional-access-intune/create-ca-select-apps.png)

7.  Selecteer **Voltooid**.
8.  Onder **Toewijzingen** selecteert u **Voorwaarden**.
    - **Aanmeldingsrisico**: kies Ja om de aanmeldingsrisicodetectie van Azure AD Identity Protection voor dit beleid te gebruiken, en kies vervolgens de aanmeldingsrisiconiveaus waarop het beleid van toepassing moet zijn.
    - **Apparaatplatformen**: identificeer op het tabblad **Opnemen** u de apparaatplatformen waarop u dit beleid voor voorwaardelijke toegang wilt toepassen. Gebruik het tabblad **Uitsluiten** om platformen van dit beleid uit te sluiten.
    - **Locaties**: geef op het tabblad **Opnemen** op of het beleid van toepassing is op een locatie, op vertrouwde netwerklocaties die onder de controle van uw IT-afdeling vallen, of op specifieke netwerklocaties. Gebruik het tabblad **Uitsluiten** om netwerklocaties van dit beleid uit te sluiten. 
    - **Client-apps**: kies **Ja** om aan te geven of het beleid van toepassing moet zijn op browser-apps, mobiele apps en desktop-clients. U kunt ook **Moderne verificatieclients** (zoals Outlook voor iOS resp. Android) en **Exchange ActiveSync-clients** selecteren.
    - **Apparaatstatus.**: het beleid voor voorwaardelijke toegang is van toepassing op alle apparaatstatussen, tenzij u Ja kiest en specifiek de statussen 'Apparaat aan Hybrid Azure AD toegevoegd' of 'Apparaat gemarkeerd als compatibel' (of beide) uitsluit.
    
      ![Nieuw beleid voor voorwaardelijke toegang maken](media/create-conditional-access-intune/create-ca-device-platforms.png)

      > [!TIP]  
      > Indien u zowel **Moderne verificatieclients** als **Exchange ActiveSync-clients** wilt beveiligen, maakt u twee afzonderlijke beleidsvarianten voor voorwaardelijke toegang, één voor elk clienttype. Exchange ActiveSync ondersteunt weliswaar moderne verificatie, maar alleen met de voorwaarde 'platform'. Andere voorwaarden, zoals meervoudige verificatie, worden niet ondersteund. Om de toegang tot Exchange Online vanaf Exchange ActiveSync effectief te beveiligen, maakt u een beleid voor voorwaardelijke toegang dat de cloud-app Office 365 Exchange Online en de client-app Exchange ActiveSync specificeert, waarbij de optie 'Beleid alleen toepassen op ondersteunde platformen' is geselecteerd.

9.  Selecteer **Voltooid**.
10. Onder **Toegangscontroles** selecteert u **Verlenen**. Configureer wat er moet gebeuren, op basis van de voorwaarden die u hebt ingesteld.  U kunt de volgende opties selecteren:
    - **Toegang blokkeren**: de gebruikers die in dit beleid worden gespecificeerd, wordt de toegang tot de apps geweigerd onder de voorwaarden die u hebt opgegeven.
    - **Toegang verlenen**: de gebruikers die in dit beleid worden gespecificeerd, wordt toegang verleend, maar u kunt nog een van de volgende acties eisen:
      - **Meervoudige verificatie vereisen**: de gebruiker dient aan extra beveiligingsvereisten te voldoen, bijvoorbeeld via telefoon of sms.
      - **Vereisen dat het apparaat als compatibel is gemarkeerd**: het apparaat moet compatibel zijn met Intune. Als het apparaat niet compatibel is, krijgt de gebruiker de optie om het apparaat in Intune te registreren. 
      - **Vereisen dat het apparaat Hybride Azure AD is toegevoegd**: apparaten moeten aan Hybrid Azure AD zijn toegevoegd.
      - **Goedgekeurde client-apps vereisen**: het apparaat moet goedgekeurde client-apps gebruiken. 
      - **Voor meerdere controles**: selecteer **Alle geselecteerde controles vereisen**, zodat alle bovenstaande vereisten worden afgedwongen wanneer een apparaat toegang probeert te krijgen tot de app.
    
      ![Toegangsbeheer - instellingen voor toegang verlenen](media/create-conditional-access-intune/create-ca-grant-access-settings.png)
 
11. Onder **Beleid inschakelen** selecteert u **Aan**.
     
     ![Beleid inschakelen](media/create-conditional-access-intune/enable-policy.png)

12. Selecteer **Maken**.

## <a name="see-also"></a>Zie tevens
[Op apps gebaseerde voorwaardelijke toegang met Intune](app-based-conditional-access-intune.md)
