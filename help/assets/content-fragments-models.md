---
title: Modellen van contentfragmenten
seo-title: Modellen van contentfragmenten
description: Inhoudsfragmentmodellen worden gebruikt om inhoudsfragmenten met gestructureerde inhoud te maken.
seo-description: Inhoudsfragmentmodellen worden gebruikt om inhoudsfragmenten met gestructureerde inhoud te maken.
uuid: 59176a32-1255-4a46-ad00-344bde843ea6
content-type: reference
topic-tags: content-fragments
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 45e67357-4524-4d25-b5f1-21182b8e803c
translation-type: tm+mt
source-git-commit: 8b83be510a67fadaa666f2ba96fbb3fc82b9cb3d

---


# Modellen van contentfragmenten {#content-fragment-models}

>[!CAUTION]
>
>Voor sommige functies voor inhoudsfragmenten is de toepassing van [AEM 6.4 Service Pack 2 (6.4.2.0) of hoger](../release-notes/sp-release-notes.md)vereist.

Met Content Fragment Models wordt de structuur van de inhoud voor [inhoudsfragmenten](content-fragments.md)gedefinieerd.

## Modellen van inhoudsfragmenten inschakelen {#enable-content-fragment-models}

>[!CAUTION]
>
>Als u Modellen van **[!UICONTROL inhoudsfragmenten]** niet inschakelt, is de optie **[!UICONTROL Maken]** niet beschikbaar voor het maken van nieuwe modellen.

Als u modellen van inhoudsfragmenten wilt inschakelen, moet u:

* Het gebruik van modellen van inhoudsfragmenten inschakelen in configuratiebeheer
* De configuratie toepassen op de map Middelen

### Modellen van inhoudsfragmenten inschakelen in Configuratiebeheer {#enable-content-fragment-models-in-configuration-manager}

Om een nieuw Model [van het Fragment van de Inhoud te](#creating-a-content-fragment-model) creëren **moet** u hen eerst toelaten gebruikend de Manager van de Configuratie:

1. Navigeer aan **[!UICONTROL Hulpmiddelen]**, **[!UICONTROL Algemeen]**, dan open Browser **[!UICONTROL van de]** Configuratie.
1. Selecteer de locatie die geschikt is voor uw website.
1. Gebruik **[!UICONTROL Maken]** om het dialoogvenster te openen waarin u:

   1. Geef een **[!UICONTROL titel]** op.
   1. Selecteer Modellen van **[!UICONTROL inhoudsfragmenten]** om het gebruik ervan in te schakelen.
   ![cfm-6420-09](assets/cfm-6420-09.png)

1. Selecteer **[!UICONTROL Maken]** om de definitie op te slaan.

### De configuratie toepassen op de middelenmap {#apply-the-configuration-to-your-assets-folder}

Wanneer de configuratie **[!UICONTROL globaal]** is ingeschakeld voor modellen van inhoudsfragmenten, kunnen alle modellen die gebruikers maken, worden gebruikt in elke map Middelen.

Als u andere configuraties (d.w.z. exclusief globaal) wilt gebruiken met een vergelijkbare map Middelen, moet u de verbinding definiëren. Dit wordt gedaan gebruikend **[!UICONTROL Configuratie]** op het lusje van de Diensten **[!UICONTROL van de]** Wolk van de Eigenschappen **[!UICONTROL van de]** Omslag van de aangewezen omslag.

## Een inhoudsfragmentmodel maken {#creating-a-content-fragment-model}

1. Navigeer naar **[!UICONTROL Gereedschappen]**, **[!UICONTROL Elementen]** en open vervolgens Modellen **[!UICONTROL inhoudsfragmenten]**.
1. Navigeer naar de map die geschikt is voor uw [configuratie](#enable-content-fragment-models).
1. Gebruik **[!UICONTROL Maken]** om de wizard te openen.

   >[!CAUTION]
   >
   >Als het [gebruik van inhoudsfragmentmodellen niet is ingeschakeld](#enable-content-fragment-models), is de optie **Maken** niet beschikbaar.

1. Geef de **[!UICONTROL modeltitel]** op. U kunt desgewenst ook een **[!UICONTROL beschrijving]** toevoegen.

   ![cfm-6420-10](assets/cfm-6420-10.png)

1. Gebruik **[!UICONTROL Maken]** om het lege model op te slaan. Een bericht zal op het succes van de actie wijzen, kunt u **[!UICONTROL Open]** selecteren om het model onmiddellijk uit te geven, of **[!UICONTROL Gedaan]** om aan de console terug te keren.

## Het model van het inhoudsfragment definiëren {#defining-your-content-fragment-model}

Het inhoudsfragmentmodel definieert in feite de structuur van de resulterende inhoudsfragmenten. Gebruikend de modelredacteur kunt u, de vereiste gebieden toevoegen en vormen:

>[!CAUTION]
>
>Het bewerken van een bestaand inhoudsfragmentmodel kan invloed hebben op afhankelijke fragmenten.

1. Navigeer naar **[!UICONTROL Gereedschappen]**, **[!UICONTROL Elementen]** en open vervolgens Modellen **[!UICONTROL inhoudsfragmenten]**.

1. Navigeer naar de map met het fragmentmodel van de inhoud.
1. Open het vereiste model voor **[!UICONTROL Bewerken]**; gebruik de snelle actie of selecteer het model en de actie op de werkbalk.

   Zodra open de modelredacteur toont:

   * links: velden al gedefinieerd
   * rechts: Er zijn **[!UICONTROL gegevenstypen]** beschikbaar voor het maken van velden (en **[!UICONTROL eigenschappen]** voor gebruik als er velden zijn gemaakt)
   >[!NOTE]
   >
   >Als een veld **vereist** is, wordt het **label** in het linkerdeelvenster gemarkeerd met een asterisk (**&amp;ast;**).

   ![cfm-6420-11](assets/cfm-6420-12.png)

1. **Een veld toevoegen**

   * Sleep een vereist gegevenstype naar de vereiste locatie voor een veld:
   ![cfm-6420-11](assets/cfm-6420-11.png)

   * Nadat een veld aan het model is toegevoegd, worden in het rechterdeelvenster de **eigenschappen** weergegeven die voor dat specifieke gegevenstype kunnen worden gedefinieerd. Hier kunt u definiëren wat voor dat veld is vereist. Bijvoorbeeld:
   ![cfm-6420-13](assets/cfm-6420-13.png)

1. **Een veld verwijderen**

   Selecteer het vereiste veld en klik op het pictogram met de prullenbak of tik erop. U wordt gevraagd de actie te bevestigen.

   ![cf-32](assets/cf-32.png)

1. Nadat u alle vereiste velden hebt toegevoegd en de eigenschappen hebt gedefinieerd, gebruikt u **[!UICONTROL Opslaan]** om de definitie te behouden. Bijvoorbeeld:

   ![cfm-6420-14](assets/cfm-6420-14.png)

## Een inhoudsfragmentmodel verwijderen {#deleting-a-content-fragment-model}

>[!CAUTION]
>
>Het verwijderen van een inhoudsfragmentmodel kan invloed hebben op afhankelijke fragmenten.

Een inhoudsfragmentmodel verwijderen:

1. Navigeer naar **[!UICONTROL Gereedschappen]**, **[!UICONTROL Elementen]** en open vervolgens Modellen **[!UICONTROL inhoudsfragmenten]**.

1. Navigeer naar de map met het fragmentmodel van de inhoud.
1. Selecteer het model, gevolgd door **[!UICONTROL Verwijderen]** op de werkbalk.

   >[!NOTE]
   >
   >Als naar het model wordt verwezen, wordt een waarschuwing gegeven. Voer de juiste actie uit.

## Een inhoudsfragmentmodel publiceren {#publishing-a-content-fragment-model}

Inhoudsfragmentmodellen moeten worden gepubliceerd wanneer/voordat afhankelijke inhoudsfragmenten worden gepubliceerd.

Een fragmentmodel voor inhoud publiceren:

1. Navigeer naar **[!UICONTROL Gereedschappen]**, **[!UICONTROL Elementen]** en open vervolgens Modellen **[!UICONTROL inhoudsfragmenten]**.

1. Navigeer naar de map met het fragmentmodel van de inhoud.
1. Selecteer het model, gevolgd door **[!UICONTROL Publiceren]** op de werkbalk.

   >[!NOTE]
   >
   >Als u een inhoudsfragment publiceert waarvoor het model nog niet is gepubliceerd, wordt dit in een selectielijst aangegeven en wordt het model met het fragment gepubliceerd.

