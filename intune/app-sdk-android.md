---
title: Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor Android
description: Met de Microsoft Intune App SDK voor Android kunt u Intune Mobile App Management (MAM) opnemen in uw Android-app.
keywords: SDK
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 403917adb1fb1156f0ed0027a316677d1e4f2f84
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2017
---
# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor Android

> [!NOTE]
> U kunt desgewenst eerst [Overzicht van de Intune App SDK](app-sdk.md) lezen voor meer informatie over de huidige functies en hoe u de integratie voor elk ondersteund platform voorbereidt.

Met de Microsoft-SDK voor de Intune-app voor Android kunt u Intune-beveiligingsbeleid voor apps (ook wel **APP-** of MAM-beleid genoemd) opnemen in uw systeemeigen Android-app. Een toepassing die is geoptimaliseerd voor Intune, is een toepassing die is geïntegreerd in de SDK voor de Intune-app. Intune-beheerders kunnen eenvoudig app-beveiligingsbeleid implementeren in uw app met Intune-functionaliteit wanneer de app actief door Intune wordt beheerd.


## <a name="whats-in-the-sdk"></a>Inhoud van de SDK

De SDK voor de Intune-app bevat de volgende bestanden:  

* **Microsoft.Intune.MAM.SDK.aar**: de SDK-onderdelen, met uitzondering van de JAR-bestanden voor Support.V4 en Support.V7. Dit bestand kan worden gebruikt in plaats van de afzonderlijke onderdelen, als uw build-systeem AAR-bestanden ondersteunt.
* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: de interfaces die nodig zijn om MAM in te schakelen in apps die gebruikmaken van de Android v4-ondersteuningsbibliotheek. Apps die deze ondersteuning nodig hebben, moeten rechtstreeks verwijzen naar het JAR-bestand.
* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: de interfaces die nodig zijn om MAM in te schakelen in apps die gebruikmaken van de Android v7-ondersteuningsbibliotheek. Apps die deze ondersteuning nodig hebben, moeten rechtstreeks verwijzen naar het JAR-bestand.
* **proguard.txt**: bevat ProGuard-regels die moeten worden toegepast als u ProGuard gebruikt.
* **CHANGELOG.txt**: bevat een overzicht van wijzigingen in elke SDK-versie.
* **THIRDPARTYNOTICES.TXT**: een kennisgeving waarin code van derden en/of OSS-code die in uw app wordt gecompileerd aan de rechthebbenden wordt toegeschreven.

Als uw buildsysteem geen AAR-bestanden ondersteunt, kunt u de volgende bestanden in plaats van Microsoft.Intune.MAM.SDK.aar mag gebruiken.
* **Microsoft.Intune.MAM.SDK.jar**: de interfaces die nodig zijn om MAM en interoperabiliteit in te schakelen met de Intune-bedrijfsportal-app. Apps moeten dit opgeven als verwijzing naar de Android-bibliotheek.
* **De resourcemap**: de resources (zoals tekenreeksen) waarop de SDK is gebaseerd.
* **AndroidManifest.xml**: invoerpunten en de bibliotheekvereisten.


## <a name="requirements"></a>Vereisten

De Intune App SDK is een gecompileerd Android-project. Als gevolg hiervan wordt de SDK grotendeels niet beïnvloed door de versie van Android die de app gebruikt voor de minimumversie of doel-API-versies. De SDK biedt ondersteuning voor Android API 14 (Android 4.0+) tot en met Android API 25 (Android 7.1).



### <a name="company-portal-app"></a>Bedrijfsportal-app
De SDK voor de Intune-app voor Android is afhankelijk van de aanwezigheid van de [bedrijfsportal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)-app op het apparaat voor het inschakelen van app-beveiligingsbeleid. De bedrijfsportal haalt het app-beveiligingsbeleid op van de Intune-service. Tijdens de initialisatie van de app worden het beleid en de code geladen om het betreffende beleid af te dwingen bij de bedrijfsportal.

> [!NOTE]
> Wanneer de bedrijfsportal-app zich niet op het apparaat bevindt, gedraagt een app met Intune-functionaliteit zich hetzelfde als een normale app die geen ondersteuning biedt voor Intune-beleid voor de beveiliging van apps.

Voor app-beveiliging zonder apparaatregistratie hoeft de gebruiker het apparaat _**niet**_ te registreren via de bedrijfsportal-app.

## <a name="sdk-integration"></a>SDK-integratie

### <a name="build-integration"></a>Build-integratie

De SDK voor de Intune-app is een standaard-Android-bibliotheek zonder externe afhankelijkheden. **Microsoft.Intune.MAM.SDK.jar** bevat zowel de benodigde interfaces om app-beveiligingsbeleid te activeren als de code die nodig is om samen te werken met de Microsoft Intune-bedrijfsportal-app.

**Microsoft.Intune.MAM.SDK.jar** moet worden opgegeven als een Android-bibliotheekverwijzing. Hiervoor opent u uw app-project in Android Studio en gaat u naar **Bestand > Nieuw > Nieuwe module** en selecteert u **.JAR/.AAR-pakket importeren**. Selecteer het Android-archiefpakket Microsoft.Intune.MAM.SDK.aar.

Daarnaast bevatten **Microsoft.Intune.MAM.SDK.Support.v4** en **Microsoft.Intune.MAM.SDK.Support.v7** Intune-varianten van respectievelijk `android.support.v4` en `android.support.v7`. Ze zijn niet ingebouwd in Microsoft.Intune.MAM.SDK.aar voor het geval een app de ondersteuningsbibliotheken niet wil opnemen. Het zijn standaard-JAR-bestanden in plaats van Android-bibliotheekprojecten.

#### <a name="proguard"></a>ProGuard

Als [ProGuard](http://proguard.sourceforge.net/) (of een ander mechanisme voor het comprimeren/onleesbaar maken van code) wordt gebruikt als een ontwikkelstap, moeten Intune SDK-klassen worden uitgesloten. Voor ProGuard kunt dit realiseren door de regels op te nemen uit het bestand proguard.txt dat wordt gedistribueerd met de SDK.

De Azure Active Directory Authentication Libraries (ADAL) hebben mogelijk hun eigen ProGuard-beperkingen. Als uw app ADAL integreert, moet u de documentatie van de ADAL volgen voor deze beperkingen.

### <a name="entry-points"></a>Invoerpunten

Deze machtigingen zijn vereist voor Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) om brokered verificatie uit te voeren. Als deze machtigingen niet worden toegekend aan de app of worden ingetrokken door de gebruiker, worden verificatiestromen waarvoor de broker (de bedrijfsportal-app) is vereist, uitgeschakeld.

De SDK voor de Intune-app vereist wijzigingen in de broncode van een app om Intune-beleid voor de beveiliging van apps in te schakelen. Dit wordt gedaan door de Android-basisklassen te vervangen door gelijkwaardige Intune-basisklassen, waarvan de namen het voorvoegsel **MAM** hebben. De SDK-klassen begeven zich tussen de Android-basisklasse en de eigen afgeleide app-versie van die klasse. Als we een activiteit als voorbeeld gebruiken, krijgt u uiteindelijk een overnamehiërarchie die er als volgt uitziet: `Activity` > `MAMActivity` > `AppSpecificActivity`.

Wanneer `AppSpecificActivity` bijvoorbeeld een interactie aangaat met het bovenliggende item (bijvoorbeeld door `super.onCreate()` aan te roepen), is `MAMActivity` is de superklasse.

Android-apps hebben gewoonlijk één modus en hebben toegang tot het systeem via hun [**context**](https://developer.android.com/reference/android/content/Context.html)-object. Apps waarin de SDK voor de Intune-app is geïntegreerd, hebben daarentegen twee modi. Deze apps houden toegang tot het systeem via het `Context`-object. Afhankelijk van de algemene `Activity` die wordt gebruikt, wordt het `Context`-object verstrekt door Android of zal het op intelligente wijze multiplexen tussen een beperkte weergave van het systeem en de `Context` die wordt verstrekt door Android.


## <a name="replace-classes-methods-and-activities-with-their-mam-equivalent"></a>Klassen, methoden en activiteiten vervangen door hun MAM-equivalent

Android-basisklassen moeten worden vervangen door hun respectieve MAM-equivalenten. Hiertoe zoekt u alle exemplaren van de klassen op in de volgende tabel en vervangt u deze door het equivalent in de Intune App SDK.

| Android-basisklasse | Intune App SDK-vervanging |
|--|--|
| enroid.app.Activity | MAMActivity |
| enroid.app.ActivityGroup | MAMActivityGroup |
| enroid.app.AliasActivity | MAMAliasActivity |
| enroid.app.Application | MAMApplication |
| enroid.app.DialogFragment | MAMDialogFragment |
| enroid.app.ExpenableListActivity | MAMExpenableListActivity |
| enroid.app.Fragment | MAMFragment |
| enroid.app.IntentService | MAMIntentService |
| enroid.app.LauncherActivity | MAMLauncherActivity |
| enroid.app.ListActivity | MAMListActivity |
| enroid.app.NativeActivity | MAMNativeActivity |
| enroid.app.PendingIntent | MAMPendingIntent (zie de opmerkingen hieronder) |
| enroid.app.Service | MAMService |
| enroid.app.TabActivity | MAMTabActivity |
| enroid.app.TaskStackBuilder | MAMTaskStackBuilder |
| enroid.app.backup.BackupAgent | MAMBackupAgent |
| enroid.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| enroid.app.backup.FileBackupHelper | MAMFileBackupHelper |
| enroid.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| enroid.content.BroadcastReceiver | MAMBroadcastReceiver |
| enroid.content.ContentProvider | MAMContentProvider |
| enroid.os.Binder | MAMBinder (alleen vereist als de Binder niet is gegenereerd op basis van een AIDL-interface (Android Interface Definition Language)) |
| enroid.provider.DocumentsProvider | MAMDocumentsProvider |
| enroid.preference.PreferenceActivity | MAMPreferenceActivity |


### <a name="microsoftintunemamsdksupportv4jar"></a>Microsoft.Intune.MAM.SDK.Support.v4.jar:

| Android-klasse Intune MAM | Intune App SDK-vervanging |
|--|--|
| enroid.suppof eent.v4.app.DialogFragment | MAMDialogFragment
| enroid.suppof eent.v4.app.FragmentActivity | MAMFragmentActivity
| enroid.suppof eent.v4.app.Fragment | MAMFragment
| enroid.suppof eent.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| enroid.suppof eent.v4.content.FileProvider | MAMFileProvider

### <a name="microsoftintunemamsdksupportv7jar"></a>Microsoft.Intune.MAM.SDK.Support.v7.jar:

|Android-klasse | Intune App SDK-vervanging |
|--|--|
|enroid.suppof eent.v7.app.ActionBarActivity | MAMActionBarActivity |


### <a name="renamed-methods"></a>Methoden waarvan de naam is gewijzigd
Nadat u hebt afgeleid van een van de MAM-invoerpunten, kunt u `Context` net als anders op een veilige manier gebruiken, bijvoorbeeld om `Activity`-klassen te starten en `PackageManager` te gebruiken.

In veel gevallen is een methode die in de Android-klasse beschikbaar is, in de vervangende MAM-klasse als definitief gemarkeerd. De vervangende MAM klasse biedt in dit geval een gelijknamige methode (meestal voorafgegaan door `MAM`) die in plaats daarvan moet worden overschreven. Wanneer een activiteit wordt afgeleid van `MAMActivity`, moet niet `onCreate()` worden overschreven en niet `super.onCreate()` worden aangeroepen, maar moet `Activity` `onMAMCreate()` overschrijven en `super.onMAMCreate()` aanroepen. De Java-compiler moet de laatste beperkingen afdwingen om het onbedoeld onderdrukken van de oorspronkelijke methode in plaats van de MAM-equivalent te voorkomen.

### <a name="pendingintent"></a>PendingIntent
In plaats van `PendingIntent.get*` moet u de methode `MAMPendingIntent.get*` gebruiken. Vervolgens kunt u gewoon de resulterende `PendingIntent` gebruiken.

### <a name="manifest-replacements"></a>Manifestvervangingen
Houd er rekening mee dat het mogelijk nodig om enkele van de bovenstaande klassevervangingen uit te voeren, zowel in het manifest als de Java-code. Speciale opmerking:
* Manifestverwijzingen naar `android.support.v4.content.FileProvider` moeten worden vervangen door `com.microsoft.intune.mam.client.support.v4.content.MAMFileProvider`.


## <a name="sdk-permissions"></a>SDK-machtigingen

De Intune App SDK vereist drie [Android-systeemmachtigingen](https://developer.android.com/guide/topics/security/permissions.html) voor apps waarin de SDK wordt geïntegreerd:

* `android.permission.GET_ACCOUNTS` (aangevraagd tijdens runtime indien nodig)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

Deze machtigingen zijn vereist voor Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) om brokered verificatie uit te voeren. Als deze machtigingen niet worden toegekend aan de app of worden ingetrokken door de gebruiker, worden verificatiestromen waarvoor de broker (de bedrijfsportal-app) is vereist, uitgeschakeld.

## <a name="logging"></a>Logboekregistratie

Logboekregistratie moet vroegtijdig worden geïnitialiseerd om de meeste waarde uit de gegevens in het logboek te halen. `Application.onMAMCreate()` is doorgaans de beste plaats om logboekregistratie te initialiseren.

Als u MAM-logboeken in uw app wilt ontvangen, maakt u een [Java-handler](http://docs.oracle.com/javase/7/docs/api/java/util/logging/Handler.html) en voegt u deze toe aan de `MAMLogHandlerWrapper`. Zodoende wordt `publish()` aangeroepen voor de toepassingshandler voor elk logboekbericht.

```java
/**
 * Global log handler that enables fine grained PII filtering within MAM logs.  
 *
 * To start using this you should build your own log handler and add it via
 * MAMComponents.get(MAMLogHandlerWrapper.class).addHandler(myHandler, false);  
 *
 * You may also remove the handler entirely via
 * MAMComponents.get(MAMLogHandlerWrapper.class).removeHandler(myHandler);
 */
public interface MAMLogHandlerWrapper {
    /**
     * Add a handler, PII can be toggled.
     *
     * @param handler handler to add.
     * @param wantsPII if PII is desired in the logs.    
     */
    void addHandler(final Handler handler, final boolean wantsPII);

    /**
     * Remove a handler.
     *
     * @param handler handler to remove.
     */
    void removeHandler(final Handler handler);
}
```



## <a name="enable-features-that-require-app-participation"></a>Functies inschakelen waarvoor app-deelname is vereist

Er zijn verschillende beleidsregels voor de beveiliging van apps die de SDK niet op zichzelf kan implementeren. De app kan het eigen gedrag voor deze functies bepalen door gebruik te maken van de verschillende API's in de volgende `AppPolicy`-interface.

```java
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * This function is now deprecated. Please use getIsSaveToLocationAllowed(SaveLocation, String) instead
 * @return True if the app is allowed to save to personal data stores; false otherwise.
 */
@Deprecated
boolean getIsSaveToPersonalAllowed();

/**
 * Check if policy prohibits saving to a content provider location.
 *
 * @param location
 *            a content URI to check
 * @return True if location is not a content URI or if policy does not prohibit saving to the content location.
 */
boolean getIsSaveToLocationAllowed(Uri location);

/**
 * Determines if the SaveLocation passed in can be saved to by the username associated with the cloud service.
 *
 * @param service
 *           see {@link SaveLocation}.
 * @param username
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between
 *           the AAD username and the cloud service username does not exist or the username is not known.
 * @return true if the location can be saved to by the identity, false if otherwise.
 */
boolean getIsSaveToLocationAllowed(SaveLocation service, String username);

/**
 * Whether the SDK PIN prompt is enabled for the app.
 *
 * @return True if the PIN is enabled. False otherwise.
 */
boolean getIsPinRequired();

/**
 * Whether the Intune Managed Browser is required to open web links.
 * @return True if the Managed Browser is required, false otherwise
 */
boolean getIsManagedBrowserRequired();

/**
 * Check if policy allows Contact sync to local contact list.
 *
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();

}

```

> [!NOTE]
> `MAMComponents.get(AppPolicy.class)` retourneert altijd een niet-null-app-beleid, zelfs als voor het apparaat of de app geen Intune-beheerbeleid van toepassing is.

### <a name="example-determine-if-pin-is-required-for-the-app"></a>Voorbeeld: bepalen of er een pincode is vereist voor de app

Als de app zijn eigen gebruikerservaring voor de pincode heeft, wilt u deze mogelijk uitschakelen als de IT-beheerder de SDK zodanig heeft geconfigureerd dat naar de pincode van het apparaat wordt gevraagd. Als u wilt bepalen of de IT-beheerder het app-pincodebeleid voor deze app heeft geïmplementeerd voor de huidige gebruiker, roept u de volgende methode aan:

```java
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

### <a name="example-determine-the-primary-intune-user"></a>Voorbeeld: de primaire Intune-gebruiker bepalen

Naast de API's die worden weergegeven in AppPolicy, wordt ook de user principal name (**UPN**) weergegeven door de `getPrimaryUser()`-API zoals gedefinieerd in de `MAMUserInfo`-interface. U kunt de UPN verkrijgen door het volgende aan te roepen:

```java
MAMUserInfo info = MAMComponents.get(MAMUserInfo.class);
if (info != null) return info.getPrimaryUser();
```

De volledige definitie van de MAMUserInfo-interface vindt u hieronder:

```java
/**
 * External facing user informations.
 *
 */
public interface MAMUserInfo {
       /**
        * Get the primary user name.
        *
        * @return the primary user name or null if the device is not enrolled.
        */
       String getPrimaryUser();
}
```

### <a name="example-determine-if-saving-to-device-or-cloud-storage-is-permitted"></a>Voorbeeld: bepalen of opslaan naar apparaat of opslag in de cloud is toegestaan

Veel apps implementeren functies waarmee de eindgebruiker bestanden lokaal of naar een cloudopslagservice kan opslaan. Met de Intune App SDK kunnen IT-beheerders beveiliging instellen tegen het lekken van gegevens door naar eigen goeddunken beleidsbeperkingen binnen hun organisatie toe te passen.  Een van de beleidsregels waarover IT controle kan uitvoeren, is of de eindgebruiker kan opslaan naar een 'persoonlijke', niet-beheerde gegevensopslag. Dit omvat het opslaan naar een lokale locatie, een SD-kaart of een back-upservice van derden.

**Voor het inschakelen van de functie is app-deelname vereist.** Als uw app de mogelijkheid biedt om rechtstreeks vanuit de app naar persoonlijke of cloudlocaties op te slaan, moet u deze functie implementeren om ervoor te zorgen dat de IT-beheerder kan bepalen of opslaan naar een locatie is toegestaan. De onderstaande API laat de app weten of opslaan naar een persoonlijke opslag volgens het huidige beleid van de Intune-beheerder is toegestaan. De app kan het beleid vervolgens afdwingen omdat deze weet of er via de app een persoonlijke gegevensopslag voor de eindgebruiker beschikbaar is.  

Voer de volgende aanroep uit om te bepalen of het beleid wordt afgedwongen:

```java
MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(
SaveLocation service, String username);
```

... waarbij `service` een van de volgende SaveLocations is:


    * SaveLocation.ONEDRIVE_FOR_BUSINESS
    * SaveLocation.LOCAL
    * SaveLocation.OTHER

De vorige methode waarmee kon worden bepaald of het overeenkomstig het beleid van een gebruiker was toegestaan om gegevens op te slaan naar verschillende locaties, was `getIsSaveToPersonalAllowed()` in dezelfde **AppPolicy**-klasse. Deze functie wordt nu **afgeschaft** en mag niet worden gebruikt. De volgende aanroep is gelijk aan `getIsSaveToPersonalAllowed()`:

```java

MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(SaveLocation.LOCAL, userNameInQuestion);
```

>[!NOTE]
> Gebruik `SaveLocation.OTHER` als de betreffende locatie niet wordt vermeld in de opsomming van **SaveLocations**.


## <a name="register-for-notifications-from-the-sdk"></a>Registreren voor meldingen van de SDK

### <a name="overview"></a>Overzicht
Met de SDK voor de Intune-app kan uw app de werking van bepaald beleid, zoals selectief wissen, beheren bij implementatie door de IT-beheerder. Als een IT-beheerder dergelijk beleid implementeert, wordt met de Intune-service een melding naar de SDK verzonden.

Uw app moet worden geregistreerd voor meldingen van de SDK door een `MAMNotificationReceiver` te maken en deze te registreren met `MAMNotificationReceiverRegistry`. Dit wordt gedaan door de ontvanger en het gewenste type melding op te geven in `App.onCreate`, zoals in het volgende voorbeeld te zien is:

```java
@Override
public void onCreate() {
    super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class)
        .registerReceiver(
            new ToastNotificationReceiver(),
            MAMNotificationType.WIPE_USER_DATA);
    }
```

### <a name="mamnotificationreceiver"></a>MAMNotificationReceiver

De `MAMNotificationReceiver`-interface ontvangt gewoon meldingen van de Intune-service. Sommige meldingen worden rechtstreeks door de SDK verwerkt, terwijl andere deelname van de app vereisen. Een app **moet** Waar of Onwaar retourneren vanaf een melding. De app moet altijd Waar retourneren, tenzij een bepaalde actie die de app naar aanleiding van de melding probeerde uit te voeren, is mislukt.

* Deze fout kan worden gerapporteerd aan de Intune-service. Een voorbeeld van een scenario waarin moet worden gerapporteerd, is als de app geen gebruikersgegevens kan wissen nadat de IT-beheerder een wisactie heeft gestart.

>[!NOTE]
> Het is veilig om te blokkeren in `MAMNotificationReceiver.onReceive`, omdat de callback niet wordt uitgevoerd op de UI-thread.

De `MAMNotificationReceiver`-interface zoals gedefinieerd in de SDK, is hieronder opgenomen:

```java
/**
 * The SDK is signaling that a MAM event has occurred.
 *
 */
public interface MAMNotificationReceiver {

    /**
     * A notification was received.
     *
     * @param notification
     *            The notification that was received.
     * @return The receiver should return true if it handled the
     *   notification without error (or if it decided to ignore the
     *   notification). If the receiver tried to take some action in
     *   response to the notification but failed to complete that
     *   action it should return false.
     */
    boolean onReceive(MAMNotification notification);
}

```

### <a name="types-of-notifications"></a>Typen meldingen

De volgende meldingen worden verzonden naar de app en enkele ervan vereisen mogelijk app-deelname:

* **WIPE_USER_DATA**: deze melding wordt verzonden in een `MAMUserNotification`-klasse. Wanneer deze melding wordt ontvangen, wordt verwacht dat de app alle gegevens verwijdert die zijn gekoppeld aan de bedrijfsidentiteit die is doorgegeven met de `MAMUserNotification`. Deze melding wordt momenteel verzonden tijdens het ongedaan maken van de registratie bij de APP-WE-service. De primaire naam van de gebruiker wordt doorgaans opgegeven tijdens het inschrijvingsproces. Als u zich voor deze melding registreert, moet uw app ervoor zorgen dat alle gegevens van de gebruiker zijn verwijderd. Als u zich niet voor de melding registreert, wordt het standaardgedrag voor selectief wissen uitgevoerd.

* **WIPE_USER_AUXILIARY_DATA**: apps kunnen zich voor deze melding registreren als de SDK voor de Intune-app de standaardactie voor selectief wissen moet uitvoeren, maar er nog steeds bepaalde aanvullende gegevens moeten worden verwijderd wanneer de wisbewerking wordt uitgevoerd.

* **REFRESH_POLICY**: deze melding wordt verzonden in een `MAMUserNotification`. Wanneer deze melding wordt ontvangen, moet alle Intune-beleid in de cache ongeldig worden gemaakt en worden bijgewerkt. Dit wordt doorgaans afgehandeld door de SDK maar moet door de app worden afgehandeld als het beleid op een persistente manier wordt gebruikt.

* **MANAGEMENT_REMOVED**: deze melding wordt verzonden in een `MAMUserNotification` en informeert de app dat deze binnenkort niet meer wordt beheerd. Zodra de app niet meer wordt beheerd, kan deze geen versleutelde bestanden en met MAMDataProtectionManager versleutelde gegevens meer lezen, geen gebruik meer maken van het versleutelde klembord of anderszins deelnemen aan het ecosysteem van beheerde apps.


> [!NOTE]
> Een app moet nooit voor zowel `WIPE_USER_DATA`- als `WIPE_USER_AUXILIARY_DATA`-meldingen.


## <a name="configure-azure-active-directory-authentication-library-adal"></a>Azure Active Directory Authentication Library (ADAL) configureren

Lees eerst de richtlijnen voor de integratie van ADAL in de [ADAL-bibliotheek op GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-android).

De SDK is afhankelijk van [ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) voor de [verificatie](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) en voorwaardelijke startscenario's, die vereisen dat apps worden geconfigureerd met [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). De configuratiewaarden worden aan de SDK doorgegeven via de metagegevens van AndroidManifest.

Als u uw app wilt configureren en de juiste verificatie wilt inschakelen, voegt u het volgende toe aan het app-knooppunt in het bestand AndroidManifest.xml. Sommige van deze configuratie-instellingen zijn alleen vereist als uw app gebruikmaakt van ADAL voor verificatie in het algemeen. In dat geval hebt u de specifieke waarden nodig waarmee uw app zich bij AAD registreert. Dit wordt gedaan om ervoor te zorgen dat de eindgebruiker niet twee keer om verificatie wordt gevraagd doordat AAD twee afzonderlijke registratiewaarden herkent: één van de app en één van de SDK.

```xml
<meta-data
    android:name="com.microsoft.intune.mam.aad.Authority"
    android:value="https://AAD authority/" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.ClientID"
    android:value="your-client-ID-GUID" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.NonBrokerRedirectURI"
    android:value="your-redirect-URI" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.SkipBroker"
    android:value="[true | false]" />
```

### <a name="adal-metadata"></a>ADAL-metagegevens

* **Instantie** is de huidige AAD-instantie die wordt gebruikt. Indien aanwezig moet u uw eigen omgeving gebruiken waar AAD-accounts zijn geconfigureerd. Als deze waarde niet aanwezig is, wordt een standaard Intune-waarde gebruikt.

* **ClientID** is de AAD-ClientID die moet worden gebruikt. U moet de ClientID van uw eigen app gebruiken als deze is geregistreerd bij AD. Als deze waarde niet aanwezig is, wordt een standaard Intune-waarde gebruikt.

* **NonBrokerRedirectURI** AAD-omleidings-URI die moet worden gebruikt in gevallen zonder broker. Als er niets is opgegeven, wordt er een standaardwaarde van `urn:ietf:wg:oauth:2.0:oob` gebruikt. Deze standaardinstellingen is geschikt voor meeste apps.

* **SkipBroker** wordt gebruikt als de ClientID niet is geconfigureerd voor het gebruik van de broker-omleidings-URI. De standaardwaarde is false (onwaar).
    * Voor apps die **ADAL niet integreren** en **niet willen deelnemen aan apparaatbrede brokered verificatie/SSO**, moet dit worden ingesteld op true (waar). Wanneer deze waarde true (waar) is, wordt alleen de omleidings-URI NonBrokerRedirectURI gebruikt.

    * Voor apps die een apparaatbrede SSO-brokering ondersteunen, moet dit false (onwaar) zijn. Wanneer de waarde false (onwaar) is, selecteert de SDK een broker in het resultaat van [`com.microsoft.aad.adal.AuthenticationContext.getRedirectUriForBroker()`](https://github.com/AzureAD/azure-activedirectory-library-for-android) en NonBrokerRedirectURI, op basis van de beschikbaarheid van de broker op het systeem. Over het algemeen is de broker beschikbaar via de bedrijfsportal-app of Azure Authenticator-app.

### <a name="common-adal-configurations"></a>Algemene ADAL-configuraties

Hieronder volgen enkele algemene manieren waarop een app kan worden geconfigureerd met ADAL. Zoek de configuratie van uw app en zorg ervoor dat u de metagegevens van de ADAL-parameters (hierboven uitgelegd) instelt op de benodigde waarden.

1. **App is niet geïntegreerd met ADAL:**

    | Vereiste ADAL-parameter | Waarde |
    |--|--|
    | Instantie | Gewenste omgeving waarin AAD-accounts zijn geconfigureerd. |
    | SkipBroker | True |

2. **App is geïntegreerd met ADAL:**

    |Vereiste ADAL-parameter| Waarde |
    |--|--|
    | Instantie | Gewenste omgeving waarin AAD-accounts zijn geconfigureerd. |
    | ClientID | De ClientID van de app (gegenereerd door Azure AD toen de app is geregistreerd) |
    | NonBrokerRedirectURI | Een geldige omleidings-URI voor de app of standaard `urn:ietf:wg:oauth:2.0:oob`. <br><br> Zorg ervoor dat u de waarde configureert als een acceptabele omleidings-URI voor de ClientID van uw app.
    | SkipBroker | False |


3. **App integreert ADAL, maar biedt geen ondersteuning voor brokered verificatie/apparaatbrede SSP:**

    |Vereiste ADAL-parameter| Waarde |
    |--|--|
    | Instantie | Gewenste omgeving waarin AAD-accounts zijn geconfigureerd. |
    | ClientID | De ClientID van de app (gegenereerd door Azure AD toen de app is geregistreerd) |
    | NonBrokerRedirectURI | Een geldige omleidings-URI voor de app of standaard `urn:ietf:wg:oauth:2.0:oob`. <br><br> Zorg ervoor dat u de waarde configureert als een acceptabele omleidings-URI voor de ClientID van uw app.
    | SkipBroker | **True** |

## <a name="app-protection-policy-without-device-enrollment"></a>App-beveiligingsbeleid zonder apparaatrinschrijving

### <a name="overview"></a>Overzicht
Met Intune-beveiligingsbeleid voor apps zonder apparaatregistratie, ook wel PP-WE of MAM-WE genoemd, kunnen apps worden beheerd door Intune zonder dat het apparaat hoeft te worden ingeschreven voor Intune MDM. APP-WE werkt met of zonder apparaatregistratie. De bedrijfsportal moet nog altijd op het apparaat worden geïnstalleerd, maar de gebruiker hoeft zich niet aan te melden bij de bedrijfsportal en hoeft het apparaat niet te registreren.

> [!NOTE]
> Alle apps moeten app-beveiligingsbeleid ondersteunen zonder apparaatregistratie.

### <a name="workflow"></a>Werkstroom

Wanneer er een nieuwe gebruikersaccount met een app wordt gemaakt, moet het account voor beheer worden geregistreerd bij de SDK voor de Intune-app. De SDK verwerkt de details met betrekking tot de registratie van de app bij de APP-WE-service. Indien nodig worden mislukte registraties na een toepasselijke tijdsinterval opnieuw uitgevoerd.

De app kan ook de status van een geregistreerde gebruiker via de SDK voor de Intune-app opvragen om te bepalen of de toegang van de gebruiker tot de bedrijfsinhoud moet worden geblokkeerd. Er kunnen meerdere accounts worden geregistreerd voor beheer, maar momenteel kan er slechts één account tegelijkertijd actief worden geregistreerd bij de APP-WE-service. Dit betekent dat het app-beveiligingsbeleid slechts door één account op de app tegelijkertijd kan worden ontvangen.

De app is vereist voor het opgeven van een callback om namens de SDK het juiste toegangstoken te verkrijgen van de Azure Active Directory Authentication Library (ADAL). Er wordt verondersteld dat de app al gebruikmaakt van ADAL om gebruikers te verifiëren en om de eigen toegangstokens te verkrijgen.

Wanneer de app een account volledig verwijdert, moet de registratie van dat account door de app ongedaan worden gemaakt om aan te geven dat de app geen beleid meer moet toepassen voor de betreffende gebruiker. Als de gebruiker is geregistreerd in de MAM-service, wordt de registratie van de gebruiker ongedaan gemaakt en wordt de app gewist.


### <a name="overview-of-app-requirements"></a>Een overzicht van de app-vereisten

Als u APP-WE-integratie wilt implementeren, moet uw app het gebruikersaccount registreren bij de MAM SDK:

1. De app _moet_ een instantie van de `MAMServiceAuthenticationCallback`-interface implementeren en registreren. De callbackinstantie moet zo vroeg mogelijk worden geregistreerd in de levenscyclus van de app (doorgaans in de methode `onMAMCreate()` van de toepassingsklasse).

2. Wanneer er een gebruikersaccount is gemaakt en de gebruiker zich heeft aangemeld bij ADAL, _moet_ de app `registerAccountForMAM()` aanroepen.

3. Wanneer een gebruikersaccount volledig wordt verwijderd, moet de app `unregisterAccountForMAM()` aanroepen om het account te verwijderen uit Intune-beheerprogramma.

    > [!NOTE]
    > Als een gebruiker zich tijdelijk bij d app afmeldt, hoeft de app `unregisterAccountForMAM()` niet aan te roepen. De aanroep kan een wisbewerking initiëren waarmee de bedrijfsgegevens voor de gebruiker volledig worden gewist.


### <a name="mamenrollmentmanager"></a>MAMEnrollmentManager

Alle benodigde verificatie- en registratie-API's vindt u in de `MAMEnrollmentManager`-interface. Een verwijzing naar de `MAMEnrollmentManager` kunt u als volgt verkrijgen:

```java
MAMEnrollmentManager mgr = MAMComponents.get(MAMEnrollmentManager.class);

// make use of mgr

```

De geretourneerde `MAMEnrollmentManager`-instantie is gegarandeerd niet null. De API-methoden worden onderverdeeld in twee categorieën: **verificatie** en **accountregistratie**.

> [!NOTE]
> `MAMEnrollmentManager` bevat enkele API-methoden die binnenkort worden afgeschaft. Voor de duidelijkheid worden alleen de relevante methoden en resultaatcodes weergegeven in het onderstaande codeblok.

```java
package com.microsoft.intune.mam.policy;

public interface MAMEnrollmentManager {
    public enum Result {
        AUTHORIZATION_NEEDED,
        NOT_LICENSED,
        ENROLLMENT_SUCCEEDED,
        ENROLLMENT_FAILED,
        WRONG_USER,
        MDM_ENROLLED,
        UNENROLLMENT_SUCCEEDED,
        UNENROLLMENT_FAILED,
        PENDING,
        COMPANY_PORTAL_REQUIRED;
    }

    //Authentication methods
    interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
    }
    void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
    void updateToken(String upn, String aadId, String resourceId, String token);

    //Registration methods
    void registerAccountForMAM(String upn, String aadId, String tenantId);
    void unregisterAccountForMAM(String upn);
    Result getRegisteredAccountStatus(String upn);
}
```

### <a name="account-authentication"></a>Accountverificatie

In deze sectie worden de verificatie-API-methoden in `MAMEnrollmentManager` beschreven en hoe ze gebruikt.

```java
interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
}
void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
void updateToken(String upn, String aadId, String resourceId, String token);
```

1. De app moet de `MAMServiceAuthenticationCallback`-interface implementeren om de SDK toe te staan een ADAL-token voor de opgegeven gebruiker en resource-id aan te vragen. De callbackinstantie moet worden opgegeven voor de `MAMEnrollmentManager` door de bijbehorende `registerAuthenticationCallback()`-methode aan te roepen. Er is mogelijk al zeer vroeg in de levenscyclus van de app een token nodig voor nieuwe registratiepogingen of check-ins voor het vernieuwen van het app-beveiligingsbeleid. De ideale plaats om de callback te registreren, is in de `onMAMCreate()`-methode van de subklasse `MAMApplication` van de app.

2. Met de `acquireToken()`-methode moet het toegangstoken worden gekregen voor de aangevraagde resource-id voor de opgegeven gebruiker. Als het aangevraagde token niet kan worden verkregen, moet null worden geretourneerd.

3. Als de app kan geen token kan verstrekken wanneer de SDK `acquireToken()` aanroept, bijvoorbeeld als de verificatie op de achtergrond is mislukt en het geen geschikt moment is om een gebruikersinterface weer te geven, kan de app op een later tijdstip een token verstrekken door de methode `updateToken()` aan te roepen. Dezelfde UPN, AAD-id en resource-id die zijn aangevraagd door de vorige aanroep naar `acquireToken()`, moeten worden doorgegeven aan `updateToken()`, samen met het token dat uiteindelijk is verkregen. De app moet deze methode zo snel mogelijk aanroepen nadat via de verstrekte callback null is geretourneerd.

> [!NOTE]
> De SDK roept `acquireToken()` periodiek aan om het token te verkrijgen. Het is dus niet strikt noodzakelijk om `updateToken()` aan te roepen. Dit wordt echter wel aanbevolen omdat dit kan helpen bij het tijdig voltooien van check-ins voor de registratie en app-beveiligingsbeleid.


### <a name="account-registration"></a>Accountregistratie

In deze sectie worden de accountregistratie-API-methoden in `MAMEnrollmentManager` beschreven en hoe ze gebruikt.

```java
void registerAccountForMAM(String upn, String aadId, String tenantId);
void unregisterAccountForMAM(String upn);
Result getRegisteredAccountStatus(String upn);
```

1. Als u een account wilt registreren voor beheer, moet de app `registerAccountForMAM()` aanroepen. Een gebruikersaccount wordt geïdentificeerd aan de hand van de bijbehorende UPN en de AAD-gebruikers-id. De tenant-id is ook vereist registratiegegevens aan de AAD-tenant van de gebruiker te koppelen. De SDK probeert de app voor de betreffende gebruiker mogelijk te registreren in de MAM-service. Als de registratie mislukt, zal de registratie periodiek opnieuw worden uitgevoerd totdat de registratie van het account ongedaan is gemaakt. U kunt het doorgaans na 12 tot 24 uur opnieuw proberen. De SDK verstrekt op asynchrone wijze informatie over de status van registratiepogingen via meldingen.

2. Omdat de AAD-verificatie is vereist, kan het gebruikersaccount het beste worden geregistreerd nadat de gebruiker is aangemeld bij de app en is geverifieerd met behulp van de ADAL.
    * De AAD-id en tenant-id van de gebruiker worden als onderdeel van het object [`AuthenticationResult`](https://github.com/AzureAD/azure-activedirectory-library-for-android) geretourneerd via de aanroep voor de ADAL-verificatie. De tenant-id is afkomstig uit de `AuthenticationResult.getTenantID()`-methode.
    * Informatie over de gebruiker vindt u een subobject van het type `UserInfo` die afkomstig is van `AuthenticationResult.getUserInfo()`, en de AAD-gebruikers-id die wordt opgehaald via dat object door `UserInfo.getUserId()` aan te roepen.

3. Als u de registratie van een account bij Intune-beheer ongedaan wilt maken, moet de app `unregisterAccountForMAM()` aanroepen. Als het account is geregistreerd en wordt beheerd, wordt de SDK-registratie van het account ongedaan gemaakt en worden de gegevens gewist. Periodieke registratiepogingen voor het account worden gestopt. De SDK verstrekt op asynchrone wijze via meldingen de status van aanvragen om de registratie ongedaan te maken.

### <a name="important-implementation-notes"></a>Belangrijke opmerkingen voor de implementatie

#### <a name="authentication"></a>Verificatie

* Wanneer de app `registerAccountForMAM()` aanroept, wordt er mogelijk kort daarna, op een andere thread, een callback ontvangen op de `MAMServiceAuthenticationCallback`-interface. In het ideale geval heeft de app voorafgaand aan de registratie van het account zijn eigen token uit ADAL verkregen om het ophalen van het **MAMService-token** te versnellen. Als de app een geldig token retourneert uit de callback, wordt de registratie voortgezet en ontvangt de app het uiteindelijke resultaat via een melding.

* Als de app geen geldig AAD-token retourneert, is het uiteindelijke resultaat van de registratiepoging `AUTHENTICATION_NEEDED`. Als de app dit resultaat ontvangt via een melding, kan dit het registratieproces versnellen door het **MAMService-token** op te halen en de methode `updateToken()` aan te roepen om het registratieproces opnieuw te initiëren. Dit is _niet_ strikt vereist, maar omdat de SDK de periodiek opnieuw registratiepogingen uitvoert en de callback aanroept om het token te verkrijgen.

* De geregistreerde `MAMServiceAuthenticationCallback` van de app wordt ook aangeroepen om een token te verkrijgen voor check-ins voor het periodiek vernieuwen van het app-beveiligingsbeleid. Als de app geen token kan verstrekken wanneer dit wordt aangevraagd, wordt er geen melding ontvangen, maar moet de app proberen een token te verkrijgen en op he volgende geschikte tijdstip `updateToken()` aanroepen om het check-inproces te versnellen. Als een token niet is opgegeven, wordt de callback bij de volgende check-inpoging gewoon aangeroepen.

#### <a name="registration"></a>Registratie

* Voor uw gemak zijnde registratiemethoden idempotent. `registerAccountForMAM()` zal bijvoorbeeld een account alleen registreren en een app alleen proberen te registreren als het account nog niet is geregistreerd, en `unregisterAccountForMAM()` maakt de registratie van een account alleen ongedaan als het account moment is geregistreerd. Alle volgende aanroepen zijn 'no-ops', zodat deze methoden zonder problemen meerdere keren kunnen worden aangeroepen. Daarnaast kan de correspondentie tussen aanroepen naar deze methoden en meldingen van de resultaten niet worden gegarandeerd: oftewel, als `registerAccountForMAM` wordt aangeroepen voor een identiteit die al is geregistreerd, de melding mogelijk niet opnieuw wordt verzonden voor die identiteit. Het is mogelijk dat er meldingen worden verzonden die niet overeenkomen met de aanroepen voor deze methoden, aangezien de SDK mogelijk periodiek registratie op de achtergrond uitvoert en er registraties ongedaan kunnen worden gemaakt op basis van wisverzoeken die van de Intune-service zijn ontvangen.

* De registratiemethoden kunnen worden aangeroepen voor elk aantal verschillende identiteiten, maar momenteel kan er slechts één gebruikersaccount worden geregistreerd. Als er op hetzelfde of vrijwel hetzelfde moment meerdere gebruikersaccounts met een licentie voor Intune en app-beveiligingsbeleid worden geregistreerd, kan niet worden gegarandeerd welk account de race wint.

* Tot slot kunt gegevens bij `MAMEnrollmentManager` opvragen om te zien of een bepaald account is geregistreerd en om de huidige status op te halen met de methode `getRegisteredAccountStatus`. Als het opgegeven account niet is geregistreerd, resulteert deze methode **null**. Als het account is geregistreerd, retourneert deze methode de status van het account als een van de leden van de `MAMEnrollmentManager.Result`-opsomming.

### <a name="result-and-status-codes"></a>Resultaat en statuscodes

Als een account voor het eerst wordt geregistreerd, krijgt het account eerst de status `PENDING`, waarmee wordt aangegeven dat de eerste registratie van de MAM-service nog niet is voltooid. Nadat de registratiepoging is voltooid, wordt er een melding met een van de resultaatcodes in de onderstaande tabel verzonden. Daarnaast retourneert de methode `getRegisteredAccountStatus()` de status van het account, zodat de app altijd kan bepalen of de toegang tot de bedrijfsinhoud voor die gebruiker is geblokkeerd. Als de registratiepoging mislukt, kan de status van het account na verloop van tijd worden gewijzigd, aangezien er op de achtergrond nieuwe registratiepogingen door de SDK worden uitgevoerd.

|Resultaatcode | Uitleg |
| -- | -- |
|AUTHORIZATION_NEEDED | Dit resultaat geeft aan dat er geen token is verstrekt door de geregistreerde `MAMServiceAuthenticationCallback`-instantie van de app of dat het token ongeldig is.  De app moet een geldig token ophalen en indien mogelijk `updateToken()` aanroepen. |
| NOT_LICENSED | De gebruiker heeft geen licentie voor Intune of er kan geen contact met de Intune MAM-service worden opgenomen.  De onbeheerde (normale) status van de app moet blijven gehandhaafd en de gebruiker moet worden geblokkeerd.  Er worden periodiek nieuwe registratiepogingen uitgevoerd voor het geval de gebruiker in de toekomst alsnog een licentie wordt verleend. |
| ENROLLMENT_SUCCEEDED | De registratie is geslaagd of de gebruiker is al geregistreerd.  In het geval van een geslaagde registratie wordt er vóór deze melding een melding voor beleidsvernieuwing verzonden.  Toegang tot bedrijfsgegevens moet worden toegestaan. |
| ENROLLMENT_FAILED | De registratie is mislukt.  Meer informatie vindt u in de logboeken van het apparaat.  De app moet in deze status geen toegang tot de bedrijfsgegevens verlenen, omdat eerder is vastgesteld dat de gebruiker een licentie heeft voor Intune.|
| WRONG_USER | Slechts één gebruiker per apparaat kan een app met de MAM-service registreren.  Als u wilt worden geregistreerd als een andere gebruiker, moet eerst de registratie van alle apps ongedaan worden gemaakt.  Anders moet deze app worden geregistreerd als de primaire gebruiker.  Deze controle wordt uitgevoerd nadat de licentie is gecontroleerd. De gebruiker moet dus worden geblokkeerd voor toegang tot de bedrijfsgegevens totdat de app is geregistreerd.|
| UNENROLLMENT_SUCCEEDED | De registratie is ongedaan gemaakt.|
| UNENROLLMENT_FAILED | Het ongedaan maken van de registratie is mislukt.  Meer informatie vindt u in de logboeken van het apparaat. |
| PENDING | De eerste registratiepoging voor de gebruiker wordt uitgevoerd.  De app kan de toegang tot de bedrijfsgegevens blokkeren totdat het resultaat van de registratie bekend is. Dit is echter geen vereiste. |
| COMPANY_PORTAL_REQUIRED | De gebruiker heeft een licentie voor Intune, maar de app kan pas worden geregistreerd nadat de bedrijfsportal-app is geïnstalleerd op het apparaat. De SDK voor de Intune-app probeert de toegang tot de app te blokkeren voor de opgegeven gebruiker en instrueert de gebruiker om de bedrijfsportal-app te installeren(zie hieronder voor meer informatie). |


### <a name="company-portal-requirement-prompt-override-optional"></a>Vereisteprompt voor de bedrijfsportal negeren (optioneel)

Als het resultaat `COMPANY_PORTAL_REQUIRED` wordt ontvangen, blokkeert de SDK het gebruik van activiteiten die gebruikmaken van de identiteit waarvoor de registratie is aangevraagd. In plaats daarvan zorgt de SDK ervoor dat er een prompt wordt weergegeven om de bedrijfsportal te downloaden. Als u dit gedrag in uw app wilt voorkomen, kunnen de activiteiten `MAMActivity.onMAMCompanyPortalRequired` implementeren.

Deze methode wordt aangeroepen voordat de SDK de standaardblokkerings-UI weergeeft. Als de app de identiteit van de activiteit wijzigt of de registratie ongedaan maakt van de gebruiker die registratiepoging heeft uitgevoerd, wordt de activiteit niet door de SDK geblokkeerd. In deze situatie is het aan de app om te voorkomen dat er bedrijfsgegevens worden gelekt.

### <a name="notifications"></a>Meldingen

Er is een nieuw type `MAMNotification` toegevoegd om de app te informeren dat het registratieverzoek is voltooid.  De `MAMEnrollmentNotification` worden ontvangen via de `MAMNotificationReceiver` interface zoals beschreven in de sectie [Registreren voor meldingen van de SDK](#register-for-notifications-from-the-sdk).

```java
public interface MAMEnrollmentNotification extends MAMUserNotification {
    MAMEnrollmentManager.Result getEnrollmentResult();
}

```

De methode `getEnrollmentResult()` retourneert het resultaat van het registratieverzoek.  Aangezien `MAMEnrollmentNotification` `MAMUserNotification` uitbreidt, is ook de identiteit van de gebruiker beschikbaar voor wie de registratiepoging is uitgevoerd. De app moet de `MAMNotificationReceiver`-interface implementeren om deze meldingen te ontvangen, zoals uiteengezet in de sectie [Registreren voor meldingen van de SDK](#Register-for-notifications-from-the-SDK).

De status van de geregistreerde account kan worden gewijzigd wanneer een registratiemelding wordt ontvangen, maar in bepaalde gevallen zal de status niet worden gewijzigd (bijvoorbeeld als de melding `AUTHORIZATION_NEEDED` wordt ontvangen na een meer informatief resultaat als `WRONG_USER`, het meer informatieve resultaat wordt gehandhaafd als de status van het account).


## <a name="protecting-backup-data"></a>Beveiligen van back-upgegevens

Vanaf Android Marshmallow (API 23) biedt Android apps twee manieren om een back-up van gegevens te maken. Elke optie is beschikbaar voor uw app en vereist andere stappen om ervoor te zorgen dat Intune-gegevensbeveiliging correct worden geïmplementeerd. U kunt de onderstaande tabel gebruiken voor een overzicht van de bijbehorende acties die zijn vereist voor een correct gegevensbeveiligingsgedrag.  In de [Android-API-handleiding](http://developer.android.com/guide/topics/data/backup.html) vindt u meer informatie over de back-upmethoden.

### <a name="auto-backup-for-apps"></a>Automatische back-ups voor apps

Android begon met het aanbieden van [automatische volledige back-ups](https://developer.android.com/guide/topics/data/autobackup.html) naar Google Drive for apps op Android Marshmallow-apparaten, ongeacht de doel-API van de app. Als u in uw AndroidManifest.xml `android:allowBackup` expliciet hebt ingesteld op **onwaar**, wordt uw app door Android nooit opgenomen in de wachtrij voor back-ups en blijven de bedrijfsgegevens in de app. In dit geval is er geen verdere actie nodig.

Het kenmerk `android:allowBackup` is echter standaard ingesteld op waar, zelfs als `android:allowBackup` niet in het manifestbestand is opgegeven. Dit betekent dat van alle app-gegevens automatisch een back-up in het Google Drive-account van de gebruiker wordt gemaakt. Deze standaardwerking vormt een **risico op het lekken van gegevens**. Daarom vereist de SDK de wijzigingen die hieronder worden beschreven om ervoor te zorgen dat gegevensbescherming wordt toegepast.  Het is belangrijk dat u de onderstaande richtlijnen voor het beveiligen van klantgegevens volgt als u uw app op Android Marshmallow-apparaten wilt uitvoeren.  

U kunt met Intune alle [functies voor automatische back-ups](https://developer.android.com/guide/topics/data/autobackup.html) gebruiken die door Android beschikbaar worden gesteld, inclusief de mogelijkheid om aangepaste regels in XML te definiëren, maar u moet de volgende stappen uitvoeren om uw gegevens te beveiligen:

1. Als uw app **geen** eigen aangepaste BackupAgent gebruikt, gebruikt u de standaard-MAMBackupAgent voor automatische volledige back-ups die aan het Intune-beleid voldoen. Als u dit doet, kunt u het `android:fullBackupOnly`-manifestkenmerk negeren, aangezien deze niet van toepassing is op onze back-upagent. Plaats het volgende in het app-manifest:

    ```xml
android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"
    ```

2. **[Optioneel]**  Als u een optionele aangepaste BackupAgent hebt geïmplementeerd, moet u ervoor zorgen dat MAMBackupAgent of MAMBackupAgentHelper gebruikt. Zie de volgende secties. Overweeg over te schakelen naar het gebruik van de **MAMDefaultFullBackupAgent** van Intune (zoals beschreven in stap 1). Hiermee kunt u eenvoudig back-ups maken op Android M en later.

3. Als u beslist welk type volledige back-up uw app moet ontvangen (niet gefilterd, gefilterd of geen), moet u het kenmerk `android:fullBackupContent` instellen op waar, onwaar of een XML-bron in uw app.

4. Vervolgens _**moet**_ alles wat u in `android:fullBackupContent` plaatst, kopiëren naar het manifest, naar een metagegevenscode met naam `com.microsoft.intune.mam.FullBackupContent`.

    **Voorbeeld 1**: als u wilt dat er volledige back-ups zonder uitsluitingen van uw app worden gemaakt, stelt u zowel het kenmerk `android:fullBackupContent` als de metagegevenscode `com.microsoft.intune.mam.FullBackupContent` in op **true (waar)**:

    ```xml
    android:fullBackupContent="true"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />  
    ```

    **Voorbeeld 2**: als u wilt dat uw app gebruikmaakt van de aangepaste BackupAgent en moet worden afgemeld voor volledige automatische back-ups die voldoen aan het Intune-beleid, moet u het kenmerk en de metagegevenscode instellen op **false (onwaar)**:

    ```xml
    android:fullBackupContent="false"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="false" />  
    ```

    **Voorbeeld 3**: als wilt dat er volledige back-ups van uw app worden gemaakt overeenkomstig uw aangepaste regels zoals gedefinieerd in een XML-bestand, stelt u het kenmerk en de metagegevenscode in op dezelfde XML-source:

    ```xml
    android:fullBackupContent="@xml/my_scheme"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```


### <a name="keyvalue-backup"></a>Key/Value-back-up

De optie [Key/Value-back-up](https://developer.android.com/guide/topics/data/keyvaluebackup.html) is beschikbaar voor alle API's 8+ en uploadt de app-gegevens naar de [Android Backup Service](https://developer.android.com/google/backup/index.html). De hoeveelheid gegevens per gebruiker van uw app is beperkt tot 5 MB. Als u Key/Value-back-up gebruikt, moet u een **BackupAgentHelper** of een **BackupAgent** gebruiken.

### <a name="backupagenthelper"></a>BackupAgentHelper

BackupAgentHelper is eenvoudiger te implementeren dan BackupAgent, zowel op het gebied van systeemeigen Android-functionaliteit als Intune MAM-integratie. Met BackupAgentHelper kan de ontwikkelaar volledige bestanden en gedeelde voorkeuren registreren bij respectievelijk een **FileBackupHelper** en **SharedPreferencesBackupHelper**, die vervolgens worden toegevoegd aan de BackupAgentHelper wanneer deze wordt gemaakt. Volg de onderstaande stappen om een BackupAgentHelper met Intune MAM te gebruiken:

1. Als u back-ups van meerdere identiteiten wilt maken met een BackupAgentHelper, volgt u de Android-richtlijn voor [het uitbreiden van BackupAgentHelper](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgentHelper).

2. Laat uw klasse de MAM-equivalent van BackupAgentHelper, FileBackupHelper en SharedPreferencesBackupHelper uitbreiden.

|Android-klasse | MAM-equivalent |
|--|--|
|BackupAgentHelper |MAMBackupAgentHelper |
|FileBackupHelper | MAMFileBackupHelper
|SharedPreferencesBackupHelper| MAMSharedPreferencesBackupHelper|

Als u deze richtlijnen volgt, kunt back-ups meerdere identiteiten maken en deze herstellen.

### <a name="backupagent"></a>BackupAgent

Met een BackupAgent kunt u veel explicieter aangeven van welke gegevens een back-up wordt gemaakt. Omdat de ontwikkelaar redelijk verantwoordelijk is voor de implementatie, zijn er meer stappen vereist om te zorgen voor de juiste mate van gegevensbeveiliging van Intune. Omdat het meeste werk naar u, de ontwikkelaar, wordt doorgeschoven, is de Intune-integratie iets bewerkelijker.

**MAM integreren:**

1. Lees de Android-handleiding [Key/Value Backup](https://developer.android.com/guide/topics/data/keyvaluebackup.html) en met name de sectie [Extending BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) aandachtig door om ervoor te zorgen dat uw implementatie van BackupAgent de Android-richtlijnen volgt.

2. Laat uw klasse `MAMBackupAgent` uitbreiden.

**Back-up maken van meerdere identiteiten:**

1. Voordat u een back-up start, controleert u of **de IT-beheerder u toestaat** een back-up van de gewenste bestanden of gegevensbuffers te maken in scenario's met meerdere identiteiten. U beschikt over de functie `isBackupAllowed` in `MAMFileProtectionManager` en `MAMDataProtectionManager` om dit te bepalen. Als er geen back-up van het bestand of de gegevensbuffer mag worden gemaakt, moet u deze te blijven opnemen in uw back-up.

2. Op een bepaald moment moet u tijdens de back-up, als u een back-up wilt maken van de identiteit voor de bestanden die u in stap 1 hebt gecontroleerd, `backupMAMFileIdentity(BackupDataOutput data, File … files)` aanroepen met de bestanden waaruit u gegevens wilt extraheren. Hierdoor worden automatisch nieuwe back-upentiteiten voor u gemaakt en naar de `BackupDataOutput` geschreven. Deze entiteiten worden automatisch gebruikt bij het herstellen.

**Meerdere identiteiten herstellen:**

De handleiding voor het maken van gegevensback-ups bevat een algemeen algoritme voor het herstellen van de gegevens van uw toepassing. Daarnaast bevat de sectie [Extending BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) een codevoorbeeld. Als u meerdere identiteiten wilt herstellen, moet u de algemene structuur in deze voorbeeldcode volgen en met name letten op het volgende:

1.  U moet een `while(data.readNextHeader())`-lus* gebruiken om door de back-upentiteiten te gaan.

2.  U moet `data.skipEntityData()`* aanroepen als `data.getKey()`* niet overeenkomt met de sleutel die u in `onBackup` hebt geschreven. Als deze stap niet wordt uitgevoerd, is het mogelijk dat uw herstelbewerkingen mislukken.

3.  Voorkom dat er tijdens het verbruik van back-entiteiten in de `while(data.readNextHeader())`-constructie* wordt geretourneerd, zodat de automatisch geschreven entiteiten niet verloren gaan.

* Waar `data` de lokale variabelenaam voor de **BackupDataInput** is die tijdens de herstelbewerking wordt doorgegeven naar uw app.

## <a name="multi-identity-optional"></a>Meerdere identiteiten (optioneel)

### <a name="overview"></a>Overzicht
De Intune App SDK past beleid standaard op de hele app toe. Meerdere identiteiten is een optionele beveiligingsfunctie voor Intune-apps die kan worden ingeschakeld zodat beleid per identiteitsniveau kan worden toegepast. Hiervoor wordt aanzienlijk meer deelname van een app vereist dan bij andere app-beveiligingsfuncties.

De app _moet_ de SDK laten weten wanneer de actieve identiteit wordt gewijzigd. De app wordt door de SDK geïnformeerd wanneer een identiteitswijziging nodig is. Zodra de gebruiker het apparaat of de app registreert, registreert de SDK deze identiteit en beschouwt de SDK deze identiteit als de primaire beheerde identiteit. Andere gebruikers in de app worden behandeld als niet-beheerd, met onbeperkte beleidsinstellingen.

> [!NOTE]
> Op dit moment wordt per apparaat slechts één met Intune beheerde identiteit ondersteund.

Een identiteit wordt gewoon als een tekenreeks gedefinieerd. Identiteiten zijn **hoofdlettergevoelig** en in geretourneerde identiteitsaanvragen, die waren gericht aan de SDK, wordt mogelijk niet hetzelfde gebruik van hoofd- en kleine letters toegepast als oorspronkelijk is gebruikt toen de identiteit werd ingesteld.


### <a name="enabling-multi-identity"></a>Meerdere identiteiten inschakelen

Alle apps worden standaard beschouwd als apps met één identiteit. U kunt aangeven dat een app met meerdere identiteiten kan werken door de volgende metagegevens in het bestand AndroidManifest.xml te plaatsen.

```xml
  <meta-data
    android:name="com.microsoft.intune.mam.MAMMultiIdentity"
    android:value="true" />
```

### <a name="setting-the-identity"></a>De identiteit instellen

Ontwikkelaars kunnen de identiteit van de app-gebruiker instellen op de volgende niveaus met aflopende prioriteit:

  1. Threadniveau
  2. Contextniveau (in het algemeen activiteit)
  3. Procesniveau

Een identiteit die is ingesteld op threadniveau, vervangt een identiteit die is ingesteld op contextniveau, die weer een identiteit vervangt die is ingesteld op procesniveau. Een identiteit die is ingesteld op een context, wordt alleen gebruikt in de juiste gekoppelde scenario's. Bestands-I/O-bewerkingen hebben bijvoorbeeld geen gekoppelde context. De volgende methoden in `MAMPolicyManager` kunnen worden gebruikt om de identiteit in te stellen en de eerder ingestelde identiteitswaarden op te halen.

```java
  public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

  public static String getUIPolicyIdentity(final Context context);

  public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

  public static String getProcessIdentity();

  public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

  public static String getCurrentThreadIdentity();

  /**
   * Get the currently applicable app policy. Same as
   * MAMComponents.get(AppPolicy.class). This method does
   * not take the context identity into account.
   */
  public static AppPolicy getPolicy();

  /**
   * Get the currently applicable app policy, taking the context
   * identity into account.
   */
  public static AppPolicy getPolicy(final Context context);


  public static AppPolicy getPolicyForIdentity(final String identity);

  public static boolean getIsIdentityManaged(final String identity);

  ```

>[!NOTE]
> U kunt de identiteit van de app wissen door deze op null in te stellen.
>
> De lege tekenreeks kan worden gebruikt als een identiteit waarvoor nooit app-beveiligingsbeleid geldt.

#### <a name="results"></a>Resultaten
Alle methoden die worden gebruikt om de identiteit in te stellen, rapporteren resultaatwaarden via `MAMIdentitySwitchResult`. Er zijn vier waarden die kunnen worden geretourneerd:

| Retourwaarde | Scenario |
|--|--|
| SUCCEEDED | De identiteit is gewijzigd. |
| NOT_ALLOWED | De identiteit kan niet worden gewijzigd. <br><br>Dit doet zich voor als wordt geprobeerd om over te schakelen naar een andere beheerde gebruiker die behoort tot dezelfde organisatie als de geregistreerde gebruiker. Dit doet zich ook voor als is geprobeerd de UI-identiteit (context) in te stellen wanneer er een andere identiteit op de huidige thread is ingesteld. |
| CANCELLED | De identiteitswijziging is geannuleerd door de gebruiker, in het algemeen door op de knop Terug te klikken bij een pincode-/verificatieprompt. |
| FAILED | De identiteitswijziging is mislukt vanwege een niet-opgegeven reden.|


Bij het instellen van een contextidentiteit wordt het resultaat asynchroon gerapporteerd. Als de context een activiteit is, weet de SDK pas of de identiteitswijziging is geslaagd nadat de voorwaardelijke start is uitgevoerd, waarvoor de gebruiker mogelijk een pincode of de volledige bedrijfsreferenties moet invoeren. Van de app wordt verwacht dat deze een `MAMSetUIIdentityCallback` implementeert. U kunt een null voor deze parameter doorgeven om dit resultaat te bereiken.

```java
    public interface MAMSetUIIdentityCallback {
        void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
  }
```

U kunt de identiteit van een activiteit ook rechtstreeks instellen via een methode in `MAMActivity` in plaats van `MAMPolicyManager.setUIPolicyIdentity` aan te roepen. Gebruik de volgende methode om dit te doen:

```java
     public final void switchMAMIdentity(final String newIdentity);
```

U kunt ook een methode in `MAMActivity` als u wilt dat de app op de hoogte wordt gebracht van het resultaat van de pogingen om de identiteit van die activiteit te wijzigen.

``` java
    public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);
```

>[!NOTE]
> Bij het overschakelen naar een andere identiteit moet de activiteit mogelijk opnieuw worden gemaakt. In dit geval wordt de `onSwitchMAMIdentityComplete`-callback geleverd aan het nieuwe exemplaar van de activiteit.


### <a name="implicit-identity-changes"></a>Impliciete identiteitswijzigingen

Naast de mogelijkheid van de app om de identiteit in te stellen, kan de identiteit van een thread of context worden gewijzigd op basis van binnenkomende gegevens vanuit een andere app met Intune-functionaliteit waarop app-beveiligingsbeleid is toegepast.

#### <a name="examples"></a>Voorbeelden

  1. Als een activiteit wordt gestart vanuit een `Intent` die door een andere MAM-app is verzonden, wordt de identiteit van de activiteit ingesteld op basis van de geldige identiteit in de andere app op het moment dat de `Intent` werd verzonden.

  2.  Voor services wordt de threadidentiteit op ongeveer dezelfde manier ingesteld als voor de duur van een `onStart`- of `onBind`-aanroep. Aanroepen naar de `Binder` die is geretourneerd door `onBind`, stellen ook tijdelijk de threadidentiteit in.

  3. Aanroepen naar een `ContentProvider` stellen op dezelfde manier de threadidentiteit voor hun duur in.


  Bovendien kan de gebruikersinteractie met een activiteit een impliciete identiteitswisseling veroorzaken.

  **Voorbeeld:**als een gebruiker tijdens `Resume` een autorisatieprompt annuleert, resulteert dit in een impliciete overgang naar een lege identiteit.

  De app wordt de mogelijkheid geboden om op de hoogte te worden gebracht van deze wijzigingen en ze zo nodig te verbieden. `MAMService` en `MAMContentProvider` maken de volgende methode beschikbaar die door subklassen kan worden overschreven:

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
  ```

  In de `MAMActivity`-klasse is er een extra parameter aanwezig in de methode:

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
  ```

  * De `AppIdentitySwitchReason` registreert de bron van de impliciete wisseling en kan de waarden `CREATE`, `RESUME_CANCELLED` en `NEW_INTENT` accepteren.  De reden `RESUME_CANCELLED` wordt gebruikt wanneer het voortzetten van de activiteit ertoe leidt dat de gebruikersinterface voor een pincode, verificatie of andere naleving wordt weergegeven en de gebruiker die gebruikersinterface probeert te annuleren, meestal door de knop Terug te gebruiken.


  * De `AppIdentitySwitchResultCallback` ziet er als volgt uit:

    ```java
    public interface AppIdentitySwitchResultCallback {
        /**
         * @param result
         *            whether the identity switch can proceed.
         */
        void reportIdentitySwitchResult(AppIdentitySwitchResult result);
    }
    ```

    Waarbij ```AppIdentitySwitchResult``` SUCCESS of FAILURE is.

De methode `onMAMIdentitySwitchRequired` wordt aangeroepen voor alle impliciete identiteitswijzigingen behalve de wijzigingen die zijn aangebracht via een Binder die is geretourneerd door `MAMService.onMAMBind`. Met de standaardimplementaties van `onMAMIdentitySwitchRequired` wordt onmiddellijk het volgende aangeroepen:

*  `reportIdentitySwitchResult(FAILURE)` wanneer de reden RESUME_CANCELLED is.

*  `reportIdentitySwitchResult(SUCCESS)` in alle andere gevallen.

  Het is niet waarschijnlijk dat de meeste apps een identiteitswisseling op een andere manier moeten blokkeren of vertragen, maar als dit voor een app toch nodig is, zijn de volgende punten van belang:

  * Als het overschakelen naar een andere identiteit wordt geblokkeerd, is het resultaat hetzelfde als wanneer de `Receive`-instellingen voor delen de gegevensinvoer verbieden.

  * Als een service wordt uitgevoerd op de hoofdthread, **moet** `reportIdentitySwitchResult` synchroon worden aangeroepen, anders loopt de UI-thread vast.

  * Voor het maken van **Activiteit** wordt `onMAMIdentitySwitchRequired` aangeroepen vóór `onMAMCreate`. Als de app UI moet weergeven om te bepalen of de identiteitswisseling is toegestaan, moet die UI worden weergegeven met een *andere* activiteit.

  * Wanneer in een **activiteit** een overgang naar de lege identiteit wordt aangevraagd met een reden die gelijk is aan RESUME_CANCELLED, moet de app de voortgezette activiteit wijzigen om gegevens consistent met die identiteitswisseling weer te geven.  Als dit niet mogelijk is, moet de app de overschakeling weigeren en wordt de gebruiker opnieuw gevraagd te voldoen aan het beleid voor de identiteit die wordt voortgezet (bijvoorbeeld doordat het invoerscherm voor de pincode van app wordt weergegeven).

    > [!NOTE]
    > Een app met meerdere identiteiten ontvangt altijd inkomende gegevens van beheerde en onbeheerde apps. Het is de verantwoordelijkheid van de app om gegevens van beheerde identiteiten op een beheerde manier te behandelen.

  Als een aangevraagde identiteit wordt beheerd (gebruik `MAMPolicyManager.getIsIdentityManaged` om dit te controleren), maar de app dat account niet kan gebruiken (bijvoorbeeld omdat accounts, zoals e-mailaccounts, eerst in de app moeten worden ingesteld), moet de identiteitswisseling worden geweigerd.



  ### <a name="file-protection"></a>Bestandsbeveiliging

  Op het moment dat een bestand wordt gemaakt, wordt er op basis van een thread- en procesidentiteit een identiteit aan het bestand gekoppeld. Deze identiteit wordt gebruikt voor zowel bestandsversleuteling als selectief wissen. Alleen bestanden waarvan de identiteit word beheerd en een beleid heeft dat versleuteling vereist, worden versleuteld. De standaard-SDK-actie voor het selectief wissen van functies wist alleen bestanden die zijn gekoppeld aan de beheerde identiteit waarvoor wissen is aangevraagd. De app kan de identiteit van een bestand opvragen of wijzigen met de klasse `MAMFileProtectionManager`.

  ```java
    public final class MAMFileProtectionManager {

        /**
         * Protect a file. This will synchronously trigger whatever protection is required for the file, and will tag the file for
         * future protection changes.
         *
         * @param identity
         *            Identity to set.
         * @param file
         *            File to protect.
         * @throws IOException
         *             If the file cannot be changed.
         */
        public static void protect(final File file, final String identity) throws IOException;

        /**
         * Get the protection info on a file.
         *
         * @param file
         *            File or directory to get information on.
         * @return File protection info, or null if there is no protection info.
         * @throws IOException
         *             If the file cannot be read or opened.
         */
        public static MAMFileProtectionInfo getProtectionInfo(final File file) throws IOException;

        /**
         * Get the protection info on a file.
         *
         * @param file
         *            File to get information on.
         * @return File protection info, or null if there is no protection info.
         * @throws IOException
         *             If the file cannot be read or opened.
         */
        public static MAMFileProtectionInfo getProtectionInfo(final ParcelFileDescriptor file) throws IOException;

    }

    public interface MAMFileProtectionInfo {
        String getIdentity();
    }

  ```

Het labelen van de bestandsidentiteit is gevoelig voor de offlinemodus. U moet rekening houden met de volgende punten:

  * Als de bedrijfsportal niet is geïnstalleerd, is taggen van bestandsidentiteit niet mogelijk.

  * Als de bedrijfsportal is geïnstalleerd maar de app geen Intune MAM-beleid heeft, is niet mogelijk om bestanden op een betrouwbare manier worden getagd met identiteitslabels.

  * Wanneer het taggen van bestandsidentiteit beschikbaar komt, worden alle eerder gemaakte bestanden als persoonlijk/onbeheerd behandeld (behorend bij de identiteit met een lege tekenreeks), tenzij de app eerder is geïnstalleerd als een beheerde app met één identiteit. In dat geval wordt deze behandeld als behorend tot de geregistreerde gebruiker.

### <a name="directory-protection"></a>Mapbeveiliging

Mappen kunnen worden beveiligd met dezelfde `protect`-methode als voor de beveiliging van bestanden. Houd er rekening mee dat de mapbeveiliging recursief wordt toegepast op alle bestanden en submappen in de map en wordt toegepast op nieuwe bestanden die in de map worden gemaakt. Omdat mapbeveiliging recursief wordt toegepast, kan het even duren voordat de aanroep `protect` is voltooid voor grote mappen. Om die reden is het mogelijk dat apps die beveiliging toepassen op een map met een groot aantal bestanden, `protect` asynchroon willen uitvoeren op een thread op de achtergrond.

### <a name="data-protection"></a>Gegevensbescherming

Het is niet mogelijk om een bestand te taggen als behorend bij meerdere identiteiten. Wanneer voor apps gegevens moeten worden opgeslagen die behoren tot verschillende gebruikers in hetzelfde bestand, kan dit handmatig worden gedaan met de functies van `MAMDataProtectionManager`. De app kan dan gegevens versleutelen en deze koppelen aan een bepaalde gebruiker. De versleutelde gegevens zijn geschikt voor het opslaan naar schijf in een bestand. U kunt de gegevens die zijn gekoppeld aan de identiteit opvragen en de gegevens kunnen dan later worden ontsleuteld.

Apps die gebruikmaken van `MAMDataProtectionManager` moeten een ontvanger implementeren voor de `MANAGEMENT_REMOVED`-melding. Nadat deze melding is voltooid, kunnen de buffers die via deze klasse zijn beveiligd, niet meer worden gelezen als bestandsversleuteling was ingeschakeld op het moment dat de buffers werden beveiligd. Een app kan deze situatie oplossen door tijdens deze melding MAMDataProtectionManager.unprotect aan te roepen voor alle buffers. U kunt ook zonder problemen de beveiliging aanroepen tijdens deze melding als u de identiteitsgegevens wilt behouden. De versleuteling is gegarandeerd uitgeschakeld tijdens de melding.

```java

public final class MAMDataProtectionManager {
    /**
     * Protect a stream. This will return a stream containing the protected
     * input.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect, read sequentially. This function
     *            will change the position of the stream but may not have
     *            read the entire stream by the time it returns. The
     *            returned stream will wrap this one. Calls to read on the
     *            returned stream may cause further reads on the original
     *            input stream. Callers should not expect to read directly
     *            from the input stream after passing it to this method.
     *            Calling close on the returned stream will close this one.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static InputStream protect(final InputStream input, final String identity);

    /**
     * Protect a byte array. This will return protected bytes.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static byte[] protect(final byte[] input, final String identity) throws IOException;

    /**
     * Unprotect a stream. This will return a stream containing the
     * unprotected input.
     *
     * @param input
     *            Input data to protect, read sequentially.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static InputStream unprotect(final InputStream input) throws IOException;

    /**
     * Unprotect a byte array. This will return unprotected bytes.
     *
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static byte[] unprotect(final byte[] input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input stream to get information on. Either this input
     *            stream must have been returned by a previous call to
     *            protect OR input.markSupported() must return true.
     *            Otherwise it will be impossible to get protection info
     *            without advancing the stream position. The stream must be
     *            positioned at the beginning of the protected data.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final InputStream input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input bytes to get information on. These must be bytes
     *            returned by a previous call to protect() or a copy of
     *            such bytes.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final byte[] input) throws IOException;
}

```

### <a name="content-providers"></a>Inhoudsproviders

Als de app ander bedrijfsgegevens biedt dan een **ParcelFileDescriptor** via een **ContentProvider**, moet de app de methode `isProvideContentAllowed(String)` in `MAMContentProvider` aanroepen om de UPN (user principal name) van de identiteit van de eigenaar door te geven voor de inhoud. Als deze functie onwaar retourneert, kan de inhoud *niet* worden geretourneerd aan de oproepende functie. Bestandsdescriptors die zijn geretourneerd via een inhoudsprovider, worden automatisch verwerkt op basis van de bestandsidentiteit.

### <a name="selective-wipe"></a>Selectief wissen

Als een app wordt geregistreerd voor de `WIPE_USER_DATA`-melding, profiteert deze niet van het voordeel van het standaardgedrag van de SDK voor selectief wissen. Voor apps die met meerdere identiteiten kunnen werken, kan dit verlies belangrijker zijn omdat met de standaard-MAM-actie voor selectief wissen alleen bestanden worden gewist waarvan de identiteit het doel is van een wisbewerking.

Als een app die met meerdere identiteiten kan werken, de standaard-MAM-functie voor selectief wissen wil uitvoeren _**en**_ eigen wisacties wil uitvoeren, moet de app worden geregistreerd voor `WIPE_USER_AUXILIARY_DATA`-meldingen. Deze melding wordt direct door de SDK verzonden, nog voordat u de standaard-MAM-actie voor selectief wissen wordt uitgevoerd. Een app mag nooit worden geregistreerd voor zowel WIPE_USER_DATA als WIPE_USER_AUXILIARY_DATA.


## <a name="style-customization-optional"></a>Stijlaanpassing (optioneel)

Weergaven die worden gegenereerd door de MAM SDK kunnen visueel worden aangepast aan de app waarin de MAM SDK is geïntegreerd. U kunt de primaire, secundaire en achtergrondkleuren en de grootte van het app-logo aanpassen. Deze stijlaanpassing is optioneel. Als er geen aangepaste stijl is geconfigureerd, worden de standaardinstellingen gebruikt.


### <a name="how-to-customize"></a>Aanpassingen maken
Als de stijlwijzigingen moeten worden toegepast op de Intune MAM-weergavenviews, moet u eerst een XML-bestand met stijloverschrijvingen maken. Dit bestand moet in de map /res/xml van uw app worden geplaatst. U kunt het bestand elke gewenste naam geven. Hieronder volgt een voorbeeld van de indeling die voor dit bestand moet worden gevolgd.

```xml
<?xml version="1.0" encoding="utf-8"?>
<styleOverrides>
    <item
        name="foreground_color"
        resource="@color/red"/>
    <item
        name="accent_color"
        resource="@color/blue"/>
    <item
        name="background_color"
        resource="@color/green"/>
    <item
        name="logo_image"
        resource="@drawable/app_logo"/>
</styleOverrides>

```

U moet de bestaande resources in uw app opnieuw gebruiken. U moet bijvoorbeeld de kleur groen in het bestand colors.xml file definiëren en een verwijzing aan het bestand toevoegen. U kunt niet de hexadecimale kleurencode #0000ff gebruiken. De maximale grootte voor het app-logo is 110 dip (dp). U kunt desgewenst een kleinere logoafbeelding gebruiken, maar de maximale grootte resulteert in de best uitziende resultaten. Als u de limiet van 110 dip overschrijdt, wordt de afbeelding verkleind, waardoor deze mogelijk onscherp wordt weergegeven.

Hieronder volgt een compleet overzicht van de toegestane stijlkenmerken, de UI-elementen die ze besturen, hun itemnamen van de XML-kenmerken en het type resource dat voor elk kenmerk wordt verwacht.

|Stijlkenmerk | UI-elementen die worden beïnvloed | Itemnaam van het kenmerk | Verwacht resourcetype |
| -- | -- | -- | -- |
| Achtergrondkleur | Achtergrondkleur van het scherm voor het invoeren van de pincode <Br>Opvulkleur van het vak voor de pincode | background_color | Kleur |
| Voorgrondkleur | Kleur van de voorgrondtekst <br> Kaderrand van het pincodevak met standaardstatus <br> Tekens (inclusief verborgen tekens) in het pincodevak wanneer de gebruiker een pincode invoert| foreground_color | Kleur|
| Accentkleur | Kaderrand van het gemarkeerde pincodevak <br> Hyperlinks |accent_color | Kleur |
| App-logo | Grote pictogrammen die worden weergegeven in het pincodescherm van de Intune-app | logo_image | Tekenbaar |

## <a name="limitations"></a>Beperkingen

### <a name="file-size-limitations"></a>Beperkingen van de bestandsgrootte

Voor grote codebasissen die worden uitgevoerd zonder [ProGuard](http://proguard.sourceforge.net/), vormen de beperkingen van de bestandsindeling van het uitvoerbare Dalvik-bestand een probleem. Met name de volgende beperkingen kunnen van toepassing zijn:

1.  De limiet van 65K op velden.
2.  De limiet van 65K op methoden.



### <a name="policy-enforcement-limitations"></a>Beperkingen op het afdwingen van beleid

* **Schermopname**: de SDK kan geen nieuwe instelwaarde voor schermopnames afdwingen bij activiteiten die Activity.onCreate al hebben doorlopen. Dit kan resulteren in een tijdsperiode waarin de app is geconfigureerd voor het uitschakelen van schermafbeeldingen maar waarin er nog steeds schermafbeeldingen kunnen worden gemaakt.

* **Gebruik van inhoudsoplossers**: het Intune-beleid voor overdracht of ontvangst kan het gebruik van een inhoudsoplosser geheel of gedeeltelijk blokkeren voor toegang tot de inhoudsprovider in een andere app. Dit zorgt ervoor dat ContentResolver-methoden null retourneren of een foutwaarde afgeven (bijvoorbeeld: `openOutputStream` genereert `FileNotFoundException` indien geblokkeerd). De app kan bepalen of het mislukte schrijven van gegevens via een inhoudsoplosser is veroorzaakt door beleid (of zou worden veroorzaakt door beleid) door de volgende oproep te plaatsen:

    ```java
    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI);
    ```

### <a name="exported-services"></a>Geëxporteerde services

 Het bestand AndroidManifest.xml, dat deel uitmaakt van de SDK voor de Intune-app, bevat **MAMNotificationReceiverService**, wat een geëxporteerde service moet zijn om toe te staan dat de bedrijfsportal meldingen naar een geoptimaliseerde app verzendt. De service controleert de oproepende functie om ervoor te zorgen dat alleen de Bedrijfsportal meldingen mag verzenden.



## <a name="expectations-of-the-sdk-consumer"></a>Verwachtingen van de SDK-consument

De Intune SDK onderhoudt het contract geleverd door de Android-API, hoewel er vaker foutmeldingen als gevolg van beleidsafdwinging kunnen worden geactiveerd. Deze aanbevolen Android-procedures verminderen de kans op fouten:

* Android SDK-functies die null kunnen retourneren, hebben nu een grotere kans om null te zijn.  Om problemen tot een minimum te beperken, zorgt u ervoor dat null-controles op de juiste plaatsen worden uitgevoerd.

* Functies die kunnen worden gecontroleerd, moeten worden gecontroleerd via hun MAM-vervangings-API's.

* Eventuele afgeleide functies moeten oproepen uitvoeren via de versies van hun bovenliggende klasse.

* Vermijd het niet-eenduidige gebruik van API's. Bijvoorbeeld: wanneer u `Activity.startActivityForResult` zonder te controleren of de requestCode vreemd gedrag kan veroorzaken.

## <a name="recommended-android-best-practices"></a>Aanbevolen procedures voor Android

* Waar mogelijk, moeten alle bibliotheekprojecten hetzelfde android:package delen. Dit zal niet sporadisch mislukken tijdens de uitvoeringstijd. Het is puur een probleem dat zich voordoet tijdens het opbouwen. In nieuwere versies van de SDK voor de Intune-app, zal de redundantie deels worden verwijderd.

* Gebruik de nieuwste hulpprogramma's van de Android SDK-build.

* Verwijder alle overbodige en ongebruikte bibliotheken (bijvoorbeeld android.support.v4).
