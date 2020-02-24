---
title: Multi-Factor Authentication vereisen voor Intune-apparaatinschrijving
titleSuffix: Microsoft Intune
description: Hoe u in Azure AD Multi-Factor Authentication vereist voor Intune-apparaatinschrijving.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: ''
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 14347d12888ff5ef61d4543409a08fbdeb371c89
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415201"
---
# <a name="require-multi-factor-authentication-for-intune-device-enrollments"></a>Multi-Factor Authentication vereisen voor Intune-apparaatinschrijvingen

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune kan Multi-Factor Authentication (MFA) in Azure Active Directory (AD) gebruiken voor apparaatregistraties om u te helpen uw zakelijke resources te beveiligen.

MFA vereist twee of meer van de volgende verificatiemethoden:

- Iets dat u weet (doorgaans een wachtwoord of pincode).
- Iets dat u hebt (een vertrouwd apparaat dat moeilijk kan worden gedupliceerd, zoals een telefoon).
- Iets van u (biometrisch, zoals een vingerafdruk).

MFA wordt ondersteund voor apparaten met iOS/iPadOS, Android, Windows 8.1 of hoger, Windows Phone 8.1 of hoger en Windows 10 Mobile of hoger.

Als u MFA inschakelt, moeten eindgebruikers twee soorten referenties opgegeven om een apparaat te registreren.

## <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Intune configureren zodat Multi-Factor Authentication wordt vereist bij het registreren van apparaten

Voer de volgende stappen uit om MFA te vereisen wanneer een apparaat wordt geregistreerd:

>[!Important]
>U moet Azure Active Directory Premium P1 of hoger toewijzen aan uw gebruikers om dit beleid te kunnen implementeren.

>[!Important]
>Configureer geen **op het apparaat gebaseerde toegangsregels** voor Microsoft Intune-registratie.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) kies **Apparaten** > **Voorwaardelijke toegang**. Het knooppunt voor voorwaardelijke toegang dat via *Intune* wordt geopend, is hetzelfde als het knooppunt dat u opent via *Azure AD*.
2. Kies **Nieuw beleid**.
3. Typ onder **Nieuw** beleid een beschrijvende naam voor het beleid.
4. Kies in de sectie **Toewijzingen** **Gebruikers en groepen**. 
5. In **Gebruikers en groepen** kiest u **Gebruikers of groepen selecteren**  en schakelt u **Gebruikers en groepen** in. Selecteer vervolgens de gebruikers en/of groepen waarop dit beleid van toepassing is en kies vervolgens **Gereed**.
6. Kies **Cloud-apps** in de sectie **Toewijzingen**.
7. Kies op het tabblad **Opnemen** onder **Cloud-apps** de optie **Apps selecteren** en kies vervolgens **Selecteren** > **Microsoft Intune-inschrijving**. Klik ten slotte op **Gereed**. Door **Microsoft Intune-inschrijving** te kiezen wordt MFA voor voorwaardelijke toegang alleen toegepast op de inschrijving van het apparaat (eenmalige MFA-prompt).
8. In het gedeelte **Toewijzingen** hoeft u voor **Voorwaarden** geen instellingen voor MFA te configureren.
9. Kies in de sectie **Besturingselementen voor toegang** de optie **Verlenen**.
10. Kies onder **Verlenen** **Toegang verlenen** en selecteer vervolgens **Meervoudige verificatie vereisen**. Selecteer niet **Vereisen dat het apparaat moet worden gemarkeerd als compatibel**, omdat de compatibiliteit van het apparaat niet kan worden gecontroleerd totdat het is ingeschreven. Kies dan de optie **Selecteren**.
11. Kies onder **Nieuw beleid** **Beleid inschakelen** > **Aan** en kies vervolgens **Maken**.



## <a name="next-steps"></a>Volgende stappen

Als eindgebruikers hun apparaat inschrijven, moeten ze zich nu met een tweede vorm van identificatie, zoals een pincode, een telefoonnummer of biometrische gegevens, verifiëren.
