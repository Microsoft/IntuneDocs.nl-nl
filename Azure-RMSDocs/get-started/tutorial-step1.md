---
# required metadata

title: Zelfstudie Snel aan de slag met Azure RMS, stap 1 | Azure RMS
description: De eerste stap van een zelfstudie voor het snel uitproberen van Microsoft Azure Rights Management voor uw organisatie, met slechts 5 stappen die u in minder dan 15 minuten kunt uitvoeren.
keywords:
author: Cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: azure
ms.service: rights-management
ms.assetid: 7c4798e6-34a0-4c3f-a47f-505764ddf322

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---



# Snel aan de slag met Azure RMS, stap 1: de Rights Management-service activeren

*Van toepassing op: Azure Rights Management, Office 365*


Ga naar: 
> [!div class="op_single_selector"]
- [Inleiding](quick-start-tutorial.md)
- [Stap 1: activeer Azure RMS](tutorial-step1.md)
- [Stap 2: installeer RMS-app voor delen](tutorial-step2.md)
- [Stap 3: e-mail het vertrouwelijke document](tutorial-step3.md)
- [Stap 4: de ontvanger leest het document](tutorial-step4.md)
- [Stap 5: houd uw document bij](tutorial-step5.md)


![Zelfstudie voor snel aan de slag met Azure RMS - stap 1](../media/AzRMS_QuickStartSteps1.PNG)

Hoewel u wellicht een abonnement hebt met ondersteuning voor Azure Rights Management, is de service standaard uitgeschakeld. Als u deze wilt activeren, kunt u het Office 365-beheercentrum of de klassieke Azure-portal gebruiken:

-   Als u een Office 365-abonnement met Azure Rights Management hebt, of een Office 365-abonnement zonder Azure Rights Management maar u beschikt over een abonnement voor Azure RMS Premium: **gebruik het Office 365-beheercentrum**.

-   Als u geen Office 365-abonnement hebt: **gebruik de klassieke Azure-portal**.

![Schermafbeeldingen van stap 1 van de zelfstudie](../media/AzRMS_Tutorial_1_Screenshots.png)

### Rights Management activeren vanuit het klassieke Office 365-beheercentrum

1.  Ga naar de [Office 365-portal](https://portal.office.com/) en meld u aan met uw werk- of schoolaccount.

2.  Als het Office 365-beheercentrum niet automatisch wordt weergegeven, selecteert u het pictogram voor het starten van de app linksboven en kiest u **Admin**. De tegel **Admin** wordt alleen weergegeven voor Office 365-beheerders.

    > [!TIP]
    > Zie [About the Office 365 admin center - Admin Help](https://support.office.com/article/About-the-Office-365-admin-center-Admin-Help-58537702-d421-4d02-8141-e128e3703547) (Over het Office 365-beheercentrum - Admin-Help) voor hulp bij het beheercentrum.

3.  Vouw in het linkerdeelvenster **SERVICE-INSTELLINGEN** uit..

4.  Klik op **Rights Management**.

5.  Klik op de pagina **RIGHTS MANAGEMENT** op **Beheren**.

6.  Klik op de pagina **Rights Management** op **Activeren**.

7.  Als de vraag **Wilt u Rights Management activeren?** verschijnt, klikt u op **Activeren**.

U ziet nu **Rights management is geactiveerd** en de optie om te deactiveren (mogelijk moet u de pagina handmatig vernieuwen)

Klik op dit moment niet op **Geavanceerde functies**. U gaat dan naar de klassieke Azure-portal waar u sjablonen kunt configureren, maar deze zijn niet nodig voor deze zelfstudie. In plaats daarvan kunt u het Office 365-beheercentrum sluiten.

### Rights Management activeren vanuit de klassieke Azure-portal

1.  Ga naar de [klassieke Azure-portal](http://go.microsoft.com/fwlink/p/?LinkID=275081) en meld u aan.

2.  Klik in het linkerdeelvenster op **ACTIVE DIRECTORY**.

3.  Klik op de pagina **Active Directory** op **RIGHTS MANAGEMENT**.

4.  Selecteer de map die u wilt beheren voor [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)], klik op **ACTIVEREN** en bevestig de actie.

**RIGHTS MANAGEMENT-STATUS** wordt nu weergegeven als **Actief** en de optie **ACTIVEREN** is vervangen door **DEACTIVEREN**.

U kunt in de portal andere opties voor Rights Management configureren, maar deze zijn niet nodig voor deze zelfstudie. U kunt de klassieke Azure-portal dus sluiten.

Dit is alles wat u moet doen voor deze stap. De service wordt geactiveerd, zodat alle gebruikers in uw organisatie nu kunnen beginnen met het beveiligen van belangrijke en gevoelige documenten. In een productieomgeving is het raadzaam om te beperken wie dit in eerste instantie kan doen, en dit vervolgens gefaseerd uit te rollen. Maar dit is niet nodig is voor deze zelfstudie.

Mogelijk wilt u ook aangepaste sjablonen configureren. Dit wordt hier echter niet uitgelegd. Met sjablonen kunnen gebruikers gemakkelijker snel de juiste instellingen toepassen wanneer ze bestanden moeten beveiligen. Wanneer u Rights Management activeert, krijgt u automatisch twee standaardsjablonen. Waarschijnlijk wilt u deze in een productieomgeving aanvullen met uw eigen aangepaste sjablonen. Maar sjablonen zijn niet nodig voor deze zelfstudie. U kunt dus doorgaan naar de volgende stap.

|Als u meer informatie wilt|Aanvullende informatie|
|--------------------------------|--------------------------|
|Informatie over het activeren van Rights Management en beheren wie bestanden en e-mails kan beveiligen wanneer de service is geactiveerd|[Azure Rights Management activeren](../deploy-use/activate-service.md)|
|Informatie over de standaardsjablonen en het maken van nieuwe, aangepaste sjablonen|[Aangepaste sjablonen configureren voor Azure Rights Management](../deploy-use/configure-custom-templates.md)|


>[!div class="step-by-step"]
[«Inleiding](quick-start-tutorial.md)
[Stap 2 »](tutorial-step2.md)

<!--HONumber=Apr16_HO4-->


