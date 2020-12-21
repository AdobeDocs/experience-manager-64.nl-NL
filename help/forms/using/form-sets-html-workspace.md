---
title: Werken met indelingen in de AEM Forms-werkruimte
seo-title: Werken met indelingen in de AEM Forms-werkruimte
description: Een formulierset is een verzameling HTML5-formulieren die zijn gegroepeerd en worden weergegeven als één set formulieren voor eindgebruikers. Leer hoe u in de AEM Forms-werkruimte met formsets kunt werken.
seo-description: Een formulierset is een verzameling HTML5-formulieren die zijn gegroepeerd en worden weergegeven als één set formulieren voor eindgebruikers. Leer hoe u in de AEM Forms-werkruimte met formsets kunt werken.
uuid: 77f81465-bd60-4aee-8507-585fe08adb78
contentOwner: vishgupt
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: c1793e2e-413c-4b6f-b96b-09e011f06263
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 1%

---


# Werken met formsets in de AEM Forms-werkruimte {#working-with-formsets-in-aem-forms-workspace}

Een formulierset is een verzameling HTML5-formulieren die zijn gegroepeerd en worden weergegeven als één set formulieren voor eindgebruikers. Wanneer eindgebruikers een formulierset beginnen te vullen, worden ze naadloos van het ene formulier naar het andere overgezet. De reeks formulieren kan vervolgens met één klik worden verzonden. Zie [Opmaak in AEM Forms](/help/forms/using/formset-in-aem-forms.md) voor meer informatie over formsets en het instellen ervan.

De AEM Forms-werkruimte ondersteunt formsets. Met formsets kunnen meerdere formulieren die betrekking hebben op een service of proces worden gegroepeerd om een bedrijfsproces te automatiseren en aan de eindgebruikers worden gepresenteerd. In dat geval kunnen de gebruikers de gehele set als één geheel invullen en hoeven afzonderlijke formulieren of processen niet te worden opgeslagen, verzonden en bijgehouden.

## Een formulierset koppelen aan het beginpunt in een AEM Forms-werkruimte-app {#attaching-a-formset-to-startpoint-in-an-aem-forms-workspace-app-br}

1. Maak de workflow voor het bedrijfsproces in Workbench. Zie [Workbench help](https://www.adobe.com/go/learn_aemforms_workbench_63) voor meer informatie.
1. Selecteer **Een CRX-element** gebruiken in presentatie en gegevens in de proceseigenschappen van het startpunt.

   ![1-1](assets/1-1.png)

1. Klik ![doorblader](assets/browse.png) (doorbladeren) naast de CRX activaweg. Het dialoogvenster Formulierelement selecteren wordt geopend.

   ![2](assets/2.png)

1. Klik op het tabblad **Formset**, selecteer de relevante formset in de lijst en klik vervolgens op **OK**.

1. Implementeer de toepassing nadat u andere relevante proceseigenschappen hebt bijgewerkt.

## Opmaak gebruiken in de AEM Forms-werkruimte {#using-formset-in-nbsp-aem-forms-workspace}

Zodra een formset aan een startpunt is gekoppeld, kan het startpunt worden aangeroepen, net als elk ander startpunt dat wordt aangeroepen, vanuit de AEM Forms-werkruimte.

De volgende bewerkingen worden ondersteund in de indeling in de AEM Forms-werkruimte:

* Opslaan als concept
* Vergrendelen
* Abandon
* Verzenden
* Bijlagen toevoegen
* Notities toevoegen
* Tussen formulieren in een formulierset navigeren met de knoppen Vorige of Volgende

![3-1](assets/3-1.png)

>[!NOTE]
>
>Voor prestatieverbetering tijdens het verplaatsen van vorige en volgende formulieren in een indeling, worden alle werkruimteknoppen (Vorige, Volgende, Opslaan, Verzenden en ... (Meer)) worden uitgeschakeld totdat het desbetreffende formulier volledig wordt weergegeven.

