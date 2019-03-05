---
title: Conflicten tussen GPO-beleid en Intune-beleid oplossen
titlesuffix: Microsoft Intune
description: Informatie over het oplossen van conflicten tussen het groepsbeleid en de beleidsregels voor de Intune-configuratie.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: eeed868d0b612b6e9bd1db290fdd71ed39e54926
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57233982"
---
# <a name="resolve-group-policy-objects-gpo-and-microsoft-intune-policy-conflicts"></a>Conflicten tussen GPO-beleid (groepsbeleidsobjecten) en Microsoft Intune-beleid oplossen

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Intune maakt gebruik van beleidsregels voor het beheren van instellingen op Windows-pc’s. U kunt bijvoorbeeld een beleidsregel gebruiken om instellingen voor de Windows Firewall op pc’s te beheren. Veel Intune-instellingen zijn vergelijkbaar met instellingen die u configureert met Windows-groepsbeleid. De twee methoden kunnen echter van tijd tot tijd met elkaar conflicteren.

Wanneer er conflicten optreden, heeft groepsbeleid op domeinniveau voorrang ten opzichte van Intune-beleid, tenzij de pc niet bij het domein kan worden aangemeld. In dit geval wordt Intune-beleid toegepast op de client-pc.

## <a name="what-to-do-if-you-are-using-group-policy"></a>Wat te doen als u groepsbeleid gebruikt
Zorg dat door u toegepaste beleidsregels niet worden beheerd door groepsbeleid. Om conflicten te helpen voorkomen, kunt u gebruikmaken van een of meer van de volgende methoden:

-   Verplaats voordat u de Intune-client installeert uw pc’s naar een organisatie-eenheid (OE) van Active Directory waarop geen groepsbeleidsinstellingen worden toegepast. U kunt ook de overname van groepsbeleid blokkeren in organisatie-eenheden met pc’s die zijn geregistreerd bij Intune en waarop u geen groepsbeleidsinstellingen wilt toepassen.

-   Gebruik een beveiligingsgroepfilter om groepsbeleidsobjecten te beperken tot uitsluitend pc’s die niet worden beheerd door Intune.

-   Schakel de groepsbeleidsobjecten die met de Intune-beleidsregels conflicteren, uit of verwijder deze.

Zie de documentatie van Windows Server voor meer informatie over Active Directory en Windows-groepsbeleid.

## <a name="how-to-filter-existing-gpos-to-avoid-conflicts-with-intune-policy"></a>Bestaande groepsbeleidsobjecten filteren om conflicten met Intune-beleid te voorkomen
Als u hebt vastgesteld dat bepaalde groepsbeleidsobjecten (GPO's) instellingen bevatten die in strijd zijn met Intune-beleidsregels, kunt u beveiligingsgroepfilters gebruiken om die groepsbeleidsobjecten te beperken tot pc’s die niet worden beheerd door Intune.

<!--- ### Use WMI filters
WMI filters selectively apply GPOs to computers that satisfy the conditions of a query. To apply a WMI filter, deploy a WMI class instance to all PCs in the enterprise before you enroll any PCs in the Intune service.

#### To apply WMI filters to a GPO

1.  Create a management object file by copying and pasting the following into a text file, and then saving it to a convenient location as **WIT.mof**. The file contains the WMI class instance that you deploy to PCs that you want to enroll in the Intune service.

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

2.  Use either a startup script or Group Policy to deploy the file. The following is the deployment command for the startup script. The WMI class instance must be deployed before you enroll client PCs in the Intune service.

    **C:/Windows/System32/Wbem/MOFCOMP &lt;path to MOF file&gt;\wit.mof**

3.  Run either of the following commands to create the WMI filters, depending on whether the GPO you want to filter applies to PCs that are managed by using Intune or to PCs that are not managed by using Intune.

    -   For GPOs that apply to PCs that are not managed by using Intune, use the following:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    -   For GPOs that apply to PCs that are managed by Intune, use the following:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4.  Edit the GPO in the Group Policy Management console to apply the WMI filter that you created in the previous step.

    -   For GPOs that should apply only to PCs that you want to manage by using Intune, apply the filter **WindowsIntunePolicyEnabled=1**.

    -   For GPOs that should apply only to PCs that you do not want to manage by using Intune, apply the filter **WindowsIntunePolicyEnabled=0**.

For more information about how to apply WMI filters in Group Policy, see the blog post [Security Filtering, WMI Filtering, and Item-level Targeting in Group Policy Preferences](http://go.microsoft.com/fwlink/?LinkId=177883). --->


U kunt GPO's alleen toepassen op de beveiligingsgroepen die u hebt opgegeven in het gebied **Beveiligingsfiltering** van de groepsbeleidsbeheerconsole voor een geselecteerd GPO. Standaard zijn GPO's van toepassing op *geverifieerde gebruikers*.

-   In de module **Active Directory: gebruikers en computers** maakt u een nieuwe beveiligingsgroep met computers en gebruikersaccounts die u niet wilt beheren met behulp van Intune. U kunt de groep bijvoorbeeld de naam *Niet in Microsoft Intune* geven.

-   In de console Groepsbeleidsbeheer op het tabblad **Delegatie** voor het geselecteerde GPO klikt u met de rechtermuisknop op de nieuwe beveiligingsgroep om de relevante machtigingen **Lezen** en **Groepsbeleid toepassen** aan gebruikers en computers in de beveiligingsgroep te delegeren. (Machtigingen voor**Groepsbeleid toepassen** zijn beschikbaar in het dialoogvenster **Geavanceerd** .)

-   Vervolgens past u het nieuwe beveiligingsgroepfilter toe op een geselecteerd GPO en verwijdert u het standaardfilter **Geverifieerde gebruikers** .

De nieuwe beveiligingsgroep moet ingeschreven blijven in de Intune-servicewijzigingen.

### <a name="see-also"></a>Zie tevens
[Windows-pc's met Microsoft Intune beheren](manage-windows-pcs-with-microsoft-intune.md)
