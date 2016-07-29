---
title: Zelfstudie voor snel starten met Azure Information Protection - Stap 1 | Azure Rights Management
description: Stap 1 in de introductiezelfstudie om Microsoft Azure Information Protection snel uit te proberen voor uw organisatie, met slechts 4 stappen die minder dan 10 minuten duren.
author: cabailey
manager: mbaldwin
ms.date: 07/11/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: f6dbb143-96f7-4a9c-8208-be9280d69de9
translationtype: Human Translation
ms.sourcegitcommit: 78f0f07271414fb646f996e7273343f2abf8852b
ms.openlocfilehash: 633b24d0c23cbbee88a2647aaa9defe376ccb40e


---

# Stap 1: Rights Management-service activeren
 
*Van toepassing op: Azure Information Protection preview*

> [!NOTE]
>Als u uw gegevens alleen wilt classificeren en niet wilt beveiligen met Azure Rights Management of als u Azure Rights Management al hebt geactiveerd voor uw tenant gaat u door naar de [volgende stap](infoprotect-tutorial-step2.md). 

Als Azure Rights Management is geactiveerd, kunt u uw meest gevoelige documenten en bestanden beveiligen nadat deze zijn geclassificeerd. U kunt Azure Rights Management activeren met behulp van het Office 365-beheercentrum of met de klassieke Azure-portal:

-   Als u een Office 365-abonnement inclusief Azure Rights Management hebt of als u een Office 365-abonnement hebt zonder Azure Rights Management, maar u wel beschikt over een abonnement voor Azure RMS Premium: **gebruik het Office 365-beheercentrum**.

-   Als u geen Office 365-abonnement hebt: **gebruik de klassieke Azure-portal**.

### Rights Management activeren vanuit het klassieke Office 365-beheercentrum

> [!NOTE]
> Als u de **evaluatieversie van het Office 365-beheercentrum** in plaats van het klassieke Office 365-beheercentrum gebruikt, raadpleegt u de instructies in [Azure Rights Management activeren vanuit de evaluatieversie van het Office 365-beheercentrum](../deploy-use/activate-office365-preview.md) of schakelt u over naar de klassieke versie om deze instructies te gebruiken. Als u wilt overschakelen naar de klassieke versie, meldt u zich aan en klikt u vervolgens op de **start**pagina op **Naar oude beheercentrum**.

1.  Ga naar de [Office 365-portal](https://portal.office.com/) en meld u aan met het account van de globale beheerder van Office 365.

2.  Als het Office 365-beheercentrum niet automatisch wordt weergegeven, selecteert u linksboven het pictogram voor het starten van de app en kiest u **Beheer**. De tegel **Beheer** wordt alleen weergegeven voor Office 365-beheerders.

  > [!TIP]
  > Zie [Over het Office 365-beheercentrum - Help voor beheerders](https://support.office.com/article/About-the-Office-365-admin-center-Admin-Help-58537702-d421-4d02-8141-e128e3703547) voor hulp bij het beheercentrum.

3.  Vouw in het linkerdeelvenster **SERVICE-INSTELLINGEN** uit.

4.  Klik op **Rights Management**.

5.  Klik op de pagina **RIGHTS MANAGEMENT** op **Beheren**.

6.  Klik op de pagina **Rights Management** op **Activeren**.

7.  Als de vraag **Wilt u Rights Management activeren?** verschijnt, klikt u op **Activeren**.

U ziet nu **Rights management is geactiveerd** en de optie om te deactiveren (mogelijk moet u de pagina handmatig vernieuwen)

Klik op dit moment niet op **Geavanceerde functies**. U gaat dan naar de klassieke Azure-portal waar u aangepaste sjablonen kunt configureren. U hebt deze sjablonen niet nodig voor deze zelfstudie. In plaats daarvan kunt u het Office 365-beheercentrum sluiten.

### Rights Management activeren vanuit de klassieke Azure-portal

1.  Ga naar de [klassieke Azure-portal](http://go.microsoft.com/fwlink/p/?LinkID=275081) en meld u aan met het account van de globale beheerder van Azure Active Directory.

2.  Klik in het linkerdeelvenster op **ACTIVE DIRECTORY**.

3.  Klik op de pagina **Active directory** op **RIGHTS MANAGEMENT**.

4.  Selecteer de map die u wilt beheren voor [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)], klik op **ACTIVEREN** en bevestig de actie.

De **RIGHTS MANAGEMENT-STATUS** wordt nu weergegeven als **Actief** en de optie **ACTIVEREN** is vervangen door **DEACTIVEREN**.

U kunt in de portal ook andere opties voor Rights Management configureren, maar deze opties zijn niet nodig voor deze zelfstudie. U kunt de klassieke Azure-portal dus sluiten.

Dit is alles wat u hoeft te doen in deze eerste stap. De Azure Rights Management-service is geactiveerd, zodat u later in de zelfstudie een van de standaard Azure Rights Management-sjablonen kunt selecteren voor het beveiligen van documenten en e-mails die als vertrouwelijk zijn geclassificeerd.

Voor een productie-implementatie wilt u mogelijk aangepaste sjablonen configureren naast of in plaats van de twee standaard sjablonen van Azure Rights Management. Aangepaste sjablonen zijn echter niet nodig voor deze zelfstudie. U kunt dus doorgaan naar stap 2.

|Als u meer informatie wilt|Aanvullende informatie|
|--------------------------------|--------------------------|
|Informatie over het activeren van Rights Management|[Azure Rights Management activeren](../deploy-use/activate-service.md)|
|Informatie over de standaardsjablonen en het maken van nieuwe, aangepaste sjablonen|[Aangepaste sjablonen configureren voor Azure Rights Management](../deploy-use/configure-custom-templates.md)|

>[!div class="step-by-step"]
[&#171; Inleiding](infoprotect-quick-start-tutorial.md)
[Stap 2 &#187;](infoprotect-tutorial-step2.md)



<!--HONumber=Jul16_HO3-->


