---
# required metadata

title: Beleidsproblemen oplossen | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Beleidsproblemen oplossen in Microsoft Intune

In dit onderwerp worden enkele problemen beschreven die mogelijk worden veroorzaakt door uw configuratie van het Microsoft Intune-beleid. Ook worden er enkele aanbevelingen gedaan om deze problemen op te lossen.

Als u het probleem niet kunt oplossen met deze informatie, raadpleegt u [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md) voor meer manieren om hulp te krijgen.


## Wordt er beleid toegepast op het apparaat?
**Probleem:** het is onduidelijk of er een bepaald beleid wordt toegepast op een apparaat of een apparaat functioneert niet overeenkomstig een beleid.

Controleer de beleidsgegevens voor elk apparaat om na te gaan hoe het beleid van invloed is op een bepaald apparaat.

In de Intune-beheerconsole vindt u voor elk apparaat een tabblad Beleid onder **Apparaateigenschappen**. Als dat niet het geval is, wordt de inschrijving voor het apparaat waarschijnlijk nog uitgevoerd of wordt er mogelijk geen beleid toegepast. Elk beleid heeft een **Bedoelde waarde** en een **Status**. De beoogde waarde is wat u wilt bereiken bij het toewijzen van het beleid. De status is wat feitelijk wordt bereikt wanneer alle beleidsregels die betrekking hebben op het apparaat samen met de beperkingen en vereisten van de hardware en het besturingssysteem als een geheel worden beschouwd. Mogelijke statussen zijn:

-   **Conform**: het apparaat heeft het beleid ontvangen en rapporteert aan de service dat het voldoet aan de instelling.

-   **Niet van toepassing**: de beleidsinstelling is niet van toepassing. E-mailinstellingen voor iOS-apparaten zijn bijvoorbeeld niet van toepassing op een Android-apparaat.

-   **In behandeling**: het beleid is naar het apparaat verzonden, maar de status is door het apparaat nog niet gerapporteerd aan de service. Zo moet de gebruiker in geval van versleuteling voor Android versleuteling inschakelen, zodat de actie mogelijk in behandeling is.

In de onderstaande schermafbeelding ziet u twee duidelijke voorbeelden:

-   **Eenvoudige wachtwoorden toestaan** is ingesteld op **Ja**, zoals wordt weergegeven in de kolom **Bedoelde waarde** , maar de **Status** is **Niet van toepassing**. Dit komt doordat eenvoudige wachtwoorden niet worden ondersteund voor Android-apparaten.

-   Evengoed wordt het uitgevouwen beleidsitem **E-mailinstellingen voor iOS-apparaten** niet op dit apparaat toegepast, omdat het een Android-apparaat is.

![Intune-apparaatbeleid](../media/Intune-Device-Policy-v.2.jpg)

> [!NOTE]
> Houd er rekening mee dat wanneer er twee sets beleidsregels met verschillende beperkingsniveaus zijn die op hetzelfde apparaat of dezelfde gebruiker van toepassing zijn, in de praktijk het meest beperkende beleid van toepassing is.

## Intervallen voor het vernieuwen en bijwerken van beleid
Beleid wordt regelmatig vernieuwd en bijgewerkt. In het algemeen moet beleid binnen 15 minuten nadat u een wijziging hebt aangebracht, op apparaten worden geregistreerd. Hier vindt u meer informatie over veelvoorkomende intervallen voor het vernieuwen van beleid:

-   **Windows-apparaat dat is ingeschreven voor MDM**: dit wordt dagelijks geactiveerd door een geplande taak om 3:00 uur lokale tijd op het apparaat.

-   **Windows Phone**: het beleid wordt elke 8 uur bijgewerkt. Dit kan worden geforceerd door in de bedrijfsportal onder **Instellingen** voor Vernieuwen te kiezen.

-   **iOS**: het beleid wordt eenmaal per dag met een willekeurig tijdsinterval bijgewerkt. Dit kan ook worden geforceerd door de bedrijfsportal te openen, het apparaat te selecteren en op **Sync** te klikken.

-   **Android**: het beleid wordt eenmaal per dag met een willekeurig tijdsinterval bijgewerkt. Dit kan ook worden geforceerd door de bedrijfsportal te openen, het apparaat te selecteren en op **Sync** te klikken.

## Aan Microsoft Intune-beleid gerelateerde fouten in policyplatform.log
Bij niet-MDM-Windows-apparaten kunnen beleidsfouten in het bestand policyplatform.log het gevolg zijn van niet-standaardinstellingen in Windows Gebruikersaccountbeheer (UAC) op het apparaat. Bepaalde niet-standaard-UAC-instellingen kunnen invloed hebben op Microsoft Intune-clientinstallaties en de beleidsuitvoering.

### UAC-problemen oplossen

1.  Stel de computer buiten gebruik, zoals wordt beschreven in [Apparaten buiten gebruik stellen vanuit Microsoft Intune-beheer](/intune/deploy-use/retire-devices-from-microsoft-intune-management).

2.  Wacht 20 minuten tot de clientsoftware is verwijderd.

    > [!NOTE]
    > Probeer niet om de client te verwijderen vanuit Programma's en onderdelen.

3.  Typ **UAC** in het startmenu om de instellingen voor Gebruikersaccountbeheer te openen.

4.  Verplaats de schuifregelaar voor meldingen naar de standaardinstelling.

## Fout 0x87D1FDE8 voor KNOX-apparaat
**Probleem**: na het maken en implementeren van een Exchange ActiveSync-e-mailprofiel voor Samsung KNOX voor verschillende Android-apparaten wordt door de apparaten de fout **0x87D1FDE8** of de fout **herstelactie is mislukt** gemeld op het tabblad &gt;-beleid van de eigenschappen van het apparaat.

Controleer de configuratie van uw EAS-profiel voor Samsung KNOX en het bronbeleid. De synchronisatieoptie voor Samsung Notes wordt niet meer ondersteund en deze optie moet niet worden geselecteerd in uw profiel. Gun de apparaten voldoende tijd (maximaal 24 uur) om het beleid te verwerken.

## Waarschuwing: het opslaan van de toegangsregels in Exchange is mislukt
**Probleem**: u ontvangt in de beheerconsole de waarschuwing **Het opslaan van de toegangsregels in Exchange is mislukt**  .

Als u beleid hebt gemaakt in de werkruimte voor beleid voor Exchange On-Premises, maar O365 gebruikt, worden de geconfigureerde beleidsinstellingen niet door Intune afgedwongen. Noteer de beleidsbron die in de waarschuwing wordt vermeld.  Verwijder onder de werkruimte voor beleid voor Exchange On-Premises de verouderde regels omdat dit algemene Exchange-regels zijn in Intune voor een on-premises Exchange-toepassing en geen betrekking hebben op O365. Maak vervolgens een nieuw beleid voor O365.

## Fout: kan de waarde niet ophalen van de computer, 0x80041013
Dit kan gebeuren als de tijd op het lokale systeem met meer dan vijf minuten afwijkt. Als de tijd op de lokale computer afwijkt, mislukken beveiligde transacties omdat de tijdstempels ongeldig zijn.

U lost dit probleem op door de lokale systeemtijd zo gelijk mogelijk in te stellen op de internettijd of op de tijd die is ingesteld op de domeincontrollers in het netwerk.

## Het beveiligingsbeleid voor verschillende MDM-apparaten kan niet worden gewijzigd
Bij Windows Phone- en Windows RT-apparaten wordt niet toegestaan dat de beveiligingsbeleidsregels die via MDM of EAS zijn ingesteld, worden teruggebracht naar een lager niveau wanneer u die eenmaal hebt ingesteld. U stelt bijvoorbeeld een **minimumaantal tekens voor het wachtwoord** in op 8 en wilt dit vervolgens terugbrengen tot 4. Het meer beperkende beleid is al toegepast op het apparaat.

Afhankelijk van het apparaatplatform moet u mogelijk het beveiligingsbeleid opnieuw instellen als u de beveiliging naar beneden toe wilt bijstellen.
Veeg bijvoorbeeld in Windows RT op het bureaublad vanaf rechts over het scherm om de **Charms**-balk te openen en klik vervolgens op **Instellingen** &gt; **Configuratiescherm**.  Selecteer de applet **Gebruikersaccounts** .
In het navigatiemenu aan de linkerkant vindt u onderaan een koppeling **Beveiligingsbeleid opnieuw instellen** . Klik hierop en klik vervolgens op **Beleid opnieuw instellen** .
Andere MDM-apparaten, zoals Android, Windows Phone 8.1 en hoger of iOS moeten mogelijk buiten gebruik worden gesteld en weer opnieuw bij de service worden ingeschreven zodat u een minder beperkend beleid kunt toepassen.

## Bij Android-apparaten worden geen wijzigingen in het beveiligingsbeleid geforceerd zonder goedkeuring van de eindgebruiker
Bij Android MDM wordt het niet toegestaan dat door de service beleidswijzigingen op apparaten worden geforceerd, zoals dat op andere platforms gebeurt. Dit wordt veroorzaakt door de Android-functionaliteit en is niet gerelateerd aan de Intune-service. Bij Android-apparaten wordt de eindgebruiker gevraagd om akkoord te gaan via het meldingsvenster van de betreffende beleidswijziging (wachtwoord, versleuteling, enzovoort).  De eindgebruiker moet reageren op de vraag en wanneer deze het beleid heeft geaccepteerd, moet dit worden toegepast.

## Kan geen beleid maken of clients inschrijven als de bedrijfsnaam speciale tekens bevat
**Probleem:** u kunt geen beleid maken of clients inschrijven.

**Oplossing:** verwijder in het [Office 365-beheercentrum](https://portal.office.com/) de speciale tekens uit de bedrijfsnaam en sla de bedrijfsgegevens op.

### Volgende stappen
Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning, zoals wordt beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).


<!--HONumber=May16_HO1-->


