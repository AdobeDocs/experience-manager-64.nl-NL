---
title: Oorspronkelijke inhoud van sandbox
seo-title: Oorspronkelijke inhoud van sandbox
description: Inhoud maken
seo-description: Inhoud maken
uuid: 9810fe47-8d1a-4238-9b9c-0cc47c63d97a
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: e8f28cd5-7950-4aab-bf62-3d4ed3d33cbd
exl-id: 171fd95d-51f6-468b-84ed-4a757dba868e
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 3%

---

# Eerste sandbox-inhoud {#initial-sandbox-content}

In deze sectie maakt u de volgende pagina&#39;s die allemaal de [paginasjabloon](initial-app.md#createthepagetemplate) gebruiken:

* SCF Sandbox Site, die wordt omgeleid naar de Engelse versie van de hoofdpagina

   * SCF Sandbox - De hoofdpagina voor de Engelse versie van de site

      * SCF-afspelen - Onderliggend item van de hoofdpagina waarop moet worden afgespeeld

Hoewel deze zelfstudie niet in [taalkopieën](../../help/sites-administering/tc-prep.md) overkomt, is deze zo ontworpen dat de hoofdpagina detectie van de voorkeurstaal voor de gebruiker kan implementeren via de HTML-koptekst en doorsturen naar de juiste hoofdpagina voor de taal. De conventie is de landcode van twee letters te gebruiken voor de knooppuntnaam van de pagina, bijvoorbeeld &quot;en&quot; voor Engels, &quot;fr&quot; voor Frans, enzovoort.

## Eerste pagina&#39;s maken {#create-first-pages}

Nu er een [paginasjabloon](initial-app.md#createthepagetemplate) is, kunnen wij de wortelpagina van de website in de /content folder vestigen.

1. De standaard-UI biedt momenteel blauwdrukken voor het maken van sites. Aangezien deze zelfstudie een eenvoudige plaats creeert, is klassieke UI nuttig.

   Als u wilt overschakelen naar de klassieke UI, selecteert u de globale navigatie en houdt u de muisaanwijzer boven de rechterzijde van het pictogram Projecten. Selecteer het pictogram *Overschakelen naar klassieke gebruikersinterface* dat verschijnt:

   ![chlimage_1-36](assets/chlimage_1-36.png)

   De capaciteit om op klassieke UI over te schakelen moet [toegelaten door een beheerder ](../../help/sites-administering/enable-classic-ui.md) zijn.

1. Van [klassieke UI Welkome pagina](http://localhost:4502/welcome.html), uitgezochte **[!UICONTROL Websites]**.

   ![chlimage_1-37](assets/chlimage_1-37.png)

   U kunt ook rechtstreeks toegang krijgen tot de klassieke UI voor websites door naar [/site-admin.](http://localhost:4502/siteadmin) te bladeren

1. Selecteer **[!UICONTROL Websites]** in het verkennervenster en selecteer **[!UICONTROL New > New Page]** op de werkbalk.

   Voer in het dialoogvenster **[!UICONTROL Create Page]** het volgende in:

   * Titel: `SCF Sandbox Site`
   * Naam: `an-scf-sandbox`
   * Selecteer **[!UICONTROL An SCF Sandbox Play Template]**
   * Klik op **[!UICONTROL Create]**

   ![chlimage_1-38](assets/chlimage_1-38.png)

1. Selecteer in het verkenner-venster de pagina die u zojuist hebt gemaakt, `/Websites/SCF Sandbox Site` en klik op **[!UICONTROL New > New Page]**:

   * Titel: `SCF Sandbox`
   * Naam: `en`
   * Selecteer **Een SCF Sandbox Play Template**
   * Klik **Maken**

1. Selecteer in het verkenner-venster de pagina die u zojuist hebt gemaakt, `/Websites/SCF Sandbox Site/SCF Sandbox` en klik op **[!UICONTROL New > New Page]**

   * Titel: `SCF Play`
   * Naam: `play`
   * Selecteer **[!UICONTROL An SCF Sandbox Play Template]**
   * Klik op **[!UICONTROL Create]**

1. Zo wordt de website nu weergegeven in de websiteconsole. U ziet dat onderliggende pagina&#39;s van het item dat is geselecteerd in het deelvenster Verkenner, worden weergegeven in het rechterdeelvenster waar ze kunnen worden beheerd.

   ![chlimage_1-39](assets/chlimage_1-39.png)

   Dit is de repository weergave van wat er is gemaakt met het gereedschap Website en de sjabloon:

   ![chlimage_1-40](assets/chlimage_1-40.png)

## Het ontwerppad toevoegen {#add-the-design-path}

Wanneer ` [/etc/designs/an-scf-sandbox](setup-website.md#setupthedesigntreeetcdesigns)` is gemaakt met de ontwerpsectie van de console Tools, wordt de eigenschap &quot;

* `cq:template="/libs/wcm/core/templates/designpage"`

is gedefinieerd, hetgeen de optionele mogelijkheid biedt om te verwijzen naar ontwerpelementen in een script met `currentDesign.getPath()`. Bijvoorbeeld

* &lt;>


   * Naam: `cq:designPath`
   * Type: `String`
   * Waarde: `/etc/designs/an-scf-sandbox`

* Klik op het groene `[+] Add`

De oplossing moet er als volgt uitzien:

![chlimage_1-41](assets/chlimage_1-41.png)

* Klik op **[!UICONTROL Save All]**

[ Problemen met opslaan? Opnieuw aanmelden! ]

>[!NOTE]
>
>Het gebruik van cq:designPath is optioneel en houdt geen verband met het [gebruik van clientlibs](develop-app.md#includeclientlibsintemplate), die in wezen vereist zijn omdat de SCF-componenten [clientlibs](client-customize.md#clientlibs-for-scf) gebruiken om hun JS en CSS te beheren.
