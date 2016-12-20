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
translationtype: Human Translation
ms.sourcegitcommit: d6ff74f0b46baf384dbdedf13ad75538dd33a089
ms.openlocfilehash: 416f200bdb72bae98897cb8d279dbdb767757da9


---

# <a name="troubleshoot-lookout-integration-with-intune"></a>Problemen met de integratie van Lookout met Intune oplossen
In dit onderwerp worden enkele veelvoorkomende problemen beschreven die zich kunnen voordoen bij de installatie van Lookout Mobile Threat Protection (MTP).
## <a name="troubleshoot-login-errors"></a>Problemen met aanmelden oplossen
### <a name="403-errors"></a>403-fouten
Er kan een 403-fout worden weergegeven wanneer u zich aanmeldt bij de [Lookout MTP-console](https://aad.lookout.com):  **U bent niet gemachtigd voor toegang tot de service**  Dit kan gebeuren wanneer de door u opgegeven gebruikersnaam niet tot de Azure Active Directory (Azure AD)-groep hoort die voor toegang tot Lookout MTP is geconfigureerd.

Lookout MTP is zo geconfigureerd dat alleen gebruikers van een geconfigureerde Azure AD-groep toegang hebben. Neem contact op met de ondersteuning van Lookout als u niet weet welke groep is geconfigureerd voor toegang tot Lookout MTP.

U kunt op een van de volgende manieren contact opnemen met de ondersteuning van Lookout:

* E-mail: enterprisesupport@lookout.com
* Meld u aan bij de [MTP-console](http://aad.lookout.com) en ga naar de module **Ondersteuning**.
* Ga naar: https://enterprise.support.lookout.com/hc/en-us/requests en dien een ondersteuningsaanvraag in.

### <a name="unable-to-sign-in"></a>Aanmelden is niet mogelijk
De volgende fout kan worden weergegeven wanneer de globale Azure AD-beheerder de initiële installatie van Lookout niet heeft geaccepteerd.

![schermopname van het aanmeldingsscherm van Lookout met een aanmeldingsfout](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

De globale beheerder kan dit probleem oplossen door zich aan te melden bij https://aad.lookout.com/les?action=consent en de prompt te accepteren om de installatie te starten. Gedetailleerdere informatie vindt u in het onderwerp [Abonnement instellen met Lookout MTP](../deploy-use/set-up-your-subscription-with-lookout-mtp.md).

## <a name="troubleshoot-device-status-issues"></a>Problemen met de apparaatstatus oplossen

### <a name="device-not-showing-up-in-the-lookout-mtp-console-device-list"></a>Het apparaat wordt niet weergegeven in de apparaatlijst in de Lookout MTP-console

Deze situatie kan zich voordoen in een van de volgende scenario's:
* Wanneer de gebruiker die eigenaar is van dit apparaat niet tot de **registratiegroep** hoort die in de **Lookout MTP-console** is opgegeven.  Ga in de module **Systeem** naar het tabblad **Intune-connector** en controleer de instellingen van het **registratiebeheer**.  Hier moeten één of meer Azure AD-groepen worden weergegeven die voor registratie zijn geconfigureerd.  Controleer of de gebruiker die eigenaar is van het ontbrekende apparaat tot een van de opgegeven Azure AD-groepen hoort.  Wanneer een nieuwe gebruiker aan de registratiegroep is toegevoegd, hangt het van het geconfigureerde polling-interval (de standaardinstelling is 5 minuten) af hoelang het duurt voordat het apparaat wordt weergegeven in de module **Apparaten** van de Lookout MTP-console.

* Als het apparaat niet door Lookout MTP wordt ondersteund.  Apparaten die niet worden ondersteund, worden weergegeven in de sectie **Beheerde apparaten** van de connectorinstellingen van de Lookout MTP-console.

### <a name="device-continues-to-be-reported-as-pending"></a>De status van het apparaat blijft **In behandeling**

Als een apparaat de status **In behandeling** heeft, betekent dit dat de eindgebruiker de Lookout for Work-app niet heeft geopend, maar wel op de knop **Activeren** heeft getikt. Lees het volgende onderwerp voor meer informatie over het activeren van apparaten met de Lookout for Work-app:

[U wordt gevraagd Lookout for Work te installeren op uw Android-apparaat ](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

### <a name="in-the-lookout-mtp-console-a-device-is-showing-as-active-but-does-not-have-a-device-id"></a>In de Lookout MTP-console wordt aangegeven dat een apparaat actief is, maar heeft het apparaat geen apparaat-id.  
Dat betekent dat de gebruiker die eigenaar is van dit apparaat niet tot de registratiegroep hoort die in de Lookout MTP-console is opgegeven.   Een apparaat kan deze status krijgen als de gebruiker die eigenaar is van het apparaat uit de registratiegroep is verwijderd of de registratiegroep waartoe de gebruiker behoorde, is verwijderd.

Ga in de module **Systeem** in de Lookout MTP-console naar het tabblad **Intune-connector** en controleer de instellingen van **Registratie**.  Hier moeten één of meer Azure AD-groepen worden weergegeven die voor registratie zijn geconfigureerd.  Controleer of de gebruiker die eigenaar is van het apparaat tot een van de opgegeven Azure AD-groepen hoort.  

Wanneer een apparaat deze status heeft, blijft de gebruiker meldingen van Lookout over gedetecteerde bedreigingen ontvangen, maar wordt geen informatie over bedreigingen naar Intune verzonden.

### <a name="device-shows-disconnected-state"></a>Een apparaat heeft de status Verbinding verbroken

De status Verbinding verbroken houdt in dat Lookout MTP gedurende een vooraf geconfigureerd tijdsinterval (de standaardinstelling is 30 dagen met een minimum van 7 dagen) niets meer van het apparaat heeft vernomen. Dit betekent dat de bedrijfsportal-app of de Lookout for Work-app niet op het apparaat is geïnstalleerd of is verwijderd. Dit probleem kan worden opgelost door de apps opnieuw te installeren. Wanneer de gebruiker Lookout for Work opent en de app activeert, wordt het apparaat opnieuw gesynchroniseerd met Lookout MTP en Intune.    

### <a name="forcing-a-resync-on-the-device"></a>Opnieuw synchroniseren op het apparaat afdwingen
In de module **Apparaten** van de Lookout MTP-console kan de beheerder het apparaat selecteren en verwijderen.   De volgende keer dat de eigenaar van het apparaat de Lookout for Work-app opent en op **Activeren** tikt, wordt de apparaatstatus opnieuw gesynchroniseerd.

### <a name="the-owner-of-the-device-is-no-longer-using-this-device"></a>De eigenaar van het apparaat gebruikt het apparaat niet meer
U moet het apparaat wissen en de nieuwe gebruiker vragen het te registreren.  Selecteer het apparaat in de [Intune-beheerconsole](https://manage.microsoft.com), klik met de rechtermuisknop en kies **Buiten gebruik stellen/wissen** om het apparaat uit het beheer te verwijderen. Nadat het apparaat buiten gebruik is gesteld, kunt u het verwijderen.

![schermopname van de apparaatmodule in de Intune-beheerconsole met de optie Buiten gebruik stellen/wissen weergegeven](../media/mtp/mtp-retire-device-intune-console.png)

U kunt ook gaan naar de module **Apparaten** module van de Lookout MTP-console gaan en **Verwijderen** kiezen.  

Zolang de nieuwe gebruiker tot een van de registratiegroepen hoort die zijn opgegeven in de Lookout MTP-console, wordt het apparaat weergegeven wanneer het apparaat eenmaal in Azure AD aan de nieuwe gebruiker is gekoppeld.

## <a name="compliance-remediation-workflows"></a>Werkstromen voor herstel van naleving
[U wordt gevraagd Lookout for Work te installeren op uw Android-apparaat]( http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

[U moet een bedreiging oplossen die met Lookout for Work op een Android-apparaat is gevonden ](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)


### <a name="see-also"></a>Zie tevens
[Uw abonnement instellen met Lookout MTP](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-your-subscription-with-lookout-mtp)



<!--HONumber=Dec16_HO2-->


