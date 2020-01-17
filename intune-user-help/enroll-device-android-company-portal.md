---
title: Een Android-apparaat inschrijven bij de Intune-bedrijfsportal | Microsoft Docs
description: Hierin wordt beschreven hoe u een Android-apparaat bij de Intune-bedrijfsportal kunt inschrijven
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: e0a2297509d6077d6508adaab96ae6eb3cf9b28f
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 01/10/2020
ms.locfileid: "75856731"
---
# <a name="enroll-your-device-with-company-portal"></a>Uw apparaat inschrijven bij de bedrijfsportal  
Schrijf uw persoonlijke of zakelijke Android-apparaat in voor veilige toegang tot uw zakelijke e-mail, apps en gegevens. De bedrijfsportal biedt ondersteuning voor Android-apparaten, inclusief Samsung Knox, met Android 4.4 en hoger.  
</br>
> [!VIDEO https://www.youtube.com/embed/k0Q_sGLSx6o?rel=0]

> [!NOTE]
> Samsung Knox is een beveiligingstype dat door sommige Samsung-apparaten wordt gebruikt als extra bescherming naast de beveiligingsfuncties van systeemeigen Android-apparaten. Als u wilt controleren of u een Samsung Knox-apparaat hebt, gaat u naar **Instellingen** > **Over apparaat**. Als de **Knox-versie** niet wordt vermeld, hebt u een systeemeigen Android-apparaat.

## <a name="enroll-device"></a>Een apparaat inschrijven  
Zorg ervoor dat u [de gratis app Intune-bedrijfsportal via Google Play hebt geïnstalleerd](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal). 

Tijdens de registratie wordt u mogelijk gevraagd om een categorie te kiezen die het beste beschrijft hoe u uw apparaat gebruikt. Het ondersteuningsteam van het bedrijf gebruikt uw antwoord om te controleren tot welke apps u toegang hebt.  

1. Open de bedrijfsportal-app en meld u aan met het account van uw werk of school.  

2. Als u wordt gevraagd de algemene voorwaarden van uw organisatie te accepteren, tikt u op **ACCEPT ALL**.  

   ![Voorbeeld afbeelding van het scherm Bedrijfsportal, voor waarden, waarbij u de knop Alles accepteren markeert.](./media/accept-terms-1911.png)  


3. Bekijk wat uw organisatie wel en niet kan zien. Tik vervolgens op **doorgaan**.


    ![Voorbeeld afbeelding van Bedrijfsportal, het scherm van uw privacy, het markeren van de knop door gaan.](./media/android-privacy-screen-1911.png)  
4. Bekijk wat u in de komende stappen kunt verwachten. Tik vervolgens op **volgende**.  

    ![Voorbeeld afbeelding van Bedrijfsportal, wat is het volgende scherm, waarbij u de knop volgende markeert.](./media/android-whats-next-1911.png)  


5. Afhankelijk van uw versie van Android, wordt u mogelijk gevraagd om toegang tot bepaalde onderdelen van uw apparaat toe te staan. Deze prompts zijn vereist voor Google en niet beheerd door micro soft.  

    Tik op **toestaan** voor de volgende machtigingen:  
    * **Bedrijfsportal voor het maken en beheren van telefoon gesprekken toestaan**: met deze machtiging kan uw apparaat het IMEI-nummer (International Mobile station Equipment Identity) delen met intune, de provider van het beheer apparaat van uw organisatie. Het is veilig om deze machtiging toe te staan. Micro soft zal nooit telefoon gesprekken voeren of beheren.  
    * **Bedrijfsportal toegang tot uw contact personen toestaan: met**deze machtiging kan de bedrijfsportal app uw werk account maken, gebruiken en beheren.  Het is veilig om deze machtiging toe te staan. Micro soft heeft nooit toegang tot uw contact personen. 

    Als u toestemming verleent, wordt u opnieuw gevraagd de volgende keer dat u zich aanmeldt bij Bedrijfsportal. Als u deze berichten wilt uitschakelen, selecteert u **Niet opnieuw vragen**. Als u app-machtigingen wilt beheren, gaat u naar de instellingen app > **Apps** > **Bedrijfsportal** > **machtigingen** > **telefoon**.  

6. Activeer de app voor het beheer van apparaten. 

    Bedrijfsportal hebt beheerders machtigingen nodig om uw apparaat veilig te beheren. Als u de app activeert, kan uw organisatie mogelijke beveiligings problemen identificeren, zoals herhaalde mislukte pogingen om uw apparaat te ontgrendelen en op de juiste wijze te reageren.  

    ![Voorbeeld afbeelding van het scherm Apparaatbeheer activeren, waarbij u de knop activeren markeert.](./media/activate-device-administrator-1911.png)  

> [!NOTE]
> Micro soft beheert de berichten op dit scherm niet. We begrijpen dat het formule ring enigszins drastisch kan lijken. Bedrijfsportal kunt niet opgeven welke beperkingen en toegang relevant zijn voor uw organisatie. Als u vragen hebt over hoe uw organisatie de app gebruikt, neemt u contact op met uw IT-ondersteunings medewerker. [Ga naar de website van de bedrijfsportal](https://go.microsoft.com/fwlink/?linkid=2010980) om de contactgegevens van uw organisatie op te zoeken.  


7. Het apparaat wordt Inge schreven. Als u een Samsung Knox-apparaat gebruikt, wordt u gevraagd het privacybeleid van de ELM-agent eerst te controleren en te bevestigen.   

    ![Voorbeeld afbeelding van het scherm voor het privacybeleid van Samsung Knox dat wordt weer gegeven tijdens de inschrijving.](./media/and-enroll-7-knox-privacy-policy.png)  

8. Controleer in het scherm **instellen van bedrijfs toegang** of het apparaat is inge schreven. Tik vervolgens op **doorgaan**.  

    ![Voor beeld van een afbeelding van Bedrijfsportal, het scherm voor het instellen van bedrijfs toegang, waarin wordt weer gegeven dat uw apparaat wordt beheerd is voltooid.](./media/update-settings-1911.png)  

9. Uw organisatie vereist mogelijk dat u de apparaatinstellingen bijwerkt. Tik op **oplossen** om een instelling aan te passen. Wanneer u klaar bent met het bijwerken van de instellingen, tikt u op **door gaan**.  

   ![Voorbeeld afbeelding van Bedrijfsportal, apparaatinstellingen bijwerken, markeringen voor oplossen en door gaan markeren.](./media/resolve-settings-1911.png)  

10. Wanneer het installatie programma is voltooid, tikt u op **gereed**.    

    ![Voor beeld van een afbeelding van Bedrijfsportal, het scherm voor het instellen van bedrijfs toegang, waarin de knop voltooid instellen en markering is gemarkeerd wordt weer gegeven.](./media/android-enrollment-done-1911.png) 

## <a name="next-steps"></a>Volgende stappen  

Voordat u probeert een school-of werk-app te installeren, gaat u naar **instellingen** > **beveiliging**en schakelt u **onbekende bronnen**in. Als u deze optie niet inschakelt, ziet u het volgende bericht wanneer u een app installeert: "Installatie geblokkeerd. Uw apparaat is uit veiligheidsoverwegingen zo ingesteld dat installaties van apps die afkomstig zijn van onbekende bronnen, worden geblokkeerd." U kunt op **instellingen** in het bericht tikken om rechtstreeks naar **onbekende bronnen**te gaan.  

> [!Note]
> Als uw organisatie gebruikmaakt van Telecom Expense Management-software, zijn er een aantal aanvullende stappen die u moet doorlopen om uw apparaat volledig in te schrijven. Zie [hier](enroll-your-device-with-telecom-expense-management-android.md) voor meer informatie.

Als er een fout optreedt bij het registreren van uw apparaat bij Intune, kunt u [een e-mailbericht naar het ondersteuningsteam van uw bedrijf verzenden](send-logs-to-your-it-admin-by-email-android.md).  

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Controleer of de contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).  