---
title: Extern vergrendelen en wachtwoordcode opnieuw instellen | Microsoft Docs
description: Intune biedt mogelijkheden voor zowel extern vergrendelen als het opnieuw instellen van de wachtwoordcode.
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 02/16/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
ms.reviewer: chrisgre
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 87589903acd3c2e7c45d62c619571a1273e7fb76
ms.openlocfilehash: 8de91a0e0640b9c0fb281686d4ecd4983134d4af

---
# <a name="help-protect-your-devices-with-remote-lock-and-passcode-reset"></a>Uw apparaten beschermen met extern vergrendelen en het opnieuw instellen van de wachtwoordcode

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune biedt mogelijkheden voor zowel extern vergrendelen als het opnieuw instellen van de wachtwoordcode.

## <a name="lock-a-device-remotely"></a>Een apparaat op afstand vergrendelen
Als een gebruiker een apparaat verliest, kunt u het apparaat op afstand vergrendelen. Het apparaat moet al zijn voorzien van een pincode of wachtwoordcode om vergrendeling op afstand te kunnen gebruiken.

In de volgende tabel wordt vermeld hoe vergrendelen op afstand werkt op verschillende mobiele platforms.

|Platform|Vergrendelen op afstand|
|------------|---------------|
|macOS|Niet ondersteund|
|iOS|Ondersteund|
|Android|Ondersteund|
|Windows 10 (mobiel)|Ondersteund|
|Windows 10 (desktop)|Niet ondersteund|
|Windows Phone 8 en Windows Phone 8.1|Ondersteund|
|Windows RT 8.1 en Windows RT|Ondersteund als de huidige gebruiker van het apparaat dezelfde gebruiker is die het apparaat heeft geregistreerd.|
|Windows 8.1|Ondersteund als de huidige gebruiker van het apparaat dezelfde gebruiker is die het apparaat heeft geregistreerd.|

Vergrendelen op afstand wordt niet ondersteund voor Windows-computers die zijn ingeschreven bij de Intune-software-client.

### <a name="lock-a-mobile-device-remotely-through-the-intune-console"></a>Een mobiel apparaat op afstand vergrendelen via de Intune-console

1.  Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Groepen** &gt; **Alle apparaten** &gt; **Alle mobiele apparaten**.

2.  Kies **Alle direct beheerde apparaten** voor apparaten die zijn geregistreerd bij Intune of **Alle door Exchange ActiveSync beheerde apparaten**.

    > [!TIP]
    > U kunt ook op gebruiker naar een apparaat navigeren. Kies **Alle gebruikers**. Kies op de pagina Eigenschappen van de gebruiker de optie **Apparaten** en vervolgens de naam van het mobiele apparaat dat u wilt vergrendelen.

3.  Kies in de lijst de apparaten die u wilt vergrendelen. Kies op de taakbalk de optie **Externe taken** en selecteer **Extern vergrendelen**.

## <a name="reset-the-passcode-on-a-device"></a>De wachtwoordcode op een apparaat opnieuw instellen
Als een gebruiker een wachtwoordcode vergeet, kunt u helpen door de wachtwoordcode van een apparaat te verwijderen of door een nieuwe tijdelijke wachtwoordcode op een apparaat af te dwingen. In de volgende tabel wordt aangegeven hoe de wachtwoordcode opnieuw moet worden ingesteld op verschillende mobiele platforms.

|Platform|Wachtwoordcode opnieuw instellen|
|------------|------------------|
|macOS|Niet ondersteund|
|iOS|Wordt ondersteund voor het wissen van de wachtwoordcode van een apparaat. Maakt geen nieuwe tijdelijke wachtwoordcode aan.|
|Android|Ondersteund in eerdere versies dan Android 7.0. Hiermee maakt u een tijdelijke wachtwoordcode.|
|Windows 10 Mobile|Ondersteund|
|Windows Phone 8 en Windows Phone 8.1|Ondersteund|
|Windows RT 8.1|Niet ondersteund|
|Windows 8.1|Niet ondersteund|
|Windows 10-bureaublad|Niet ondersteund|

Wachtwoordcode opnieuw instellen wordt niet ondersteund voor Windows-computers die zijn ingeschreven bij de Intune-software-client.

### <a name="reset-a-passcode"></a>Een wachtwoordcode opnieuw instellen

1.  Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Groepen** &gt; **Alle apparaten** &gt; **Alle mobiele apparaten**.

2.  Kies **Alle direct beheerde apparaten** voor apparaten die zijn geregistreerd bij Intune of **Alle door Exchange ActiveSync beheerde apparaten**.

    > [!TIP]
    > U kunt ook op gebruiker naar een apparaat navigeren. Klik op **Alle gebruikers**. Klik op de pagina Eigenschappen van de gebruiker op **Apparaten** en vervolgens op de naam van de gebruiker wiens mobiele apparaat u wilt wissen.

3.  Kies in de lijst de apparaten die u wilt vergrendelen. Kies op de taakbalk **Externe taken** en selecteer **Wachtwoordcode opnieuw instellen**.


### <a name="see-also"></a>Zie tevens
[Apparaten buiten gebruik stellen](retire-devices-from-microsoft-intune-management.md) en [Selectief wissen in Windows voor beheer van apparaatgegevens](http://technet.microsoft.com/library/dn486874.aspx)



<!--HONumber=Feb17_HO3-->


