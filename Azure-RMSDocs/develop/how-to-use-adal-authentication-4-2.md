---
title: Azure Portal gebruiken voor het configureren van RMS-verificatie | Azure RMS
description: Biedt een overzicht van het verificatieproces met ADAL
keywords: authentication, RMS, ADAL
author: bruceperlerms
manager: mbaldwin
ms.date: 06/14/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 2680b399-febb-4bd6-b844-ac3d1e69aca4
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3f43f5605b1c341d7be618327038d1a86a305a5b
ms.openlocfilehash: cb82f0333ed17ee2994608baa3bbb50d42f19073


---

# Instructies: Azure Portal gebruiken voor het configureren van RMS-verificatie

Verificatie met Azure RMS voor uw app met Azure Active Directory Authentication Library (ADAL).

Als u deze methode gebruikt, moet uw toepassing zelf de OAuth-verificatie beheren. Met deze methode oefent de RMS-client een door de toepassing gedefinieerde callback uit wanneer verificatie vereist is.

## Configureren via Azure Portal
Volg eerst deze handleiding voor het configureren via Azure Portal: [Azure RMS configureren voor ADAL verificatie](adal-auth.md). Zorg ervoor dat u de *client-id* en *omleidings-URI* uit dit proces kopieert en opslaat voor later gebruik.

## Voorbeeld van code
Het volgende codefragment is afkomstig uit een groter voorbeeld van code voor mobiele clients waarmee u Azure ADAL kunt inschakelen. Zie het volledige voorbeeld op [MSIPCSampleApp](https://github.com/AzureAD/rms-sdk-ui-for-android/tree/master/samples/MsipcSampleApp) voor meer informatie

       /**
       * Instantiates a new rms authentication callback.
       *
       * @param parentActivity the parent activity
       * @throws NoSuchAlgorithmException the no such algorithm exception
       * @throws InvalidKeySpecException the invalid key spec exception
       * @throws UnsupportedEncodingException the unsupported encoding exception
       */

       public MsipcAuthenticationCallback(Activity parentActivity) throws NoSuchAlgorithmException, InvalidKeySpecException, UnsupportedEncodingException
       {
         mParentActivity = parentActivity;
         setADALKeyStore();

         /**
         * Note: Following values of are client_id and redirect_uri are for demo purpose only.
         * Your values will come from the preceeding Azure Portal process.
         */
         mClientId = "com.microsoft.rightsmanagement.sampleapp";
         mRedirectURI = mClientId + "://authorize";
       }


## Verwante onderwerpen

- [MSIPCSampleApp](https://github.com/AzureAD/rms-sdk-ui-for-android/tree/master/samples/MsipcSampleApp)
- [Azure RMS configureren voor ADAL-verificatie](adal-auth.md)



<!--HONumber=Jun16_HO4-->


