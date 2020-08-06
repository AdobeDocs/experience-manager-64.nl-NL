---
title: Editor
seo-title: Editor
description: Leer hoe u terug kunt schakelen naar de klassieke UI-editor.
seo-description: Leer hoe u terug kunt schakelen naar de klassieke UI-editor.
uuid: 78ba4db0-affa-4081-bf29-a3306720c968
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: 5fca5401-502d-483b-bfc1-ef53e2c041b7
translation-type: tm+mt
source-git-commit: 9fa15a44cf83a50538cea3fb37bcccf405f66738
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 1%

---


# Editor{#editor}

Door gebrek, is de capaciteit om op klassieke UI van de redacteur over te schakelen onbruikbaar gemaakt.

![chlimage_1-9](assets/chlimage_1-9.png)

Voer de volgende stappen uit om de optie **Openen in klassieke gebruikersinterface** in het menu **Pagina-informatie** weer in te schakelen.

1. Gebruik CRXDE Lite om het volgende knooppunt te zoeken:

   `/libs/wcm/core/content/editor/jcr:content/content/items/content/header/items/headerbar/items/pageinfopopover/items/list/items/classicui`

   Bijvoorbeeld

   `http://localhost:4502/crx/de/index.jsp#/libs/wcm/core/content/editor/jcr%3Acontent/content/items/content/header/items/headerbar/items/pageinfopopover/items/list/items/classicui](http://localhost:4502/crx/de/index.jsp#/libs/wcm/core/content/editor/jcr%3Acontent/content/items/content/header/items/headerbar/items/pageinfopopover/items/list/items/classicui`

1. Maak een bedekking met de optie **Overlay knooppunt** . bijvoorbeeld:

   * **Pad**: `/apps/wcm/core/content/editor/jcr:content/content/items/content/header/items/headerbar/items/pageinfopopover/items/list/items/classicui`
   * **Locatie** bedekking: `/apps/`
   * **Identieke knooppunttypen**: actief (schakel het selectievakje in)

1. Voeg de volgende teksteigenschap met meerdere waarden toe aan het bovenliggende knooppunt:

   `sling:hideProperties = ["granite:hidden"]`

1. De optie **Openen in klassieke gebruikersinterface** is weer beschikbaar in het menu **Pagina-informatie** wanneer u pagina&#39;s bewerkt.

   ![chlimage_1-10](assets/chlimage_1-10.png)

