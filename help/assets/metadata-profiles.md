---
title: Gebruik metagegevensprofielen om standaardmetagegevens toe te passen op alle elementen in een map
description: Informatie over metagegevensprofielen voor elementen. Leer hoe u een metagegevensprofiel maakt en toepast op mapelementen.
contentOwner: AG
feature: Metadata
role: User,Admin
exl-id: a7b0f1d6-7deb-4565-8c7f-27cad7cd6bf8
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1159'
ht-degree: 16%

---

# Metadataprofielen {#metadata-profiles}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Met een metagegevensprofiel kunt u standaardmetagegevens toepassen op elementen in een map. Maak een metagegevensprofiel en pas dit toe op een map. Elk element dat u vervolgens uploadt naar de map, neemt de standaardmetagegevens over die u hebt geconfigureerd in het metagegevensprofiel.

## Een metagegevensprofiel toevoegen {#adding-a-metadata-profile}

1. Tik of klik op de knop [!DNL Experience Manager] logo en navigeer naar **[!UICONTROL Tools > Assets > Metadata Profiles]** en tikt u vervolgens op **[!UICONTROL Create]**.
1. Voer een titel in voor het metagegevensprofiel, bijvoorbeeld Voorbeeldmetagegevens, en klik op **[!UICONTROL Submit]**. De **[!UICONTROL Edit Form]** voor het profiel Metagegevens wordt weergegeven.

   ![chlimage_1-480](assets/chlimage_1-480.png)

1. Klik op een component en configureer de eigenschappen ervan in het dialoogvenster **[!UICONTROL Settings]** tab. Klik bijvoorbeeld op de knop **[!UICONTROL Description]** en de eigenschappen ervan bewerken.

   ![chlimage_1-481](assets/chlimage_1-481.png)

   Bewerk de volgende eigenschappen voor de **[!UICONTROL Description]** component:

   * **[!UICONTROL Field Label]**: De weergavenaam van de eigenschap metadata. Dit is alleen voor de gebruikersverwijzing.
   * **[!UICONTROL Map to Property]**: De waarde van deze eigenschap geeft het relatieve pad/de naam naar het knooppunt met middelen waar het wordt opgeslagen in de opslagplaats. De waarde moet altijd beginnen met `./` omdat het aangeeft dat het pad zich onder het knooppunt van het element bevindt.

   ![chlimage_1-482](assets/chlimage_1-482.png)

   De waarde die u opgeeft voor **[!UICONTROL Map to property]** wordt opgeslagen als een eigenschap onder het metagegevensknooppunt van het element. Als u bijvoorbeeld `/jcr:content/metadata/dc:desc` als de naam van **[!UICONTROL Map to property]**, [!DNL Experience Manager] De waarde wordt opgeslagen in de elementen `dc:desc` op het metagegevensknooppunt van het element.

   * **[!UICONTROL Default Value]**: Gebruik deze eigenschap om een standaardwaarde voor de metagegevenscomponent toe te voegen. Als u bijvoorbeeld &quot;Mijn beschrijving&quot; opgeeft, wordt deze waarde toegewezen aan de eigenschap `dc:desc` op het metagegevensknooppunt van het element.

   ![chlimage_1-483](assets/chlimage_1-483.png)

   >[!NOTE]
   >
   >Een standaardwaarde toevoegen aan een nieuwe eigenschap metadata (die nog niet bestaat op het tabblad . `/jcr:content/metadata` node) geeft de eigenschap en de waarde ervan niet weer op het element **[!UICONTROL Properties]** pagina standaard. Als u de nieuwe eigenschap wilt weergeven op de knop [!UICONTROL Properties] pagina van het element, wijzig de overeenkomstige schemavorm.

1. (Optioneel) Voeg meer componenten toe aan de **[!UICONTROL Edit Form]** van de **[!UICONTROL Build Form]** en hun eigenschappen configureren in het dialoogvenster **[!UICONTROL Settings]** tab. De volgende eigenschappen zijn beschikbaar op het tabblad **[!UICONTROL Build Form]**:

| Component | Eigenschappen |
|---|---|
| [!UICONTROL Section Header] | veldlabel, <br> Beschrijving |
| [!UICONTROL Single Line Text] | veldlabel, <br> Toewijzen aan eigenschap, <br> Standaardwaarde |
| [!UICONTROL Multi Value Text] | veldlabel, <br> Toewijzen aan eigenschap, <br> Standaardwaarde |
| [!UICONTROL Number] | veldlabel, <br> Toewijzen aan eigenschap, <br> Standaardwaarde |
| [!UICONTROL Date] | veldlabel, <br> Toewijzen aan eigenschap, <br> Standaardwaarde |
| [!UICONTROL Standard Tags] | veldlabel, <br> Toewijzen aan eigenschap, <br> Standaardwaarde, <br> Beschrijving |

![chlimage_1-484](assets/chlimage_1-484.png)

1. Klik op **[!UICONTROL Done]**. Het metagegevensprofiel wordt toegevoegd aan de lijst met profielen in het dialoogvenster **[!UICONTROL Metadata Profiles]** pagina.

   ![chlimage_1-485](assets/chlimage_1-485.png)

## Een metagegevensprofiel kopiëren {#copying-a-metadata-profile}

1. Van de **[!UICONTROL Metadata Profiles]** selecteert u een profiel om er een kopie van te maken.

   ![chlimage_1-486](assets/chlimage_1-486.png)

1. Klik op **[!UICONTROL Copy]** op de werkbalk.
1. In de **[!UICONTROL Copy Metadata Profile]** voert u een titel in voor de nieuwe kopie van het profiel.
1. Klik op **[!UICONTROL Copy]**. Een kopie van het profiel wordt weergegeven in de lijst met profielen in het dialoogvenster **[!UICONTROL Metadata Profiles]** pagina.

   ![chlimage_1-487](assets/chlimage_1-487.png)

## Een metagegevensprofiel verwijderen {#deleting-a-metadata-profile}

1. Van de **[!UICONTROL Metadata Profiles]** selecteert u een profiel dat u wilt verwijderen.

   ![chlimage_1-488](assets/chlimage_1-488.png)

1. Klikken **[!UICONTROL Delete Metadata Profiles]** in de werkbalk.
1. Klik in het dialoogvenster op **[!UICONTROL Delete]** om de verwijderbewerking te bevestigen. Het metagegevensprofiel wordt uit de lijst verwijderd.

## Een metagegevensprofiel toepassen op mappen {#applying-a-metadata-profile-to-folders}

Wanneer u een metagegevensprofiel toewijst aan een map, nemen eventuele submappen het profiel automatisch over van de bovenliggende map. Dit betekent dat u slechts één metagegevensprofiel kunt toewijzen aan een map. Denk daarom zorgvuldig na over de mapstructuur van de locatie waar u middelen uploadt, opslaat, gebruikt en archiveert.

Als u een ander metagegevensprofiel aan een map hebt toegewezen, overschrijft het nieuwe profiel het vorige profiel. De vorige bestaande mapelementen blijven ongewijzigd. Het nieuwe profiel wordt toegepast op de elementen die later aan de map worden toegevoegd.

Mappen waaraan een profiel is toegewezen, worden in de gebruikersinterface aangeduid met de naam van het profiel dat in de kaartnaam wordt weergegeven.

![chlimage_1-489](assets/chlimage_1-489.png)

U kunt metagegevensprofielen toepassen op specifieke mappen of op alle elementen.

### Metagegevensprofielen toepassen op specifieke mappen {#applying-metadata-profiles-to-specific-folders}

U kunt een metadataprofiel toepassen op een map vanuit het menu **[!UICONTROL Tools]**, of vanuit **[!UICONTROL Properties]** als u zich in een map bevindt. In deze sectie wordt beschreven hoe u op beide manieren metadataprofielen kunt toepassen op mappen.

Mappen waaraan al een profiel is toegewezen, worden aangegeven door de naam van het profiel direct onder de mapnaam weer te geven.

#### Metagegevensprofielen toepassen op mappen vanuit de gebruikersinterface Profielen {#applying-metadata-profiles-to-folders-from-profiles-user-interface}

1. Tik op de knop [!DNL Experience Manager] logo en navigeer naar **[!UICONTROL Tools > Assets > Metadata Profiles]**.
1. Selecteer het metagegevensprofiel dat u wilt toepassen op een of meerdere mappen.

   ![chlimage_1-490](assets/chlimage_1-490.png)

1. Tik op **[!UICONTROL Apply Metadata Profile to Folder(s)]** en selecteer de map of meerdere mappen die u wilt gebruiken om de nieuw geüploade assets te ontvangen en tik op **[!UICONTROL Done]**. Mappen waaraan al een profiel is toegewezen, worden aangegeven door de naam van het profiel direct onder de mapnaam weer te geven.

#### Metagegevensprofielen toepassen op mappen vanuit Eigenschappen {#applying-metadata-profiles-to-folders-from-properties}

1. Tik in de linkerspoorstaaf **[!UICONTROL Assets]** Navigeer vervolgens naar de map waarop u een metagegevensprofiel wilt toepassen.
1. Tik in de map op het vinkje om het te selecteren en tik vervolgens op  **[!UICONTROL Properties]**.

1. Selecteer het tabblad **[!UICONTROL Metadata Profiles]**, selecteer het profiel in het vervolgkeuzemenu en klik op **[!UICONTROL Save]**.

   ![chlimage_1-491](assets/chlimage_1-491.png)

   Mappen waaraan al een profiel is toegewezen, worden aangegeven door de naam van het profiel direct onder de mapnaam weer te geven.

### Een metagegevensprofiel algemeen toepassen {#applying-a-metadata-profile-globally}

Naast het toepassen van een profiel op een map, kunt u er ook een globaal toepassen, zodat alle inhoud die u uploadt naar [!DNL Experience Manager] op elementen in een willekeurige map is het geselecteerde profiel toegepast. Ga als volgt te werk als u een metagegevensprofiel globaal wilt toepassen:

1. Voer een van de volgende handelingen uit:

   * Navigeren naar `https://[aem_server]:[port]/mnt/overlay/dam/gui/content/assets/foldersharewizard.html/content/dam` en pas het juiste profiel toe en tik of klik op **[!UICONTROL Save]**.

      ![chlimage_1-492](assets/chlimage_1-492.png)

   * Navigeer naar CRXDE Lite naar het volgende knooppunt: `/content/dam/jcr:content`. De eigenschap toevoegen `metadataProfile:/etc/dam/metadata/dynamicmedia/<name_of_metadata_profile>` en tikken **[!UICONTROL Save All]**.

      ![chlimage_1-493](assets/chlimage_1-493.png)

## Een metagegevensprofiel uit mappen verwijderen {#removing-a-metadata-profile-from-folders}

Wanneer u een metagegevensprofiel uit een map verwijdert, nemen eventuele submappen automatisch de verwijdering van het profiel uit de bovenliggende map over. Alle verwerking van bestanden die in de mappen zijn opgetreden, blijft echter intact.

U kunt een metagegevensprofiel uit een map verwijderen vanuit de map **[!UICONTROL Tools]** of als u zich in de map bevindt, vanuit de **[!UICONTROL Properties]**. In deze sectie wordt beschreven hoe u metadataprofielen op beide manieren uit mappen kunt verwijderen.

### Metaprofielen uit mappen verwijderen via de gebruikersinterface Profielen {#removing-metadata-profiles-from-folders-via-profiles-user-interface}

Ga als volgt te werk als u een metagegevensprofiel uit mappen wilt verwijderen via de gebruikersinterface van Profielen:

1. Tik op de knop [!DNL Experience Manager] logo en navigeer naar **[!UICONTROL Tools > Assets > Metadata Profiles]**.
1. Selecteer het metagegevensprofiel dat u uit een of meerdere mappen wilt verwijderen.
1. Tikken **[!UICONTROL Remove Metadata Profile from Folder(s)]** en selecteer de map of meerdere mappen waaruit u een profiel wilt verwijderen. Tik vervolgens op **[!UICONTROL Done]**.

   U kunt bevestigen dat het metagegevensprofiel niet meer wordt toegepast op een map omdat de naam niet langer onder de mapnaam wordt weergegeven.

### Metagegevensprofielen uit mappen verwijderen met eigenschappen {#removing-metadata-profiles-from-folders-via-properties}

1. Tik op de knop [!DNL Experience Manager] logo en navigeer **[!UICONTROL Assets]** en vervolgens naar de map waaruit u een metagegevensprofiel wilt verwijderen.
1. Tik in de map op het vinkje om het te selecteren en tik vervolgens op **[!UICONTROL Properties]**.
1. Selecteer **[!UICONTROL Metadata Profiles]** tab, dan selecteren **[!UICONTROL None]** in het keuzemenu. Tik op **[!UICONTROL Save]**.

Mappen waaraan al een profiel is toegewezen, worden aangegeven door de naam van het profiel direct onder de mapnaam weer te geven.
