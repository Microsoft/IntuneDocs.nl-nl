---
title: 'Procedure: ingebouwde rechten gebruiken| Azure RMS'
description: Bevat een overzicht van de ingebouwde rechten die RMS SDK 4.2 biedt en de gebruiksbeperkingen die een app moet afdwingen bij het naleven van deze beperkingen.
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 9142dd29-f1f4-4c2f-82ac-534f14b8bba1
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
experiment_id: priyamo-TableVsFlatList-20160805
translationtype: Human Translation
ms.sourcegitcommit: 024a29d7c7db2e4c0578a95c93e22f8e7a5b173e
ms.openlocfilehash: d644f8aac4999baf4aadfbda2d936359bc235c31


---

# Procedure: ingebouwde rechten gebruiken

Dit onderwerp bevat een overzicht van de ingebouwde rechten die de Microsoft Rights Management SDK 4.2 biedt en van de gebruiksbeperkingen die een app moet afdwingen bij het naleven van deze beperkingen. In de onderstaande tabel ziet u de ingebouwde rechten; algemene rechten, rechten voor bewerkbare documenten en e-mailadresrechten, gevolgd door een beschrijving en hun waarden per besturingssysteem.

**Opmerking**: zie voor de Linux-SDK het bronbestand *rights.h* voor meer informatie.

## Algemene rechten ##

| Rechts | Beschrijving | Android | iOS en OS X | Windows Store en Windows Phone | Linux |
|-------|-------------|---------|-------------|---------------------------------|-------|
| **Alle** | Een verzameling van alle algemene rechten. | [CommonRights.All](/rights-management/sdk/4.2/api/android/commonrights#msipcthin2_commonrights_class_java_ALL) | [MSCommonRights owner](/rights-management/sdk/4.2/api/iOS/mscommonrights#msipcthin2_mscommonrights_interface_objc___NSString__owner_)| [CommonRights.All</strong>](/rights-management/sdk/4.2/api/winrt/commonrights#msipcthin2_commonrights)| [CommonRights::All](http://azuread.github.io/rms-sdk-for-cpp/classrmscore_1_1modernapi_1_1CommonRights.html)|
| **Eigenaar**| Hiermee wordt volledige controle over de beveiligde inhoud geboden |  [CommonRights.Owner](/rights-management/sdk/4.2/api/android/commonrights#msipcthin2_commonrights_class_java_Owner) |[MSCommonRights owner](/rights-management/sdk/4.2/api/iOS/mscommonrights#msipcthin2_mscommonrights_interface_objc___NSString__owner_) |[CommonRights.Owner](/rights-management/sdk/4.2/api/winrt/commonrights#msipcthin2_commonrights_owner) |  [CommonRights::Owner](http://azuread.github.io/rms-sdk-for-cpp/classrmscore_1_1modernapi_1_1CommonRights.html)|
| **Geef** | Het recht om beveiligde inhoud weer te geven. Als dit recht is verleend, kan de gebruiker doorgaans beveiligde inhoud openen en bekijken. Er zijn echter aanvullende rechten vereist voor het wijzigen, uitpakken, doorsturen of opslaan van de inhoud. |  [CommonRights.View](/rights-management/sdk/4.2/api/android/commonrights#msipcthin2_commonrights_class_java_View) | [MSCommonRights view](/rights-management/sdk/4.2/api/iOS/mscommonrights#msipcthin2_mscommonrights_interface_objc___NSString__owner_)|[CommonRights.View](/rights-management/sdk/4.2/api/android/commonrights#msipcthin2_commonrights_class_java_View) | [CommonRights::View](http://azuread.github.io/rms-sdk-for-cpp/classrmscore_1_1modernapi_1_1CommonRights.html) |


## Rechten voor bewerkbare documenten ##

| Rechts | Beschrijving | Android | iOS en OS X | Windows Store en Windows Phone | Linux |
|-------|-------------|---------|-------------|---------------------------------|-------|
| **Alle** | Een verzameling die alle rechten voor bewerkbare documenten bevat.| [EditableDocumentRights.All](/rights-management/sdk/4.2/api/android/editabledocumentrights#msipcthin2_editabledocumentrights_class_java_ALL) | [MSEditableDocumentRights all](/rights-management/sdk/4.2/api/iOS/mseditabledocumentrights#msipcthin2_mseditabledocumentrights_interface_objc) | [EditableDocumentRights.All](/rights-management/sdk/4.2/api/winrt/editabledocumentrights#msipcthin2_editabledocumentrights_all) |[EditableDocumentRights::All](http://azuread.github.io/rms-sdk-for-cpp/classrmscore_1_1modernapi_1_1EditableDocumentRights.html)|
| **Opmerking** | Het recht om opmerkingen toe te voegen aan het document. | [EditableDocumentRights.Comment](/rights-management/sdk/4.2/api/android/editabledocumentrights#msipcthin2_editabledocumentrights_class_java_Comment)|[MSEditableDocumentRights comment](/rights-management/sdk/4.2/api/iOS/mseditabledocumentrights#msipcthin2_mseditabledocumentrights_interface_objc) |[EditableDocumentRights.Comment](/rights-management/sdk/4.2/api/winrt/editabledocumentrights#msipcthin2_editabledocumentrights__comment)| [EditableDocumentRights::Comment](http://azuread.github.io/rms-sdk-for-cpp/classrmscore_1_1modernapi_1_1EditableDocumentRights.html)|
| **Bewerken** | Het recht om beveiligde inhoud te bewerken en op te slaan in dezelfde beveiligde indeling. Als dit recht is verleend, kan de gebruiker normaal gesproken beveiligde inhoud wijzigen en vervolgens opslaan in hetzelfde bestand. | [EditableDocumentRights.Edit](/rights-management/sdk/4.2/api/android/editabledocumentrights#msipcthin2_editabledocumentrights_class_java_Edit) | [MSEditableDocumentRights edit](/rights-management/sdk/4.2/api/iOS/mseditabledocumentrights#msipcthin2_mseditabledocumentrights_interface_objc) | [EditableDocumentRights.Edit](/rights-management/sdk/4.2/api/winrt/editabledocumentrights#msipcthin2_editabledocumentrights_edit) | [EditableDocumentRights::Edit](http://azuread.github.io/rms-sdk-for-cpp/classrmscore_1_1modernapi_1_1EditableDocumentRights.html) |
| **Exporteren** | Het recht om inhoud te extraheren uit een beveiligde indeling en deze in een andere door AD RMS beveiligde indeling te plaatsen. Als dit recht is verleend, kan de gebruiker doorgaans beveiligde inhoud opslaan naar andere indelingen met AD RMS-beveiliging, bijvoorbeeld, als de toepassing een functie *Opslaan als* heeft. | [EditableDocumentRights.Export](/rights-management/sdk/4.2/api/android/editabledocumentrights#msipcthin2_editabledocumentrights_class_java_Export) | [MSEditableDocumentRights exportable](/rights-management/sdk/4.2/api/iOS/mseditabledocumentrights#msipcthin2_mseditabledocumentrights_interface_objc) |[EditableDocumentRights.Export](/rights-management/sdk/4.2/api/winrt/editabledocumentrights#msipcthin2_editabledocumentrights_export) | [EditableDocumentRights::Export](http://azuread.github.io/rms-sdk-for-cpp/classrmscore_1_1modernapi_1_1EditableDocumentRights.html)|
| **Uitpakken** | Het recht om inhoud op te halen uit een beveiligde indeling en deze in een niet-beveiligde indeling te plaatsen. Als dit recht is verleend, kan de gebruiker doorgaans gegevens uit beveiligde inhoud kopiëren en plakken. Als de app een functie <em>Opslaan als</em> heeft, kan de gebruiker mogelijk ook beveiligde inhoud opslaan in onbeveiligde indelingen en andere beveiligde indelingen. Dit recht heeft dezelfde waarde als het uitpakrecht voor e-mailadres. |  [EditableDocumentRights.Extract](/rights-management/sdk/4.2/api/android/editabledocumentrights#msipcthin2_editabledocumentrights_class_java_Extract) |[MSEditableDocumentRights extract](/rights-management/sdk/4.2/api/iOS/mseditabledocumentrights#msipcthin2_mseditabledocumentrights_interface_objc) | [EditableDocumentRights.Extract](/rights-management/sdk/4.2/api/winrt/editabledocumentrights#msipcthin2_editabledocumentrights_extract) |  [EditableDocumentRights::Extract](http://azuread.github.io/rms-sdk-for-cpp/classrmscore_1_1modernapi_1_1EditableDocumentRights.html)|
| **Afdrukken** | Het recht om beveiligde inhoud af te drukken. Als dit recht is verleend, kan de gebruiker doorgaans beveiligde inhoud afdrukken. Dit recht heeft dezelfde waarde als het afdrukrecht voor e-mail. | [EditableDocumentRights.Print](/rights-management/sdk/4.2/api/android/editabledocumentrights#msipcthin2_editabledocumentrights_class_java_Print) |  [MSEditableDocumentRights print](/rights-management/sdk/4.2/api/iOS/mseditabledocumentrights#msipcthin2_mseditabledocumentrights_interface_objc)| [EditableDocumentRights.Print](/rights-management/sdk/4.2/api/winrt/editabledocumentrights#msipcthin2_editabledocumentrights_print) | [EditableDocumentRights::Print](http://azuread.github.io/rms-sdk-for-cpp/classrmscore_1_1modernapi_1_1EditableDocumentRights.html)|
 

## E-mailrechten ##

| Rechts | Beschrijving | Android | iOS en OS X | Windows Store en Windows Phone | Linux |
|-------|-------------|---------|-------------|---------------------------------|-------|
| **Alle** |Een verzameling die alle e-mailrechten bevat. |  [EmailRights.All](/rights-management/sdk/4.2/api/android/emailrights#msipcthin2_emailrights_class_java_ALL) | [MSEmailRights all](/rights-management/sdk/4.2/api/iOS/msemailrights#msipcthin2_msemailrights_interface_objc) | [EmailRights.All](/rights-management/sdk/4.2/api/winrt/emailrights#msipcthin2_emailrights_all)|[EmailRights::All](http://azuread.github.io/rms-sdk-for-cpp/classrmscore_1_1modernapi_1_1EmailRights.html)|
| **Uitpakken** | Het recht om inhoud op te halen uit een beveiligde indeling en deze in een niet-beveiligde indeling te plaatsen. Als dit recht is verleend, kan de ontvanger van een e-mail doorgaans gegevens uit een beveiligd bericht kopiëren en plakken. Als de app een functie <em>Opslaan als</em> heeft, kan de ontvanger mogelijk ook beveiligde inhoud opslaan naar onbeveiligde indelingen en andere beveiligde indelingen. Dit recht heeft dezelfde waarde als het uitpakrecht voor bewerkbare documenten. | [EmailRights.Extract](/rights-management/sdk/4.2/api/android/emailrights#msipcthin2_emailrights_class_java_Extract) | [MSEmailRights extract](/rights-management/sdk/4.2/api/iOS/msemailrights#msipcthin2_msemailrights_interface_objc) | [EmailRights.Extract</strong>](/rights-management/sdk/4.2/api/winrt/emailrights#msipcthin2_emailrights_extract) | [EmailRights::Extract](http://azuread.github.io/rms-sdk-for-cpp/classrmscore_1_1modernapi_1_1EmailRights.html) |
|**Doorsturen**| Het recht om een beveiligd bericht door te sturen. Als dit recht is verleend, kan de ontvanger van een e-mail doorgaans een beveiligd bericht doorsturen.| [<strong>EmailRights.Forward</strong>](/rights-management/sdk/4.2/api/android/emailrights#msipcthin2_emailrights_class_java_Forward) | [MSEmailRights forward](/rights-management/sdk/4.2/api/iOS/msemailrights#msipcthin2_msemailrights_interface_objc) | [EmailRights.Forward](/rights-management/sdk/4.2/api/winrt/emailrights#msipcthin2_emailrights_forward) | [EmailRights::Forward](http://azuread.github.io/rms-sdk-for-cpp/classrmscore_1_1modernapi_1_1EmailRights.html) |
|**Afdrukken** | Het recht om beveiligde inhoud af te drukken. Als dit recht is verleend, kan de ontvanger van een e-mail doorgaans een beveiligd bericht afdrukken. Dit recht heeft dezelfde waarde als het afdrukrecht voor bewerkbare documenten. | [EmailRights.Print](/rights-management/sdk/4.2/api/android/emailrights#msipcthin2_emailrights_class_java_Print) |[MSEmailRights print](/rights-management/sdk/4.2/api/iOS/msemailrights#msipcthin2_msemailrights_interface_objc) | [EmailRights.Print](/rights-management/sdk/4.2/api/winrt/emailrights#msipcthin2_emailrights_print) | [EmailRights::Print](http://azuread.github.io/rms-sdk-for-cpp/classrmscore_1_1modernapi_1_1EmailRights.html)|
| **Beantwoorden** | Als dit recht is verleend, kan de ontvanger van een e-mail gewoonlijk een beveiligd bericht beantwoorden en een kopie van het oorspronkelijke bericht opnemen. | [EmailRights.Reply](/rights-management/sdk/4.2/api/android/emailrights#msipcthin2_emailrights_class_java_Reply) | [MSEmailRights reply](/rights-management/sdk/4.2/api/iOS/msemailrights#msipcthin2_msemailrights_interface_objc) | [EmailRights.Reply](/rights-management/sdk/4.2/api/winrt/emailrights#msipcthin2_emailrights_reply) | [EmailRights::Reply](http://azuread.github.io/rms-sdk-for-cpp/classrmscore_1_1modernapi_1_1EmailRights.html)|
| **ReplyAll** | Als dit recht is verleend, kan de ontvanger van een e-mail gewoonlijk alle ontvangers van een beveiligd bericht beantwoorden en een kopie van het oorspronkelijke bericht opnemen. | [EmailRights.ReplyAll</strong>](/rights-management/sdk/4.2/api/android/emailrights#msipcthin2_emailrights_class_java_ReplyAll) | [MSEmailRights replyAll](/rights-management/sdk/4.2/api/iOS/msemailrights#msipcthin2_msemailrights_interface_objc) | [EmailRights.ReplyAll](/rights-management/sdk/4.2/api/winrt/emailrights#msipcthin2_emailrights_replyall) | [EmailRights::ReplyAll](http://azuread.github.io/rms-sdk-for-cpp/classrmscore_1_1modernapi_1_1EmailRights.html)|



<!--HONumber=Aug16_HO4-->


