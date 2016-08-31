---
title: Azure Rights Management activeren vanuit de klassieke Azure-portal | Azure RMS
description: 'Volg deze instructies als u toegang tot de Azure-portal hebt. Bijvoorbeeld: u hebt een abonnement voor Enterprise Mobility Suite of Azure Rights Management Premium.'
author: cabailey
manager: mbaldwin
ms.date: 06/27/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 9b0a0227-88ce-44b8-ba3f-31eeaab27ff7
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26b043f1f9e7a1e0cd00c2f31c28f7d6685f0232
ms.openlocfilehash: 573aa437d8449212bd2f22b532342e4c7e3a1be6


---

# Azure Rights Management activeren vanuit de klassieke Azure-portal

>*Van toepassing op: Azure Rights Management*


Volg deze instructies als u toegang tot de Azure-portal hebt. Bijvoorbeeld: u hebt een abonnement voor Enterprise Mobility Suite of Azure Rights Management Premium.

> [!TIP]
> Bekijk een video van 2 minuten: [Azure RMS activeren](https://channel9.msdn.com/series/pit-stop-enterprise-mobility-suite/activate-azure-rms)

1.  [Meld u aan bij de klassieke Azure-portal](http://go.microsoft.com/fwlink/p/?LinkID=275081) nadat u zich hebt aangemeld voor uw Azure-account. Gebruik het account van de globale beheerder zoals het account waarmee u het abonnement dat Azure Rights Management bevat hebt gedownload.

2.  Klik in het linkerdeelvenster op **ACTIVE DIRECTORY**.

3.  Klik op de pagina **Active directory** op **RIGHTS MANAGEMENT**.

4.  Selecteer de map die u wilt beheren voor [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)], klik op **ACTIVEREN** en bevestig de actie.

    > [!NOTE]
    >Als er een activeringsfout optreedt, kan het zijn dat uw service-abonnement of productversie geen recht geeft op [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)].
    >
    >Gebruik de informatie in [Cloudabonnementen die Azure RMS ondersteunen](../get-started/requirements-subscriptions.md) om te controleren op RMS-ondersteuning. Voor hulp bij dit probleem stuurt u een e-mailbericht naar [askipteam](mailto:askipteam?subject=I%20cannot%20activate%20RMS).


De **RIGHTS MANAGEMENT-STATUS** wordt nu weergegeven als **Actief** en de optie **ACTIVEREN** is vervangen door **DEACTIVEREN**.

## Rights Management-statuswaarden en -beschrijvingen in de klassieke Azure-portal
Naast de status **Actief** die aangeeft dat de Rights Management-service is ingeschakeld en gereed is voor gebruik, ziet u mogelijk ook **Inactief**, **Niet beschikbaar** of **Niet geautoriseerd**.

|Statuswaarde|Beschrijving|
|----------------|---------------|
|**Actief**|[!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)] is ingeschakeld en gereed voor gebruik.|
|**Inactief**|[!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)] is uitgeschakeld en moet worden geactiveerd voordat uw organisatie bestanden kan beveiligen.|
|**Niet beschikbaar**|De [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)]-service is niet actief. Probeer het later opnieuw.|
|**Niet geautoriseerd**|U bent niet gemachtigd om de status van de [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)]-service weer te geven. Uw account is bijvoorbeeld vergrendeld of u bent niet de algemene beheerder voor de geselecteerde tenant.|

## Volgende stappen
Terug naar [Azure Rights Management activeren](activate-service.md).


<!--HONumber=Aug16_HO4-->


