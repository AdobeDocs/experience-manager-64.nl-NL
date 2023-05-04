---
title: Contentfragmenten beheren
seo-title: Managing Content Fragments
description: Inhoudsfragmenten worden opgeslagen als elementen, zodat ze voornamelijk worden beheerd vanaf de middelenconsole.
seo-description: Content Fragments are stored as Assets, so are primarily managed from the Assets console.
uuid: 0659cf03-b4e8-4b8b-bec7-0082f980115a
contentOwner: AEM Docs
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: content-fragments
content-type: reference
discoiquuid: da8f968b-91cc-45a8-ae4b-757b4f840b8e
exl-id: b21ba7a1-6e6f-4b95-9336-b49f7e932af5
feature: Content Fragments
role: User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1440'
ht-degree: 3%

---

# Contentfragmenten beheren {#managing-content-fragments}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

>[!CAUTION]
>
>Voor bepaalde functies voor inhoudsfragmenten moet de toepassing van [AEM 6.4 Service Pack 2 (6.4.2.0) of later](/help/release-notes/sp-release-notes.md).

Inhoudsfragmenten worden opgeslagen als **[!UICONTROL Assets]**, en dus in de eerste plaats vanuit de **[!UICONTROL Assets]** console.

>[!NOTE]
>
>Inhoudsfragmenten worden vervolgens gebruikt bij het ontwerpen van pagina&#39;s. zie [Pagina&#39;s ontwerpen met inhoudsfragmenten](/help/sites-authoring/content-fragments.md).

## Inhoudsfragmenten maken {#creating-content-fragments}

### Een inhoudsmodel maken {#creating-a-content-model}

[Inhoudsfragmentmodellen](content-fragments-models.md) kunnen worden ingeschakeld en gemaakt voordat u inhoudsfragmenten met gestructureerde inhoud maakt.

>[!NOTE]
>
>Zie [Inhoudsfragmenten ontwikkelen](/help/sites-developing/customizing-content-fragments.md) voor nadere informatie over templates; worden gebruikt voor eenvoudige inhoudsfragmenten.

### Een inhoudsfragment maken {#creating-a-content-fragment}

De methode voor het maken van een inhoudsfragment is (in principe) hetzelfde voor eenvoudige en gestructureerde fragmenten:

1. Ga naar de map **[!UICONTROL Assets]** waar u het fragment wilt maken.
1. Selecteren **[!UICONTROL Create]** vervolgens **[!UICONTROL Content Fragment]** om de wizard te openen.
1. In de eerste stap van de wizard moet u de basis van het nieuwe fragment opgeven.

   * Dit kan een:

      * [Sjabloon](/help/sites-developing/content-fragment-templates.md) - bijvoorbeeld **[!UICONTROL Simple Fragment]**
      * [Model](content-fragments-models.md) - wordt gebruikt om een fragment te maken waarvoor gestructureerde inhoud nodig is; bijvoorbeeld **Luchthaven** model
   * Alle beschikbare sjablonen en modellen worden weergegeven.

   Na selectie kunt u **[!UICONTROL Next]** om verder te gaan.

   ![cfm-6420-15](assets/cfm-6420-15.png)

1. In de **[!UICONTROL Properties]** stap specificeren:

   * **[!UICONTROL Basic]**

      * **[!UICONTROL Title]**

         De fragmenttitel.

         Verplicht.

      * **[!UICONTROL Description]**
      * **[!UICONTROL Tags]**
   * **[!UICONTROL Advanced]**

      * **[!UICONTROL Name]**

         de naam; wordt gebruikt om de URL te vormen.

         Verplicht; wordt automatisch afgeleid van de titel, maar kan worden bijgewerkt.


1. Selecteren **[!UICONTROL Create]** om de actie te voltooien, dan **[!UICONTROL Open]** het fragment voor bewerken of terugkeren naar de console met **[!UICONTROL Done]**.

## Handelingen voor een inhoudsfragment {#actions-for-a-content-fragment}

In de **[!UICONTROL Assets]** een reeks acties beschikbaar is voor uw inhoudsfragmenten:

* van de werkbalk; nadat u het fragment hebt geselecteerd, zijn alle relevante handelingen beschikbaar.
* Als [snelle acties](/help/sites-authoring/basic-handling.md#quick-actions); een subset van acties beschikbaar voor de afzonderlijke fragmentkaarten.

![cfm-6420-17](assets/cfm-6420-17.png)

Selecteer het fragment om de werkbalk weer te geven met de toepasselijke acties:

* **[!UICONTROL Download]**

   * Sla het fragment op als een ZIP-bestand. U kunt definiëren of u Elements, Variaties, Metagegevens wilt opnemen.

* **[!UICONTROL Create]**
* **[!UICONTROL Checkout]**
* **[!UICONTROL Properties]**

   * Hiermee kunt u de metagegevens van het fragment weergeven en/of bewerken.

* **[!UICONTROL Edit]**

   * Hiermee kunt u [het fragment openen voor het bewerken van inhoud](content-fragments-variations.md) samen met de elementen, variaties, bijbehorende inhoud en metagegevens.

* **[!UICONTROL Manage Tags]**
* **[!UICONTROL To Collection]**

   * Voeg het fragment toe aan een verzameling.
   * Dit kan ook gebeuren wanneer [een verzameling koppelen aan het fragment](content-fragments-assoc-content.md#adding-associated-content).

* **[!UICONTROL Copy/Paste]**
* **[!UICONTROL Move]**
* **[!UICONTROL Quick Publish]**
* **[!UICONTROL Manage Publication]**
* **[!UICONTROL Delete]**

>[!NOTE]
>
>Veel van deze zijn [standaardhandelingen voor elementen](managing-assets-touch-ui.md) en/of de [bureaubladtoepassing](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app.html).

## De fragmenteditor openen {#opening-the-fragment-editor}

Uw fragment openen voor bewerken:

>[!CAUTION]
>
>Als u een inhoudsfragment wilt bewerken, hebt u [de juiste machtigingen](/help/sites-developing/customizing-content-fragments.md#asset-permissions). Neem contact op met de systeembeheerder als er problemen optreden.

1. Gebruik de **[!UICONTROL Assets]** -console om naar de locatie van het inhoudsfragment te navigeren.
1. Open het fragment voor bewerking door:

   * Klikken of tikken op de fragment- of fragmentkoppeling (dit is afhankelijk van de consoleweergave).
   * Het fragment selecteren en vervolgens **[!UICONTROL Edit]** op de werkbalk.

   De fragmenteditor wordt geopend:

   ![cfm-6420-18](assets/cfm-6420-18.png)

   >[!NOTE]
   >
   >1. Er wordt een bericht weergegeven wanneer al naar het fragment wordt verwezen op een inhoudspagina.
   >
   >2. Het zijpaneel kan worden verborgen of weergegeven met de opdracht **[!UICONTROL Toggle Side Panel]** pictogram.


1. Navigeer door de drie modi met de pictogrammen in het zijpaneel:

   * Variaties: [De inhoud bewerken](#editing-the-content-of-your-fragment) en [Uw variaties beheren](#creating-and-managing-variations-within-your-fragment)
   * [Annotaties](content-fragments-variations.md#annotating-a-content-fragment)
   * [Gekoppelde inhoud](#associating-content-with-your-fragment)
   * [Metagegevens](#viewing-and-editing-the-metadata-properties-of-your-fragment)

   ![cfm-10](assets/cfm-10.png)

1. Nadat u wijzigingen hebt aangebracht, kunt u **[!UICONTROL Save]** of **[!UICONTROL Cancel]** zoals vereist.

   >[!NOTE]
   >
   >Beide **[!UICONTROL Save]** en **[!UICONTROL Cancel]** sluit de editor af - zie [Opslaan, Annuleren en versies](#save-cancel-and-versions) voor volledige informatie over hoe beide opties werken voor inhoudsfragmenten.

## Opslaan, Annuleren en versies {#save-cancel-and-versions}

>[!NOTE]
>
>Versies kunnen ook [gemaakt, vergeleken en teruggezet vanaf de tijdlijn](https://helpx.adobe.com/experience-manager/6-3/assets/using/content-fragments-managing.html#timeline-for-content-fragments).

De editor heeft twee opties:

* **[!UICONTROL Save]**

   Hiermee slaat u de laatste wijzigingen op en sluit u de editor af.

   >[!CAUTION]
   >
   >Als u een inhoudsfragment wilt bewerken, hebt u [de juiste machtigingen](/help/sites-developing/customizing-content-fragments.md#asset-permissions). Neem contact op met de systeembeheerder als er problemen optreden.

   >[!NOTE]
   >
   >Het is mogelijk om in de redacteur te blijven, die een reeks veranderingen aanbrengt, alvorens te selecteren **[!UICONTROL Save]**.

   >[!CAUTION]
   >
   >Naast het opslaan van uw wijzigingen, **[!UICONTROL Save]** werkt ook verwijzingen bij en zorgt ervoor dat de verzender wordt leeggemaakt zoals vereist. Deze wijzigingen kunnen enige tijd in beslag nemen. Hierdoor kan de prestaties van een groot/complex/zwaar geladen systeem worden beïnvloed.
   >
   >
   >Houd hier rekening mee wanneer u **[!UICONTROL Save]** en voert u vervolgens snel de fragmenteditor opnieuw in om verdere wijzigingen aan te brengen en op te slaan.

* **[!UICONTROL Cancel]**

   Sluit de editor af zonder de laatste wijzigingen op te slaan.

AEM tijdens het bewerken van het inhoudsfragment automatisch versies maken om ervoor te zorgen dat eerdere inhoud kan worden hersteld als u **[!UICONTROL Cancel]** uw wijzigingen:

1. Wanneer een inhoudsfragment wordt geopend om te bewerken, wordt op het bestaan van een cookie-token gecontroleerd dat aangeeft of een *bewerksessie* bestaat:

   1. Als het token wordt gevonden, wordt het fragment beschouwd als onderdeel van de bestaande bewerkingssessie.
   1. Als het token *niet* beschikbaar is en de gebruiker begint met het bewerken van inhoud, wordt een versie gemaakt en wordt een token voor deze nieuwe bewerkingssessie verzonden naar de client, waar deze in een cookie wordt opgeslagen.

1. Terwijl er een *actief* tijdens het bewerken van de sessie wordt de inhoud die wordt bewerkt automatisch om de 600 seconden opgeslagen (standaard).

   >[!NOTE]
   >
   >Het auto sparen interval is configureerbaar gebruikend `/conf` mechanisme.
   >
   >Standaardwaarde, zie:
   >
   >`/libs/settings/dam/cfm/jcr:content/autoSaveInterval`

1. Als de gebruiker selecteert om **[!UICONTROL Cancel]** de bewerking, de versie die aan het begin van de bewerkingssessie is gemaakt, wordt hersteld en de token wordt verwijderd om de bewerkingssessie te beëindigen.
1. Als de gebruiker selecteert om **[!UICONTROL Save]** de bewerkingen, de bijgewerkte elementen/variaties worden voortgezet en het token wordt verwijderd om de bewerkingssessie te beëindigen.

## De inhoud van het fragment bewerken {#editing-the-content-of-your-fragment}

Als u het fragment hebt geopend, kunt u de opdracht [Variaties](content-fragments-variations.md) gebruiken om uw inhoud te ontwerpen.

## Variaties maken en beheren in uw fragment {#creating-and-managing-variations-within-your-fragment}

Nadat u de Master inhoud hebt gemaakt, kunt u [Variaties](content-fragments-variations.md) van die inhoud.

## Inhoud koppelen aan uw fragment {#associating-content-with-your-fragment}

U kunt ook [gekoppelde inhoud](content-fragments-assoc-content.md) met een fragment. Dit biedt een verbinding zodat elementen (d.w.z. afbeeldingen) (optioneel) met het fragment kunnen worden gebruikt wanneer het aan een inhoudspagina wordt toegevoegd.

## De metagegevens (eigenschappen) van het fragment weergeven en bewerken {#viewing-and-editing-the-metadata-properties-of-your-fragment}

U kunt de eigenschappen van een fragment weergeven en bewerken met de opdracht [[!UICONTROL Metadata]](content-fragments-metadata.md) tab.

## Tijdlijn voor inhoudsfragmenten {#timeline-for-content-fragments}

Naast de standaardopties [Tijdlijn](managing-assets-touch-ui.md#timeline) biedt zowel informatie als acties die specifiek zijn voor inhoudsfragmenten:

* Informatie weergeven over versies, opmerkingen en annotaties
* Handelingen voor versies

   * **[[!UICONTROL Revert to this Version]](#reverting-to-a-version)** (selecteer een bestaand fragment en selecteer vervolgens een specifieke versie)
   * **[[!UICONTROL Compare to Current]](#comparing-fragment-versions)** (selecteer een bestaand fragment en selecteer vervolgens een specifieke versie)
   * Voeg een **[!UICONTROL Label]** en/of **[!UICONTROL Comment]** (selecteer een bestaand fragment en selecteer vervolgens een specifieke versie)
   * **[!UICONTROL Save as Version]** (selecteer een bestaand fragment en klik vervolgens op de pijl omhoog onder aan de tijdlijn)

* Handelingen voor annotaties

   * **[!UICONTROL Delete]**

>[!NOTE]
>
>Opmerkingen zijn:
>
>* Standaardfunctionaliteit voor alle elementen
>* Gemaakt in tijdlijn
>* Verwant aan het fragmentelement
>
>Annotaties (voor inhoudsfragmenten) zijn:
>
>* Opgegeven in de fragmenteditor
>* Specifiek voor een geselecteerd tekstsegment binnen het fragment


Bijvoorbeeld:

![cfm-6420-19](assets/cfm-6420-19.png)

## Fragmentversies vergelijken {#comparing-fragment-versions}

De **[!UICONTROL Compare to Current]** actie is beschikbaar via [[!UICONTROL Timeline]](https://helpx.adobe.com/experience-manager/6-3/assets/using/content-fragments-managing.html#timeline-for-content-fragments) nadat u een specifieke versie hebt geselecteerd.

Hiermee wordt het volgende geopend:

* de **[!UICONTROL Current]** (laatste) versie (links)

* de geselecteerde versie **v&lt;*x.y*>** (rechts)

Zij worden naast elkaar weergegeven, waarbij:

* Eventuele verschillen worden gemarkeerd

   * Verwijderde tekst - rood
   * Ingevoegde tekst - groen
   * Vervangen tekst - blauw

* Met het pictogram voor volledig scherm kunt u elke versie afzonderlijk openen. dan terug naar de parallelle weergave
* U kunt **[!UICONTROL Revert]** naar de specifieke versie
* **[!UICONTROL Done]** zult u aan de console terugkeren

>[!NOTE]
>
>U kunt de fragmentinhoud niet bewerken wanneer u fragmenten vergelijkt.

![cfm-6420-20](assets/cfm-6420-20.png)

## Een versie herstellen  {#reverting-to-a-version}

U kunt terugkeren naar een specifieke versie van het fragment:

* Rechtstreeks vanuit de [[!UICONTROL Timeline]](content-fragments-managing.md#timeline-for-content-fragments).

   Selecteer de gewenste versie en klik vervolgens op **[!UICONTROL Revert to this Version]** handeling.

* while [een versie vergelijken met de huidige versie](content-fragments-managing.md#comparing-fragment-versions) u **[!UICONTROL Revert]** naar de geselecteerde versie.

## Een fragment publiceren en ernaar verwijzen {#publishing-and-referencing-a-fragment}

>[!CAUTION]
>
>Als het fragment op een model is gebaseerd, moet u ervoor zorgen dat de [model is gepubliceerd](content-fragments-models.md#publishing-a-content-fragment-model).
>
>Als u een inhoudsfragment publiceert waarvoor het model nog niet is gepubliceerd, wordt dit in een selectielijst aangegeven en wordt het model met het fragment gepubliceerd.

Inhoudsfragmenten moeten worden gepubliceerd voor gebruik in de publicatieomgeving. Zij kunnen worden gepubliceerd:

* Na de aanmaak; van de **[!UICONTROL Assets]** console.
* Wanneer u [Een pagina publiceren die het fragment gebruikt](/help/sites-authoring/content-fragments.md#publishing); het fragment wordt weergegeven in de paginaverwijzingen.

>[!CAUTION]
>
>Nadat een fragment is gepubliceerd en/of waarnaar wordt verwezen, geeft AEM een waarschuwing weer wanneer een auteur het fragment opent om opnieuw te bewerken. Hiermee wordt u gewaarschuwd dat wijzigingen in het fragment ook van invloed zijn op de pagina&#39;s waarnaar wordt verwezen.

## Een fragment verwijderen {#deleting-a-fragment}

Een fragment verwijderen:

1. In de **[!UICONTROL Assets]** navigeren naar de locatie van het inhoudsfragment.
1. Selecteer het fragment.

   >[!NOTE]
   >
   >De **[!UICONTROL Delete]** Handeling is niet beschikbaar als een snelle handeling.

1. Selecteren **[!UICONTROL Delete]** op de werkbalk.
1. Bevestig de **[!UICONTROL Delete]** handeling.

   >[!CAUTION]
   >
   >Als er al naar het fragment wordt verwezen op een pagina, wordt er een waarschuwingsbericht weergegeven en moet u bevestigen dat u wilt doorgaan met een **[!UICONTROL Force Delete]**. Het fragment wordt samen met de bijbehorende component voor contentfragmenten uit alle contentpagina&#39;s verwijderd.
