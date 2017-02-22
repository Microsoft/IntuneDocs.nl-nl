---
title: Apple Configurator-serienummers toevoegen| Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u met Apple Configurator serienummers kunt toevoegen aan iOS-apparaten die het eigendom zijn van de onderneming.'
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d408aa38-7d1e-40df-9067-246e53f6e26f
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 65a6b2e22359bdcb9b0c15a84c6b3586dafe4d6c
ms.openlocfilehash: 71d29a245f8f900a7427528167bae0b52565d42b


---

# <a name="add-apple-configurator-serial-numbers"></a>Apple Configurator-serienummers toevoegen 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Volg deze stappen om serienummers toe te voegen aan Intune als u [door het bedrijf beheerde iOS-apparaten met Apple Configurator wilt inschrijven met de configuratieassistent] ((enroll-ios-devices-with-apple-configurator-and-setup-assistant.md). U kunt serienummers één voor één toevoegen of een bestand met door komma's gescheiden waarden (csv) met serienummers uploaden. Nadat u serienummers hebt toegevoegd, kunt u hieraan een profiel toewijzen. Het profiel bevat specifieke beheerinstellingen die u op apparaten wilt toepassen. 

Andere methoden voor het registreren van iOS-apparaten worden beschreven in [Choose how to enroll iOS devices in Intune](choose-ios-enrollment-method.md) (Kiezen hoe iOS-apparaten worden geregistreerd in Intune).

**Apple Configurator-serienummers toevoegen aan Intune**

1. Maak een lijst met twee kolommen met door komma's gescheiden waarden (.csv) zonder koptekst. Voeg de IMEI-id in de linkerkolom toe en de details in de rechterkolom. Een lijst kan momenteel maximaal 500 rijen bevatten. In een teksteditor ziet de .csv-lijst er ongeveer zo uit:

    F7TLWCLBX196, apparaatdetails</br>
   DLXQPCWVGHMJ, apparaatdetails

2. Kies in Azure Portal **Meer services**, voer **Intune** in het tekstvak in en kies **Overige** > **Intune**.

3.  Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Apple-inschrijving**.

4. Selecteer **Apple Configurator-serienummers** onder **Instellingen van de inschrijving van Apple Configurator beheren**.

5. Selecteer **Toevoegen** op de blade **Apple Configurator-serienummers**.

6. Selecteer op de blade **Serienummers toevoegen** een profiel dat u wilt toepassen op de serienummers die u importeert. Als u een bestand met nieuwe details importeert die de bestaande details overschrijven, selecteert u Details voor bestaande id's overschrijven zodat de nieuwe details de bestaande vervangen.

7. Navigeer naar het .csv-bestand met serienummers en selecteer **Toevoegen**.

## <a name="assign-a-profile-to-specific-serial-numbers"></a>Een profiel toewijzen aan specifieke serienummers

Met Intune kunt u profielen toewijzen vanaf twee verschillende plaatsen in Azure Portal. U kunt de onderstaande stappen gebruiken of u kunt profielen toewijzen vanaf de blade Apple Configurator-inschrijvingsprofielen waar u het profiel maakt (zie [iOS-apparaten inschrijven met Apple Configurator met behulp van Configuratieassistent](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md)). Aan de hand van de onderstaande stappen kunt u het profiel alleen toewijzen als u het profiel al hebt gemaakt.

1. Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Apple-inschrijving**.

2. Selecteer op de blade **Apple Configurator-serienummers** de seriële nummers waaraan u een profiel wilt toewijzen en selecteer vervolgens **Profiel toewijzen**.

3. Selecteer op de blade **Profiel toewijzen** het profiel dat u wilt toewijzen en selecteer vervolgens **Toewijzen**.

## <a name="delete-serial-numbers"></a>Serienummers verwijderen
U kunt serienummers verwijderen die u eerder hebt geïmporteerd. U kunt serienummers alleen verwijderen als het apparaat eerst wordt uitgeschreven. Als u een serienummer verwijdert, kunt u Apple Configurator niet gebruiken via Configuratieassistent tenzij u het serienummer opnieuw toevoegt.

## <a name="view-the-state-of-a-device"></a>De status van een apparaat weergeven
De serienummers van een apparaat kunnen een van de volgende twee statussen hebben:

- Ingeschreven: het apparaat is ingeschreven en is verbonden met de Intune-service
- Geen contact: het apparaat is nooit verbonden met de Intune-service.
- Opnieuw instellen in behandeling: het apparaat is ingeschreven, maar er is een wijziging uitgevoerd (de instelling voor de inschrijving of het toegepaste DEP-profiel is gewijzigd). Als u het DEP-profiel van een apparaat wijzigt, worden de wijzigingen pas toegepast als het apparaat wordt uitgeschreven en vervolgens weer wordt ingeschreven.

**De status van een serienummer weergeven**

Selecteer op de blade **Apple Configurator-serienummers** het serienummer waarvan u de status wilt bekijken en kijk onder het item **Status**.



<!--HONumber=Feb17_HO1-->


