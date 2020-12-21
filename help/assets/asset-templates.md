---
title: Elementsjablonen
description: Meer informatie over Asset-sjablonen in AEM Assets en over het gebruik van Asset-sjablonen om marketingmateriaal te maken.
uuid: 7ba87c1d-70cd-4b89-86f3-971b93885f1e
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 340b62f7-2405-4d2d-846d-2c444d6cc77b
translation-type: tm+mt
source-git-commit: b6f0dc15244f71ecdb8d937810d3c5d393a7712f
workflow-type: tm+mt
source-wordcount: '1571'
ht-degree: 0%

---


# Asset Templates {#asset-templates}

Elementsjablonen zijn een speciale klasse elementen die het snel opnieuw gebruiken van visueel rijke inhoud voor digitale media en gedrukte media mogelijk maken. Een activamalplaatje omvat twee delen, de vaste overseinensectie en de editable sectie.

De sectie met vaste berichten kan eigen inhoud bevatten, zoals merklogo en copyrightinformatie die zijn uitgeschakeld voor bewerking. De bewerkbare sectie kan visuele en tekstuele inhoud bevatten in velden die kunnen worden bewerkt om berichten aan te passen.

Dankzij de flexibiliteit om beperkte bewerkingen uit te voeren en globale handtekeningen te beveiligen, zijn asset templates ideaal voor bouwstenen voor snelle aanpassing en distributie van inhoud als inhoudsartefacten voor verschillende functies. Door inhoud te hergebruiken, worden de kosten voor het beheer van afdruk- en digitale kanalen verlaagd en kunnen holistische en consistente ervaringen op deze kanalen worden opgedaan.

Als markeerteken kunt u sjablonen opslaan en beheren in AEM Assets en één basissjabloon gebruiken om eenvoudig meerdere persoonlijke afdrukervaringen te maken. U kunt diverse soorten marketing onderpand, met inbegrip van brochures, vliegers, postcards, visitekaartjes, etc. tot stand brengen om uw marketing bericht aan klanten lucently over te brengen. U kunt ook uitvoer van meerdere pagina&#39;s samenstellen op basis van bestaande of nieuwe afdrukuitvoer. Met name kunt u tegelijkertijd eenvoudig zowel digitale als afdrukervaringen bieden, zodat gebruikers een consistente, geïntegreerde ervaring hebben.

Elementsjablonen zijn meestal InDesign-bestanden, maar de ervaring met InDesign vormt geen belemmering voor het maken van stellaire artefacten. U hoeft de velden van uw InDesign-sjabloon niet toe te wijzen aan de productvelden die u anders nodig hebt bij het maken van catalogi. U kunt de sjablonen in de WYSIWYG-modus rechtstreeks in de webinterface bewerken. Als InDesign uw bewerkingswijzigingen echter wil verwerken, moet u AEM Assets eerst configureren voor integratie met de InDesign-server.

De mogelijkheid om InDesign-sjablonen te bewerken vanuit de webinterface helpt u de samenwerking tussen Creative Suite- en Marketing-medewerkers te bevorderen en tegelijkertijd de tijd die nodig is om lokale promotieinitiatieven op de markt te brengen te verkorten.

U kunt het volgende doen met middelensjablonen:

* Bewerkbare sjabloonvelden wijzigen vanuit de webinterface
* De basisopmaak van tekst bepalen, zoals tekengrootte, stijl en tekst op tagniveau
* Afbeeldingen in de sjabloon wijzigen met de inhoudkiezer
* Sjabloonbewerkingen voorvertonen
* Meerdere sjabloonbestanden samenvoegen om een vervorming van meerdere pagina&#39;s te maken

Wanneer u een sjabloon voor uw onderpand kiest, maakt AEM Assets een kopie van de sjabloon die u kunt bewerken. De oorspronkelijke sjabloon blijft behouden, zodat uw globale handtekening intact blijft en opnieuw kan worden gebruikt om de consistentie van uw merk te handhaven.

U kunt het bijgewerkte bestand in de bovenliggende map in de volgende indelingen exporteren:

* INDD
* PDF
* JPG

U kunt de uitvoer in deze indelingen ook downloaden naar uw lokale systeem.

## Een zekerheid maken {#creating-a-collateral}

Overweeg een scenario waarin u digitaal afdrukbaar materiaal wilt maken, zoals brochures, vliegers en advertenties voor een komende campagne en wereldwijd wilt delen met verkooppunten. Het creëren van onderpand dat op een malplaatje wordt gebaseerd helpt een verenigde klantenervaring over kanalen leveren. Ontwerpers kunnen de campagnemalplaatjes (enig-pagina of multi-page) tot stand brengen gebruikend een creatieve oplossing, zoals InDesign en de malplaatjes uploaden aan AEM Assets voor u. Voordat u een zekerheid maakt, moet u een of meer INDD-sjablonen hebben geüpload naar en beschikbaar in Experience Manager vooraf.

1. Klik of tik op het AEM logo en klik op **[!UICONTROL Assets]** op de navigatiepagina.
1. Kies **[!UICONTROL Templates]** uit de opties.

   ![chlimage_1-306](assets/chlimage_1-306.png)

1. Klik/tik **[!UICONTROL Create]**, en kies dan het onderpand u van het menu wilt creëren. Kies bijvoorbeeld **[!UICONTROL Brochure]**.

   ![chlimage_1-307](assets/chlimage_1-307.png)

1. Een of meer INDD-sjablonen vooraf uploaden naar en beschikbaar hebben in Experience Manager. Kies een sjabloon voor de brochure en klik/tik **[!UICONTROL Next]**.

   ![chlimage_1-308](assets/chlimage_1-308.png)

1. Geef een naam en een optionele beschrijving voor de brochure op.

   ![chlimage_1-309](assets/chlimage_1-309.png)

1. (Optioneel) Klik/tik op het pictogram **[!UICONTROL Tags]** naast het veld **[!UICONTROL Tags]** en selecteer een of meer tags voor de brochure. Klik/tik **[!UICONTROL Confirm]** om uw selectie te bevestigen.

   ![chlimage_1-310](assets/chlimage_1-310.png)

1. Klik op **[!UICONTROL Create]**. Een dialoogvenster bevestigt dat er een nieuwe brochure wordt gemaakt. Klik/tik **[!UICONTROL Open]** om de brochure in Edit wijze te openen.

   ![chlimage_1-311](assets/chlimage_1-311.png)

   U kunt ook het dialoogvenster sluiten en naar de map op de pagina Sjablonen gaan waarmee u bent begonnen om de brochure weer te geven die u hebt gemaakt. Het type van het onderpand verschijnt op zijn duimnagel in kaartmening. In dit geval wordt de brochure bijvoorbeeld weergegeven op de miniatuur.

   ![chlimage_1-312](assets/chlimage_1-312.png)

## Een zekerheden bewerken {#editing-a-collateral}

U kunt direct nadat u het hebt gemaakt, een onderpand bewerken. U kunt de sjabloon ook openen vanaf de pagina Sjablonen of de elementpagina.

1. Voer een van de volgende handelingen uit om het onderpand te openen voor bewerking:

   * Open het onderpand (brochure in dit geval) u in stap 7 van [het Creëren van een Zekerheid ](asset-templates.md#creating-a-collateral) creeerde.
   * Navigeer op de pagina Sjablonen naar de map waarin u het onderpand hebt gemaakt en klik of tik op de handeling Snel bewerken op de miniatuur van het onderpand.
   * Klik/tik op het pictogram Bewerken op de werkbalk op de elementpagina voor het onderpand.
   * Selecteer het onderpand en klik/tik op het pictogram Bewerken op de werkbalk.

   ![chlimage_1-313](assets/chlimage_1-313.png)

   De elementenzoeker en de teksteditor worden links op de pagina weergegeven. De teksteditor is standaard geopend.

   U kunt de teksteditor gebruiken om de tekst te wijzigen die u in het tekstveld wilt weergeven. U kunt de tekengrootte, stijl, kleur en tekst op tagniveau wijzigen.

   Met behulp van de zoekfunctie voor middelen kunt u in AEM Assets door afbeeldingen bladeren of naar afbeeldingen zoeken en de bewerkbare afbeeldingen in de sjabloon vervangen door afbeeldingen van uw keuze.

   ![chlimage_1-314](assets/chlimage_1-314.png)

   De bewerkbare tekst wordt rechts weergegeven. Een veld kan alleen in AEM Assets worden bewerkt als het desbetreffende veld in de sjabloon is gecodeerd in InDesign. Met andere woorden, ze moeten in InDesign bewerkbaar worden gemaakt.

   ![chlimage_1-315](assets/chlimage_1-315.png)

   >[!NOTE]
   >
   >Zorg ervoor dat uw AEM-instantie is geïntegreerd met een InDesign-server, zodat AEM Assets gegevens kan extraheren uit de InDesign-sjabloon en deze beschikbaar kan maken voor bewerking. Zie [AEM Assets integreren met InDesign Server](indesign.md) voor meer informatie.

1. Als u de tekst in een bewerkbaar veld wilt wijzigen, klikt of tikt u op het tekstveld in de lijst met bewerkbare velden en bewerkt u de tekst in het veld.

   ![chlimage_1-316](assets/chlimage_1-316.png)

   U kunt de teksteigenschappen, zoals lettertypestijl, -kleur en -grootte, bewerken met de beschikbare opties.

1. Klik/tik het **[!UICONTROL Preview]** pictogram om een voorvertoning van de tekstveranderingen te bekijken.

   ![chlimage_1-317](assets/chlimage_1-317.png)

1. Als u een afbeelding wilt omwisselen, klikt of tikt u op het pictogram **[!UICONTROL Asset Finder]**.

   ![chlimage_1-318](assets/chlimage_1-318.png)

1. Selecteer het afbeeldingsveld in de lijst met bewerkbare velden en sleep een gewenste afbeelding van de elementkiezer naar het bewerkbare veld.

   ![chlimage_1-319](assets/chlimage_1-319.png)

   U kunt ook naar afbeeldingen zoeken met behulp van trefwoorden, tags en op basis van hun publicatiestatus. U kunt door de AEM Assets-opslagplaats bladeren en naar de locatie van de gewenste afbeelding navigeren.

   ![chlimage_1-320](assets/chlimage_1-320.png)

1. Klik/tik het **[!UICONTROL Preview]** pictogram om een voorvertoning van het beeld te bekijken.

   ![chlimage_1-321](assets/chlimage_1-321.png)

1. Als u een specifieke pagina in een pagina-element wilt bewerken dat uit meerdere pagina&#39;s bestaat, gebruikt u de paginanavigator onderaan.

   ![chlimage_1-322](assets/chlimage_1-322.png)

1. Klik/tik het **[!UICONTROL Preview]** pictogram op de toolbar om voorproef alle veranderingen. Klik/tik **[!UICONTROL Done]** om de het uitgeven veranderingen in het onderpand te bewaren.

   >[!NOTE]
   >
   >De pictogrammen Voorvertoning en Gereed zijn alleen beschikbaar als de bewerkbare afbeeldingsvelden in het onderpand geen ontbrekende pictogrammen hebben. Als er pictogrammen ontbreken in het onderpand, komt dat omdat AEM de afbeeldingen in de InDesign-sjabloon niet kan oplossen. In de volgende gevallen kunnen AEM afbeeldingen gewoonlijk niet oplossen:
   >
   >* Afbeeldingen worden niet ingesloten in de onderliggende InDesign-sjabloon
   >* Afbeeldingen worden gekoppeld vanuit het lokale bestandssysteem

   >
   >Ga als volgt te werk om AEM in te schakelen om afbeeldingen op te lossen:
   >
   >* Afbeeldingen insluiten tijdens het maken van InDesign-sjablonen (zie [Informatie over koppelingen en ingesloten afbeeldingen](https://helpx.adobe.com/indesign/using/graphics-links.html)).
   >* Koppel AEM aan uw lokale bestandssysteem en wijs vervolgens ontbrekende pictogrammen toe aan bestaande AEM.

   >
   >Voor meer informatie rond het werken met de documenten van InDesign, zie [Beste praktijken voor het Werken met de Documenten van InDesign in AEM](https://helpx.adobe.com/experience-manager/kb/best-practices-idd-docs-aem.html).

1. Als u een PDF-uitvoering voor de brochure wilt genereren, selecteert u de optie Acrobat in het dialoogvenster en klikt u op **[!UICONTROL Continue]**.
1. Het onderpand wordt gecreeerd in de omslag u met begon. Als u de vertoningen wilt weergeven, opent u het desbetreffende element en kiest u **[!UICONTROL Renditions]** in de lijst GlobalNav.

   ![chlimage_1-323](assets/chlimage_1-323.png)

1. Klik/tik op de PDF-uitvoering in de lijst met uitvoeringen om het PDF-bestand te downloaden. Open het PDF-bestand om het onderpand te bekijken.

   ![chlimage_1-324](assets/chlimage_1-324.png)

## Zekerheden samenvoegen {#merge-collateral}


1. Klik of tik **[!UICONTROL Tools > Assets]**.
1. Kies **[!UICONTROL Templates]** uit de opties.
1. Klik/tik **[!UICONTROL Create]** en kies **[!UICONTROL Merge]** van het menu.

   ![chlimage_1-325](assets/chlimage_1-325.png)

1. Klik/tik op het pictogram Samenvoegen op de pagina Sjabloon samenvoegen.

   ![chlimage_1-326](assets/chlimage_1-326.png)

1. Navigeer naar de locatie van de elementen die u wilt samenvoegen, klik of tik op de miniaturen van de elementen die u wilt samenvoegen om deze te selecteren.

   ![chlimage_1-327](assets/chlimage_1-327.png)

   U kunt zelfs sjablonen zoeken in het vak UniverseelZoeken.

   ![chlimage_1-328](assets/chlimage_1-328.png)

   U kunt door de AEM Assets-opslagplaats of -verzamelingen bladeren, naar de locatie van de gewenste sjablonen navigeren en deze vervolgens selecteren om samen te voegen.

   ![chlimage_1-329](assets/chlimage_1-329.png)

   U kunt verschillende filters toepassen om de gewenste sjablonen te doorzoeken. U kunt bijvoorbeeld naar sjablonen zoeken op basis van het bestandstype of de tags.

   ![chlimage_1-330](assets/chlimage_1-330.png)

1. Klik/tik **[!UICONTROL Next]** van de toolbar.
1. Wijzig in het scherm **[!UICONTROL Preview & Reorder]** desgewenst de sjablonen en geef een voorvertoning weer van de sjablonen die u wilt samenvoegen. Klik vervolgens op of tik op **[!UICONTROL Next]** op de werkbalk.

   ![chlimage_1-331](assets/chlimage_1-331.png)

1. In het Configure scherm van het Malplaatje, specificeer een naam voor het onderpand. U kunt desgewenst tags opgeven die u geschikt acht. Als u de uitvoer in PDF-indeling wilt exporteren, selecteert u de optie **[!UICONTROL Acrobat (.PDF)]**. Standaard wordt het onderpand geëxporteerd in JPG- en InDesign-indeling. Klik op **[!UICONTROL Change Thumbnail]** om de weergaveminiatuur voor de pagina-elementen te wijzigen.

   ![chlimage_1-332](assets/chlimage_1-332.png)

1. Klik/tik **[!UICONTROL Save]** en klik/tik **[!UICONTROL OK]** in het dialoogvenster om het dialoogvenster te sluiten. Het uit meerdere pagina&#39;s bestaande element wordt gemaakt in de map waarmee u bent begonnen.

   >[!NOTE]
   >
   >U kunt een samengevoegd onderpand later niet bewerken of gebruiken om ander onderpand te maken.

