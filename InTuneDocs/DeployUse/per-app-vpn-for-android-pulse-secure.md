---
# required metadata

title: VPN per app voor Android met behulp van Pulse Secure | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 05/08/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: chrisbal
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Een aangepast beleid gebruiken voor een VPN-profiel per app voor Android-apparaten

U kunt een VPN-profiel per app maken voor Android-apparaten die worden beheerd door Intune. U moet eerst een VPN-profiel maken dat gebruikmaakt van het verbindingstype Pulse Secure. Vervolgens maakt u een aangepast configuratiebeleid waarmee dit profiel aan specifieke apps wordt gekoppeld. Nadat u deze beleidsregels hebt geïmplementeerd voor uw Android-apparaat of gebruikersgroepen en uw een van de opgegeven apps op de ze apparaten opent, wordt er een VPN-verbinding voor die app geopend. 

### Stap 1: Een VPN-profiel maken

1. Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Beleid** > **Beleid toevoegen**.
2. Selecteer een sjabloon voor het nieuwe beleid door **Android** uit te vouwen en kies vervolgens **VPN-profiel (Android 4 en hoger)**.

3. In de sjabloon kiest u voor **Verbindingstype**, de optie **Pulse Secure**.
4. Voltooi het VPN-profiel en sla het op. Zie [VPN-profielen](Help%20users%20connect%20to%20their%20work%20using%20VPN%20profiles%20with%20Microsoft%20Intune.md) voor meer informatie over VPN-profielen.

> [!NOTE]
Noteer de naam van het VPN-profiel voor gebruik in de volgende stap. Bijvoorbeeld **MyAppVpnProfile**.
   
### Stap 2: Een aangepast configuratiebeleid maken
    
   1. Kies in de Intune-beheerconsole achtereenvolgens **Beleid** -> **Beleid toevoegen** -> **Android** -> **Aangepaste configuratie** -> **Beleid maken**.
   2. Geef een naam voor het beleid op.
   3. Klik onder **OMA-URI-instellingen** op **Toevoegen**.
   4. Geef een naam voor de instelling op.
   5. Geef voor **Gegevenstype** de optie **Tekenreeks** op.
   6. Geef voor **OMA-URI** deze tekenreeks op: **./Vendor/MSFT/VPN/Profile/*Name*/PackageList**, waarbij *Name* de naam van het VPN-profiel is dat u in stap 1 hebt genoteerd. In het voorbeeld dat hier wordt gebruikt, is de tekenreeks **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.
   7.   Geef bij **Waarde** een lijst met pakketten op (gescheiden door puntkomma's) die aan het profiel moeten worden gekoppeld.  Als u bijvoorbeeld wilt dat Excel en de Google Chrome-browser de VPN-verbinding gebruiken, voert u het volgende in: **com.microsoft.office.excel;com.android.chrome**.
  

   ![Voorbeeld van een aangepast VPN-beleid per app voor Android](..\media\android_per_app_vpn_oma_uri.png) 
#### Uw lijst met apps instellen als een zwarte of witte lijst (optioneel)
U kunt opgeven dat VPN-verbinding *niet* mag worden gebruikt door de lijst met apps door de waarde **BLACKLIST** te gebruiken.  Alle andere apps kunnen verbinding maken via VPN.

U kunt eventueel opgeven dat *alleen* de opgegeven apps de VPN-verbinding kunnen gebruiken door de waarde **WHITELIST** te gebruiken.
 

1.  Klik onder OMA-URI-instellingen op **Toevoegen**.
2.  Geef een naam voor de instelling op.
3.  Geef voor **Gegevenstype** de optie **Tekenreeks** op.
4.  Geef voor **OMA-URI** deze tekenreeks op: **./Vendor/MSFT/VPN/Profile/*Name*/Mode**, waarbij *Name* de naam is van het VPN-profiel dat u in stap 1 hebt genoteerd. In het voorbeeld dat hier wordt gebruikt, is de tekenreeks **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.
5.  Geef voor **Waarde** **BLACKLIST** of **WHITELIST** op. 


   
### Stap 3: Beide beleidsregels implementeren

U moet *beide* beleidsregels naar *dezelfde* Intune-groepen implementeren.

   1.  Selecteer het beleid dat u wilt implementeren in de werkruimte **Beleid** en klik vervolgens op **Implementatie beheren**.

2.  In het dialoogvenster **Implementatie beheren** :

    -   **Het beleid implementeren**: selecteer een of meer groepen waarvoor u het beleid wilt implementeren en klik vervolgens op **Toevoegen** &gt; **OK**.

    -   **Het dialoogvenster sluiten zonder het beleid te implementeren**: klik op **Annuleren**.

Een statusoverzicht en waarschuwingen op de pagina **Overzicht** van de werkruimte **Beleid** identificeren beleidsproblemen die uw aandacht nodig hebben. Bovendien wordt er een statusoverzicht weergegeven in de werkruimte Dashboard.



<!--HONumber=Jun16_HO1-->


