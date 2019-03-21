---
title: Uw Android-apparaat registreren bij Intune | Microsoft Docs
description: Hierin wordt beschreven hoe u een Android-apparaat bij Intune kunt inschrijven
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/05/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 188c32a2fd38d3445380a9d1898b90a3bb080ae1
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57335204"
---
# <a name="enroll-your-android-device-in-intune"></a>Uw Android-apparaat inschrijven bij Intune

Als uw bedrijf of school gebruikmaakt van Microsoft Intune, kunt u uw Android-apparaat registreren voor toegang tot zakelijke e-mail, bestanden en andere bronnen. Door uw apparaten te registreren, kan uw IT-afdeling deze werk- of schoolbronnen beheren en veilig houden, en beschikt u over de vrijheid om het apparaat van uw voorkeur te gebruiken voor uw werk. Zie [Wat gebeurt er wanneer ik de bedrijfsportal-app installeer en mijn apparaat inschrijf?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md) voor meer informatie over inschrijving.

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment/player]

Deze registratie-instructies zijn bestemd voor 'native' en Samsung Knox Android-apparaten. Samsung Knox is een beveiligingstype dat door sommige Samsung-apparaten wordt gebruikt als extra bescherming naast de beveiligingsfuncties van native Android-apparaten. Als u wilt controleren of u een Samsung Knox-apparaat hebt, gaat u naar **Instellingen** > **Over apparaat**. Als de Knox-versie niet wordt vermeld, hebt u een systeemeigen Android-apparaat.

Voor of na de registratie wordt u mogelijk gevraagd om een categorie te kiezen die het beste beschrijft hoe u uw apparaat gebruikt. Het ondersteuningsteam van het bedrijf gebruikt deze categorie om te controleren tot welke apps u toegang hebt.

**Ga als volgt te werk om uw Android-apparaat te registeren:**

1. Installeer de gratis app Intune-bedrijfsportal via [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal).

2. Open de app Bedrijfsportal.

3. Tik in het **aanmeldingsscherm** van de bedrijfsportal op **Aanmelden** en meld u vervolgens aan met uw werk- of schoolaccount.

   ![De bedrijfsportal-app voor het Android-welkomstscherm, waarin de gebruiker wordt gevraagd zich aan te melden met het vereist werk- of schoolaccount. Hierin wordt tevens gewaarschuwd dat Microsoft-accounts en andere persoonlijke accounts worden niet geaccepteerd.](./media/and-enroll-0-welcome-screen.png)   

4. Als het ondersteuningsteam van het bedrijf voorwaarden van het bedrijf heeft ingesteld, tikt u op **ACCEPTEREN** om de voorwaarden te accepteren. Dit scherm kan enigszins afwijken van de onderstaande afbeelding, afhankelijk van de Android-versie die u momenteel gebruikt.

   ![android-bedrijfsportal-aanmelden](./media/and-enroll-3-accept-terms.png)

5. Meld u aan bij de bedrijfsportal-app met uw werk- of schoolaccount en wachtwoord, en tik vervolgens op **Aanmelden**.

   ![android-bedrijfsportal-aanmelden](./media/and-enroll-2-cp-sign-in.png)

6. Tik in het scherm **Instellen van bedrijfstoegang** op **DOORGAAN**.

   ![Het scherm Instellen van bedrijfstoegang](/intune/media/android_cp_enroll_01_1709_new.png)

   > [!NOTE]
   > De gele driehoeken betekenen niet dat er al een fout is opgetreden. Deze pictogrammen geven aan dat er nog stappen moeten worden voltooid in het inschrijvingsproces.

7. Bekijk een lijst met zaken die het ondersteuningsteam van het bedrijf wel en niet kan zien op het apparaat en tik op **DOORGAAN**.

   ![Privacy-instellingen](/intune/media/android_cp_enroll_02_after_1710.png)

8. Lees op het scherm **De volgende stap** wat er gebeurt tijdens het registreren en tik vervolgens op **REGISTREREN**.

   ![Het scherm De volgende stap](/intune/media/android_cp_enroll_03_after_1710.png)

9. Als u Android 6.0 of hoger gebruikt, moet u deze stap uitvoeren. Ga anders naar de volgende stap.

   Als het ondersteuningsteam van het bedrijf bepaald beleid heeft ingesteld, ziet u mogelijk de volgende berichten:
   - **De bedrijfsportal toestaan telefoongesprekken uit te voeren en te beheren?**

     ![android-bedrijfsportal-aanmelden](./media/and-enroll-3a-allow-phone-access.png)

   Als u dit bericht ziet, tikt u op **TOESTAAN**. Het is veilig om op TOESTAAN te tikken, omdat **Microsoft nooit telefoongesprekken uitvoert of beheert**. Google beheert de tekst van het bericht. De tekst kan niet worden gewijzigd door Microsoft. Als u toegang toestaat, staat u alleen toe dat het IMEI-nummer ( International Mobile Equipment Identity) van uw apparaat wordt verzonden naar Intune. Het IMEI-nummer is vergelijkbaar met een serienummer en is uniek voor een mobiel apparaat.

   Als u de toegang weigert, wordt het bericht de volgende keer dat u zich bij de bedrijfsportal aanmeldt, opnieuw weergegeven. U kunt echter toekomstige berichten uitschakelen door op het selectievakje **Niet opnieuw vragen** te tikken. Als u later besluit toegang te verlenen, gaat u naar **Instellingen** &gt; **Apps** &gt; **Bedrijfsportal** &gt; **Machtigingen** &gt; **Telefoon** en schakelt u de machtiging in.

   - **Toestaan dat Bedrijfsportal toegang heeft tot uw contactpersonen?**

     ![android-bedrijfsportal-aanmelden](./media/and-enroll-3b-allow-contacts-access.png)

     Als u dit bericht ziet, tikt u op **TOESTAAN**. Het is veilig om op TOESTAAN te tikken, omdat **Microsoft nooit toegang tot uw contactpersonen probeert te krijgen**. Google beheert de tekst van het bericht. De tekst kan niet worden gewijzigd door Microsoft. Als u toegang toestaat, kan alleen met de bedrijfsportal-app uw werkaccount worden gemaakt, gebruikt en beheerd.

     Als u de toegang weigert, wordt het bericht de volgende keer dat u zich bij de bedrijfsportal aanmeldt, opnieuw weergegeven. U kunt echter toekomstige berichten uitschakelen door op het selectievakje **Niet opnieuw vragen** te tikken. Als u later besluit toegang te verlenen, gaat u naar **Instellingen** &gt; **Apps** &gt; **Bedrijfsportal** &gt; **Machtigingen** &gt; **Telefoon** en schakelt u de machtiging in.

10. Tik op het scherm **Apparaatbeheerder activeren** op **Activeren**.

    ![Het scherm Apparaatbeheerder activeren](./media/and-enroll-5-activate.png)

    De rol van apparaatbeheerder houdt in dat de bedrijfsportal uw apparaat moet beheren. Het stelt uw beheerder in staat om bepaalde dingen te bekijken, zoals het aantal keren dat u uw scherm hebt ontgrendeld en bepaalde acties hebt ondernomen.

    Van belang is om te weten dat deze acties worden ondernomen vanwege de beveiliging. Het ondersteuningsteam van het bedrijf schendt uw privacy niet en wist uw gegevens niet wanneer daar geen reden toe is. De beheerder wil er gewoon voor zorgen dat de bedrijfsgegevens veilig worden bewaard.

    Microsoft heeft geen zeggenschap over dit bericht en de bewoording kan enigszins drastisch overkomen. Met de bedrijfsportal kunnen niet alleen de beperkingen en toegang worden weergegeven die relevant zijn voor uw organisatie. Deze worden alle tegelijk op dit scherm weergegeven. Neem aan de hand van de contactgegevens op de [website van de bedrijfsportal](https://go.microsoft.com/fwlink/?linkid=2010980) contact op met het ondersteuningsteam van het bedrijf als u vragen hebt met betrekking tot uw eigen organisatie.

11. Volg de aanwijzingen voor het invoeren van de pincode of het wachtwoord. Als u al een pincode of wachtwoord op dit apparaat hebt ingesteld, wordt dit scherm niet weergegeven of wordt u niet verzocht om een nieuwe pincode of nieuw wachtwoord in te voeren.

    ![Pincode of wachtwoord instellen](./media/and-enroll-6-PIN-native.png)

12. Als u een Samsung Knox-apparaat gebruikt, tikt u op **Bevestigen**. U ziet dan een bericht dat uw apparaat wordt geregistreerd. Als u een systeemeigen Android-apparaat gebruikt, let dan op het volgende scherm waarin wordt weergegeven dat het apparaat wordt geregistreerd.

    ![Samsung Knox-privacybeleid](./media/and-enroll-7-knox-privacy-policy.png)

    Op dit scherm wordt aangegeven dat uw apparaat wordt geregistreerd.

    ![Het scherm Apparaat registreren](./media/and-enroll-8-device-enrolling.png)

13. Wanneer het scherm **Instellen van bedrijfstoegang** wordt weergegeven, tikt u op **DOORGAAN**. Als er een bericht verschijnt waarin wordt aangegeven dat het apparaat niet voldoet aan het beleid, volgt u de instructies om het probleem te verhelpen en tikt u vervolgens op **DOORGAAN**.

    ![Het apparaat is niet compatibel, maar is geregistreerd](/intune/media/android_cp_enroll_05_post_1709.png)

    ![Er zijn problemen met apparaatcompatibiliteit die moeten worden opgelost](/intune/media/android_cp_enroll_03_post_1709.png)

    Als u op de problemen tikt, wordt meer informatie over het betreffende probleem weergegeven.

    ![Uitgevouwen weergave van problemen met apparaatcompatibiliteit](/intune/media/android_cp_enroll_04_post_1709.png)

    ![Het scherm Instellen van bedrijfstoegang](./media/and-enroll-9d-comp-access-setup.png)  

14. Tik in het scherm **Instellen van bedrijfstoegang is voltooid** op **GEREED**. Uw apparaat is nu geregistreerd.

    ![Het scherm Instellen van bedrijfstoegang is voltooid](./media/and-enroll-10-comp-access-setup-complete.png)

Ga naar **Instellingen** &gt; **Beveiliging** en schakel **Onbekende bronnen** in voordat u bedrijfsapps installeert. Als u deze optie niet inschakelt voordat u apps installeert, wordt het volgende bericht weergegeven: "Installatie geblokkeerd. Uw apparaat is uit veiligheidsoverwegingen zo ingesteld dat installaties van apps die afkomstig zijn van onbekende bronnen, worden geblokkeerd." U kunt in het foutberichtvenster op **Instellingen** tikken om naar de optie **Onbekende bronnen** te gaan.

> [!Note]
> Als uw organisatie gebruikmaakt van Telecom Expense Management-software, zijn er een aantal aanvullende stappen die u moet doorlopen om uw apparaat volledig in te schrijven. Zie [hier](enroll-your-device-with-telecom-expense-management-android.md) voor meer informatie.

Als er een fout optreedt bij het registreren van uw apparaat bij Intune, kunt u [registratiefouten naar het ondersteuningsteam van het bedrijf verzenden](send-enrollment-errors-to-your-it-admin-android.md).

Nog hulp nodig? Neem contact op met het ondersteuningsteam van het bedrijf (zie de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980) voor contactgegevens) of stuur een e-mail naar het <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android-team</a>.
