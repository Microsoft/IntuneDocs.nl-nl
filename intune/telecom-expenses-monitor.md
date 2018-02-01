---
title: Een Telecom Expense Management-service instellen
titleSuffix: Azure portal
description: Configureer de Telecom Expense Management-service van Saaswedo voor integratie met Intune.
keywords: Saaswedo
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e9b0b22dc3831cbb14ab876b5f4e58f82cf53abc
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="set-up-a-telecom-expense-management-service-in-intune"></a>Een Telecom Expense Management-service instellen in Intune
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met Intune kunt u telecomuitgaven van gegevensgebruik op mobiele apparaten in bedrijfseigendom beheren. Hiervoor is Intune geïntegreerd met de Telecom Expense Management-oplossing Datalert van Saaswedo, een extern bedrijf dat software ontwikkelt. Datalert is realtime Telecom Expense Management-software waarmee u telecomgegevensgebruik kunt beheren en kostbare en onverwachte gegevens- en roamingoverschrijdingen voor uw door Intune beheerde apparaten kunt voorkomen.

Doordat Datalert in Intune is geïntegreerd, kunt u centraal gebruikslimieten instellen, controleren en afdwingen voor roaming- en binnenlandse gegevens met geautomatiseerde waarschuwingen wanneer de limieten de gedefinieerde drempelwaarden overschrijden. U kunt de service configureren om verschillende acties op afzonderlijke gebruikers of groepen eindgebruikers toe te passen, waaronder het uitschakelen van roaming, wanneer gebruikers de drempelwaarde overschrijden. Vanuit de Datalert-beheerconsole zijn rapporten over het gegevensgebruik en met controlegegevens beschikbaar.

Het volgende diagram laat zien hoe Intune is geïntegreerd met Datalert.

  ![Diagram van Intune en Datalert-integratie](./media/tem-datalert-intune-solution-diagram.png)

Voordat u de Datalert-service met Intune kunt gebruiken, moet u instellingen configureren in de Datalert-console en in Intune. De verbinding moet zijn ingeschakeld voor de Datalert-service en voor Intune. Als de Datalert-kant van de verbinding is ingeschakeld maar de Intune-kant nog niet, ontvangt Intune de communicatie maar wordt deze genegeerd.

## <a name="supported-platforms"></a>Ondersteunde platforms

- Samsung Knox
- iOS 8.0 en hoger

## <a name="prerequisites"></a>Vereisten

- Een abonnement op Microsoft Intune en toegang tot Azure Portal.
- Een abonnement op de Telecom Expense Management-service Datalert

## <a name="list-of-telecom-expense-management-providers"></a>Lijst met Telecom Expense Management-providers

Intune kan momenteel worden geïntegreerd met de volgende Telecom Expense Management-providers:

[Telecom Expense Management-service Datalert van Saaswedo](http://www.datalert.biz/)

## <a name="deploy-the-intune-and-datalert-integrated-solution"></a>Implementeer de geïntegreerde Intune en Datalert-oplossing

Voordat u begint, moet u ervoor zorgen dat u al een Intune en een DatalertTelecom Expense Management-service-abonnement hebt.

### <a name="step-1-connect-the-datalert-service-to-microsoft-intune"></a>Stap 1: maak verbinding tussen de Datalert-service en Microsoft Intune

1. Meld u aan bij de Datalert-beheerconsole met uw beheerdersreferenties.

2. In de Datalert-beheerconsole gaat u naar het tabblad **Instellingen** en van daaruit naar **MDM-configuratie**.

3. Selecteer **Blokkering opheffen** om de instellingen op de pagina te kunnen invoeren.

4. Kies de optie **Server-MDM** bij **Microsoft Intune**.

5. Voer uw Azure-tenant-ID in bij **Azure AD-domein** en selecteer vervolgens de knop **Verbinding**.

    Als u **Verbinding** selecteert, controleert de Datalert-service bij Intune of er geen bestaande Datalert-verbindingen met Intune bestaan. Na enkele seconden verschijnt een Microsoft-aanmeldingspagina gevolgd door de Azure-verificatie voor Datalert.

6. Selecteer **Accepteren** op de Microsoft-verificatiepagina. U wordt doorgestuurd naar de bedankpagina van Datalert, die na enkele seconden wordt gesloten. Datalert valideert de verbinding en er wordt een groen vinkje weergegeven naast een lijst met items die is gevalideerd. Als de validatie mislukt, ziet u een bericht in rood. Als dit gebeurt, neemt u contact op met de Datalert-ondersteuning voor hulp.

    De volgende schermafbeelding toont de groene vinkjes die u kunt verwachten als de verbinding is geslaagd.

  ![Datalert-pagina die geslaagde verbinding toont](./media/tem-mdm-configuration-mdm-server-page.png)

### <a name="step-2-check-that-the-telecom-expense-management-feature-is-active-in-intune"></a>Stap 2: controleer of de functie Telecom Expense Management actief is in Intune

Nadat u stap 1 hebt voltooid, wordt de verbinding automatisch ingeschakeld en wordt de status **Actief** weergegeven in de Azure-portal. Deze stappen laten zien hoe u controleert op de status **Actief**.

1. Meld u aan bij Azure Portal.

2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.

3. Kies op de blade **Intune** de optie **Apparaatconfiguratie**.

4. Ga naar de blade **Apparaatconfiguratie** en kies **Instellen** > **Telecom Expense Management**.

   Zoek naar de verbindingsstatus **Actief**bovenaan de pagina.

  ![Azure-portal met Datalert-verbindingsstatus Actief](./media/tem-azure-portal-enable-service.png)

### <a name="step-3-deploy-the-datalert-app-to-corporate-enrolled-devices"></a>Stap 3: de app Datalert voor zakelijke geregistreerde apparaten implementeren

Om ervoor te zorgen dat alleen gegevensgebruik wordt verzameld van lijnen in bedrijfseigendom, moet u in Intune categorieën voor apparaten maken en vervolgens de app Datalert alleen richten op zakelijke telefoons. Volg de stappen in de volgende subsecties.

#### <a name="define-device-categories-and-device-groups-mapped-to-the-categories"></a>Categorieën voor apparaten en apparaatgroepen die zijn toegewezen aan de categorieën definiëren

Afhankelijk van de behoeften van uw organisatie moet u ten minste twee categorieën voor apparaten maken (bijvoorbeeld zakelijk en persoonlijk), en voor elke categorie dynamische apparaatgroepen maken. U kunt meer categorieën voor uw organisatie maken, indien nodig.

Deze categorieën worden weergegeven aan gebruikers tijdens de inschrijving. Afhankelijk van welke categorie de gebruiker kiest, wordt het geregistreerde apparaat verplaatst naar de overeenkomstige apparaatgroep. Zie [Apparaten toewijzen aan groepen](device-group-mapping.md) voor instructies over het maken van de categorieën voor apparaten.

  ![Schermafbeelding van het tabblad Een beleid toevoegen](./media/tem-dynamic-membership-rules.png)

#### <a name="create-the-datalert-app-in-intune"></a>De app Datalert in Intune maken

Volg deze stappen om de app Datalert in Intune te maken voor elk platform. In de volgende stappen wordt iOS als voorbeeld gebruikt.

1. Kies op de blade **Intune** van Azure Portal **Mobiele apps**.

2. Kies op de blade **Mobile apps** Achterenvolgens **Beheren** > **Apps**.

3. Selecteer **Toevoegen** om een app toe te voegen.

4. Selecteer het type app. Voor iOS selecteert u bijvoorbeeld **iOS-App Store**.

5. In **Zoek in de App Store**, zoekt u de app Datalert door **Datalert** in het zoekvenster in te voeren.

6. Selecteer de app **Datalert** en dan **OK**.

  ![Schermafbeelding van het tabblad Een beleid toevoegen](./media/tem-select-app-from-apple-app-store.png)

7. Voltooi de resterende stappen om een app voor iOS te maken.

  ![Schermafbeelding van het tabblad Een beleid toevoegen](./media/tem-steps-to-create-the-app.png)

#### <a name="assign-the-datalert-app-to-the-corporate-device-group"></a>De app Datalert aan de groep bedrijfsapparaten toewijzen

1. Selecteer de iOS Datalert-app die u in de vorige stap hebt gemaakt.

2. Ga op de blade **Apps** naar **Toewijzingen** > **beheren**.

3. Kies **Groepen selecteren** en volg de stappen om de groep bedrijfsapparaten te selecteren.

4. Kies of u de installatie van de app verplicht of optioneel wilt maken voor de groep. De volgende voorbeeldschermafbeelding toont de verplichte installatie, wat betekent dat gebruikers de installatie van de Datalert-app moeten installeren na het registreren van hun apparaat.

  ![Schermafbeelding van het tabblad Een beleid toevoegen](./media/tem-assign-datalert-app-to-device-group.png)

### <a name="step-4-add-corporate-paid-phone-lines-to-the-datalert-console"></a>Stap 4: zakelijk betaalde telefoonlijnen aan de Datalert-console toevoegen

U hebt nu de Intune- en Datalert-services geconfigureerd om met elkaar te communiceren. Nu moet u uw zakelijk betaalde telefoonlijnen in de Datalert-console toevoegen en drempelwaarden en acties voor schendingen van mobiel gebruik of roaming definiëren. U kunt zakelijk betaalde telefoonlijnen handmatig aan de Datalert-console toevoegen of de lijnen automatisch laten toevoegen nadat het apparaat is geregistreerd bij Intune.

Om deze items in te stellen, gaat u naar de pagina [Datalert setup for Microsoft Intune](http://www.datalert.fr/microsoft-intune/intune-setup) (http://www.datalert.fr/microsoft-intune/intune-setup) en volgt u de stappen in de setup-wizard in het tabblad **instellingen**.

  ![Schermafbeelding van het tabblad Een beleid toevoegen](./media/tem-add-phone-lines-to-datalert-console.png)


De Datalert-service is nu actief. Er wordt begonnen met het controleren van het gegevensgebruik en het uitschakelen van mobiele en roaminggegevens op apparaten die de geconfigureerde gebruikslimieten overschrijden.

## <a name="client-enrollment-experience"></a>Clientregistratie
Voor de clientregistratie ziet u de volgende onderwerpen:
-   [Uw iOS-apparaat registreren bij Telecom Expense Management](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-ios)
-   [Uw Android-apparaat registreren bij Telecom Expense Management](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-android)

## <a name="turning-off-the-datalert-service"></a>De Datalert-service uitschakelen

Het uitschakelen van de Datalert-service in Azure Portal leidt tot het volgende:

- alle acties die zijn toegepast op apparaten als gevolg van eerdere schendingen van de gebruikslimieten, worden ongedaan gemaakt.
- gebruikers zijn niet meer geblokkeerd voor gegevenstoegang en roaming.
- Intune ontvangt nog wel de signalen die afkomstig zijn van de service, maar deze worden genegeerd.

**De service uitschakelen**

1. Selecteer op de blade **Telecom Expense Management** in Azure Portal **Uitschakelen**.

2. Selecteer **Opslaan**.

## <a name="viewing-data-usage-and-roaming-reports"></a>Rapporten over gegevensgebruik en roaming weergeven

Op dit moment zijn rapporten over gegevensgebruik alleen beschikbaar in de Datalert-beheerconsole van Saaswedo.

De instructies die uw eindgebruikers volgen voor het installeren van de Datalert-app worden snel toegevoegd.
