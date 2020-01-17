---
title: Inschrijving van een Windows-apparaat bij de Intune-bedrijfsportal | Microsoft Docs
description: Ga aan de slag met het inschrijven van een Windows-apparaat in de bedrijfsportal
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/24/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 36250832-c6fd-4e8d-b681-de735023ebc3
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: 86c158f73d820fa2e719fe92b884c77f315fcb94
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 01/10/2020
ms.locfileid: "75858808"
---
# <a name="windows-device-enrollment-in-intune-company-portal"></a>Inschrijving van een Windows-apparaat bij de Intune-bedrijfsportal  

Schrijf uw Windows-apparaat in bij de Intune-bedrijfsportal-app voor beveiligde toegang tot apps, e-mailberichten en bestanden van werk en school. Als bepaalde apps door uw organisatie worden vereist of aangeraden, zoals Office of OneDrive, ontvangt u deze tijdens de inschrijving of zijn ze beschikbaar in de bedrijfsportal na de inschrijving.  

U kunt Windows 10-apparaten inschrijven via de website *of* app van de bedrijfsportal. Als u een apparaat met een eerdere versie van Windows inschrijft, moet u het apparaat via de website van de bedrijfsportal inschrijven.  

## <a name="install-company-portal-app"></a>De bedrijfsportal-app installeren  
Het is mogelijk dat de bedrijfsportal-app al op uw apparaat is geïnstalleerd. Controleer of de app op uw lijst __Alle apps__ staat.  Als u Bedrijfsportal niet in de lijst met apps ziet, volgt u deze stappen om de app te installeren.  

1. Open **Microsoft Store** op uw apparaat.

2. Typ in het veld **Zoeken** **Bedrijfsportal**.

3. Selecteer in de lijst met resultaten **Bedrijfsportal** > **Installeren**.

4. Selecteer **Installeren** of **Gratis**. Er is geen verschil tussen deze twee opties. De woorden worden weergegeven op basis van de manier waarop uw organisatie de app heeft ingesteld.  

## <a name="find-windows-10-version-number"></a>Het Windows 10 versienummer opzoeken  
De stappen voor inschrijving verschillen voor verschillende versies van Windows 10-apparaten. In de volgende stappen wordt beschreven hoe u het versienummer kunt vinden op pc's en mobiele apparaten met Windows 10. Wanneer u uw versie kent, kunt u doorgaan met de aanbevolen inschrijvingsstappen.  

### <a name="windows-10-desktop-devices"></a>Windows 10 Desktop-apparaten  

1. Ga naar **Start**.

2. Typ in de zoekbalk de zin 'Over uw pc.' Selecteer __Over uw pc__ in de resultaten.  


   ![zoekinstellingen voor info over uw pc](media/searching_for_about_your_pc.png)  

3. Schuif omlaag naar **Windows-specificaties** om de Windows 10-**versie** te vinden die is geïnstalleerd op uw pc.  


   ![Windows 10 Desktop - over uw pc](media/settings_about_pc.png)  

4. Als uw versie  

    * __1607 of hoger is__: Schrijf het apparaat in via de route [**Instellingen** > **Account** > **Toegang tot werk of school**](enroll-windows-10-device.md#enroll-windows-10-version-1607-and-later-device).   
    * __1511 of lager is__: Schrijf het apparaat in via de route [**Instellingen** > **Account** > **Uw accounts**](enroll-windows-10-device.md#enroll-windows-10-version-1511-and-earlier-device).  

### <a name="windows-10-mobile-devices"></a>Windows 10 Mobile-apparaten

1. Ga naar __alle apps__ en selecteer de app __Instellingen__.
2. Selecteer __Systeem__ > __Info__.
3. Zoek onder __Apparaatgegevens__ de __versie__.  
4. Als uw versie  

    * __1607 of hoger is__: Schrijf het apparaat in via de route [**Instellingen** > **Toegang tot werk of school**](enroll-windows-10-device.md#enroll-windows-10-version-1607-and-later-device).   
    * __1511 of lager is__: Schrijf het apparaat in via de route [**Instellingen** > **Accounts**](enroll-windows-10-device.md#enroll-windows-10-version-1511-and-earlier-device).  

## <a name="enroll-non-windows-10-devices"></a>Niet-Windows 10-apparaten inschrijven  
Gebruik de volgende artikelen om andere ondersteunde Windows-apparaten in te schrijven via de website van de bedrijfsportal:   
* [Windows 8.1- of Windows RT 8.1-apparaat](enroll-your-W81-or-rt81-windows.md)  
* [Windows Phone 8.1-apparaat](enroll-your-wp81-windows.md)    

## <a name="it-administrator-support"></a>Ondersteuning IT-beheerder  
Als u een IT-beheerder bent en in de problemen raakt tijdens het inschrijven van apparaten, kunt u [Troubleshooting Windows device enrollment problems in Microsoft Intune (Problemen oplossen met de inschrijving van Windows-apparaten in Microsoft Intune)](https://support.microsoft.com/help/4469913) raadplegen. Dit artikel bevat algemene fouten, de oorzaken en de stappen om deze op te lossen.  

## <a name="next-steps"></a>Volgende stappen  
Nu u de ondersteunde apparaten en het versienummer van uw Windows 10 weet, kunt u doorgaan met het aanbevolen artikel voor de inschrijving.  
 
Zie de volgende artikelen voor meer informatie over het beheer van apparaten, de bedrijfsportal en hoe beide in scholen en op het werk worden gebruikt:  
* [Beheerde apparaten gebruiken om toegang te krijgen tot werk- of schoolresources](use-managed-devices-to-get-work-done.md)  
* [Wat gebeurt er wanneer u uw apparaat registreert bij Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md)  
* [Welke gegevens kan mijn organisatie zien wanneer ik mijn apparaat inschrijf?](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md)  

Hebt u hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. [Ga naar de website van de bedrijfsportal](https://go.microsoft.com/fwlink/?linkid=2010980) om de contactgegevens voor IT van uw organisatie op te zoeken.  
