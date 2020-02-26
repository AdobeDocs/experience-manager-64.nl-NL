---
title: Gebruik metagegevensprofielen om standaardmetagegevens toe te passen op alle elementen in een map
description: Informatie over metagegevensprofielen voor elementen. Leer hoe u een metagegevensprofiel maakt en toepast op mapelementen.
contentOwner: AG
translation-type: tm+mt
source-git-commit: af1955ab1fdcf16dd9a9d3ad36336e6c1aac9312

---


# Metadataprofielen {#metadata-profiles}

Met een metagegevensprofiel kunt u standaardmetagegevens toepassen op elementen in een map. Maak een metagegevensprofiel en pas dit toe op een map. Elk element dat u vervolgens uploadt naar de map, neemt de standaardmetagegevens over die u hebt geconfigureerd in het metagegevensprofiel.

## Een metagegevensprofiel toevoegen {#adding-a-metadata-profile}

1. Tik of klik op het AEM-logo en navigeer naar **[!UICONTROL Gereedschappen > Middelen > Metagegevensprofielen]** en tik op **[!UICONTROL Maken]**.
1. Voer een titel in voor Metagegevensprofiel, bijvoorbeeld Voorbeeldmetagegevens, en klik op **[!UICONTROL Verzenden]**. Het formulier **** Bewerken voor het metagegevensprofiel wordt weergegeven.

   ![chlimage_1-480](assets/chlimage_1-480.png)

1. Klik op een component en configureer de eigenschappen ervan op het tabblad **[!UICONTROL Instellingen]** . Klik bijvoorbeeld op de component **[!UICONTROL Beschrijving]** en bewerk de eigenschappen ervan.

   ![chlimage_1-481](assets/chlimage_1-481.png)

   Bewerk de volgende eigenschappen voor de component **[!UICONTROL Description]** :

   * **[!UICONTROL Veldlabel]**: De weergavenaam van de eigenschap metadata. Dit is alleen voor de gebruikersverwijzing.
   * **[!UICONTROL Toewijzen aan eigenschap]**: De waarde van deze eigenschap geeft het relatieve pad/de naam naar het knooppunt met middelen waar het wordt opgeslagen in de opslagplaats. De waarde moet altijd beginnen met `./` omdat dit aangeeft dat het pad zich onder het knooppunt van het element bevindt.
   ![chlimage_1-482](assets/chlimage_1-482.png)

   De waarde die u opgeeft voor de eigenschap **** Map to wordt opgeslagen als een eigenschap onder het metagegevensknooppunt van het element. Bijvoorbeeld als u opgeeft. `/jcr:content/metadata/dc:desc` als naam van **[!UICONTROL Kaart aan bezit]**, slaat de Middelen van AEM de waarde `dc:desc` bij de de meta-gegevensknoop van het element op.

   * **[!UICONTROL Standaardwaarde]**: Gebruik deze eigenschap om een standaardwaarde voor de metagegevenscomponent toe te voegen. Als u bijvoorbeeld &quot;Mijn beschrijving&quot; opgeeft, wordt deze waarde toegewezen aan de eigenschap `dc:desc` in het metagegevensknooppunt van het element.
   ![chlimage_1-483](assets/chlimage_1-483.png)

   >[!NOTE]
   >
   >Een standaardwaarde toevoegen aan een nieuwe eigenschap metadata (die nog niet bestaat op het tabblad . `/jcr:content/metadata` node) geeft de eigenschap en de waarde ervan standaard niet weer op de pagina **[!UICONTROL Eigenschappen]** van het element. Als u de nieuwe eigenschap wilt weergeven op de pagina [!UICONTROL Eigenschappen] van het element, wijzigt u het corresponderende schema.

1. (Optioneel) Voeg meer componenten toe aan het **[!UICONTROL bewerkingsformulier]** op het tabblad **[!UICONTROL Formulier]** samenstellen en configureer de eigenschappen op het tabblad **[!UICONTROL Instellingen]** . De volgende eigenschappen zijn beschikbaar op het tabblad **[!UICONTROL Formulier]** samenstellen:

| Component | Eigenschappen |
|---|---|
| [!UICONTROL Sectiekop] | Veldlabel, <br> beschrijving |
| [!UICONTROL Tekst met één regel] | Veld, label, <br> toewijzen aan eigenschap, <br> standaardwaarde |
| [!UICONTROL Meerdere waardetekst] | Veld, label, <br> toewijzen aan eigenschap, <br> standaardwaarde |
| [!UICONTROL Getal] | Veld, label, <br> toewijzen aan eigenschap, <br> standaardwaarde |
| [!UICONTROL Date] | Veld, label, <br> toewijzen aan eigenschap, <br> standaardwaarde |
| [!UICONTROL Standaardlabels] | Veld, label, <br> toewijzen aan eigenschap, <br> standaardwaarde, <br> beschrijving |

![chlimage_1-484](assets/chlimage_1-484.png)

1. Klik op **[!UICONTROL Gereed]**. Het metagegevensprofiel wordt toegevoegd aan de lijst met profielen op de pagina **[!UICONTROL Metagegevensprofielen]** .

   ![chlimage_1-485](assets/chlimage_1-485.png)

## Een metagegevensprofiel kopiëren {#copying-a-metadata-profile}

1. Selecteer op de pagina **[!UICONTROL Metagegevensprofielen]** een profiel om er een kopie van te maken.

   ![chlimage_1-486](assets/chlimage_1-486.png)

1. Klik op **[!UICONTROL Kopiëren]** op de werkbalk.
1. Voer in het dialoogvenster Metagegevensprofiel **** kopiëren een titel in voor de nieuwe kopie van het profiel.
1. Klik op **[!UICONTROL Kopiëren]**. Een kopie van het profiel wordt weergegeven in de lijst met profielen op de pagina **[!UICONTROL Metagegevensprofielen]** .

   ![chlimage_1-487](assets/chlimage_1-487.png)

## Een metagegevensprofiel verwijderen {#deleting-a-metadata-profile}

1. Selecteer op de pagina **[!UICONTROL Metagegevensprofielen]** een profiel dat u wilt verwijderen.

   ![chlimage_1-488](assets/chlimage_1-488.png)

1. Klik op **[!UICONTROL Metagegevensprofielen]** verwijderen op de werkbalk.
1. Klik in het dialoogvenster op **[!UICONTROL Verwijderen]** om het verwijderen te bevestigen. Het metagegevensprofiel wordt uit de lijst verwijderd.

## Een metagegevensprofiel toepassen op mappen {#applying-a-metadata-profile-to-folders}

Wanneer u een metagegevensprofiel toewijst aan een map, nemen eventuele submappen het profiel automatisch over van de bovenliggende map. Dit betekent dat u slechts één metagegevensprofiel kunt toewijzen aan een map. Denk daarom zorgvuldig na over de mapstructuur van de locatie waar u middelen uploadt, opslaat, gebruikt en archiveert.

Als u een ander metagegevensprofiel aan een map hebt toegewezen, overschrijft het nieuwe profiel het vorige profiel. De vorige bestaande mapelementen blijven ongewijzigd. Het nieuwe profiel wordt toegepast op de elementen die later aan de map worden toegevoegd.

Mappen waaraan een profiel is toegewezen, worden in de gebruikersinterface aangeduid met de naam van het profiel dat in de kaartnaam wordt weergegeven.

![chlimage_1-489](assets/chlimage_1-489.png)

U kunt metagegevensprofielen toepassen op specifieke mappen of op alle elementen.

### Metagegevensprofielen toepassen op specifieke mappen {#applying-metadata-profiles-to-specific-folders}

U kunt een metagegevensprofiel toepassen op een map vanuit het menu **[!UICONTROL Gereedschappen]** of vanuit **[!UICONTROL Eigenschappen]** in de map. In deze sectie wordt beschreven hoe u op beide manieren metagegevensprofielen kunt toepassen op mappen.

Mappen waaraan al een profiel is toegewezen, worden aangegeven door de naam van het profiel direct onder de mapnaam weer te geven.

#### Metagegevensprofielen toepassen op mappen vanuit de gebruikersinterface Profielen {#applying-metadata-profiles-to-folders-from-profiles-user-interface}

1. Tik op het AEM-logo en navigeer naar **[!UICONTROL Gereedschappen > Middelen > Metagegevensprofielen]**.
1. Selecteer het metagegevensprofiel dat u wilt toepassen op een of meerdere mappen.

   ![chlimage_1-490](assets/chlimage_1-490.png)

1. Tik op Metagegevensprofiel **[!UICONTROL toepassen op map(pen)]** en selecteer de map of meerdere mappen die u wilt gebruiken voor de zojuist geüploade elementen en tik op **[!UICONTROL Gereed]**. Mappen waaraan al een profiel is toegewezen, worden aangegeven door de naam van het profiel direct onder de mapnaam weer te geven.

#### Metagegevensprofielen toepassen op mappen vanuit Eigenschappen {#applying-metadata-profiles-to-folders-from-properties}

1. Tik in het linkerspoor op **[!UICONTROL Middelen]** en navigeer naar de map waarop u een metagegevensprofiel wilt toepassen.
1. Tik in de map op het vinkje om het te selecteren en tik vervolgens op **[!UICONTROL Eigenschappen]**.

1. Selecteer het tabblad **[!UICONTROL Metagegevensprofielen]** , selecteer het profiel in de vervolgkeuzelijst en klik op **[!UICONTROL Opslaan]**.

   ![chlimage_1-491](assets/chlimage_1-491.png)

   Mappen waaraan al een profiel is toegewezen, worden aangegeven door de naam van het profiel direct onder de mapnaam weer te geven.

### Een metagegevensprofiel algemeen toepassen {#applying-a-metadata-profile-globally}

Naast het toepassen van een profiel op een map, kunt u er ook een globaal toepassen, zodat het geselecteerde profiel wordt toegepast op inhoud die in AEM-elementen in een map is geüpload. Ga als volgt te werk als u een metagegevensprofiel globaal wilt toepassen:

1. Voer een van de volgende handelingen uit:

   * Navigeer naar `https://[aem_server]:[port]/mnt/overlay/dam/gui/content/assets/foldersharewizard.html/content/dam` en pas het juiste profiel toe en tik op **[!UICONTROL Opslaan]** of klik op Opslaan.

      ![chlimage_1-492](assets/chlimage_1-492.png)

   * Navigeer naar CRXDE Lite naar het volgende knooppunt: `/content/dam/jcr:content`. Voeg de eigenschap toe `metadataProfile:/etc/dam/metadata/dynamicmedia/<name_of_metadata_profile>` en tik op **[!UICONTROL Alles]** opslaan.

      ![chlimage_1-493](assets/chlimage_1-493.png)

## Een metagegevensprofiel uit mappen verwijderen {#removing-a-metadata-profile-from-folders}

Wanneer u een metagegevensprofiel uit een map verwijdert, nemen eventuele submappen automatisch de verwijdering van het profiel uit de bovenliggende map over. Alle verwerking van bestanden die in de mappen zijn opgetreden, blijft echter intact.

U kunt een metagegevensprofiel uit een map verwijderen vanuit het menu **[!UICONTROL Gereedschappen]** of vanuit de map **[!UICONTROL Eigenschappen]**. In deze sectie wordt beschreven hoe u metagegevensprofielen op beide manieren uit mappen kunt verwijderen.

### Metaprofielen uit mappen verwijderen via de gebruikersinterface Profielen {#removing-metadata-profiles-from-folders-via-profiles-user-interface}

Ga als volgt te werk als u een metagegevensprofiel uit mappen wilt verwijderen via de gebruikersinterface van Profielen:

1. Tik op het AEM-logo en navigeer naar **[!UICONTROL Gereedschappen > Middelen > Metagegevensprofielen]**.
1. Selecteer het metagegevensprofiel dat u uit een of meerdere mappen wilt verwijderen.
1. Tik op Metagegevensprofiel **[!UICONTROL verwijderen uit map(pen)]** en selecteer de map of meerdere mappen waaruit u een profiel wilt verwijderen. Tik vervolgens op **[!UICONTROL Gereed]**.

   U kunt bevestigen dat het metagegevensprofiel niet meer wordt toegepast op een map omdat de naam niet langer onder de mapnaam wordt weergegeven.

### Metagegevensprofielen uit mappen verwijderen met eigenschappen {#removing-metadata-profiles-from-folders-via-properties}

1. Tik op het AEM-logo en navigeer naar **[!UICONTROL Middelen]** en vervolgens naar de map waaruit u een metagegevensprofiel wilt verwijderen.
1. Tik in de map op het vinkje om het te selecteren en tik vervolgens op **[!UICONTROL Eigenschappen]**.
1. Selecteer het tabblad **[!UICONTROL Metagegevensprofielen]** en selecteer **[!UICONTROL Geen]** in het keuzemenu. Tik op **[!UICONTROL Opslaan]**.

Mappen waaraan al een profiel is toegewezen, worden aangegeven door de naam van het profiel direct onder de mapnaam weer te geven.
