---
title: Websitestructuur instellen
seo-title: Setup Website Structure
description: Mappen instellen
seo-description: Set up directories
uuid: a31edcd5-dab8-4a42-953b-1d076c2182b2
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: d18c0ece-4c4f-499c-ac94-a9aaa7f883c4
exl-id: 6d2226da-f691-4e8b-9494-a25e1c3d4b85
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 1%

---

# Websitestructuur instellen {#setup-website-structure}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

In de onderstaande instructies worden de mappen beschreven die op de volgende locaties moeten worden gemaakt om uw website in te stellen:

* `/apps/an-scf-sandbox`
Hier bevinden aangepaste toepassingen en sjablonen zich

* `/etc/designs/an-scf-sandbox`
Hier bevinden zich downloadbare ontwerpelementen

* `/content/an-scf-sandbox`
Dit is waar de downloadbare webpagina&#39;s zich bevinden

De code in deze zelfstudie vertrouwt erop dat de naam van de hoofdmap gelijk is voor de toepassing, het ontwerp en de inhoud. Als u een andere naam voor uw website kiest, vervangt u deze altijd `an-scf-sandbox` met de naam die u hebt gekozen.

>[!NOTE]
>
>Namen:
>
>* De namen die in CRXDE worden gezien zijn knooppuntnamen die de weg aan adresseerbare inhoud vormen
>* Node names may contain spaces, but when used in an URI, the space must be encoded either as &#39;%20&#39; or &#39;+&#39;
>* Node-namen kunnen afbreekstreepjes en onderstrepingstekens bevatten, maar deze moeten worden gecodeerd als er in een Java-bestand naar wordt verwezen als een pakketnaam. Zowel koppeltekens als onderstrepingstekens worden overgeslagen met een onderstrepingsteken gevolgd door de Unicode-waarde:
   >
   >   * afbreekstreepje wordt &#39;_002d&#39;
   >   * onderstrepingsteken wordt &#39;_005f&#39;


## De toepassingsmap (/apps) instellen {#setup-the-application-directory-apps}

De map /apps in de opslagplaats bevat de code met implementaties van het gedrag en de rendering van de pagina&#39;s die vanuit de map /content worden aangeboden.

De map /apps is beveiligd en niet toegankelijk voor het publiek, net als de mappen /content en /etc/designs.

1. Maken `/apps/an-scf-sandbox` map.

   Gebruiken **[!UICONTROL CRXDE Lite]** in het deelvenster Verkenner

   1. Selecteer `/apps` map
   1. Klikken met rechtermuisknop **[!UICONTROL Create]**... of de **[!UICONTROL Create...]** menu
   1. Selecteer **[!UICONTROL Create Folder...]** .
   1. In de **[!UICONTROL Create Folder]** dialoogvenster, enter `an-scf-sandbox`
   1. Klik op **[!UICONTROL OK]**

1. Maken **[!UICONTROL components]** submap.

   1. Selecteer `/apps/an-scf-sandbox` map
   1. Klik op **[!UICONTROL Create > Create Folder]**
   1. In de **[!UICONTROL Create Folder]** dialoogvenster, enter **[!UICONTROL components]**
   1. Klik op **[!UICONTROL OK]**

1. Maken **[!UICONTROL templates]** submap.

   1. Selecteer `/apps/an-scf-sandbox` map
   1. Klik op **[!UICONTROL Create > Create Folder]**
   1. In de **[!UICONTROL Create Folder]** dialoogvenster, enter **[!UICONTROL templates]**
   1. Klik op **[!UICONTROL OK]**
   1. Opnieuw selecteren `/apps/an-scf-sandbox`
   1. Selecteer **[!UICONTROL Save All]**

   Net als bij elk bewerkingsproces, kunt u dit vaak opslaan. Als u problemen ondervindt met het invoeren van gegevens, kan dit zijn omdat er een time-out is opgetreden bij uw aanmelding of omdat u vorige bewerkingen moet opslaan.

1. De structuur in het deelvenster Verkenner van CRXDE Lite moet er nu ongeveer als volgt uitzien:

   ![chlimage_1-44](assets/chlimage_1-44.png)

## De ontwerpmap instellen (/etc/designs) {#setup-the-design-directory-etc-designs}

De map /etc/designs bevat de afbeeldingen, scripts en opmaakmodellen die samen met de pagina-inhoud moeten worden gedownload.

1. Blader naar het gereedschap Designer in de klassieke gebruikersinterface als u het gereedschap Designer wilt gebruiken [https://&lt;server>:&lt;port>/miscadmin](http://localhost:4502/miscadmin).

   Opmerking: Als u CRXDE Lite gebruikt om een knooppunt van het type te maken `cq:Page`De instellingen voor toegangsbeheer en replicatie worden niet ingesteld op de standaardinstellingen voor een pagina.

1. Selecteer in het deelvenster Verkenner de optie **[!UICONTROL Designs]** en klik vervolgens op **[!UICONTROL New > New Page]**.

   Enter:

   * Titel: **Een SCF-sandbox**
   * Naam: **an-scf-sandbox**
   * Selecteren **Ontwerppaginasjabloon**

   Klik op **[!UICONTROL Create]**

   ![chlimage_1-45](assets/chlimage_1-45.png)

1. Vernieuw het verkennervenster als de map &quot;An SCF Sandbox&quot; niet wordt weergegeven.

1. Ga terug naar CRXDE Lite (http:// localhost:4502/crx/de) en vouw /etc/designs uit om het knooppunt met de naam &quot;an-scf-sandbox&quot; weer te geven.

   In de rechterbenedenruit van CRXDE, kunt u het lusje van Eigenschappen, het lusje van het Controle van de Toegang en het lusje van de Replicatie bekijken om te zien wat gebruikend het Malplaatje van de Pagina van het Ontwerp werd bepaald.

   ![chlimage_1-46](assets/chlimage_1-46.png)

## De inhoudsdirectory (/inhoud) instellen {#setup-the-content-directory-content}

De map /content in de opslagmap is waar de website-inhoud zich bevindt. De paden onder /content bestaan uit de paden van de URL voor browserverzoeken.

*Na* de [paginasjabloon](initial-app.md#createthepagetemplate) wordt gemaakt als onderdeel van de oorspronkelijke toepassing, kan de eerste pagina-inhoud worden gemaakt op basis van de sjabloon.... [**ê**](initial-app.md)
