---
title: Acrobat Sign integreren met AEM Forms
seo-title: Integrate Acrobat Sign with AEM Forms
description: Leer hoe u Acrobat Sign for AEM Forms configureert
seo-description: Learn how to configure Acrobat Sign for AEM Forms
uuid: 9efd5c44-3d87-4c56-aa6c-e65397fff243
contentOwner: sashanka
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: 7d494c2e-d457-4d52-89be-a77ffa07eb88
feature: Adaptive Forms, Acrobat Sign
exl-id: e7c27623-a889-4bd5-bfff-cfe513cd1a35
source-git-commit: f8b19b6723d333e76fed111b9fde376b3bb13a1d
workflow-type: tm+mt
source-wordcount: '942'
ht-degree: 0%

---

# Acrobat Sign integreren met AEM Forms {#integrate-adobe-sign-with-aem-forms}

Acrobat Sign maakt workflows voor e-handtekeningen mogelijk voor adaptieve formulieren. E-handtekeningen verbeteren workflows om documenten te verwerken voor juridische documenten, verkoop, salarisadministratie, personeelsbeheer en nog veel meer gebieden.

In een standaard Acrobat Sign- en adaptief formulierscenario vult een gebruiker een adaptief formulier op **een dienst aanvragen**. Bijvoorbeeld een creditcardaanvraag en een burgerservicepakket. Wanneer een gebruiker het toepassingsformulier invult, verzendt en ondertekent, wordt het formulier naar de serviceprovider verzonden voor verdere actie. De serviceprovider controleert de toepassing en gebruikt Acrobat Sign om de goedgekeurde toepassing te markeren. Als u vergelijkbare workflows voor elektronische handtekeningen wilt inschakelen, kunt u Acrobat Sign integreren met AEM Forms.

Als u Acrobat Sign met AEM Forms wilt gebruiken, configureert u Acrobat Sign in AEM Cloud Services:

## Vereisten {#prerequisites}

U hebt het volgende nodig om Acrobat Sign te integreren met AEM Forms:

* Een actief [Acrobat Sign Developer-account.](https://acrobat.adobe.com/us/en/why-adobe/developer-form.html)
* An [SSL ingeschakeld](/help/sites-administering/ssl-by-default.md) AEM Forms-server.
* An [Acrobat Sign API-toepassing](https://www.adobe.io/apis/documentcloud/sign/docs.html#!adobedocs/adobe-sign/master/gstarted/create_app.md).
* Referenties (client-id en clientgeheim) van Acrobat Sign API-toepassing.
* Als u de configuratie opnieuw configureert, verwijdert u de bestaande Acrobat Sign-configuratie uit zowel auteur- als publicatieinstanties.
* Gebruiken [identieke cryptosleutel](/help/sites-administering/security-checklist.md#make-sure-you-properly-replicate-encryption-keys-when-needed) voor auteur- en publicatieinstanties.

## Acrobat Sign configureren met AEM Forms {#configure-adobe-sign-with-aem-forms}

Voer de volgende stappen uit om Acrobat Sign met AEM Forms in de Author-instantie te configureren nadat u aan de voorwaarden hebt voldaan:

1. Navigeer in AEM Forms-auteurinstantie naar **Gereedschappen** ![hamer](assets/hammer.png) > **Algemeen** > **Configuratiebrowser**.
   * Zie de [Documentatie van de configuratievenster](/help/sites-administering/configurations.md) voor meer informatie .
1. Op de **[!UICONTROL Configuration Browser]** pagina, tikken **[!UICONTROL Create]**.
1. In de **[!UICONTROL Create Configuration]** dialoogvenster, geeft u een **[!UICONTROL Title]** voor de configuratie, laat toe **[!UICONTROL Cloud Configurations]** en tikken **[!UICONTROL Create]**. Er wordt een configuratiecontainer voor cloudservices gemaakt.
1. Navigeren naar **Gereedschappen** ![hamer](assets/hammer.png) > **Cloud Services** > **Acrobat Sign** en selecteert u de configuratiecontainer die u in de bovenstaande stap hebt gemaakt.

   >[!NOTE]
   >
   >U kunt de stappen 1-4 uitvoeren om een nieuwe configuratiecontainer te maken en een Acrobat Sign-configuratie in de container te maken of de bestaande `global` map in **Gereedschappen** ![hamer](assets/hammer.png) > **Cloud Services** > **Acrobat Sign**. Als u de configuratie in de nieuwe configuratiecontainer creeert, zorg ervoor om de containernaam in te specificeren **[!UICONTROL Configuration Container]** wanneer u een adaptief formulier maakt.

   >[!NOTE]
   Zorg ervoor dat de URL van de configuratiepagina voor cloudservices begint met **HTTPS**. Zo niet, [SSL inschakelen](/help/sites-administering/ssl-by-default.md) voor AEM Forms-server.

1. Tik op de configuratiepagina op **[!UICONTROL Create]** om Acrobat Sign-configuratie te maken in AEM Forms.
1. In de **[!UICONTROL General]** tabblad van het dialoogvenster **[!UICONTROL Create Acrobat Sign Configuration]** pagina, geeft u een **Naam** voor de configuratie en tikken **Volgende**. U kunt desgewenst een titel opgeven en naar een miniatuur voor de configuratie bladeren.

1. Kopieer de URL in het huidige browservenster naar een laptop. Het is vereist om Acrobat Sign-toepassing te configureren met AEM Forms.

1. Configureer OAuth-instellingen voor de Acrobat Sign-toepassing:

   1. Open een browservenster en meld u aan bij de Acrobat Sign-ontwikkelaarsaccount.
   1. Selecteer de toepassing die voor AEM Forms is geconfigureerd en tik op OAuth configureren voor toepassing.
   1. In de **URL omleiden** voegt u de HTTPS-URL toe die u in de vorige stap hebt gekopieerd en klikt u op **Opslaan**.
   1. Schakel de volgende OAuth-instellingen voor de Acrobat Sign-toepassing in en klik op **Opslaan**.
   * samenvoeging_read
   * samenvoeging_write
   * aggregatie_verzenden
   * widget_write
   * workflow_read

   Voor geleidelijke informatie om montages OAuth voor een toepassing van Acrobat Sign te vormen en de sleutels te verkrijgen, zie [Auteursinstellingen voor de toepassing configureren](https://www.adobe.io/apis/documentcloud/sign/docs.html#!adobedocs/adobe-sign/master/gstarted/configure_oauth.md) ontwikkelaarsdocumentatie.

   ![OAuth Config](assets/oauthconfig_new.png)

1. Ga terug naar de **Acrobat Sign-configuratie maken** pagina. In de **[!UICONTROL Settings]** de **[!UICONTROL OAuth URL]** in field wordt de volgende standaard-URL vermeld:

   `https://secure.na1.echosign.com/public/oauth`

   waarbij:

   **nl1** verwijst naar de standaard databasedeelt.

   U kunt de waarde voor het delen van de database wijzigen. Start de server opnieuw om de nieuwe waarde voor de databaseschijf te kunnen gebruiken.

1. Geef de **Client-id** (ook toepassings-id genoemd) en **Clientgeheim**. Selecteer **Acrobat Sign ook inschakelen voor bijlagen** om bestanden die zijn gekoppeld aan een adaptief formulier, toe te voegen aan het corresponderende Acrobat Sign-document dat ter ondertekening is verzonden.

   Tik op **[!UICONTROL Connect to Acrobat Sign]**. Geef bij de aanwijzing voor referenties de gebruikersnaam en het wachtwoord op van het account dat wordt gebruikt bij het maken van een Acrobat Sign-toepassing.

   Tikken **[!UICONTROL Create]** om de Acrobat Sign-configuratie te maken.

1. Open AEM webconsole. De URL is `https://'[server]:[port]'/system/console/configMgr`
1. Openen **Forms Common Configuration Service.**
1. In de **Toestaan** veld, **selecteren** Alle gebruikers - Alle gebruikers, anoniem of aangemeld, kunnen een voorbeeld van bijlagen bekijken, formulieren verifiëren en ondertekenen en op **Opslaan.** Author-instantie is geconfigureerd voor gebruik van Acrobat Sign.
1. Gebruiken [replicatie](/help/sites-deploying/replication.md) om identieke configuratie op overeenkomstige te creëren publiceer instanties.

Acrobat Sign is nu geïntegreerd met AEM Forms en klaar voor gebruik in adaptieve formulieren. Naar [Acrobat Sign-service in een adaptieve vorm gebruiken](../../forms/using/working-with-adobe-sign.md#configure-adobe-sign-for-an-adaptive-form), geeft u de hierboven gemaakte configuratiecontainer op in adaptieve formuliereigenschappen.

## Acrobat Sign-planner configureren om de ondertekeningsstatus te synchroniseren {#configure-adobe-sign-scheduler-to-sync-the-signing-status}

Een adaptief formulier dat geschikt is voor Acrobat Sign wordt alleen verzonden nadat alle ondertekenaars het ondertekeningsproces hebben voltooid. Standaard is de Acrobat Sign Scheduler-service gepland om na elke 24 uur de respons van de ondertekenaar van de (opiniepeiling)gegevens te controleren. U kunt het standaardinterval voor uw milieu veranderen. Voer de volgende stappen uit om het standaardinterval te wijzigen:

1. Meld u aan bij de AEM Forms-server met beheerdersreferenties en navigeer naar **Gereedschappen** > **Bewerkingen** > **Webconsole**.

   U kunt ook de volgende URL openen in een browservenster:
   `https://[localhost]:'port'/system/console/configMgr`

1. Zoek en open de **Acrobat Sign Configuration Service** optie. Geef een [uitsnijdexpressie](https://en.wikipedia.org/wiki/Cron#CRON_expression) in de **Uitdrukking voor statusupdate van planner** veld en klik op **Opslaan**. Bijvoorbeeld, om de configuratieservice dagelijks bij 00:00 am in werking te stellen, specificeer `0 0 0 1/1 * ? *` in de **Uitdrukking voor statusupdate van planner** veld.

Het standaardinterval voor het synchroniseren van de status van Acrobat Sign is nu gewijzigd.

## Verwante artikelen {#related-articles}

* [Acrobat Sign in een adaptieve vorm gebruiken](../../forms/using/working-with-adobe-sign.md)
* [Acrobat Sign gebruiken met AEM Forms (video)](https://helpx.adobe.com/experience-manager/kt/forms/using/adobe-sign-integration-feature-video.html)
* [Acrobat Sign integreren met AEM Forms](../../forms/using/adobe-sign-integration-adaptive-forms.md)
