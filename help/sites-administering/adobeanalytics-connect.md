---
title: Verbinding maken met Adobe Analytics en frameworks maken
seo-title: Verbinding maken met Adobe Analytics en frameworks maken
description: Leer hoe u AEM verbindt met SiteCatalyst en frameworks maakt.
seo-description: Leer hoe u AEM verbindt met SiteCatalyst en frameworks maakt.
uuid: 04325409-435c-4394-9ab7-c9022e19e085
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: 88dbfd34-1f8d-47a2-893d-20faf1a80f95
translation-type: tm+mt
source-git-commit: fb4e6aef84d733c578e0f2ee7407016715e77cf5
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 0%

---


# Verbinding maken met Adobe Analytics en frameworks maken{#connecting-to-adobe-analytics-and-creating-frameworks}

Als u webgegevens wilt bijhouden van uw AEM in Adobe Analytics, maakt u een Adobe Analytics Cloud Services-configuratie en een Adobe Analytics-framework:

* **Adobe Analytics-configuratie:** De informatie over je Adobe Analytics-account. Met de Adobe Analytics-configuratie kunnen AEM verbinding maken met Adobe Analytics. Maak een Adobe Analytics-configuratie voor elk account dat u gebruikt.
* **Adobe Analytics Framework:** Een set toewijzingen tussen eigenschappen van Adobe Analytics-rapportsuite en CQ-variabelen. Gebruik een framework om te configureren hoe uw websitegegevens uw Adobe Analytics-rapporten vullen. Frameworks zijn gekoppeld aan een Adobe Analytics-configuratie. U kunt veelvoudige kaders voor elke configuratie tot stand brengen.

Wanneer u een webpagina aan een framework koppelt, wordt de pagina en de onderliggende pagina door het framework bijgehouden. Paginaweergaven kunnen vervolgens worden opgehaald uit Adobe Analytics en worden weergegeven in de Sites-console.

## Vereisten {#prerequisites}

### Adobe Analytics-account {#adobe-analytics-account}

Als u AEM gegevens in Adobe Analytics wilt bijhouden, moet u een geldige Adobe Marketing Cloud Adobe Analytics-account hebben.

De Adobe Analytics-account moet:

* beschikken over **beheerdersrechten**
* Ben toegewezen aan de de gebruikersgroep van de Toegang **van de Dienst van het** Web.

>[!CAUTION]
>
>Het bieden van **beheerdersrechten** (in Adobe Analytics) is niet genoeg om een gebruiker in staat te stellen verbinding te maken van AEM naar Adobe Analytics. De rekening moet de voorrechten van de Toegang **van de** Dienst van het Web ook hebben.

![chlimage_1-316](assets/chlimage_1-316.png)

Voordat u verdergaat, moet u ervoor zorgen dat u zich op een van de volgende manieren kunt aanmelden bij Adobe Analytics:

* [Aanmelden bij Adobe Experience Cloud](https://login.experiencecloud.adobe.com/exc-content/login.html)

* [Aanmelden bij Adobe Analytics](https://sc.omniture.com/login/)

### AEM configureren om uw Adobe Analytics-datacenters te gebruiken {#configuring-aem-to-use-your-adobe-analytics-data-centers}

Adobe Analytics- [datacenters](https://developer.omniture.com/en_US/content_page/concepts-terminology/c-how-is-data-stored) verzamelen, verwerken en opslaan gegevens die bij uw Adobe Analytics-rapportenpakket horen. U moet AEM configureren om het datacenter te gebruiken dat als host fungeert voor uw Adobe Analytics-rapportsuite. In de volgende tabel staan de beschikbare datacenters en de bijbehorende URL.

| Datacenter | URL |
|---|---|
| San Jose | https://api.omniture.com/admin/1.4/rest/ |
| Dallas | https://api2.omniture.com/admin/1.4/rest/ |
| Londen | https://api3.omniture.com/admin/1.4/rest/ |
| Singapore | https://api4.omniture.com/admin/1.4/rest/ |
| Oregon | https://api5.omniture.com/admin/1.4/rest/ |

AEM gebruikt standaard het datacenter van San Jose (https://api.omniture.com/admin/1.4/rest/).

Gebruik de Console van het [Web om de bundel](/help/sites-deploying/configuring-osgi.md#osgi-configuration-with-the-web-console) OSGi **Adobe te vormen AEM de Cliënt** van HTTP van Analytics vande Analyse. Voeg de URL **van het** datacenter toe voor het datacenter dat fungeert als host voor een rapportenpakket waarvoor uw AEM gegevens verzamelen.

![aa-07](assets/aa-07.png)

1. Open de webconsole in uw webbrowser. ([http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr))
1. Ga uw geloofsbrieven in om tot de console toegang te hebben.

   >[!NOTE]
   >
   >Neem contact op met de sitebeheerder om te weten te komen of u toegang hebt tot deze console.

1. Selecteer het punt van de Configuratie genoemd **Adobe AEM de Cliënt** van HTTP van Analytics.
1. Als u de URL voor een datacenter wilt toevoegen, drukt u op + naast de lijst URL&#39;s van **datacenter** en typt u de URL in het vak.

1. Als u een URL uit de lijst wilt verwijderen, klikt u op de knop - naast de URL.
1. Klik op Opslaan.

## De verbinding met Adobe Analytics configureren {#configuring-the-connection-to-adobe-analytics}

>[!CAUTION]
>
>Vanwege beveiligingswijzigingen in de Adobe Analytics API is het niet langer mogelijk om de versie van de Activity Map te gebruiken die in AEM is opgenomen.
>
>De [ActivityMap-plug-in van Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/activity-map/getting-started/get-started-users/activitymap-install.html) moet nu worden gebruikt.

## Configureren voor de Activity Map {#configuring-for-the-activity-map}

>[!CAUTION]
>
>Vanwege beveiligingswijzigingen in de Adobe Analytics API is het niet langer mogelijk om de versie van de Activity Map te gebruiken die in AEM is opgenomen.
>
>De [ActivityMap-plug-in van Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/activity-map/getting-started/get-started-users/activitymap-install.html) moet nu worden gebruikt.

## Een Adobe Analytics-framework maken {#creating-a-adobe-analytics-framework}

Voor identiteitskaart van de Reeks van het Rapport (RSID) die u gebruikt, kunt u controleren welke serverinstanties (auteur, publiceert, of allebei) gegevens aan de Reeks van het Rapport bijdragen:

* **Alles**: De informatie van zowel de auteur als de publicatieinstantie vult de Reeks van het Rapport.
* **Auteur**: Alleen informatie van de auteur wordt in de rapportsuite ingevuld.
* **Publiceren**: Alleen informatie uit de publicatieversie wordt in de rapportsuite ingevuld.

>[!NOTE]
>
>Het selecteren van het type van serverinstantie beperkt geen vraag tot Adobe Analytics, het controleert slechts welke vraag RSID omvat.
>
>Bijvoorbeeld, wordt een kader gevormd om de *driemaandelijkse rapportreeks* te gebruiken en de auteur is de geselecteerde serverinstantie. Wanneer de pagina&#39;s samen met het kader worden gepubliceerd, worden de vraag nog gemaakt aan Adobe Analytics, nochtans bevatten deze vraag niet RSID. Slechts omvatten de vraag van de auteursinstantie RSID.

1. Gebruikend **Navigatie**, uitgezochte **Hulpmiddelen**, **Cloud Services**, toen **Verouderde Cloud Services**.
2. Blader naar **Adobe Analytics** en klik op **[+]** naast **Beschikbare configuraties**.
3. Klik op de koppeling **[+]** naast uw Adobe Analytics-configuratie.

4. In het dialoogvenster **Kader** maken:

   * Geef een **titel** op.
   * U kunt optioneel de **naam** opgeven voor het knooppunt dat de frameworkgegevens in de opslagplaats opslaat.
   * Adobe Analytics **Framework selecteren**

   Klik op **Maken**.

   Het framework wordt geopend voor bewerking.

5. Klik in de sectie **Rapporten** van de zijpod (rechterkant van het hoofddeelvenster) op Item **** toevoegen. Vervolgens gebruikt u de vervolgkeuzelijst om de rapportsuite-id (bijvoorbeeld `geometrixxauth`) te selecteren waarmee het framework werkt.

   >[!NOTE]
   >
   >De zoeker naar inhoud aan de linkerkant wordt gevuld met Adobe Analytics-variabelen (SiteCatalyst-variabelen) wanneer u een rapportsuite-id selecteert.

6. Gebruik vervolgens de keuzelijst Modus **** Uitvoeren (naast de rapportsuite-id) om de serverinstanties te selecteren die u informatie naar de rapportsuite wilt verzenden.

   ![aa-framework-01](assets/aa-framework-01.png)

7. Als u het framework beschikbaar wilt maken op de publicatie-instantie van uw site, klikt u op het tabblad **Pagina** van sidekick op Framework **activeren.**

### Serverinstellingen voor Adobe Analytics configureren {#configuring-server-settings-for-adobe-analytics}

Met het raamsysteem kunt u de serverinstellingen binnen elk Adobe Analytics-framework wijzigen.

>[!CAUTION]
>
>Deze instellingen bepalen waar en hoe uw gegevens worden verzonden. Het is dus van essentieel belang dat u *niet met deze instellingen* knoeit en dat uw Adobe Analytics-vertegenwoordiger deze instellingen instelt.

Begin door het paneel te openen. Druk op de pijl-omlaag naast **Servers**:

![server_001](assets/server_001.png)

* **Trackingserver**

   * bevat de URL waarmee Adobe Analytics-aanroepen worden verzonden

      * cname - Wordt standaard ingesteld op de *Bedrijfsnaam * van de Adobe Analytics-account
      * d1 - komt overeen met het datacenter waarnaar de informatie wordt verzonden (kan d1, d2 of d3 zijn)
      * sc.omtr dc.net - domeinnaam

* **Secure Tracking Server**

   * Bevat dezelfde segmenten als de trackingserver
   * Dit wordt gebruikt voor het verzenden van gegevens van beveiligde pagina&#39;s (https://)

* **Naamruimte van bezoeker**

   * De naamruimte bepaalt het eerste deel van de URL voor bijhouden.
   * Als u bijvoorbeeld de naamruimte wijzigt in **CNAME** , zullen de aanroepen naar Adobe Analytics er als **CNAME.d1.omtr dc.net** uitzien in plaats van als standaard.

## Een pagina koppelen aan een Adobe Analytics-framework {#associating-a-page-with-a-adobe-analytics-framework}

Wanneer een pagina is gekoppeld aan een Adobe Analytics-framework, verzendt de pagina gegevens naar Adobe Analytics wanneer de pagina wordt geladen. Variabelen die door de pagina worden gevuld, worden toegewezen aan en opgehaald uit Adobe Analytics-variabelen in het framework. Paginaweergaven worden bijvoorbeeld opgehaald uit Adobe Analytics.

Afstammingen van de pagina nemen de koppeling met het framework over. Wanneer u bijvoorbeeld de hoofdpagina van uw site aan een framework koppelt, worden alle pagina&#39;s van de site aan het framework gekoppeld.

1. Selecteer in de **Sites** -console de pagina die u wilt instellen met tekstspatiëring.
1. Open de **[Pagina-eigenschappen](/help/sites-authoring/editing-page-properties.md)**, rechtstreeks vanuit de console of de pagina-editor.
1. Open het tabblad **Cloud Services** .

1. Gebruik de keuzelijst Configuratie **** toevoegen om **Adobe Analytics** te selecteren uit de beschikbare opties. Als er overerving is, moet u die uitschakelen voordat de kiezer beschikbaar wordt.

1. De keuzelijst voor **Adobe Analytics** wordt toegevoegd aan de beschikbare opties. Gebruik deze optie om de vereiste frameworkconfiguratie te selecteren.

1. Selecteer **Opslaan en sluiten**.
1. **[Publiceer](/help/sites-authoring/publishing-pages.md)**de pagina om de pagina en alle aangesloten configuraties/bestanden te activeren.
1. De laatste stap bestaat uit het bezoeken van de pagina op de publicatie-instantie en het zoeken naar een trefwoord (bijvoorbeeld een augmentor) met de component **Zoeken** .
1. U kunt dan de vraag controleren die aan Adobe Analytics wordt gemaakt gebruikend een aangewezen hulpmiddel; bijvoorbeeld [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html).
1. Gebruikend het verstrekte voorbeeld, zou de vraag de ingevoerde waarde (d.w.z. augplant) in eVar7 moeten bevatten en de gebeurtenislijst zou event3 moeten bevatten.

### Paginaweergaven {#page-views}

Wanneer een pagina aan een kader van Adobe Analytics wordt geassocieerd, kan het aantal paginameningen in de mening van de Lijst van de console van Plaatsen worden getoond.

Zie [De gegevens](/help/sites-authoring/pa-using.md) van de analyse van de pagina zien voor meer informatie.

### Het Interval van de Invoer vormen {#configuring-the-import-interval}

Vorm de aangewezen instantie van de **Adobe AEM de Beheerde dienst van de Configuratie** van de Opiniepeiling:

* **Interval opiniepeiling**:

   Het interval, in seconden, waarmee de service paginaweergavegegevens van Adobe Analytics ophaalt.

   Het standaardinterval is 43200000 ms (12 uur).

* **Inschakelen**:

   Schakel de service in of uit. Standaard is de service ingeschakeld.

Om deze dienst te vormen OSGi, kunt u of de [Console](/help/sites-deploying/configuring-osgi.md#osgi-configuration-with-the-web-console) van het Web of een knoop [osgiConfig in de bewaarplaats](/help/sites-deploying/configuring-osgi.md#osgi-configuration-in-the-repository) (de dienst PID is `com.day.cq.polling.importer.impl.ManagedPollConfigImpl`) gebruiken.

## Adobe Analytics-configuraties en/of frameworks bewerken {#editing-adobe-analytics-configurations-and-or-frameworks}

Ga net als bij het maken van een Adobe Analytics-configuratie of -framework naar het scherm (verouderd) **Cloud Services** . Selecteer **Configuraties** tonen en klik op de koppeling naar de specifieke configuratie die u wilt bijwerken.

Wanneer u een Adobe Analytics-configuratie bewerkt, moet u ook op de knop **Bewerken** drukken op de configuratiepagina zelf om het dialoogvenster Component **** bewerken te openen.

## Adobe Analytics-frameworks verwijderen {#deleting-adobe-analytics-frameworks}

Als u een Adobe Analytics-framework wilt verwijderen, [opent u het eerst voor bewerking](#editing-adobe-analytics-configurations-and-or-frameworks).

Selecteer vervolgens Framework **** verwijderen op het tabblad **Pagina** van het hulpwerkgebied.

