---
title: Kanaal en webkanaal afdrukken
seo-title: Print channel and web channel
description: Afdrukkanaalsjablonen importeren en webkanaalsjablonen maken en inschakelen
seo-description: Importing print channel templates and creating and enabling web channel templates
uuid: 19e6ffab-00d2-4084-9ee7-9643b11eb6c6
topic-tags: interactive-communications
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 71bba66a-3cac-445b-9941-aa4bcf9b2160
feature: Interactive Communication
exl-id: cb7a8e96-4440-47ec-b506-275d5acc774e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 0%

---

# Kanaal en webkanaal afdrukken {#print-channel-and-web-channel}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Afdrukkanaalsjablonen importeren en webkanaalsjablonen maken en inschakelen

De interactieve Mededelingen kunnen door twee kanalen worden geleverd: afdrukken en web. Het afdrukkanaal wordt gebruikt om PDF en papieren communicatie te maken, zoals een gedrukte brief als een herinnering voor verzekeringspremies, terwijl het webkanaal wordt gebruikt om online ervaringen te bieden, zoals een creditcardverklaring op een website.

Auteurs van interactieve communicatie kunnen elementen zoals documentfragmenten en afbeeldingen hergebruiken om zowel afdruk- als webversies van interactieve communicatie te maken.

Een van de voorwaarden voor [Interactieve communicatie maken](/help/forms/using/create-interactive-communication.md) moet de sjablonen voor afdrukken en/of webkanaal beschikbaar hebben op de server. Hoewel sjabloonauteurs de webkanaalsjabloon op AEM zelf maken, wordt de XDP-afdruksjabloon gemaakt in Adobe Forms Designer en geüpload naar de server.

## Kanaal afdrukken {#printchannel}

Het kanaal van de druk van een Interactieve Communicatie gebruikt XFA vormmalplaatje, XDP. Een XDP is ontworpen in Adobe Forms Designer. Voor meer informatie over het maken van afdrukkanaalsjablonen raadpleegt u [Indelingsontwerp](/help/forms/using/layout-design-details.md). Als u een sjabloon voor een afdrukkanaal wilt gebruiken in uw interactieve communicatie, moet u de sjabloon uploaden naar de AEM Forms-server.

### Interactieve communicatiekanaalsjabloon uploaden {#upload-interactive-communication-print-channel-template}

Als u de sjabloon wilt uploaden, moet u lid zijn van de gebruikersgroep voor formulieren. Gebruik de volgende stappen om de sjabloon voor het afdrukkanaal (XDP) te uploaden naar AEM Forms:

1. Selecteer **[!UICONTROL Forms]** > **[!UICONTROL Forms & Documents]**.

1. Tik op **[!UICONTROL Create]** > **[!UICONTROL File Upload]**.

   Navigeer en selecteer de juiste sjabloon voor het afdrukkanaal (XDP) en tik op **[!UICONTROL Open]**.

## Webkanaal {#web-channel}

Sjabloonauteurs en -beheerders kunnen websjablonen maken, bewerken en inschakelen. Als u andere gebruikers wilt toestaan websjablonen te maken, moet u ze rechten geven. Zie voor meer informatie [Beheer van gebruikers-, groep- en toegangsrechten](/help/sites-administering/user-group-ac-admin.md).

### Webkanaalsjabloon ontwerpen {#authoring-web-channel-template}

Als u een webkanaalsjabloon wilt maken, moet u eerst een sjabloonmap maken. Nadat u een websjabloon in een sjabloonmap hebt gemaakt, moet u de sjabloon zo instellen dat gebruikers van formulieren een interactief communicatiekanaal kunnen maken op basis van de sjabloon.

Voer de volgende stappen uit om een webkanaalsjabloon te maken:

1. Maak een sjabloonmap om uw interactieve communicatiesweb-sjablonen te behouden, als u dat nog niet hebt. Voor meer informatie, zie de Omslagen van het Malplaatje in [Paginasjablonen - Bewerkbaar](/help/sites-developing/page-templates-editable.md).

   1. Tikken **[!UICONTROL Tools]** ![gereedschappen-1](assets/tools-1.png) > **[!UICONTROL Configuration Browser]**.
      * Zie de [Documentatie van de configuratievenster](/help/sites-administering/configurations.md) voor meer informatie .
   1. Tik op de pagina Configuration Browser (Configuratiebrowser) op **[!UICONTROL Create]**.
   1. Geef in het dialoogvenster Configuratie maken een titel voor de map op. Controleer **[!UICONTROL Editable Templates]** en tikken **[!UICONTROL Create]**.

      De omslag wordt gecreeerd en vermeld in Browser van de Configuratie pagina.

1. Navigeer naar de juiste sjabloonmap en maak een websjabloon.

   1. Navigeer naar de juiste sjabloonmap door **[!UICONTROL Tools]** > **[!UICONTROL Templates > Folder]**.
   1. Tik op **[!UICONTROL Create]**.
   1. Selecteren **[!UICONTROL Interactive Communication - Web Channel]** en tikken **[!UICONTROL Next]**.
   1. Voer een titel en beschrijving voor de sjabloon in en tik op **[!UICONTROL Create]**.

      De sjabloon wordt gemaakt en er verschijnt een dialoogvenster.

   1. Tikken **[!UICONTROL Open]** om het malplaatje te openen u in de redacteur van het Malplaatje hebt gecreeerd.

      De Sjablooneditor wordt weergegeven.

      ![webchannelsjabloon](assets/webchanneltemplate.png)

      Bij het maken of bewerken van een sjabloon zijn er verschillende aspecten die een sjabloonauteur kan definiëren. Het maken of bewerken van een sjabloon lijkt op het ontwerpen van pagina&#39;s. Zie Sjablonen bewerken - Sjabloonauteurs in voor meer informatie [Paginasjablonen maken](/help/sites-authoring/templates.md).

1. Schakel de sjabloon in als u het gebruik van deze sjabloon voor het maken van interactieve communicatie wilt toestaan.

   1. Tikken **[!UICONTROL Tools]** ![gereedschappen-1](assets/tools-1.png) > **[!UICONTROL Templates]**.
   1. Navigeer naar de gewenste sjabloon, selecteer deze en tik op **[!UICONTROL Enable]** en in het waarschuwingsbericht tikt u op **[!UICONTROL Enable]**.

      Het malplaatje wordt toegelaten en zijn status wordt getoond zoals Toegelaten. Nu kunt u doorgaan met het maken van een interactieve communicatie waarin u de zojuist gemaakte sjabloon voor webkanalen kunt gebruiken.

### Kanaal afdrukken als master voor webkanaal {#print-channel-as-master-for-web-channel}

Tijdens het ontwerpen van een interactieve communicatie kunnen auteurs deze optie selecteren om het webkanaal synchroon met het afdrukkanaal te maken. Als u het afdrukkanaal gebruikt als master voor het webkanaal, weet u zeker dat de inhoud, overerving en gegevensbinding van het webkanaal worden afgeleid van het afdrukkanaal en dat de wijzigingen die in het afdrukkanaal zijn aangebracht, worden weerspiegeld in het webkanaal. De interactieve auteurs van communicatie mogen echter de overerving voor specifieke componenten in het webkanaal onderbreken, indien nodig.

![printweb_2-2](assets/printweb_2-2.png)
