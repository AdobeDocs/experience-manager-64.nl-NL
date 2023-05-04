---
title: Berichtenonderdeel
seo-title: Messaging Feature
description: Het vormen van de componenten van het Overseinen
seo-description: Configuring Messaging components
uuid: 29ab63b6-67a1-4eb8-8cf8-c1ff52ff2bac
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 88ee8573-58c4-42cd-8e36-2ea4a0d654e4
exl-id: e03cf05c-2469-4883-ae7b-9d7e6660b71f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 0%

---

# Berichtenonderdeel {#messaging-feature}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Naast de openbaar zichtbare interacties die in forums en commentaren voorkomen, laat de overseineneigenschap van AEM Communities communityleden toe om met elkaar meer privé in wisselwerking te staan.

Dit onderdeel kan worden opgenomen wanneer een [community-site](overview.md#communitiessites) wordt gemaakt.

De overseineneigenschappen verstrekken de capaciteit om:

* Een bericht sturen naar een of meer leden van de community
* Een bericht sturen naar een groep van leden van de gemeenschap
* Een bericht met bijlagen verzenden
* Een bericht doorsturen
* Een bericht beantwoorden
* Een bericht verwijderen
* Een verwijderd bericht herstellen

Om de overseineneigenschap toe te laten en te wijzigen, bezoek

* [Berichten configureren](messaging.md) voor beheerders
* [Grondbeginselen van berichten](essentials-messaging.md) voor ontwikkelaars

>[!NOTE]
>
>Toevoegen wordt niet ondersteund `Compose Message, Message, or Message List` componenten (gevonden in `Communities`(componentgroep) naar een pagina in de bewerkingsmodus van de auteur.

## Berichtencomponenten configureren {#configuring-messaging-components}

Wanneer het overseinen voor een communautaire plaats wordt toegelaten, is het volledig opstelling zonder verdere configuratie noodzakelijk. Deze informatie wordt verstrekt als er een behoefte is om de standaardconfiguratie te veranderen.

### Berichtlijst configureren (berichtvakBox) {#configuring-message-list-messagebox}

Om de configuratie van de lijst met berichten te wijzigen voor **Inbox**, **Verzonden items**, en **Prullenbak** pagina&#39;s van de overseineneigenschap, open de plaats in [bewerkingsmodus auteur](sites-console.md#authoring-site-content).

In `Preview` in, selecteert u de **[!UICONTROL Messages]** verbinding om de belangrijkste overseinenpagina te openen. Selecteer vervolgens **[!UICONTROL Inbox, Sent Items, or Trash]** om de component voor die berichtlijst te vormen.

In `Edit` selecteert u de component op de pagina.

Als u toegang wilt tot het configuratiedialoogvenster, moet u de overerving annuleren door de optie `link`pictogram.

Zodra de configuratie volledig is, is het noodzakelijk om overerving te herstellen door te selecteren `broken link` pictogram.

![chlimage_1-396](assets/chlimage_1-396.png)

Als de overerving is geannuleerd, kunt u de optie `configure` pictogram om het configuratiedialoogvenster te openen.

![chlimage_1-397](assets/chlimage_1-397.png)

#### Het tabblad Basis {#basic-tab}

![chlimage_1-398](assets/chlimage_1-398.png)

* **[!UICONTROL Service selector]**
(*Vereist*) Stel deze in op de waarde van de eigenschap `serviceSelector.name` van de [AEM Communities Messaging Operations Service](messaging.md#messaging-operations-service).

* **[!UICONTROL Compose Page]**
(*Vereist*) De pagina die moet worden geopend wanneer een lid op de knop `Reply` knop. De doelpagina moet de **[!UICONTROL Compose Message]** formulier.

* **[!UICONTROL Reply/View as Resource]**
Als deze optie is ingeschakeld, verwijzen de URL van de reactie en de URL van de weergave naar een bron, anders worden gegevens doorgegeven als queryparameters in de URL.

* **[!UICONTROL Profile Display Form]**
Het profielformulier dat moet worden gebruikt om het afzenderprofiel weer te geven.

* **[!UICONTROL Trash Folder]**
Als deze optie is ingeschakeld, worden in deze component Berichtlijst alleen berichten weergegeven die zijn gemarkeerd als verwijderd (prullenbak).

* **[!UICONTROL Folder Paths]**
(*Vereist*) Verwijzen naar de waarden die zijn ingesteld voor `inbox.path.name` en `sentitems.path.name` in de [AEM Communities Messaging Operations Service](messaging.md#messaging-operations-service). Wanneer het vormen voor een `Inbox`Voeg één item toe met de waarde van `inbox.path.name`. Wanneer het vormen voor een `Outbox`Voeg één item toe met de waarde van `sentitems.path.name`. Wanneer het vormen voor `Trash`Voeg twee items met beide waarden toe.

#### Tabblad Weergave {#display-tab}

![chlimage_1-399](assets/chlimage_1-399.png)

* **[!UICONTROL Mark Read Button]**
Als deze optie is ingeschakeld, wordt een 
`Read`knop waarmee een bericht kan worden gemarkeerd als gelezen.

* **[!UICONTROL Mark Unread Button]**
Als deze optie is ingeschakeld, wordt een 
`Mark Unread` knop waarmee een bericht kan worden gemarkeerd als gelezen.

* **[!UICONTROL Delete Button]**
Als deze optie is ingeschakeld, wordt een 
`Delete`knop waarmee een bericht kan worden gemarkeerd als gelezen. Hiermee wordt de verwijderfunctie gedupliceerd als **`Message Options`** wordt ook gecontroleerd.

* **[!UICONTROL Message Options]**
Indien ingeschakeld, wordt weergegeven 
**`Reply`**, **`Reply All`**, **`Forward`** en **`Delete`** knoppen waarmee een bericht kan worden weergegeven of verwijderd. Hiermee wordt de verwijderfunctie gedupliceerd als **`Delete Button`** wordt ook gecontroleerd.

* **[!UICONTROL Messages Per Page]**
Het opgegeven aantal is het maximumaantal berichten dat per pagina in een pagineringsschema wordt weergegeven. Als geen aantal wordt gespecificeerd (verlaten leeg), dan worden alle berichten getoond en er is geen paginering.

* **[!UICONTROL Timestamp patterns]**
Geef tijdstempelpatronen op voor een of meer talen. Standaard is dit voor en, de, fr, it, es, ja, zh_CN, ko_KR.

* **[!UICONTROL Display User]**
Kies 
**`Sender`** of **`Recipients`** om te bepalen of de afzender of de Ontvanger moet worden weergegeven.

### Bericht voor samenstellen configureren {#configuring-compose-message}

Als u de configuratie van de pagina voor samenstellen van berichten wilt wijzigen, opent u de site in [bewerkingsmodus auteur](sites-console.md#authoring-site-content).

In `Preview`in, selecteert u de **[!UICONTROL Messages]** verbinding om de belangrijkste overseinenpagina te openen. Selecteer vervolgens de knop Nieuw bericht om het dialoogvenster `Compose Message` pagina..

In `Edit` Selecteer in de modus de hoofdcomponent op de pagina die de berichttekst bevat.

Als u toegang wilt tot het configuratiedialoogvenster, moet u de overerving annuleren door de optie `link`pictogram.

Zodra de configuratie volledig is, is het noodzakelijk om overerving te herstellen door te selecteren `broken link` pictogram.

![chlimage_1-400](assets/chlimage_1-400.png)

Als de overerving is geannuleerd, kunt u de optie `configure` pictogram om het configuratiedialoogvenster te openen.

![chlimage_1-401](assets/chlimage_1-401.png)

#### Het tabblad Basis {#basic-tab-1}

![chlimage_1-402](assets/chlimage_1-402.png)

* **[!UICONTROL Redirect URL]**
Voer de URL in van de pagina die wordt weergegeven nadat het bericht is verzonden. Bijvoorbeeld, 
`../messaging.html`.

* **[!UICONTROL Cancel URL]**
Voer de URL van de weergegeven pagina in als de afzender het bericht annuleert. Bijvoorbeeld, 
`../messaging.html`.

* **[!UICONTROL Maximum length of Message Subject]**
Het maximum aantal tekens dat is toegestaan in het veld Onderwerp. Bijvoorbeeld 500. Standaard is geen limiet.

* **[!UICONTROL Maximum length of Message Body]**
Het maximum aantal tekens dat is toegestaan in het veld Inhoud. Bijvoorbeeld 10000. Standaard is geen limiet.

* **[!UICONTROL Service selector]**
(*Vereist*) Stel deze in op de waarde van de eigenschap **`serviceSelector.name`** van de [AEM Communities Messaging Operations Service](messaging.md#messaging-operations-service).

#### Tabblad Weergave {#display-tab-1}

![chlimage_1-403](assets/chlimage_1-403.png)

* **[!UICONTROL Show Subject Field]**
Indien ingeschakeld, geeft u de optie 
`Subject` en schakelt u het toevoegen van een onderwerp aan het bericht in. Standaard is niet ingeschakeld.

* **[!UICONTROL Subject Label]**
Voer de tekst in die naast de 
`Subject` veld. Standaard is `Subject`.

* **[!UICONTROL Show Attach File Field]**
Indien ingeschakeld, geeft u de optie 
`Attachment` en schakel het toevoegen van bestandsbijlagen aan het bericht in. Standaard is niet ingeschakeld.

* **[!UICONTROL Attach File Label]**
Voer de tekst in die naast de 
`Attachment` veld. Standaard is **`Attach File`**.

* **[!UICONTROL Show Content Field]**
Indien ingeschakeld, geeft u de optie 
`Content` en schakelt u het toevoegen van een berichttekst in. Standaard is niet ingeschakeld.

* **[!UICONTROL Content Label]**
Voer de tekst in die naast de 
`Content` veld. Standaard is **`Body`**.

* **[!UICONTROL With Rich Text Editor]**
Als deze optie is ingeschakeld, wordt het gebruik van een tekstvak met aangepaste inhoud met een eigen RTF-editor aangegeven. Standaard is niet ingeschakeld.

* **[!UICONTROL Timestamp patterns]**
Geef tijdstempelpatronen op voor een of meer talen. Standaard is dit voor en, de, fr, it, es, ja, zh_CN, ko_KR.
