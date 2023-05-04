---
title: HTML5-serviceproxy voor formulieren
seo-title: HTML5 forms service proxy
description: De Proxy van de Dienst van HTML5 vormen is een configuratie om een volmacht voor de voorleggingsdienst te registreren. Om de Volmacht van de Dienst te vormen, specificeer URL van de voorleggingsdienst door request parameter submissionServiceProxy.
seo-description: HTML5 forms Service Proxy is a configuration to register a proxy for the submission service. To configure Service Proxy, specify the URL of submission service through request parameter submissionServiceProxy.
uuid: 03ee7dea-d23e-4600-8b0a-698f4530b889
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: 2791c9a1-38a2-4154-8bea-2f7c564b46c8
feature: Mobile Forms
exl-id: 42da25de-7ad0-4e9a-8139-149954f9bd8e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 0%

---

# HTML5-serviceproxy voor formulieren {#html-forms-service-proxy}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

De Proxy van de Dienst van HTML5 vormen is een configuratie om een volmacht voor de voorleggingsdienst te registreren. Om de Volmacht van de Dienst te vormen, specificeer URL van de voorleggingsdienst door verzoekparameter *submissionServiceProxy*.

## Voordelen van de Volmacht van de Dienst {#benefits-of-service-proxy-br}

De serviceproxy verwijdert het volgende:

* Voor de workflow voor HTML5-formulieren moet de verzendservice &quot;/content/xfaforms/submission/default&quot; worden geopend voor gebruikers van HTML-5-formulieren. Het stelt AEM servers aan een breder onbedoeld publiek bloot.
* De service-URL is ingesloten in het runtimemodel van het formulier. Het is niet mogelijk om dienstURL weg te veranderen.
* De verzending bestaat uit twee stappen. Voor het verzenden van de formuliergegevens zijn ten minste twee ritten naar de server vereist. Hierdoor wordt de belasting op de server verhoogd.
* HTML5-formulieren verzenden gegevens in de aanvraag van de POST in plaats van PDF. Voor werkstromen waarbij zowel PDF- als HTML5-formulieren worden gebruikt, zijn twee verschillende verwerkingsmethoden vereist.

## Topologieën {#topologies-br}

HTML5 vormen kunnen volgende topologieën gebruiken om met de AEM servers te verbinden.

* Een topologie waar AEM Server of HTML5 vormen gegevens via POST naar de server verzenden.
* Een topologie waar de volmachtsserver de gegevens van de POST naar de server verzendt.

![HTML5 de volmachtstopologieën van de vormendienst](assets/topology.png)

HTML5 de volmachtstopologieën van de vormendienst

HTML5-formulieren maken verbinding met de AEM servers om serverscripts, webservices en verzendingen uit te voeren. De XFA-runtime van de HTML5-formulieren gebruikt Ajax-aanroepen van het eindpunt &quot;/bin/xfaforms/submit&quot; met verschillende parameters om verbinding te maken met de AEM. HTML5-formulieren verbinden AEM servers om de volgende bewerkingen uit te voeren:

### Voer Server-zijdig manuscripten en de Diensten van het Web uit {#execute-server-sided-scripts-and-web-services}

De scripts die zijn gemarkeerd om op de server te worden uitgevoerd, worden serverscripts genoemd. De volgende lijst maakt een lijst van alle parameters die in Server-zijde manuscripten en de Diensten van het Web worden gebruikt.

<table> 
 <tbody> 
  <tr> 
   <td><p><strong>Parameter</strong></p> </td> 
   <td><p><strong>Beschrijving</strong></p> </td> 
  </tr> 
  <tr> 
   <td><p>activiteit</p> </td> 
   <td><p>De activiteit bevat de gebeurtenissen die het verzoek teweegbrengen. Bijvoorbeeld klikken, afsluiten of wijzigen</p> </td> 
  </tr> 
  <tr> 
   <td><p>contextSom</p> </td> 
   <td><p>contextSom bevat SOM-expressie van het object waar gebeurtenissen worden uitgevoerd.</p> </td> 
  </tr> 
  <tr> 
   <td><p>Sjabloon</p> </td> 
   <td><p>De sjabloon bevat de sjabloon die wordt gebruikt om het formulier te genereren.</p> </td> 
  </tr> 
  <tr> 
   <td><p>contentRoot</p> </td> 
   <td><p>contentRoot bevat de hoofdmap van de sjabloon die wordt gebruikt om het formulier weer te geven.</p> </td> 
  </tr> 
  <tr> 
   <td><p>Gegevens</p> </td> 
   <td><p>Gegevens bevatten batchbytes die worden gebruikt om het formulier te genereren.</p> </td> 
  </tr> 
  <tr> 
   <td><p>formDom</p> </td> 
   <td><p>formDom bevat DOM van het HTML5-formulier in JSON-indeling.</p> </td> 
  </tr> 
  <tr> 
   <td><p>packet</p> </td> 
   <td><p>Het pakket wordt als formulier opgegeven.</p> </td> 
  </tr> 
  <tr> 
   <td><p>debugDir</p> </td> 
   <td><p>debugDir bevat de map voor foutopsporing die wordt gebruikt om het formulier te genereren.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Gegevens verzenden {#submit-data}

Als u op de knop Verzenden klikt, sturen HTML5-formulieren gegevens naar de server. De volgende tabel bevat een lijst met alle parameters die HTML5-formulieren naar de server verzenden.

<table> 
 <tbody> 
  <tr> 
   <td><p><strong>Parameter</strong></p> </td> 
   <td><p><strong>Beschrijving</strong></p> </td> 
  </tr> 
  <tr> 
   <td><p>Sjabloon</p> </td> 
   <td><p>Sjabloon waarmee het formulier wordt gegenereerd.</p> </td> 
  </tr> 
  <tr> 
   <td><p>contentRoot</p> </td> 
   <td><p>de hoofdmap van de sjabloon die wordt gebruikt om het formulier te genereren.</p> </td> 
  </tr> 
  <tr> 
   <td><p>Gegevens</p> </td> 
   <td><p>batchbytes die worden gebruikt om het formulier weer te geven.</p> </td> 
  </tr> 
  <tr> 
   <td><p>formDom</p> </td> 
   <td><p>DOM van het HTML5-formulier in JSON-indeling.</p> </td> 
  </tr> 
  <tr> 
   <td><p>voorlegger</p> </td> 
   <td><p>De URL waar de gegevens-XML wordt gepost.</p> </td> 
  </tr> 
  <tr> 
   <td><p>debugDir</p> </td> 
   <td><p>De map voor foutopsporing die wordt gebruikt om het formulier te genereren.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Hoe werkt de verzendproxy? {#how-nbsp-the-nbsp-submit-proxy-works}

De verzendserviceproxy fungeert als een pass through als de verzender niet aanwezig is in de parameter request. Het fungeert als een doorbraak. Het verzendt het verzoek naar het /bin/xfaforms/submitAction eindpunt en verzendt de reactie naar XFA runtime.

De voorgelegde de dienstvolmacht selecteert een topologie als voorlegger in de verzoekparameter aanwezig is.

* Als AEM servers de gegevens posten, dienst van de volmacht als ervaart. Het verzendt het verzoek naar het /bin/xfaforms/submitAction eindpunt en verzendt de reactie naar XFA runtime.
* Als de volmacht de gegevens post, gaat de volmachtsdienst alle parameters behalve submitUrl tot over */bin/xfaforms/submit* eindpunt en ontvangt xml bytes in response stream. Dan, post de volmachtsdienst de gegevens xml bytes aan submitUrl voor verwerking.

* Voordat u gegevens (verzoek om POST) naar een server verzendt, controleren HTML5-formulieren de connectiviteit en beschikbaarheid van de server. Om connectiviteit en beschikbaarheid te verifiëren, verzenden de vormen van HTML een leeg hoofdverzoek naar de server. Als de server beschikbaar is, verzendt het formulier HTML5 gegevens (verzoek van de POST) naar de server. Als de server niet beschikbaar is, een foutbericht *Kan geen verbinding maken met de server.* wordt weergegeven. De detectie vooraf voorkomt dat gebruikers het formulier kunnen bijvullen. De volmachtsservlet behandelt hoofdverzoek en werpen geen uitzondering.
