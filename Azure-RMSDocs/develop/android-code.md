---
title: Voorbeelden van Android-code | Azure RMS
description: In dit onderwerp vindt u belangrijke code-elementen voor de Android-versie van de RMS SDK.
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 58CC2E50-1E4D-4621-A947-25312C3FF519
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 024a29d7c7db2e4c0578a95c93e22f8e7a5b173e
ms.openlocfilehash: aabb3d79049c257cc979e929aa5ed9bbc4673cde


---

# Voorbeelden van Android-code

In dit onderwerp vindt u belangrijke code-elementen voor de Android-versie van de RMS SDK.

**Opmerking** In de voorbeeldcode en beschrijvingen die volgen, gebruiken we de term MSIPC (Microsoft Information Protection en Control) om te verwijzen naar het clientproces.


## De Microsoft Rights Management SDK 4.2 gebruiken: belangrijkste scenario's

Hieronder vindt u codevoorbeelden uit een grotere voorbeeldtoepassing. Deze representeren ontwikkelingsscenario’s die belangrijk zijn voor uw begrip van deze SDK. De voorbeelden laten het volgende zien: het gebruik van de door Microsoft beveiligde bestandsindeling waarnaar wordt verwezen als beveiligd bestand, het gebruik van aangepaste beveiligde bestandsindelingen en het gebruik van aangepaste UI-besturingselementen.



Voor gebruik met deze SDK voor het Android-besturingssysteem is de voorbeeldtoepassing *MSIPCSampleApp* beschikbaar. Zie [rms-sdk-ui-for-android](https://github.com/AzureAD/rms-sdk-ui-for-android) op GitHub voor toegang tot deze voorbeeldtoepassing.

### Scenario: een met RMS beveiligd bestand gebruiken

-   **Stap 1**: maak een [**ProtectedFileInputStream**](/rights-management/sdk/4.2/api/android/com.microsoft.rightsmanagement#msipcthin2_protectedfileinputstream_class_java).

    **Bron**: *MsipcAuthenticationCallback.java*

    **Beschrijving**: maak een [**ProtectedFileInputStream**](/rights-management/sdk/4.2/api/android/com.microsoft.rightsmanagement#msipcthin2_protectedfileinputstream_class_java)-object via de methode waarmee de serviceverificatie wordt geïmplementeerd met behulp van de [**AuthenticationRequestCallback**](/rights-management/sdk/4.2/api/android/com.microsoft.rightsmanagement#msipcthin2_authenticationrequestcallback_interface_java) om een token op te halen door een exemplaar van **AuthenticationRequestCallback**, als de parameter *mRmsAuthCallback*, door te geven aan de MSIPC-API. Zie de aanroep aan [**ProtectedFileInputStream.create**](/rights-management/sdk/4.2/api/android/protectedfileinputstream#msipcthin2_protectedfileinputstream_create_method) aan het einde van de volgende sectie met voorbeeldcode.

        public void startContentConsumptionFromPtxtFileFormat(InputStream inputStream)
        {
            CreationCallback<ProtectedFileInputStream> protectedFileInputStreamCreationCallback =
              new CreationCallback<ProtectedFileInputStream>()
            {
                @Override
                public Context getContext()
                {
                   …
               }

                @Override
                public void onCancel()
                {
                   …
                }

                @Override
                public void onFailure(ProtectionException e)
                {
                   …
                }

                @Override
                public void onSuccess(ProtectedFileInputStream protectedFileInputStream)
                {
                   …
                   …
                    byte[] dataChunk = new byte[16384];
                    try
                    {
                        while ((nRead = protectedFileInputStream.read(dataChunk, 0,
                                dataChunk.length)) != -1)
                        {
                            …
                        }
                         …
                        protectedFileInputStream.close();
                    }
                    catch (IOException e)
                    {
                      …
                    }  
              }
            };
            try
            {
               …
                ProtectedFileInputStream.create(inputStream, null, mRmsAuthCallback,
                                                PolicyAcquisitionFlags.NONE,
                                                protectedFileInputStreamCreationCallback);
            }
            catch (com.microsoft.rightsmanagement.exceptions.InvalidParameterException e)
            {
                …
            }
        }


-   **Stap 2**: stel verificatie in met behulp van de Active Directory Authentication Library (ADAL).

    **Bron**: *MsipcAuthenticationCallback.java*.

    **Beschrijving**: in deze stap ziet u hoe de ADAL wordt gebruikt voor het implementeren van een [**AuthenticationRequestCallback**](/rights-management/sdk/4.2/api/android/com.microsoft.rightsmanagement#msipcthin2_authenticationrequestcallback_interface_java) met voorbeeldverificatieparameters. Zie voor meer informatie over het gebruik van ADAL [Azure AD Authentication Library (ADAL)](https://msdn.microsoft.com/library/jj573266.aspx).


        class MsipcAuthenticationCallback implements AuthenticationRequestCallback
        {

        …

        @Override
        public void getToken(Map<String, String> authenticationParametersMap,
                             final AuthenticationCompletionCallback authenticationCompletionCallbackToMsipc)
        {
            String authority = authenticationParametersMap.get("oauth2.authority");
            String resource = authenticationParametersMap.get("oauth2.resource");
            String userId = authenticationParametersMap.get("userId");
            final String userHint = (userId == null)? "" : userId;
            AuthenticationContext authenticationContext = App.getInstance().getAuthenticationContext();
            if (authenticationContext == null || !authenticationContext.getAuthority().equalsIgnoreCase(authority))
            {
                try
                {
                    authenticationContext = new AuthenticationContext(App.getInstance().getApplicationContext(), authority, …);
                    App.getInstance().setAuthenticationContext(authenticationContext);
                }
                catch (NoSuchAlgorithmException e)
                {
                    …
                    authenticationCompletionCallbackToMsipc.onFailure();
                }
                catch (NoSuchPaddingException e)
                {
                    …
                    authenticationCompletionCallbackToMsipc.onFailure();
                }
           }
            App.getInstance().getAuthenticationContext().acquireToken(mParentActivity, resource, mClientId, mRedirectURI, userId, mPromptBehavior,
                           "&USERNAME=" + userHint, new AuthenticationCallback<AuthenticationResult>()
                            {
                                @Override
                                public void onError(Exception exc)
                                {
                                    …
                                    if (exc instanceof AuthenticationCancelError)
                                    {
                                         …
                                        authenticationCompletionCallbackToMsipc.onCancel();
                                    }
                                    else
                                    {
                                         …
                                        authenticationCompletionCallbackToMsipc.onFailure();
                                    }
                                }

                                @Override
                                public void onSuccess(AuthenticationResult result)
                                {
                                    …
                                    if (result == null || result.getAccessToken() == null
                                            || result.getAccessToken().isEmpty())
                                    {
                                         …
                                    }
                                    else
                                    {
                                        // request is successful
                                        …
                                        authenticationCompletionCallbackToMsipc.onSuccess(result.getAccessToken());
                                    }
                                }
                            }

                            );
                      }


-   **Stap 3**: controleer via de [**accessCheck**](/rights-management/sdk/4.2/api/android/userpolicy#msipcthin2_userpolicy_accesscheck_method_java)-methode van [**UserPolicy**](/rights-management/sdk/4.2/api/android/userpolicy) of deze gebruiker met deze inhoud beschikt over het recht **Bewerken**.

    **Bron**: *TextEditorFragment.java*


         //check if user has edit rights and apply enforcements
                if (!mUserPolicy.accessCheck(EditableDocumentRights.Edit))
                {
                    mTextEditor.setFocusableInTouchMode(false);
                    mTextEditor.setFocusable(false);
                    mTextEditor.setEnabled(false);
                    …
                }


### Scenario: een nieuw beveiligd bestand maken met behulp van een sjabloon

Dit scenario begint met het ophalen van een lijst met sjablonen, waarbij de eerste wordt geselecteerd om een beleid te maken en vervolgens het nieuwe beveiligde bestand wordt gemaakt en ernaar wordt geschreven.

-   **Stap 1**: haal een lijst met sjablonen op via een [**TemplateDescriptor**](/rights-management/sdk/4.2/api/android/templatedescriptor#msipcthin2_templatedescriptor_class_java)-object.

    **Bron**: *MsipcTaskFragment.java*



    CreationCallback<List<TemplateDescriptor>> getTemplatesCreationCallback = new CreationCallback<List<TemplateDescriptor>>() { @Override public Context getContext() { …
          }

          @Override
          public void onCancel()
          {
              …
          }

          @Override
          public void onFailure(ProtectionException e)
          {
              …
          }

          @Override
          public void onSuccess(List<TemplateDescriptor> templateDescriptors)
          {
             …
          }
      }; try { …
          mIAsyncControl = TemplateDescriptor.getTemplates(emailId, mRmsAuthCallback, getTemplatesCreationCallback); } catch (com.microsoft.rightsmanagement.exceptions.InvalidParameterException e) { …
      }


-    **Stap 2**: maak met behulp van de eerste sjabloon in de lijst een [**UserPolicy**](/rights-management/sdk/4.2/api/android/userpolicy).

    **Bron**: *MsipcTaskFragment.java*



      CreationCallback<UserPolicy> userPolicyCreationCallback = new CreationCallback<UserPolicy>() { @Override public Context getContext() { …
          }

          @Override
          public void onCancel()
          {
              …
          }

          @Override
          public void onFailure(ProtectionException e)
          {
              …
          }

          @Override
          public void onSuccess(final UserPolicy item)
          {
              …
          }
      }; try { …
          mIAsyncControl = UserPolicy.create((TemplateDescriptor)selectedDescriptor, mEmailId, mRmsAuthCallback, UserPolicyCreationFlags.NONE, userPolicyCreationCallback); …
      } catch (InvalidParameterException e) { …
      }


-    **Stap 3**: maak een [**ProtectedFileOutputStream**](/rights-management/sdk/4.2/api/android/protectedfileoutputstream#msipcthin2_protectedfileoutputstream_class_java) en schrijf er inhoud naartoe.

    **Bron**: *MsipcTaskFragment.java*


    private void createPTxt(final byte[] contentToProtect) { …
            CreationCallback<ProtectedFileOutputStream> protectedFileOutputStreamCreationCallback = new CreationCallback<ProtectedFileOutputStream>() { @Override public Context getContext() { …
                }

                @Override
                public void onCancel()
                {
                 …
                }

                @Override
                public void onFailure(ProtectionException e)
                {
                 …
                }

                @Override
                public void onSuccess(ProtectedFileOutputStream protectedFileOutputStream)
                {
                    try
                    {
                        // write to this stream
                        protectedFileOutputStream.write(contentToProtect);
                        protectedFileOutputStream.flush();
                        protectedFileOutputStream.close();
                        …
                    }
                    catch (IOException e)
                    {
                        …
                    }
                }
            };
            try
            {
                File file = new File(filePath);
                outputStream = new FileOutputStream(file);
                mIAsyncControl = ProtectedFileOutputStream.create(outputStream, mUserPolicy, originalFileExtension,
                        protectedFileOutputStreamCreationCallback);
            }
            catch (FileNotFoundException e)
            {
                 …
            }
            catch (InvalidParameterException e)
            {
                 …
            }
        }



### Scenario: een aangepast beveiligd bestand openen

-   **Stap 1**: maak op basis van een *serializedContentPolicy* een [**UserPolicy**](/rights-management/sdk/4.2/api/android/userpolicy).

    **Bron**: *MsipcTaskFragment.java*


    CreationCallback<UserPolicy> userPolicyCreationCallbackFromSerializedContentPolicy = new CreationCallback<UserPolicy>() { @Override public void onSuccess(UserPolicy userPolicy) { …
                }

                @Override
                public void onFailure(ProtectionException e)
                {
                  …
                }

                @Override
                public void onCancel()
                {
                  …
                }

                @Override
                public Context getContext()
                {
                  …
                }
            };


    try {   ...

      // serializedContentPolicyLength lezen uit inputStream.
      long serializedContentPolicyLength = readUnsignedInt(inputStream);

      // PL-bytes lezen uit de invoerstroom met behulp van de PL-grootte.
      byte[] serializedContentPolicy = new byte[(int)serializedContentPolicyLength]; inputStream.read(serializedContentPolicy);

      ...

      UserPolicy.acquire(serializedContentPolicy, null, mRmsAuthCallback, PolicyAcquisitionFlags.NONE,           userPolicyCreationCallbackFromSerializedContentPolicy); } catch (com.microsoft.rightsmanagement.exceptions.InvalidParameterException e) {   ... } catch (IOException e) {   ... }



-    **Stap 2**: maak met behulp van de [**UserPolicy**](/rights-management/sdk/4.2/api/android/userpolicy) uit **stap 1** een [**CustomProtectedInputStream**](/rights-management/sdk/4.2/api/android/customprotectedinputstream#msipcthin2_customprotectedinputstream_class_java).

    **Bron**: *MsipcTaskFragment.java*



      CreationCallback<CustomProtectedInputStream> customProtectedInputStreamCreationCallback = new CreationCallback<CustomProtectedInputStream>() { @Override public Context getContext() { …
         }

         @Override
         public void onCancel()
         {
             …
         }

         @Override
         public void onFailure(ProtectionException e)
         {
             …
         }

         @Override
         public void onSuccess(CustomProtectedInputStream customProtectedInputStream)
         {
            …

             byte[] dataChunk = new byte[16384];
             try
             {
                 while ((nRead = customProtectedInputStream.read(dataChunk, 0, dataChunk.length)) != -1)
                 {
                      …
                 }
                  …
                 customProtectedInputStream.close();
             }
             catch (IOException e)
             {
                …
             }
             …
         }
     };

    try {  ...

      // De grootte van de versleutelde inhoud ophalen.
      long encryptedContentLength = readUnsignedInt(inputStream);

      updateTaskStatus(new TaskStatus(TaskState.Starting, "Consuming content", true));

      CustomProtectedInputStream.create(userPolicy, inputStream,                                 encryptedContentLength,                                 customProtectedInputStreamCreationCallback); } catch (com.microsoft.rightsmanagement.exceptions.InvalidParameterException e) {  ... } catch (IOException e) {  ... }


-    **Stap 3**: lees inhoud van de [**CustomProtectedInputStream**](/rights-management/sdk/4.2/api/android/customprotectedinputstream#msipcthin2_customprotectedinputstream_class_java) in *mDecryptedContent* en sluit vervolgens af.

    **Bron**: *MsipcTaskFragment.java*


    @Override public void onSuccess(CustomProtectedInputStream customProtectedInputStream) {  mUserPolicy = customProtectedInputStream.getUserPolicy();  ByteArrayOutputStream buffer = new ByteArrayOutputStream();

      int nRead;                      
      byte[] dataChunk = new byte[16384];

      try  {    while ((nRead = customProtectedInputStream.read(dataChunk, 0,                                                        dataChunk.length)) != -1)    {       buffer.write(dataChunk, 0, nRead);    }

        buffer.flush();    mDecryptedContent = new String(buffer.toByteArray(), Charset.forName("UTF-8"));

        buffer.close();    customProtectedInputStream.close();  }  catch (IOException e)  {    ...  } }


### Scenario: een aangepaste beveiligd bestand maken met behulp van een aangepast (ad hoc) beleid

-   **Stap 1**: maak met een e-mailadres dat is opgegeven door de gebruiker, een beleidsdescriptor.

    **Bron**: *MsipcTaskFragment.java*

    **Beschrijving**: in de praktijk zouden de volgende objecten worden gemaakt met behulp van gebruikersinvoer uit de apparaatinterface; [**UserRights**](/rights-management/sdk/4.2/api/android/userrights#msipcthin2_userrights_class_java) en [**PolicyDescriptor**](/rights-management/sdk/4.2/api/android/policydescriptor#msipcthin2_policydescriptor_interface_java).



      // Lijst met gebruikersrechten maken   UserRights userRights = new UserRights(Arrays.asList("consumer@domain.com"),     Arrays.asList( CommonRights.View, EditableDocumentRights.Print));   ArrayList<UserRights> usersRigthsList = new ArrayList<UserRights>();   usersRigthsList.add(userRights);

      // Beleidsdescriptor maken met behulp van lijst met gebruikersrechten   PolicyDescriptor policyDescriptor = PolicyDescriptor.createPolicyDescriptorFromUserRights(                                                          usersRigthsList);   policyDescriptor.setOfflineCacheLifetimeInDays(10);   policyDescriptor.setContentValidUntil(new Date());



-    **Stap 2**: maak op basis van de *selectedDescriptor* een aangepaste [**UserPolicy**](/rights-management/sdk/4.2/api/android/userpolicy).

    **Bron**: *MsipcTaskFragment.java*


       mIAsyncControl = UserPolicy.create((PolicyDescriptor)selectedDescriptor,                                          mEmailId, mRmsAuthCallback,                                          UserPolicyCreationFlags.NONE,                                          userPolicyCreationCallback);



-   **Stap 3**: maak en schrijf inhoud naar de [**CustomProtectedOutputStream**](/rights-management/sdk/4.2/api/android/customprotectedoutputstream#msipcthin2_customprotectedoutputstream_class_java) en sluit vervolgens af.

    **Bron**: *MsipcTaskFragment.java*


    File file = new File(filePath); final OutputStream outputStream = new FileOutputStream(file); CreationCallback<CustomProtectedOutputStream> customProtectedOutputStreamCreationCallback = new CreationCallback<CustomProtectedOutputStream>() { @Override public Context getContext() { …
            }

            @Override
            public void onCancel()
            {
              …
            }

            @Override
            public void onFailure(ProtectionException e)
            {
              …
            }

            @Override
            public void onSuccess(CustomProtectedOutputStream protectedOutputStream)
            {
                try
                {
                    // write serializedContentPolicy
                    byte[] serializedContentPolicy = mUserPolicy.getSerializedContentPolicy();
                    writeLongAsUnsignedIntToStream(outputStream, serializedContentPolicy.length);
                    outputStream.write(serializedContentPolicy);
                    // write encrypted content
                    if (contentToProtect != null)
                    {
                        writeLongAsUnsignedIntToStream(outputStream,
                                CustomProtectedOutputStream.getEncryptedContentLength(contentToProtect.length,
                                        protectedOutputStream.getUserPolicy()));
                        protectedOutputStream.write(contentToProtect);
                        protectedOutputStream.flush();
                        protectedOutputStream.close();
                    }
                    else
                    {
                        outputStream.flush();
                        outputStream.close();
                    }
                    …
                }
                catch (IOException e)
                {
                  …
                }
            }
        };
        try
        {
            mIAsyncControl = CustomProtectedOutputStream.create(outputStream, mUserPolicy,
                    customProtectedOutputStreamCreationCallback);
        }
        catch (InvalidParameterException e)
        {
          …
        }


 

 



<!--HONumber=Aug16_HO4-->


