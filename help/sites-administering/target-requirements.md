---
title: Vereisten voor integratie met Adobe Target
seo-title: Prerequisites for Integrating with Adobe Target
description: Lees meer over de voorwaarden voor integratie met Adobe Target.
seo-description: Find out about the prerequisites for integrating with Adobe Target.
uuid: 88be6a97-c964-4e42-a3a2-ed9b2c9ee49e
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: a84fd0ab-0bcd-48cf-bba3-fb29308fa0f8
exl-id: f47e5c6a-ed52-4493-83bd-73e5e693d117
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 0%

---

# Vereisten voor integratie met Adobe Target{#prerequisites-for-integrating-with-adobe-target}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Als onderdeel van het [integratie van AEM en Adobe Target](/help/sites-administering/target.md), moet u bij Adobe Target registreren, de replicatieagent vormen, en activiteitenmontages op het publicatieknooppunt beveiligen.

## Registreren bij Adobe Target {#registering-with-adobe-target}

Als u AEM wilt integreren met Adobe Target, hebt u een geldig Adobe Target-account nodig. Deze account moet minimaal **fiatteur **level rechten hebben. Wanneer u zich bij Adobe Target registreert, ontvangt u een clientcode. U hebt de clientcode en uw Adobe Target-aanmeldingsnaam en -wachtwoord nodig om verbinding te maken AEM met Adobe Target.

De clientcode identificeert de Adobe Target-klantenaccount wanneer de Adobe Target-server wordt aangeroepen.

>[!NOTE]
>
>Uw account moet ook door het Target-team zijn ingeschakeld om de integratie te kunnen gebruiken.
>
>
>Als dit niet het geval is, kunt u contact opnemen met [Adobe Target Klantenservice](https://experienceleague.adobe.com/docs/target/using/cmp-resources-and-contact-information.html).

## Toelatend de Agent van de Replicatie van het Doel {#enabling-the-target-replication-agent}

Test en doel [replicatieagent](/help/sites-deploying/replication.md) moet zijn ingeschakeld op de instantie van de auteur. Merk op dat deze replicatieagent niet door gebrek wordt toegelaten als u gebruikte [nosamplcontent](/help/sites-deploying/configure-runmodes.md#using-samplecontent-and-nosamplecontent) uitvoeringsmodus voor het installeren van AEM. Voor meer informatie over het beveiligen van uw productieomgeving raadpleegt u de [Beveiligingscontrolelijst](/help/sites-administering/security-checklist.md).

1. Klik of tik op de AEM startpagina **Gereedschappen** > **Implementatie** > **Replicatie**.
1. Klikken of tikken **Medewerkers op auteur**.
1. Klik of tik op **Test en doel (test en doel)** replicatieagent, en dan klikken of tikken **Bewerken**.
1. Selecteer de optie Ingeschakeld en klik of tik op **OK**.

   >[!NOTE]
   >
   >Wanneer u de Test en de replicatieagent van het Doel vormt, in **Vervoer** tab, de URI is standaard ingesteld op **tnt:///**. Deze URI niet vervangen door **https://admin.testandtarget.omniture.com**.
   >
   >Houd er rekening mee dat als u de verbinding probeert te testen met **tnt:///**, wordt een fout gegenereerd. Dit wordt verwacht omdat deze URI alleen voor intern gebruik is en niet mag worden gebruikt **Verbinding testen**.

## Het knooppunt Activiteitsinstellingen beveiligen {#securing-the-activity-settings-node}

U moet het knooppunt met activiteiteninstellingen beveiligen **cq:ActivitySettings** op de publicatie-instantie zodat deze niet toegankelijk is voor normale gebruikers. Het knooppunt activity settings mag alleen toegankelijk zijn voor de service die de activiteitensynchronisatie afhandelt voor Adobe Target.

De **cq:ActivitySettings** knooppunt beschikbaar in CRXDE-lijst onder `/content/campaigns/*nameofbrand*`* *onder de activiteiten jcr:content node;* *bijvoorbeeld `/content/campaign/we-retail/master/myactivity/jcr:content/cq:ActivitySettings`. Dit knooppunt wordt alleen gemaakt nadat u een component als doel hebt ingesteld.

De **cq:ActivitySettings** knoop onder jcr van de activiteit:inhoud wordt beschermd door volgende ACLs:

* Alles weigeren voor iedereen
* jcr:read,rep:write toestaan voor &#39;target-activity-authors&#39; (de auteur is lid van deze groep uit de doos)
* jcr:read,rep:write voor &quot;targetService&quot; toestaan

Met deze instellingen zorgt u ervoor dat normale gebruikers geen toegang hebben tot de knoopeigenschappen. Gebruik zelfde ACLs op auteur en bij publiceren. Zie [Gebruikersbeheer en beveiliging](/help/sites-administering/security.md) voor meer informatie .

## De AEM externalizer configureren {#configuring-the-aem-externalizer}

Wanneer u een activiteit bewerkt in Adobe Target, verwijst de URL naar **localhost** tenzij u de URL wijzigt in het AEM auteurknooppunt.

De AEM-externalizer configureren:

1. Navigeer naar de OSGi-webconsole op **https://&lt;server>:&lt;port>/system/console/configMgr.**
1. Zoeken **Day CQ Link ExternalAlizer** en voer het domein voor het auteurknooppunt in.

   ![chlimage_1-120](assets/chlimage_1-120.png)
