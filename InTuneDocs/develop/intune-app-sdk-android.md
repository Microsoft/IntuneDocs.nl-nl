---
title: Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor Android | Microsoft Intune
description: 
keywords: SDK
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: edbc701effb3817c2f9a160f05e7b5bc8ad0070e
ms.openlocfilehash: ee3a668a5415d14eb82e64e6bb16d9621bb13b57


---


# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor Android

> [!NOTE]
> U kunt desgewenst eerst [Overzicht van de Intune App SDK](intune-app-sdk.md) lezen voor meer informatie over de huidige functies en hoe u de integratie voor elk ondersteund platform voorbereidt. 

Met de Microsoft Intune App SDK voor Android kunt u Intune Mobile App Management (MAM) opnemen in uw Android-app. Een MAM-toepassing is een app die is geïntegreerd met de Intune App SDK en die u als IT-beheerder in staat stelt om beleid op uw mobiele app te implementeren wanneer de app actief door Intune wordt beheerd.

# <a name="whats-in-the-sdk"></a>Inhoud van de SDK 

De Intune App SDK voor Android is een standaard Android-bibliotheek zonder externe afhankelijkheden. De SDK bestaat uit het volgende:  

* **Microsoft.Intune.MAM.SDK.jar**: de interfaces die nodig zijn om MAM en interoperabiliteit in te schakelen met de Intune-bedrijfsportal-app. Apps moeten dit opgeven als verwijzing naar de Android-bibliotheek.

* **Microsoft.Intune.MAM.SDK.Support.v4.jar**: de interfaces die nodig zijn om MAM in te schakelen in apps die gebruikmaken van de Android v4-ondersteuningsbibliotheek.  Apps die deze ondersteuning nodig hebben, moeten rechtstreeks verwijzen naar het JAR-bestand. 

* **Microsoft.Intune.MAM.SDK.Support.v7.jar**: de interfaces die nodig zijn om MAM in te schakelen in apps die gebruikmaken van de Android v7-ondersteuningsbibliotheek. Apps die deze ondersteuning nodig hebben, moeten rechtstreeks verwijzen naar het JAR-bestand.

* **De brondirectory**: de bronnen (zoals tekenreeksen) waarop de SDK is gebaseerd. 

* **Microsoft.Intune.MAM.SDK.aar**: de SDK-onderdelen, met uitzondering van de JAR-bestanden voor Support.V4 en Support.V7. Dit bestand kan worden gebruikt in plaats van de afzonderlijke onderdelen, als uw build-systeem AAR-bestanden ondersteunt.

* **AndroidManifest.xml**: de extra invoerpunten en de bibliotheekvereisten. 

* **THIRDPARTYNOTICES.TXT**: een kennisgeving waarin code van derden of OSS-code die in uw app wordt gecompileerd aan de rechthebbenden wordt toegeschreven. 

# <a name="requirements"></a>Vereisten 

De Intune App SDK is een gecompileerd Android-project. Als gevolg hiervan is de SDK grotendeels agnostisch ten opzichte van de versie van Android die de app gebruikt voor de minimumversie of de doel-API-versie. De SDK biedt ondersteuning voor Android-API 14 (Android 4.0+) tot en met Android-API 24. 

De Intune App SDK voor Android is afhankelijk van de aanwezigheid van de [bedrijfsportal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)-app op het apparaat voor het inschakelen van MAM-beleid. Voor MAM zonder apparaatinschrijving hoeft de gebruiker het apparaat **niet** te registreren via de bedrijfsportal.


# <a name="how-the-intune-app-sdk-works"></a>De werking van de Intune App SDK 

##<a name="entry-points"></a>Invoerpunten

De Intune App SDK vereist wijzigingen in de broncode van een app om Intune-beleid voor het beheer van apps in te schakelen. Dit wordt gedaan door de Android-basisklassen te vervangen door gelijkwaardige Intune-basisklassen, waarvan de namen het voorvoegsel **MAM** hebben. De SDK-klassen begeven zich tussen de Android-basisklasse en de eigen afgeleide app-versie van die klasse.  Als we een activiteit als voorbeeld gebruiken, krijgt u uiteindelijk een overnamehiërarchie die er als volgt uitziet: Activity > MAMActivity > AppSpecificActivity.

Wanneer **AppSpecificActivity** bijvoorbeeld samenwerkt met het bovenliggende item (zoals het aanroepen van `super.onCreate()`), is **MAMActivity** de bovenliggende klasse. 

Android-apps hebben gewoonlijk één modus en hebben toegang tot het systeem via hun [context](https://developer.android.com/reference/android/content/Context.html)-object.  Apps waarin de Intune App SDK is opgenomen, hebben daarentegen twee modi. Deze apps blijven toegang houden tot het systeem via het context-object, maar afhankelijk van de gebruikte basisactiviteit wordt het context-object ofwel aangeleverd door Android, of multiplext het intelligent tussen een beperkte weergave van het systeem en de door Android geleverde context.

Wanneer u een Android-[invoerpunt](https://developer.android.com/guide/components/fundamentals.html) gebruikt dat wordt onderdrukt door het overeenkomstige MAM-equivalent, moet de MAM-versie van de levenscyclus van het invoerpunt worden gebruikt (met uitzondering van de klasse **MAMApplication**).

Bijvoorbeeld: wanneer een activiteit wordt afgeleid van **MAMActivity** moet deze in plaats van het onderdrukken van `onCreate` en het aanroepen van `super.onCreate` `onMAMCreate` onderdrukken en `super.onMAMCreate` aanroepen. Hierdoor kan (onder andere) het starten van de activiteit in bepaalde gevallen door Intune worden beperkt. 


##<a name="sdk-permissions"></a>SDK-machtigingen

De Intune App SDK vereist drie [Android-systeemmachtigingen](https://developer.android.com/guide/topics/security/permissions.html) voor apps waarin de SDK wordt geïntegreerd:

* `android.permission.GET_ACCOUNTS`  [aangevraagd tijdens runtime indien nodig]
* `android.permission.MANAGE_ACCOUNTS`
* `android.permission.USE_CREDENTIALS`

Deze machtigingen zijn vereist voor Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/)) om brokered verificatie uit te voeren. Als deze machtigingen niet worden toegekend aan de app of worden ingetrokken door de gebruiker, worden verificatiestromen waarvoor de broker (de bedrijfsportal-app) is vereist, uitgeschakeld.


##<a name="company-portal"></a>Bedrijfsportal

Waarom is de bedrijfsportal-app vereist? Wanneer de bedrijfsportal op het apparaat is geïnstalleerd en voor de gebruiker restrictiebeleid voor toepassingen is opgehaald vanuit de Intune-service, worden de SDK-invoerpunten asynchroon geïnitialiseerd. Initialisatie is alleen vereist wanneer het proces in eerste instantie door Android is gemaakt. Tijdens de initialisatie wordt er verbinding met de bedrijfsportal-app gemaakt en wordt er beleid van de app opgehaald.  

> [!NOTE]
> Wanneer de bedrijfsportal-app niet op het apparaat aanwezig is, wordt de werking van de app waarin Intune is ingeschakeld niet gewijzigd en fungeert de app als een normale app.


# <a name="how-to-integrate-with-the-intune-app-sdk"></a>Integratie met de Intune App SDK
 
Zoals eerder beschreven, vereist de SDK wijzigingen in de broncode van een app om beleid voor app-beheer te kunnen inschakelen. Hieronder worden de stappen uitgelegd voor het inschakelen van MAM in uw app: 

## <a name="replace-classes-methods-and-activities-with-their-mam-equivalent-required"></a>Klassen, methoden en activiteiten vervangen door hun MAM-equivalent (vereist) 

Android-basisklassen moeten worden vervangen door hun respectieve MAM-equivalenten. Hiertoe zoekt u alle exemplaren van de klassen op in de onderstaande tabel en vervangt u deze door het equivalent in de Intune App SDK. 

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
| enroid.app.PendingIntent | **MAMPendingIntent** * |
| enroid.app.Service | MAMService |
| enroid.app.TabActivity | MAMTabActivity |
| enroid.app.TaskStackBuilder | MAMTaskStackBuilder |
| enroid.app.backup.BackupAgent | MAMBackupAgent |
| enroid.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| enroid.app.backup.FileBackupHelper | MAMFileBackupHelper |
| enroid.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| enroid.content.BroadcastReceiver | MAMBroadcastReceiver |
| enroid.content.ContentProvider | MAMContentProvider |
| enroid.os.Binder | **MAMBinder** (alleen vereist als de Binder niet is gegenereerd op basis van een Android Interface Definition Language (AIDL)-interface) |
| enroid.provider.DocumentsProvider | MAMDocumentsProvider |
| enroid.preference.PreferenceActivity | MAMPreferenceActivity |


**Microsoft.Intune.MAM.SDK.Suppof eent.v4.jar**:

| Android-klasse Intune MAM | Intune App SDK-vervanging |
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
>Vergeet niet dat wanneer u een Android-[invoerpunt](https://developer.android.com/guide/components/fundamentals.html) gebruikt dat wordt onderdrukt door het overeenkomstige MAM-equivalent, de MAM-versie van de levenscyclus van het invoerpunt moet worden gebruikt (met uitzondering van de klasse **MAMApplication**).
>
>Bijvoorbeeld: wanneer een activiteit wordt afgeleid van **MAMActivity**, moet deze in plaats van het onderdrukken van `onCreate` en het aanroepen van `super.onCreate`, `onMAMCreate` onderdrukken en `super.onMAMCreate` aanroepen. Hierdoor kan (onder andere) het starten van de activiteit in bepaalde gevallen door Intune worden beperkt. 

### <a name="pendingintents-and-renamed-methods"></a>PendingIntents en methoden met een gewijzigde naam 

Na het afleiden van een van de MAM-invoerpunten, kunt u de context zonder problemen gebruiken zoals u normaal doet: activiteiten starten, **PackageManager** gebruiken enzovoort.  

**PendingIntents** vormen een uitzondering op deze regel. Bij het aanroepen van dergelijke klassen moet u de naam van de klasse wijzigen. In plaats van dat bijvoorbeeld `PendingIntent.get*` wordt gebruikt, gebruikt u de methode `MAMPendingIntents.get*`. Hierna kunnen de resulterende **PendingIntents** op de gewone manier worden gebruikt.

In sommige gevallen is een methode die in de Android-klasse beschikbaar is, in de vervangende MAM-klasse als definitief gemarkeerd. De vervangende MAM klasse biedt in dit geval een gelijknamige methode (meestal voorafgegaan door "MAM") die in plaats daarvan moet worden onderdrukt. In plaats van het overschrijven van `ContentProvider.query`onderdrukt u bijvoorbeeld `MAMContentProvider.queryMAM`. De Java-compiler moet de laatste beperkingen afdwingen om het onbedoeld onderdrukken van de oorspronkelijke methode in plaats van de MAM-equivalent te voorkomen. 

##<a name="enable-features-that-require-app-participation"></a>Functies inschakelen waarvoor app-deelname is vereist 

Er zijn enkele beleidsregels die de SDK niet op zichzelf kan implementeren. De app kan de eigen werking voor deze functies bepalen met verschillende API's in de **AppPolicy**-interface hieronder.  

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

## <a name="enable-it-control-over-app-saving-behavior"></a>IT-beheer van het opslaggedrag van de app inschakelen

Veel apps implementeren functies waarmee de eindgebruiker bestanden lokaal of naar een cloudopslagservice kan opslaan. Met de Intune App SDK kunnen IT-beheerders beveiliging instellen tegen het lekken van gegevens door naar eigen goeddunken beleidsbeperkingen binnen hun organisatie toe te passen.  Een van de beleidsregels waarover IT controle kan uitvoeren, is of de eindgebruiker kan opslaan naar een 'persoonlijke', niet-beheerde gegevensopslag. Dit omvat het opslaan naar een lokale locatie, een SD-kaart of een back-upservice van derden. 

**Voor het inschakelen van de functie is app-deelname vereist.** Als uw app de mogelijkheid biedt om rechtstreeks vanuit de app naar persoonlijke of cloudlocaties op te slaan, moet u deze functie implementeren om ervoor te zorgen dat de IT-beheerder kan bepalen of opslaan naar een locatie is toegestaan. De onderstaande API laat de app weten of opslaan naar een persoonlijke opslag volgens het huidige beleid van de Intune-beheerder is toegestaan. De app kan het beleid vervolgens afdwingen omdat deze weet of er via de app een persoonlijke gegevensopslag voor de eindgebruiker beschikbaar is.  

Om te bepalen of het beleid wordt afgedwongen, kan de app de volgende oproep verzenden: 

```
MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();
```

**Opmerking**: `MAMComponents.get(AppPolicy.class)` retourneert altijd een niet-null-app-beleid, zelfs als voor het apparaat of de app geen Intune-beheerbeleid van toepassing is. 

## <a name="allow-app-to-detect-if-pin-policy-is-required"></a>Toestaan dat de app detecteert of pincodebeleid is vereist
 
Mogelijk wilt u bepaalde functionaliteit van enkele Intune-app-beperkingen uitschakelen om functionaliteit in de Intune App SDK niet te dupliceren. Als de app bijvoorbeeld een eigen gebruikerservaring voor pincodes heeft, kan dit beleid worden uitgeschakeld als de SDK is geconfigureerd om te vereisen dat de eindgebruiker een pincode invoert. 

Om te bepalen of er Intune-pincodebeleid is geconfigureerd om bij het starten een app-pincode te vereisen, kan de app de volgende oproep verzenden: 

```
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

## <a name="registering-for-notifications-from-the-sdk"></a>Registreren voor meldingen van de SDK  

Met de Intune App SDK kan uw app de werking van bepaald beleid, zoals selectief wissen, beheren bij implementatie door de IT-beheerder. Als een IT-beheerder dergelijk beleid implementeert, wordt met de Intune-service een melding naar de SDK verzonden.

Uw app moet worden geregistreerd voor meldingen van de SDK door een **MAMNotificationReceiver**-klasse te maken en deze te registreren met **MAMNotificationReceiverRegistry**. Dit wordt gedaan door de ontvanger en het gewenste type melding op te geven in `App.onCreate`, zoals in het volgende voorbeeld te zien is:

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

**MAMNotificationReceiver** ontvangt gewoon meldingen vanuit de Intune-service. Sommige meldingen worden rechtstreeks door de SDK verwerkt, terwijl andere deelname van de app vereisen. 

Een app **moet** Waar of Onwaar retourneren vanaf een melding. 

De app moet altijd Waar retourneren, tenzij een bepaalde actie die de app naar aanleiding van de melding probeerde uit te voeren, is mislukt. 

* Deze fout kan worden gerapporteerd aan de Intune-service. Een voorbeeld van een scenario waarin moet worden gerapporteerd, is als de app geen gebruikersgegevens kan wissen nadat de IT-beheerder een wisactie heeft gestart. 

Het is veilig om te blokkeren in `MAMNotificationReceiver.onReceive`, omdat de callback niet wordt uitgevoerd op de UI-thread. 

De **MAMNotificationReceiver**-interface is hieronder opgenomen zoals gedefinieerd in de SDK: 

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

##<a name="types-of-notifications"></a>Typen meldingen
De volgende meldingen worden verzonden naar de app en enkele ervan vereisen mogelijk app-deelname: 

* **`WIPE_USER_DATA`**: deze melding wordt verzonden in een **MAMUserNotification**-klasse. Wanneer deze melding wordt ontvangen, wordt verwacht dat de app alle gegevens verwijdert die zijn gekoppeld aan de bedrijfsidentiteit die is doorgegeven met de **MAMUserNotification**. Deze melding wordt momenteel verzonden tijdens het uitschrijven bij de Intune-service. De primaire naam van de gebruiker wordt doorgaans opgegeven tijdens het inschrijvingsproces. Als u zich voor deze melding registreert, moet uw app ervoor zorgen dat alle gegevens van de gebruiker zijn verwijderd. Als u zich niet voor de melding registreert, wordt het standaardgedrag voor selectief wissen uitgevoerd.

* **`WIPE_USER_AUXILIARY_DATA`**: apps kunnen zich voor deze melding registreren als de Intune App SDK de standaardactie voor selectief wissen moet uitvoeren, maar er nog steeds bepaalde aanvullende gegevens moeten worden verwijderd wanneer het wissen wordt uitgevoerd.  

* **`REFRESH_POLICY`**: deze melding wordt verzonden in een **MAMUserNotification**. Wanneer deze melding wordt ontvangen, moet alle Intune-beleid in de cache ongeldig worden gemaakt en worden bijgewerkt. Dit wordt doorgaans afgehandeld door de SDK maar moet door de app worden afgehandeld als het beleid op een persistente manier wordt gebruikt. 



## <a name="protecting-backup-data"></a>Beveiligen van back-upgegevens 

Vanaf Android Marshmallow (API 23) biedt Android apps twee manieren om een back-up van gegevens te maken. Elke optie is beschikbaar voor uw app en vereist andere stappen om ervoor te zorgen dat Intune-gegevensbeveiliging correct worden geïmplementeerd. U kunt de onderstaande tabel gebruiken voor een overzicht van de bijbehorende acties die zijn vereist voor een correct gegevensbeveiligingsgedrag.  In de [Android-API-handleiding](http://developer.android.com/guide/topics/data/backup.html) vindt u meer informatie over de back-upmethoden. 

### <a name="auto-backup-for-apps"></a>Automatische back-ups voor apps

Android begon met het aanbieden van [automatische volledige back-ups](https://developer.android.com/guide/topics/data/autobackup.html) op Android Marshmallow-apparaten, ongeacht de doel-API van de app. Als u in uw AndroidManifest.xml `android:allowBackup` expliciet hebt ingesteld op **onwaar**, wordt uw app door Android nooit opgenomen in de wachtrij voor back-ups en blijven de bedrijfsgegevens in de app. In dit geval is er geen verdere actie nodig.

Het kenmerk `android:allowBackup` is echter standaard ingesteld op waar, zelfs als `android:allowBackup` niet in het manifestbestand is opgegeven. Dit betekent dat van alle app-gegevens automatisch een back-up in het Google Drive-account van de gebruiker wordt gemaakt. Deze standaardwerking vormt een **risico op het lekken van gegevens**. Daarom vereist de SDK de wijzigingen die hieronder worden beschreven om ervoor te zorgen dat gegevensbescherming wordt toegepast.  Het is belangrijk dat u de onderstaande richtlijnen voor het beveiligen van klantgegevens volgt als u uw app op Android Marshmallow-apparaten wilt uitvoeren.  

*  Als u geen back-upagent hebt geschreven om een back-up van uw app te maken met behulp van een **MAMBackupAgent** of **MAMBackupAgentHelper**, moet u overwegen en bepalen hoe uw app-gegevens worden geüpload bij automatische back-ups. U kunt met Intune alle [functies voor automatische back-ups](https://developer.android.com/guide/topics/data/autobackup.html) gebruiken die door Android beschikbaar worden gesteld, inclusief de mogelijkheid om aangepaste regels in XML te definiëren, maar u moet de volgende stappen uitvoeren om uw gegevens te beveiligen:

    1. Gebruik de standaard MAMBackupAgent voor automatische volledige back-ups die aan het Intune-beleid voldoen. Plaats `android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"` in uw app-manifest. 
    2. Als u beslist welk type volledige back-up uw app moet ontvangen (niet gefilterd, gefilterd of geen), moet u het kenmerk `android:fullBackupContent` instellen op waar, onwaar of een XML-bron in uw app. Kopieer wat u in `android:fullBackupContent` plaatst, in een metadata-tag met de naam `com.microsoft.intune.mam.FullBackupContent`

    **Voorbeelden**: als uw app volledige back-ups volgens uw aangepaste regels in een XML-bestand moet hebben, geeft u als volgt een bron onder de metadata-tag `com.microsoft.intune.mam.FullBackupContent` in uw manifest op: 
    ```
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```



### <a name="keyvalue-backup"></a>Key/Value-back-up

Deze optie is voor alle API's beschikbaar en maakt gebruik van `BackupAgent` en `BackupAgentHelper`. 

#### <a name="using-backupagenthelper"></a>Met behulp van BackupAgentHelper

`BackupAgentHelper` is veel eenvoudiger te implementeren dan `BackupAgent` , zowel op het gebied van systeemeigen Android-functionaliteit als MAM-integratie. `BackupAgentHelper` kan de ontwikkelaar volledige bestanden en gedeelde voorkeuren registreren bij respectievelijk een `FileBackupHelper` of een `SharedPreferencesBackupHelper`, die vervolgens worden toegevoegd aan de `BackupAgentHelper` nadat deze is gemaakt. 

#### <a name="using-backupagent"></a>Met behulp van BackupAgent

`BackupAgent` kunt u veel explicieter aangeven van welke gegevens een back-up wordt gemaakt. Deze opties betekenen echter wel dat u niet kunt profiteren van het back-upproces van Android.  Omdat u redelijk verantwoordelijk bent voor de implementatie, zijn er meer stappen vereist om te zorgen voor de juiste mate van gegevensbeveiliging van MAM. Omdat het meeste werk naar u, de ontwikkelaar, wordt doorgeschoven, is de MAM-integratie iets bewerkelijker. 

##### <a name="app-does-not-have-a-backup-agent"></a>App heeft geen back-upagent
  
Dit zijn de ontwikkelaarsopties wanneer `android:allowBackup =true`:

###### <a name="full-back-up-according-to-a-configuration-file"></a>Volledige back-up op basis van een configuratiebestand: 

Geef een bron op onder de metagegevenstag `com.microsoft.intune.mam.FullBackupContent` in uw manifest. Bijvoorbeeld:     `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Voeg het volgende kenmerk toe aan de `<application>` -tag: `android:fullBackupContent="@xml/my_scheme"`, waarbij `my_scheme` een XML-bron in uw app is. 

###### <a name="full-back-dup-without-exclusions"></a>Volledige back-up zonder uitsluitingen 

Geef een tag op in het manifest, zoals `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />` 
 
Voeg het volgende kenmerk toe aan de `<application>`-tag: `android:fullBackupContent="true"`.

##### <a name="app-has-a-backup-agent"></a>App heeft een back-upagent

Volg de aanbevelingen in de gedeelten `BackupAgent` en `BackupAgentHelper` hierboven. 

Overweeg over te schakelen naar het gebruik van onze `MAMDefaultFullBackupAgent`, waarmee u eenvoudig back-ups kunt maken op Android M. 

#### <a name="before-your-backup"></a>Voordat u een back-up maakt

Voordat u met uw back-up begint, moet u controleren of de bestanden of gegevensbuffers waarvan u een back-up wilt maken, inderdaad in aanmerking komen voor een back-up. We bieden u een functie `isBackupAllowed` in `MAMFileProtectionManager` en `MAMDataProtectionManager` om dit te bepalen. Als er geen back-up van het bestand of de gegevensbuffer mag worden gemaakt, moet u niet proberen deze te blijven gebruiken in uw back-up.

Als u op een bepaald moment tijdens de back-up een back-up wilt maken van de identiteit voor de bestanden die u in stap 1 hebt gecontroleerd, moet u `backupMAMFileIdentity(BackupDataOutput data, File … files)` aanroepen met de bestanden waaruit u gegevens wilt extraheren. Hierdoor worden automatisch nieuwe back-upentiteiten voor u gemaakt en naar de `BackupDataOutput` geschreven. Deze entiteiten worden automatisch gebruikt bij het herstellen. 

### <a name="configure-azure-directory-authentication-library-adal"></a>Azure Directory Authentication Library (ADAL) configureren  

De SDK is voor verificatie en voorwaardelijke startscenario's afhankelijk van ADAL. ADAL vereist dat apps een bepaalde hoeveelheid Azure Active Directory-configuratie bevatten. De configuratiewaarden worden aan de SDK doorgegeven via de metagegevens van het `AndroidManifest` . Als u uw app wilt configureren en de juiste verificatie wilt inschakelen, voegt u het volgende toe aan het app-knooppunt in het `AndroidManifest`. Sommige van deze configuratie-instellingen zijn alleen vereist als uw app gebruikmaakt van ADAL voor verificatie in het algemeen; in dat geval hebt u de specifieke waarden nodig waarmee uw app zich bij AAD registreert. Dit wordt gedaan om ervoor te zorgen dat de eindgebruiker niet tweemaal om verificatie wordt gevraagd doordat AAD twee afzonderlijke registratiewaarden herkent: één van de app en één van de SDK. 

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

#### <a name="common-adal-configurations"></a>Algemene ADAL-configuraties 

Hieronder vindt u algemene configuratie-instellingen voor de waarden die hierboven worden uitgelegd. 

##### <a name="app-does-not-integrate-adal"></a>App is niet geïntegreerd met ADAL

* De instantie moet worden ingesteld op de gewenste omgeving waar AAD-accounts zijn geconfigureerd.

* SkipBroker moet worden ingesteld op Waar.

##### <a name="app-integrates-adal"></a>App is geïntegreerd met ADAL

* De instantie moet worden ingesteld op de gewenste omgeving waar AAD-accounts zijn geconfigureerd.

* Client-ID moet worden ingesteld op de client-ID van de app.

* `NonBrokerRedirectURI` moet worden ingesteld op een geldige omleidings-URI voor de app.
    * Or `urn:ietf:wg:oauth:2.0:oob` moet worden geconfigureerd als een geldige AAD omleidings-URI.

* SkipBroker moet worden ingesteld op Onwaar (of moet afwezig zijn)

* AAD moet worden geconfigureerd voor het accepteren van de omleidings-URI van de broker.

##### <a name="app-integrates-adal-but-does-not-support-the-aad-authenticator-app"></a>App is geïntegreerd met ADAL maar biedt geen ondersteuning voor de AAD Authenticator-app.

* De instantie moet worden ingesteld op de gewenste omgeving waar AAD-accounts zijn geconfigureerd.

* Client-ID moet worden ingesteld op de client-ID van de app.

* `NonBrokerRedirectURI` moet worden ingesteld op een geldige omleidings-URI voor de app.

    * Or `urn:ietf:wg:oauth:2.0:oob` moet worden geconfigureerd als een geldige AAD omleidings-URI.

### <a name="how-to-enable-logging-in-the-sdk"></a>Het inschakelen van logboekregistratie in de SDK 

Logboekregistratie vindt plaats via het `java.util.logging` -framework. Voor het ontvangen van de logboeken stelt u algemene logboekregistratie in zoals beschreven in de [Technische Java-handleiding](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). Afhankelijk van de app is `App.onCreate` doorgaans de beste plaats voor het initiëren van logboekregistratie. Houd er rekening mee dat logboekberichten worden ingevoerd met de klassenaam, die ook kan worden verborgen.

##<a name="multiidentity"></a>Meerdere identiteiten
###<a name="overview"></a>Overzicht
De Intune App SDK past beleid standaard op de hele app toe. Meerdere identiteiten is een MAM-functie die kan worden ingeschakeld zodat beleid moet worden toegepast op een niveau per identiteit.  Hiervoor wordt aanzienlijk meer deelname van een app vereist dan bij andere MAM-functies. De app moet de app-SDK laten weten wanneer de actieve identiteit moet worden gewijzigd. Ook informeert de SDK de app wanneer een identiteitswijziging nodig is. Op dit moment wordt slechts één beheerde identiteit ondersteund. Zodra de gebruiker het apparaat of de app inschrijft, gebruikt de SDK deze identiteit en beschouwt de SDK deze identiteit als de primaire beheerde identiteit. Andere gebruikers in de app worden beschouwd als niet-beheerd met onbeperkte beleidsinstellingen. 

Een identiteit wordt gewoon als een tekenreeks gedefinieerd. Identiteiten zijn hoofdlettergevoelig en in geretourneerde identiteitsaanvragen, die waren gericht aan de SDK, wordt mogelijk niet hetzelfde gebruik van hoofd- en kleine letters toegepast als oorspronkelijk is gebruikt toen de identiteit werd ingesteld.

###<a name="enabling-multiidentity"></a>Meerdere identiteiten inschakelen
Alle apps worden standaard beschouwd als apps met één identiteit. Een app geeft aan met meerdere identiteiten te kunnen werken door de volgende metagegevens in het Android-manifest te plaatsen.

```
<meta-data
            android:name="com.microsoft.intune.mam.MAMMultiIdentity"
            android:value="true" />
```
###<a name="setting-the-identity"></a>De identiteit instellen

Ontwikkelaars kunnen de identiteit van de app instellen op de volgende niveaus: 
1. Procesniveau 
2. Contextniveau (in het algemeen activiteit) 
3. Threadniveau 

Een identiteit die is ingesteld op threadniveau, vervangt een identiteit die is ingesteld op contextniveau, die weer een identiteit vervangt die is ingesteld op procesniveau. Een identiteit die is ingesteld op contextniveau, wordt alleen gebruikt wanneer dat mogelijk is. Bestands-I/O-bewerkingen bijvoorbeeld hebben geen gekoppelde context. De volgende methoden voor MAMPolicyManager kunnen worden gebruikt voor het instellen van de identiteit en ophalen van de identiteitswaarden die eerder zijn ingesteld.

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
U kunt ook de identiteit van de app wissen door deze op null in te stellen. De lege tekenreeks kan worden gebruikt als een identiteit waarvoor nooit beperkingen gelden. Alle methoden voor het instellen van de identiteit rapporteren resultaatwaarden terug via ``` MAMIdentitySwitchResult```. Er zijn vier waarden die kunnen worden geretourneerd:

1.**SUCCEEDED**: de identiteitswijziging is geslaagd 2.**NOT_ALLOWED**: de identiteitswijziging is niet toegestaan. Dit doet zich voor als er is geprobeerd over te schakelen naar een andere zakelijke gebruiker die behoort tot hetzelfde bedrijf als de geregistreerde gebruiker. Dit doet zich ook voor als is geprobeerd de UI (context)-identiteit in te stellen wanneer er een andere identiteit op de huidige thread is ingesteld.
3.**CANCELLED**: de identiteitswijziging is geannuleerd door de gebruiker, in het algemeen door op de knop Terug te klikken bij een pincode-/verificatieprompt.
4.**FAILED**: de identiteitswijziging is mislukt vanwege een niet-opgegeven reden.

Bij het instellen van een contextidentiteit wordt het resultaat asynchroon gerapporteerd. Als de context een activiteit is, wordt pas bekend of de identiteitswijziging is geslaagd nadat de voorwaardelijke start is uitgevoerd waarvoor de gebruiker mogelijk een pincode of de volledige bedrijfsreferenties moet invoeren. Van de app wordt verwacht dat deze een ```MAMSetUIIdentityCallback``` implementeert om dit resultaat te ontvangen, hoewel het toegestaan is null voor deze parameter door te geven.

```
public interface MAMSetUIIdentityCallback {
    void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult); 
}
```

U kunt de identiteit van een activiteit ook rechtstreeks instellen via een methode voor MAMActivity in plaats van ``` MAMPolicyManager.setUIPolicyIdentity``` aan te roepen. U kunt dit doen door de volgende methode te gebruiken:

 ```public final void switchMAMIdentity(final String newIdentity);```

Apps kunnen ook een methode voor MAMActivity overschrijven om te worden geïnformeerd over het resultaat van pogingen om de identiteit van die activiteit te wijzigen 

```public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);```

**Opmerking:** bij het overschakelen naar een andere identiteit is het misschien nodig de activiteit opnieuw te maken. In dit geval wordt de ```onSwitchMAMIdentityComplete```-callback geleverd aan het nieuwe exemplaar van de activiteit.

###<a name="implicit-identity-changes"></a>Impliciete identiteitswijzigingen

Naast de mogelijkheid van de app om de identiteit in te stellen, kan de identiteit van een thread of context worden gewijzigd op basis van binnenkomende gegevens vanuit een andere app waarin MAM is ingeschakeld. Als een activiteit bijvoorbeeld wordt gestart vanuit een intent die door een andere MAM-app is verzonden, wordt de identiteit van de activiteit ingesteld op basis van de geldige identiteit in de andere app op het moment dat de intent werd verzonden.
Voor services wordt de identiteit van de thread op dezelfde manier ingesteld voor de duur van een onStart- of onBind-aanroep. Aanroepen naar de Binder die zijn geretourneerd door onBind, stellen ook tijdelijk de threadidentiteit in.
Aanroepen naar een ```ContentProvider``` stellen op dezelfde manier de threadidentiteit voor hun duur in.
Bovendien kan de gebruikersinteractie met een activiteit een impliciete identiteitswisseling veroorzaken.
Als bijvoorbeeld een gebruiker tijdens ```Resume``` een autorisatieprompt annuleert, heeft dit een impliciete overgang naar een lege identiteit tot gevolg.
De app heeft de mogelijkheid gekregen met deze wijzigingen te werken en ze zo nodig te verbieden. ```MAMService``` en ```MAMContentProvider``` maken de volgende methode beschikbaar die door subklassen kan worden vervangen:

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
De ```AppIdentitySwitchReason``` registreert de bron van de impliciete wisseling en kan de waarden ```CREATE```, ```RESUME_CANCELLED``` en ```NEW_INTENT``` accepteren.  De reden ```RESUME_CANCELLED``` wordt gebruikt wanneer het voortzetten van de activiteit ertoe leidt dat de gebruikersinterface voor een pincode, verificatie of andere naleving wordt weergegeven en de gebruiker die gebruikersinterface probeert te annuleren, meestal door de knop Terug te gebruiken.
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
Waarbij ```AppIdentitySwitchResult``` ofwel ```SUCCESS``` of ```FAILURE``` is. 

De methode ```onMAMIdentitySwitchRequired``` wordt aangeroepen voor alle impliciete identiteitswijzigingen behalve de wijzigingen die zijn aangebracht via een Binder die is geretourneerd door ```MAMService.onMAMBind```. De standaardimplementatie van ```onMAMIdentitySwitchRequired``` roept onmiddellijk ```reportIdentitySwitchResult(FAILURE)``` aan wanneer de reden ```RESUME_CANCELLED``` is en ```reportIdentitySwitchResult(SUCCESS)``` in alle andere gevallen. 

Het is niet waarschijnlijk dat de meeste apps een identiteitswisseling op een andere manier moeten blokkeren of vertragen, maar als dit voor een app toch nodig is, zijn de volgende punten van belang: *als een identiteitswisseling wordt geblokkeerd, is het resultaat hetzelfde als wanneer de instellingen voor het delen van ```Receive``` de binnenkomende gegevens had verboden. *```reportIdentitySwitchResult``` **moet** synchroon worden aangeroepen als een service op de hoofdthread wordt uitgevoerd, anders loopt de UI-thread vast. 
*Voor het maken van een ```Activity``` wordt eerst ```onMAMIdentitySwitchRequired``` en daarna ```onMAMCreate``` aangeroepen. Als de app UI moet weergeven om te bepalen of de identiteitswisseling is toegestaan, moet die UI worden weergegeven met een andere activiteit. *Wanneer in een activiteit een overgang naar de lege identiteit wordt aangevraagd met een reden die gelijk is aan ```RESUME_CANCELLED```, moet de app de voortgezette activiteit wijzigen om gegevens consistent met die identiteitswisseling weer te geven.  Als dit niet mogelijk is, moet de app de wisseling weigeren en wordt de gebruiker opnieuw gevraagd te voldoen aan het beleid voor de identiteit die wordt voortgezet (bijvoorbeeld door het scherm voor het invoeren van de pincode weer te geven). 

**Opmerking:** een app met meerdere identiteiten ontvangt altijd inkomende gegevens van beheerde en onbeheerde apps. Het is de verantwoordelijkheid van de app om gegevens van beheerde identiteiten op een beheerde manier te behandelen. Als een aangevraagde identiteit wordt beheerd met ```(MAMPolicyManager.getIsIdentityManaged)```, maar de app dat account niet kan gebruiken (bijvoorbeeld omdat accounts, zoals e-mailaccounts, eerst in de app moeten worden ingesteld), moet de identiteitswisseling worden geweigerd.

##<a name="file-protection"></a>Bestandsbeveiliging
Elk bestand heeft een identiteit die op het moment van aanmaak is gekoppeld op basis van een thread- en procesidentiteit. Deze identiteit wordt gebruikt voor zowel bestandsversleuteling als selectief wissen. Alleen bestanden waarvan de identiteit een beleid heeft dat versleuteling vereist, worden versleuteld. De standaard-SDK-actie voor selectief wissen wist alleen bestanden die zijn gekoppeld aan de identiteit waarvoor het wissen is aangevraagd. De app kan de identiteit van een bestand opvragen of wijzigen met ```MAMFileProtectionManager```
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

**Opmerking:** het taggen van bestandsidentiteit is gevoelig voor de offline modus. Met de volgende punten moet rekening worden gehouden.
* Als de bedrijfsportal niet is geïnstalleerd, is taggen van bestandsidentiteit niet mogelijk. 
* Als de bedrijfsportal is geïnstalleerd maar de app geen beleid heeft, is het betrouwbaar taggen van bestandsidentiteit niet mogelijk.
* Wanneer het taggen van bestandsidentiteit beschikbaar komt, worden alle eerder gemaakte bestanden als persoonlijk behandeld (behorend bij de identiteit met een lege tekenreeks) tenzij de app eerder is geïnstalleerd als een beheerde app met één identiteit. In dat geval wordt deze behandeld als behorend tot de geregistreerde gebruiker.

###<a name="data-protection"></a>Gegevensbescherming
Het is niet mogelijk om een bestand te taggen als behorend bij meerdere identiteiten. Wanneer voor apps gegevens moeten worden opgeslagen die behoren tot verschillende gebruikers in hetzelfde bestand, kan dit handmatig worden gedaan met de functies van ```MAMDataProtectionManager```. De app kan dan gegevens versleutelen en deze koppelen aan een bepaalde gebruiker. De versleutelde gegevens zijn geschikt voor het opslaan naar schijf in een bestand. U kunt de gegevens die zijn gekoppeld aan de identiteit opvragen en de gegevens kunnen dan later worden ontsleuteld. 

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
##<a name="content-providers"></a>Inhoudsproviders
Als de app mogelijk andere bedrijfsgegevens levert dan een ```ParcelFileDescriptor``` via een ```ContentProvider```, moet de app de ```MAMContentProvider```-methode ```isProvideContentAllowed(String)``` aanroepen die de ```UPN``` van de eigenaar voor de inhoud doorgeeft. Als deze functie onwaar retourneert, kan de inhoud niet worden geretourneerd naar de aanroeper. Bestandsdescriptors die zijn geretourneerd via een inhoudsprovider, worden automatisch verwerkt op basis van de bestandsidentiteit.

##<a name="selective-wipe"></a>Selectief wissen
Als een app wordt geregistreerd voor de ```WIPE_USER_DATA```-melding, profiteert deze niet van het voordeel van de standaard-SDK-actie voor selectief wissen. Voor apps die met meerdere identiteiten kunnen werken, kan dit belangrijker zijn omdat met de standaard-MAM-actie voor selectief wissen alleen bestanden worden gewist die overeenkomen met de identiteit waarvoor moet worden gewist. Als u een app maakt die met meerdere identiteiten kan werken, kunt u zich registreren voor ```WIPE_USER_AUXILIARY_DATA```, waarmee u kunt profiteren van het standaard-SDK-wisgedrag. Deze melding wordt direct verzonden voordat de standaard-SDK-actie voor selectief wissen wordt uitgevoerd. Houd er rekening mee dat een app nooit voor zowel ```WIPE_USER_DATA``` als ```WIPE_USER_AUXILIARY_DATA``` wordt geregistreerd.

## <a name="known-platform-limitations"></a>Bekende beperkingen van het platform 

### <a name="file-size-limitations"></a>Beperkingen van de bestandsgrootte 

Op Android kunnen de beperkingen van de bestandsindeling van het uitvoerbare Dalvik-bestand een probleem vormen voor grote code-databases die zonder ProGuard worden uitgevoerd. Met name de volgende beperkingen kunnen van toepassing zijn: 

* De limiet van 65K op velden.

* De limiet van 65K op methoden.

Wanneer er veel projecten worden opgenomen, ontvangt elk android:package een kopie van R waardoor het aantal velden aanzienlijk toeneemt naarmate er meer bibliotheken worden toegevoegd. De volgende aanbevelingen kunnen helpen deze beperking te verzachten:
 
* Waar mogelijk, moeten alle bibliotheekprojecten hetzelfde android:package delen. Dit zal niet sporadisch mislukken in het veld, omdat het puur een probleem met de build-tijd is.   Bovendien verwerken nieuwere versies van de Android SDK vooraf DEX-bestanden om een deel van de redundantie weg te nemen. Hierdoor wordt de afstand van de velden nog verder verlaagd.

* Gebruik de nieuwste hulpprogramma's van de Android SDK-build die beschikbaar zijn.

* Verwijder alle overbodige en ongebruikte bibliotheken (bijvoorbeeld `android.support.v4`).

### <a name="policy-enforcement-limitations"></a>Beperkingen op het afdwingen van beleid

**Schermopname**: de SDK kan geen nieuwe instelwaarde voor schermopnames afdwingen bij activiteiten die Activity.onCreate al hebben doorlopen. Dit kan resulteren in een tijdsperiode waarin de app is geconfigureerd voor het uitschakelen van schermafbeeldingen maar waarin er nog steeds schermafbeeldingen kunnen worden gemaakt.

**Met behulp van inhoudsoplossers*: het beleid voor overdracht of ontvangst kan het gebruik van een inhoudsoplosser geheel of gedeeltelijk blokkeren voor toegang tot de inhoudsprovider in een andere app. Dit zorgt ervoor dat ContentResolver-methoden null retourneren of een foutwaarde afgeven (bijvoorbeeld: `openOutputStream` genereert `FileNotFoundException` indien geblokkeerd). De app kan bepalen of het mislukte schrijven van gegevens via een inhoudsoplosser is veroorzaakt door beleid (of zou worden veroorzaakt door beleid) door de volgende oproep te plaatsen:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Geëxporteerde services**: het bestand `AndroidManifest.xml` dat deel uitmaakt van de Intune App SDK bevat `MAMNotificationReceiverService`, wat een geëxporteerde service moet zijn om toe te staan dat de Bedrijfsportal meldingen naar een geïnformeerde app verzendt. De service controleert de oproepende functie om ervoor te zorgen dat alleen de Bedrijfsportal meldingen mag verzenden. 

## <a name="recommended-android-best-practices"></a>Aanbevolen procedures voor Android 

De Intune SDK onderhoudt het contract geleverd door de Android-API, hoewel er vaker foutmeldingen als gevolg van beleidsafdwinging kunnen worden geactiveerd. Deze aanbevolen Android-procedures verminderen de kans op fouten: 

* Android SDK-functies die null kunnen retourneren, hebben nu een grotere kans om null te zijn.  Om problemen tot een minimum te beperken, zorgt u ervoor dat null-controles op de juiste plaatsen worden uitgevoerd.

* Functies die kunnen worden gecontroleerd, moeten worden gecontroleerd via hun SDK-API's.

* Eventuele afgeleide functies moeten oproepen uitvoeren via de versies van hun bovenliggende klasse.

* Vermijd het niet-eenduidige gebruik van API's. Bijvoorbeeld: `Activity.startActivityForResult/onActivityResult` zonder te controleren of de requestCode vreemd gedrag kan veroorzaken






<!--HONumber=Oct16_HO5-->


