---
title: Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor Android | Microsoft Intune
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 63d94a83a3a5ad9520abab3ef25e8d9690c26ce7
ms.openlocfilehash: 090b295ee8bf4aadb17bc58bf0282e87daf67a40


---

# Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor Android

> [!NOTE]
> U kunt desgewenst eerst [Overzicht van de Intune App SDK](intune-app-sdk.md) lezen voor meer informatie over de huidige functies en hoe u de integratie voor elk ondersteund platform voorbereidt. 

## Inhoud van de SDK 

De Intune App SDK voor Android is een standaard Android-bibliotheek zonder externe afhankelijkheden. De SDK bestaat uit het volgende:  

* **`Microsoft.Intune MAM.SDK.jar`**: de interfaces die nodig zijn om MAM in te schakelen in een app, naast het inschakelen van compatibiliteit met de Microsoft Intune-bedrijfsportal-app. Apps moeten dit opgeven als verwijzing naar de Android-bibliotheek.

* **`Microsoft.Intune.MAM.SDK.Support.v4.jar`**: de interfaces die nodig zijn om MAM in te schakelen in apps die gebruikmaken van de Android v4-ondersteuningsbibliotheek.  Apps die deze ondersteuning nodig hebben, moeten rechtstreeks verwijzen naar de directory met jar-bestanden. 

* **`Microsoft.Intune.MAM.SDK.Support.v7.jar`**: de interfaces die nodig zijn om MAM in te schakelen in apps die gebruikmaken van de Android v7-ondersteuningsbibliotheek.   Apps die deze ondersteuning nodig hebben, moeten rechtstreeks verwijzen naar het jar-bestand.

* **De brondirectory**: de bronnen (zoals tekenreeksen) waarop de SDK is gebaseerd. 

* **`Microsoft.Intune.MAM.SDK.aar`**: de SDK-onderdelen, met uitzondering van de JAR-bestanden voor Support.V4 en Support.V7. Dit bestand kan worden gebruikt in plaats van de afzonderlijke onderdelen, als uw build-systeem AAR-bestanden ondersteunt.

* **`AndroidManifest.xml`**: de extra toegangspunten en de vereisten voor bibliotheken. 

* **`THIRDPARTYNOTICES.TXT`**: een kennisgeving waarin code van derden of OSS-code die in uw app wordt gecompileerd aan de rechthebbenden wordt toegeschreven. 

## Vereisten 

De Intune App SDK is een gecompileerd Android-project. Als gevolg hiervan is de SDK grotendeels agnostisch ten opzichte van de versie van Android die de app gebruikt voor de minimumversie of de doel-API-versie. De SDK biedt ondersteuning voor Android-API 14 (Android 4.0 +) tot en met Android 24. 

## De werking van de Intune App SDK 

De Intune App SDK vereist wijzigingen in de broncode van een app om het beheerbeleid van de app in te schakelen. Dit wordt gedaan door de Android-basisklassen te vervangen door gelijkwaardige beheerde klassen, waarnaar in het document wordt verwezen middels het voorvoegsel `MAM`. De SDK-klassen begeven zich tussen de Android-basisklasse en de eigen afgeleide app-versie van die klasse.  Als we een activiteit als voorbeeld gebruiken, krijgt u uiteindelijk een overnamehiërarchie die er als volgt uitziet: `Activity ->MAMActivity->AppSpecificActivity`.

Wanneer `AppSpecificActivity` wil communiceren met de bovenliggende activiteit, bijvoorbeeld `super.onCreate())`, is `MAMActivity` de bovenliggende klasse, ondanks dat deze zich in de overnamehiërarchie bevindt en een aantal methoden vervangt. Android-apps hebben één modus en hebben toegang tot het gehele systeem via hun context-object.  Apps waarin de SDK Intune App is opgenomen, hebben echter twee modi, omdat de apps toegang blijven houden tot het systeem via het context-object, maar afhankelijk van de gebruikte basisactiviteit wordt het context-object ofwel aangeleverd door Android, of multiplext het intelligent tussen een beperkte weergave van het systeem en de door Android geleverde context.

De Intune App SDK voor Android is afhankelijk van de aanwezigheid van de Bedrijfsportal-app op het apparaat voor het inschakelen van MAM-beleid. Wanneer de Bedrijfsportal-app niet aanwezig is, wordt het gedrag van de app waarin MAM is ingeschakeld niet gewijzigd en fungeert de app als elke andere mobiele app. Wanneer de Bedrijfsportal is geïnstalleerd en beleid voor de gebruiker heeft, worden de SDK-toegangspunten asynchroon geïnitialiseerd. Initialisatie is alleen vereist wanneer het proces in eerste instantie door Android is gemaakt. Tijdens de initialisatie wordt er verbinding met de Bedrijfsportal-app gemaakt en wordt er restrictiebeleid voor apps gedownload.  

## Integratie met de Intune App SDK
 
Zoals eerder beschreven, vereist de Intune App SDK wijzigingen in de broncode van een app om het beheerbeleid van de app te kunnen inschakelen. Hieronder worden de stappen uitgelegd voor het inschakelen van MAM in uw app: 

### Klassen, methoden en activiteiten vervangen door hun MAM-equivalent (vereist) 

* Android-basisklassen moeten worden vervangen door hun MAM-equivalent. Hiertoe zoekt u alle exemplaren van de klassen op in de onderstaande tabel en vervangt u deze door het equivalent in de Intune App SDK.  

    | Android-klasse | Intune App SDK-vervanging |
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
    | enroid.app.PendingIntent | MAMPendingIntent |
    | enroid.app.Service | MAMService |
    | enroid.app.TabActivity | MAMTabActivity |
    | enroid.app.TaskStackBuilder | MAMTaskStackBuilder |
    | enroid.app.backup.BackupAgent | MAMBackupAgent |
    | enroid.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
    | enroid.app.backup.FileBackupHelper | MAMFileBackupHelper |
    | enroid.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
    | enroid.content.BroadcastReceiver | MAMBroadcastReceiver |
    | enroid.content.ContentProvider | MAMContentProvider |
    | enroid.os.Binder | MAMBinder* |
    | enroid.provider.DocumentsProvider | MAMDocumentsProvider |
    | enroid.preference.PreferenceActivity | MAMPreferenceActivity |

    * Binder hoeft alleen te worden vervangen door MAMBinder als de Binder is niet gegenereerd op basis van een AIDL-interface.

    **Microsoft.Intune.MAM.SDK.Suppof eent.v4.jar**:

    | Android-klasse Intune MAM | SDK-vervanging |
    |--|--|
    | enroid.suppof eent.v4.app.DialogFragment | MAMDialogFragment
    | enroid.suppof eent.v4.app.FragmentActivity | MAMFragmentActivity
    | enroid.suppof eent.v4.app.Fragment | MAMFragment
    | enroid.suppof eent.v4.app.TaskStackBuilder | MAMTaskStackBuilder
    | enroid.suppof eent.v4.content.FileProvider | MAMFileProvider
    
    **Microsoft.Intune.MAM.SDK.Suppof eent.v7.jar**:

    |Android-klasse | Intune MAM SDK-vervanging |
    |--|--|
    |enroid.suppof eent.v7.app.ActionBarActivity | MAMActionBarActivity |


* Wanneer u een Android-ingangspunt gebruikt dat wordt onderdrukt door het overeenkomstige MAM-equivalent, moet er een alternatieve versie van de levenscyclus van het ingangspunt worden gebruikt (met uitzondering van de klasse `MAMApplication`).

    Wanneer een activiteit wordt afgeleid van `MAMActivity`moet deze in plaats van het onderdrukken van `onCreate` en het aanroepen van `super.onCreate`bijvoorbeeld `onMAMCreate` onderdrukken en`uper.onMAMCreate`. Hierdoor kan (onder andere) het starten van de activiteit in bepaalde gevallen worden beperkt. 

### Functies inschakelen waarvoor app-deelname is vereist 

Er zijn enkele beleidsregels die de SDK niet op zichzelf kan implementeren. Om de app in staat te stellen het eigen gedrag voor deze functies te bepalen, geven we verschillende API's weer die u kunt vinden in de `AppPolicy` -interface hieronder.  

    /**
     * External facing app policies.
     */
    public interface AppPolicy {
        /**
         * Restrict where an app can save personal data.
         * 
         * @return True if the app is allowed to save to personal data stores;
         *         false otherwise.
         */
        boolean getIsSaveToPersonalAllowed();
    
        /**
         * Check if policy prohibits saving to a content provider location.
         * 
         * @param location
         *            a content URI to check
         * @return True if location is not a content URI or if policy does not 
         *         prohibit saving to the content location.
         */
        boolean getIsSaveToLocationAllowed(android.net.Uri location); 
    
        /**
         * Whether the SDK PIN prompt is enlightened for the app.
         * 
         * @return True if the PIN is enabled. False otherwise.
         */
        boolean getIsPinRequired();
        /**
         * Whether the Intune Managed Browser is required to open web links.
         *
         * @return True if the Managed Browser is required, false otherwise
         */
        boolean getIsManagedBrowserRequired();
    }

### Controle van de IT-beheerder over het opslaggedrag van de app inschakelen

Veel apps implementeren functies waarmee de eindgebruiker bestanden lokaal of naar een andere service kan opslaan. Met de Intune App SDK kunnen IT-beheerders beveiliging instellen tegen het lekken van gegevens door naar eigen goeddunken beleidsbeperkingen binnen hun organisatie toe te passen.  Een van de beleidsregels waarover de beheerder controle kan uitvoeren, is of de eindgebruiker kan opslaan naar een persoonlijke gegevensopslag. Dit omvat het opslaan naar een lokale locatie, een SD-kaart of een back-upservice. Voor het inschakelen van de functie is app-deelname vereist. Als uw app de mogelijkheid biedt om rechtstreeks vanuit de app naar persoonlijke of cloudlocaties op te slaan, moet u deze functie implementeren om ervoor te zorgen dat de IT-beheerder kan bepalen of opslaan naar een locatie al of niet is toegestaan. De onderstaande API laat de app weten of opslaan naar een persoonlijke opslag volgens het huidige beheerdersbeleid is toegestaan. De app kan het beleid vervolgens afdwingen omdat deze weet of er via de app een persoonlijke gegevensopslag voor de eindgebruiker beschikbaar is.  

Om te bepalen of het beleid wordt afgedwongen, kan de app de volgende oproep verzenden: 

    MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();

**Opmerking**: MAMComponents.get(AppPolicy.class) retourneert altijd een niet-null-app-beleid, zelfs als het apparaat of de app niet beheerd wordt. 

### Toestaan dat de app detecteert of pincodebeleid is vereist
 
 Er zijn extra beleidsregels waarvan de app mogelijk enkele functionaliteiten wil uitschakelen om dubbele functionaliteit in de Intune App SDK te voorkomen. Als de app bijvoorbeeld zijn eigen gebruikerservaring voor pincodes heeft, wil de app dit beleid mogelijk uitschakelen als de SDK is geconfigureerd om te vereisen dat de eindgebruiker een pincode invoert. 

Om te bepalen of het pincodebeleid zo is geconfigureerd dat er periodiek een pincode wordt vereist, kan de app de volgende oproep verzenden: 

    MAMComponents.get(AppPolicy.class).getIsPinRequired();

### Registreren voor meldingen van de SDK  

Met de Intune App SDK kan uw app controle uitvoeren over het gedrag wanneer bepaalde beleidsregels, zoals voor het wissen op afstand, worden gebruikt door de IT-beheerder. Hiertoe moet u zich registreren voor meldingen van de SDK door het maken van een `MAMNotificationReceiver` -klasse en het registreren van deze klasse met behulp van `MAMNotificationReceiverRegistry`. Dit wordt gedaan door de ontvanger en het type melding dat de ontvanger wil ontvangen, op te geven in  `App.onCreate`, zoals in het volgende voorbeeld te zien is:
 
    @Override
      public void onCreate() {
            super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class).registerReceiver(
    new ToastNotificationReceiver(), MAMNotificationType.WIPE_USER_DATA);
    }

`MAMNotificationReceiver` ontvangt gewoon meldingen. Sommige meldingen worden rechtstreeks door de SDK verwerkt, terwijl andere deelname van de app vereisen. Een app moet Waar of Onwaar retourneren vanaf een melding. De app moet altijd Waar retourneren, tenzij een bepaalde actie die de app naar aanleiding van de melding probeerde uit te voeren, is mislukt. Deze fout kan worden gemeld aan de Intune-service, bijvoorbeeld als de app aangeeft dat het wissen van gebruikersgegevens is mislukt. Het is veilig om te blokkeren in `MAMNotificationReceiver.onReceive`; de retouraanroep wordt niet uitgevoerd op de UI-thread. 

De MAMNotificationReceiver-interface is hieronder opgenomen onder zoals gedefinieerd in de SDK: 

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

De volgende meldingen worden verzonden naar de app en enkele ervan vereisen mogelijk app-deelname: 

* **De melding `WIPE_USER_DATA`**: deze melding wordt verzonden in een `MAMUserNotification`-klasse. Wanneer deze melding wordt ontvangen, moet de app alle gegevens verwijderen die zijn gekoppeld aan de identiteit die is doorgegeven met de `MAMUserNotification`. Deze melding wordt momenteel verzonden tijdens het uitschrijven bij de Intune-service. De primaire naam van de gebruiker wordt doorgaans opgegeven tijdens het inschrijvingsproces. Als u zich voor deze melding registreert, moet uw app ervoor zorgen dat alle gebruikersgegevens zijn verwijderd. Als u zich niet voor de melding registreert, wordt het standaardgedrag voor selectief wissen uitgevoerd. 

* **De melding `WIPE_USER_AUXILIARY_DATA`**: apps kunnen zich voor deze melding registreren als ze willen dat de Intune App SDK de standaardactie voor wissen uitvoert, maar nog steeds bepaalde aanvullende gegevens willen verwijderen wanneer het wissen wordt uitgevoerd.  

* **De melding `REFRESH_POLICY`**: deze melding wordt zonder aanvullende informatie verzonden in een MAMNotification. Wanneer deze melding wordt ontvangen, wordt eventueel beleid in de cache niet langer als ongeldig beschouwd en moet dus worden gecontroleerd wat het beleid inhoudt. Dit wordt doorgaans afgehandeld door de SDK maar moet door de app worden afgehandeld als het beleid op een persistente manier wordt gebruikt. 

### In behandeling zijnde intents en methoden 

Na het afleiden van een van de MAM-toegangspunten, kunt u de context gebruiken zoals u normaal doet, voor het starten van activiteiten, met behulp van de `PackageManager`, enzovoort.  `PendingIntents` vormen een uitzondering op deze regel. Bij het aanroepen van dergelijke klassen moet u de naam van de klasse wijzigen. In plaats dat bijvoorbeeld `PendingIntent.get*` wordt gebruikt, gebruikt u `MAMPendingIntents.get*`. 

In sommige gevallen is een methode die in de Android-klasse beschikbaar is, in de vervangende MAM-klasse als definitief gemarkeerd. De vervangende MAM klasse biedt in dit geval een gelijknamige methode (meestal voorafgegaan door "MAM") die in plaats daarvan moet worden onderdrukt. In plaats van het overschrijven van `ContentProvider.query`onderdrukt u bijvoorbeeld `MAMContentProvider.queryMAM`. De Java-compiler moet de laatste beperkingen afdwingen om het onbedoeld onderdrukken van de oorspronkelijke methode in plaats van de MAM-equivalent te voorkomen. 

## Beveiligen van back-upgegevens 

Vanaf Android Marshmallow (API 23) biedt Android apps twee manieren om een back-up van gegevens te maken. Deze opties zijn beschikbaar voor gebruik in uw app en vereisen verschillende stappen om ervoor te zorgen dat de MAM-gegevensbeveiliging op de juiste wijze wordt toegepast. U kunt de onderstaande tabel gebruiken voor een snel overzicht van de bijbehorende acties die zijn vereist voor een correct gegevensbeveiligingsgedrag.  U kunt ook meer informatie over Android-back-ups vinden in de [Android-ontwikkelaarshandleiding voor gegevensback-up](http://developer.android.com/guide/topics/data/backup.html). 

### Automatische volledige back-up

In Android M begon Android met het aanbieden van automatische volledige back-ups naar apps, ongeacht de doel-API, bij uitvoering op een M Android-apparaat. Zolang het kenmerk `android:allowBackup` niet is ingesteld op Onwaar, ontvangt een app volledige, ongefilterde back-ups van de app. Hierdoor ontstaat het risico op gegevenslekken en daarom vereist de SDK de wijzigingen die in de onderstaande tabel worden beschreven om ervoor te zorgen dat gegevensbescherming wordt toegepast.  Het is belangrijk dat u de onderstaande richtlijnen opvolgt om de gegevens van uw klanten correct te beveiligen.  Als u `android:allowBackup=false` instelt, wordt uw app nooit door het besturingssysteem in de wachtrij voor back-ups geplaatst en zijn er geen verdere acties voor MAM, aangezien er geen back-up wordt gemaakt.
 
 ## “key/value” backups

Deze optie is voor alle API's beschikbaar en maakt gebruik van `BackupAgent` en `BackupAgentHelper`. 

#### Met behulp van BackupAgentHelper

`BackupAgentHelper` is veel eenvoudiger te implementeren dan `BackupAgent`, zowel op het gebied van systeemeigen Android-functionaliteit als MAM-integratie. `BackupAgentHelper` kan de ontwikkelaar volledige bestanden en gedeelde voorkeuren registreren bij respectievelijk een `FileBackupHelper` of een `SharedPreferencesBackupHelper`, die vervolgens worden toegevoegd aan de `BackupAgentHelper` nadat deze is gemaakt. 

#### Met behulp van BackupAgent

`BackupAgent` kunt u veel explicieter aangeven van welke gegevens een back-up wordt gemaakt. Deze opties betekenen echter wel dat u niet kunt profiteren van het back-upproces van Android.  Omdat u redelijk verantwoordelijk bent voor de implementatie, zijn er meer stappen vereist om te zorgen voor de juiste mate van gegevensbeveiliging van MAM. Omdat het meeste werk naar u, de ontwikkelaar, wordt doorgeschoven, is de MAM-integratie iets bewerkelijker. 

##### App heeft geen back-upagent
  
Dit zijn de ontwikkelaarsopties wanneer `Android:allowbBackup =true`:

###### Volledige back-up op basis van een configuratiebestand: 

Geef een bron op onder de metagegevenstag `com.microsoft.intune.mam.FullBackupContent` in uw manifest. Bijvoorbeeld:
    `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Voeg het volgende kenmerk toe aan de `<application>` -tag: `android:fullBackupContent="@xml/my_scheme"`, waarbij `my_scheme` een XML-bron in uw app is. 

###### Volledige back-up zonder uitsluitingen 

Geef een tag op in het manifest, zoals `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />` 
 
Voeg het volgende kenmerk toe aan de `<application>`-tag: `android:fullBackupContent="true"`.

##### App heeft een back-upagent

Volg de aanbevelingen in de gedeelten `BackupAgent` en `BackupAgentHelper` hierboven. 

Overweeg over te schakelen naar het gebruik van onze `MAMDefaultFullBackupAgent`, waarmee u eenvoudig back-ups kunt maken op Android M. 

#### Voordat u een back-up maakt

Voordat u met uw back-up begint, moet u controleren of de bestanden of gegevensbuffers waarvan u een back-up wilt maken, inderdaad in aanmerking komen voor een back-up. We bieden u een functie `isBackupAllowed` in `MAMFileProtectionManager` en `MAMDataProtectionManager` om dit te bepalen. Als er geen back-up van het bestand of de gegevensbuffer mag worden gemaakt, moet u niet proberen deze te blijven gebruiken in uw back-up.

Als u op een bepaald moment tijdens de back-up een back-up wilt maken van de identiteit voor de bestanden die u in stap 1 hebt gecontroleerd, moet u `backupMAMFileIdentity(BackupDataOutput data, File … files)` aanroepen met de bestanden waaruit u gegevens wilt extraheren. Hierdoor worden automatisch nieuwe back-upentiteiten voor u gemaakt en naar de `BackupDataOutput` geschreven. Deze entiteiten worden automatisch gebruikt bij het herstellen. 

### Azure Directory Authentication Library (ADAL) configureren  

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

#### Algemene ADAL-configuraties 

Hieronder vindt u algemene configuratie-instellingen voor de waarden die hierboven worden uitgelegd. 

##### App is niet geïntegreerd met ADAL

* De instantie moet worden ingesteld op de gewenste omgeving waar AAD-accounts zijn geconfigureerd.

* SkipBroker moet worden ingesteld op Waar.

##### App is geïntegreerd met ADAL

* De instantie moet worden ingesteld op de gewenste omgeving waar AAD-accounts zijn geconfigureerd.

* Client-ID moet worden ingesteld op de client-ID van de app.

* `NonBrokerRedirectURI` moet worden ingesteld op een geldige omleidings-URI voor de app.
    * Or `urn:ietf:wg:oauth:2.0:oob` moet worden geconfigureerd als een geldige AAD omleidings-URI.

* SkipBroker moet worden ingesteld op Onwaar (of moet afwezig zijn)

* AAD moet worden geconfigureerd voor het accepteren van de omleidings-URI van de broker.

##### App is geïntegreerd met ADAL maar biedt geen ondersteuning voor de AAD Authenticator-app.

* De instantie moet worden ingesteld op de gewenste omgeving waar AAD-accounts zijn geconfigureerd.

* Client-ID moet worden ingesteld op de client-ID van de app.

* `NonBrokerRedirectURI` moet worden ingesteld op een geldige omleidings-URI voor de app.

    * Or `urn:ietf:wg:oauth:2.0:oob` moet worden geconfigureerd als een geldige AAD omleidings-URI.

### Het inschakelen van logboekregistratie in de SDK 

Logboekregistratie vindt plaats via het `java.util.logging` -framework. Voor het ontvangen van de logboeken stelt u algemene logboekregistratie in zoals beschreven in de [Technische Java-handleiding](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). Afhankelijk van de app is `App.onCreate` doorgaans de beste plaats voor het initiëren van logboekregistratie. Houd er rekening mee dat logboekberichten worden ingevoerd met de klassenaam, die ook kan worden verborgen.

## Bekende beperkingen van het platform 

### Beperkingen van de bestandsgrootte 

Op Android kunnen de beperkingen van de bestandsindeling van het uitvoerbare Dalvik-bestand een probleem vormen voor grote code-databases die zonder ProGuard worden uitgevoerd. Met name de volgende beperkingen kunnen van toepassing zijn: 

* De limiet van 65K op velden.

* De limiet van 65K op methoden.

Wanneer er veel projecten worden opgenomen, ontvangt elk android:package een kopie van R waardoor het aantal velden aanzienlijk toeneemt naarmate er meer bibliotheken worden toegevoegd. De volgende aanbevelingen kunnen helpen deze beperking te verzachten:
 
* Waar mogelijk, moeten alle bibliotheekprojecten hetzelfde android:package delen. Dit zal niet sporadisch mislukken in het veld, omdat het puur een probleem met de build-tijd is.   Bovendien verwerken nieuwere versies van de Android SDK vooraf DEX-bestanden om een deel van de redundantie weg te nemen. Hierdoor wordt de afstand van de velden nog verder verlaagd.

* Gebruik de nieuwste hulpprogramma's van de Android SDK-build die beschikbaar zijn.

* Verwijder alle overbodige en ongebruikte bibliotheken (bijvoorbeeld `android.support.v4`).

### Beperkingen op het afdwingen van beleid

**Schermopname**: de SDK kan geen nieuwe instelwaarde voor schermopnames afdwingen bij activiteiten die Activity.onCreate al hebben doorlopen. Dit kan resulteren in een tijdsperiode waarin de app is geconfigureerd voor het uitschakelen van schermafbeeldingen maar waarin er nog steeds schermafbeeldingen kunnen worden gemaakt.

**Met behulp van inhoudsoplossers*: het beleid voor overdracht of ontvangst kan het gebruik van een inhoudsoplosser geheel of gedeeltelijk blokkeren voor toegang tot de inhoudsprovider in een andere app. Dit zorgt ervoor dat ContentResolver-methoden null retourneren of een foutwaarde afgeven (bijvoorbeeld: `openOutputStream` genereert `FileNotFoundException` indien geblokkeerd). De app kan bepalen of het mislukte schrijven van gegevens via een inhoudsoplosser is veroorzaakt door beleid (of zou worden veroorzaakt door beleid) door de volgende oproep te plaatsen:

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Geëxporteerde services**: het bestand `AndroidManifest.xml` dat deel uitmaakt van de Intune App SDK bevat `MAMNotificationReceiverService`, wat een geëxporteerde service moet zijn om toe te staan dat de Bedrijfsportal meldingen naar een geïnformeerde app verzendt. De service controleert de oproepende functie om ervoor te zorgen dat alleen de Bedrijfsportal meldingen mag verzenden. 

## Aanbevolen procedures voor Android 

De Intune SDK onderhoudt het contract geleverd door de Android-API, hoewel er vaker foutmeldingen als gevolg van beleidsafdwinging kunnen worden geactiveerd. Deze aanbevolen Android-procedures verminderen de kans op fouten: 

* Android SDK-functies die null kunnen retourneren, hebben nu een grotere kans om null te zijn.  Om problemen tot een minimum te beperken, zorgt u ervoor dat null-controles op de juiste plaatsen worden uitgevoerd.

* Functies die kunnen worden gecontroleerd, moeten worden gecontroleerd via hun SDK-API's.

* Eventuele afgeleide functies moeten oproepen uitvoeren via de versies van hun bovenliggende klasse.

* Vermijd het niet-eenduidige gebruik van API's. Bijvoorbeeld: `Activity.startActivityForResult/onActivityResult` zonder te controleren of de requestCode vreemd gedrag kan veroorzaken



<!--HONumber=Aug16_HO5-->


