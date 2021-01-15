---
title: Verbeterde slimme tags
description: Verbeterde slimme tags
uuid: 4452ca05-1f20-4f80-884a-a739ae7b8b0e
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
discoiquuid: c1b52aac-1eaf-4cfa-801f-77aeca0d90ea
translation-type: tm+mt
source-git-commit: b9dffdda37992f3a9f34953b8dd391d6f6361ceb
workflow-type: tm+mt
source-wordcount: '1504'
ht-degree: 15%

---


# Verbeterde slimme tags {#enhanced-smart-tags}

## Overzicht van verbeterde slimme tags {#overview-of-enhanced-smart-tags}

Organisaties die met digitale middelen te maken hebben, maken steeds vaker gebruik van een door taxonomie gecontroleerde woordenlijst in metagegevens van bedrijfsmiddelen. In wezen, omvat het een lijst van sleutelwoorden die de werknemers, de partners, en de klanten algemeen gebruiken om naar digitale activa van een bepaalde klasse te verwijzen en te zoeken. Door elementen te labelen met een woordenschat die door de taxonomie wordt bepaald, kunt u ze gemakkelijk herkennen en ophalen door zoekopdrachten op basis van tags.

Vergeleken met natuurlijke taalwoordenboeken, helpt het etiketteren van digitale activa die op bedrijfstaxonomie worden gebaseerd hen op de zaken van een bedrijf te richten en zorgt ervoor dat de meest relevante activa in onderzoeken verschijnen.

Een autofabrikant kan bijvoorbeeld autoafbeeldingen labelen met modelnamen, zodat alleen relevante afbeeldingen worden weergegeven wanneer afbeeldingen van verschillende modellen worden doorzocht om een promotiecampagne te ontwerpen.

Als u wilt dat de Smart Content Service de juiste tags toepast, moet u deze trainen om uw taxonomie te herkennen. Als u de service wilt trainen, moet u eerst een set elementen en tags beheren die deze elementen het beste beschrijven. Pas deze tags toe op de middelen en voer een trainingsworkflow uit om de service te helpen leren.

Nadat een tag is opgeleid en gereed, kan de service deze tags nu toepassen op elementen via een workflow voor labelen.

Op de achtergrond gebruikt de Smart Content Service het AI-framework van Adobe Sensei om het algoritme voor imageherkenning op te leiden voor uw tagstructuur en bedrijfskatonomie. Deze inhoudsinfo wordt vervolgens gebruikt om relevante tags toe te passen op een andere set elementen.

Smart Content Service is een cloudservice die wordt gehost op [!DNL Adobe I/O]. Om het in Adobe Experience Manager (AEM) te gebruiken, moet de systeembeheerder uw AEM instantie met [!DNL Adobe I/O] integreren.

Samenvattend, zijn hier de belangrijkste stappen om de Slimme Dienst van de Inhoud te gebruiken:

* Onboarding
* Elementen en labels controleren (taxonomidefinitie)
* De Smart Content Service trainen
* Automatisch labelen

![stroomschema](assets/flowchart.gif)

## Vereisten {#prerequisites}

Voordat u de service Slimme inhoud kunt gebruiken, moet u het volgende doen om een integratie te maken op [!DNL Adobe I/O]:

* Een Adobe ID-account met beheerdersrechten voor de organisatie.
* De service Smart Content Service is ingeschakeld voor uw organisatie.

## Onboarding {#onboarding}

De Smart Content Service kan worden aangeschaft als toevoeging aan AEM. Nadat u de aankoop hebt gedaan, wordt een e-mail verzonden naar de beheerder van uw organisatie met een koppeling naar [!DNL Adobe I/O].

De beheerder kan de verbinding volgen om de Slimme Dienst van de Inhoud met AEM te integreren. Zie [Slimme tags configureren](config-smart-tagging.md) om de service te integreren met AEM Assets.

Het instapproces is volledig wanneer de beheerder de dienst vormt en gebruikers in AEM toevoegt.

>[!NOTE]
>
>Zie [Slimme tags](https://helpx.adobe.com/experience-manager/6-3/assets/using/touch-ui-smart-tags.html) als u AEM versie 6.3 of lager gebruikt en automatische labelservice voor uw elementen nodig hebt. Slimme tags maken geen gebruik van de AI-mogelijkheden en zijn minder nauwkeurig dan de verbeterde functie Slimme tags toepassen.

## Elementen en labels {#reviewing-assets-and-tags} controleren

Nadat u aan boord wordt genomen, is het eerste wat u wilt doen een reeks markeringen identificeren die deze beelden in de context van uw zaken het best beschrijven.

Hierna kunt u afbeeldingen bekijken om een set afbeeldingen te identificeren die het beste bij uw product passen voor een bepaalde zakelijke behoefte. Zorg ervoor dat de elementen in uw gekromde set voldoen aan [trainingsrichtlijnen voor Smart Content Service](smart-tags-training-guidelines.md).

Voeg de elementen toe aan een map en pas de tags toe op elk element vanaf de eigenschappenpagina. Voer vervolgens de trainingsworkflow uit op deze map. Met de gekromde set elementen kan de Smart Content Service effectief meer elementen trainen met behulp van uw taxonomidefinities.

>[!NOTE]
>
>1. Opleiding is een onherroepelijk proces. Adobe raadt u aan de tags in de gekromde set elementen te controleren voordat u de Smart Content Service op de tags informeert.
>1. Lees [Richtlijnen voor training voor Smart Content Service](smart-tags-training-guidelines.md) voordat u de training voor een tag start.
>1. Wanneer u de Slimme Dienst van de Inhoud voor het eerst opleidt, adviseert Adobe dat u het op minstens twee verschillende markeringen opleidt.

>



## De Smart Content Service {#training-the-smart-content-service} trainen

Als u wilt dat de Smart Content Service uw bedrijfskrionomie herkent, voert u deze uit op een reeks elementen die al tags bevatten die relevant zijn voor uw bedrijf. Na de training kan de service dezelfde taxonomie toepassen op een vergelijkbare set activa.

U kunt de service meerdere keren trainen om de service beter in staat te stellen relevante tags toe te passen. Voer na elke trainingscyclus een labelworkflow uit en controleer of uw elementen correct zijn gecodeerd.

U kunt de Slimme Dienst van de Inhoud periodiek of op vereiste basis trainen.

>[!NOTE]
>
>De trainingsworkflow wordt alleen uitgevoerd voor mappen.

### Periodieke training {#periodic-training}

U kunt de Slimme Dienst van de Inhoud toelaten om periodiek op de activa en bijbehorende markeringen binnen een omslag te trainen. Open de eigenschappenpagina van de elementenmap, selecteer **[!UICONTROL Enable Smart Tags]** onder het tabblad **[!UICONTROL Details]** en sla de wijzigingen op.

![enable_smart_tags](assets/enable_smart_tags.png)

Als deze optie voor een map is geselecteerd, voert AEM automatisch een trainingsworkflow uit om de Smart Content Service op te leiden voor de map en de bijbehorende tags. Standaard wordt de trainingsworkflow wekelijks om 12:30 uur uitgevoerd op zaterdag.

### On-demand training {#on-demand-training}

U kunt de Slimme Dienst van de Inhoud wanneer vereist van de console van het Werkschema trainen.

1. Tik of klik op het AEM-logo en ga naar **[!UICONTROL Tools > Workflow > Models]**.
1. Selecteer op de pagina **[!UICONTROL Workflow Models]** de workflow **[!UICONTROL Smart Tags Training]** en tik of klik vervolgens op **[!UICONTROL Start Workflow]** op de werkbalk.
1. Blader in het dialoogvenster **[!UICONTROL Run Workflow]** naar de payload-map met de gecodeerde middelen voor het trainen van de service.
1. Geef een titel op voor de workflow en voeg een opmerking toe. Tik vervolgens op **[!UICONTROL Run]** of klik op . De elementen en tags worden ter training aangeboden.

   ![workflow_dialog](assets/workflow_dialog.png)

>[!NOTE]
>
>Nadat de middelen in een map zijn verwerkt voor training, worden alleen de gewijzigde middelen verwerkt in volgende trainingscycli.

### Trainingsrapporten {#viewing-training-reports} weergeven

Om te controleren of de Slimme Dienst van de Inhoud op uw markeringen in de trainingsreeks activa wordt getraind, herzie het rapport van de opleidingswerkstroom van de console van Rapporten.

1. Tik of klik op het AEM-logo en ga naar **[!UICONTROL Tools > Assets > Reports]**.
1. Tik of klik op de pagina **[!UICONTROL Asset Reports]** op **[!UICONTROL Create]**.
1. Selecteer het rapport **[!UICONTROL Smart Tags Training]** en tik of klik op de werkbalk op **[!UICONTROL Next]**.
1. Geef een titel en beschrijving voor het rapport op. Laat onder **[!UICONTROL Schedule Report]** de optie **[!UICONTROL Now]** ingeschakeld. Als u het rapport voor later wilt plannen, selecteert u **[!UICONTROL Later]** en geeft u een datum en tijd op. Tik of klik vervolgens op **[!UICONTROL Create]** op de werkbalk.
1. Selecteer op de pagina **[!UICONTROL Asset Reports]** het rapport dat u hebt gegenereerd. Tik of klik op het pictogram **[!UICONTROL View]** op de werkbalk om het rapport weer te geven.
1. Bekijk de details van het rapport.

   Het rapport geeft de trainingsstatus weer voor de tags die u hebt getraind. De groene kleur in de kolom **[!UICONTROL Training Status]** geeft aan dat de Smart Content Service is getraind voor de tag. Een gele kleur geeft aan dat de service niet volledig is getraind voor een bepaalde tag. Voeg in dit geval meer afbeeldingen met de desbetreffende tag toe en voer de trainingsworkflow uit om de service volledig op de tag te trainen.

   Als dit rapport uw tags niet bevat, voert u de trainingsworkflow voor deze tags opnieuw uit.

1. Als u het rapport wilt downloaden, selecteert u het in de lijst en tikt u op het pictogram **[!UICONTROL Download]** op de werkbalk. Het rapport wordt gedownload als Excel-bestand.

## Elementen automatisch {#tagging-assets-automatically} labelen

Nadat u de Slimme Dienst van de Inhoud hebt opgeleid, kunt u het etiketteren werkschema teweegbrengen om aangewezen markeringen op een verschillende reeks gelijkaardige activa automatisch toe te passen.

U kunt de tagwerkstroom periodiek of telkens wanneer dat nodig is uitvoeren.

>[!NOTE]
>
>De tagwerkstroom wordt zowel op elementen als op mappen uitgevoerd.

### Periodieke labels {#periodic-tagging}

U kunt de Slimme Dienst van de Inhoud toelaten om activa binnen een omslag periodiek te etiketteren. Open de eigenschappenpagina van de elementenmap, selecteer **[!UICONTROL Enable Smart Tags]** onder het tabblad **[!UICONTROL Details]** en sla de wijzigingen op.

Als deze optie voor een map is geselecteerd, worden de middelen in de map automatisch gelabeld door de Smart Content Service. Standaard wordt de tagwerkstroom elke dag om 12.00 uur uitgevoerd.

### Tags op aanvraag {#on-demand-tagging}

U kunt de tagwerkstroom activeren door uw elementen direct te labelen:

* Workflowconsole
* Tijdlijn

>[!NOTE]
>
>Als u de labelworkflow uitvoert vanuit de tijdlijn, kunt u tags toepassen op maximaal 15 elementen tegelijk.

#### Elementen labelen vanaf de workflowconsole {#tagging-assets-from-the-workflow-console}

1. Tik of klik op het AEM-logo en ga naar **[!UICONTROL Tools > Workflow > Models]**.
1. Selecteer op de pagina **[!UICONTROL Workflow Models]** de workflow **[!UICONTROL DAM Smart Tags Assets]** en tik of klik vervolgens op **[!UICONTROL Start Workflow]** op de werkbalk.

   ![dam_smart_tag_workflow](assets/dam_smart_tag_workflow.png)

1. Blader in het dialoogvenster **[!UICONTROL Run Workflow]** naar de payload-map met elementen waarop u de tags automatisch wilt toepassen.
1. Geef een titel voor de workflow en een optionele opmerking op. Tik vervolgens op **[!UICONTROL Run]** of klik op .

   ![tagging_dialog](assets/tagging_dialog.png)

   Navigeer naar de map met middelen en controleer de tags om te controleren of de Smart Content Service uw elementen correct heeft gelabeld. Zie [Slimme tags beheren](managing-smart-tags.md) voor meer informatie.

#### Elementen labelen vanaf de tijdlijn {#tagging-assets-from-the-timeline}

1. Selecteer in de gebruikersinterface Middelen de map met elementen of specifieke elementen waarop u slimme tags wilt toepassen.
1. Tik op het pictogram GlobalNav of klik op dit pictogram en open de tijdlijn.
1. Tik/klik op de pijl onderaan en tik/klik op **[!UICONTROL Start Workflow]**.

   ![start_workflow](assets/start_workflow.png)

1. Selecteer de **[!UICONTROL DAM Smart Tag Assets]** workflow en geef een titel op voor de workflow.
1. Tik of klik op **[!UICONTROL Start]**. De workflow past de labels toe op elementen. Navigeer naar de map met middelen en controleer de tags om te controleren of de Smart Content Service uw elementen correct heeft gelabeld. Zie [Slimme tags beheren](managing-smart-tags.md) voor meer informatie.

>[!NOTE]
>
>In de volgende coderingscycli worden alleen de gewijzigde elementen opnieuw gecodeerd met nieuw opgeleide tags.
>
>Zelfs ongewijzigde elementen worden echter gecodeerd als de ruimte tussen de laatste en huidige coderingscycli voor de coderingsworkflow meer dan 24 uur bedraagt.
>
>Voor workflows met periodieke tags worden ongewijzigde elementen gecodeerd als de tussenruimte langer is dan zes maanden.
