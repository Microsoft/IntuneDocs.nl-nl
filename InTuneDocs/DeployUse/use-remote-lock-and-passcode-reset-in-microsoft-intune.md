---
title: Extern vergrendelen gebruiken en wachtwoordcode opnieuw instellen | Microsoft Intune
description: Intune biedt mogelijkheden voor zowel extern vergrendelen als het opnieuw instellen van de wachtwoordcode.
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
ms.reviewer: chrisgre
translationtype: Human Translation
ms.sourcegitcommit: e9cbf5858cc4e860b540f421b6d463b8e7a429cf
ms.openlocfilehash: c2b4b6308569e1e67a1c3da18c12d19bdeecf08e

---
# Uw apparaten beschermen met extern vergrendelen en het opnieuw instellen van de wachtwoordcode
Microsoft Intune biedt mogelijkheden voor zowel extern vergrendelen als het opnieuw instellen van de wachtwoordcode.

## Een apparaat op afstand vergrendelen
Als een gebruiker het apparaat verliest, kunt u het apparaat vergrendelen op afstand. In de volgende tabel wordt vermeld hoe vergrendelen op afstand werkt op verschillende mobiele platforms.

|Platform|Vergrendelen op afstand|
|------------|---------------|
|iOS|Ondersteund|
|Android|Ondersteund|
|Windows 10 en Windows 10 Mobile|Ondersteund|
|Windows Phone 8 en Windows Phone 8.1|Ondersteund|
|Windows RT 8.1 en Windows RT|Ondersteund als de huidige gebruiker van het apparaat dezelfde gebruiker is die het apparaat heeft geregistreerd.|
|Windows 8.1|Ondersteund als de huidige gebruiker van het apparaat dezelfde gebruiker is die het apparaat heeft geregistreerd.|


### Een mobiel apparaat op afstand vergrendelen via de Intune-console

1.  Kies in de [Intune-beheerdersconsole](https://manage.microsoft.com/) **Groepen** &gt; **Alle apparaten** &gt; **Alle mobiele apparaten**.

2.  Kies **Alle direct beheerde apparaten** voor apparaten die zijn geregistreerd bij Intune of **Alle door Exchange ActiveSync beheerde apparaten**.

    > [!TIP]
    > U kunt ook op gebruiker naar een apparaat navigeren. Kies **Alle gebruikers**. Kies op de pagina Eigenschappen van de gebruiker de optie **Apparaten** en vervolgens de naam van de gebruiker wiens mobiele apparaat u wilt wissen.

3.  Kies in de lijst de apparaten die u wilt vergrendelen. Kies op de taakbalk de optie **Externe taken** en selecteer **Extern vergrendelen**.

## De wachtwoordcode op een apparaat opnieuw instellen
Als een gebruiker de wachtwoordcode vergeet, kunt u helpen door de wachtwoordcode van een apparaat te verwijderen of door een nieuwe en tijdelijke wachtwoordcode op een apparaat af te dwingen. In de volgende tabel wordt vermeld hoe de wachtwoordcode opnieuw moet worden ingesteld op verschillende mobiele platforms.

|Platform|Wachtwoordcode opnieuw instellen|
|------------|------------------|
|iOS|Wordt ondersteund voor het wissen van de wachtwoordcode van een apparaat. Maakt geen nieuwe tijdelijke wachtwoordcode aan.|
|Android|Wordt ondersteund en er wordt een tijdelijke wachtwoordcode aangemaakt.|
|Windows 10 Mobile|Ondersteund|
|Windows Phone 8 en Windows Phone 8.1|Ondersteund|
|Windows RT 8.1 en Windows RT|Niet ondersteund|
|Windows 8.1|Niet ondersteund|

### Een wachtwoordcode opnieuw instellen

1.  Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Groepen** &gt; **Alle apparaten** &gt; **Alle mobiele apparaten**.

2.  Kies **Alle direct beheerde apparaten** voor apparaten die zijn geregistreerd bij Intune of **Alle door Exchange ActiveSync beheerde apparaten**.

    > [!TIP]
    > U kunt ook op gebruiker naar een apparaat navigeren. Klik op **Alle gebruikers**. Klik op de pagina Eigenschappen van de gebruiker op **Apparaten** en vervolgens op de naam van de gebruiker wiens mobiele apparaat u wilt wissen.

3.  Kies in de lijst de apparaten die u wilt vergrendelen. Kies op de taakbalk **Externe taken** en selecteer **Wachtwoordcode opnieuw instellen**.


### Zie tevens
[Apparaten buiten gebruik stellen](retire-devices-from-microsoft-intune-management.md)
[Selectief wissen in Windows voor beheer van apparaatgegevens](http://technet.microsoft.com/library/dn486874.aspx)



<!--HONumber=Jul16_HO4-->


