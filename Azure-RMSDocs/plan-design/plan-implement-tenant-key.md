---
# required metadata

title: Uw Azure Rights Management-tenantsleutel plannen en implementeren | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Uw Azure Rights Management-tenantsleutel plannen en implementeren

*Van toepassing op: Azure Rights Management, Office 365*

Gebruik de informatie in dit artikel om uw Rights Management-tenantsleutel (RMS) voor Azure RMS te plannen en te beheren. In plaats van Microsoft uw tenantsleutel te laten beheren (standaard), wilt u wellicht zelf uw tenantsleutel beheren om te voldoen aan specifieke regels die gelden voor uw organisatie.  Uw eigen tenantsleutel beheren wordt ook wel aangeduid als BYOK (Bring Your Own Key).

> [!NOTE]
> De RMS-tenantsleutel wordt ook wel aangeduid als de SLC-sleutel (serverlicentiecertificaat). Azure RMS onderhoudt een of meer sleutels voor elke organisatie die zich abonneert op Azure RMS. Wanneer een sleutel wordt gebruikt voor RMS binnen een organisatie (zoals gebruikerssleutels, computersleutels, sleutels voor documentversleuteling), worden ze cryptografisch gekoppeld aan uw RMS-tenantsleutel.

**In één oogopslag:** gebruik de volgende tabel als een snelle handleiding voor de aanbevolen topologie van uw tenantsleutels. Vervolgens gebruikt u de extra documentatie voor meer informatie.

Als u Azure RMS implementeert met een tenantsleutel die wordt beheerd door Microsoft, kunt u later overstappen naar BYOK. U kunt momenteel echter uw Azure RMS-tenantsleutel niet overzetten van BYOK naar Beheerd door Microsoft.

|Zakelijke vereiste|Aanbevolen tenantsleuteltopologie|
|------------------------|-----------------------------------|
|Snel en zonder speciale hardware Azure RMS implementeren|Beheerd door Microsoft|
|Volledige IRM-functionaliteit is vereist in Exchange Online met Azure RMS|Beheerd door Microsoft|
|Uw sleutels worden door u gemaakt en beveiligd in een Hardware Security Module (HSM)|BYOK<br /><br />Op dit moment leidt deze configuratie tot een gereduceerde IRM-functionaliteit in Exchange Online. Zie [BYOK-prijzen en -beperkingen](byok-price-restrictions.md) voor meer informatie.|

## Uw tenantsleuteltopologie kiezen: Beheerd door Microsoft (de standaardinstelling) of Beheerd door uzelf (BYOK)
Beslis welke tenantsleuteltopologie het beste is voor uw organisatie. Standaard genereert Azure RMS uw tenantsleutel en beheert het de meeste aspecten van de levenscyclus van de tenantsleutel. Dit is de eenvoudigste optie met de laagste administratieve overhead. In de meeste gevallen hoeft u zelfs niet te weten dat u een tenantsleutel hebt. U hoeft u alleen aan te melden voor Azure RMS en de rest van het sleutelbeheerproces wordt uitgevoerd door Microsoft.

U kunt ook zelf uw tenantsleutel volledig beheren. U moet dan zelf uw tenantsleutel maken en het originele exemplaar binnen uw bedrijf bewaren. Dit scenario wordt vaak Bring Your Own Key (BYOK) genoemd. Met deze optie gebeurt er het volgende:

1.  U genereert uw tenantsleutel op uw locatie in overeenstemming met uw IT-beleid.

2.  U draagt de tenantsleutel van een Hardware Security Module (HSM) in uw bezit over aan HSM's die eigendom zijn van en worden beheerd door Microsoft. Tijdens dit proces blijft uw tenantsleutel altijd binnen de grenzen van uw hardwarebeveiliging.

3.  Wanneer u uw tenantsleutel overdraagt aan Microsoft, blijft deze beveiligd met Thales HSM's. Microsoft heeft samengewerkt met Thales om ervoor te zorgen dat uw tenantsleutel niet kan worden geëxtraheerd uit HSM's van Microsoft.

Hoewel dit optioneel is, wilt u waarschijnlijk ook gebruikmaken van de bijna realtime logboeken van Azure RMS om te zien hoe en wanneer uw tenantsleutel precies wordt gebruikt.

> [!NOTE]
> Azure RMS gebruikt als extra beveiligingsmaatregel afzonderlijke beveiligingswerelden voor zijn datacentra in Noord-Amerika, EMEA (Europa, Midden-Oosten en Afrika) en Azië. Wanneer u uw eigen tenantsleutel beheert, is deze gebonden aan de beveiligingswereld van de regio waar uw RMS-tenant is geregistreerd. Een tenantsleutel van een Europese klant kan bijvoorbeeld niet worden gebruikt in datacenters in Noord-Amerika of Azië.

## De levenscyclus van de tenantsleutel
Als u besluit dat Microsoft uw tenantsleutel moet beheren, voert Microsoft het grootste deel van de bewerkingen uit tijdens de levenscyclus van de sleutel. Als u echter besluit zelf uw tenantsleutel te beheren, bent u verantwoordelijk voor veel bewerkingen en een aantal extra procedures tijdens de levenscyclus van de sleutel.

In het volgende diagram worden deze twee opties weergegeven en met elkaar vergeleken. Het eerste diagram toont hoe weinig beheerdersoverhead er voor u is in de standaardconfiguratie, waarbij Microsoft de tenantsleutel beheert.

![Levenscyclus van de Azure RMS-tenantsleutel, beheerd door Microsoft, de standaard](../media/RMS_BYOK_cloud.png)

Het tweede diagram toont de extra stappen die vereist zijn wanneer u uw eigen tenantsleutel beheert.

![Levenscyclus van de Azure RMS-tenantsleutel, beheerd door u, BYOK](../media/RMS_BYOK_onprem.png)

Als u besluit uw tenantsleutel door Microsoft te laten beheren, is er geen verdere actie vereist om de sleutel te genereren. U kunt dan direct door naar de [Volgende stappen](plan-implement-tenant-key.md#next-steps).

Als u besluit uw tenantsleutel zelf te beheren, leest u de volgende gedeeltes voor meer informatie.

## Uw Azure Rights Management-tenantsleutel implementeren

Gebruik de informatie en procedures in dit gedeelte als u hebt besloten om uw eigen tenantsleutel te genereren en beheren. Het BYOK-scenario (Bring Your Own Key) uitvoeren:


> [!IMPORTANT]
> Als u al begonnen bent [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] te gebruiken (de service is geactiveerd) en u hebt gebruikers die Office 2010 uitvoeren, neemt u contact op met de klantenondersteuning van Microsoft (CSS) voordat u deze procedures uitvoert. Afhankelijk van uw scenario en vereisten, kunt u BYOK blijven gebruiken, maar met enkele beperkingen of bijkomende stappen.
> 
> Neem ook contact op met CSS als uw organisatie specifieke beleidsregels voor het verwerken van sleutels heeft.

### Vereisten voor BYOK
Zie de volgende tabel voor een lijst met vereisten voor BYOK (Bring Your Own Key).

|Vereiste|Meer informatie|
|---------------|--------------------|
|Een abonnement dat Azure RMS ondersteunt.|Zie [Cloudabonnementen die Azure RMS ondersteunen](../get-started/requirements-subscriptions.md) voor meer informatie over de beschikbare abonnementen.|
|U gebruikt geen RMS voor personen of Exchange Online. Of als u Exchange Online gebruikt, begrijpt en accepteert u de beperkingen van het gebruik van BYOK met deze configuratie.|Zie voor meer informatie over de beperkingen en huidige limieten van BYOK [BYOK-prijzen en -beperkingen](byok-price-restrictions.md).<br /><br />**Belangrijk**: BYOK is momenteel niet compatibel met Exchange Online.|
|Thales HSM, smartcards en ondersteunende software.<br /><br />**Opmerking**: als u van AD RMS migreert naar Azure RMS door over te stappen van een softwaresleutel naar een hardwaresleutel, moet u minimaal versie 11.62 voor de Thales-stuurprogramma's hebben.|U moet toegang hebben tot een Thales Hardware Security Module en operationele basiskennis hebben van Thales HSM's. Zie [Thales Hardware Security Module](http://www.thales-esecurity.com/msrms/buy) voor de lijst met compatibele modellen of om een HSM aan te schaffen als u die niet hebt.|
|Als u uw tenantsleutel wilt overdragen via internet in plaats van fysiek aanwezig te zijn in Redmond, Verenigde Staten, zijn er drie vereisten:<br /><br />Vereiste 1: een offline x64-werkstation met als besturingssysteem minimaal Windows 7 en Thales nShield-software van ten minste versie 11.62.<br /><br />Als op dit werkstation Windows 7 wordt uitgevoerd, moet u [Microsoft .NET Framework 4.5 installeren](http://go.microsoft.com/fwlink/?LinkId=225702).<br /><br />Vereiste 2: een werkstation dat is verbonden met internet en waarop minimaal Windows 7 wordt uitgevoerd.<br /><br />Vereiste 3: een USB-station of ander draagbaar opslagapparaat met ten minste 16 MB vrije ruimte.|Deze vereisten gelden niet als u naar Redmond komt en uw tenantsleutel persoonlijk overdraagt.<br /><br />Uit veiligheidsoverwegingen raden we u aan het eerste werkstation niet aan te sluiten op een netwerk. Dit wordt echter niet door het programma afgedwongen.<br /><br />Opmerking: in de volgende instructies wordt dit eerste werkstation aangeduid als het **niet-verbonden werkstation**.<br /><br />Als uw tenantsleutel bedoeld is voor een productienetwerk, raden we u bovendien aan een tweede, afzonderlijk werkstation te gebruiken om de toolset te downloaden en de tenantsleutel te uploaden. Voor testdoeleinden kunt u echter hetzelfde werkstation gebruiken als het eerste.<br /><br />Opmerking: in de volgende instructies wordt dit tweede werkstation aangeduid als het **met internet verbonden werkstation**.|

De procedures om uw eigen tenantcode te generen en gebruiken, zijn afhankelijk van het feit of u dit persoonlijk wilt doen of via internet:

-   **Via internet:** hiervoor zijn een paar extra configuratiestappen vereist, zoals het downloaden en gebruiken van een toolset en Windows PowerShell-cmdlets. U hoeft echter niet fysiek aanwezig te zijn in een Microsoft-faciliteit om uw tenantsleutel over te dragen. De beveiliging wordt op de volgende manieren gehandhaafd:

    -   U genereert de tenantsleutel op een offline werkstation, wat de kwetsbaarheid voor aanvallen verkleint.

    -   De tenantsleutel wordt versleuteld met een KEK-sleutel (Key Exchange Key), die versleuteld blijft totdat deze is overgedragen naar de Azure RMS HSM's. Alleen de versleutelde versie van uw tenantsleutel verlaat het oorspronkelijke werkstation.

    -   Een hulpprogramma stelt de eigenschappen in op uw tenantsleutel, waardoor deze wordt gekoppeld aan de Azure RMS-beveiligingswereld. Dus nadat de HSM's van Azure RMS uw tenantsleutel hebben ontvangen en gedecodeerd, kan de sleutel alleen door deze HSM's worden gebruikt. Uw tenantsleutel kan niet worden geëxporteerd. Deze koppeling wordt afgedwongen door de Thales HSM's.

    -   De KEK-sleutel (Key Exchange Key) waarmee uw tenantsleutel wordt versleuteld, wordt gegenereerd in de Azure RMS HSM's en kan niet worden geëxporteerd. De HSM's dwingen af dat er geen versie van de KEK buiten de HSM's kan bestaan. Bovendien bevat de toolset een attest van Thales dat de KEK niet kan worden geëxporteerd en is gegenereerd binnen een legitieme, door Thales vervaardigde HSM.

    -   De toolset bevat een attest van Thales dat de Azure RMS-beveiligingswereld ook is gegeneerd met een legitieme, door Thales vervaardigde HSM. Dit is uw bewijs dat Microsoft legitieme hardware gebruikt.

    -   Microsoft gebruikt afzonderlijke KEK's en afzonderlijke beveiligingswerelden in elke geografische regio, wat ervoor zorgt dat uw tenantsleutel alleen kan worden gebruikt in datacenters in de regio waarin u de sleutel hebt versleuteld. Een tenantsleutel van een Europese klant kan bijvoorbeeld niet worden gebruikt in datacenters in Noord-Amerika of Azië.

    > [!NOTE]
    > Uw tenantsleutel kan veilig worden verplaatst via niet-vertrouwde computers en netwerken omdat de sleutel is versleuteld en wordt beveiligd met machtigingen op het niveau van toegangsbeheer, waardoor de sleutel alleen bruikbaar is binnen uw HSM's en de HSM's van Microsoft voor Azure RMS. U kunt de scripts die in de toolset worden meegeleverd, gebruiken om de veiligheidsmaatregelen te controleren. U kunt ook meer informatie lezen over hoe dit werkt vanuit Thales: [Hardwaresleutelbeheer in de RMS-cloud](https://www.thales-esecurity.com/knowledge-base/white-papers/hardware-key-management-in-the-rms-cloud).

-   **Persoonlijk:** hiervoor moet u contact opnemen met de klantondersteuning van Microsoft (CSS) om een afspraak te maken voor de overdracht van de sleutel voor Azure RMS. U moet naar een vestiging van Microsoft in Redmond (Washington) in de Verenigde Staten komen om uw tenantsleutel over te dragen aan de Azure RMS-beveiligingswereld.

Als u instructies nodig hebt, selecteert u of u uw eigen tenantsleutel via internet of persoonlijk gaat genereren en overdragen: 

- [Via internet](generate-tenant-key-internet.md)
- [Persoonlijk](generate-tenant-key-in-person.md)


## Volgende stappen

Nu u een planning hebt gemaakt en u zo nodig de tenantsleutel hebt gegenereerd, doet u het volgende:

1.  Begin uw tenantsleutel te gebruiken:

    -   Als u dat nog niet hebt gedaan, moet u nu Rights Management activeren zodat uw organisatie kan beginnen RMS te gebruiken. Gebruikers beginnen onmiddellijk uw tenantsleutel te gebruiken (beheerd door Microsoft of door u).

        Zie voor meer informatie over activeren [Azure Rights Management activeren](../deploy-use/activate-service.md).

    -   Als u Rights Management al had geactiveerd en vervolgens hebt besloten uw eigen tenantsleutel te beheren, stappen gebruikers geleidelijk van de oude tenantsleutel over op de nieuwe. Deze gespreide overgang kan een paar weken duren. Documenten en bestanden die waren beveiligd met de oude tenantsleutel, blijven toegankelijk voor gemachtigde gebruikers.

2.  Overweeg gebruikslogboekregistratie te gebruiken: hiermee wordt elke transactie geregistreerd die RMS uitvoert.

    Als u had besloten uw eigen tenantsleutel te beheren, bevat de logboekregistratie informatie over het gebruik van uw tenantsleutel. Zie het volgende voorbeeld van een in Excel weergegeven logboekbestand, waarin de aanvraagtypen **Decrypt** en **SignDigest** aangeven dat de tenantsleutel wordt gebruikt.

    ![logboekbestand waarin de tenantsleutel wordt gebruikt](../media/RMS_Logging.gif)

    Zie [Het gebruik van Azure Rights Management registreren in een logboek en analyseren](../deploy-use/log-analyze-usage.md) voor meer informatie.

3.  Onderhoud uw tenantsleutel.

    Zie voor meer informatie [Bewerkingen voor uw Azure Rights Management-tenantsleutel](../deploy-use/operations-tenant-key.md).



<!--HONumber=Apr16_HO4-->


