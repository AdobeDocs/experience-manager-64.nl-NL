---
title: Vereisten voor integratie met Adobe Target
seo-title: Vereisten voor integratie met Adobe Target
description: Lees meer over de voorwaarden voor integratie met Adobe Target.
seo-description: Lees meer over de voorwaarden voor integratie met Adobe Target.
uuid: 88be6a97-c964-4e42-a3a2-ed9b2c9ee49e
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: a84fd0ab-0bcd-48cf-bba3-fb29308fa0f8
translation-type: tm+mt
source-git-commit: 501a6c470113d249646f4424a19ee215a82b032d
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 0%

---


# Vereisten voor integratie met Adobe Target{#prerequisites-for-integrating-with-adobe-target}

Als deel van de [integratie van AEM en Adobe Target](/help/sites-administering/target.md), moet u bij Adobe Target registreren, de replicatieagent, en veilige activiteitenmontages op publiceren knoop vormen.

## Registreren bij Adobe Target {#registering-with-adobe-target}

Als u AEM wilt integreren met Adobe Target, hebt u een geldig Adobe Target-account nodig. Deze account moet minimaal **fiatteur **level rechten hebben. Wanneer u zich bij Adobe Target registreert, ontvangt u een clientcode. U hebt de clientcode en uw Adobe Target-aanmeldingsnaam en -wachtwoord nodig om verbinding te maken AEM met Adobe Target.

De clientcode identificeert de Adobe Target-klantenaccount wanneer de Adobe Target-server wordt aangeroepen.

>[!NOTE]
>
>Uw account moet ook door het Target-team zijn ingeschakeld om de integratie te kunnen gebruiken.
>
>
>Neem contact op met de klantenservice [van](https://docs.adobe.com/content/help/en/target/using/cmp-resources-and-contact-information.html)Adobe Target als dit niet het geval is.

## Toelatend de Agent van de Replicatie van het Doel {#enabling-the-target-replication-agent}

De test en de [replicatieagent](/help/sites-deploying/replication.md) van het Doel moet op de auteursinstantie worden toegelaten. Merk op dat deze replicatieagent niet door gebrek wordt toegelaten als u de [nosamplcontent](/help/sites-deploying/configure-runmodes.md#using-samplecontent-and-nosamplecontent) looppas wijze voor het installeren van AEM gebruikte. Raadpleeg de lijst [Beveiligingscontrole](/help/sites-administering/security-checklist.md)voor meer informatie over het beveiligen van uw productieomgeving.

1. Klik of tik op **Gereedschappen** > **Implementatie** > **Replicatie** op de introductiepagina AEM.
1. Klik of tik **Agenten op Auteur**.
1. Klik of tik de **Test en (test en doel)** replicatieagent van het Doel, en klik of tik dan **uitgeven**.
1. Selecteer de optie Ingeschakeld en klik of tik op **OK**.

   >[!NOTE]
   >
   >Wanneer u de de replicatieagent van de Test en van het Doel vormt, op het lusje van het **Vervoer** , wordt URI geplaatst door gebrek aan **tnt:///**. Vervang deze URI niet door **https://admin.testandtarget.omniture.com**.
   >
   >Houd er rekening mee dat als u de verbinding probeert te testen met **tnt:///**, dit een fout veroorzaakt. Dit wordt verwacht aangezien dit URI voor intern gebruik slechts is en niet met de Verbinding **van de** Test zou moeten worden gebruikt.

## Het knooppunt Activiteitsinstellingen beveiligen {#securing-the-activity-settings-node}

U moet het knooppunt activity settings (activity settings) **cq:ActivitySettings** op de publicatie-instantie beveiligen, zodat dit niet toegankelijk is voor normale gebruikers. Het knooppunt activity settings mag alleen toegankelijk zijn voor de service die de activiteitensynchronisatie afhandelt voor Adobe Target.

Het knooppunt **cq:ActivitySettings** is beschikbaar in de CRXDE-lijst onder `/content/campaigns/*nameofbrand*`* *onder het knooppunt activities jcr:content.* *bijvoorbeeld `/content/campaign/we-retail/master/myactivity/jcr:content/cq:ActivitySettings`. Dit knooppunt wordt alleen gemaakt nadat u een component als doel hebt ingesteld.

De **cq:ActivitySettings** knoop onder jcr van de activiteit:inhoud wordt beschermd door volgende ACLs:

* Alles weigeren voor iedereen
* jcr:read,rep:write toestaan voor &#39;target-activity-authors&#39; (de auteur is lid van deze groep uit de doos)
* jcr:read,rep:write voor &quot;targetService&quot; toestaan

Met deze instellingen zorgt u ervoor dat normale gebruikers geen toegang hebben tot de knoopeigenschappen. Gebruik zelfde ACLs op auteur en bij publiceren. Zie [Gebruikersbeheer en Beveiliging](/help/sites-administering/security.md) voor meer informatie.

## De AEM externalizer configureren {#configuring-the-aem-externalizer}

Wanneer u een activiteit bewerkt in Adobe Target, verwijst de URL naar de **localhost** , tenzij u de URL wijzigt op het AEM auteurknooppunt.

De AEM-externalizer configureren:

1. Navigeer naar de OSGi-webconsole op **https://&lt;server>:&lt;port>/system/console/configMgr.**
1. Zoek **de Verbinding Externalzer** van CQ van de Dag en ga het domein voor de auteursknoop in.

   ![chlimage_1-120](assets/chlimage_1-120.png)

