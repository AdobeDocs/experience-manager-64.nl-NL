---
title: Algemene stappen voor aanpassing van de AEM Forms-werkruimte
seo-title: Generic steps for AEM Forms workspace customization
description: Aan de slag met het aanpassen van de gebruikersinterface van de AEM Forms-werkruimte.
seo-description: How to get started customizing AEM Forms workspace user interface.
uuid: 555b5039-cd68-4090-8a8f-30b654474f55
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 54326a05-3fb0-4111-a6ec-230b6473052e
exl-id: 2c0dab68-d77e-46fb-832d-90edea510750
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 3%

---

# Algemene stappen voor aanpassing van de AEM Forms-werkruimte {#generic-steps-for-aem-forms-workspace-customization}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De algemene stappen voor het uitvoeren van aanpassingen zijn:

1. Aanmelden bij CRXDE Lite via toegang `https://[server]:[port]/lc/crx/de/index.jsp`.
1. Een map maken met de naam `ws`om `/apps`, als deze niet bestaat. Klik op **[!UICONTROL Save All]**.
1. Bladeren naar `/apps/ws`en navigeer naar de **[!UICONTROL Access Control]** tab.
1. In de **[!UICONTROL Access Control]** lijst, klikt u op **[!UICONTROL +]** om een nieuwe vermelding toe te voegen. Klikken **[!UICONTROL +]** opnieuw.
1. Zoek en selecteer de **[!UICONTROL PERM_WORKSPACE_USER]** Opdrachtgever.

   ![Selecteer PERM_WORKSPACE_USER principal als onderdeel van de algemene stappen om de HTML Workspace aan te passen](assets/perm_workspace_user.png)

1. Geef `jcr:read` aan de Opdrachtgever.
1. Klik op **[!UICONTROL Save All]**.
1. Kopieer de `GET.jsp` en `html.jsp`bestanden van de `/libs/ws`aan de `/apps/ws` map.
1. Kopieer de `/libs/ws/locales` in de `/apps/ws` map. Klik op **[!UICONTROL Save All]**.
1. De verwijzingen en relatieve paden in het dialoogvenster `GET.jsp` bestand, zoals hieronder weergegeven, en klik op **[!UICONTROL Save all]**.

   ```
   <meta http-equiv="refresh" content="0;URL='/lc/apps/ws/index.html'" />
   ```

1. Ga als volgt te werk voor CSS-aanpassingen:

   1. Ga naar de `/apps/ws` en maak een nieuwe map met de naam `css`.
   1. In de `css`map, maakt u een nieuw bestand met de naam `newStyle.css`.
   1. Openen `/apps/ws/html`.jsp en wijzigen van

   ```css
   <link lang="en" rel="stylesheet" type="text/css" href="css/style.css" />
   <link lang="en" rel="stylesheet" type="text/css" href="css/jquery-ui.css"/>
   ```

   tot

   ```css
   <link lang="en" rel="stylesheet" type="text/css" href="../../libs/ws/css/style.css" />
   <link lang="en" rel="stylesheet" type="text/css" href="css/newStyle.css" />
   <link lang="en" rel="stylesheet" type="text/css" href="../../libs/ws/css/jquery-ui.css"/>
   ```

   >[!NOTE]
   >
   >Plaats de vermelding van het door de gebruiker gedefinieerde CSS-bestand na de vermelding newStyle.css, zoals hierboven weergegeven.

1. Wijzig in het bestand /apps/ws/html.jsp

   ```css
   <script data-main="js/main" src="js/libs/require/require.js"></script>
   ```

   tot

   ```css
   <script data-main="js/main" src="../../libs/ws/js/libs/require/require.js"></script>
   ```

1. Ga als volgt te werk:

   1. Een map maken met de naam `js`om `/apps/ws`. Klik op **[!UICONTROL Save All]**.
   1. Een map maken met de naam `libs`om `/apps/ws/js`. Klik op **[!UICONTROL Save All]**.
   1. Een map maken met de naam `jqueryui`om `/apps/ws/js/libs`. Klik op **[!UICONTROL Save All]**.
   1. Kopiëren `/libs/ws/js/libs/jqueryui/jquery.ui.datepicker-ja.js` tot `/apps/ws/js/libs/jqueryui`. Klik op **[!UICONTROL Save All]**.

1. Doe het volgende voor HTML aanpassingen:

   1. Onder `/apps/ws/js`, maakt u een map met de naam `runtime`. Klik op **[!UICONTROL Save All]**.
   1. Onder `/apps/ws/js/runtime`, maakt u een map met de naam `templates`. Klik op **[!UICONTROL Save All]**.
   1. Kopiëren `/libs/ws/js/main.js` tot `/apps/ws/js/main.js`.
   1. /libs/ws/js/registry.js kopiëren naar `/apps/ws/js/registry.js`.

1. Klikken **[!UICONTROL Save All]**, cache verwijderen en de AEM Forms-werkruimte vernieuwen.

   Toegang krijgen tot de URL `https://[server]:[port]/lc/ws` en meld u aan met de gegevens van de beheerder/het wachtwoord. De browser wordt omgeleid naar `https://[server]:[port]/lc/apps/ws/index.html`.
