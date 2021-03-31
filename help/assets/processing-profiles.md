---
title: Profielen voor het verwerken van metagegevens, afbeeldingen en video's
description: Een profiel is een set regels met betrekking tot de opties die moeten worden toegepast op elementen die naar een map zijn geüpload. Geef op welk metagegevensprofiel en videocoderingsprofiel u wilt toepassen op de video-elementen die u uploadt. Voor afbeeldingselementen kunt u ook opgeven welk afbeeldingsprofiel u wilt toepassen op afbeeldingselementen om deze op de juiste wijze te laten bijsnijden.
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
feature: Workflow,middelenbeheer,uitvoeringen
role: Business Practice,Administrator
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '1333'
ht-degree: 2%

---


# Profielen voor het verwerken van metagegevens, afbeeldingen en video&#39;s {#profiles-for-processing-metadata-images-and-videos}

Een profiel is een recept voor welke opties u kunt toepassen op middelen die naar een map worden geüpload. U kunt bijvoorbeeld opgeven welk metagegevensprofiel en videocoderingsprofiel u wilt toepassen op video-elementen die u uploadt. Of welk afbeeldingsprofiel u wilt toepassen op afbeeldingselementen om deze op de juiste wijze te laten bijsnijden.

Deze regels kunnen het toevoegen van metagegevens, het slim uitsnijden van afbeeldingen of het instellen van videocoderingsprofielen omvatten. In AEM kunt u drie typen profielen maken, die in detail worden besproken op de volgende koppelingen:

* [Metadataprofielen](metadata-profiles.md)
* [Afbeeldingsprofielen](image-profiles.md)
* [Videoprofielen](video-profiles.md)

U moet beheerdersrechten hebben om metagegevens, afbeeldingen of videoprofielen te maken, te bewerken en te verwijderen.

Nadat u de metagegevens, de afbeelding of het videoprofiel hebt gemaakt, wijst u deze toe aan een of meer mappen die u gebruikt als bestemming voor nieuw geüploade elementen.

Een belangrijk concept voor het gebruik van profielen in AEM Assets is dat deze aan mappen worden toegewezen. Binnen een profiel bevinden zich instellingen in de vorm van metagegevensprofielen, samen met videoprofielen of afbeeldingsprofielen. Met deze instellingen wordt de inhoud van een map samen met een van de submappen verwerkt. Daarom heeft de manier waarop u bestanden en mappen benoemt, hoe u submappen ordent en hoe u de bestanden in deze mappen verwerkt, een grote invloed op de manier waarop deze elementen door een profiel worden verwerkt. Door consistente en geschikte naamgevingsstrategieën voor bestanden en mappen te gebruiken, samen met goede praktijken voor metagegevens, kunt u optimaal gebruikmaken van de verzameling van digitale elementen en ervoor zorgen dat de juiste bestanden worden verwerkt door het juiste profiel. Zie [Elementen ordenen met mappen](organize-assets.md#organize-using-folders) voor een voorbeeld.

>[!NOTE]
>
>Elementen die u van de ene map naar de andere verplaatst, worden niet opnieuw verwerkt. Stel dat u Map 1 hebt waaraan profiel A is toegewezen en Map 2 waaraan profiel B is toegewezen. Als u elementen verplaatst van map 1 naar map 2, behouden de verplaatste elementen hun oorspronkelijke verwerking van map 1.
>
>Hetzelfde geldt ook wanneer u elementen verplaatst tussen twee mappen waaraan hetzelfde profiel is toegewezen.

## Elementen in een map {#reprocessing-assets} opnieuw verwerken

>[!NOTE]
>
>Alleen van toepassing op *Dynamic Media - Scene7 mode* in AEM 6.4.7.0 of later.

U kunt elementen opnieuw verwerken in een map die al een bestaand verwerkingsprofiel heeft dat u later hebt gewijzigd.

Stel dat u een afbeeldingsprofiel hebt gemaakt en dit aan een map hebt toegewezen. Bij alle afbeeldingselementen die u naar de map hebt geüpload, wordt het afbeeldingsprofiel automatisch toegepast op de elementen. Later besluit u echter om een nieuwe verhouding voor slimme uitsnijden toe te voegen aan het profiel. Nu hoeft u de elementen niet meer opnieuw naar de map te selecteren en te uploaden, maar gewoon de *Scene7 uit te voeren: Elementen opnieuw verwerken* workflow.

U kunt de herverwerkingsworkflow uitvoeren op een element waarvoor de verwerking de eerste keer is mislukt. Zelfs als u geen verwerkingsprofiel hebt bewerkt of geen verwerkingsprofiel hebt toegepast, kunt u de herverwerkingsworkflow op elk gewenst moment op een map met middelen uitvoeren.

U kunt optioneel de batchgrootte van de workflow voor het opnieuw verwerken aanpassen van een standaard van 50 elementen tot 1000 elementen. Wanneer u _Scene7 in werking stelt: Elementen opnieuw verwerken_ in een map, middelen worden gegroepeerd in batches en vervolgens naar de Dynamic Media-server verzonden voor verwerking. Na de verwerking worden de metagegevens van elk element in de volledige batchset bijgewerkt op AEM. Als de partij erg groot is, kan er een vertraging optreden bij de verwerking. Als de batch te klein is, kunnen er te veel ronde overgangen naar de Dynamic Media-server plaatsvinden.

Zie [De batchgrootte van de workflow voor opnieuw verwerken aanpassen](#adjusting-load).

>[!NOTE]
>
>Als u een massale migratie van middelen van Dynamic Media Classic naar AEM uitvoert, moet u de de replicatieagent van de Migratie op de server van Dynamic Media toelaten. Wanneer de migratie volledig is, zorg ervoor u de agent onbruikbaar maakt. De Migratie-publicatieagent moet zijn uitgeschakeld op de Dynamic Media-server, zodat de workflow voor opnieuw verwerken naar behoren functioneert.

<!-- Batch size is the number of assets that are amalgamated into a single IPS (Dynamic Media’s Image Production System) job. When you run the Scene7: Reprocess Assets workflow, the job is triggered on IPS. The number of IPS jobs that are triggered is based on the total number of assets in the folder, divided by the batch size. For example, suppose you had a folder with 150 assets and a batch size of 50. In this case, three IPS jobs are triggered. The assets are updated when the entire batch size (50 in our example) is processed in IPS. The job then moves onto the next IPS job and so on until complete. If you increase the batch size, you may notice a longer delay with assets getting updated. -->

**Elementen in een map** opnieuw verwerken:

1. Navigeer AEM vanaf de elementenpagina naar een map met elementen waaraan een verwerkingsprofiel is toegewezen en waarvoor u de **Scene7 wilt toepassen: Asset** opnieuw verwerken,

   Mappen waaraan al een verwerkingsprofiel is toegewezen, worden aangegeven door de naam van het profiel direct onder de mapnaam in de Kaartweergave weer te geven.

1. Selecteer een map.

   * In de workflow worden alle bestanden in de geselecteerde map recursief bekeken.
   * Als er een of meer submappen met elementen in de geselecteerde hoofdmap staan, wordt elk element in de mappenhiërarchie opnieuw verwerkt.
   * U kunt het beste deze workflow niet uitvoeren in een mappenhiërarchie met meer dan 1000 elementen.

1. Klik in de linkerbovenhoek van de pagina in de vervolgkeuzelijst op **[!UICONTROL Timeline]**.
1. Klik in de linkerbenedenhoek van de pagina, rechts van het veld Opmerking, op het karatpictogram ( **^** ).

   ![Workflow 1 voor opnieuw verwerken van middelen](/help/assets/assets/reprocess-assets1.png)

1. Klik op **[!UICONTROL Start Workflow]**.
1. Kies **[!UICONTROL Scene7: Reprocess Assets]** in de vervolgkeuzelijst **[!UICONTROL Start Workflow]**.
1. (Optioneel) Voer in het tekstveld **Voer een titel van de workflow in** een naam voor de workflow in. U kunt de naam gebruiken om naar de werkstroominstantie te verwijzen, indien nodig.

   ![Activa opnieuw verwerken 2](/help/assets/assets/reprocess-assets2.png)

1. Klik **[!UICONTROL Start]**, dan klik **[!UICONTROL Confirm]**.

   Klik op **[!UICONTROL Tools > Workflow]** om de workflow te controleren of de voortgang van de AEM te controleren. Selecteer een workflow op de pagina Workflowinstanties. Klik op **[!UICONTROL Open History]** op de menubalk. U kunt een geselecteerde workflow ook beëindigen, opschorten of hernoemen vanuit dezelfde pagina Workflowinstanties.

### De batchgrootte van de workflow voor opnieuw verwerken aanpassen {#adjusting-load}

(Optioneel) De standaardbatch-grootte in de opwerkingsworkflow is 50 elementen per taak. Deze optimale omvang van de partijen wordt bepaald door de gemiddelde omvang van de activa en de typen activa waarvoor het herproces wordt uitgevoerd. Een hogere waarde betekent dat u veel bestanden in één herverwerkingstaak hebt. De verwerkingsbanner blijft daarom langer op AEM middelen staan. Als de gemiddelde bestandsgrootte echter klein-1 MB of kleiner-Adobe is, wordt u aangeraden de waarde te verhogen tot honderden, maar nooit meer dan 1000. Als het gemiddelde bestand groot-honderden megabytes-Adobe is, kunt u het beste de batch tot 10 verkleinen.

**De batchgrootte van de workflow voor opnieuw verwerken optioneel aanpassen**

1. Tik in Experience Manager op **[!UICONTROL Adobe Experience Manager]** om naar de globale navigatieconsole te gaan en tik vervolgens op het pictogram **[!UICONTROL Tools]** (hamer) > **[!UICONTROL Workflow > Models]**.
1. Voor de pagina van de Modellen van het Werkschema, in de Mening van de Kaart of de Mening van de Lijst, selecteer **[!UICONTROL Scene7: Reprocess Assets]**.

   ![Pagina Workflowmodellen met Scene7: Workflow voor opnieuw verwerken van middelen die zijn geselecteerd in Kaartweergave](/help/assets/assets-dm/reprocess-assets7.png)

1. Klik op **[!UICONTROL Edit]** op de werkbalk. Met een nieuw browsertabblad wordt de Scene7 geopend: Modelpagina voor middelenwerkstroom opnieuw verwerken.
1. Op de Scene7: Tik in de rechterbovenhoek op **[!UICONTROL Edit]** om de workflow te &quot;ontgrendelen&quot;.
1. Selecteer in de workflow de Scene7-component Batch uploaden om de werkbalk te openen en tik vervolgens op **[!UICONTROL Configure]** op de werkbalk.

   ![Scene7-component Batch uploaden](/help/assets/assets-dm/reprocess-assets8.png)

1. Stel in het dialoogvenster **[!UICONTROL Batch Upload to Scene7–Step Properties]** het volgende in:
   * Typ desgewenst een nieuwe titel en beschrijving voor de taak in de tekstvelden **[!UICONTROL Title]** en **[!UICONTROL Description]**.
   * Selecteer **[!UICONTROL Handler Advance]** als uw manager aan de volgende stap zal verdergaan.
   * Voer in het veld **[!UICONTROL Timeout]** de time-out van het externe proces (seconden) in.
   * Voer in het veld **[!UICONTROL Period]** een pollinginterval (seconden) in om te testen of het externe proces is voltooid.
   * Voer in **[!UICONTROL Batch field]** het maximumaantal elementen (50-1000) in dat u wilt verwerken in een uploadtaak voor batchverwerking van een Dynamic Media-server.
   * Selecteer **[!UICONTROL Advance on timeout]** als u wilt vooruitgaan wanneer de onderbreking wordt bereikt. Schakel deze optie uit als u wilt doorgaan naar het Postvak IN wanneer de time-out is bereikt.

   ![Eigenschappen, dialoogvenster](/help/assets/assets-dm/reprocess-assets3.png)

1. Tik in de rechterbovenhoek van het dialoogvenster **[!UICONTROL Batch Upload to Scene7–Step Properties]** op **[!UICONTROL Done]**.

1. In de rechterbovenhoek van de Scene7: Tik op **[!UICONTROL Sync]** om de modelpagina Elementen opnieuw te verwerken. Wanneer u **[!UICONTROL Synced]** ziet, wordt het model van de werkschemaruntime met succes gesynchroniseerd en klaar om activa in een omslag opnieuw te verwerken.

   ![Het workflowmodel synchroniseren](/help/assets/assets-dm/reprocess-assets1.png)

1. Sluit het browsertabblad waarin de Scene7 wordt weergegeven: Workflowmodel voor opnieuw verwerken van middelen.

<!-- 1. Return to the browser tab that has the open Workflow Models page, then press **Esc** to exit the selection.
1. In the upper-left corner of the page, tap **[!UICONTROL Adobe Experience Manager]** to access the global navigation console, then tap the **[!UICONTROL Tools]** (hammer) icon > **[!UICONTROL General > CRXDE Lite]**.
1. In the folder tree on the left side of the CRXDE Lite page, navigate to the following location:

   `/conf/global/settings/workflow/models/scene7_reprocess_assets/jcr:content/flow/reprocess/metaData`

   ![CRXDE Lite](/help/assets/assets/workflow-models9.png)

1. On the right side of the CRXDE Lite page, in the lower portion, enter the following name, type, and value in its respective field:
    * **[!UICONTROL Name]**: `reprocess-batch-size`
    * **[!UICONTROL Type]**: `Long`
    * **[!UICONTROL Value]**: enter a default value (50-1000) for the batch size
1. In the lower-right corner, tap **[!UICONTROL Add]**. The new property appears as the following:

    ![Saving the new property](/help/assets/assets/workflow-models10.png)

1. On the menu bar of the CRXDE Lite page, tap **[!UICONTROL Save All]**.
1. In the upper-left corner of the page, tap **[!UICONTROL CRXDE Lite]** to return to the main AEM console
1. Repeat steps 1-7 to re-synchronize the new batch size to the Scene7: Reprocess Assets workflow model. -->
