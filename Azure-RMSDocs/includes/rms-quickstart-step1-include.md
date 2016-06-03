![Zelfstudie Snel starten, stap 1](../media/AzRMS_QuickStartSteps1.PNG)

Hoewel u mogelijk een abonnement hebt met ondersteuning voor Azure Rights Management, is de service standaard uitgeschakeld. Als u de service wilt activeren, kunt u het Office 365-beheercentrum of de klassieke Azure-portal gebruiken:

-   Als u een Office 365-abonnement inclusief Azure Rights Management hebt of als u een Office 365-abonnement hebt zonder Azure Rights Management, maar u wel beschikt over een abonnement voor Azure RMS Premium: **gebruik het Office 365-beheercentrum**.

-   Als u geen Office 365-abonnement hebt: **gebruik de klassieke Azure-portal**.

![Klassieke Azure-portal](../media/AzRMS_Tutorial_1_Screenshots.png)

#### Rights Management activeren vanuit het Office 365-beheercentrum

1.  Ga naar de [Office 365-portal](https://portal.office.com/) en meld u aan met uw werk- of schoolaccount.

2.  Als het Office 365-beheercentrum niet automatisch wordt weergegeven, selecteert u linksboven het pictogram voor het starten van de app en kiest u **Beheer**. De tegel **Beheer** wordt alleen weergegeven voor Office 365-beheerders.

    > [!TIP]
    > Zie [Over het Office 365-beheercentrum - Help voor beheerders](https://support.office.com/article/About-the-Office-365-admin-center-Admin-Help-58537702-d421-4d02-8141-e128e3703547) voor hulp bij het beheercentrum.

3.  Vouw in het linkerdeelvenster **SERVICE-INSTELLINGEN** uit.

4.  Klik op **Rights Management**.

5.  Klik op de pagina **RIGHTS MANAGEMENT** op **Beheren**.

6.  Klik op de pagina **Rights Management** op **Activeren**.

7.  Als de vraag **Wilt u Rights Management activeren?** verschijnt, klikt u op **Activeren**.

U ziet nu **Rights management is geactiveerd** en de optie om te deactiveren (mogelijk moet u de pagina handmatig vernieuwen)

Klik op dit moment niet op **Geavanceerde functies**. U gaat dan naar de klassieke Azure-portal waar u sjablonen kunt configureren, maar deze sjablonen zijn voor deze zelfstudie niet nodig. In plaats daarvan kunt u het Office 365-beheercentrum sluiten.

#### Rights Management activeren vanuit de Azure-portal

1.  Ga naar de [klassieke Azure-portal](http://go.microsoft.com/fwlink/p/?LinkID=275081) en meld u aan.

2.  Klik in het linkerdeelvenster op **ACTIVE DIRECTORY**.

3.  Klik op de pagina **Active directory** op **RIGHTS MANAGEMENT**.

4.  Selecteer de map die u wilt beheren voor [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)], klik op **ACTIVEREN** en bevestig de actie.

De **RIGHTS MANAGEMENT-STATUS** wordt nu weergegeven als **Actief** en de optie **ACTIVEREN** is vervangen door **DEACTIVEREN**.

U kunt in de portal ook andere opties voor Rights Management configureren, maar deze opties zijn niet nodig voor deze zelfstudie. U kunt de klassieke Azure-portal dus sluiten.

Dit is alles wat u hoeft te doen in deze eerste stap. De service wordt geactiveerd. Alle gebruikers in uw organisatie kunnen nu beginnen met het beveiligen van belangrijke en gevoelige documenten. In een productieomgeving is het raadzaam om in eerste instantie te beperken wie dit kan doen en dit vervolgens gefaseerd uit te rollen. Maar dat is voor deze zelfstudie niet nodig.

Mogelijk wilt u voor een productie-implementatie ook aangepaste sjablonen configureren. Dit wordt hier echter niet uitgelegd. Met sjablonen kunnen gebruikers gemakkelijker snel de juiste instellingen toepassen wanneer ze bestanden willen beveiligen. Wanneer u Rights Management activeert, krijgt u automatisch twee standaardsjablonen. Waarschijnlijk wilt u deze in een productieomgeving aanvullen met uw eigen aangepaste sjablonen. Sjablonen zijn echter niet nodig voor deze zelfstudie. U kunt dus doorgaan naar de volgende stap.

|Als u meer informatie wilt|Aanvullende informatie|
|--------------------------------|--------------------------|
|Informatie over het activeren van Rights Management en beheren wie er bestanden en e-mailberichten kunnen beveiligen wanneer de service is geactiveerd   →|[Azure Rights Management activeren](../deploy-use/activate-azure-classic.md)|
|Informatie over de standaardsjablonen en het maken van nieuwe, aangepaste sjablonen   →|[Aangepaste sjablonen configureren voor Azure Rights Management](../deploy-use/create-template.md)|


<!--HONumber=Apr16_HO3-->


