---
# required metadata

title: Azure RMS configureren voor ADAL-verificatie | Azure RMS
description: Bevat de stappen voor het configureren van Azure ADAL-verificatie
keywords: authentication, RMS, ADAL
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: f89f59b7-33d1-4ab3-bb64-1e9bda269935

# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Azure RMS configureren voor ADAL-verificatie

Dit onderwerp bevat informatie over het configureren van Azure ADAL-configuratie.

## Azure Authentication installeren

U hebt het volgende nodig:

- Een [abonnement voor Microsoft Azure](https://azure.microsoft.com/en-us/) (een gratis proefversie is voldoende). Zie [How users sing up for RMS for individuals](../understand-explore/rms-for-individuals-user-sign-up.md) voor meer informatie
- Een abonnement voor Microsoft Azure Rights Management (een gratis account voor [RMS voor personen](https://technet.microsoft.com/en-us/library/dn592127.aspx) is voldoende).

> [!NOTE] Vraag uw IT-beheerder of u beschikt over een abonnement voor Microsoft Azure Rights Management en laat uw IT-beheerder de volgende stappen uitvoeren. Als uw organisatie geen abonnement heeft, vraagt u uw IT-beheerder om er een te maken. Daarnaast moet uw IT-beheerder moet zich abonneren op een *werk- of schoolaccount*, in plaats van een *Microsoft-account* (bijvoorbeeld Hotmail).

Na het aanmelden voor Microsoft Azure:

- Meld u met een account met beheerdersbevoegdheden aan bij de [Azure-beheerportal](https://manage.windowsazure.com) voor uw organisatie.

![Azure-aanmelding](../media/AzurePortalLogin.png)

- Blader omlaag naar de toepassing **Active Directory** aan de linkerkant van de portal.

![Selecteer Active Directory](../media/AzureADPick.png)

- Als u nog geen map hebt gemaakt, kiest u de knop **Nieuw** in de linkeronderhoek van de portal.

![Selecteer NIEUW](../media/AzureNewBtn.png)

- Selecteer het tabblad **Rights Management** en zorg ervoor dat de **Rights Management-status** **Actief**, **Onbekend** of **Niet geautoriseerd** is. Als de status **Inactief** is, kiest u de knop **Activeren** middenonder in de portal en bevestigt u uw selectie.

![Kies ACTIVEREN](../media/RMTab.png)

- Maak nu een nieuwe *Eigen toepassing* in uw directory door via Toepassingen uw directory te kiezen.

![Selecteer TOEPASSINGEN](../media/CreateNativeApp.png)

- Kies vervolgens de knop **Toevoegen** middenonder in de portal.

![Selecteer TOEVOEGEN](../media/AddAppBtn.png)

- Kies bij de prompt **Add an application my organization is developing** (Een toepassing toevoegen die door mijn organisatie wordt ontwikkeld).

![Add an application my organization is developing (Een toepassing toevoegen die door mijn organisatie wordt ontwikkeld) selecteren](../media/AddAnAppPick.png)

- Geef uw toepassing een naam door **EIGEN CLIENTTOEPASSING** te selecteren en de knop **Volgende** te kiezen.

![Uw app een naam geven](../media/TellUsInput.png)

- Voeg een omleidings-URI toe en klik op volgende.
  De omleidings-URI moet een geldige URI zijn en moet uniek zijn voor uw directory. U kunt bijvoorbeeld het volgende gebruiken: `com.mycompany.myapplication://authorize`.

![Omleidings-URI toevoegen](../media/RedirectURI.png)

- Selecteer uw toepassing in de map en kies **CONFIGUREREN**.

![Kies CONFIGUREREN](../media/ConfigYourApp.png)

>[!NOTE] Kopieer de **CLIENT-ID** en **OMLEIDINGS-URI** en sla deze op voor toekomstig gebruik tijdens het configureren van de RMS-client.

- Blader naar beneden in uw toepassing-instellingen en kies de knop **Toepassing toevoegen** onder **Machtigingen voor andere toepassingen**.

>[!NOTE] De **overgedragen machtigingen** die zichtbaar zijn voor Windows Azure Active Directory zijn standaard correct: slechts één optie moet geselecteerd zijn en deze optie is **Aanmelden en gebruikersprofiel lezen**.

![Toepassing toevoegen selecteren](../media/PermissionsToOtherBtn.png)

- Voeg nu deze GUID `00000012-0000-0000-c000-000000000000` toe aan het invoervak **BEGINNEN MET** en klik op de knop Controleren.

![GUID toevoegen](../media/AddGUID.png)

- Kies de plusknop (+) naast **Microsoft Rights Management**.

![Selecteer de knop +.](../media/ChoosePlusBtn.png)

- Kies nu het vinkje in de linkeronderhoek van het dialoogvenster.

![Het vinkje kiezen](../media/ChooseCheck.png)

- U kunt nu een afhankelijkheid aan uw toepassing toevoegen voor Azure RMS. U kunt de afhankelijkheid als volgt toevoegen: selecteert het nieuwe item **Microsoft Rights Management Services** onder **Machtigingen voor andere toepassingen** en kies selectievakje **Beveiligde inhoud maken en openen voor gebruikers** onder de keuzelijst **Gedelegeerde machtigingen:**.

![Machtigingen instellen](../media/AddDependency.png)

- Sla uw toepassing op om de wijzigingen vast te leggen. Kies hiervoor het pictogram **Opslaan** middenonder in de portal.

![OPSLAAN selecteren](../media/SaveApplication.png)


<!--HONumber=Jun16_HO2-->


