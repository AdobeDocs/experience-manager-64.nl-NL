---
title: '"[!DNL Experience Manager Assets] Introductiepagina"'
description: De pagina Middelen aanpassen voor een uitgebreide ervaring met welkomstschermen, waaronder een momentopname van recente activiteiten rond elementen.
contentOwner: AG
feature: Developer Tools,Asset Management
role: Admin,User
exl-id: f47c6da7-aa21-4f49-9c66-2a8091e19561
source-git-commit: d9cfb5376210234b3b05877509c273c52d9cecf3
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 1%

---

# [!DNL Adobe Experience Manager Assets] Introductiepagina {#aem-assets-home-page-experience}

Personaliseer [!DNL Experience Manager Assets] De homepage voor een rijke het ontvangen het schermervaring, met inbegrip van een momentopname van recente activiteiten rond activa.

De [!DNL Adobe Experience Manager Assets] De startpagina biedt een uitgebreide en persoonlijke welkomstschermervaring, die een momentopname van recente activiteiten bevat, zoals elementen die onlangs zijn weergegeven of geüpload.

De elementenstartpagina is standaard uitgeschakeld. Voer de volgende stappen uit om het in te schakelen:

1. Toegang tot [!DNL Experience Manager] Configuratiebeheer, klik op **[!UICONTROL Tools > Operation > Web Console]**.
1. Open de **DAM DAM-gebeurtenisrecorder dag** service.
1. Selecteer **[!UICONTROL Enable this service]** om het opnemen van activiteiten in te schakelen.

   ![chlimage_1-250](assets/chlimage_1-250.png)

1. Van de **Gebeurtenistypen** selecteert u de gebeurtenissen die moeten worden opgenomen en slaat u de wijzigingen op.

   >[!CAUTION]
   >
   >Als u de weergaveopties voor het element, de bekeken projecten en de weergegeven verzamelingen inschakelt, wordt het aantal opgenomen gebeurtenissen aanzienlijk verhoogd.

1. Open de **[!UICONTROL DAM Asset Home Page Feature Flag]** service van Configuration Manager `https://[AEM_server]:[port]/system/console/configMgr`.
1. Selecteer **[!UICONTROL isEnabled.name]** om de functie Homepage van middelen in te schakelen. Sla de wijzigingen op.

   ![chlimage_1-251](assets/chlimage_1-251.png)

1. Open de **[!UICONTROL User Preferences]** en selecteert u **[!UICONTROL Enable Assets Home Page]**. Sla de wijzigingen op.

   ![user_preferences](assets/user_preferences.png)

Nadat u de elementenstartpagina hebt ingeschakeld, navigeert u vanuit de navigatiepagina naar de gebruikersinterface Middelen.

![home_page](assets/home_page.png)

Tik/klik op de knop **[!UICONTROL Click here to configure your experience link]** om uw gebruikersnaam, achtergrondafbeelding en profielafbeelding toe te voegen.

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

**Activiteit**: In deze sectie wordt **Mijn activiteiten** De widget geeft recente activiteiten weer die door de aangemelde gebruiker zijn uitgevoerd met elementen (waaronder elementen zonder vertoningen), zoals het uploaden van middelen, downloads, het maken van elementen, bewerkingen, opmerkingen, annotaties en shares.

**Recent**: De **Onlangs bekeken** widget onder deze sectie toont onlangs betreden entiteiten door de het programma geopende gebruiker, met inbegrip van omslagen, inzamelingen, en projecten.

**Discover**: De **Nieuw** widget in deze sectie geeft de elementen en vertoningen weer die onlangs zijn geüpload naar de [!DNL Assets] -instantie.

Schakel de optie **DAM-service voor het opschonen van gebeurtenissen** van de Manager van de Configuratie. Nadat u deze dienst toelaat, worden de activiteiten van de het programma geopende gebruiker die een gespecificeerd aantal overschrijden geschrapt door het systeem.

Het welkomstscherm biedt eenvoudige navigatiehulpmiddelen, zoals pictogrammen op de werkbalk, voor toegang tot mappen, verzamelingen en catalogi.

>[!NOTE]
>
>Als u de services Day CQ DAM Event Recorder en DAM Event Purge inschakelt, worden meer schrijfbewerkingen naar JCR uitgevoerd en wordt de zoekindex aanzienlijk verhoogd, waardoor de belasting op de [!DNL Experience Manager] server. De extra belasting op de [!DNL Experience Manager] kan de prestaties van de server beïnvloeden.

>[!CAUTION]
>
>Het vastleggen, filteren en leegmaken van gebruikersactiviteiten die vereist zijn voor Asset Home Page legt de prestaties extra zwaar. Daarom moeten beheerders de startpagina effectief configureren voor doelgebruikers.
>
>Adobe raadt beheerders en gebruikers die bulkbewerkingen uitvoeren aan de functie Startpagina van bedrijfsmiddelen niet te gebruiken om te voorkomen dat gebruikers meer gaan werken. Daarnaast kunnen beheerders opnameactiviteiten voor specifieke gebruikers uitsluiten door **DAM DAM-gebeurtenisrecorder dag** van de Manager van de Configuratie.
>
>Als u deze functie gebruikt, raadt Adobe u aan de opschoonfrequentie te laten bepalen op basis van het laden van de server.
