---
title: Wachtwoordcode opnieuw instellen op Windows-apparaten met Intune
titlesuffix: Azure portal
description: "In dit artikel leest u hoe u met Intune de wachtwoordcode opnieuw kunt instellen op Windows-apparaten die zijn geïntegreerd met de Microsoft-service PIN Reset."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: faf3e9b81f76755135f73f8753305d96d227ec14
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/15/2017
---
# <a name="reset-the-passcode-on-windows-devices-integrated-with-the-microsoft-pin-reset-service-using-intune"></a>Intune gebruiken om de wachtwoordcode opnieuw in te stellen op Windows-apparaten die zijn geïntegreerd met de Microsoft-service PIN Reset

De functie voor het opnieuw instellen van de wachtwoordcode voor Windows-apparaten is geïntegreerd met de Microsoft-service PIN Reset om u in staat te stellen een nieuwe wachtwoordcode te genereren voor apparaten met Windows 10 Mobile. Microsoft Windows 10-makersupdate of hoger moet zijn geïnstalleerd op de apparaten.

## <a name="supported-platforms"></a>Ondersteunde platforms

- Windows: ondersteund op Windows 10 Creators Update en hoger (lid van Azure AD-domein)
- Windows Phone: niet ondersteund
- iOS: niet ondersteund
- macOS: niet ondersteund
- Android: niet ondersteund


## <a name="before-you-start"></a>Voordat u begint

Voordat u de wachtwoordcode op Windows-apparaten op afstand opnieuw kunt instellen, moet u de service PIN Reset toevoegen aan uw Intune-tenant en de apparaten configureren die u beheert. Volg de onderstaande instructies om deze taken uit te voeren:

### <a name="connect-intune-with-the-pin-reset-service"></a>Intune verbinden met de service PIN Reset

1. Ga naar [de website van Microsoft PIN Reset Service Integration](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent) en meld u aan met het tenantbeheerdersaccount dat u gebruikt voor het beheren van uw Intune-tenant.
2. Nadat u zich hebt aangemeld, klikt u op **Accepteren** om de service PIN Reset toegang te geven tot uw account.<br>
![Pagina Microsoft PIN Reset Service Integration](./media/pin-reset-service-application.png)
3. In Azure Portal kunt u controleren of Intune en de service PIN Reset zijn geïntegreerd door naar de blade Bedrijfstoepassingen - Alle toepassingen te gaan. Zie ook de volgende schermafbeelding:<br>
![De integratie van PIN Reset in Azure](./media/pin-reset-service-home-screen.png)
4. Meld u aan bij [deze website](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) met behulp van uw beheerreferenties voor de Intune-tenant en kies opnieuw **Accepteren** om de service toegang te geven tot uw account.

### <a name="configure-windows-devices-to-use-pin-reset"></a>Windows-apparaten configureren voor de service PIN Reset

Als u de service PIN Reset wilt configureren op Windows-apparaten die u beheert, gebruikt u een [aangepast apparaatbeleid van Intune Windows 10](custom-settings-windows-10.md) om de functie in te schakelen. Configureer het beleid met behulp van de volgende Configuration Service Provider (CSP) van Windows:


- **Voor apparaten** - **./Device/Vendor/MSFT/PassportForWork/*tenant ID*/Policies/EnablePinRecovery**

*tenant ID* verwijst naar uw Azure Active Directory, de directory-id die u kunt verkrijgen via de pagina **Eigenschappen** van Azure Active Directory.

Stel de waarde voor deze CSP in op **Waar**.

## <a name="steps-to-reset-the-passcode"></a>Stappen voor het opnieuw instellen van de wachtwoordcode

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies op de blade **Apparaten** achtereenvolgens **Beheren** > **Alle apparaten**.
5. Selecteer het apparaat waarvoor u de wachtwoordcode opnieuw wilt instellen en kies vervolgens **Nieuwe wachtwoordcode** op de blade met apparaateigenschappen.
6. Kies **Ja** ter bevestiging. De wachtwoordcode wordt gegenereerd en wordt gedurende zeven dagen weergegeven in de portal.

## <a name="next-steps"></a>Volgende stappen

Als het opnieuw instellen van de wachtwoordcode mislukt, kunt u in de portal een koppeling volgen voor meer informatie.


