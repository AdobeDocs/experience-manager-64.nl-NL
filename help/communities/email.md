---
title: E-mail configureren
seo-title: Configuring Email
description: E-mailconfiguratie voor gemeenschappen
seo-description: Email configuration for Communities
uuid: e8422cc2-1594-43b0-b587-82825636cec1
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: b4d38e45-eaa0-4ace-a885-a2e84fdfd5a1
pagetitle: Configuring Email
role: Admin
exl-id: 0a0222e7-ca30-4603-94ad-582005b2de11
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 0%

---

# E-mail configureren {#configuring-email}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

AEM Communities gebruikt e-mail voor

* [Publikaties](notifications.md)
* [Communityabonnementen](subscriptions.md)

De e-mailfunctie werkt standaard niet omdat hiervoor een SMTP-server en een SMTP-gebruiker moet worden opgegeven.

>[!CAUTION]
>
>E-mail voor meldingen en abonnementen moet alleen zijn geconfigureerd op de [primaire uitgever](deploy-communities.md#primary-publisher).

## Standaardconfiguratie e-mailservice {#default-mail-service-configuration}

De standaardmailservice is vereist voor zowel meldingen als abonnementen.

* Op de primaire uitgever
* Aangemeld met beheerdersrechten
* Toegang krijgen tot [Webconsole](../../help/sites-deploying/configuring-osgi.md)

   * Bijvoorbeeld: [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr)

* Zoek de `Day CQ Mail Service`
* Het bewerkingspictogram selecteren

Dit is gebaseerd op de documentatie voor [E-mailmelding configureren](../../help/sites-administering/notification.md), maar met een verschil op dat gebied `"From" address` is *niet* vereist en moet leeg blijven.

Bijvoorbeeld (alleen invullen met waarden voor illustratieve doeleinden):

![chlimage_1-98](assets/chlimage_1-98.png)

* **[!UICONTROL SMTP server host name]**: *(vereist)* De SMTP-server die moet worden gebruikt.

* **[!UICONTROL SMTP server port]** *(vereist)* De SMTP serverhaven moet 25 of hoger zijn.

* **[!UICONTROL SMTP user]**: *(vereist)* De SMTP-gebruiker.

* **[!UICONTROL SMTP password]**: *(vereist)* Het wachtwoord van de SMTP-gebruiker.

* **[!UICONTROL "From" address]**: Leeg laten
* **[!UICONTROL SMTP use SSL]**: Als deze optie is ingeschakeld, wordt beveiligde e-mail verzonden. Zorg ervoor dat de poort is ingesteld op 465 of zoals is vereist voor de SMTP-server.
* **[!UICONTROL Debug email]**: Indien gecontroleerd, laat registreren van SMTP serverinteractie toe.

## AEM Communities E-mailconfiguratie {#aem-communities-email-configuration}

Wanneer de [standaardmailservice](#default-mail-service-configuration) wordt gevormd, de twee bestaande instanties van `AEM Communities Email Reply Configuration` OSGi config, inbegrepen in de versie, wordt functioneel.

Slechts moet de instantie voor abonnementen verder worden gevormd wanneer het toestaan van antwoord door e-mail.

1. ` [email](#configuration-for-notifications)` instance

   voor meldingen, die geen ondersteuning bieden voor e-mail met antwoorden, en die niet mogen worden gewijzigd

1. ` [subscriptions-email](#configuration-for-subscriptions)` instance

   vereist configuratie om het creëren van post van antwoord e-mail volledig toe te laten

U bereikt als volgt de e-mailconfiguratieinstanties van de Gemeenschappen:

* Op de primaire uitgever
* Aangemeld met beheerdersrechten
* Toegang krijgen tot [Webconsole](../../help/sites-deploying/configuring-osgi.md)

   * Bijvoorbeeld: [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr)

* Zoeken `AEM Communities Email Reply Configuration`

![chlimage_1-99](assets/chlimage_1-99.png)

### Configuratie voor meldingen {#configuration-for-notifications}

De instantie van `AEM Communities Email Reply Configuration` OSGi config met de Naam e-mail is voor de berichteigenschap. Deze functie bevat geen e-mailantwoord.

Deze configuratie moet niet worden gewijzigd.

* Zoek de `AEM Communities Email Reply Configuration`
* Het bewerkingspictogram selecteren
* Controleer de **Naam** is `email`

* Verifiëren **Bericht maken van e-mail met antwoord** is `unchecked`

![chlimage_1-100](assets/chlimage_1-100.png)

### Configuratie voor abonnementen {#configuration-for-subscriptions}

Voor Gemeenschapsabonnementen is het mogelijk om de mogelijkheid voor een lid om inhoud te posten in of uit te schakelen door op een e-mail te antwoorden.

* Zoek de `AEM Communities Email Reply Configuration`
* Het bewerkingspictogram selecteren
* Controleer de **Naam** is `subscriptions-email`

![chlimage_1-101](assets/chlimage_1-101.png)

* **[!UICONTROL Name]** : *(vereist)* `subscriptions-email`. Niet bewerken.

* **[!UICONTROL Create post from reply email]**: Als deze optie is ingeschakeld, kan de ontvanger van het e-mailbericht met abonnement inhoud posten door een antwoord te verzenden. Standaard is ingeschakeld.
* **[!UICONTROL Add tracked id to header]**: Standaard is `Reply-To`.

* **[!UICONTROL Maximum length of Subject]**: Als tracker-id aan de onderwerpregel wordt toegevoegd, is dit de maximumlengte van het onderwerp, met uitzondering van de bijgehouden id, waarna het wordt bijgesneden. Deze waarde moet zo klein mogelijk zijn om te voorkomen dat bijgehouden id-informatie verloren gaat. De standaardwaarde is 200.
* **[!UICONTROL Email "From" address]**: *(vereist)* Adres dat de bericht e-mail van zou worden geleverd. Waarschijnlijk hetzelfde **SMTP-gebruiker** gespecificeerd voor [standaardmailservice](#configuredefaultmailservice). Standaard is `no-reply@example.com`.

* **[!UICONTROL Reply-to-Delimiter]**: Als tracker-id wordt toegevoegd aan de header die reageert, wordt dit scheidingsteken gebruikt. Standaard is `+` (plusteken).

* **[!UICONTROL Tracker Id prefix in subject]**: Als tracker-id aan de onderwerpregel wordt toegevoegd, wordt dit voorvoegsel gebruikt. Standaard is `post#`.

* **[!UICONTROL Tracker id prefix in message body]**: Als tracker-id aan de hoofdtekst van het bericht wordt toegevoegd, wordt dit voorvoegsel gebruikt. Standaard is `Please do not remove this:`.

* **[!UICONTROL Email as HTML]**: Indien ingeschakeld, wordt het inhoudstype van het e-mailbericht ingesteld op `"text/html;charset=utf-8"`. Standaard is ingeschakeld.

* **[!UICONTROL Default user name]**: Deze naam wordt gebruikt voor geen naamgebruikers. Standaard is `no-reply@example.com`.

* **[!UICONTROL Templates root path]**: De e-mail wordt samengesteld met een sjabloon die op dit hoofdpad is opgeslagen. Standaard is `/etc/community/templates/subscriptions-email`.

## Opiniepeilingimportmodule configureren {#configure-polling-importer}

Om de e-mail in de gegevensopslagplaats te brengen, is het noodzakelijk om een opiniepeilingimporteur te vormen en zijn eigenschappen in de bewaarplaats manueel te vormen.

### Nieuwe importmodule voor opiniepeiling toevoegen {#add-new-polling-importer}

* Op de primaire uitgever
* Aangemeld met beheerdersrechten
* Blader bijvoorbeeld naar de pollingimporterconsole. [http://localhost:4503/etc/importers/polling.html](http://localhost:4503/etc/importers/polling.html)
* Selecteer **[!UICONTROL Add]**

![chlimage_1-102](assets/chlimage_1-102.png)

* **[!UICONTROL Type]**: *(vereist)* Omlaag trekken en selecteren `POP3 (over SSL).`

* **[!UICONTROL URL]**: *(vereist)* De uitgaande mailserver. Bijvoorbeeld, `pop.gmail.com:995/INBOX?username=community-emailgmail.com&password=****`

* **[!UICONTROL Import to Path]**&amp;last: *(vereist)* Instellen op `/content/usergenerated/mailFolder/postEmails`
door naar de 
`postEmails`map en selecteer **OK**

* **[!UICONTROL Update Interval in Seconds]**: *(optioneel)* De postserver die voor de standaard postdienst wordt gevormd kan vereisten betreffende de waarde van het updateinterval hebben. Voor Gmail kan bijvoorbeeld een interval van `300`.

* **[!UICONTROL Login]**: *(optioneel)*

* **[!UICONTROL Password]**: *(optioneel)*

* Selecteer **[!UICONTROL OK]**

### Protocol aanpassen voor nieuwe pollingimportmodule {#adjust-protocol-for-new-polling-importer}

Nadat de nieuwe stemconfiguratie is opgeslagen, moeten de eigenschappen van de e-mailimportfunctie met abonnement verder worden gewijzigd om het protocol te wijzigen van `POP3` tot `emailreply`

Gebruiken [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md):

* Op de primaire uitgever
* Aangemeld met beheerdersrechten
* Bladeren naar [https://&lt;server>:&lt;port>/crx/de/index.jsp#/etc/importers/polling](http://localhost:4503/crx/de/index.jsp#/etc/importers/polling)
* Selecteer de nieuwe configuratie
* De volgende eigenschappen wijzigen

   * **feedType**: vervangen `pop3s` with **`emailreply`**
   * **bron**: protocol van bron vervangen `pop3s://` with **`emailreply://`**

![chlimage_1-103](assets/chlimage_1-103.png)

De rode driehoeken geven de gewijzigde eigenschappen aan. Sla de wijzigingen op:

* Selecteer **[!UICONTROL Save All]**
