---
title: E-mailmelding configureren
seo-title: Configuring Email Notification
description: Leer hoe u e-mailmeldingen in AEM kunt configureren.
seo-description: Learn how to configure Email Notification in AEM.
uuid: 6cbdc312-860b-4a69-8bbe-2feb32204a27
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: 6466d7b8-e308-43c5-acdc-dec15f796f64
exl-id: ea12035c-09b6-4197-ab23-c27fe71e7432
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 1%

---

# E-mailmelding configureren{#configuring-email-notification}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

AEM stuurt e-mailmeldingen naar gebruikers die:

* Hebt u zich op paginagebeurtenissen geabonneerd, bijvoorbeeld aanpassing of replicatie. De [Melding in vak](/help/sites-classic-ui-authoring/author-env-inbox.md#subscribing-to-notifications) in deze sectie wordt beschreven hoe u zich op dergelijke gebeurtenissen kunt abonneren.

* Hebt u zich geabonneerd op forumgebeurtenissen.
* Een stap in een werkstroom uitvoeren. De [Stap deelnemer](/help/sites-developing/workflows-step-ref.md#participant-step) in deze sectie wordt beschreven hoe u e-mailmeldingen in een workflow kunt activeren.

Voorwaarden:

* Voor de gebruiker(s) moet(en) een geldig e-mailadres zijn gedefinieerd in dit profiel.
* De **CQ-mailservice op dag** moet correct worden geconfigureerd.

Wanneer een gebruiker op de hoogte wordt gesteld, ontvangt hij een e-mail in de taal die in zijn profiel wordt bepaald. Elke taal heeft zijn eigen malplaatje dat kan worden aangepast. U kunt nieuwe e-mailsjablonen toevoegen voor nieuwe talen.

>[!NOTE]
>
>Wanneer het werken met AEM zijn er verscheidene methodes om de configuratiemontages voor dergelijke diensten te beheren; zie [OSGi configureren](/help/sites-deploying/configuring-osgi.md) voor meer details en de aanbevolen werkwijzen.

## De Mail Service configureren {#configuring-the-mail-service}

Als AEM e-mailberichten wilt kunnen verzenden, **CQ-mailservice op dag** moet correct worden geconfigureerd. U kunt de configuratie in de console van het Web bekijken. Wanneer het werken met AEM zijn er verscheidene methodes om de configuratiemontages voor dergelijke diensten te beheren; zie [OSGi configureren](/help/sites-deploying/configuring-osgi.md) voor meer details en de aanbevolen werkwijzen.

De volgende beperkingen zijn van toepassing:

* De **SMTP-serverpoort** moet 25 of hoger zijn.

* De **hostnaam SMTP-server** mag niet leeg zijn.
* De **Adres &quot;Van&quot;** mag niet leeg zijn.

Om u te helpen een probleem met **CQ-mailservice op dag** kunt u de logbestanden van de service bekijken:

`com.day.cq.mailer.DefaultMailService`

De configuratie kijkt als volgt in de console van het Web:

![chlimage_1-276](assets/chlimage_1-276.png)

## Het kanaal voor e-mailmeldingen configureren {#configuring-the-email-notification-channel}

Wanneer u zich abonneert op berichten voor pagina- of forumgebeurtenissen, wordt het e-mailadres ingesteld op `no-reply@acme.com` standaard. U kunt deze waarde wijzigen door het dialoogvenster **E-mailkanaal voor meldingen** in de webconsole.

Als u het e-mailadres wilt configureren, voegt u een `sling:OsgiConfig` aan de gegevensopslagruimte. Gebruik de volgende procedure om de knoop direct toe te voegen gebruikend CRXDE Lite:

1. Voeg in CRXDE Lite een map met de naam `config` onder de toepassingsmap.
1. Voeg in de configuratiemap een knooppunt met de naam:

   `com.day.cq.wcm.notification.email.impl.EmailChannel` van het type `sling:OsgiConfig`

1. Voeg een `String` eigenschap voor de benoemde node `email.from`. Geef voor de waarde het e-mailadres op dat u wilt gebruiken.

1. Klikken **Alles opslaan**.

Gebruik de volgende procedure om het knooppunt in de bronmappen van het inhoudspakket te definiëren:

1. In uw `jcr_root/apps/*app_name*/config folder`, maakt u een bestand met de naam `com.day.cq.wcm.notification.email.impl.EmailChannel.xml`

1. Voeg de volgende XML toe om het knooppunt te vertegenwoordigen:

   `<?xml version="1.0" encoding="UTF-8"?> <jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0" xmlns:jcr="https://www.jcp.org/jcr/1.0" jcr:primaryType="sling:OsgiConfig" email.from="name@server.com"/>`
1. Vervang de waarde van de optie `email.from` attribute ( `name@server.com`) met uw e-mailadres.

1. Sla het bestand op.

## De Workflow Email Notification Service configureren {#configuring-the-workflow-email-notification-service}

Wanneer u e-mailmeldingen over de workflow ontvangt, worden zowel het adres van de e-mail als het URL-voorvoegsel van de host ingesteld op standaardwaarden. U kunt deze waarden wijzigen door het dialoogvenster **Day CQ Workflow Email Notification Service** in de webconsole. Als u dat doet, wordt aanbevolen de wijziging in de opslagplaats voort te zetten.

De standaardconfiguratie kijkt als volgt in de Console van het Web:

![chlimage_1-277](assets/chlimage_1-277.png)

### E-mailsjablonen voor paginamelding {#email-templates-for-page-notification}

De e-mailsjablonen voor paginaberichten staan hieronder:

`/libs/settings/notification-templates/com.day.cq.wcm.core.page`

De standaardsjabloon Engels ( `en.txt`) wordt als volgt gedefinieerd:

```xml
subject=[CQ Page Event Notification]: Page Event

header=-------------------------------------------------------------------------------------\n \
Time: ${time}\n \
User: ${userFullName} (${userId})\n \
-------------------------------------------------------------------------------------\n\n

message=The following pages were affected by the event: \n \
 \n \
${modifications} \n \
 \n\n
footer=\n \
-------------------------------------------------------------------------------------\n \
This is an automatically generated message. Please do not reply.
```

#### E-mailsjablonen aanpassen voor paginamelding {#customizing-email-templates-for-page-notification}

U kunt als volgt de Engelse e-mailsjabloon voor paginabeldingen aanpassen:

1. Open het bestand in CRXDE:

   `/libs/settings/notification-templates/com.day.cq.wcm.core.page/en.txt`

1. Wijzig het bestand naar wens.
1. Sla de wijzigingen op.

De sjabloon moet de volgende indeling hebben:

```
 subject=<text_1>
 header=<text_2>
 message=<text_3>
 footer=<text_4>
```

Wanneer &lt;text_x> Dit kan een combinatie zijn van statische tekst en dynamische tekenreeksvariabelen. De volgende variabelen kunnen in de e-mailsjabloon voor paginaberichten worden gebruikt:

* `${time}`, de datum en het tijdstip van de gebeurtenis.

* `${userFullName}`, de volledige naam van de gebruiker die de gebeurtenis heeft geactiveerd.

* `${userId}`, de id van de gebruiker die de gebeurtenis heeft geactiveerd.
* `${modifications}`beschrijft het type paginagebeurtenis en het paginapad in de notatie:

   &lt;page event=&quot;&quot; type=&quot;&quot;> => &lt;page path=&quot;&quot;>

   Bijvoorbeeld:

   PageModified => /content/geometrixx/nl/products

### E-mailsjablonen voor forumkennisgeving {#email-templates-for-forum-notification}

E-mailsjablonen voor forummeldingen vindt u onder:

`/etc/notification/email/default/com.day.cq.collab.forum`

De standaardsjabloon Engels ( `en.txt`) wordt als volgt gedefinieerd:

```xml
subject=[CQ Forum Notification]

header=-------------------------------------------------------------------------------------\n \
Time: Time: ${time}\n \
Forum Page Path: ${forum.path}\n \
-------------------------------------------------------------------------------------\n\n

message=Page: ${host.prefix}${forum.path}.html\n

footer=\n \
-------------------------------------------------------------------------------------\n \
This is an automatically generated message. Please do not reply.
```

#### E-mailsjablonen aanpassen voor forummelding {#customizing-email-templates-for-forum-notification}

U kunt als volgt de Engelse e-mailsjabloon voor forumkennisgeving aanpassen:

1. Open het bestand in CRXDE:

   `/etc/notification/email/default/com.day.cq.collab.forum/en.txt`

1. Wijzig het bestand naar wens.
1. Sla de wijzigingen op.

De sjabloon moet de volgende indeling hebben:

```
 subject=<text_1>
 header=<text_2>
 message=<text_3>
 footer=<text_4>
```

Wanneer `<text_x>` Dit kan een combinatie zijn van statische tekst en dynamische tekenreeksvariabelen.

De volgende variabelen kunnen binnen het e-mailmalplaatje voor forumberichten worden gebruikt:

* `${time}`, de datum en het tijdstip van de gebeurtenis.

* `${forum.path}`, het pad naar de forumpagina.

### E-mailsjablonen voor workflowmelding {#email-templates-for-workflow-notification}

Het e-mailsjabloon voor workflowmeldingen (Engels) bevindt zich op:

`/libs/settings/workflow/notification/email/default/en.txt`

Het wordt als volgt gedefinieerd:

```xml
subject=Workflow notification: ${event.EventType}

header=-------------------------------------------------------------------------------------\n \
Time: ${event.TimeStamp}\n \
Step: ${item.node.title}\n \
User: ${participant.name} (${participant.id})\n \
Workflow: ${model.title}\n \
-------------------------------------------------------------------------------------\n\n

message=Content: ${host.prefix}${payload.path.open}\n

footer=\n \
-------------------------------------------------------------------------------------\n \
View the overview in your ${host.prefix}/aem/inbox\n \
-------------------------------------------------------------------------------------\n \
This is an automatically generated message. Please do not reply.
```

#### E-mailsjablonen aanpassen voor workflowmelding {#customizing-email-templates-for-workflow-notification}

U kunt als volgt de Engelse e-mailsjabloon voor workflowgebeurtenismeldingen aanpassen:

1. Open het bestand in CRXDE:

   `/libs/settings/workflow/notification/email/default/en.txt`

1. Wijzig het bestand naar wens.
1. Sla de wijzigingen op.

De sjabloon moet de volgende indeling hebben:

```
subject=<text_1>
 header=<text_2>
 message=<text_3>
 footer=<text_4>
```

>[!NOTE]
>
>Wanneer `<text_x>` Dit kan een combinatie zijn van statische tekst en dynamische tekenreeksvariabelen. Elke regel van een `<text_x>` item moet worden beëindigd met een backslash ( `\`), behalve in de laatste instantie, wanneer de afwezigheid van de backslash het einde van de `<text_x>` tekenreeksvariabele.
>
>Meer informatie over de sjabloonindeling vindt u in de [javadocs van the Properties.load()](https://docs.oracle.com/javase/8/docs/api/java/util/Properties.html#load-java.io.InputStream-) methode.

De methode `${payload.path.open}` onthult de weg aan de lading van het werkpunt. Voor bijvoorbeeld een pagina in Sites, dan `payload.path.open` zou vergelijkbaar zijn met `/bin/wcmcommand?cmd=open&path=…`.; dit is zonder de servernaam, die is waarom het malplaatje dit met presteert `${host.prefix}`.

De volgende variabelen kunnen binnen het e-mailmalplaatje worden gebruikt:

* `${event.EventType}`, type gebeurtenis
* `${event.TimeStamp}`, datum en tijdstip van de gebeurtenis
* `${event.User}`, de gebruiker die de gebeurtenis heeft geactiveerd
* `${initiator.home}`, het pad naar het initiatorknooppunt

* `${initiator.name}`, de naam van de aanvrager

* `${initiator.email}`, e-mailadres van de aanvrager
* `${item.id}`, de id van het werkitem
* `${item.node.id}`, id van het knooppunt in het workflowmodel dat aan dit werkitem is gekoppeld
* `${item.node.title}`, titel van het werkitem
* `${participant.email}`, e-mailadres van de deelnemer
* `${participant.name}`, naam van de deelnemer
* `${participant.familyName}`, familienaam van de deelnemer
* `${participant.id}`, id van de deelnemer
* `${participant.language}`, de taal van de deelnemer
* `${instance.id}`, de workflow-id
* `${instance.state}`, de workflowstatus
* `${model.title}`, titel van het workflowmodel
* `${model.id}`, de id van het workflowmodel

* `${model.version}`, de versie van het workflowmodel
* `${payload.data}`, de lading

* `${payload.type}`, het ladingstype
* `${payload.path}`, pad van de lading
* `${host.prefix}`, hostvoorvoegsel, bijvoorbeeld: http://localhost:4502

### Een e-mailsjabloon toevoegen voor een nieuwe taal {#adding-an-email-template-for-a-new-language}

Een sjabloon toevoegen voor een nieuwe taal:

1. Voeg in CRXDE een bestand toe `<language-code>.txt` hieronder:

   * `/libs/settings/notification-templates/com.day.cq.wcm.core.page` : voor paginameldingen
   * `/etc/notification/email/default/com.day.cq.collab.forum` : voor forummeldingen
   * `/libs/settings/workflow/notification/email/default` : voor workflowmeldingen

1. Pas het bestand aan de taal aan.
1. Sla de wijzigingen op.

>[!NOTE]
>
>De `<language-code>` gebruikt als de bestandsnaam van de e-mailsjabloon moet een taalcode van twee letters in kleine letters zijn die door AEM wordt herkend. Voor taalcodes is AEM gebaseerd op ISO-639-1.

## E-mailberichten voor AEM Assets configureren {#assetsconfig}

Wanneer Verzamelingen in AEM Assets worden gedeeld of niet gedeeld, kunnen gebruikers e-mailmeldingen ontvangen van AEM. Voer de volgende stappen uit om e-mailmeldingen te configureren.

1. De e-mailservice configureren, zoals hierboven beschreven in [De Mail Service configureren](/help/sites-administering/notification.md#configuring-the-mail-service).
1. Meld u aan bij AEM als beheerder. Klikken **Gereedschappen** >  **Bewerkingen** >  **Webconsole** om Webconsoleconfiguratie te openen.
1. Bewerken **Day CQ DAM Resource Collection Servlet**. Selecteren **e-mail verzenden**. Klikken **Opslaan**.
