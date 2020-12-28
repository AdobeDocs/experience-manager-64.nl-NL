---
title: Sling Adapters
seo-title: Sling Adapters
description: Sling biedt een adapterpatroon om objecten die de Aanpasbare interface implementeren, gemakkelijk te vertalen
seo-description: Sling biedt een adapterpatroon om objecten die de Aanpasbare interface implementeren, gemakkelijk te vertalen
uuid: 07f66a33-072d-49e1-8e67-8b80a6a9072a
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: c081b242-67e4-4820-9bd3-7e4495df459e
translation-type: tm+mt
source-git-commit: 269facfb6351b0b7c73e963ac7c5dc0b57c78a3e
workflow-type: tm+mt
source-wordcount: '1747'
ht-degree: 0%

---


# Sling Adapters{#using-sling-adapters}

[](https://sling.apache.org) Slingaanbiedingen een  [adapterpatroon ](https://sling.apache.org/site/adapters.html) om voorwerpen gemakkelijk te vertalen die de  [](https://sling.apache.org/apidocs/sling5/org/apache/sling/api/adapter/Adaptable.html#adaptTo%28java.lang.Class%29) Adaptable interface uitvoeren. Deze interface biedt een algemene methode [adjustTo()](https://sling.apache.org/apidocs/sling5/org/apache/sling/api/adapter/Adaptable.html#adaptTo%28java.lang.Class%29) waarmee het object wordt omgezet in het klassetype dat als argument wordt doorgegeven.

Bijvoorbeeld om een voorwerp van het Middel aan het overeenkomstige voorwerp van de Knoop te vertalen, kunt u eenvoudig doen:

```java
Node node = resource.adaptTo(Node.class);
```

## Gevallen {#use-cases} gebruiken

Er zijn de volgende gebruiksgevallen:

* Hiermee krijgt u implementatiespecifieke objecten.

   Bijvoorbeeld, verleent een op JCR-Gebaseerde implementatie van generische [`Resource`](https://sling.apache.org/apidocs/sling5/org/apache/sling/api/resource/Resource.html) interface toegang tot onderliggende JCR [`Node`](https://docs.adobe.com/content/docs/en/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html).

* Het maken van sneltoetsen voor objecten waarvoor interne contextobjecten moeten worden doorgegeven.

   Bijvoorbeeld, op JCR-Gebaseerd [`ResourceResolver`](https://sling.apache.org/apidocs/sling5/org/apache/sling/api/resource/ResourceResolver.html) houdt een verwijzing naar [`JCR Session`](https://docs.adobe.com/content/docs/en/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Session.html) van het verzoek, die beurtelings voor vele voorwerpen nodig is die op die verzoekzitting gebaseerd zullen werken, zoals [`PageManager`](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/PageManager.html) of [`UserManager`](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/security/UserManager.html).

* Snelkoppeling naar services.

   Een zeldzaam geval - `sling.getService()` is ook eenvoudig.

### Null-retourwaarde {#null-return-value}

`adaptTo()` kan null retourneren.

Hiervoor zijn verschillende redenen, waaronder:

* de implementatie ondersteunt het doeltype niet
* een adapterfabriek die deze zaak afhandelt, is niet actief (bijv. vanwege ontbrekende serviceverwijzingen)
* interne voorwaarde is mislukt
* service is niet beschikbaar

Het is belangrijk dat u de null-case netjes afhandelt. Voor jsp-renderingen kan het acceptabel zijn dat de jsp mislukt als dat resulteert in een leeg stuk inhoud.

### {#caching}

Om prestaties te verbeteren, zijn de implementaties vrij om het voorwerp in het voorgeheugen onder te brengen dat van een `obj.adaptTo()` vraag is teruggekeerd. Als `obj` het zelfde is, is het teruggekeerde voorwerp het zelfde.

Deze caching wordt uitgevoerd voor alle `AdapterFactory` gebaseerde gevallen.

Er is echter geen algemene regel: het object kan een nieuw of een bestaand object zijn. Dit betekent dat u niet op één van beide gedrag kunt vertrouwen. Daarom is het belangrijk, vooral binnen `AdapterFactory`, dat de voorwerpen in dit scenario herbruikbaar zijn.

### Hoe werkt {#how-it-works}

Er zijn verschillende manieren waarop `Adaptable.adaptTo()` kan worden geïmplementeerd:

* door het object zelf; het implementeren van de methode zelf en het toewijzen aan bepaalde objecten.
* Met een [`AdapterFactory`](https://sling.apache.org/apidocs/sling5/org/apache/sling/api/adapter/AdapterFactory.html)`, dat willekeurige voorwerpen in kaart kan brengen.

   De objecten moeten nog steeds de `Adaptable`-interface implementeren en [`SlingAdaptable`](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/adapter/SlingAdaptable.html) uitbreiden (die de `adaptTo`-aanroep aan een centrale adapterbeheerder doorgeeft).

   Hierdoor kunnen koppelingen naar het `adaptTo`-mechanisme voor bestaande klassen worden gebruikt, zoals `Resource`.

* Een combinatie van beide.

In het eerste geval kunnen de javadocs aangeven wat `adaptTo-targets` mogelijk is. Voor specifieke subklassen zoals de op JCR gebaseerde Resource is dit echter vaak niet mogelijk. In het laatste geval maken implementaties van `AdapterFactory` doorgaans deel uit van de klassen van het type private van een bundel en worden ze dus niet weergegeven in een client-API, en worden ze niet vermeld in javadocs. Theoretisch, zou het mogelijk zijn om tot alle `AdapterFactory` implementaties van [OSGi](/help/sites-deploying/configuring-osgi.md) de dienstruntime toegang te hebben en hun &quot;adaptable&quot;(bronnen en doelstellingen) configuraties te bekijken, maar niet hen aan elkaar in kaart te brengen. Uiteindelijk hangt dit af van de interne logica, die moet worden gedocumenteerd. Vandaar deze verwijzing.

## Referentie {#reference}

### Verschuiven {#sling}

[**Bronnen worden**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.html) aangepast aan:

<table> 
 <tbody> 
  <tr> 
   <td><a href="https://docs.adobe.com/content/docs/en/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html">Knooppunt</a></td> 
   <td>Als dit een JCR-node-based resource is of een JCR-eigenschap die verwijst naar een knooppunt.</td> 
  </tr> 
  <tr> 
   <td><a href="https://docs.adobe.com/content/docs/en/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Property.html">Eigenschap</a></td> 
   <td>Als dit een op JCR-eigenschap gebaseerde bron is.</td> 
  </tr> 
  <tr> 
   <td><a href="https://docs.adobe.com/content/docs/en/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Item.html">Item</a></td> 
   <td>Als dit een op JCR gebaseerde bron (knooppunt of eigenschap) is.</td> 
  </tr> 
  <tr> 
   <td><a href="https://java.sun.com/j2se/1.5.0/docs/api//java/util/Map.html">Kaart</a></td> 
   <td>Keert een kaart van de eigenschappen terug, als dit een JCR-knoop-gebaseerd middel (of andere middel ondersteunend waardekaarten) is.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/ValueMap.html">ValueMap</a></td> 
   <td>Retourneert een handig te gebruiken kaart van de eigenschappen, als dit een JCR-node-based resource (of andere resource die waardekaarten ondersteunt) is. Kan ook (eenvoudigere) worden bereikt door <br /> <code><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/ResourceUtil.html#getvaluemap%28org.apache.sling.api.resource.resource%29">ResourceUtil.getValueMap(Resource)</a></code> (behandelt ongeldige geval, enz.) te gebruiken.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/inherit/InheritanceValueMap.html">InheritanceValueMap</a></td> 
   <td>Uitbreiding van <a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/ValueMap.html">ValueMap</a> waarmee de hiërarchie van bronnen kan worden gebruikt wanneer u eigenschappen zoekt.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/PersistableValueMap.html">PersistableValueMap</a></td> 
   <td>Als dit een JCR-node-based middel is en de gebruiker toestemmingen heeft om eigenschappen op die knoop te wijzigen.<br /> Opmerking: meerdere permanente kaarten delen hun waarden niet .</td> 
  </tr> 
  <tr> 
   <td><a href="https://java.sun.com/j2se/1.5.0/docs/api/java/io/InputStream.html">InputStream</a></td> 
   <td>Hiermee wordt de binaire inhoud van een "bestand" geretourneerd<code>nt:resource</code></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td><code>AuthorizableResourceProvider</code><code>org.apache.sling.jackrabbit.usermanager</code><code>/system/userManager</code></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td><code>cq:Page</code><code>cq:PseudoPage</code></td></tr><tr><td></td><td><code>cq:Component</code></td></tr><tr><td></td><td><code>cq:Page</code></td></tr><tr><td></td><td><code>cq:Template</code></td></tr><tr><td></td><td><code>cq:Page</code></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td><code>cq:Tag</code></td></tr><tr><td></td><td><code>cq:Preferences</code></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td></td></tr><tr><td></td><td><code>cq:ContentSyncConfig</code></td></tr><tr><td></td><td><code>cq:ContentSyncConfig</code></td></tr></tbody></table>

[****](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/ResourceResolver.html) ResourceResolveradapts aan:

<table> 
 <tbody> 
  <tr> 
   <td><a href="https://docs.adobe.com/content/docs/en/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Session.html">Sessie</a></td> 
   <td>De JCR-sessie van het verzoek, als dit een op JCR gebaseerde resourceoplosser is (standaardwaarde).</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/PageManager.html">PageManager</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/components/ComponentManager.html">ComponentManager</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/designer/Designer.html">Designer</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/dam/api/AssetManager.html">AssetManager</a></td> 
   <td>Gebaseerd op de zitting JCR, als dit op JCR-Gebaseerde middeloplosser is.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/tagging/TagManager.html">TagManager</a></td> 
   <td>Gebaseerd op de zitting JCR, als dit op JCR-Gebaseerde middeloplosser is.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/security/UserManager.html">UserManager</a></td> 
   <td>Gebaseerd op de zitting JCR, als dit op JCR-Gebaseerde middeloplosser is, en als de gebruiker toestemmingen heeft om tot UserManager toegang te hebben.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/jackrabbit/api/security/user/Authorizable.html">Toestemming</a> </td> 
   <td>De huidige gebruiker.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/jackrabbit/api/security/user/User.html">Gebruiker</a><br /> </td> 
   <td>De huidige gebruiker.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/security/privileges/PrivilegeManager.html">PrivilegeManager</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/preferences/Preferences.html">Voorkeuren</a></td> 
   <td>Voorkeuren van de huidige gebruiker (op basis van een JCR-sessie als dit een op JCR gebaseerde resourceoplosser is).</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/preferences/PreferencesService.html">PreferencesService</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/auth/pin/PinManager.html">PinManager</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/search/QueryBuilder.html">QueryBuilder</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/Externalizer.html">ExternalAlizer</a></td> 
   <td>Voor het externaliseren van absolute URLs, zelfs met uit het verzoekvoorwerp.<br /> </td> 
  </tr> 
 </tbody> 
</table>

[****](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/SlingHttpServletRequest.html) SlingHttpServletRequestadapts aan:

Geen doelstellingen nog, maar voert Aangepast uit en kon als bron in een douane AdapterFactory worden gebruikt.

[****](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/SlingHttpServletResponse.html) SlingHttpServletResponse past zich aan:

<table> 
 <tbody> 
  <tr> 
   <td><a href="https://java.sun.com/j2se/1.5.0/docs/api/org/xml/sax/ContentHandler.html">ContentHandler</a><br />  (XML)</td> 
   <td>Als dit een sling rewriter reactie is.</td> 
  </tr> 
 </tbody> 
</table>

#### WCM {#wcm}

[**Pagina&#39;s**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/Page.html) worden aangepast aan:

<table> 
 <tbody> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.html">Resource</a><br /> </td> 
   <td>Bron van de pagina.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/LabeledResource.html">LabeledResource</a></td> 
   <td>Gelabelde bron (== dit).</td> 
  </tr> 
  <tr> 
   <td><a href="https://docs.adobe.com/content/docs/en/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html">Knooppunt</a></td> 
   <td>Knooppunt van de pagina.</td> 
  </tr> 
  <tr> 
   <td>...</td> 
   <td>Alles waaraan de bron van de pagina kan worden aangepast.</td> 
  </tr> 
 </tbody> 
</table>

[****](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/components/Component.html) Componenten worden aangepast aan:

| [Resource](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.html) | Bron van de component. |
|---|---|
| [LabeledResource](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/LabeledResource.html) | Gelabelde bron (== dit). |
| [Knooppunt](https://docs.adobe.com/content/docs/en/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html) | Knooppunt van de component. |
| ... | Alles waaraan de bron van de component kan worden aangepast. |

[**Templateaanpassingen**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/Template.html) aan:

<table> 
 <tbody> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.html">Resource</a><a href="https://docs.adobe.com/content/docs/en/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html"><br /> </a></td> 
   <td>Bron van de sjabloon.</td> 
  </tr> 
  <tr> 
   <td><a href="https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/LabeledResource.html">LabeledResource</a></td> 
   <td>Gelabelde bron (== dit).</td> 
  </tr> 
  <tr> 
   <td><a href="https://docs.adobe.com/content/docs/en/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html">Knooppunt</a></td> 
   <td>Knooppunt van deze sjabloon.</td> 
  </tr> 
  <tr> 
   <td>...</td> 
   <td>Alles waaraan de bron van de sjabloon kan worden aangepast.</td> 
  </tr> 
 </tbody> 
</table>

#### Beveiliging {#security}

[**Toegestane**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/security/Authorizable.html),  [****](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/security/User.html) gebruikers en  [****](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/security/Group.html) groepen passen zich aan:

| [Knooppunt](https://docs.adobe.com/content/docs/en/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html) | Retourneert het thuisknooppunt van de gebruiker/groep. |
|---|---|
| [ReplicationStatus](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/replication/ReplicationStatus.html) | Retourneert de replicatiestatus voor het thuisknooppunt van de gebruiker/groep. |

#### DAM {#dam}

[**Elementen**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/dam/api/Asset.html) worden aangepast aan:

| [Resource](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.html) | Middelen van het actief. |
|---|---|
| [Knooppunt](https://docs.adobe.com/content/docs/en/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html) | Node of the asset. |
| ... | Alles waaraan de middelen van het actief kunnen worden aangepast. |

#### Tags {#tagging}

[**Tags**](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/tagging/Tag.html) aanpassen aan:

| [Resource](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.html) | Bron van de tag. |
|---|---|
| [Knooppunt](https://docs.adobe.com/content/docs/en/spec/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html) | Knooppunt van de tag. |
| ... | Alles waaraan de bron van de tag kan worden aangepast. |

#### Overig {#other}

Daarnaast biedt Sling / JCR / OCM ook een ` [AdapterFactory](https://sling.apache.org/site/adapters.html#Adapters-AdapterFactory)` voor aangepaste OCM-objecten ([Objectinhoudtoewijzing](https://jackrabbit.apache.org/object-content-mapping.html)).
