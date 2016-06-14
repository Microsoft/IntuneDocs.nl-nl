---
# required metadata

title: Conflicten tussen GPO-beleid en Intune-beleid oplossen | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Conflicten tussen GPO-beleid (groepsbeleidsobjecten) en Microsoft Intune-beleid oplossen
Intune gebruikt beleidsregels voor het beheren van instellingen op de computers die u beheert. U kunt bijvoorbeeld een beleidsregel gebruiken om instellingen voor de Windows Firewall op computers te beheren. Veel van de Intune-instellingen zijn vergelijkbaar met instellingen die u configureert met Windows-groepsbeleid. De beide methoden kunnen echter van tijd tot tijd met elkaar conflicteren.

Als er conflicten optreden, heeft groepsbeleid op domeinniveau voorrang ten opzichte van Intune-beleid, tenzij de computer niet bij het domein kan worden aangemeld. In dit geval wordt Intune-beleid toegepast op de clientcomputer.

## Wat te doen als u groepsbeleid gebruikt
Controleer of beleidsregels die u toepast, niet worden beheerd door groepsbeleid. Om te conflicten te helpen voorkomen, kunt u gebruikmaken van een of meer van de volgende methoden:

-   Verplaats uw computers voordat u de Intune-client installeert, naar een organisatie-eenheid (OE) van Active Directory waarop geen groepsbeleidsinstellingen worden toegepast. U kunt ook de overname van groepsbeleid blokkeren in organisatie-eenheden met computers die zijn ingeschreven in Intune en waarop u geen groepsbeleidsinstellingen wilt toepassen.

-   Gebruik een WMI-filter of een beveiligingsfilter om groepsbeleidsobjecten te beperken tot computers die niet worden beheerd door Intune. Raadpleeg hieronder het gedeelte [Bestaande groepsbeleidsobjecten filteren om conflicten met het Microsoft Intune-beleid te voorkomen](resolve-gpo-and-microsoft-intune-policy-conflicts.md#BKMK_Filter) voor informatie over en voorbeelden van de werkwijze.

-   Schakel de groepsbeleidsobjecten die met de Intune-beleidsregels conflicteren, uit of verwijder deze.

Zie de documentatie van Windows Server voor meer informatie over Active Directory en Windows-groepsbeleid.

## Bestaande groepsbeleidsobjecten filteren om conflicten met Intune-beleid te voorkomen
Als u groepsbeleidsobjecten (GPO's) hebt geïdentificeerd met instellingen die conflicteren met Intune-beleidsregels, kunt u een van de volgende filtermethoden gebruiken om de desbetreffende groepsbeleidsobjecten te beperken tot computers die niet worden beheerd door Intune.

### WMI-filters gebruiken
WMI-filters passen GPO's selectief toe op computers die voldoen aan de voorwaarden van een query. Om een WMI-filter toe te passen, implementeert u een WMI-klasse-instantie op alle computers in de onderneming voordat u computers bij de Intune-service inschrijft.

#### WMI-filters toepassen op een GPO

1.  Maak een beheerobjectbestand door de volgende gegevens te kopiëren en in een tekstbestand te plakken en dit bestand vervolgens op een geschikte locatie als **WIT.mof** op te slaan. Het bestand bevat de WMI-klasse-instantie die u implementeert op computers die u wilt inschrijven bij de Intune-service.

    ```
    //Beginning of MOF file.
    #pragma classflags("forceupdate")
    #pragma namespace ("\\\\.\\Root")
    instance of __Namespace
    {
       Name = "WindowsIntune";
    };

    #pragma namespace ("\\\\.\\Root\\WindowsIntune")
    [
       Description("This class defines Microsoft Intune common properties")
    ]
    class WindowsIntune_ManagedNode
    {
       [ read, Description("This defines whether Microsoft Intune Policy is enabled"): DisableOverride ToSubClass ]
       boolean WindowsIntunePolicyEnabled;
       [ read, key, Description("This property defines the version." "Example: 1.0"): ToSubClass ]
       string Version;
    };

    instance of WindowsIntune_ManagedNode
    {
       Version = "1.0";
       WindowsIntunePolicyEnabled = 1;
    };
    ```

2.  Gebruik een opstartscript of een groepsbeleid om het bestand te implementeren. Hieronder volgt de implementatieopdracht voor het opstartscript. De WMI-klasse-instantie moet worden geïmplementeerd voordat u clientcomputers inschrijft bij de Intune-service.

    **C:/Windows/System32/Wbem/MOFCOMP &lt;pad naar mof-bestand&gt;\wit.mof**

3.  Voer een van de volgende opdrachten uit om de WMI-filters te maken. Welke opdracht u kiest, is afhankelijk van het gegeven of het GPO dat u wilt filteren, van toepassing is op pc’s die worden beheerd met Intune of op computers die niet worden beheerd met Intune.

    -   Voor GPO's die van toepassing zijn op computers die niet worden beheerd met Intune, gebruikt u het volgende:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    -   Voor GPO's die van toepassing zijn op computers die worden beheerd met Intune, gebruikt u het volgende:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4.  Bewerk het GPO in de groepsbeleidsbeheerconsole om het WMI-filter toe te passen dat u in de vorige stap hebt gemaakt.

    -   Voor GPO's die alleen van toepassing moeten zijn op computers die u wilt beheren met Intune, past u het filter **WindowsIntunePolicyEnabled=1** toe.

    -   Voor GPO's die alleen van toepassing moeten zijn op computers die u niet wilt beheren met Intune, past u het filter **WindowsIntunePolicyEnabled=0** toe.

Zie het blogbericht [Security Filtering, WMI Filtering, and Item-level Targeting in Group Policy Preferences](http://go.microsoft.com/fwlink/?LinkId=177883) (Engelstalig) voor meer informatie over het toepassen van WMI-filters in groepsbeleid.

### Beveiligingsgroepfilters gebruiken
Met groepsbeleid kunt u GPO´s toepassen op alleen de beveiligingsgroepen die u hebt opgegeven in het gebied **Beveiligingsfiltering** van de groepsbeleidsbeheerconsole voor een geselecteerd GPO. Standaard zijn GPO's van toepassing op **geverifieerde gebruikers**.

-   In de module **Active Directory: gebruikers en computers** maakt u een nieuwe beveiligingsgroep met computers en gebruikersaccounts die u niet met behulp van Intune wilt beheren. U kunt de groep bijvoorbeeld de naam **Niet in Microsoft Intune** geven.

-   In de console Groepsbeleidsbeheer op het tabblad **Delegatie** voor het geselecteerde GPO klikt u met de rechtermuisknop op de nieuwe beveiligingsgroep om de relevante machtigingen **Lezen** en **Groepsbeleid toepassen** aan gebruikers en computers in de beveiligingsgroep te delegeren. (Machtigingen voor**Groepsbeleid toepassen** zijn beschikbaar in het dialoogvenster **Geavanceerd** .)

-   Vervolgens past u het nieuwe beveiligingsgroepfilter toe op een geselecteerd GPO en verwijdert u het standaardfilter **Geverifieerde gebruikers** .

De nieuwe beveiligingsgroep moet ingeschreven blijven in de Intune-servicewijzigingen.

### Zie tevens
[Windows-pc's met Microsoft Intune beheren](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


