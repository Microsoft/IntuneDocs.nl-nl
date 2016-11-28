---
title: Microsoft Intune App SDK Xamarin-onderdeel | Microsoft Intune
description: 
keywords: SDK, Xamarin, intune
author: oydang
manager: karthikaraman
ms.author: oydang
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: karthikaraman
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ca4623db80d711f3543b6d688fb1bb1ef228c62c
ms.openlocfilehash: e2d43fff8772046fe7426b267e39d53b278d4e5c


---

# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Intune App SDK Xamarin-onderdeel

## <a name="overview"></a>Overzicht
Met het [Intune App SDK Xamarin-onderdeel](https://components.xamarin.com/view/microsoft.intune.mam) kunt u de [beheerfuncties voor Intune Mobile App](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) inschakelen in iOS- en Android-apps die zijn gebouwd met Xamarin. Met dit onderdeel kunnen ontwikkelaars eenvoudig functies voor app-restrictie en gegevensbescherming inbouwen in hun app op basis van Xamarin.

U zult merken dat u SDK-functies kunt inschakelen zonder het gedrag van uw app te wijzigen. Als u het onderdeel hebt gemaakt in uw mobiele iOS- of Android-app, kan de IT-beheerder via Microsoft Intune beleid implementeren dat verschillende functies voor gegevensbescherming ondersteunt.

## <a name="supported-scenarios"></a>Ondersteunde scenario's

### <a name="platforms"></a>Platformen
* Android
* iOS


### <a name="emm-scenarios"></a>EMM-scenario's

* Intune MAM op bij MDM van Intune ingeschreven apparaten
* Intune MAM op bij EMM van derden ingeschreven apparaten
* Intune MAM op niet-ingeschreven, niet-beheerde apparaten

Xamarin-apps die zijn gemaakt met het Intune App SDK Xamarin-onderdeel kunnen nu Mobile Application Management-beleid (MAM) van Intune ontvangen op zowel apparaten die zijn ingeschreven bij Mobile Device Management als apparaten die niet zijn ingeschreven.

## <a name="prerequisites"></a>Vereisten

* **[Alleen android]** Op het apparaat moet altijd de meest recente Microsoft Intune-bedrijfsportal-app zijn geïnstalleerd.

## <a name="get-started"></a>Aan de slag

1.  Download **Xamarin component.exe** [hier](https://components.xamarin.com/submit/xpkg) en pak het uit.

2. Lees de [licentievoorwaarden](https://components.xamarin.com/license/microsoft.intune.mam) voor het Microsoft Intune MAM Xamarin-onderdeel.

3.  Download de map Intune App SDK Xamarin Component van [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) of [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam) en pak de map uit. De bestanden die u in stap 1 en stap 2 hebt gedownload, moeten zich op hetzelfde mappenniveau bevinden.

4.  Voer `Xamain.Component.exe install <.xam> file` uit als beheerder vanaf de opdrachtregel.

5.  Klik in Visual Studio met de rechtermuisknop op **onderdelen** in uw eerder gemaakte Xamarin-project.

6.  Selecteer **Onderdelen bewerken** en voeg het Intune App SDK-onderdeel toe dat u lokaal op uw computer hebt gedownload.



## <a name="enabling-intune-mam-in-your-ios-mobile-app"></a>Intune MAM inschakelen in uw mobiele iOS-app
1.  Als u de Intune App SDK wilt initialiseren, moet u API's in de `AppDelegate.cs`-klasse aanroepen. Bijvoorbeeld:

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.  Nu het onderdeel is toegevoegd en geïnitialiseerd, kunt u de algemene stappen volgen voor het inbouwen van de App SDK in een mobiele iOS-app. De volledige documentatie voor het inschakelen van systeemeigen iOS-apps vindt u in de [Ontwikkelaarshandleiding voor Intune App SDK voor iOS](intune-app-sdk-ios).
3. **Belangrijk**: Er zijn verschillende wijzigingen die specifiek zijn voor iOS-apps op basis van Xamarin. Bij het inschakelen van sleutelketengroepen moet u bijvoorbeeld het volgende toevoegen om de Xamarin-voorbeeldapp in te voegen die we in het onderdeel hebben opgenomen. Hieronder volgt een voorbeeld van de groepen die u in uw sleutelketengroepen aanwezig moeten zijn:

      ```xml
      <?xml version="1.0" encoding="UTF-8"?>
      <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
      <plist version="1.0">
            <dict>
                  <key>keychain-access-groups</key>
                  <array>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample</string>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample.intunemam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.intune.mam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.adalcache</string>
                  </array>
            </dict>
      </plist>
      ```

U hebt de benodigde stappen voor het inbouwen van het onderdeel in uw iOS-app op basis van Xamarin voltooid. Als u Xcode gebruikt voor het ontwikkelen van uw project, kunt u de `Intune App SDK Settings.bundle` gebruiken. Hiermee kunt u beleidsinstellingen van Intune in- en uitschakelen tijdens het ontwikkelen van uw project met het oog op testen en foutopsporing. Volg de stappen in de [Ontwikkelaarshandleiding voor Intune App SDK voor iOS](intune-app-sdk-ios) en lees de sectie over [foutopsporing in Xcode](intune-app-sdk-ios#debug-information) om te profiteren van dit pakket.

## <a name="enabling-mam-in-your-android-mobile-app"></a>MAM inschakelen in uw mobiele Android-app
Voor Android-apps op basis van Xamarin die geen gebruikmaken van een UI-framework, leest en volgt u de [Ontwikkelaarshandleiding voor de Intune App SDK voor Android]. Voor uw Android-app op basis van Xamarin moet u klasse, methoden en activiteiten vervangen door hun MAM-equivalent op basis van de [tabel](intune-app-sdk-android#replace-classes-methods-and-activities-with-their-mam-equivalent-required) in de handleiding. Als uw app geen definitie van een `android.app.Application` klasse bevat, moet u een klasse maken en zorgen voor overname van `MAMApplication`.

Voor Xamarin Forms en andere UI-frameworks hebben we het hulpprogramma `MAM.Remapper` meegeleverd. Dit hulpprogramma voert de klassevervanging voor u uit. U moet echter wel de volgende stappen uitvoeren:

1.  Voeg een verwijzing toe naar ` Microsoft.Intune.MAM.Remapper.Tasks` Nuget-pakketversie 0.1.0.0 of hoger.

2.  Voeg de volgende regel toe aan uw Android-csproj:
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Stel de build-bewerking van het toegevoegde bestand `remapping-config.json` in op **RemappingConfigFile**. Het meegeleverde `remapping-config.json` werkt alleen met Xamarin.Forms. Raadpleeg het Leesmij-bestand in het Remapper Nuget-pakket voor andere UI-frameworks.

## <a name="test-your-app"></a>Uw app testen

U hebt de basisstappen voor het inbouwen van het onderdeel in uw app voltooid. U kunt nu de stappen in de Xamarin Android-voorbeeldapp volgen. We bieden twee voorbeelden, één voor Xamarin.Forms en het andere voor Android.



<!--HONumber=Nov16_HO3-->


