---
title: Oorspronkelijke inhoud van sandbox
seo-title: Initial Sandbox Content
description: Inhoud maken
seo-description: Create content
uuid: 9810fe47-8d1a-4238-9b9c-0cc47c63d97a
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: e8f28cd5-7950-4aab-bf62-3d4ed3d33cbd
exl-id: 171fd95d-51f6-468b-84ed-4a757dba868e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 1%

---

# Oorspronkelijke inhoud van sandbox {#initial-sandbox-content}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

In deze sectie maakt u de volgende pagina&#39;s die allemaal de [paginasjabloon](initial-app.md#createthepagetemplate):

* SCF Sandbox Site, die wordt omgeleid naar de Engelse versie van de hoofdpagina

   * SCF Sandbox - De hoofdpagina voor de Engelse versie van de site

      * SCF-afspelen - Onderliggend item van de hoofdpagina waarop moet worden afgespeeld

Hoewel deze zelfstudie niet in [taalkopieën](../../help/sites-administering/tc-prep.md), wordt het ontworpen zodat de wortelpagina opsporing van de aangewezen taal voor de gebruiker door de kopbal van de HTML kan uitvoeren, en aan de aangewezen belangrijkste pagina voor de taal opnieuw richt. De conventie is de landcode van twee letters te gebruiken voor de knooppuntnaam van de pagina, bijvoorbeeld &quot;en&quot; voor Engels, &quot;fr&quot; voor Frans, enzovoort.

## Eerste pagina&#39;s maken {#create-first-pages}

Nu is er een [paginasjabloon](initial-app.md#createthepagetemplate), kunnen wij de wortelpagina van de website in de /content folder vestigen.

1. De standaard-UI biedt momenteel blauwdrukken voor het maken van sites. Aangezien deze zelfstudie een eenvoudige plaats creeert, is klassieke UI nuttig.

   Als u wilt overschakelen naar de klassieke UI, selecteert u de globale navigatie en houdt u de muisaanwijzer boven de rechterzijde van het pictogram Projecten. Selecteer *Overschakelen naar klassieke gebruikersinterface* pictogram dat verschijnt:

   ![chlimage_1-36](assets/chlimage_1-36.png)

   De capaciteit om op klassieke UI over te schakelen moet zijn [ingeschakeld door een beheerder](../../help/sites-administering/enable-classic-ui.md).

1. Van de [klassieke gebruikersinterface Welkomstpagina](http://localhost:4502/welcome.html), selecteert u **[!UICONTROL Websites]**.

   ![chlimage_1-37](assets/chlimage_1-37.png)

   U kunt ook rechtstreeks toegang krijgen tot de klassieke UI voor websites door te bladeren naar [/site-beheerder.](http://localhost:4502/siteadmin)

1. Selecteer in het deelvenster Verkenner de optie **[!UICONTROL Websites]** en selecteer vervolgens op de werkbalk **[!UICONTROL New > New Page]**.

   In de **[!UICONTROL Create Page]** voert u het volgende in:

   * Titel: `SCF Sandbox Site`
   * Naam: `an-scf-sandbox`
   * Selecteer **[!UICONTROL An SCF Sandbox Play Template]**
   * Klik op **[!UICONTROL Create]**

   ![chlimage_1-38](assets/chlimage_1-38.png)

1. Selecteer in het deelvenster Verkenner de pagina die u zojuist hebt gemaakt. `/Websites/SCF Sandbox Site`en klik op **[!UICONTROL New > New Page]**:

   * Titel: `SCF Sandbox`
   * Naam: `en`
   * Selecteren **Een SCF-sandbox-afspeelsjabloon**
   * Klikken **Maken**

1. Selecteer in het deelvenster Verkenner de pagina die u zojuist hebt gemaakt. `/Websites/SCF Sandbox Site/SCF Sandbox`en klik op **[!UICONTROL New > New Page]**

   * Titel: `SCF Play`
   * Naam: `play`
   * Selecteer **[!UICONTROL An SCF Sandbox Play Template]**
   * Klik op **[!UICONTROL Create]**

1. Zo wordt de website nu weergegeven in de websiteconsole. U ziet dat onderliggende pagina&#39;s van het item dat is geselecteerd in het deelvenster Verkenner, worden weergegeven in het rechterdeelvenster waar ze kunnen worden beheerd.

   ![chlimage_1-39](assets/chlimage_1-39.png)

   Dit is de repository weergave van wat er is gemaakt met het gereedschap Website en de sjabloon:

   ![chlimage_1-40](assets/chlimage_1-40.png)

## Het ontwerppad toevoegen {#add-the-design-path}

Wanneer ` [/etc/designs/an-scf-sandbox](setup-website.md#setupthedesigntreeetcdesigns)` werd gecreeerd gebruikend de ontwerpsectie van de console van Hulpmiddelen, het bezit &quot;

* `cq:template="/libs/wcm/core/templates/designpage"`

is gedefinieerd, waardoor u optioneel kunt verwijzen naar ontwerpelementen in een script dat `currentDesign.getPath()`. Bijvoorbeeld

* &lt;% String favIcon = currentDesign.getPath() + &quot;/favicon.ico&quot;; %>


   * Naam: `cq:designPath`
   * Type: `String`
   * Waarde: `/etc/designs/an-scf-sandbox`

* Klik op groen `[+] Add`

De oplossing moet er als volgt uitzien:

![chlimage_1-41](assets/chlimage_1-41.png)

* Klik op **[!UICONTROL Save All]**

[ Problemen met opslaan? Opnieuw aanmelden! ]

>[!NOTE]
>
>Het gebruik van cq:designPath is optioneel en staat los van het [gebruik van clientlibs](develop-app.md#includeclientlibsintemplate), die hoofdzakelijk worden vereist aangezien de componenten SCF gebruiken [clientlibs](client-customize.md#clientlibs-for-scf) om hun JS en CSS te beheren.
