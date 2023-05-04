---
title: Werken met indelingen in de AEM Forms-werkruimte
seo-title: Working with Formsets in AEM Forms workspace
description: Een formulierset is een verzameling van HTML5-formulieren die zijn gegroepeerd en gepresenteerd als één set formulieren voor eindgebruikers. Leer hoe u in de AEM Forms-werkruimte met formsets kunt werken.
seo-description: A formset is a collection of HTML5 forms grouped and presented as a single set of forms to end users. Learn how you can work with formsets in AEM Forms workspace.
uuid: 77f81465-bd60-4aee-8507-585fe08adb78
contentOwner: vishgupt
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: c1793e2e-413c-4b6f-b96b-09e011f06263
exl-id: 4e39f6dd-b7a3-4c6c-be1f-66b9a5743352
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 0%

---

# Werken met indelingen in de AEM Forms-werkruimte {#working-with-formsets-in-aem-forms-workspace}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Een formulierset is een verzameling van HTML5-formulieren die zijn gegroepeerd en gepresenteerd als één set formulieren voor eindgebruikers. Wanneer eindgebruikers een formulierset beginnen te vullen, worden ze naadloos van het ene formulier naar het andere overgezet. De reeks formulieren kan vervolgens met één klik worden verzonden. Voor meer informatie over formsets en hoe u deze instelt, raadpleegt u [Opmaak in AEM Forms](/help/forms/using/formset-in-aem-forms.md).

De AEM Forms-werkruimte ondersteunt formsets. Met formsets kunnen meerdere formulieren die betrekking hebben op een service of proces worden gegroepeerd om een bedrijfsproces te automatiseren en aan de eindgebruikers worden gepresenteerd. In dat geval kunnen de gebruikers de gehele set als één geheel invullen en hoeven afzonderlijke formulieren of processen niet te worden opgeslagen, verzonden en bijgehouden.

## Een formulierset koppelen aan het beginpunt in een AEM Forms-werkruimte-app {#attaching-a-formset-to-startpoint-in-an-aem-forms-workspace-app-br}

1. Maak de workflow voor het bedrijfsproces in Workbench. Zie voor meer informatie [Workbench Help](https://www.adobe.com/go/learn_aemforms_workbench_63).
1. Van de proceseigenschappen van het startpunt, selecteer **Een CRX-element gebruiken** in presentatie en gegevens.

   ![1-1](assets/1-1.png)

1. Klikken ![doorbladeren](assets/browse.png) (Bladeren) naast het CRX-middelenpad. Het dialoogvenster Formulierelement selecteren wordt geopend.

   ![2](assets/2.png)

1. Klik op de knop **Inzet** selecteert u de desbetreffende indeling in de lijst en klikt u vervolgens op **OK**.

1. Implementeer de toepassing nadat u andere relevante proceseigenschappen hebt bijgewerkt.

## Indeling gebruiken in de AEM Forms-werkruimte {#using-formset-in-nbsp-aem-forms-workspace}

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
