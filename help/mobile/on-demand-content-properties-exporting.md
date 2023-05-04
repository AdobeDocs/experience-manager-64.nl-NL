---
title: Inhoud-eigenschappen gebruiken om inhoud te exporteren
seo-title: Using Content Properties to Export Content
description: Op de volgende pagina worden App-eigenschappen en -knooppunten weergegeven.
seo-description: The following page shows App Properties and Nodes.
uuid: 73f1832f-e457-47d0-a0e1-80af90897d31
contentOwner: User
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/MOBILE
topic-tags: developing-on-demand-services-app
discoiquuid: a3006835-b1d2-47d6-959a-cdb692e34e1e
exl-id: 27aa405d-2388-4f91-85d0-1a8709e0d5d0
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---

# Inhoud-eigenschappen gebruiken om inhoud te exporteren{#using-content-properties-to-export-content}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

>[!NOTE]
>
>Adobe raadt aan de SPA Editor te gebruiken voor projecten die renderen op basis van één pagina voor toepassingsframework op de client-side vereisen (bijvoorbeeld Reageren). [Meer informatie](/help/sites-developing/spa-overview.md).

Apps worden weergegeven als *cq:pagina&#39;s* in AEM.

Ze delen dezelfde gemeenschappelijke eigenschappen die in *cq:pagina* naast de hieronder getoonde andere die integratie ondersteunende eigenschappen vertegenwoordigen.

## App-eigenschappen {#app-properties}

De volgende tabel toont **Eigenschappen en knooppunten van app**.

<table>
 <tbody>
  <tr>
   <td><strong>PropertyName</strong></td>
   <td><strong>Type</strong></td>
   <td><strong>Beschrijving</strong></td>
  </tr>
  <tr>
   <td>dps-cloudConfig</td>
   <td>String:Path</td>
   <td><p>Pad naar een geconfigureerde Mobile On-Demand Cloud Service. Wordt gebruikt voor acties van AEM Mobile naar Mobile On-Demand (API-aanroep)</p> <p>Deze koppeling wordt geconfigureerd via de tegel Verbinding beheren wanneer een auteur een Cloud Service Mobiel op aanvraag kiest om de app aan te koppelen.</p> </td>
  </tr>
  <tr>
   <td>dps-exportTemplate</td>
   <td>String:Path</td>
   <td><p>Pad naar de exportconfiguraties van de app. De exportconfiguratie is een map met 2 onderliggende ContentSync-exportconfiguratiesjablonen;</p> <p><i>dps-artikel</i>: ContentSync exportconfiguratie om artikelinhoud te exporteren</p> <p><i>dps-HTMLResources</i>: ContentSync exportconfiguratie voor het exporteren van gedeelde app/artikel-bronnen</p> </td>
  </tr>
  <tr>
   <td>dps-projectId</td>
   <td>String</td>
   <td><p>Id/URI van het Mobile On-Demand-project waaraan deze app is gekoppeld of gekoppeld.</p> <p>Deze vereniging wordt gevormd via de Manage tegel van de Verbinding wanneer een auteur het project van een lijst van beschikbare projecten voor de bijbehorende Mobiele Cloud Service On-Demand kiest.</p> </td>
  </tr>
  <tr>
   <td>dps-projectTitle</td>
   <td>String</td>
   <td>App-titel.</td>
  </tr>
  <tr>
   <td>dps-resourceType</td>
   <td>String</td>
   <td>Inhoudstype.</td>
  </tr>
  <tr>
   <td>dps-sharedHTMLResources-lastUploaded</td>
   <td>Datum</td>
   <td>Datum van laatste upload van gedeelde bronnen van AEM naar AEM Mobile.</td>
  </tr>
  <tr>
   <td>dps-sharedHTMLResources-lastUploadedBy</td>
   <td>String:userid</td>
   <td>Id van de gebruiker die het laatste uploaden van een verzoek om gedeelde bronnen van AEM naar AEM Mobile heeft uitgevoerd.</td>
  </tr>
  <tr>
   <td>pge-dashboard-config</td>
   <td>String:Path</td>
   <td>Pad naar een dashboardconfiguratie. Het pad kan zo nodig worden omgeleid naar een aangepaste dashbaord-configuratie.</td>
  </tr>
  <tr>
   <td>sling:resourceType</td>
   <td>String:Path</td>
   <td><p>Pad naar cq:Component die is of is uitgebreid <i>mobiele apps/core/components/instance.</i></p> <p>Dit biedt de aanwezigheid en rendering in de Apps Catalog.</p> </td>
  </tr>
 </tbody>
</table>

U kunt ***Eigenschappen van inhoud*** om inhoud te maken. Zie de volgende bronnen voor het maken en exporteren van artikelen en gedeelde bronnen:

* [Eigenschappen van inhoud](/help/mobile/content-properties.md)
* [Artikel-exportconfiguratie maken](/help/mobile/creating-article-export-configuration.md)
* [Configuratie voor gedeelde bronnen exporteren](/help/mobile/creating-shared-resources-export-configuration.md)
