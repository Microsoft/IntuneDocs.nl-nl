---
title: Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor Android | Microsoft Docs
description: Met de Microsoft Intune App SDK voor Android kunt u Intune Mobile App Management (MAM) opnemen in uw Android-app.
keywords: SDK
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 905be6a926dc5bab8e9b1016ba82751ee47313e5
ms.openlocfilehash: 178fbaeb1d3235a81cb4da49b7a955f6999c49a2
ms.lasthandoff: 02/18/2017


---


# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor Android

> [!NOTE]
> U kunt desgewenst eerst [Overzicht van de Intune App SDK](intune-app-sdk.md) lezen voor meer informatie over de huidige functies en hoe u de integratie voor elk ondersteund platform voorbereidt.

Met de Microsoft Intune App SDK voor Android kunt u Intune Mobile App Management (MAM) opnemen in uw Android-app. Een MAM-app is geïntegreerd met de Intune App SDK. Hiermee kunnen IT-beheerders beleid implementeren voor uw mobiele app wanneer die actief door Intune wordt beheerd.

## <a name="whats-in-the-sdk"></a>Inhoud van de SDK

De Intune App SDK voor Android is een standaard Android-bibliotheek zonder externe afhankelijkheden. De SDK bestaat uit:  

* **Microsoft.Intune.MAM.SDK.jar**: de interfaces die nodig zijn om MAM en interoperabiliteit in te schakelen met de Intune-bedrijfsportal-app. Apps moeten dit opgeven als verwijzing naar de Android-bibliotheek.

* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: de interfaces die nodig zijn om MAM in te schakelen in apps die gebruikmaken van de Android v4-ondersteuningsbibliotheek. Apps die deze ondersteuning nodig hebben, moeten rechtstreeks verwijzen naar het JAR-bestand.

* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: de interfaces die nodig zijn om MAM in te schakelen in apps die gebruikmaken van de Android v7-ondersteuningsbibliotheek. Apps die deze ondersteuning nodig hebben, moeten rechtstreeks verwijzen naar het JAR-bestand.

* **De resourcedirectory**: de resources (zoals tekenreeksen) waarop de SDK is gebaseerd.

* **Microsoft.Intune.MAM.SDK.aar**: de SDK-onderdelen, met uitzondering van de JAR-bestanden voor Support.V4 en Support.V7. Dit bestand kan worden gebruikt in plaats van de afzonderlijke onderdelen, als uw build-systeem AAR-bestanden ondersteunt.

* **AndroidManifest.xml**: de extra invoerpunten en de bibliotheekvereisten.

* **THIRDPARTYNOTICES.TXT**: een kennisgeving waarin code van derden en/of OSS-code die in uw app wordt gecompileerd aan de rechthebbenden wordt toegeschreven.

## <a name="requirements"></a>Vereisten

De Intune App SDK is een gecompileerd Android-project. Als gevolg hiervan wordt de SDK grotendeels niet beïnvloed door de versie van Android die de app gebruikt voor de minimumversie of doel-API-versies. De SDK biedt ondersteuning voor Android-API 14 (Android 4.0+) tot en met Android-API 24.

De Intune App SDK voor Android is afhankelijk van de aanwezigheid van de [bedrijfsportal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)-app op het apparaat voor het inschakelen van MAM-beleid. Voor MAM zonder apparaatinschrijving hoeft de gebruiker het apparaat *niet* te registreren via de bedrijfsportal-app.


## <a name="how-the-intune-app-sdk-works"></a>De werking van de Intune App SDK

###<a name="entry-points"></a>Invoerpunten

De Intune App SDK vereist wijzigingen in de broncode van een app om Intune-beleid voor het beheer van apps in te schakelen. Dit wordt gedaan door de Android-basisklassen te vervangen door gelijkwaardige Intune-basisklassen, waarvan de namen het voorvoegsel `MAM` hebben. De SDK-klassen begeven zich tussen de Android-basisklasse en de eigen afgeleide app-versie van die klasse. Als we een activiteit als voorbeeld gebruiken, krijgt u uiteindelijk een overnamehiërarchie die er als volgt uitziet: `Activity` > `MAMActivity` > `AppSpecificActivity`.

Wanneer `AppSpecificActivity` bijvoorbeeld een interactie aangaat met het bovenliggende item (bijvoorbeeld door `super.onCreate()` aan te roepen), is `MAMActivity` is de superklasse.

Android-apps hebben gewoonlijk één modus en hebben toegang tot het systeem via hun [context](https://developer.android.com/reference/android/content/Context.html)-object. Apps waarin de Intune App SDK is opgenomen, hebben daarentegen twee modi. Deze apps houden toegang tot het systeem via het `Context`-object. Afhankelijk van de algemene `Activity` die wordt gebruikt, wordt het `Context`-object verstrekt door Android of zal het op intelligente wijze multiplexen tussen een beperkte weergave van het systeem en de `Context` die wordt verstrekt door Android.

Wanneer een Android-[invoerpunt](https://developer.android.com/guide/components/fundamentals.html) is overschreven door het MAM-equivalent, moet de MAM-versie van de levenscyclus van het invoerpunt worden gebruikt (met uitzondering van de klasse `MAMApplication`).

Wanneer een activiteit wordt afgeleid van `MAMActivity`, moet niet `onCreate` worden overschreven en niet `super.onCreate` worden aangeroepen, maar moet `Activity` `onMAMCreate` overschrijven en `super.onMAMCreate` aanroepen. Zodoende kan Intune (onder andere) de start van de `Activity` in bepaalde gevallen beperken.


###<a name="sdk-permissions"></a>SDK-machtigingen

De Intune App SDK vereist drie [Android-systeemmachtigingen](https://developer.android.com/guide/topics/security/permissions.html) voor apps waarin de SDK wordt geïntegreerd:

* `android.permission.GET_ACCOUNTS` (aangevraagd tijdens runtime indien nodig)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

Deze machtigingen zijn vereist voor Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/)) om brokered verificatie uit te voeren. Als deze machtigingen niet worden toegekend aan de app of worden ingetrokken door de gebruiker, worden verificatiestromen waarvoor de broker (de bedrijfsportal-app) is vereist, uitgeschakeld.


###<a name="company-portal-app"></a>Bedrijfsportal-app

Waarom is de bedrijfsportal-app vereist? Wanneer de bedrijfsportal-app op het apparaat is geïnstalleerd en een restrictiebeleid voor toepassingen is opgehaald vanuit de Intune-service, worden de SDK-invoerpunten asynchroon geïnitialiseerd. Er hoeft alleen te worden geïnitialiseerd wanneer het proces aanvankelijk door Android wordt gemaakt. Tijdens de initialisatie wordt er verbinding met de bedrijfsportal-app gemaakt en wordt er beleid van de app opgehaald.  

> [!NOTE]
> Wanneer de bedrijfsportal-app niet op het apparaat aanwezig is, wordt de werking van de app waarin Intune is ingeschakeld niet gewijzigd en fungeert de app als een normale app.


## <a name="how-to-integrate-with-the-intune-app-sdk"></a>Integratie met de Intune App SDK

Zoals eerder beschreven, vereist de SDK wijzigingen in de broncode van een app om beleid voor app-beheer te kunnen inschakelen. Hieronder worden de stappen uitgelegd voor het inschakelen van MAM in uw app:

### <a name="replace-classes-methods-and-activities-with-their-mam-equivalent-required"></a>Klassen, methoden en activiteiten vervangen door hun MAM-equivalent (vereist)

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
| enroid.app.PendingIntent | MAMPendingIntent* |
| enroid.app.Service | MAMService |
| enroid.app.TabActivity | MAMTabActivity |
| enroid.app.TaskStackBuilder | MAMTaskStackBuilder |
| enroid.app.backup.BackupAgent | MAMBackupAgent |
| enroid.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| enroid.app.backup.FileBackupHelper | MAMFileBackupHelper |
| enroid.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| enroid.content.BroadcastReceiver | MAMBroadcastReceiver |
| enroid.content.ContentProvider | MAMContentProvider |
| enroid.os.Binder | AMBinder (alleen vereist als de Binder niet is gegenereerd op basis van een AIDL-interface (Android Interface Definition Language) |
| enroid.provider.DocumentsProvider | MAMDocumentsProvider |
| enroid.preference.PreferenceActivity | MAMPreferenceActivity |


**Microsoft.Intune.MAM.SDK.Suppof eent.v4.jar**:

| Android-klasse Intune-MAM | Intune App SDK-vervanging |
|--|--|
| enroid.suppof eent.v4.app.DialogFragment | MAMDialogFragment
| enroid.suppof eent.v4.app.FragmentActivity | MAMFragmentActivity
| enroid.suppof eent.v4.app.Fragment | MAMFragment
| enroid.suppof eent.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| enroid.suppof eent.v4.content.FileProvider | MAMFileProvider

**Microsoft.Intune.MAM.SDK.Suppof eent.v7.jar**:

|Android-klasse | Intune App SDK-vervanging |
|--|--|
|enroid.suppof eent.v7.app.ActionBarActivity | MAMActionBarActivity |

>[!NOTE]
>Vergeet niet dat wanneer een Android-[invoerpunt](https://developer.android.com/guide/components/fundamentals.html) is overschreven door het MAM-equivalent, de MAM-versie van de levenscyclus van het invoerpunt moet worden gebruikt (met uitzondering van de klasse `MAMApplication`).
>
>Wanneer een activiteit wordt afgeleid van `MAMActivity`, moet niet `onCreate` worden overschreven en niet `super.onCreate` worden aangeroepen, maar moet `Activity` `onMAMCreate` overschrijven en `super.onMAMCreate` aanroepen. Zodoende kan Intune (onder andere) de start van de `Activity` in bepaalde gevallen beperken.

#### <a name="pendingintent-classes-and-renamed-methods"></a>PendingIntents-klassen en methoden met een gewijzigde naam

Nadat u hebt afgeleid van een van de MAM-invoerpunten, kunt u `Context` net als anders op een veilige manier gebruiken, bijvoorbeeld om `Activity`-klassen te starten en `PackageManager` te gebruiken.  

`PendingIntent`-klassen vormen een uitzondering op deze regel. Wanneer u dergelijke klassen aanroept, moet u de naam van de klasse wijzigen. U moet bijvoorbeeld in plaats van `PendingIntent.get*` de methode `MAMPendingIntent.get*` gebruiken. Vervolgens kunt u gewoon de resulterende `PendingIntent` gebruiken.

In sommige gevallen is een methode die in de Android-klasse beschikbaar is, in de vervangende MAM-klasse als definitief gemarkeerd. De vervangende MAM klasse biedt in dit geval een gelijknamige methode (meestal voorafgegaan door `MAM`) die in plaats daarvan moet worden overschreven. In plaats van het overschrijven van `ContentProvider.query`onderdrukt u bijvoorbeeld `MAMContentProvider.queryMAM`. De Java-compiler moet de laatste beperkingen afdwingen om het onbedoeld onderdrukken van de oorspronkelijke methode in plaats van de MAM-equivalent te voorkomen.

###<a name="enable-features-that-require-app-participation"></a>Functies inschakelen waarvoor app-deelname is vereist

Er zijn enkele beleidsregels die de SDK niet zelf kan implementeren. De app kan het eigen gedrag voor deze functies bepalen door gebruik te maken van de verschillende API's in de volgende `AppPolicy`-interface.

```
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * <strong>This function is now deprecated. Please use {@link #getIsSaveToLocationAllowed(SaveLocation, String)} instead</strong>
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
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between the AAD username and the cloud service username does not exist or the username is not known.
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

### <a name="enable-it-control-over-app-saving-behavior"></a>IT-beheer van het opslaggedrag van de app inschakelen

Veel apps implementeren functies waarmee de gebruiker bestanden lokaal of naar een cloudopslagservice kan opslaan. Met de Intune App SDK kunnen IT-beheerders beveiliging instellen tegen het lekken van gegevens door naar eigen goeddunken beleidsbeperkingen binnen hun organisatie toe te passen.  Een van de beleidsregels die door IT-beheerders kan worden bepaald, is of de gebruiker kan opslaan naar een 'persoonlijke', niet-beheerde gegevensopslag. Dit omvat het opslaan naar een lokale locatie, een SD-kaart of een back-upservice van derden.

Voor het inschakelen van de functie is app-deelname vereist. Als uw app de mogelijkheid biedt om rechtstreeks vanuit de app naar persoonlijke of cloudlocaties op te slaan, moet u deze functie implementeren om ervoor te zorgen dat de IT-beheerder kan bepalen of opslaan naar een locatie al of niet is toegestaan.   

De app kan de volgende oproep verzenden om te bepalen of het beleid wordt afgedwongen: Deze aanroep laat de app weten of het huidige beleid van de Intune-beheerder toestaat dat er wordt opgeslagen naar een persoonlijk archief. De app kan het beleid vervolgens afdwingen omdat deze weet of er via de app een persoonlijke gegevensopslag voor de eindgebruiker beschikbaar is.

```
MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();
```

> [!NOTE]
> `MAMComponents.get(AppPolicy.class)` retourneert altijd een niet-null-app-beleid, zelfs als voor het apparaat of de app geen Intune-beheerbeleid van toepassing is.

### <a name="let-the-app-detect-if-a-pin-policy-is-required"></a>De app laten detecteren of een pincodebeleid is vereist

Mogelijk wilt u bepaalde functionaliteit van enkele Intune-app-beperkingen uitschakelen om te voorkomen dat functionaliteit in de Intune App SDK wordt gedupliceerd. Als de app bijvoorbeeld een eigen gebruikerservaring voor pincodes heeft, wilt u dit beleid mogelijk uitschakelen als de SDK is geconfigureerd om te vereisen dat de gebruiker een pincode invoert.

Als u wilt bepalen of er Intune-pincodebeleid is geconfigureerd om bij het starten een app-pincode te vereisen, kan de app de volgende aanroep verzenden:

```
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

### <a name="register-for-notifications-from-the-sdk"></a>Registreren voor meldingen van de SDK  

Met de Intune App SDK kan uw app het gedrag van bepaalde beleidsregels, zoals selectief wissen, beheren wanneer de IT-beheerder ze implementeert. Als een IT-beheerder dergelijk beleid implementeert, wordt met de Intune-service een melding naar de SDK verzonden.

Uw moet worden geregistreerd voor meldingen van de SDK door een `MAMNotificationReceiver` -klasse te maken en deze te registreren met `MAMNotificationReceiverRegistry`. Dit wordt gedaan door zoals in dit voorbeeld de ontvanger en het gewenste type melding op te geven in `App.onCreate`:

```
@Override
public void onCreate() {
    super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class)
.registerReceiver(
                new ToastNotificationReceiver(),
MAMNotificationType.WIPE_USER_DATA);
    }
```

`MAMNotificationReceiver` ontvangt gewoon meldingen vanuit de Intune-service. Bepaalde meldingen worden rechtstreeks door de SDK verwerkt. Voor andere meldingen is ook de app nodig.

Een app *moet* Waar of Onwaar retourneren vanaf een melding. De app moet altijd true (waar) retourneren, tenzij een bepaalde actie die de app naar aanleiding van de melding probeert uit te voeren, mislukt. Deze fout kan worden gerapporteerd aan de Intune-service. Een voorbeeld van een scenario waarin moet worden gerapporteerd, is als de app geen gebruikersgegevens kan wissen nadat de IT-beheerder een wisbewerking heeft gestart.

Het is veilig om te blokkeren in `MAMNotificationReceiver.onReceive`, omdat de callback niet wordt uitgevoerd op de UI-thread.

De volgende `MAMNotificationReceiver`-interface wordt gedefinieerd in de SDK:

```
/**
 * The SDK is signaling that a WG event has occurred.
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

###<a name="types-of-notifications"></a>Typen meldingen

De volgende meldingen worden verzonden naar de app. Voor sommige van deze meldingen is mogelijk deelname van de app vereist.

* **`WIPE_USER_DATA`**: deze melding wordt verzonden in een `MAMUserNotification`-klasse. Wanneer deze melding wordt ontvangen, wordt verwacht dat de app alle gegevens verwijdert die zijn gekoppeld aan de bedrijfsidentiteit die is doorgegeven met de `MAMUserNotification`. Deze melding wordt momenteel verzonden tijdens het ongedaan maken van de registratie bij de Intune-service. De primaire naam van de gebruiker wordt doorgaans opgegeven tijdens het inschrijvingsproces. Als u zich voor deze melding registreert, moet uw app ervoor zorgen dat alle gegevens van de gebruiker zijn verwijderd. Als u zich niet voor de melding registreert, voert de app het standaardgedrag voor selectief wissen uit.

* **`WIPE_USER_AUXILIARY_DATA`**: apps kunnen zich voor deze melding registreren als de Intune App SDK de standaardactie voor selectief wissen moet uitvoeren, maar ze ook bepaalde aanvullende gegevens willen verwijderen wanneer de wisbewerking wordt uitgevoerd.  

* **`REFRESH_POLICY`**: deze melding wordt verzonden in een `MAMUserNotification`. Wanneer deze melding wordt ontvangen, moet alle Intune-beleid in de cache ongeldig worden gemaakt en worden bijgewerkt. Doorgaans wordt deze taak verwerkt door de SDK. Als het beleid echter op een permanente manier wordt gebruikt, moet deze taak worden verwerkt door de app.



### <a name="protection-of-backup-data"></a>Beveiliging van back-upgegevens

Vanaf Android Marshmallow (API 23) biedt Android apps twee manieren om een back-up van gegevens te maken. Elke optie is beschikbaar voor uw app en vereist andere stappen om ervoor te zorgen dat Intune-gegevensbeveiliging correct worden geïmplementeerd. In de [Android-API-handleiding](http://developer.android.com/guide/topics/data/backup.html) vindt u meer informatie over de back-upmethoden.

#### <a name="automatic-backup-for-apps"></a>Automatische back-ups voor apps

Android begon met het aanbieden van [automatische volledige back-ups](https://developer.android.com/guide/topics/data/autobackup.html) op Android Marshmallow-apparaten, ongeacht de doel-API van de app. Als u `android:allowBackup` in uw AndroidManifest.xml-bestand expliciet instelt op false (onwaar), wordt uw app door Android nooit opgenomen in de wachtrij voor back-ups en de bedrijfsgegevens in de app staan. In dit geval is er geen verdere actie nodig.

Het kenmerk `android:allowBackup` wordt standaard ingesteld op true (waar), zelfs als `android:allowBackup` niet in het manifestbestand is opgegeven. Dit betekent dat van alle app-gegevens automatisch een back-up in het Google Drive-account van de gebruiker wordt gemaakt. Deze standaardwerking vormt een *risico op het lekken van gegevens*. De SDK vereist de volgende wijzigingen om ervoor te zorgen dat gegevensbescherming wordt toegepast. Het is belangrijk dat u deze richtlijnen voor het beveiligen van klantgegevens volgt als u uw app op Android Marshmallow-apparaten wilt uitvoeren.  

Als u geen back-upagent hebt geschreven om een back-up van uw app te maken met `MAMBackupAgent` of `MAMBackupAgentHelper`, moet u overwegen en bepalen hoe Auto Backup uw app-gegevens uploadt. Met Intune kunt u alle [functies voor automatisch back-ups](https://developer.android.com/guide/topics/data/autobackup.html) gebruiken die beschikbaar zijn in Android, inclusief de mogelijkheid om aangepaste regels in XML te definiëren. Maar u moet deze stappen volgen om uw gegevens te beveiligen:

1. Gebruik de standaard `MAMBackupAgent` om toe te staan dat er automatisch volledige back-ups worden gemaakt die aan het Intune-beleid voldoen. Plaats `android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"` in uw app-manifest.

2. Als u beslist welk type volledige back-up uw app moet ontvangen (niet gefilterd, gefilterd of geen), stelt u het kenmerk `android:fullBackupContent` in op true (waar), false (onwaar) of een XML-resource in uw app. Kopieer wat u in `android:fullBackupContent` plaatst, naar een metadata-tag met de naam `com.microsoft.intune.mam.FullBackupContent`.

    Als u bijvoorbeeld wilt dat er volledige back-ups volgens uw aangepaste regels in een XML-bestand van uw app moeten worden gemaakt, geeft u als volgt een bron onder de metadata-tag `com.microsoft.intune.mam.FullBackupContent` in uw manifest op:
    ```
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```



#### <a name="keyvalue-backup"></a>Sleutelwaardeback-up

Deze back-upoptie voor sleutelwaarden is beschikbaar voor alle API's en maakt gebruik van `BackupAgentHelper` en `BackupAgent`.

##### <a name="backupagenthelper"></a>BackupAgentHelper

`BackupAgentHelper` is veel eenvoudiger te implementeren dan `BackupAgent`, zowel wat betreft de systeemeigen Android-functionaliteit als de MAM-integratie. Met `BackupAgentHelper` kunt u respectievelijk complete bestanden en gedeelde voorkeuren registreren bij `FileBackupHelper` of `SharedPreferencesBackupHelper`. Deze worden vervolgens toegevoegd aan `BackupAgentHelper` wanneer ze worden gemaakt.

##### <a name="backupagent"></a>BackupAgent

Met `BackupAgent` kunt u veel explicieter aangeven van welke gegevens een back-up moet worden gemaakt. Deze optie betekent echter wel dat u niet kunt profiteren van het back-upframework van Android. Omdat u verantwoordelijk bent voor de implementatie, zijn er meer stappen vereist om te zorgen voor de juiste mate van gegevensbeveiliging van MAM. Omdat het meeste werk naar u, de ontwikkelaar, wordt doorgeschoven, is de MAM-integratie iets bewerkelijker.

###### <a name="app-does-not-have-a-backup-agent"></a>App heeft geen back-upagent

Dit zijn de ontwikkelaarsopties wanneer `android:allowBackup =true`.

####### <a name="full-backup-according-to-a-configuration-file"></a>Volledige back-up op basis van een configuratiebestand

Geef een bron op onder de metagegevenstag `com.microsoft.intune.mam.FullBackupContent` in uw manifest. Bijvoorbeeld:     `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Voeg het volgende kenmerk toe aan de `<application>` -tag: `android:fullBackupContent="@xml/my_scheme"`, waarbij `my_scheme` een XML-bron in uw app is.

####### <a name="full-backup-without-exclusions"></a>Volledige back-up zonder uitsluitingen

Geef een tag op in het manifest, zoals `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />`.

Voeg het volgende kenmerk toe aan de `<application>`-tag: `android:fullBackupContent="true"`.

###### <a name="app-has-a-backup-agent"></a>App heeft een back-upagent

Volg de eerdere aanbevelingen in deze handleiding voor `BackupAgent` en `BackupAgentHelper`.

Overweeg over te schakelen naar het gebruik van onze `MAMDefaultFullBackupAgent`, waarmee u eenvoudig back-ups kunt maken op Android Marshmallow.

##### <a name="before-your-backup"></a>Voordat u een back-up maakt

Voordat u met uw back-up begint, moet u controleren of er een back-up van de gewenste bestanden of gegevensbuffers mag worden gemaakt. We hebben u een `isBackupAllowed`-functie in `MAMFileProtectionManager` en `MAMDataProtectionManager` gegeven om dit te kunnen controleren. Als er geen back-up van het bestand of de gegevensbuffer mag worden gemaakt, moet u niet ze niet in uw back-up blijven gebruiken.

Op een bepaald moment moet u tijdens de back-up, als u een back-up wilt maken van de identiteit voor de bestanden die u in stap 1 hebt gecontroleerd, `backupMAMFileIdentity(BackupDataOutput data, File … files)` aanroepen met de bestanden waaruit u gegevens wilt extraheren. Hierdoor worden automatisch nieuwe back-upentiteiten voor u gemaakt en naar `BackupDataOutput` geschreven. Deze entiteiten worden automatisch gebruikt bij het herstellen.

#### <a name="azure-directory-authentication-library-setup"></a>Azure Directory Authentication Library (ADAL) instellen  

De SDK gebruikt ADAL voor scenario's voor verificatie en voorwaardelijk starten. Deze scenario's vereisen dat apps over een zekere mate van Azure AD-configuratie beschikken (Azure Active Directory). De configuratiewaarden worden aan de SDK doorgegeven via de metagegevens van het `AndroidManifest` .

Als u uw app wilt instellen en de juiste verificatie wilt inschakelen, voegt u het volgende toe aan het app-knooppunt in `AndroidManifest`. Sommige van deze configuraties zijn alleen vereist als uw app voor de verificatie doorgaans gebruikmaakt van ADAL. In dat geval hebt u de specifieke waarden nodig die uw app heeft gebruikt zichzelf te registreren bij Azure AD. Zodoende wordt ervoor gezorgd dat de gebruiker niet twee keer om verificatie wordt gevraagd, omdat Azure AD twee afzonderlijke registratiewaarden herkent: één van de app en één van de SDK.

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

Van GUID's wordt niet verwacht dat zij worden voorgegaan of gevolgd door een accolade.

##### <a name="common-adal-configurations"></a>Algemene ADAL-configuraties

De volgende instellingen zijn de algemene configuratie-instellingen voor de waarden die eerder zijn uitgelegd.

###### <a name="app-does-not-integrate-adal"></a>App is niet geïntegreerd met ADAL

* De instantie moet worden ingesteld op de gewenste omgeving waar Azure AD-accounts zijn geconfigureerd.

* SkipBroker moet worden ingesteld op Waar.

###### <a name="app-integrates-adal"></a>App is geïntegreerd met ADAL

* De instantie moet worden ingesteld op de gewenste omgeving waar Azure AD-accounts zijn geconfigureerd.

* Client-ID moet worden ingesteld op de client-ID van de app.

* `NonBrokerRedirectURI` moet worden ingesteld op een geldige omleidings-URI voor de app. Of `urn:ietf:wg:oauth:2.0:oob` moet worden ingesteld als een geldige Azure AD omleidings-URI.

* SkipBroker moet worden ingesteld op false (onwaar) (of afwezig zijn).

* AAD moet zodanig worden ingesteld dat de omleidings-URI van de broker wordt geaccepteerd.

###### <a name="app-integrates-adal-but-does-not-support-the-azure-ad-authenticator-app"></a>App is geïntegreerd met ADAL maar biedt geen ondersteuning voor de Azure AD Authenticator-app

* De instantie moet worden ingesteld op de gewenste omgeving waar Azure AD-accounts zijn geconfigureerd.

* Client-ID moet worden ingesteld op de client-ID van de app.

* `NonBrokerRedirectURI` moet worden ingesteld op een geldige omleidings-URI voor de app. Of `urn:ietf:wg:oauth:2.0:oob` moet worden ingesteld als een geldige Azure AD omleidings-URI.

#### <a name="logging-in-the-sdk"></a>Logboekregistratie in de SDK

Logboekregistratie vindt plaats via het `java.util.logging` -framework. Voor het ontvangen van de logboeken stelt u algemene logboekregistratie in zoals beschreven in de [Technische Java-handleiding](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). Afhankelijk van de app is `App.onCreate` doorgaans de beste plaats voor het initiëren van logboekregistratie. Houd er rekening mee dat logboekberichten worden ingevoerd met de klassenaam. Deze is mogelijk verborgen.

###<a name="multi-identity"></a>Meerdere identiteiten

Het beleid dat door de Intune App SDK wordt toegepast, wordt standaard toegepast op de hele app. Meerdere identiteiten is een MAM-functie waarmee u beleid kunt toepassen per identiteit. Hiervoor wordt aanzienlijk meer deelname van een app vereist dan bij andere MAM-functies. De app meldt aan de app-SDK wanneer de actieve identiteit zal worden gewijzigd. Wanneer er een identiteitswijziging is vereist, moet dit door de SDK aan de app worden gemeld.

Op dit moment wordt slechts één beheerde identiteit ondersteund. Nadat de gebruiker het apparaat of de app inschrijft, gebruikt de SDK deze identiteit en beschouwt de SDK deze identiteit als de primaire beheerde identiteit. Andere gebruikers in de app worden behandeld als niet-beheerd met onbeperkte beleidsinstellingen.

Een identiteit wordt gewoon als een tekenreeks gedefinieerd. Identiteiten zijn niet hoofdlettergevoelig. In identiteitsaanvragen die door de SDK worden geretourneerd, wordt mogelijk niet hetzelfde gebruik van hoofd- en kleine letters toegepast als bij het instellen van de identiteit.

####<a name="enabling-multi-identity"></a>Meerdere identiteiten inschakelen

Alle apps worden standaard beschouwd als apps met één identiteit. Een app geeft aan met meerdere identiteiten te kunnen werken door de volgende metagegevens in het Android-manifest te plaatsen.

```
<meta-data
            android:name="com.microsoft.intune.mam.MAMMultiIdentity"
            android:value="true" />
```
####<a name="setting-the-identity"></a>De identiteit instellen

U kunt de identiteit van de app instellen op de volgende niveaus:

1. Procesniveau

2. Contextniveau (doorgaans `Activity`)

3. Threadniveau

Een identiteit die is ingesteld op threadniveau, vervangt een identiteit die is ingesteld op het niveau `Context`, die weer een identiteit vervangt die is ingesteld op procesniveau. Een identiteit die is ingesteld op `Context`, wordt alleen gebruikt wanneer dit van toepassing is. Bestands-I/O-taken hebben bijvoorbeeld geen gekoppelde `Context`. U kunt de volgende methoden voor `MAMPolicyManager` gebruiken om de identiteit in te stellen en de eerder ingestelde identiteitswaarden op te halen.

```
public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

public static String getUIPolicyIdentity(final Context context);

public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

public static String getProcessIdentity();

public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

public static String getCurrentThreadIdentity();

/**
 * Get the currently applicable app policy. Same as MAMComponents.get(AppPolicy.class). This method does
    not take the context identity into account.
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
U kunt ook de identiteit van de app wissen door deze op null in te stellen. De lege tekenreeks kan worden gebruikt als een identiteit waarvoor nooit beperkingen gelden. Alle methoden voor het instellen van de identiteit rapporteren resultaatwaarden via ``` MAMIdentitySwitchResult```. Er kunnen vier waarden worden geretourneerd:

* **SUCCEEDED**: de identiteitswijziging is geslaagd.

* **NOT_ALLOWED**: de identiteit kan niet worden gewijzigd. Dit doet zich voor als er is geprobeerd over te schakelen naar een andere zakelijke gebruiker die behoort tot hetzelfde bedrijf als de geregistreerde gebruiker. Dit doet zich ook voor als is geprobeerd de UI-identiteit (`Context`) in te stellen wanneer er een andere identiteit op de huidige thread is ingesteld.

* **CANCELLED**: de identiteitswijziging is geannuleerd door de gebruiker, doorgaans door de knop Terug te klikken bij een pincode-/verificatieprompt.

* **FAILED**: de identiteitswijziging is mislukt vanwege een niet-opgegeven reden.

Bij het instellen van een `Context`-identiteit wordt het resultaat asynchroon gerapporteerd. Als `Context` een `Activity`-klasse is, is pas na een voorwaardelijke start bekend of de identiteitswijziging i geslaagd. Het is mogelijk dat de gebruiker een pincode of de volledige bedrijfsreferenties moet opgeven voor een voorwaardelijke start. Van de app wordt verwacht dat deze een ```MAMSetUIIdentityCallback``` implementeert om dit resultaat te ontvangen, hoewel het toegestaan is null voor deze parameter door te geven.

```
public interface MAMSetUIIdentityCallback {
    void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
}
```

U kunt de identiteit van een activiteit ook rechtstreeks instellen via een methode voor `MAMActivity` in plaats van ```MAMPolicyManager.setUIPolicyIdentity``` aan te roepen. U kunt dit doen door de volgende methode te gebruiken:

 ```public final void switchMAMIdentity(final String newIdentity);```

Apps kunnen ook een methode voor `MAMActivity` overschrijven om te worden geïnformeerd over het resultaat van pogingen om de identiteit van die activiteit te wijzigen.

```public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);```

> [!NOTE]
> Bij het overschakelen naar een andere identiteit moet de activiteit mogelijk opnieuw worden gemaakt. In dit geval wordt de ```onSwitchMAMIdentityComplete```-callback geleverd aan het nieuwe exemplaar van de activiteit.


####<a name="implicit-identity-changes"></a>Impliciete identiteitswijzigingen

Naast de mogelijkheid van de app om de identiteit in te stellen, kan de identiteit van een thread of context worden gewijzigd op basis van binnenkomende gegevens vanuit een andere app waarvoor MAM is ingeschakeld. Als een activiteit bijvoorbeeld wordt gestart vanuit een `Intent`-klasse die door een andere MAM-app is verzonden, wordt de identiteit van de activiteit ingesteld op basis van de geldige identiteit in de andere app op het moment dat de `Intent`-klasse is verzonden.

Voor services wordt de identiteit van de thread op dezelfde manier ingesteld als voor de duur van een `onStart`- of `onBind`-aanroep. Aanroepen naar de `Binder` die is geretourneerd door `onBind`, stellen ook tijdelijk de threadidentiteit in. Aanroepen naar een ```ContentProvider``` stellen op dezelfde manier de threadidentiteit voor hun duur in.

Bovendien kan de gebruikersinteractie met een activiteit een impliciete identiteitswisseling veroorzaken. Als bijvoorbeeld een gebruiker tijdens ```Resume``` een autorisatieprompt annuleert, heeft dit een impliciete overgang naar een lege identiteit tot gevolg.
De app kan op de hoogte worden gebracht van deze wijzigingen en ze in bepaalde gevallen zo nodig verbieden. ```MAMService``` en ```MAMContentProvider``` maken de volgende methode beschikbaar die door subklassen kan worden vervangen:

```
public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
```
In het geval van ```MAMActivity``` is er een extra parameter aanwezig in de methode:
```
public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
```
Het ```AppIdentitySwitchReason```-gedeelte legt de bron van de impliciete switch vast. De volgende waarden kunnen worden geaccepteerd: ```CREATE```, ```RESUME_CANCELLED``` en ```NEW_INTENT```.  De reden ```RESUME_CANCELLED``` wordt gebruikt wanneer het voortzetten van de activiteit ertoe leidt dat de gebruikersinterface voor een pincode, verificatie of andere naleving wordt weergegeven en de gebruiker die gebruikersinterface probeert te annuleren, meestal door de knop Terug te gebruiken.
```AppIdentitySwitchResultCallback``` ziet er als volgt uit:
```
public interface AppIdentitySwitchResultCallback {
    /**
     * @param result
     *            whether the identity switch can proceed.
     */
    void reportIdentitySwitchResult(AppIdentitySwitchResult result);
}
```
```AppIdentitySwitchResult``` is ```SUCCESS``` of ```FAILURE```.

De methode ```onMAMIdentitySwitchRequired``` wordt aangeroepen voor alle impliciete identiteitswijzigingen behalve de wijzigingen die zijn aangebracht via een `Binder`-klasse die is geretourneerd door ```MAMService.onMAMBind```. De standaardimplementatie van ```onMAMIdentitySwitchRequired``` roept onmiddellijk ```reportIdentitySwitchResult(FAILURE)``` aan wanneer de reden ```RESUME_CANCELLED``` is. In alle andere gevallen wordt ```reportIdentitySwitchResult(SUCCESS)``` aangeroepen.

De meeste apps hoeven een identiteitswisseling niet op een andere manier te blokkeren of vertragen. Maar als een app dit wel moet doen, moet u rekening houden met de volgende punten:

* Als het overschakelen naar een andere identiteit wordt geblokkeerd, is het resultaat hetzelfde als wanneer de ```Receive```-instellingen voor delen de gegevensinvoer verbieden.

* Als een service wordt uitgevoerd op de hoofdthread, *moet* ```reportIdentitySwitchResult``` synchroon worden aangeroepen, anders loopt de UI-thread vast.

* Voor het maken van ```Activity``` wordt eerst ```onMAMIdentitySwitchRequired``` en vervolgens ```onMAMCreate``` aangeroepen. Als de app UI moet weergeven om te controleren of de identiteitswisseling is toegestaan, moet die UI worden weergegeven met een andere activiteit.

* Wanneer er in een ```Activity``` een overgang naar de lege identiteit wordt aangevraagd met een reden die gelijk is aan ```RESUME_CANCELLED```, moet de app de voortgezette activiteit wijzigen om gegevens weer te geven die consistent zijn met die identiteitswisseling. Als dit niet mogelijk is, moet de app de andere identiteit weigeren. De gebruiker wordt opnieuw gevraagd te voldoen aan het beleid voor de identiteit die wordt voortgezet (bijvoorbeeld door het scherm voor het invoeren van de pincode weer te geven).

> [!NOTE]
> Een app met meerdere identiteiten ontvangt altijd inkomende gegevens van beheerde en onbeheerde apps. Het is de verantwoordelijkheid van de app om gegevens van beheerde identiteiten op een beheerde manier te behandelen. Als een aangevraagde identiteit wordt beheerd ```(MAMPolicyManager.getIsIdentityManaged)```, maar de app dat account niet kan gebruiken (bijvoorbeeld omdat er eerst accounts, zoals e-mailaccounts, in de app moeten worden ingesteld), moet de identiteitswisseling worden geweigerd.

###<a name="file-protection"></a>Bestandsbeveiliging

Op het moment dat een bestand wordt gemaakt, wordt er op basis van een thread- en procesidentiteit een identiteit aan het bestand gekoppeld. Deze identiteit wordt gebruikt voor zowel bestandsversleuteling als selectief wissen. Alleen bestanden waarvan de identiteit een beleid heeft dat versleuteling vereist, worden versleuteld. De standaard-SDK-actie voor selectief wissen wist alleen bestanden die zijn gekoppeld aan de identiteit waarvoor een wisbewerking is aangevraagd. De app kan de identiteit van een bestand opvragen of wijzigen met ```MAMFileProtectionManager```.
```
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
}

public interface MAMFileProtectionInfo {
String getIdentity();
}
```

> [!NOTE]
> Het labelen van de bestandsidentiteit is gevoelig voor de offlinemodus. Houd rekening met de volgende punten:
> * Als de bedrijfsportal-app niet is geïnstalleerd, kunnen bestanden niet worden gelabeld met een identiteit.
>
> * Als de bedrijfsportal is geïnstalleerd maar de app geen beleid heeft, kunnen bestanden niet op een betrouwbare manier worden gelabeld met een identiteit.
>
> * Wanneer het labelen van bestandsidentiteit beschikbaar komt, worden alle eerder gemaakte bestanden als persoonlijk behandeld (behorend bij de identiteit met een lege tekenreeks), tenzij de app eerder is geïnstalleerd als een beheerde app met één identiteit. In dat geval worden ze behandeld als behorend tot de geregistreerde gebruiker.

####<a name="data-protection"></a>Gegevensbescherming

Het is niet mogelijk om een bestand te taggen als behorend bij meerdere identiteiten. Wanneer apps gegevens moeten opslaan die toebehoren aan verschillende gebruikers in hetzelfde bestand, kan dit handmatig worden gedaan met de functies van ```MAMDataProtectionManager```. De app kan dan gegevens versleutelen en deze koppelen aan een bepaalde gebruiker. De versleutelde gegevens zijn geschikt voor het opslaan naar schijf in een bestand. U kunt de gegevens opvragen die aan de identiteit zijn gekoppeld. De gegevens kunnen later worden ontsleuteld.

```
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
###<a name="content-providers"></a>Inhoudsproviders

Als de app mogelijk andere bedrijfsgegevens levert dan een ```ParcelFileDescriptor``` via een ```ContentProvider```, moet de app de ```MAMContentProvider```-methode ```isProvideContentAllowed(String)``` aanroepen die de ```UPN``` van de eigenaar voor de inhoud doorgeeft. Als deze functie false (onwaar) retourneert, kan de inhoud niet worden geretourneerd naar de oproepende functie. Bestandsdescriptors die zijn geretourneerd via een inhoudsprovider, worden automatisch verwerkt op basis van de bestandsidentiteit.

###<a name="selective-wipe"></a>Selectief wissen

Als een app wordt geregistreerd voor de ```WIPE_USER_DATA```-melding, profiteert deze niet van het voordeel van de standaard-SDK-actie voor selectief wissen. Voor apps die met meerdere identiteiten kunnen werken, kan dit belangrijker zijn omdat met de standaard-MAM-actie voor selectief wissen alleen bestanden worden gewist die overeenkomen met de identiteit waarvoor moet worden gewist.

Als u een app bouwt die waarvoor meerdere identiteiten kunnen worden gebruikt, kunt u zich registreren voor ```WIPE_USER_AUXILIARY_DATA```. Met deze melding kunt u profiteren van het standaard-SDK-gedrag voor wissen. Deze melding wordt direct verzonden voordat u de standaard-SDK-actie voor selectief wissen uitvoert. Houd er rekening mee dat een app nooit voor zowel ```WIPE_USER_DATA``` als ```WIPE_USER_AUXILIARY_DATA``` wordt geregistreerd.

### <a name="known-platform-limitations"></a>Bekende beperkingen van het platform

#### <a name="file-size-limitations"></a>Beperkingen van de bestandsgrootte

Op Android kunnen de beperkingen van de bestandsindeling van het uitvoerbare Dalvik-bestand een probleem vormen voor grote code-databases die zonder ProGuard worden uitgevoerd. Met name de volgende beperkingen kunnen van toepassing zijn:

* De limiet van 65.000 voor velden

* De limiet van 65.000 voor methoden

Wanneer u veel projecten opneemt, ontvangt elk `android:package` een kopie van R. Hierdoor neemt het aantal velden aanzienlijk toe naarmate er meer bibliotheken worden toegevoegd. De volgende aanbevelingen kunnen helpen deze beperking te verminderen:

* Waar mogelijk, moeten alle bibliotheekprojecten hetzelfde `android:package` delen. Dit zal niet sporadisch mislukken in het veld, omdat het puur een probleem met de build-tijd is. Bovendien verwerken nieuwere versies van de Android SDK vooraf DEX-bestanden om een deel van de redundantie weg te nemen. Hierdoor wordt de afstand van de velden nog verder verlaagd.

* Gebruik de nieuwste hulpprogramma's van de Android SDK-build die beschikbaar zijn.

* Verwijder alle overbodige en ongebruikte bibliotheken (bijvoorbeeld `android.support.v4`).

#### <a name="policy-enforcement-limitations"></a>Beperkingen op het afdwingen van beleid

**Schermopname**: de SDK kan geen nieuwe instelwaarde voor schermopnames afdwingen in `Activity`-klassen die `Activity.onCreate` al hebben doorlopen. Dit kan resulteren in een tijdsperiode waarin de app is ingesteld voor het uitschakelen van schermafbeeldingen maar waarin er nog steeds schermafbeeldingen kunnen worden gemaakt.

**Inhoudsoplossers**: het beleid voor overdracht of ontvangst kan het gebruik van een inhoudsoplosser geheel of gedeeltelijk blokkeren voor toegang tot de inhoudsprovider in een andere app. Dit leidt ertoe dat de `ContentResolver`-methoden null of een foutwaarde retourneren. (Als `openOutputStream` bijvoorbeeld wordt geblokkeerd, wordt `FileNotFoundException` geretourneerd.) De app kan deze aanroep uitvoeren om te controleren of een beleid een fout veroorzaakt (of kan veroorzaken) bij het schrijven van gegevens via een inhoudsoplosser:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Geëxporteerde services**: het `AndroidManifest.xml`-bestand dat is opgenomen in de Intune App SDK is voorzien van `MAMNotificationReceiverService`. Als u meldingen via de bedrijfsportal-app wilt verzenden naar een app met deze functionaliteit, moet dit een geëxporteerde service zijn. De service controleert de oproepende functie om ervoor te zorgen dat alleen de bedrijfsportal-app meldingen mag verzenden.

### <a name="android-best-practices"></a>Aanbevolen procedures voor Android

De Intune SDK onderhoudt het contract geleverd door de Android-API, hoewel er vaker foutmeldingen als gevolg van beleidsafdwinging kunnen worden geactiveerd. Deze aanbevolen Android-procedures verminderen de kans op fouten:

* Android SDK-functies die null kunnen retourneren, hebben nu een grotere kans om null te zijn. Zorg ervoor dat null-controles op de juiste plaatsen worden uitgevoerd, om de problemen te minimaliseren.

* Voor functies die u kunt controleren, gebruikt u de bijbehorende SDK API's om ze te controleren.

* Eventuele afgeleide functies moeten oproepen uitvoeren via de versies van hun superklasseversies.

* Vermijd het niet-eenduidige gebruik van API's. Als u bijvoorbeeld `Activity.startActivityForResult/onActivityResult` gebruikt zonder te controleren of `requestCode` tot vreemd gedrag leidt.

