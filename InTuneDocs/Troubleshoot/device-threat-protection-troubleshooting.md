---
title: Problemen met de integratie van Lookout oplossen | Microsoft Docs
description: In dit onderwerp wordt beschreven hoe problemen die vaak voorkomen bij de integratie van Lookout kunnen worden opgelost
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: de2f224f203257fe539196557180f0b5da5d8373
ms.lasthandoff: 04/14/2017


---

# <a name="troubleshoot-lookout-integration-with-intune"></a>Problemen met de integratie van Lookout met Intune oplossen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In dit onderwerp worden enkele veelvoorkomende problemen beschreven die zich kunnen voordoen bij de installatie van Lookout Mobile Threat Protection (MTP).

**Aanmeldingsfouten**

## <a name="403-errors"></a>403-fouten
Er wordt een 403-fout weergegeven wanneer u zich aanmeldt bij de [Lookout MTP-console](https://aad.lookout.com):  **U bent niet gemachtigd voor toegang tot de service**  Dit kan gebeuren wanneer de opgegeven gebruikersnaam niet tot de Azure Active Directory (AD)-groep hoort die voor toegang tot Lookout MTP is geconfigureerd.

Lookout MTP staat alleen gebruikers uit een geconfigureerde Azure AD-groep toe voor toegang tot de service. Neem contact op met de ondersteuning van Lookout als u wilt weten welke groep is geconfigureerd voor toegang tot Lookout MTP:

* E-mail: enterprisesupport@lookout.com
* Meld u aan bij de [MTP-console](http://aad.lookout.com) en ga naar de module **Ondersteuning**.
* Ga naar: https://enterprise.support.lookout.com/hc/requests en dien een ondersteuningsaanvraag in.

## <a name="unable-to-sign-in"></a>Aanmelden is niet mogelijk
De volgende fout wordt weergegeven wanneer de globale Azure AD-beheerder de initiële installatie van Lookout niet heeft geaccepteerd.

![schermopname van het aanmeldingsscherm van Lookout met een aanmeldingsfout](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

De globale beheerder kan dit probleem oplossen door zich aan te melden bij https://aad.lookout.com/les?action=consent en de prompt te accepteren om de installatie te starten. Gedetailleerdere informatie vindt u in het onderwerp [Abonnement instellen met Lookout MTP](../deploy-use/set-up-your-subscription-with-lookout-mtp.md).

**Problemen met de apparaatstatus**

## <a name="device-missing-from-lookout-device-list"></a>Apparaat ontbreekt in de lijst met apparaten van Lookout

Deze situatie kan zich voordoen in een van de volgende scenario's:
* De eigenaar van het apparaat is niet opgenomen in de **registratiegroep** die in de **Lookout MTP-console** is opgegeven.  Ga in de [Lookout-console](http://aad.lookout.com) naar **Systeem** > **Intune-connector** > **Registratiebeheer**.  Bekijk de Azure AD-groepen die geconfigureerd zijn registratie en controleer of de gebruiker van het apparaat deel uitmaakt van een van de Azure AD-groepen.  Nadat een gebruiker aan de registratiegroep is toegevoegd, hangt het van het geconfigureerde polling-interval (de standaardinstelling is 5 minuten) af hoelang het duurt voordat het apparaat wordt weergegeven in de module **Apparaten** van de Lookout MTP-console.
* Als het apparaat niet door Lookout MTP wordt ondersteund.  Apparaten die niet worden ondersteund, worden weergegeven in de sectie **Beheerde apparaten** van de connectorinstellingen van de Lookout MTP-console.

### <a name="device-reported-as-pending"></a>Apparaat gerapporteerd als **in behandeling**

Een apparaat heeft de status **In behandeling** als de eindgebruiker de Lookout for Work-app niet heeft geopend, maar wel op de knop **Activeren** heeft getikt. Zie [U wordt gevraagd Lookout for Work te installeren op uw Android-apparaat](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android) of [U wordt gevraagd Lookout for Work te installeren op uw iOS-apparaat](https://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-ios) voor meer informatie over de activering van het apparaat met de Lookout for Work-app.

## <a name="device-whos-active-but-has-no-device-id"></a>Apparaat is actief, maar heeft geen apparaat-id
Als een actief apparaat in de Lookout MTP-console geen apparaat-id heeft, maakt de gebruiker van het apparaat deel uit van de registratiegroep. Een apparaat kan deze status krijgen als de gebruiker van het apparaat uit de registratiegroep is verwijderd of als de registratiegroep is verwijderd.

Ga in de [Lookout-console](http://aad.lookout.com) naar **Systeem** > **Intune-connector** > **Registratie** en controleer de instellingen.  Bekijk de Azure AD-groepen en controleer of de gebruiker van het apparaat deel uitmaakt van een van de Azure AD-groepen.

Wanneer een apparaat deze status heeft, blijft de gebruiker meldingen van Lookout over gedetecteerde bedreigingen ontvangen, maar wordt geen informatie over bedreigingen naar Intune verzonden.

## <a name="device-reported-as-disconnected"></a>Apparaat gerapporteerd als **verbinding verbroken**

**Verbinding verbroken** betekent dat het apparaat nog niet is gesynchroniseerd met Lookout MTP in het geconfigureerde interval, dat standaard 30 dagen bedraagt met een minimum van 7 dagen. De bedrijfsportal-app of de Lookout for Work-app ontbreekt in het apparaat. Dit probleem kan worden opgelost door de apps opnieuw te installeren. Wanneer de gebruiker Lookout for Work opent en de app activeert, wordt het apparaat opnieuw gesynchroniseerd met Lookout MTP en Intune.

### <a name="forcing-a-device-sync"></a>Synchronisatie van een apparaat afdwingen
In de module **Apparaten** van de Lookout MTP-console kan de beheerder het apparaat selecteren en verwijderen.   De volgende keer dat de eigenaar van het apparaat de Lookout for Work-app opent en op **Activeren** tikt, wordt de apparaatstatus opnieuw gesynchroniseerd.

## <a name="device-has-a-new-user"></a>Apparaat heeft een nieuwe gebruiker
U moet het apparaat wissen en de nieuwe gebruiker vragen het apparaat te registreren.  Selecteer het apparaat in de [Intune-beheerconsole](https://manage.microsoft.com), klik met de rechtermuisknop en kies **Buiten gebruik stellen/wissen** om het apparaat uit het beheer te verwijderen. Nadat het apparaat buiten gebruik is gesteld, kunt u het verwijderen.

![schermopname van de apparaatmodule in de Intune-beheerconsole met de optie Buiten gebruik stellen/wissen weergegeven](../media/mtp/mtp-retire-device-intune-console.png)

U kunt ook naar de module **Apparaten** van de [Lookout-console](http://aad.lookout.com) gaan en **Verwijderen** kiezen.

Als de nieuwe gebruiker deel uitmaakt van een Lookout MTP-registratiegroep, wordt het apparaat weergegeven zodra het in Azure AD aan de nieuwe gebruiker is gekoppeld.

## <a name="compliance-remediation-workflows"></a>Werkstromen voor herstel van naleving
- [U wordt gevraagd Lookout for Work te installeren op uw Android-apparaat]( http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)
- [U moet een bedreiging oplossen die met Lookout for Work op een Android-apparaat is gevonden](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)
- [U moet een bedreiging oplossen die met Lookout for Work op een iOS-apparaat is gevonden](https://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-ios)


### <a name="see-also"></a>Zie tevens
[Uw abonnement instellen met Lookout MTP](https://docs.microsoft.com/intune/deploy-use/set-up-your-subscription-with-lookout-mtp)

