---
title: Intune App SDK Xamarin-onderdeel
description: 
keywords: SDK, Xamarin, intune
author: erikre
manager: angrobe
ms.author: erikre
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ae53ced489542ba7e675e547740f1858d761c7ab
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/04/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Intune App SDK Xamarin-onderdeel

> [!NOTE]
> U kunt desgewenst eerst het artikel [Aan de slag met Intune App SDK](app-sdk-get-started.md) lezen, waarin wordt uitgelegd hoe u de integratie voor elk ondersteund platform kunt voorbereiden.



## <a name="overview"></a>Overzicht
Met het [Intune App SDK Xamarin-onderdeel](https://components.xamarin.com/view/microsoft.intune.mam) kunt u het [appbeveleigingsbeleid voor Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) inschakelen in iOS- en Android-apps die zijn gebouwd met Xamarin. Met dit onderdeel kunnen ontwikkelaars eenvoudig beschermingsfuncties van Intune inbouwen in hun Xamarin-apps.

> [!NOTE]
> Ondersteuning voor de Intune SDK voor Xamarin is momenteel beschikbaar in de preview-versie. 

Met de Microsoft Intune App SDK Xamarin Component kunt u Intune-beveiligingsbeleid voor apps (ook wel APP- of MAM-beleid genoemd) opnemen in de apps die u met Xamarin hebt ontwikkeld. Een MAM-app is geïntegreerd met de Intune App SDK. IT-beheerders kunnen app-beveiligingsbeleid implementeren in uw mobiele app wanneer die actief door Intune wordt beheerd.

## <a name="whats-supported"></a>Wat wordt ondersteund

### <a name="developer-machines"></a>Machines van ontwikkelaars
* macOS


### <a name="mobile-app-platforms"></a>Mobiele app-platformen
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Scenario’s voor Intune Mobile Application Management

* Apparaten die zijn ingeschreven bij Intune MDM
* Apparaten die zijn ingeschreven bij EMM van derden
* Onbeheerde apparaten (niet ingeschreven bij een MDM)

Xamarin-apps die zijn gemaakt met de Intune App SDK Xamarin Component, kunnen nu app-beveiligingsbeleid van Intune ontvangen op apparaten die wel en apparaten die niet zijn ingeschreven in Mobile Device Management (MDM) van Intune.

## <a name="prerequisites"></a>Vereisten

* **[Alleen android]** Op het apparaat moet de meest recente Microsoft Intune-bedrijfsportal-app zijn geïnstalleerd.

## <a name="get-started"></a>Aan de slag

1.  Download **Xamarin component.exe** [hier](https://components.xamarin.com/submit/xpkg) en pak het uit.

2. Lees de [licentievoorwaarden](https://components.xamarin.com/license/microsoft.intune.mam) voor het Microsoft Intune MAM Xamarin-onderdeel.

3.  Download de map Intune App SDK Xamarin Component van [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) of [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam) en pak de map uit. De bestanden die u in stap 1 en stap 3 hebt gedownload, moeten zich op hetzelfde mappenniveau bevinden.

4.  Voer `Xamarin.Component.exe install <.xam> file` uit als beheerder vanaf de opdrachtregel.

5.  Klik in Visual Studio met de rechtermuisknop op **onderdelen** in uw eerder gemaakte Xamarin-project.

6.  Selecteer **Onderdelen bewerken** en voeg het Intune App SDK-onderdeel toe dat u lokaal op uw computer hebt gedownload.



## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>App-beveiligingsbeleid voor Intune inschakelen in uw mobiele iOS-app
1.  Volg de algemene stappen voor het integreren van de Intune App SDK in een mobiele iOS-app. U kunt beginnen met stap 3 van de integratie-instructies uit de [Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor iOS](app-sdk-ios.md#build-the-sdk-into-your-mobile-app).
    **Belangrijk**: delen van sleutelketens inschakelen voor een app wijkt in Visual Studio enigszins af van de procedure in Xcode. Open de plist Entitlements van de app en zorg ervoor dat de optie 'Enable Keychain' is ingeschakeld en dat de juiste groepen voor het delen van de sleutelketen in die sectie zijn toegevoegd. Controleer vervolgens of de plist Entitlements is opgegeven in het veld 'Custom Entitlements' van de opties voor 'iOS Bundle Signing' van het project voor alle betrokken configuratie-/platformcombinaties.
2.  Nadat het onderdeel is toegevoegd en de app correct is geconfigureerd, kan uw app gebruikmaken van de Intune SDK API's. Daarvoor moet u de volgende naamruimte opnemen:
      ```csharp
      using Microsoft.Intune.MAM;
      ```
3.    Om het app-beveiligingsbeleid te kunnen ontvangen, moet uw app worden geregistreerd in de Intune MAM-service. Als uw app al de Azure Active Directory Authentication Library (ADAL) gebruikt om gebruikers te verifiëren, moet uw app de UPN van de gebruiker doorgeven aan de registerAndEnrollAccount-methode van IntuneMAMEnrollmentManager nadat deze is geverifieerd:
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      **Belangrijk**: zorg ervoor dat u de standaard ADAL-instellingen van de Intune App SDK overschrijft met die van uw app. U kunt dit doen via de IntuneMAMSettings-woordenlijst in de Info.plist van de app, zoals vermeld in de [Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk), maar u kunt ook gebruikmaken van de eigenschappen voor het overschrijven van AAD van de IntuneMAMPolicyManager-instantie. De methode Info.plist wordt aanbevolen voor toepassingen waarvan de ADAL-instellingen statisch zijn, terwijl de eigenschappen voor overschrijven worden aanbevolen voor toepassingen die deze waarden tijdens runtime bepalen. 
      
      Als uw app geen gebruikmaakt van ADAL en u verificatie wilt uitvoeren met de SDK Intune, moet uw app de loginAndEnrollAccoun-methode van IntuneMAMEnrollmentManager aanroepen:
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>App-beveiligingsbeleid inschakelen in uw mobiele Android-app
Voor Android-apps op basis van Xamarin die geen gebruik maken van een UI-framework, leest en volgt u de [Ontwikkelaarshandleiding voor de Intune App SDK voor Android](app-sdk-android.md). Voor uw Android-app op basis van Xamarin moet u klasse, methoden en activiteiten vervangen door hun MAM-equivalent op basis van de [tabel](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) in de handleiding. Als uw app geen definitie van een `android.app.Application`-klasse bevat, moet u een klasse maken en zorgen voor overname van `MAMApplication`.

Voor Xamarin Forms en andere UI-frameworks hebben we het hulpprogramma `MAM.Remapper` meegeleverd. Dit hulpprogramma voert de klassevervanging voor u uit. U moet echter wel de volgende stappen uitvoeren:

1.  Voeg een verwijzing toe naar `Microsoft.Intune.MAM.Remapper.Tasks` NuGet-pakketversie 0.1.0.0 of hoger.

2.  Voeg de volgende regel toe aan uw Android-csproj:
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Stel de build-bewerking van het toegevoegde bestand `remapping-config.json` in op **RemappingConfigFile**. Het meegeleverde `remapping-config.json` werkt alleen met Xamarin.Forms. Raadpleeg het Leesmij-bestand in het Remapper NuGet-pakket voor andere UI-frameworks.

## <a name="next-steps"></a>Volgende stappen

U hebt de basisstappen voor het inbouwen van het onderdeel in uw app voltooid. U kunt nu de stappen in de Xamarin Android-voorbeeldapp volgen. We bieden twee voorbeelden, één voor Xamarin.Forms en het andere voor Android.
