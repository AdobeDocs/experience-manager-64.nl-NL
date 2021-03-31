---
title: Ervaring met homepage in AEM Assets
description: Pas de AEM Assets Home-pagina aan voor een uitgebreide ervaring met welkomstschermen, inclusief een momentopname van recente activiteiten rond middelen.
contentOwner: AG
feature: Gereedschappen voor ontwikkelaars, beheer van bedrijfsmiddelen
role: Beheerder, Business Practiter
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 1%

---


# AEM Assets Home Page Experience {#aem-assets-home-page-experience}

Pas de AEM Assets Home-pagina aan voor een uitgebreide ervaring met welkomstschermen, inclusief een momentopname van recente activiteiten rond middelen.

De startpagina van Adobe Experience Manager (AEM) Assets biedt een uitgebreide en persoonlijke welkomstscherm met een momentopname van recente activiteiten, zoals elementen die onlangs zijn weergegeven of geüpload.

De elementenstartpagina is standaard uitgeschakeld. Voer de volgende stappen uit om het in te schakelen:

1. Om tot AEM Manager van de Configuratie toegang te hebben, klik **[!UICONTROL Tools > Operation > Web Console]**.
1. Open de **Day CQ DAM-gebeurtenisrecorder**-service.
1. Selecteer **[!UICONTROL Enable this service]** om activiteitenopname toe te laten.

   ![chlimage_1-250](assets/chlimage_1-250.png)

1. Selecteer in de lijst **Gebeurtenistypen** de gebeurtenissen die moeten worden opgenomen en sla de wijzigingen op.

   >[!CAUTION]
   >
   >Als u de weergaveopties voor het element, de bekeken projecten en de weergegeven verzamelingen inschakelt, wordt het aantal opgenomen gebeurtenissen aanzienlijk verhoogd.

1. Open de **[!UICONTROL DAM Asset Home Page Feature Flag]** dienst van de Manager `https://[AEM_server]:[port]/system/console/configMgr` van de Configuratie.
1. Selecteer de optie **[!UICONTROL isEnabled.name]** om de functie Introductiepagina van Elementen in te schakelen. Sla de wijzigingen op.

   ![chlimage_1-251](assets/chlimage_1-251.png)

1. Open het dialoogvenster **[!UICONTROL User Preferences]** en selecteer **[!UICONTROL Enable Assets Home Page]**. Sla de wijzigingen op.

   ![user_preferences](assets/user_preferences.png)

Nadat u de elementenstartpagina hebt ingeschakeld, navigeert u vanuit de navigatiepagina naar de gebruikersinterface Middelen.

![home_page](assets/home_page.png)

Tik/klik op **[!UICONTROL Click here to configure your experience link]** om uw gebruikersnaam, achtergrondafbeelding en profielafbeelding toe te voegen.

De pagina Middelen Home bevat de volgende secties:

* Welkomstsectie
* Widget-sectie

**Welkomstsectie**

Als uw profiel bestaat, wordt in de welkomstsectie een welkomstbericht weergegeven dat aan u is gericht. Bovendien worden uw profielfoto en een welkomstafbeelding weergegeven (indien al geconfigureerd).

Als uw profiel onvolledig is, geeft de welkomstsectie een algemeen welkomstbericht en een tijdelijke aanduiding voor uw profielafbeelding weer.

**Widget-sectie**

Deze sectie verschijnt onder de welkomstsectie en toont buiten-de-dooswidgets onder de volgende secties:

* Activiteit
* Recent
* Discover

**Activiteit**: Onder deze sectie geeft de widget  **Mijn** activiteit recente activiteiten weer die door de aangemelde gebruiker zijn uitgevoerd met elementen (waaronder elementen zonder vertoningen), zoals het uploaden van middelen, downloads, het maken van elementen, bewerkingen, opmerkingen, annotaties en shares.

**Recent**: De  **onlangs** Viewwidget onder deze sectie toont onlangs betreden entiteiten door de het programma geopende gebruiker, met inbegrip van omslagen, inzamelingen, en projecten.

**Detecteren**: In de  **** widget Newwidget onder deze sectie worden de elementen en vertoningen weergegeven die onlangs naar de instantie AEM Assets zijn geüpload.

Om het zuiveren van de gegevens van de gebruikersactiviteit toe te laten, laat **DAM de Dienst van de Woorden van de Gebeurtenis** van de Manager van de Configuratie toe. Nadat u deze dienst toelaat, worden de activiteiten van de het programma geopende gebruiker die een gespecificeerd aantal overschrijden geschrapt door het systeem.

Het welkomstscherm biedt eenvoudige navigatiehulpmiddelen, zoals pictogrammen op de werkbalk, voor toegang tot mappen, verzamelingen en catalogi.

>[!NOTE]
>
>Als u de services Day CQ DAM-gebeurtenisrecorder en DAM-gebeurtenis leegmaken inschakelt, worden schrijfbewerkingen naar JCR en zoekindexering verhoogd, waardoor de belasting op de AEM server aanzienlijk toeneemt. De extra belasting op de AEM kan van invloed zijn op de prestaties.

>[!CAUTION]
>
>Het vastleggen, filteren en leegmaken van gebruikersactiviteiten die vereist zijn voor Asset Home Page legt de prestaties extra zwaar. Daarom moeten beheerders de startpagina effectief configureren voor doelgebruikers.
>
>Adobe raadt beheerders en gebruikers die bulkbewerkingen uitvoeren aan de functie Startpagina van bedrijfsmiddelen niet te gebruiken om te voorkomen dat gebruikers meer gaan werken. Daarnaast kunnen beheerders opnameactiviteiten voor specifieke gebruikers uitsluiten door CQ DAM-gebeurtenisrecorder **van** Dag te configureren in Configuratiebeheer.
>
>Als u deze functie gebruikt, raadt Adobe u aan de opschoonfrequentie te laten bepalen op basis van het laden van de server.
