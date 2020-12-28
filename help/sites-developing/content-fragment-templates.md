---
title: Sjablonen voor inhoudsfragmenten
seo-title: Sjablonen voor inhoudsfragmenten
description: Sjablonen worden geselecteerd wanneer u een inhoudsfragment maakt en bieden het nieuwe fragment de basisstructuur, het basiselement en de variatie
seo-description: Sjablonen worden geselecteerd wanneer u een inhoudsfragment maakt en bieden het nieuwe fragment de basisstructuur, het basiselement en de variatie
uuid: 74675e82-26b4-4105-8031-21de51131236
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 8c399a27-abdb-41fb-bd76-f30d22f1d68f
translation-type: tm+mt
source-git-commit: 0e1dc3ea47f03cd2e0cbeb2bf98eeec9ccc5d64f
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 4%

---


# Sjablonen voor inhoudsfragmenten{#content-fragment-templates}

>[!CAUTION]
>
>Voor bepaalde functionaliteit van contentfragment is de toepassing van [AEM 6.4 Service Pack 2 (6.4.2.0)](/help/release-notes/sp-release-notes.md) vereist.

>[!CAUTION]
>
>[Het wordt nu ](/help/assets/content-fragments-models.md) aanbevolen om al uw fragmenten te maken.
>
>De fragmentmodellen van de inhoud worden gebruikt voor alle voorbeelden in Wij.Retail.

Sjablonen worden geselecteerd wanneer u een inhoudsfragment maakt. Ze bieden het nieuwe fragment de basisstructuur, elementen en variatie. De sjablonen die voor inhoudsfragmenten worden gebruikt, zijn afhankelijk van de Granite Configuration Manager.

De out-of-the-box sjablonen worden bewaard onder:

* `/libs/settings/dam/cfm/templates`

U kunt uw sitespecifieke sjablonen voor inhoudsfragmenten maken onder:

* `/apps/settings/dam/cfm/templates`

   De locatie voor het bedekken van out-of-the-box sjablonen of het aanbieden van klantspecifieke, toepassingsbrede sjablonen die niet bedoeld zijn om tijdens runtime te worden uitgebreid/gewijzigd.

* `/conf/global/settings/dam/cfm/templates`

   De locatie voor klantspecifieke sjablonen die voor de hele organisatie moeten worden gewijzigd tijdens runtime.

De rangorde is (in aflopende volgorde) `/conf`, `/apps`, `/libs`.

>[!CAUTION]
>
>U ***must*** verandert niets in `/libs` weg.
>
>Dit komt doordat de inhoud van `/libs` de volgende keer wordt overschreven dat u uw exemplaar bijwerkt (en dat kan worden overschreven wanneer u een hotfix- of functiepakket toepast).
>
>De aanbevolen methode voor configuratie en andere wijzigingen is:
>
>1. Het vereiste item opnieuw maken (dat wil zeggen zoals het bestaat in `/libs`) onder `/apps`
   >
   >
1. Wijzigingen aanbrengen binnen `/apps`

>



De basisstructuur van een template wordt aangehouden onder:

```xml
conf
  global
    settings
      dam
        cfm
          templates
            <template-name>
              ...
```

Met de specifieke structuur:

```xml
+ <template-name>
    - jcr:primaryType
    - jcr:title
    - jcr:description
    - initialAssociatedContent
    - precreateElements
    - version 
    + elements
        - jcr:primaryType
        + <element-name>
            - jcr:primaryType
            - jcr:title 
            - defaultContent 
            - initialContentType 
            - name 
        ... + other element definitions
    + variations
        - jcr:primaryType 
        + <variation-name>
            - jcr:primaryType 
            - jcr:title 
            - jcr:description
            - name 
        ... + other variation definitions 
```

Meer details over de knopen en hun eigenschappen zijn:

* **Sjabloonmodel**

<table> 
 <tbody> 
  <tr> 
   <th>Naam</th> 
   <th>Type</th> 
   <th>Waarde</th> 
  </tr> 
  <tr> 
   <td><code>&lt;<em>template-name</em>&gt;</code></td> 
   <td><code>nt:unstructured</code></td> 
   <td>Dit knooppunt is de basis voor elke sjabloon. Het is verplicht en moet een unieke naam hebben.</td> 
  </tr> 
  <tr> 
   <td><code>jcr:title</code></td> 
   <td><p><code>String</code></p> <p>required<br /> </p> </td> 
   <td>De titel van de sjabloon (weergegeven in de wizard <strong>Fragment maken</strong>).</td> 
  </tr> 
  <tr> 
   <td><code>jcr:description</code></td> 
   <td><p><code>String</code></p> <p>optioneel</p> </td> 
   <td>Een tekst die het doel van het malplaatje beschrijft (die in <strong>Create Fragment</strong> tovenaar wordt getoond).</td> 
  </tr> 
  <tr> 
   <td><code>initialAssociatedContent</code></td> 
   <td><p><code>String[]</code></p> <p>optioneel</p> </td> 
   <td>Een array met paden naar verzamelingen die standaard aan een nieuw gemaakt inhoudsfragment moeten worden gekoppeld.</td> 
  </tr> 
  <tr> 
   <td><code>precreateElements</code></td> 
   <td><p><code>Boolean</code></p> <p>required</p> </td> 
   <td><p><code>true</code>, als de subassets die de elementen (behalve het master element) van het inhoudsfragment vertegenwoordigen, moeten worden gemaakt wanneer het inhoudsfragment wordt gemaakt; <em>false</em> als deze 'ter plekke' moeten worden gemaakt.</p> <p><strong>Opmerking</strong>: momenteel moet deze parameter worden ingesteld op  <code>true</code>.</p> </td> 
  </tr> 
  <tr> 
   <td><code>version</code></td> 
   <td><p><code>Long</code></p> <p>vereist</p> </td> 
   <td><p>Versie van de inhoudsstructuur; momenteel ondersteund:</p> <p><strong>Opmerking</strong>: momenteel moet deze parameter worden ingesteld op  <code>2</code>.<br /> </p> </td> 
  </tr> 
 </tbody> 
</table>

* **Elementen**

<table> 
 <tbody> 
  <tr> 
   <th>Naam</th> 
   <th>Type</th> 
   <th>Waarde</th> 
  </tr> 
  <tr> 
   <td><code>elements</code> </td> 
   <td><p><code>nt:unstructured</code></p> <p>vereist</p> </td> 
   <td><p>Knooppunt dat de definitie van de elementen van het inhoudsfragment bevat. Het is verplicht en moet minstens één kindknoop voor het <strong>Hoofd</strong> element bevatten, maar kan [1.. bevatten.n] onderliggende knooppunten.</p> <p>Wanneer de sjabloon wordt gebruikt, wordt de elementensubvertakking gekopieerd naar de modelsubvertakking van het fragment.</p> <p>Het eerste element (zoals weergegeven in CRXDE Lite) wordt automatisch beschouwd als het <i>main</i>-element; de knooppuntnaam is irrelevant en het knooppunt zelf heeft geen speciale betekenis, afgezien van het feit dat het wordt vertegenwoordigd door het hoofdactief; de overige elementen worden behandeld als subactiva.</p> </td> 
  </tr> 
 </tbody> 
</table>

* **Elementnaam**

<table> 
 <tbody> 
  <tr> 
   <th>Naam</th> 
   <th>Type</th> 
   <th>Waarde</th> 
  </tr> 
  <tr> 
   <td><code>&lt;<i>element-name</i>&gt;</code></td> 
   <td><code>nt:unstructured</code></td> 
   <td>Dit knooppunt definieert een element. Het is verplicht en moet een unieke naam hebben.</td> 
  </tr> 
  <tr> 
   <td><code>jcr:title</code></td> 
   <td><p><code>String</code></p> <p>vereist</p> </td> 
   <td>De titel van het element (wordt weergegeven in de elementenkiezer van de fragmenteditor).</td> 
  </tr> 
  <tr> 
   <td><code>defaultContent</code></td> 
   <td><p><code>String</code></p> <p>optioneel</p> <p>default: ""</p> </td> 
   <td>de initiële inhoud van het element; alleen worden gebruikt als <code>precreateElements</code><i> = </i><code>true</code></td> 
  </tr> 
  <tr> 
   <td><code>initialContentType</code></td> 
   <td><p><code>String</code></p> <p>optioneel</p> <p>default: <code>text/html</code></p> </td> 
   <td><p>Eerste inhoudstype van het element; alleen worden gebruikt als <code>precreateElements</code><i> = </i><code>true</code>; momenteel ondersteund:</p> 
    <ul> 
     <li><code>text/html</code></li> 
     <li><code>text/plain</code></li> 
     <li><code>text/x-markdown</code></li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><code>name</code></td> 
   <td><p><code>String</code></p> <p>vereist</p> </td> 
   <td>De interne naam van het element; moet uniek zijn voor het fragmenttype.</td> 
  </tr> 
 </tbody> 
</table>

* **Variaties**

<table> 
 <tbody> 
  <tr> 
   <th>Naam</th> 
   <th>Type</th> 
   <th>Waarde</th> 
  </tr> 
  <tr> 
   <td><code>variations</code> </td> 
   <td><p><code>nt:unstructured</code></p> <p>optioneel</p> </td> 
   <td>Dit optionele knooppunt bevat de definitie van de initiële variaties van het inhoudsfragment.</td> 
  </tr> 
 </tbody> 
</table>

* **Naam variatie**

<table> 
 <tbody> 
  <tr> 
   <th>Naam</th> 
   <th>Type</th> 
   <th>Waarde</th> 
  </tr> 
  <tr> 
   <td><code>&lt;<i>variation-name</i>&gt;</code> </td> 
   <td><p><code>nt:unstructured</code></p> <p>vereist als er een variatieknooppunt aanwezig is</p> </td> 
   <td><p>Definieert een oorspronkelijke variatie.<br /> De variatie wordt standaard toegevoegd aan alle elementen van het inhoudsfragment.</p> <p>De variatie zal de zelfde aanvankelijke inhoud hebben zoals het respectieve element (zie <code class="code">defaultContent/
       initialContentType</code>)</p> </td> 
  </tr> 
  <tr> 
   <td><code>jcr:title</code></td> 
   <td><p><code>String</code></p> <p>vereist</p> </td> 
   <td>De titel van de variatie (weergegeven in de tab <strong>Variatie</strong> van de fragmenteditor (linkerrail)).</td> 
  </tr> 
  <tr> 
   <td><code>jcr:desciption</code></td> 
   <td><p><code>String</code></p> <p>optioneel</p> <p>standaard: ""</p> </td> 
   <td>Een tekst die een beschrijving van de variatie <span> (getoond in <strong>Variatie</strong> tabel (linkerspoor)).</span> verstrekt.</td> 
  </tr> 
 </tbody> 
</table>

