---
title: Aanmelden voor een gratis proefversie van 30 dagen | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: aanmelden voor Intune op Azure.'
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 01/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cd98141b4b377f0013607f2a2ebb93a93cd7f0ce
ms.openlocfilehash: ce69e7efbee286839a1bf3440db692bd237b0e06


---

# <a name="sign-up-for-a-microsoft-intune-free-trial-for-the-azure-portal-preview"></a>Aanmelden voor een gratis proefversie van Microsoft Intune voor de preview-versie van Azure Portal

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Dit artikel begeleidt u bij het aanmelden voor een proefversie van de zelfstandige versie van Intune voor de preview-versie van Azure Portal. <!---and prepares your trial with some users so that you can then follow the associated evaluation guide to see how Intune manages mobile devices. ---> <!---or app data when devices are not enrolled in Intune.--->

<!--- ## Assumptions
This sign-up article and the evaluation guide assume you are using the trial for evaluation purposes only and intend to start with a clean environment when you subscribe.

To make it easy for you to get started with the trial, we are setting up a very simple environment that uses only Intune and assumes it will be your sole method of managing devices (known as the mobile device management authority). However, throughout the guide we will point you to deeper technical content if you want to explore farther.

You can do everything in the trial version that you can do in a subscription version; the only difference is you are limited to 100 user accounts in the trial.--->

<!--- ## Sign up for your trial--->
1. Ga naar de [registratiepagina voor Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) en vul het formulier in om u aan te melden voor een proefabonnement.

 <!--- If you have a work or school account and want to use that for your Intune trial, follow [these sign-in instructions](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-1) instead. However, this article assumes that you are not using such an account.---><br/> ![Afbeelding van de registratiepagina](./media/1-clicking-try.png)

 > [!TIP]
> Als de landinstellingen voor de meeste IT-activiteiten en van de meeste gebruikers afwijkt van die van u, kunt u de desbetreffende landinstellingen selecteren onder **Where's your company located?** (Waar bevindt uw bedrijf zich?).

2. Aan het einde van het aanmeldingsproces krijgt u een bericht met de gegevens van uw nieuwe account. <br/> ![Afbeelding van accountgegevens](./media/2-end-of-sign-up-process.png) <br/>Als u nu klikt op **You're ready to go** (U bent klaar om aan de slag te gaan), wordt u naar het Office 365-beheercentrum geleid, waar u gebruikers aan uw testomgeving kunt toevoegen. <br/><br/>Als u rechtstreeks naar de preview-versie van Intune Azure Portal wilt gaan, opent u een nieuw browservenster en voert u **https://portal.azure.com** in de adresbalk in. U wordt dan geleid naar de aanmeldingspagina van Azure waar u de referenties kunt opgeven die u hebt ontvangen om u aan te melden. Gebruik dit adres altijd als u zich wilt aanmelden voor de Intune-proefversie. <br/> ![Afbeelding van de aanmeldingspagina van de Azure Portal](./media/azure-portal-signin.png)

De eerste keer dat u zich bij Intune Azure Preview aanmeldt, wordt Intune nog niet weergegeven in het Azure-dashboard. De Intune-service aan uw Azure-dashboard toevoegen:
1. Kies **Meer services >** in de lijst met Azure-services links van het dashboard en voer **Intune** in het zoekvak in.
2. Kies **Intune** uit de lijst en selecteer de ster om de service toe te voegen aan de lijst met services.<br/> ![Afbeelding van het selecteren van Intune uit de lijst met services](./media/azure-add-intune1.png)
3. Kies vervolgens **Intune** in de lijst met services om het Intune-dashboard te openen.

Wanneer u zich aanmeldt voor een proefversie, ontvangt u tevens een e-mailbericht met gegevens over uw account op het e-mailadres dat u hebt opgegeven tijdens het aanmeldingsproces. In deze e-mail wordt bevestigd dat uw proefversie actief is.


<!--- ## Add users
Before you leave the Office 365 Admin center for Intune, you need to add some users to your trial account.

In the Office 365 Admin center, you can add users individually or in bulk by uploading a .csv file. We will do both to set up your trial. However, in your production environment, you will probably want to take advantage of your Azure Active Directory user accounts, which you can learn more about in our [Getting Started guide](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) and in the [Next steps](#Next-steps) section of this article.

### Add an individual user
1. Choose either of the options to add a use to open a form that allows you to create a user. Only the items starred with an asterisk (\*) are required.
![Image of add user button options](./media/sign-up/add-user.png)


2.  When you add the user, the final step will be to send the user an email with their temporary Intune password. For the purposes of this evaluation, use your own work email address so you will receive the log-on information and see the email your users will get. You can then use these user identities to enroll test devices.<br/>

 ![Image of add user final step](./media/sign-up/new-user-2.png)

3. If you want to assign a user an admin role after you create it, you can edit the role in the Office 365 Admin center by selecting the user name from your list of users, and then choosing **Edit** in the Role line to see the list of user roles you can select from and assign to that user.

 ![Image of user  role options](./media/sign-up/change-user-role.png)

### Import multiple users
1. You will find the wizard for importing multiple users in the **More** list.

 ![Image of option to add multiple users](./media/sign-up/add-multiple-users.png)

2. To help you set up your .csv file correctly, you can download a template file to populate with your user data. Download the .csv file that contains headers and sample user information to see exactly the kind of data is needed for each field.

 ![Image of first step in bulk enrollment wizard](./media/sign-up/bulk-enroll-step-1.png)


3. After you’ve created and saved your .csv file, choose **Browse** to select the file. Verify, and choose **Next**. Your users will be uploaded and added to your list of active users.

> [!NOTE]
> Your users won't show up in Intune until they've enrolled a device to be managed.

Now it’s time to head over to Intune to start managing your users, their devices, and their apps.--->

## <a name="keeping-the-admin-experiences-straight"></a>Zorg voor een juiste werkwijze voor beheer
<!---### Classic Intune
There are two portals you will use for classic Intune:
- The Office 365 Admin center ([portal.office.com](https://portal.office.com))
- The Intune administration console ([manage.microsoft.com](https://manage.microsoft.com))

Normally, you’ll do your work in the Intune administration console, shown below. This is the site where you set up and manage your groups, policies, devices, and apps.

![Image of Intune administration console](./media/sign-up/intune-admin-console.png)

However, you will use the Office 365 Admin center, shown below, to add and manage your users and other aspects of your account, including billing and support.

![Image of Office 365 Admin center](./media/sign-up/office-admin-center.png)

You can navigate from the Office 365 Admin center to the Intune admin console. The admin centers are under the last item in the left navigation pane. Choose **Intune** to open the Intune admin console in a new tab.

![Image of link to Intune administration console](./media/sign-up/link-to-intune.png)

To get from Intune back to the Office 365 Admin center, choose the **Add Users** task on the Groups Overview page.

![Image of link back to Office 365  Admin center](./media/sign-up/task-add-users.png)--->

<!---### Intune Azure preview--->
Er zijn drie portals die u kunt gebruik voor Intune Azure Preview:
- Het Intune-dashboard in Azure ([portal.azure.com](https://portal.azure.com)) waar u de [mogelijkheden van Intune in de Azure Portal](what-is-microsoft-intune.md) kunt bekijken.
- Het Office 365-beheercentrum ([portal.office.com](https://portal.office.com)) waar u gebruikers kunt toevoegen en beheren als u Azure Active Directory hiervoor niet gebruikt. U kunt ook andere aspecten van uw account beheren, zoals facturering en ondersteuning.
- De klassieke Intune-beheerconsole ([manage.microsoft.com](https://manage.microsoft.com)) waar u de functies kunt bekijken die nog niet aan Azure zijn toegevoegd.

Doorgaans voert u uw werkzaamheden uit in het Intune-dashboard, dat hieronder wordt weergegeven. Dit is de site waar u uw groepen, beleid, apparaten en apps instelt en beheert.

U kunt vanuit het dashboard naar de klassieke Intune-beheerconsole gaan door de tegel **Klassieke Intune-portal openen** te kiezen.

Voer https://portal.azure.com in de adresbalk van uw browser in om terug te keren naar Intune Azure Preview en kies nogmaals **Intune** in de lijst met services.

 ![Afbeelding van Intune-dashboard](./media/intune-azure-dashboard.png)


U gebruikt het Office 365-beheercentrum (zie hieronder) echter om gebruikers en andere aspecten van uw account toe te voegen en te beheren, met inbegrip van de facturering en ondersteuning.

![Afbeelding van het Office 365-beheercentrum](./media/office-admin-center.png)

Als u van het Office 365-beheercentrum naar het Intune-dashboard wilt gaan, voert u https://portal.azure.com in de adresbalk van uw browser in. Kies **Intune** in de lijst met services.

U vanuit Intune wilt terugkeren naar het Office 365-beheercentrum, voert u https://portal.office.com in de adresbalk van uw browser in. Als u al bent aangemeld bij Intune, gaat u rechtstreeks naar het Office 365-beheercentrum.

## <a name="next-steps"></a>Volgende stappen

### <a name="intune-azure-preview"></a>Intune Azure Preview
Meer informatie over [Intune in Azure Preview Portal](what-is-microsoft-intune.md)
### <a name="classic-intune"></a>Klassieke versie van Intune
Evaluatiescenario: [Mobile Device Management evalueren in Microsoft Intune](https://docs.microsoft.com/intune/understand-explore/mobile-device-management-trial-guide-microsoft-intune)

### <a name="integration-with-other-products"></a>Integratie met andere producten
Meer informatie over het gebruik van uw Azure Active Directory-gebruikersaccounts met Intune:
- [Identiteitsvereisten](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [Adreslijstsynchronisatie](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Vereisten voor Multi-factor Authentication](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

Meer informatie over het gebruik van [Intune met System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management)



<!--HONumber=Feb17_HO1-->


