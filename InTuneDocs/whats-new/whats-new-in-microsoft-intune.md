---
title: Wat is er nieuw? | Microsoft Docs
description: Ontdek wat er nieuw is in de release van Microsoft Intune van deze maand en in oudere releases
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 053cf0a1b5d06496397b36cbd1a7ebdce420fed3
ms.openlocfilehash: 5158d58c32066ea720335a878fef87451542c195


---
# <a name="whats-new-in-microsoft-intune---january-2017"></a>Wat is er nieuw in Microsoft Intune - januari 2017
Ontdek wat er nieuw is in deze release van Microsoft Intune. U vindt hier ook informatie over toekomstige wijzigingen waar u rekening mee moet houden én informatie over oudere releases.

> [!Note]
> Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nieuwe mogelijkheden

<!--### Actions for non-compliance <!--730266
_Actions for non-compliance_ is a new feature of compliance policies that lets you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.-->

### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Interne consolerapporten voor MAM zonder registratie<!--677961-->
Er zijn nieuwe rapporten voor app-beveiliging toegevoegd voor zowel geregistreerde als niet-geregistreerde apparaten. [Meer informatie over hoe u MAM-beleid met Intune kunt bewaken vindt u hier](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

<!--### Conditional access for MAM with SharePoint Online <!--679339
You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint Online.  You can get started using Intune mobile app management in the Azure portal. Look for the __Conditional Access__ section in the __Settings__ blade which will include the option for SharePoint Online. This feature will ship separately from the rest of the service release. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="android-711-support---694397--"></a>Android 7.1.1-ondersteuning <!--694397-->
Intune biedt nu volledige ondersteuning en volledig beheer voor Android 7.1.1.

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them---unknown--"></a>Oplossing voor het probleem waarbij iOS-apparaten inactief zijn of waarbij de beheerconsole er niet mee kan communiceren <!--unknown-->
Wanneer het contact tussen de apparaten van gebruikers en Intune verloren gaat, kunt u de gebruikers stappen voor probleemoplossing aandragen waarmee ze weer toegang krijgen tot de bedrijfsresources. Zie [Apparaten zijn inactief of de beheerconsole kan er niet mee communiceren](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="notices"></a>Mededelingen

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Standaardinstelling voor het beheren van Windows-desktops via Windows-instellingen <!--663050-->
Het standaardgedrag voor het registreren van Windows 10-desktops verandert. Nieuwe registraties volgen het standaardproces van registratie via de MDM-agent in plaats van via de pc-agent.

De bedrijfsportalwebsite biedt gebruikers van Windows 10-desktops registratie-instructies om ze te helpen bij het toevoegen van Windows 10-desktopcomputers als mobiele apparaten. Dit heeft geen gevolgen voor momenteel ingeschreven pc's en met behulp van de pc-agent kan uw organisatie nog altijd Windows 10-desktops beheren [als u dat liever hebt](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

<!--### Company Portal for iOS links open inside the app <!--665954
Links inside of the Company Portal app for iOS, including those to documentation and apps, will open directly in the Company Portal app using an in-app view of Safari. This update will ship separately from the service update in January.-->

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Verbetering van MAM-ondersteuning voor selectief wissen <!--581242-->
Eindgebruikers krijgen extra informatie over het verkrijgen van toegang tot werk- of schoolgegevens als die gegevens automatisch worden verwijderd op basis van het beleid 'Offline interval voordat app-gegevens worden gewist'.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Bedrijfsportal voor iOS-koppelingen openen in de app <!--665954-->
Koppelingen in de bedrijfsportal-app voor iOS, inclusief koppelingen naar documentatie en apps, worden rechtstreeks in de bedrijfsportal-app geopend met behulp van in-app-weergave van Safari. Deze update wordt afzonderlijk van de service-update in januari verzonden.

### <a name="modernizing-the-company-portal-website---753980--"></a>De bedrijfsportalwebsite moderniseren <!--753980-->
Te beginnen in februari ondersteunt de bedrijfsportalwebsite apps die zijn gericht op gebruikers die geen beheerde apparaten hebben. De website wordt in overeenstemming gebracht met andere Microsoft-producten en -services met een nieuw contrasterend kleurenschema, dynamische illustraties en een ‘hamburgermenu’, ![hamburgermenu van de bedrijfsportalwebsite](./media/CP_hamburger_menu.png) dat contactgegevens van de helpdesk bevat, alsmede informatie over bestaande beheerde apparaten. De landingspagina wordt opnieuw ingedeeld om de nadruk te leggen op apps die beschikbaar zijn voor gebruikers, met carrousels voor uitgelichte en recent bijgewerkte apps. U kunt voor-en-na afbeeldingen vinden op de pagina [Wat is er nieuw in de app-gebruikersinterface van Intune?](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui#January_2017).

### <a name="new-documentation-for-app-protection-policies---583398--"></a>Nieuwe documentatie voor app-beveiligingsbeleid<!--583398-->
We hebben de documentatie bijgewerkt voor beheerders en app-ontwikkelaars die beleid voor app-beveiliging (ook wel MAM-beleid genoemd) willen inschakelen in hun iOS- en Android-apps met behulp van de Intune App Wrapping Tool of Intune App SDK.

De volgende artikelen zijn bijgewerkt:

* [Bepalen hoe u apps voorbereidt op Mobile Application Management met Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [iOS-apps voorbereiden voor Mobile Application Management met de Intune App Wrapping Tool](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Aan de slag met de Microsoft Intune App SDK](https://docs.microsoft.com/intune/develop/intune-app-sdk-get-started)
* [Ontwikkelaarshandleiding voor Intune App SDK voor iOS](https://docs.microsoft.com/intune/develop/intune-app-sdk-ios)

De volgende artikelen zijn nieuwe toevoegingen aan de documentenbibliotheek:

* [Intune App SDK Cordova-invoegtoepassing](https://docs.microsoft.com/intune/develop/intune-app-sdk-cordova)
* [Intune App SDK Xamarin-onderdeel](https://docs.microsoft.com/intune/develop/intune-app-sdk-xamarin)

<!--### Progress bar when launching the Company Portal on iOS <!--665978
The Company Portal for iOS is introducing a progress bar on the launch screen to provide the user with information about the loading processes that occur. There will be a phased rollout of the progress bar to replace the spinner. This means that some of your users will see the new progress bar while others will continue to see the spinner.-->

### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Voortgangsbalk bij het starten van de bedrijfsportal in iOS <!--665978-->
De bedrijfsportal voor iOS introduceert een voortgangsbalk op het startscherm met informatie voor de gebruiker over het laden van processen die optreden. Er is een gefaseerde rollout van de voortgangsbalk als vervanging van het kringveld. Dit betekent dat sommige van uw gebruikers de nieuwe voortgangsbalk te zien krijgen, terwijl anderen blijven het kringveld blijven zien.

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Wat is er nieuw in de openbare preview-versie van de nieuwe Intune-ervaring voor beheerders in Azure <!--736542-->

Aan het begin van kalenderjaar 2017 migreren we de volledige functionaliteit voor beheerders naar Azure, voor krachtig en geïntegreerd beheer van EMS-kernwerkstromen op een modern serviceplatform dat kan worden uitgebreid met Graph API’s.

Vanaf deze maand zal de openbare preview-versie van de nieuwe beheerderservaring te zien zijn voor nieuwe evaluatietenants in de Azure-portal. Tijdens de preview-periode worden de mogelijkheden en pariteit met de bestaande Intune-console iteratief geleverd.

De beheerderservaring in de Azure-portal zal gebruikmaken van de eerder aangekondigde nieuwe functionaliteit voor groepen en targeting. Wanneer uw bestaande tenant wordt gemigreerd naar de nieuwe ervaring voor groepen, vindt ook de migratie plaats naar de preview-versie van de nieuwe beheerderservaring. Als u in de tussentijd de nieuwe functionaliteit wilt testen of bekijken totdat de migratie van uw tenant is voltooid, kunt u zich aanmelden voor een nieuw Intune-evaluatieaccount of de [nieuwe documentatie](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune) raadplegen.

Als u vragen hebt over de planning van de migratie van uw tenant, neemt u contact op met het migratieteam via [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

U kunt [hier](https://docs.microsoft.com/intune-azure/introduction/whats-new) vinden wat er nieuw is in de Intune-preview-versie in Azure.

### <a name="see-also"></a>Zie tevens
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap voor cloudplatform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Wat is nieuw in de Azure-preview?](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Wat is er nieuw in de gebruikersinterface van de bedrijfsportal?](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Wat is er nieuw (archief)](whats-new-archive.md)



<!--HONumber=Feb17_HO1-->


