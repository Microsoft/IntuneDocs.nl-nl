---
title: Inschrijving voor macOS-apparaten instellen
titlesuffix: Microsoft Intune
description: Meer informatie over hoe u de inschrijving voor iOS-apparaten in Intune instelt.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0d58cb3199405a8a32d169e74e4f0009841f5d09
ms.sourcegitcommit: 0ac196d1d06f4f52f01610eb26060419d248168b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/13/2018
ms.locfileid: "40251708"
---
# <a name="set-up-enrollment-for-macos-devices-in-intune"></a>Inschrijving voor macOS-apparaten instellen in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met Intune kunt u macOS-apparaten beheren om gebruikers toegang te geven tot zakelijke e-mail en apps.

Als Intune-beheerder kunt u inschrijving instellen voor bedrijfseigen macOS-apparaten en macOS-apparaten in privé-eigendom (Bring-Your-Own-Device of BYOD). 

## <a name="prerequisites"></a>Vereisten

Voer de volgende vereisten uit voordat u inschrijving van macOS-apparaten instelt:

- [Domeinen configureren](custom-domain-name-configure.md)
- [MDM-instantie instellen](mdm-authority-set.md)
- [Groepen maken](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [De bedrijfsportal configureren](company-portal-app.md)
- Gebruikerslicenties toewijzen in de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Een Apple MDM-pushcertificaat ophalen](apple-mdm-push-certificate-get.md)

## <a name="user-owned-macos-devices-byod"></a>macOS-apparaten die het eigendom van gebruikers zijn (BYOD)

U kunt gebruikers hun persoonlijke apparaten laten inschrijven voor Intune-beheer, wat Bring-Your-Own-Device of BYOD wordt genoemd. Nadat u aan de vereisten hebt voldaan en gebruikerslicenties hebt toegewezen, kunnen uw gebruikers hun apparaten als volgt registreren:
- door naar de [bedrijfswebsite](https://portal.manage.microsoft.com) te gaan; of
- de bedrijfsportal-app te downloaden.
U kunt hen ook een link naar online inschrijvingsstappen sturen: [Uw macOS-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Zie de volgende artikelen voor meer informatie over andere taken voor eindgebruikers:

- [Bronnen over de eindgebruikerservaring in Microsoft Intune](end-user-educate.md)
- [Uw macOS-apparaat gebruiken met Intune](/intune-user-help/using-your-macos-device-with-intune)

## <a name="company-owned-macos-devices"></a>Bedrijfseigen macOS-apparaten
Voor organisaties die apparaten voor hun gebruikers aanschaffen, ondersteunt Intune de volgende inschrijvingsmethoden voor macOS-apparaten die bedrijfseigendom zijn:
- [Het Device Enrollment Program (DEP) van Apple](device-enrollment-program-enroll-macos.md): organisaties kunnen nu macOS-apparaten aanschaffen via het Device Enrollment Program (DEP) van Apple. Met DEP kunt u een registratieprofiel draadloos implementeren om apparaten voor beheer in te schrijven.
- [Device Enrollment Program (DEM)](device-enrollment-manager-enroll.md): u kunt een DEM-account gebruiken om maximaal duizend apparaten te registreren.

## <a name="block-macos-enrollment"></a>macOS-inschrijving blokkeren
Standaard kunt u met Intune macOS-apparaten registreren. Zie [Beperkingen voor apparaattypen instellen](enrollment-restrictions-set.md) als u de inschrijving van macOS-apparaten wilt blokkeren.

## <a name="enroll-virtual-macos-machines-for-testing"></a>Virtuele macOS-machines inschrijven voor testen

> [!NOTE]
> Virtuele macOS-machines worden alleen ondersteund voor het testen. Gebruik geen virtuele macOS-machines als productieapparaten voor uw eindgebruikers. 

U kunt virtuele macOS-machines inschrijven voor het testen met ofwel Parallels Desktop of VMware Fusion. 

Voor Parallels Desktop moet u het hardwaretype en het serienummer voor de virtuele machines instellen zodat deze kunnen worden herkend door Intune. Volg de instructies van Parallels voor [het instellen van het hardwaretype](http://kb.parallels.com/123594) en [serienummer](http://kb.parallels.com/123455) om de vereiste instellingen voor het testen op te geven. U wordt aangeraden het hardwaretype van het apparaat waarop de virtuele machines worden uitgevoerd, af te stemmen op het hardwaretype van de virtuele machines die u maakt. U vindt dit hardwaretype in **Apple-menu** > **Over deze Mac** > **Systeeminformatie** > **Modelnaam**. 

Voor VMware Fusion moet u [het VMX-bestand bewerken](https://kb.vmware.com/s/article/1014782) om het hardwaremodel en serienummer van de virtuele machine in te stellen. U wordt aangeraden het hardwaretype van het apparaat waarop de virtuele machines worden uitgevoerd, af te stemmen op het hardwaretype van de virtuele machines die u maakt. U vindt dit hardwaretype in **Apple-menu** > **Over deze Mac** > **Systeeminformatie** > **Modelnaam**. 

## <a name="user-approved-enrollment"></a>Door de gebruiker goedgekeurde inschrijving

Door de gebruiker goedgekeurde MDM-inschrijving is een type macOS-inschrijving die u kunt gebruiken om bepaalde vertrouwelijke instellingen te beheren. Zie de [ondersteuningsdocumentatie van Apple](https://support.apple.com/HT208019) voor meer informatie.

Na de inschrijving met behulp van de macOS-bedrijfsportal, moet de gebruiker handmatig goedkeuren met behulp van de systeemvoorkeuren om door de gebruiker te worden goedgekeurd. Instructies hiervoor vindt u in de macOS-bedrijfsportal voor gebruikers van macOS 10.13.2 en later.

Ga naar de Intune-portal en kies vervolgens **Apparaten** > **Alle apparaten**> kies het apparaat > **Hardware** om te achterhalen of een apparaat door de gebruiker is goedgekeurd. Schakel het veld **Goedgekeurd door gebruiker** in.

## <a name="next-steps"></a>Volgende stappen

Nadat macOS-apparaten zijn geregistreerd, kunt u [aangepaste instellingen voor macOS-apparaten maken](custom-settings-macos.md).
