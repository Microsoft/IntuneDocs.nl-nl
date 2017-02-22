---
title: Een Telecom Expense Management-service instellen | Intune Azure Preview | | Microsoft Docs
description: 'Intune Azure Preview: de Telecom Expense Management-service van Saaswedo configureren voor integratie met Intune.'
keywords: Saaswedo
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 915d61344a3c1d388305dd51b1e2463bd2e32770
ms.openlocfilehash: 8d94fec099e1dc8918077062fb73b94a5973ea96

---

# <a name="set-up-a-telecom-expense-management-service-in-intune-azure-preview"></a>Een Telecom Expense Management-service instellen in Intune Azure Preview
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune is geïntegreerd met de Telecom Expense Management-oplossing Datalert van Saaswedo, een extern bedrijf dat software ontwikkelt. Datalert is realtime Telecom Expense Management-software waarmee u telecomgegevensgebruik kunt beheren en kostbare en onverwachte gegevens- en roamingoverschrijdingen voor uw door Intune beheerde apparaten kunt voorkomen. Doordat Datalert in Intune is geïntegreerd, kunt u centraal gebruikslimieten instellen, controleren en afdwingen voor roaming- en binnenlandse gegevens met geautomatiseerde waarschuwingen wanneer de limieten de gedefinieerde drempelwaarden overschrijden. U kunt de service configureren om verschillende acties op afzonderlijke gebruikers of groepen eindgebruikers toe te passen, waaronder het uitschakelen van roaming, wanneer gebruikers de drempelwaarde overschrijden. Vanuit de Datalert-beheerconsole zijn rapporten over het gegevensgebruik en met controlegegevens beschikbaar.

Voordat u de Datalert-service met Intune kunt gebruiken, moet u instellingen configureren in de Datalert-console en in Intune. De verbinding moet zijn ingeschakeld voor de Datalert-service en voor Intune. Als de Datalert-kant van de verbinding is ingeschakeld maar de Intune-kant nog niet, ontvangt Intune de communicatie maar wordt deze genegeerd.

>[!NOTE]
>Als u deze functie in uw proeftenant wilt inschakelen, [neemt u contact op met Microsoft-ondersteuning](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) voor activering en met Datalert-ondersteuning voor de vereiste softwarelicenties.

## <a name="supported-platforms"></a>Ondersteunde platforms

- Samsung Knox
- iOS 8.0 en hoger

## <a name="prerequisites"></a>Vereisten

- Een abonnement op Microsoft Intune
- Een abonnement op de Telecom Expense Management-service Datalert

## <a name="list-of-telecom-expense-management-providers"></a>Lijst met Telecom Expense Management-providers

Intune kan momenteel worden geïntegreerd met de volgende Telecom Expense Management-providers:

[Telecom Expense Management-service Datalert van Saaswedo](http://www.datalert.biz/)

## <a name="configure-intune-to-work-with-the-datalert-service"></a>Intune configureren om met de Datalert-service te werken

 

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Apparaten configureren** op de blade **Intune**.
2. Kies **Instellen** > **Telecom Expense Management** op de blade **Apparaatconfiguratie**.
2. Selecteer onder **Telecom-onkostenbeheer** de optie **Verbindingsstatus**.

3. Selecteer **Lijst met TEM-serviceproviders** en selecteer vervolgens uw provider in de onderstaande lijst. Er wordt een pagina speciaal voor uw provider geopend. Voor Saaswedo wordt de Datalert-pagina geopend. U moet met Saaswedo Datalert werken om een abonnement te kopen.

4. In de **Datalert**-beheerconsole:

    a. Ga naar het tabblad **Instellingen** en ga vervolgens naar de sectie **MDM-configuratie**.

    b. Selecteer **Ontgrendelen** om de instellingen op de pagina te kunnen invoeren.

    c. Kies voor **Server-MDM** de optie **Microsoft Intune**.

    d. Voer voor **Tenant-id** uw tenant-id van Intune in en selecteer de knop **Verbinding**. Als u **Verbinding** selecteert, controleert de Datalert-service bij Intune of er geen bestaande Datalert-verbindingen met Intune bestaan. Na enkele seconden verschijnt een Microsoft-aanmeldingspagina gevolgd door de Azure-verificatie voor Datalert.

    e. Selecteer op de Microsoft-verificatiepagina **Accepteren**. U wordt doorgestuurd naar de bedankpagina van Datalert die na enkele seconden wordt gesloten. Datalert valideert de verbinding en er wordt een groen vinkje weergegeven naast een lijst met items die is gevalideerd. Als de validatie mislukt, ziet u een bericht in rood. Als dit gebeurt, neemt u contact op met de Datalert-ondersteuning voor hulp.

5. Wacht enkele minuten en ga vervolgens naar Azure Portal. Controleer hier of voor de verbindingsstatus **Actief** wordt weergegeven. 

    >[!NOTE]
    >Als u deze functie in uw proeftenant wilt inschakelen, neemt u [contact op met Microsoft-ondersteuning](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

6. Ga terug naar de Datalert-beheerconsole en configureer uw gegevenslijnen:

    a. Ga naar het tabblad **Instellingen**.

    b. Ga naar de wizard **Setup** en volg de stappen in de wizard.



De Datalert-service is nu actief. Er wordt begonnen met het controleren van het gegevensgebruik en het uitschakelen van mobiele en roaminggegevens op apparaten die de geconfigureerde gebruikslimieten overschrijden.

## <a name="turning-off-the-datalert-service"></a>De Datalert-service uitschakelen

Het uitschakelen van de Datalert-service in Azure Portal leidt tot het volgende:

- Alle acties die zijn toegepast op apparaten als gevolg van eerdere schendingen van de gebruikslimieten, worden ongedaan gemaakt.
- Gebruikers zijn niet meer geblokkeerd voor gegevenstoegang en roaming.
- Intune ontvangt nog wel de signalen die afkomstig zijn van de service, maar deze worden genegeerd.

**De service uitschakelen**

1. Selecteer op de blade **Telecom-onkostenbeheer** in Azure Portal **Uitschakelen**.

2. Selecteer **Opslaan**.

## <a name="viewing-data-usage-and-roaming-reports"></a>Rapporten over gegevensgebruik en roaming weergeven

Op dit moment zijn rapporten over gegevensgebruik alleen beschikbaar in de Datalert-beheerconsole van Saaswedo.



<!--HONumber=Feb17_HO2-->


