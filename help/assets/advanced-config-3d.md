---
title: Geavanceerde configuratie-instellingen
seo-title: Geavanceerde configuratie-instellingen
description: Leer over geavanceerde configuratiemontages die op de integratie van AEM 3D voor zowel Maya als niet-Maya plaatsingen van toepassing zijn.
seo-description: Leer over geavanceerde configuratiemontages die op de integratie van AEM 3D voor zowel Maya als niet-Maya plaatsingen van toepassing zijn.
uuid: 016e7745-e3c3-4d77-b95a-c0e671d719e2
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: e43fd002-2954-4ef1-ac2b-e8d45afa75be
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f
workflow-type: tm+mt
source-wordcount: '1334'
ht-degree: 0%

---


# Geavanceerde configuratie-instellingen {#advanced-configuration-settings}

Terwijl de standaardconfiguratiemontages voor typisch gebruiksgevallen aangewezen zijn, kunnen sommige situaties u vereisen om veranderingen aan te brengen.

De volgende geavanceerde configuratie-instellingen zijn van toepassing op de integratie van AEM 3D voor zowel Maya- als niet-Maya-implementaties.

Alle instellingen zijn toegankelijk via **CRXDE Lite** in AEM (**[!UICONTROL Tools > General > CRXDE Lite]**).

>[!NOTE]
>
>Als u het pakket opnieuw installeert, worden alle instellingen weer op de standaardwaarden ingesteld.

>[!CAUTION]
>
>Als u instellingen bewerkt die niet in de onderstaande tabel worden vermeld, kan dit leiden tot onverwachte of ongewenste programmagedragingen.

## Configuratie van elementtypen {#asset-types-configuration}

In **CRXDE Lite** in AEM (**[!UICONTROL Tools > General > CRXDE Lite]**), heb toegang tot de volgende configuraties:

| Pad | Beschrijving |
|---|---|
| `/libs/settings/dam/v3D/assetTypes/*/Conversion` | Hiermee geeft u het bestandstype op voor de tussentijdse 3D-indeling die tijdens de opname wordt gemaakt. Moet leeg zijn voor &#39;fbx&#39;- en &#39;obj&#39;-bestandsindelingen of &#39;fbx&#39; voor indelingen die door Maya zijn ingeschakeld. |
| `/libs/settings/dam/v3D/assetTypes/*/Enabled` | Ingesteld op true of false om deze vermelding in de lijst **[!UICONTROL assetTypes]** in of uit te schakelen. |
| `/libs/settings/dam/v3D/assetTypes/*/Extension` | Geef een of meer achtervoegsels of bestandsextensies met komma&#39;s op die aan dit type element moeten worden gekoppeld. |
| `/libs/settings/dam/v3D/assetTypes/*/IngestRegime` | Moet `native` zijn voor FBX- en OBJ-bestandsindelingen en `maya` voor indelingen die door Maya zijn ingeschakeld. |
| `/libs/settings/dam/v3D/assetTypes/*/MimeType` | Geeft het mime-type voor dit elementtype aan. Voor formaten die door Maya worden toegelaten wordt het geadviseerd om `application/x-ext` te gebruiken, waar `ext` de koord als `Extension` waarde wordt gespecificeerd. |

## Ingestieconfiguratie {#ingestion-configuration}

In **CRXDE Lite** in AEM (**[!UICONTROL Tools > General > CRXDE Lite]**), heb toegang tot de volgende configuraties:

<table> 
 <tbody> 
  <tr> 
   <td><strong>Pad</strong></td> 
   <td><strong>Beschrijving</strong></td> 
  </tr> 
  <tr> 
   <td>/libs/settings/dam/v3D/settings/addGroundPlaneImageOnIngest</td> 
   <td>Hiermee wordt het genereren van een omgevingsslagschaduw ingeschakeld bij weergave of rendering met een IBL-werkgebied. Is van toepassing op Voorvertoning en Rendering met RapidRefine</td> 
  </tr> 
  <tr> 
   <td><p>/libs/settings/dam/v3D/settings/CleupRenderWorkDir</p> </td> 
   <td>Stel in op <strong>false</strong> om tijdelijke bestanden na conversie en rendering in de map MayaWork te behouden. Dit kan handig zijn bij het opsporen van fouten in Maya-conversie en -rendering.</td> 
  </tr> 
  <tr> 
   <td>/libs/settings/dam/v3D/settings/invokeAnimationOnIngest</td> 
   <td><p>Wanneer toegelaten, is ImageMagick geïnstalleerd op de server en magickPath wordt gevormd. Met Snel verfijnen maakt u een eenvoudige animatie voor 3D-objecten die als miniatuur worden gebruikt in de Kaartweergave en andere weergaven.</p> <p>Het maken van animaties verbruikt aanzienlijke CPU-bronnen tijdens het innameproces.</p> </td> 
  </tr> 
  <tr> 
   <td>/libs/settings/dam/v3D/settings/invokeLightMapsOnIngest</td> 
   <td>Hiermee kunt u bij inname automatisch lichte kaarten maken. Stel in op <strong>false</strong> om het automatisch maken van een lichtkaart uit te schakelen. dit kan het CPU-verbruik aanzienlijk verlagen ten koste van een lagere kwaliteit voor voorvertonen en renderen met Rapid Refine. Heeft geen invloed op de rendering met Maya.</td> 
  </tr> 
  <tr> 
   <td>/libs/settings/dam/v3D/settings/gPlaneZero</td> 
   <td><p>Wanneer ingesteld op <strong>true</strong> (standaardwaarde), worden objecten indien nodig verticaal verplaatst om ervoor te zorgen dat alle delen van het object zich boven het grondvlak bevinden (y=0).</p> <p>Wanneer deze waarde wordt ingesteld op <strong>false</strong> (standaardwaarde), worden objecten niet verplaatst en kunnen ze gedeeltelijk worden verborgen door het grondvlak van een werkgebied. (Alleen van toepassing op voorvertoning en rendering met Rapid Refine.) Het heeft echter geen invloed op de rendering met Maya. Wanneer ingesteld op <strong>true</strong>, kan de verticale positie van objecten in Maya anders zijn dan in de voorvertoning of bij rendering met Rapid Refine.</p> </td> 
  </tr> 
  <tr> 
   <td>/libs/settings/dam/v3D/Paths/magickPath</td> 
   <td>Het pad en de naam naar het ImageMagick-hulpprogramma voor conversie. Een absoluut pad is vereist als het maken van miniaturen met animatie is ingeschakeld.</td> 
  </tr> 
  <tr> 
   <td>/libs/settings/dam/v3D/settings/MaxCpuPercentage</td> 
   <td><p>Hiermee geeft u op hoeveel CPU's maximaal worden gebruikt voor innameverwerking van 3D-elementen.</p> <p>Hogere waarden versnellen de inname, maar kunnen ertoe leiden dat AEM over het geheel genomen minder reageren. Deze instelling is bij benadering. Dat wil zeggen dat de nauwkeurigheid toeneemt met het aantal beschikbare CPU-cores.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Cloud Services configuratie-instellingen {#cloud-services-configuration-settings}

Waarden voor de volgende instellingen worden opgegeven door uw Adobe-accountmanager, -expert of -supportmedewerker.

| **Pad** | **Beschrijving** |
|---|---|
| `/libs/settings/dam/v3D/services/aws/accountId` | De account-id van de Adobe AWS-account. |
| `/libs/settings/dam/v3D/services/aws/bucketName` | de naam van het S3-overdrachtssegment; normaal `aem3d`. |
| `/libs/settings/dam/v3D/services/aws/customerId` | De unieke id die door Adobe aan uw organisatie wordt toegewezen. Wordt gebruikt als gebruikers-id voor AWS Cognito. |
| `/libs/settings/dam/v3D/services/aws/encryptedPassword` | Het wachtwoord dat aan deze customerId is gekoppeld. Wordt gebruikt als wachtwoord voor AWS-codering. |
| `/libs/settings/dam/v3D/services/aws/region` | Het AWS-gebied waar de cloudservices worden geïmplementeerd. |
| `/libs/settings/dam/v3D/services/aws/userPoolId` | De toepasselijke AWS Cognito-gebruikersnaam. |
| `/libs/settings/dam/v3D/services/dncr/clientId` | De AWS Cognito client-id voor de Dncr-conversieservice. |

## Algemene verwerkingsinstellingen {#common-processing-settings}

In **CRXDE Lite** in AEM (**[!UICONTROL Tools > General > CRXDE Lite]**), heb toegang tot de volgende configuraties:

| **Pad** | **Beschrijving** |
|---|---|
| `/libs/settings/dam/v3D/Paths/mayaWorkPath` | De naam en locatie van de werkmap voor Maya-conversie en -rendering. De map wordt automatisch gemaakt als deze niet bestaat. |
| `/libs/settings/dam/v3D/Paths/maxWorkPath` | Naam en locatie van de werkmap voor maximale 3ds-conversie. De map wordt automatisch gemaakt als deze niet bestaat. |
| `/libs/settings/dam/v3D/settings/debugNative` | Stel in op **[!UICONTROL true]** om het maken van foutopsporingsgegevens tijdens de conversie en rendering van indelingen met de RapidRefine-renderer mogelijk te maken. |

## Rendererconfiguratie {#renderer-configuration}

In **CRXDE Lite** in AEM (**[!UICONTROL Tools > General > CRXDE Lite]**), heb toegang tot de volgende configuraties:

| **Pad** | **Beschrijving** |
|---|---|
| `/libs/settings/dam/v3D/settings/dynamicIBL` | Wanneer ingesteld op **[!UICONTROL true]** en vooraf gegenereerde lichtmaps niet beschikbaar zijn (dat wil zeggen invokeLightMapsOnIngest=false), maakt de renderer Rapid Refine lichtmaps tijdens rendering om de renderkwaliteit te verbeteren. Deze instelling kan de rendertijd aanzienlijk verhogen. Door de instelling op **[!UICONTROL false]** wordt het CPU-gebruik in dergelijke situaties tot een minimum beperkt, maar kan de renderkwaliteit afnemen. |
| `/libs/settings/dam/v3D/renderers/*/Enabled` | Stel in op **[!UICONTROL true]** of **[!UICONTROL false]** om respectievelijk een renderer in of uit te schakelen. |
| `/libs/settings/dam/v3D/renderers/*/Display` | Hiermee kunt u de tekenreeks wijzigen die wordt weergegeven voor een ingeschakelde renderer in de rendererkiezer in het deelvenster Rendering. |
| `/libs/settings/dam/v3D/renderers/*/MaxCpuPercentage` | Hiermee geeft u op hoeveel CPU&#39;s maximaal worden gebruikt voor het renderen van 3D-scènes. Hogere waarden versnellen de rendering, maar kunnen ertoe leiden dat AEM over het algemeen minder responsief worden. Deze instelling is bij benadering. Dat wil zeggen dat de nauwkeurigheid toeneemt met het aantal beschikbare CPU-cores. |

## Instellingen voor voorvertoning van 3D-element {#d-asset-preview-settings}

In **CRXDE Lite** in AEM (**[!UICONTROL Tools > General > CRXDE Lite]**), heb toegang tot de volgende configuraties:

| Pad | Beschrijving |
|---|---|
| `/libs/settings/dam/v3D/WebGLSites/autoSpin` | Stel in op **[!UICONTROL true]** of **[!UICONTROL false]** om automatisch centrifugeren (automatische camera-omdraaiing) bij het laden van de pagina in of uit te schakelen. |
| `/libs/settings/dam/v3D/WebGLSites/autoSpinAfterReset` | Stel in op **[!UICONTROL true]** om automatisch centrifugeren opnieuw te starten nadat **[!UICONTROL Reset]** is ingedrukt. Wordt genegeerd wanneer automatisch draaien is uitgeschakeld. |
| `/libs/settings/dam/v3D/WebGLSites/autoSpinSpeed` | Hiermee geeft u de snelheid (omwentelingen per minuut) en de richting van de automatische centrifuge op, met negatieve waarden voor rotatie van rechts naar links en positieve waarden voor rotatie van links naar rechts. |
| `/libs/settings/dam/v3D/WebGL/continueRotate` | Stel in op **[!UICONTROL false]** om het vervolg uit te schakelen met de geleidelijke vervaging van de viewerreacties op aanraak- en muisbewegingen. |
| `/libs/settings/dam/v3D/WebGL/curtainColor` | Hiermee geeft u de kleur op van het gordijn voor laden dat optioneel de viewport van de voorvertoning van het 3D-element tijdens het laden en initialiseren kan bedekken. R,G,B-waarde, met elke kleurcomponent in het bereik 0 tot en met 255. |
| `/libs/settings/dam/v3D/WebGL/fadeCurtains` | Wanneer ingesteld op **[!UICONTROL true]**, vervaagt het gordijn geleidelijk tijdens de laatste onderdelen van de viewerinitialisatie. Wanneer ingesteld op **[!UICONTROL false]**, blijft het gordijn dekkend totdat het laden en initialiseren is voltooid. |
| `/libs/settings/dam/v3D/WebGL/showCurtains` | Stel in op **[!UICONTROL true]** of **[!UICONTROL false]** om het taakgordijn voor voorvertoning van 3D-elementen in of uit te schakelen. |
| `/libs/settings/dam/v3D/WebGL/spinHeight` | Wanneer automatisch draaien is ingeschakeld en actief, wordt de verticale positie van de camera automatisch aangepast ten opzichte van de hoogte van het 3D-object. Wanneer deze is ingesteld op 0,5, wordt de camera verticaal op een hoogte van 1/2 van het object geplaatst. Dit betekent dat de horizon verticaal in de viewport moet worden gecentreerd. Bij hogere waarden kijkt de camera omlaag naar het object en wordt de hoogte van de gerenderde horizon verhoogd. Bij lagere waarden kijkt de camera omhoog naar het object en verlaagt de horizon. |

## Instellingen voor 3D-sitecomponenten {#d-sites-component-settings}

In **CRXDE Lite** in AEM (**[!UICONTROL Tools > General > CRXDE Lite]**), heb toegang tot de volgende configuraties:

| Pad | Beschrijving |
|---|---|
| `/libs/settings/dam/v3D/WebGLSites/autoSpinAfterReset` | Stel in op **[!UICONTROL true]** om automatisch centrifugeren (automatische camera-omdraaiing) opnieuw te activeren nadat u op de thuiscomputer hebt gedrukt. Wordt genegeerd wanneer automatisch draaien is uitgeschakeld. |
| `/libs/settings/dam/v3D/WebGLSites/continueRotate` | Stel in op **[!UICONTROL false]** om het vervolg uit te schakelen met de geleidelijke vervaging van de viewerreacties op aanraak- en muisbewegingen. |
| `/libs/settings/dam/v3D/WebGLSites/curtainColor` | Hiermee geeft u de kleur op van het gordijn voor laden dat optioneel de viewport van de component 3D-sites tijdens het laden kan bedekken. R,G,B-waarde, met elke kleurcomponent in het bereik 0 tot en met 255. |
| `/libs/settings/dam/v3D/WebGLSites/fadeCurtains` | Wanneer ingesteld op **[!UICONTROL true]**, zal het ladingsgordijn geleidelijk verdwijnen tijdens de laatste delen van lading en initialisering. Wanneer ingesteld op **[!UICONTROL false]**, blijft het gordijn dekkend totdat het laden en initialiseren is voltooid. |
| `/libs/settings/dam/v3D/WebGLSites/showCurtains` | Stel in op **[!UICONTROL true]** of **[!UICONTROL false]** om het laadgordijn voor de component 3D-sites in of uit te schakelen. |
| `/libs/settings/dam/v3D/WebGLSites/spinHeight` | Wanneer automatisch draaien is ingeschakeld en actief, wordt de verticale positie van de camera automatisch aangepast ten opzichte van de hoogte van het 3D-object. Wanneer deze is ingesteld op 0,5, wordt de camera verticaal op een hoogte van 1/2 van het object geplaatst. Dit betekent dat de horizon verticaal in de viewport moet worden gecentreerd. Bij hogere waarden kijkt de camera omlaag naar het object en wordt de hoogte van de gerenderde horizon verhoogd. Bij lagere waarden kijkt de camera omhoog naar het object en verlaagt de horizon. |

