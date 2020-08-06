---
title: Formuliergegevensmodel maken
seo-title: Formuliergegevensmodel maken
description: Leer hoe te om modellen van vormgegevens met of zonder gevormde gegevensbronnen tot stand te brengen.
seo-description: Leer hoe te om modellen van vormgegevens met of zonder gevormde gegevensbronnen tot stand te brengen.
uuid: bed1a82e-a799-4034-9068-1478b95e6c70
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: integration
discoiquuid: 3a3a6ede-52af-4c37-8a51-c2ea721a28dc
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 0%

---


# Formuliergegevensmodel maken {#create-form-data-model}

Leer hoe te om modellen van vormgegevens met of zonder gevormde gegevensbronnen tot stand te brengen.

![](do-not-localize/data-integeration.png)

AEM Forms-gegevensintegratie biedt een intuïtieve gebruikersinterface voor het maken van en werken met formuliergegevensmodellen. Een formuliergegevensmodel is gebaseerd op gegevensbronnen voor gegevensuitwisseling; u kunt echter wel een formuliergegevensmodel maken met of zonder gegevensbron. Er zijn twee benaderingen om van gegevensmodel afhankelijk van tot stand te brengen of u gegevensbronnen hebt gevormd:

* **Vooraf geconfigureerde gegevensbronnen** gebruiken: Als u gegevensbronnen hebt geconfigureerd zoals wordt beschreven in Gegevensbronnen [](/help/forms/using/configure-data-sources.md)configureren, kunt u deze selecteren tijdens het maken van een formuliergegevensmodel. Hiermee worden alle gegevensmodelobjecten, eigenschappen en services van de geselecteerde gegevensbronnen beschikbaar gemaakt voor gebruik in het formuliergegevensmodel.

* **Zonder gegevensbronnen**: Als u geen gegevensbronnen hebt geconfigureerd voor uw formuliergegevensmodel, kunt u het nog steeds maken zonder gegevensbronnen. U kunt het gegevensmodel van het formulier gebruiken om adaptieve formulieren en interactieve communicatie te maken en deze te testen met behulp van voorbeeldgegevens. Wanneer gegevensbronnen beschikbaar zijn, kunt u het formuliergegevensmodel binden met gegevensbronnen, die automatisch worden weergegeven in de bijbehorende adaptieve formulieren en interactieve communicatie.

>[!NOTE]
>
>U moet lid zijn van zowel **fdm-auteur** als **formulieren-gebruiker** groepen om formuliergegevensmodel te kunnen maken en ermee te kunnen werken. Neem contact op met de AEM beheerder om lid te worden van de groepen.

## Formuliergegevensmodel maken {#data-sources}

Zorg ervoor dat u de gegevensbronnen hebt geconfigureerd die u wilt gebruiken in het formuliergegevensmodel, zoals beschreven in Gegevensbronnen [](/help/forms/using/configure-data-sources.md)configureren. Ga als volgt te werk om een formuliergegevensmodel te maken op basis van geconfigureerde gegevensbronnen:

1. Navigeer in AEM auteurinstantie naar **[!UICONTROL Forms > Data Integrations]**.
1. Tik op **[!UICONTROL Create > Form Data Model]**.
1. In het dialoogvenster Formuliergegevensmodel maken:

   * Geef een naam op voor het gegevensmodel van het formulier.
   * (**Optioneel**) Geef een titel, beschrijving en codes op voor het formuliergegevensmodel.
   * (**Optioneel en alleen van toepassing als gegevensbronnen zijn geconfigureerd**) Tik op het verdeelstreepje naast het **[!UICONTROL Data Source Configuration]** veld en selecteer het configuratieknooppunt waar de cloudservices voor de gegevensbronnen die u wilt gebruiken zich bevinden. Het beperkt de lijst van gegevensbronnen beschikbaar voor selectie op de volgende pagina tot degenen beschikbaar in de geselecteerde configuratieknooppunt. Alle JDBC-database- en AEM gegevensbronnen van gebruikersprofielen worden standaard weergegeven. Als u geen configuratieknooppunt selecteert, worden de gegevensbronnen van alle configuratieknooppunten vermeld.

   Tik op **[!UICONTROL Next]**.

1. (**Alleen van toepassing als gegevensbronnen zijn geconfigureerd**) In het **[!UICONTROL Select Datasource]** scherm worden de beschikbare gegevensbronnen weergegeven, indien aanwezig. Selecteer gegevensbronnen die u wilt gebruiken in het formuliergegevensmodel.
1. Tik **[!UICONTROL Create]** en tik in het bevestigingsvenster op **[!UICONTROL Open]** om de formuliergegevensmodeleditor te openen.

Laten we de verschillende componenten van de gebruikersinterface van de formuliergegevensmodel bekijken.

![Een formuliergegevensmodel met drie gegevensbronnen: een RESTful-service, AEM gebruikersprofiel en een RDBMS](assets/fdm-ui.png)

**A. Gegevensbronnen** Maakt een lijst van gegevensbronnen in een model van vormgegevens. Breid een gegevensbron uit om zijn voorwerpen en de diensten van het gegevensmodel te bekijken.

**B. Vernieuw de Definities** van de Gegevensbron Vetst om het even welke veranderingen in gegevensbrondefinities van gevormde gegevensbronnen en werkt hen op het Bronlusje van Gegevens van de modelredacteur van vormgegevens bij.

**C. Model** inhoudsgebied waar toegevoegde gegevensmodelvoorwerpen verschijnen.

**D. Het gebied van de Inhoud van de diensten** waar de toegevoegde gegevensbronverrichtingen of de diensten verschijnen.

**E. Gereedschappen op de werkbalk** voor het werken met het formuliergegevensmodel. Op de werkbalk ziet u meer opties, afhankelijk van het geselecteerde object in het formuliergegevensmodel.

**F. Hiermee voegt u geselecteerde** gegevensmodelobjecten en -services toe aan het formuliergegevensmodel.

Zie [Werken met formuliergegevensmodel](/help/forms/using/work-with-form-data-model.md)voor meer informatie over de formuliergegevensmodeleditor en hoe u ermee kunt werken om het formuliergegevensmodel te bewerken en te configureren.

## Gegevensbronnen bijwerken {#update}

Ga als volgt te werk om gegevensbronnen toe te voegen aan of bij te werken naar een bestaand formuliergegevensmodel.

1. Ga naar **[!UICONTROL Forms > Data Integrations]**, selecteer het model van vormgegevens waarin u gegevensbronnen toevoegen of wilt bijwerken, en tik **[!UICONTROL Properties]**.
1. Ga in de eigenschappen van het formuliergegevensmodel naar het **[!UICONTROL Update Source]** tabblad.

   Op het tabblad Bron bijwerken:

   * Tik op het bladerpictogram in het **[!UICONTROL Context-Aware Configuration]** veld en selecteer een configuratieknooppunt waar de cloudconfiguratie voor de gegevensbron die u wilt toevoegen zich bevindt. Als u geen knooppunt selecteert, worden cloudconfiguraties die alleen in het `global` knooppunt aanwezig zijn, weergegeven wanneer u tikt **[!UICONTROL Add Sources]**.
   * Als u een nieuwe gegevensbron wilt toevoegen, tikt u op de gegevensbronnen die u aan het formuliergegevensmodel wilt toevoegen **[!UICONTROL Add Sources]** en selecteert u deze. Alle gegevensbronnen binnen gevormd `global` en de geselecteerde configuratieknooppunt, als om het even welk, worden getoond.
   * Als u een bestaande gegevensbron wilt vervangen door een andere gegevensbron van hetzelfde type, tikt u op het **[!UICONTROL Edit]** pictogram voor de gegevensbron en selecteert u een gegevensbron in de lijst met beschikbare gegevensbronnen.
   * Tik op het **[!UICONTROL Delete]** pictogram voor de gegevensbron om een bestaande gegevensbron te verwijderen. Het pictogram Verwijderen is uitgeschakeld als een gegevensmodelobject in de gegevensbron wordt toegevoegd aan het formuliergegevensmodel.

   ![fdm-eigenschappen](assets/fdm-properties.png)

1. Tik **[!UICONTROL Save & Close]** om de updates op te slaan.

>[!NOTE]
>
>Nadat u nieuwe gegevensbronnen hebt toegevoegd of bestaande gegevensbronnen hebt bijgewerkt in een formuliergegevensmodel, zorgt u ervoor dat u de bindingsverwijzingen naar behoren bijwerkt in adaptieve formulieren en interactieve communicatie die gebruikmaken van het bijgewerkte formuliergegevensmodel.

## Volgende stappen {#next-steps}

U hebt nu een formuliergegevensmodel waaraan gegevensbronnen zijn toegevoegd. Vervolgens kunt u het gegevensmodel van het formulier bewerken om gegevensmodelobjecten en -services toe te voegen en te configureren, koppelingen tussen gegevensmodelobjecten toe te voegen, eigenschappen te bewerken, aangepaste gegevensmodelobjecten en -eigenschappen toe te voegen, voorbeeldgegevens te genereren, enzovoort.

Zie [Werken met formuliergegevensmodel](/help/forms/using/work-with-form-data-model.md)voor meer informatie.
