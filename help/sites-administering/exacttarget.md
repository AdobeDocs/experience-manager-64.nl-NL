---
title: Integreren met ExactTarget
seo-title: Integrating with ExactTarget
description: Leer hoe u AEM kunt integreren met ExactTarget.
seo-description: Learn how to integrate AEM with ExactTarget.
uuid: dafa0a1a-2d1e-40fc-a729-f2ce7ebc7807
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: d1cff2bb-9fdf-49cb-a695-d437bba5653d
exl-id: 943e5199-271f-4015-a9f7-4d39c00deabe
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 0%

---

# Integreren met ExactTarget{#integrating-with-exacttarget}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Door AEM te integreren met Exact Target kunt u in AEM gemaakte e-mailberichten beheren en verzenden via Exact Target. U kunt hiermee ook de beheerfuncties voor leads van Exact Target gebruiken via AEM formulieren op AEM pagina&#39;s.

De integratie biedt u de volgende functies:

* De capaciteit om E-mail in AEM tot stand te brengen en hen te publiceren aan Exact Doel voor distributie.
* De capaciteit om actie van een AEM vorm te plaatsen om een Exact abonnee van het Doel tot stand te brengen.

Nadat ExactTarget is geconfigureerd, kunt u nieuwsbrieven of e-mails naar ExactTarget publiceren. Zie [Nieuwsbrieven publiceren naar een e-mailservice](/help/sites-authoring/personalization.md).

## Een ExactTarget-configuratie maken {#creating-an-exacttarget-configuration}

De configuraties ExactTarget kunnen via de Diensten van de Wolk of Hulpmiddelen worden toegevoegd. Beide methoden worden in deze sectie beschreven.

### ExactTarget configureren via Cloudservices {#configuring-exacttarget-via-cloudservices}

Om een configuratie ExactTarget in Cloud Services te creëren:

1. Klik op de welkomstpagina op **Cloud Services**. (Of rechtstreeks toegang tot `https://<hostname>:<port>/etc/cloudservices.html`.)
1. Klikken **ExactTarget** en vervolgens **Configureren**. Het ExactTarget configuratievenster opent.

   ![chlimage_1-182](assets/chlimage_1-182.png)

1. Voer een titel en eventueel een naam in en klik op **Maken**. Het** ExactTarget Settings* configuratievenster wordt geopend.

   ![chlimage_1-31](assets/chlimage_1-31.jpeg)

1. Voer de gebruikersnaam en het wachtwoord in en selecteer een API-eindpunt (bijvoorbeeld **https://webservice.exacttarget.com/Service.asmx**).
1. Klikken **Verbind met ExactTarget.** Wanneer de verbinding tot stand is gebracht, wordt het dialoogvenster geslaagd. Klikken **OK** om het venster te sluiten.

   ![chlimage_1-32](assets/chlimage_1-32.jpeg)

1. Selecteer een account, indien beschikbaar. De account is bestemd voor Enterprise 2.0-klanten. Klikken **OK**.

   ExactTarget is gevormd. U kunt de configuratie bewerken door op **Bewerken**. U kunt naar ExactTarget gaan door te klikken **Ga naar ExactTarget**.

1. AEM beschikt nu over een functie voor gegevensextensie. U kunt ExactTarget-gegevensextensiekolommen importeren. Dit kan worden gevormd door &quot;+&quot;teken te klikken dat behalve met succes tot stand gebrachte configuratie ExactTarget verschijnt. U kunt een van de bestaande gegevensextensies selecteren in de vervolgkeuzelijst. Voor meer informatie over hoe te om gegevensuitbreidingen te vormen, verwijs [ExactTarget-documentatie](https://help.exacttarget.com/en/documentation/exacttarget/subscribers/data_extensions_and_data_relationships).

   De geïmporteerde kolommen voor gegevensextensies kunnen later worden gebruikt via de **Tekst en personalisatie** component.

   ![chlimage_1-33](assets/chlimage_1-33.jpeg)

### ExactTarget configureren via tools {#configuring-exacttarget-via-tools}

Om een configuratie ExactTarget in Hulpmiddelen tot stand te brengen:

1. Klik op de welkomstpagina op **Gereedschappen**. Of navigeer daar rechtstreeks door naar `https://<hostname>:<port>/misadmin#/etc`.
1. Selecteren **Gereedschappen** vervolgens **Cloud Services-configuraties,** dan **ExactTarget**.
1. Klikken **Nieuw** om het venster **Pagina maken **te openen.

   ![chlimage_1-34](assets/chlimage_1-34.jpeg)

1. Voer de **Titel** en eventueel de **Naam** en klik op **Maken**.
1. Ga de configuratieinformatie in zoals die in stap 4 in de vorige procedure wordt geschetst. Volg die procedure om het vormen ExactTarget te beëindigen.

### Meerdere configuraties toevoegen {#adding-multiple-configurations}

Meerdere configuraties toevoegen:

1. Klik op de welkomstpagina op **Cloud Services** en klik op **ExactTarget**. Klikken op **Configuraties tonen** knoop die verschijnt als één of meerdere configuraties ExactTarget beschikbaar zijn. Alle beschikbare configuraties worden vermeld.
1. Klik op de knop **+** ondertekenen naast Beschikbare configuraties. Hierdoor wordt het **Configuraties maken** venster. Volg de vorige configuratieprocedure om een nieuwe configuratie tot stand te brengen.
