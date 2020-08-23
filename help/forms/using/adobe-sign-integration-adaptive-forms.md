---
title: Adobe Sign integreren met AEM Forms
seo-title: Adobe Sign integreren met AEM Forms
description: Leer hoe u Adobe Sign for AEM Forms configureert
seo-description: Leer hoe u Adobe Sign for AEM Forms configureert
uuid: 9efd5c44-3d87-4c56-aa6c-e65397fff243
contentOwner: sashanka
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: 7d494c2e-d457-4d52-89be-a77ffa07eb88
translation-type: tm+mt
source-git-commit: b698a1348df3ec2ab455c236422784d10cbcf7c2
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 0%

---


# Adobe Sign integreren met AEM Forms {#integrate-adobe-sign-with-aem-forms}

Leer hoe u Adobe Sign for AEM Forms configureert

Adobe Sign maakt workflows voor e-handtekeningen mogelijk voor adaptieve formulieren. E-handtekeningen verbeteren workflows om documenten te verwerken voor juridische documenten, verkoop, salarisadministratie, personeelsbeheer en nog veel meer gebieden.

In een standaard Adobe Sign- en adaptief formulierscenario vult een gebruiker een adaptief formulier om een service aan te vragen. Bijvoorbeeld een creditcardaanvraag en een burgerservicepakket. Wanneer een gebruiker het toepassingsformulier invult, verzendt en ondertekent, wordt het formulier naar de serviceprovider verzonden voor verdere actie. De serviceprovider controleert de toepassing en gebruikt Adobe Sign om de goedgekeurde toepassing te markeren. Als u vergelijkbare workflows voor elektronische handtekeningen wilt inschakelen, kunt u Adobe Sign integreren met AEM Forms.

Als u Adobe Sign met AEM Forms wilt gebruiken, configureert u Adobe Sign in AEM Cloud Services:

## Vereisten {#prerequisites}

U hebt het volgende nodig om Adobe Sign te integreren met AEM Forms:

* Een actief [Adobe Sign-ontwikkelaarsaccount](https://acrobat.adobe.com/us/en/why-adobe/developer-form.html).
* Een AEM Forms-server met [SSL ingeschakeld](/help/sites-administering/ssl-by-default.md) .
* Een [Adobe Sign API-toepassing](https://www.adobe.io/apis/documentcloud/sign/docs.html#!adobedocs/adobe-sign/master/gstarted/create_app.md).
* Referenties (client-id en clientgeheim) van Adobe Sign API-toepassing.

## Adobe Sign configureren met AEM Forms {#configure-adobe-sign-with-aem-forms}

Voer de volgende stappen uit om Adobe Sign met AEM Forms in de Author-instantie te configureren nadat u aan de voorwaarden hebt voldaan:

1. Navigeer in de AEM Forms-auteurinstantie naar **[!UICONTROL Tools** ![hammer](assets/hammer.png) > **General** > **Configuration Browser]**.
1. On the **[!UICONTROL Configuration Browser]** page, tap **[!UICONTROL Create]**.
1. Geef in het **[!UICONTROL Create Configuration]** dialoogvenster een waarde op **[!UICONTROL Title]** voor de configuratie, schakel **[!UICONTROL Cloud Configurations]** deze in en tik op **[!UICONTROL Create]**. Er wordt een configuratiecontainer voor cloudservices gemaakt.
1. Navigeer naar **[!UICONTROL Tools** ![hammer](assets/hammer.png) > **Cloud Services** > **Adobe Sign]** en selecteer de configuratiecontainer die u in de bovenstaande stap hebt gemaakt.

   >[!NOTE]
   >
   >Zorg ervoor dat de URL van de configuratiepagina voor cloudservices begint met **HTTPS**. Als dat niet het geval is, [schakelt u SSL](/help/sites-administering/ssl-by-default.md) voor de AEM Forms-server in.

1. Tik op de configuratiepagina **[!UICONTROL Create]** om Adobe Sign-configuratie te maken in AEM Forms.
1. Geef op het **[!UICONTROL General]** tabblad van de **[!UICONTROL Create Adobe Sign Configuration]** pagina een waarde op **[!UICONTROL Name]** voor de configuratie en tik op **[!UICONTROL Next]**. U kunt desgewenst een titel opgeven en naar een miniatuur voor de configuratie bladeren.

   Kopieer de URL in het huidige browservenster. Het is vereist om Adobe Sign-toepassing te configureren met AEM Forms.

1. Configureer OAuth-instellingen voor de Adobe Sign-toepassing:

   1. Open een browservenster en meld u aan bij de Adobe Sign-ontwikkelaarsaccount.
   1. Selecteer de toepassing die voor AEM Forms is geconfigureerd en tik op OAuth configureren voor toepassing.
   1. Voeg in het **[!UICONTROL Redirect URL]** vak de HTTPS-URL toe die u in de vorige stap hebt gekopieerd en klik op **[!UICONTROL Save]**.
   1. Schakel de volgende OAuth-instellingen voor de Adobe Sign-toepassing in en klik op **[!UICONTROL Save]**.
   * samenvoeging_read
   * samenvoeging_write
   * aggregatie_verzenden
   * widget_write
   * workflow_read

   Voor geleidelijke informatie om montages OAuth voor een toepassing van Adobe Sign te vormen en de sleutels te verkrijgen, zie de montages van de Auth van de [Vorm voor de documentatie van de toepassingsontwikkelaar](https://www.adobe.io/apis/documentcloud/sign/docs.html#!adobedocs/adobe-sign/master/gstarted/configure_oauth.md) .

   ![OAuth Config](assets/oauth_config.png)

1. Ga terug naar de **[!UICONTROL Create Adobe Sign Configuration]** pagina. Op het **[!UICONTROL Settings]** tabblad geeft het **[!UICONTROL OAuth URL]** veld de volgende standaard-URL weer:

   `https://secure.na1.echosign.com/public/oauth`

   waarbij:

   **na1** verwijst naar het standaard gegevensbestandaandeel.

   U kunt de waarde voor het delen van de database wijzigen. Start de server opnieuw om de nieuwe waarde voor de databaseschijf te kunnen gebruiken.

1. Geef de opties **[!UICONTROL Client ID]** (ook toepassings-id genoemd) en **[!UICONTROL Client Secret]**. Selecteer de **[!UICONTROL Enable Adobe Sign for attachments also]** optie om bestanden die zijn gekoppeld aan een adaptief formulier, toe te voegen aan het corresponderende Adobe Sign-document dat ter ondertekening is verzonden.

   Tik op **[!UICONTROL Connect to Adobe Sign]**. Geef bij de aanwijzing voor referenties de gebruikersnaam en het wachtwoord op van het account dat wordt gebruikt bij het maken van een Adobe Sign-toepassing.

   Tik **[!UICONTROL Create]** om de Adobe Sign-configuratie te maken.

1. Open AEM webconsole. De URL is `https://[server]:[port]/system/console/configMgr`
1. Open **[!UICONTROL Forms Common Configuration Service]**.
1. Selecteer in het **[!UICONTROL Allow]** veld **[!UICONTROL All users]** - Alle gebruikers, anoniem of aangemeld, kunnen een voorbeeld van bijlagen bekijken, formulieren verifiëren en ondertekenen en klikken **[!UICONTROL Save]**. Author-instantie is geconfigureerd voor gebruik van Adobe Sign.
1. Meld u aan bij de instantie [Publiceren](/help/sites-deploying/deploy.md) en open de volgende URL:

   `https://<server-name>:<port>/libs/granite/configurations/content/view.html/conf`

1. Herhaal stap 1 tot en met 12 om Adobe Sign met AEM Forms te configureren. Gebruik dezelfde titel voor configuratie (zoals opgegeven in stap 3) en dezelfde naam (zoals opgegeven in stap 6) om de instellingen te repliceren die op de instantie Auteur zijn geconfigureerd.

   Adobe Sign is nu geïntegreerd met AEM Forms en klaar voor gebruik in adaptieve formulieren. Als u de Adobe Sign-service in een adaptieve vorm [wilt](/help/forms/using/working-with-adobe-sign.md#configure-adobe-sign-for-an-adaptive-form)gebruiken, geeft u de hierboven gemaakte configuratiecontainer op in adaptieve formuliereigenschappen.

## Adobe Sign-planner configureren om de ondertekeningsstatus te synchroniseren {#configure-adobe-sign-scheduler-to-sync-the-signing-status}

Een adaptief formulier dat geschikt is voor Adobe Sign wordt alleen verzonden nadat alle ondertekenaars het ondertekeningsproces hebben voltooid. Standaard is de Adobe Sign Scheduler-service gepland om na elke 24 uur de respons van de ondertekenaar van de (opiniepeiling)gegevens te controleren. U kunt het standaardinterval voor uw milieu veranderen. Voer de volgende stappen uit om het standaardinterval te wijzigen:

1. Meld u met beheerdersgegevens aan bij de AEM Forms-server en navigeer naar **[!UICONTROL Tools]** > **Bewerkingen** > **Webconsole**.

   U kunt ook de volgende URL openen in een browservenster:

   `https://[localhost]:[port]/system/console/configMgr`

1. Zoek en open de **[!UICONTROL Adobe Sign Configuration Service]** optie. Geef een [uitsnijdexpressie](https://en.wikipedia.org/wiki/Cron#CRON_expression) op in het **[!UICONTROL Status Update Scheduler Expression]** veld en klik **[!UICONTROL Save]**. Bijvoorbeeld, om de configuratieservice dagelijks om 00:00 uur in werking te stellen, specificeer `0 0 0 1/1 * ? *` op het **[!UICONTROL Status Update Scheduler Expression]** gebied.

Het standaardinterval voor het synchroniseren van de status van Adobe Sign is nu gewijzigd.
