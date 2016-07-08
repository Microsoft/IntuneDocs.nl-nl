---
title: Wat is er nieuw en release-opmerkingen | Azure RMS
description: Geeft een overzicht van belangrijke wijzigingen en functies in deze nieuwe versie van de RMS SDK.
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 06/16/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 4fa1c686-b00b-4734-9abb-141ce582a6af
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
ms.sourcegitcommit: f7dd88d90357c99c69fe4fdde67c1544595e02f8
ms.openlocfilehash: eccc0ba9c13e0c35c8d0c8877ce92f9b99e83835


---

# Wat is er nieuw en opmerkingen bij de release

## Wat is er nieuw?
Microsoft Rights Management SDK 4.2 maakt het activeren van de RMS-toepassing een stuk eenvoudiger en biedt hierbij meer flexibiliteit. In dit onderwerp worden de belangrijke wijzigingen en functies in deze nieuwe versie van de RMS SDK beschreven.

-   [Nieuw voor juni 2016](#new_for_June_2016)
-   [Update van december 2015](#december_2015_update)
-   [Update van juli 2015: voegt ondersteuning toe voor Linux/C++-ontwikkeling](#july_2015_update_-_adds_support_for_linux___c___development)
-   [Update van mei 2015: voegt beheer voor logboekregistratie toe](#may_2015_update_-_adds_logging_control)
-   [Update van februari 2015: voegt ondersteuning toe voor Windows Store-apps](#february_2015_update_-_adds_windows_store_application_support)
-   [Update van januari 2015: voegt ondersteuning toe voor het WinPhone-platform](#january_2015_update_-_adds_winphone_platform_support)
-   [Update van oktober 2014: upgrade naar Microsoft RMS SDK 4.1](#october_2014_update_-_upgrade_to_microsoft_rms_sdk_4.1)
-   [Opmerkingen bij de release](#release-notes)
-   [Veelgestelde vragen](#frequently_asked_questions)

### Nieuw voor juni 2016

- **Ondersteuning voor moderne verificatie** - Biedt aanmelding bij RMS-geschikte apps op basis van Active Directory Authentication Library (ADAL). Hiermee zijn aanmeldingsfuncties mogelijk zoals Multi-Factor Authentication (MFA), onafhankelijke identiteitsproviders op basis van SAML met RMS-clienttoepassingen en verificatie op basis van smartcards en certificaten. Daarnaast is het gebruik van het basisverificatieprotocol in voor RMS-geschikt apps niet meer nodig dankzij deze ondersteuning.
- **Ondersteuning voor documenttracking** -Ontwikkelaars kunnen nu documenttracking inschakelen bij het beveiligen van documenten in hun apps 
- Verbeterde prestaties
- Oplossingen voor problemen


### Update van december 2015

Bij deze release heeft de RMS SDK voor apparaten nu versie 4.2 en hierin zijn toegevoegd:

-   Documenttracking, alleen RMS Online, voor iOS-/OS X- en Android-besturingssystemen.

    Zie voor meer informatie en gebruiksrichtlijnen voor iOS en OS X de klasse [**MSLicenseMetadata**](/rights-management/sdk/4.2/api/iOS/mslicensemetadata#msipcthin2_mslicensemetadata_class_objc) die trackinggegevens en de aanvullende registratiemethode voor documenttracking bevat voor [**MSUserPolicy**](/rights-management/sdk/4.2/api/iOS/iOS#msipcthin2_msuserpolicy_interface_objc). Er zijn gelijksoortige toevoegingen aan [**LicenseMetadata**](/rights-management/sdk/4.2/api/android/com.microsoft.rightsmanagement#msipcthin2_licensemetadata_interface_java) en [**UserPolicy**](/rights-management/sdk/4.2/api/android/userpolicy) voor Android.

    Zie [**Documenttracking gebruiken**](how-to-use-document-tracking.md) voor een gedetailleerde beschrijving van de functie voor documenttracking.

-   Een reeks synchrone methoden die parallel lopen aan de asynchrone versies voor de Android-API:

    [**De synchrone methode CustomProtectedInputStream.create**](/rights-management/sdk/4.2/api/android/customprotectedinputstream#msipcthin2_customprotectedinputstream_create_synchronous_method_java)

    [**De synchrone methode CustomProtectedOutputStream.create**](/rights-management/sdk/4.2/api/android/customprotectedoutputstream#msipcthin2_customprotectedoutputstream_create_synchronous_method)

    [**De synchrone methode ProtectedFileInputStream.create**](/rights-management/sdk/4.2/api/android/protectedfileinputstream#msipcthin2_protectedfileinputstream_create_synchronous_method)

    [**De synchrone methode ProtectedFileOutputStream.create**](/rights-management/sdk/4.2/api/android/customprotectedoutputstream#msipcthin2_customprotectedoutputstream_create_synchronous_method)

    [**De synchrone methode TemplateDescriptor.getTemplates**](/rights-management/sdk/4.2/api/android/templatedescriptor#msipcthin2_templatedescriptor_gettemplates_synchronous_method_java)

    [**De synchrone methode UserPolicy.acquire**](/rights-management/sdk/4.2/api/android/userpolicy#msipcthin2_userpolicy_acquire_synchronous_method_java)

    [**De synchrone methode UserPolicy.create (PolicyDescriptor…)**](/rights-management/sdk/4.2/api/android/userpolicy#msipcthin2_userpolicy_create_policydescriptor_______synchronous_method_java)

    [**De synchrone methode UserPolicy.create (TempalteDescriptor…)**](/rights-management/sdk/4.2/api/android/userpolicy#msipcthin2_userpolicy_create_templatedescriptor_______synchronous_method_java)

-   Er is een nieuwe klasse [**ProtectedBuffer**](/rights-management/sdk/4.2/api/android/com.microsoft.rightsmanagement#msipcthin2_protectedbuffer_class) toegevoegd aan de Android-API.
-   Updates voor het verbeteren van de foutberichten en probleemoplossing.
-   Aanzienlijke prestatieverbeteringen voor cryptografische bewerkingen.

### Update van juli 2015: voegt ondersteuning toe voor Linux/C++-ontwikkeling

In deze versie wordt het volgende toegevoegd:

-   RMS SDK 4.1 voor Linux-platformen

    Zie [Aan de slag](get-started.md) voor meer informatie.

### Update van mei 2015: voegt beheer voor logboekregistratie toe

In deze release wordt ondersteuning toegevoegd voor het volgende:

-   iOS

    App versleutelen en ontsleutelen kan afzonderlijk en parallel worden uitgevoerd.

    Zie [**MSProtector**](/rights-management/sdk/4.2/api/iOS/iOS#msipcthin2_msprotector_class_objc) voor meer informatie.

    Beheerinstellingen voor het logboekregistratieniveau zijn ingeschakeld.

    Zie [Fout- en prestatieregistratie inschakelen](enabling-logging.md) voor meer informatie

    Er is ondersteuning toegevoegd voor het wissen van de cache.

    Zie [**MSProtection:resetStateWithCompletionBlock**](/rights-management/sdk/4.2/api/iOS/msprotection#msipcthin2_msprotection_resetstatewithcompletionblock_method_objc) voor meer informatie.

### Update van februari 2015: voegt ondersteuning toe voor Windows Store-apps

Deze release voegt ondersteuning toe voor Windows Store-apps en komt functioneel overeen met de Windows Phone-, Android- en iOS-/OS X-release voor RMS SDK 4.1.

### Update van januari 2015: voegt ondersteuning toe voor het WinPhone-platform

Deze release voegt ondersteuning toe voor het Windows Phone-besturingssysteem en komt functioneel overeen met de Android- en iOS-/OS X-release voor RMS SDK 4.1.

## Update van oktober 2014: upgrade naar Microsoft RMS SDK 4.1

Met versie 4.1 van de RMS SDK worden de volgende nieuwe functies toegevoegd voor Google Android en Apple iOS/OS X.

-   SDK-API-uitbreidingen voor Android en iOS/OS X voor verwerking met *toestemming van de gebruiker*. Hierbij wordt bevestiging van de gebruiker gevraagd voor SDK-gedrag. Momenteel wordt toestemming van de gebruiker ondersteund voor documenttracking en de toegang tot onbekende URL's voor de AD RMS-service.

    Zie als voorbeeld de versie van de Android-API van [**ConsentCallback-interface**](/rights-management/sdk/4.2/api/android/com.microsoft.rightsmanagement#msipcthin2_consentcallback_interface_java) voor meer informatie.

-   iOS 8 en OS X 10.10 (Yosemite) worden nu ondersteund. Er zijn ook enkele wijzigingen van eigenschapsnamen doorgevoerd die worden vereist door Xcode 6.

    Bijvoorbeeld: MSUserPolicy.name is gewijzigd in [**MSUserPolicy.policyName**](/rights-management/sdk/4.2/api/iOS/msuserpolicy#msipcthin2_msuserpolicy_name_property_objc).

## Opmerkingen bij de release

In deze sectie wordt informatie verstrekt over de huidige en vorige versies van de Microsoft Rights Management SDK 4.x-API's, waarvan u als ontwikkelaar mogelijk op de hoogte wilt zijn.

**Release met globale beschikbaarheid van AD RMS SDK 4.1 voor iOS-/OS X- en Android-platformen**

-   **AD RMS-ondersteuning**: IT-beheerders kunnen RMS-apps voor mobiele apparaten gebruiken met de nieuwe uitbreidingen voor mobiele apparaten van de AD RMS-server.
-   **Offlinegebruik**: eindgebruikers hebben offlinetoegang tot de gegevens die door RMS zijn beveiligd.
-   **Gescheiden verificatie** Ontwikkelaars kunnen gebruikmaken van hun eigen verificatiebibliotheek voor Azure RMS en AD RMS (of gebruikmaken van de aanbevolen [Azure AD Authentication Library (ADAL)](https://MSDN.Microsoft.Com/library/jj573266.aspx)).
-   **Gescheiden gebruikersinterface**: ontwikkelaars kunnen hun gebruikersinterface bouwen voor het beveiligen en gebruiken van documenten die door RMS worden beveiligd.
-   **Opnieuw ontworpen API**: ontwikkelaars kunnen nu gebruikmaken van een eenvoudige en transparante API voor versleuteling en ontsleuteling, die met een minimale inspanning zorgt voor consistentie in het RMS-gedrag en de gebruikerservaring.

**Van toepassing op alle platformen**

-   De RMS SDK 4.x-API's zijn niet *thread-veilig*.

**Android**

-   Wanneer u een voorbeeldapp gebruikt op een Amazon® Kindle-apparaat om .ptxt-bijlagen weer te geven, moet u eerst het bestand downloaden voordat u het weergeeft.

    **Oplossing**: dit is een bekend probleem en wordt later verholpen.

-   Een toepassing die gebruikmaakt van de SDK kan vastlopen als meerdere exemplaren worden toegestaan.

    **Oplossing**: zorg ervoor dat de toepassing het aanroepen van de Android-API door meerdere exemplaren niet toestaat.

-   Wanneer ik de methode [**ProtectedFileOutputStream**](/rights-management/sdk/4.2/api/android/protectedfileoutputstream#msipcthin2_protectedfileoutputstream_class_java)**.write(byte\[\] array, int offset, int length)** gebruik met een lengte die afwijkt van de waarde *array.length*, kan ik de inhoud later niet gebruiken met de SDK.

    **Oplossing**: dit is een bekend probleem. U kunt dit als volgt oplossen: geef altijd een **byte \[\]**-matrix door met dezelfde lengte als de lengteparameter of gebruik de methode [**ProtectedFileOutputStream**](/rights-management/sdk/4.2/api/android/protectedfileoutputstream#msipcthin2_protectedfileoutputstream_class_java)**.write(byte\[\] array)**.

**iOS en OS X**

-   Er zijn twee dialecten in het Portugees die worden ondersteund door onze SDK’s voor iOS en OS X. Vanwege een fout wordt de eerste lokalisatie momenteel helaas niet volledig ondersteund. Vanwege deze fout wordt het Portugees niet volledig ondersteund. De meeste tekst wordt vertaald, maar niet de gebruikersinterface.

    1. Portugees

    2. Portugees (Portugal)

**Alleen voor iOS**

-   RMS SDK 4.x geeft de indicator voor netwerkactiviteit niet weer.

    Dit is een bekend verschijnsel dat bij iOS kan optreden volgens de Apple Human Interface-richtlijnen.

**Alleen voor OS X**

-   RMS SDK 4.x geeft de indicator voor netwerkactiviteit niet weer.

    Dit is een bekend verschijnsel dat bij OS X kan optreden volgens de Apple Human Interface-richtlijnen.

-   **Oplossing**: als u een MDI-toepassing (Multiple Document Interface) wilt maken met onze SDK voor OS X, hanteert u de volgende richtlijn.

    De volgende methoden mogen niet gelijktijdig worden uitgevoerd. Als u wilt controleren of de uitvoering is voltooid, gebruikt u de methode voor voltooiingsblokken zoals deze wordt beschreven.

    - [**protectedDataWithProtectedFile**](/rights-management/sdk/4.2/api/iOS/msprotecteddata#msipcthin2_msprotecteddata_protecteddatawithprotectedfile_completionblock_method_objc)
    - [**customProtectedDataWithPolicy**](/rights-management/sdk/4.2/api/iOS/mscustomprotecteddata#msipcthin2_mscustomprotecteddata_customprotecteddatawithpolicy_protecteddata_contentstartposition_contentsize_completionblock_method_objc)



**Opmerking**: MDI-toepassingen worden niet ondersteund door onze API voor iOS.

## Veelgestelde vragen

**Alle platforms**

**V**: er wordt in de beveiligingswerkstroom geen gebruikersinterface weergegeven waarin **aangepaste machtigingen** kunnen worden geselecteerd. Waarom?

**A**: dit is een bekend probleem en wordt later verholpen.

**V**: hoe kom ik aan nieuwe organisatietenants om de SDK en voorbeeldtoepassingen uit te proberen?

**A**: als u referenties voor Azure AD RMS-testorganisaties wilt aanvragen, stuurt u een e-mail naar <rmcstbeta@microsoft.com>.

**V**: ik zie in de documentatie geen bespreking van de testhiërarchie. Waarom?

**A**: de nieuwe AD RMS SDK's bevatten geen testhiërarchie. U werkt altijd met de productiehiërarchie.

**V**: In versie 2.1 van de RMS SDK was er een gegenereerd manifest nodig voor elke toepassing waarmee gegevensbeveiliging werd geïmplementeerd. Geldt dit nog steeds voor versie 4.0 en hoger van de SDK?

**A**: nee, er zijn geen manifesten meer nodig voor versie 3.0 en hoger van de Rights Management SDK.

**Android**

**V**: in welke ontwikkelomgevingen is de SDK getest?

**A**: Eclipse Juno met Google API 15 en hoger.

**V**: kan ik de annuleringsmethode cancel() aanroepen vanuit de gebruikersinterfacethread?
**N**: u moet cancel() aanroepen vanuit een andere thread dan een gebruikersinterfacethread, omdat anders de netwerkverbinding wordt afgebroken.

**iOS**

**V**: welke platformen zijn geverifieerd voor SDK-ontwikkeling?

**A**: Xcode 5.0 met iOS 7 en hoger.

**Q**: ik heb een methode cancel() aangeroepen voor een bewerking, maar ik heb nog geen melding gekregen dat de bewerking is voltooid. Waarom?

**A**: niet alle bewerkingen kunnen worden geannuleerd, dus een annuleringsbewerking wordt naar omstandigheden zo goed mogelijk uitgevoerd.

**OS x**

**Q**: Sample App Framework is aangepast voor Xcode 5. Kan ik het ook gebruiken met Xcode 4.6?

**A**: de OS X SDK kan worden gebruikt met Xcode 4.6 en hoger, evenals met OS X 10.8 en hoger.

 

 



<!--HONumber=Jun16_HO4-->


