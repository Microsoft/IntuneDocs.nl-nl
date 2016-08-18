---
title: Veelgestelde vragen over de evaluatieversie van Azure Information Protection | Azure Information Protection
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 08/10/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 4b595b6a-7eb0-4438-b49a-686431f95ddd
ms.reviewer: adhall
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d17bacf8e148622db0e2393f40d3fd37c8f086eb
ms.openlocfilehash: c61e299cac50069afc119d37fd461cda88a2afd3


---

# Veelgestelde vragen over de evaluatieversie van Azure Information Protection

>*Van toepassing op: Azure Information Protection preview*

**[ Deze informatie is voorlopig en kan worden gewijzigd. ]**

Hebt u een vraag over de preview-versie van Azure Information Protection?  U vindt hier wellicht het antwoord. 

Deze lijst wordt geregeld bijgewerkt en sommige informatie wordt verplaatst naar de hoofddocumentatie. In dit artikel nemen we nieuwe vragen op die klanten ons stellen. 

## Wat kan ik met de preview-versie van Azure Information Protection doen en wat zijn de beperkingen momenteel?

Met deze preview-versie wordt een Information Protection-balk aan Microsoft Office-toepassingen toegevoegd waarmee u classificatielabels die aan gegevens zijn toegewezen kunt bekijken en wijzigen. Classificatie kan handmatig worden uitgevoerd, als een aanbeveling of automatisch. Voor de classificaties die u opgeeft kunnen de gegevens worden beveiligd door een Azure Rights Management-sjabloon.  

De classificatielabels en het gedrag van de classificaties worden geconfigureerd in Azure Portal. U kunt het standaard ingebouwde beleid gebruiken om Azure Information Protection snel te evalueren, of uw eigen beleid aanmaken. U kunt de kleuren, namen en de volgorde van de classificatielabels wijzigen die zichtbaar zijn voor gebruikers. U kunt ook de knopinfo en visuele markeringen voor de classificatie configureren, zoals de koptekst, voettekst of het watermerk.

Probeer onze zelfstudie om snel te starten om binnen enkele minuten aan de slag te gaan: [Zelfstudie voor snel starten met Azure Information Protection](infoprotect-quick-start-tutorial.md).

Met de preview kunt u het nieuwe **Premium P2-serviceplan**. Sommige geavanceerde functies, zoals automatische en aanbevolen labels, zijn mogelijk niet beschikbaar in uw huidige plan. Zie het volgende blogbericht [Introductie van Enterprise Mobility + Security](https://blogs.technet.microsoft.com/enterprisemobility/2016/07/07/introducing-enterprise-mobility-security/) voor informatie over de verschillende serviceplannen (Azure Information Protection Premium P1 en Azure Information Protection Premium P2).

Deze preview-versie heeft de volgende beperkingen: Bekijk de aankondigingen op de blog [Enterprise Mobility en Security](https://blogs.technet.microsoft.com/enterprisemobility/?product=azure-information-protection) en onze [Yammer-site](https://www.yammer.com/askipteam/#/threads/inGroup?type=in_group&feedId=8652489&view=all) om te controleren wanneer extra functies en mogelijkheden beschikbaar zijn:

- Er is geen centrale logboekregistratie voor de classificaties en labels.

- Labelnamen en knopinfo worden slechts in één taal ondersteund.

- De voorwaarden voor automatische classificatie moeten woordgroepen of patronen zijn.

- Bestanden kunnen niet worden geclassificeerd in Windows Bestandenverkenner.

- Office-apps voor mobiele apparaten (iOS en Android) en Mac-computers en de Office web-apps (Office Online) worden nog niet ondersteund.

- Er is geen integratie met Exchange Online of SharePoint Online.

- De SDK voor partners en ontwikkelaars is niet beschikbaar.

## Welk abonnement heb ik nodig Azure Information Protection uit te proberen?

Voor de preview-versie kunt u elk abonnement gebruiken waarmee u over Azure Rights Management beschikt. Azure Information Protection is beschikbaar in alle regio's. Voor meer informatie over de beschikbare abonnementen en koppelingen naar gratis proefversies raadpleegt u [Azure RMS-vereisten: cloudabonnementen die ondersteuning bieden voor Azure RMS](../get-started/requirements-subscriptions.md).

Als u het Azure Information Protection-beleid in Azure Portal wilt configureren, moet u een abonnement voor Azure hebben. Als u nog geen Azure-abonnement voor uw organisatie hebt, kunt u er een krijgen door u aan te melden voor een gratis proefversie. Ga naar de pagina [Aan de slag met Azure](https://account.windowsazure.com/organization) en volg de instructies.

Eventuele wijzigingen in de vereisten van het abonnement worden aangekondigd op de blog [Enterprise Mobility and Security](https://blogs.technet.microsoft.com/enterprisemobility/?product=azure-information-protection).

## Moet ik een globale beheerder zijn om de preview van Azure Information Protection te kunnen gebruiken?

In de preview-versie kan elke gebruiker die door Azure is geverifieerd het Azure Information Protection-beleid van de tenant voor het classificeren en labelen weergeven en configureren in Azure Portal. Als u echter een label wilt configureren om een Azure Rights Management-sjabloon toe te passen, moet u als globale beheerder zijn aangemeld voor Azure Active Directory.

Als u hebt geselecteerd dat het demobeleid wordt geïnstalleerd als u de [Azure Information Protection-client](https://www.microsoft.com/en-us/download/details.aspx?id=53018) installeert, hoeft u zich niet eens aan te melden bij de portal om deze preview-versie te gebruiken. Het demobeleid installeert lokaal het standaardbeleid voor Azure Information Protection, zodat u documenten en e-mailberichten kunt labelen. U kunt echter geen nieuwe labels maken of toevoegen zonder dat u bij Azure Portal bent aangemeld. 

Als u de documenten en e-mailberichten die u classificeert en van labels voorziet wilt beveiligen en u Azure Rights Management nog niet hebt geactiveerd, hebt u voor het activeringsproces speciale beheerdersmachtigingen nodig. Zie [Moet ik een globale beheerder zijn om Azure RMS te configureren of kan ik delegeren aan andere beheerders?](../get-started/faqs.md#do-you-need-to-be-a-global-admin-to-configure-azure-rms-or-can-i-delegate-to-other-administrators) voor meer informatie.


## Ondersteunt Azure Information Protection lokale en hybride scenario's?

Azure Information Protection is een cloudoplossing. Als u Azure Information Protection voor een hybride scenario wilt implementeren, neemt u contact op met het Information Protection-team via askipteam@microsoft.com.

## Welke clientplatforms en toepassingen worden ondersteund door Azure Information Protection?

Dit wordt beschreven en bijgewerkt in [Vereisten voor Azure Information Protection](requirements-azure-infoprotect.md).


## Hoe krijgen computers informatie over het beleid van Azure Information Protection en hoe vaak wordt deze informatie bijgewerkt?

Telkens wanneer een gebruiker een Office-toepassing opent, controleert de Azure Information Protection-client of er een nieuwere versie van het Azure Information Protection-beleid beschikbaar is. Als er een nieuwere versie is, wordt deze gedownload via een HTTPS-koppeling om de gegevens te beveiligen. 

Als meerdere exemplaren van de Office-toepassing zijn geladen wanneer een nieuw Azure Information Protection-beleid wordt gepubliceerd, moet u alle exemplaren sluiten om de nieuwste versie van het beleid op te halen. Als er bijvoorbeeld twee Word-documenten zijn geopend en u het bijgewerkte Azure Information Protection-beleid in slechts één document wilt testen: sluit beide Word-documenten en open het document dat u wilt gebruiken met het nieuwste beleid opnieuw.

## Waar kunnen bestanden worden opgeslagen om Azure Information Protection te kunnen gebruiken? 

Het maakt niet uit waar de bestanden worden opgeslagen, omdat Azure Information Protection permanente labels en beveiliging toepast op bestanden en e-mailberichten.

## Kan ik alleen nieuwe gegevens classificeren of kan ik bestaande gegevens ook classificeren?

De acties voor het Azure Information Protection-beleid worden ingesteld wanneer documenten worden bewaard en e-mailberichten worden verstuurd, zowel voor nieuwe als bestaande documenten. 

Als u bewaarde bestanden wilt classificeren, opent u de bestanden en bewaart u deze in uw Office-toepassing. 

Op dit moment kunt u niet in bulk bestanden classificeren. U moet elk document afzonderlijk openen en bewaren in de Office-toepassing. 

## Kan ik Azure Information Protection alleen gebruiken voor classificatie, zonder versleutelings- en gebruiksrechten af te dwingen?

Ja. U kunt een Azure Information Protection-beleid configureren dat alleen van toepassing is op een label. We vermoeden dat dit geldt voor de meerderheid van implementatienetwerken waarin u alleen bepaalde documenten of e-mailberichten wilt beveiligen waarvoor speciaal gegevensbeheer is vereist.

## Hoe gaat automatische classificatie in zijn werk?

U kunt in Azure Portal gebruikmaken van vooraf ingestelde patronen, zoals creditcardnummers of burgerservicenummers. U kunt ook een aangepaste tekenreeks of aangepast patroon definiëren als voorwaarde voor automatische classificatie.

Een voorbeeld hiervan vindt u in de [Zelfstudie voor snel starten met Azure Information Protection](infoprotect-quick-start-tutorial.md). 

De nauwkeurigheid van de classificatie is afhankelijk van de configuratie van de classificatieregel, die is gebaseerd op voorwaarden. Op dit moment worden alleen tekstpatronen en reguliere expressies ondersteund. Zie [Voorwaarden voor automatische en aanbevolen classificatie voor Azure Information Protection configureren](configure-policy-classification.md) voor een uitleg van de opties die beschikbaar zijn tijdens de preview, met enkele voorgestelde voorbeelden om te testen. De detectie wordt uitgevoerd als het document wordt opgeslagen of een e-mailbericht wordt verzonden.

We raden u aan dat u begint met de aanbevolen acties voor gebruikers in plaats van met de volledig automatische acties voor de beste gebruikerservaring en om de bedrijfscontinuïteit te waarborgen. Hierdoor hebben uw gebruikers de mogelijkheid om de acties voor labels en beveiliging te accepteren of deze suggesties te overschrijven.   

## Kan Azure Information Protection gebruikers vragen om bestanden zelf te classificeren in plaats van gebruik te maken van automatische classificatie? 

Ja. Met Azure Portal kunt u instellen of u gebruik wilt maken van automatische classificatie of van aanbevelingen aan gebruikers door de optie **Selecteren hoe dit label wordt toegepast: automatisch of aanbevolen aan gebruiker** in te stellen op **Aanbevolen**.

Een voorbeeld hiervan vindt u in de [Zelfstudie voor snel starten met Azure Information Protection](infoprotect-quick-start-tutorial.md).  

## Kan ik afdwingen dat alle documenten worden geclassificeerd?

Ja. Als u gebruikers verplicht om alle bestanden die ze opslaan in Azure Portal te classificeren, stelt u de optie **Alle documenten en e-mailberichten moeten een label hebben** in op **Aan**. 

## Kan ik classificaties uit een bestand verwijderen?

Ja. Om een classificatie uit een bestand te verwijderen, opent u het bestand in de Office-toepassing, klikt u op het pictogram **Label bewerken** in de Information Protection-balk. Vervolgens klikt u op het pictogram **Label verwijderen** en klikt u vervolgens op **OK** om uw actie te bevestigen. 


## Kan ik gebruikers vragen waarom ze het classificatieniveau wijzigen?

Ja. Als u wilt dat gebruikers hun wijzigingen in de classificatie moeten rechtvaardigen, stelt u in Azure Portal de optie **Users must provide justification when lowering the sensitivity level (Gebruikers moeten een reden opgeven wanneer ze het gevoeligheidsniveau verlagen)** in op **Aan**. Wanneer ze dit doen, worden de actie en hun reden hiervoor vastgelegd in hun lokale Windows-gebeurtenislogboek: **Toepassing** > **Microsoft Azure Information Protection**.

## Hoe kan ik inhoud automatisch beveiligen nadat deze is geclassificeerd?

In Azure Portal kunt u een Azure Rights Management-sjabloon selecteren om inhoud automatisch te beveiligen volgens het niveau van de classificatie die u opgeeft.

Een voorbeeld hiervan vindt u in de [Zelfstudie voor snel starten met Azure Information Protection](infoprotect-quick-start-tutorial.md). Zie [Een label configureren om Rights Management-beveiliging toe te passen](configure-policy-protection.md) voor meer informatie.

## Kan een bestand met twee verschillende classificaties worden geclassificeerd?

Indien nodig, kunt u onderliggende labels maken om subcategorieën beter te beschrijven voor een bepaald gevoeligheidslabel. Het hoofdlabel **Geheim** kan bijvoorbeeld onderliggende labels als **Geheim – juridisch** en **Geheim – financiën** bevatten. Vervolgens kunt u andere visuele markeringen voor classificaties en andere Rights Management-sjablonen toepassen op de verschillende onderliggende labels.

Alhoewel u visuele markeringen, beveiliging en voorwaarden op beide niveaus kunt instellen, kunt u voor onderliggende niveaus deze instelling alleen op het onderliggende niveau instellen. Als u dezelfde instellingen op het bovenliggende label en het onderliggende niveau configureert, hebben de instellingen op het onderliggende niveau voorrang.

## Hoe kunnen DLP-oplossingen en andere toepassingen worden geïntegreerd met Azure Information Protection?

Omdat Azure Information Protection gebruikmaakt van permanente metagegevens voor de classificatie met een duidelijk tekstlabel, kan deze informatie worden gelezen door DLP-oplossingen en andere toepassingen. Deze metagegevens worden in bestanden in de aangepaste eigenschappen bewaard. In e-mailberichten wordt deze informatie weergegeven in de koptekst van het bericht.

## Hoe gaat het bijhouden en intrekken van documenten voor Azure Information Protection in zijn werk?

Documenttracking voor bestanden die u classificeert en beveiligt met Azure Information Protection werkt op dezelfde manier als in Azure Rights Management en de RMS-toepassing voor delen. U kunt ook toegang tot de documenttrackingsite krijgen met de Azure Information Protection-client (versie 1.0.233 of hoger): 

- Klik in een Office-toepassing op het tabblad **Start** in de groep **Beveiliging** op **Beveiligen** > **Gebruik bijhouden**. 

Zie [Uw documenten bijhouden en intrekken met gebruik van de RMS-toepassing voor delen](../rms-client/sharing-app-track-revoke.md) voor meer informatie.

## Hoe dwingt Azure Information Protection de beleidsregels af die ik configureer?

Als een document wordt beveiligd door een Azure Rights Management-sjabloon wordt de gebruiker eerst geverifieerd om te controleren of hij rechten heeft voor dit document. Vervolgens wordt het beleid voor gebruiksrecht afgedwongen door de toepassing. 

## Hoe gebruikt Azure Information Protection Azure Active Directory?

Azure Information Protection gebruikt Azure Active Directory voor gebruikersverificatie.

## Kan ik bepalen welke gebruikers Azure Information Protection mogen gebruiken om inhoud te classificeren en te beveiligen?

U kunt beperken welke gebruikers gegevens kunnen classificeren en beveiligen door de distributie van de Azure Information Protection-client te beperken. 

Bestanden en e-mailberichten die door Azure Information Protection zijn geclassificeerd kunnen door elke gebruiker worden gebruikt of bewerkt. Hiervoor hoeft de Azure Information Protection-client niet te zijn geïnstalleerd. 

## Hoe kan ik een probleem melden of feedback voor deze preview verzenden?

Als u een probleem hebt met deze preview-versie, klikt u in uw Office-toepassing op het tabblad **Start** en klikt u in de **Beveiliging**sgroep op **Beveiligen** en vervolgens op **Help en feedback**. Klik in het dialoogvenster **Microsoft Azure Information Protection** op **Feedback verzenden**. Hiermee wordt een e-mail verzonden aan het Information Protection-team en worden logbestanden van uw pc toegevoegd om vast te stellen wat het probleem is. 

Als u vragen of feedback hebt, gebruikt u de [Azure Information Protection Yammer-site](https://www.yammer.com/askipteam/#/threads/inGroup?type=in_group&feedId=8652489&view=all). 

## Wat moet ik doen als ik mijn vraag hier niet vind?

Controleer eerst of uw vraag niet is opgenomen in de [Aankondiging van de Azure Information Protection preview](https://blogs.technet.microsoft.com/enterprisemobility/2016/07/12/azure-information-protection-public-preview-available-now/) op de Enterprise Mobility and Security-blog.

Ga vervolgens naar onze [Yammer-site](https://www.yammer.com/askipteam/#/threads/inGroup?type=in_group&feedId=8652489&view=all) om te zien of iemand anders deze vraag al heeft gesteld. Als dat niet het geval is, kunt u uw vraag daar plaatsen.







<!--HONumber=Aug16_HO2-->


