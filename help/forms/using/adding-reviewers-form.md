---
title: Verzendrevisoren koppelen aan een formulier
seo-title: Verzendrevisoren koppelen aan een formulier
description: Leer hoe u revisoren voor verzending kunt koppelen aan een formulier in AEM Forms. Gekoppelde revisoren reviseren een formulier dat via de portal Formulieren is verzonden.
seo-description: Leer hoe u revisoren voor verzending kunt koppelen aan een formulier in AEM Forms. Gekoppelde revisoren reviseren een formulier dat via de portal Formulieren is verzonden.
uuid: 66834c2b-ae70-4a6e-ae8e-07d0e38de06b
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: 7c39383b-b430-40a1-9bcb-f5aaccb616ad
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 0%

---


# Verzendrevisoren koppelen aan een formulier {#associating-submission-reviewers-with-a-form}

Wanneer u een formulier maakt, kunt u gebruikers die de verzendingen van het formulier bekijken, via de portal Formulieren opgeven en feedback geven. Uw organisatie kan feedback verzamelen en de ingediende formulieren opnieuw bewerken.

In AEM Forms kunt u een revisorgroep aan een formulier koppelen. Gebruikers die aan een revisiegroep van een formulier zijn toegevoegd, zien de verzendingen van dit formulier en geven feedback.

Revisieersgroepen die aan een formulier zijn toegewezen, kunnen alleen de verzendingen van het opgegeven formulier bekijken.

## Vereiste {#prerequisite}

### De eigenschap Groepen van verzendrevisoren inschakelen voor adaptieve formulieren met de Schema-editor {#enabling-submission-reviewer-groups-property-for-adaptive-forms-using-metadata-schema-editor} voor metagegevens

Als u een revisorgroep aan een formulier wilt koppelen, bewerkt u het metagegevensschema van adaptieve formulieren. Standaard kunt u geen revisorgroep toevoegen aan een verzonden formulier.

Het schema voor metagegevens bewerken:

1. In de auteurwijze, onder Experience Manager, klik **[!UICONTROL Tools > Assets > Metadata Schemas]**.
1. Navigeer op de pagina Schema Forms naar **[!UICONTROL Forms > Forms Authored in AEM]**.

   De URL van de pagina is:

   ```
   https://<hostname>:<port>/mnt/overlay/dam/gui/content/metadataschemaeditor/
    schemalist.html/dam/content/schemaeditors/forms/forms/
    aem-authored
   ```

1. Selecteer **[!UICONTROL Adaptive Form]** en klik **[!UICONTROL Edit]**.
1. Klik op **[!UICONTROL Advanced]** op de pagina Formulier bewerken.
1. Op het Geavanceerde lusje, belemmering-en-daling de **[!UICONTROL Single Line Text]** component beschikbaar onder de Vorm van de Bouwstijl.
1. Selecteer de toegevoegde tekstcomponent om zijn montages te zien.

   Voer onder Instellingen `./jcr:content/metadata/form-submission-reviewer-group` in het veld Toewijzen aan eigenschap in.

   Het groepsveld Verzendrevisor in de eigenschappen Geavanceerd van het adaptieve formulier wordt ingeschakeld met de naam die u opgeeft onder Veld Label.

## Verzendrevisoren koppelen aan een formulier {#associating-submission-reviewers-with-a-form-1}

Als u revisoren wilt koppelen aan een adaptief formulier, maakt u een revisorgroep en voegt u gebruikers toe. Voeg de gemaakte revisorgroep toe onder het veld revisor voor formulierverzending in de geavanceerde eigenschappen van het formulier.\
Met gebruikersgroepen kunt u verschillende sets revisoren aan verschillende adaptieve formulieren koppelen. Met deze functie voorkomt u dat een niet-geautoriseerde gebruiker een verzendcontrole uitvoert.

Voordat u de volgende stappen uitvoert, raadpleegt u [Vereiste](/help/forms/using/adding-reviewers-form.md#prerequisite).

Navigeer naar **[!UICONTROL Tools > Operations > Security > Groups]** om een groep te maken en er leden aan toe te voegen.\
Zie [Gebruikersbeheer en Services](/help/sites-administering/security.md) voor meer informatie.\
Zorg ervoor dat u de groep toevoegt u als lid van de uit-van-de-doos gebruikersgroep creeert: **formulieren-indiening-revisoren**. Deze gebruikersgroep wordt geleverd bij AEM Forms en zorgt ervoor dat gebruikers worden toegevoegd als revisoren voor verzending.

Gebruikersgroepen koppelen aan een adaptief formulier:

1. Navigeer in de ontwerpmodus naar **[!UICONTROL Forms > Forms & Documents]**.
1. Selecteer een adaptief formulier met de optie **[!UICONTROL Select]** en klik op **[!UICONTROL View Properties]**.
1. Klik in het venster Eigenschappen van het formulier op **[!UICONTROL Edit]** en klik vervolgens op **[!UICONTROL ADVANCED]**.
1. Voer de groep in het groepsveld voor de revisorgroep voor verzending in en klik op **[!UICONTROL Done]**.

   Het veld Subrevisorgroep wordt weergegeven met de naam die u hebt opgegeven in het bewerkte metagegevensschema van adaptieve formulieren.

>[!NOTE]
>
>Repliceer gebruikers en formulieren om ervoor te zorgen dat de gebruikers en formulieren beschikbaar zijn in de externe implementatie van AEM Forms.
>
>Zorg ervoor dat alle gebruikers worden gerepliceerd als reviserende leden van de gebruikersgroepen in de externe implementatie.

