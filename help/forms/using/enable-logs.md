---
title: Logboek inschakelen voor HTML5-formulieren
seo-title: Enable logging for HTML5 forms
description: Met het hulpprogramma Logger kunt u zich aanmelden voor een formulier en kunt u fouten in formuliergerelateerde problemen opsporen.
seo-description: The logger utility enables logging for a form and helps you debug form-related issues.
uuid: d6279092-57f3-4fc6-b41b-9caf65459d4d
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: 23bc7cd2-7d06-4ef8-977a-778e290daef9
feature: Mobile Forms
exl-id: c7953d1b-a332-4138-b744-516f3881cd4d
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 3%

---

# Logboek inschakelen voor HTML5-formulieren {#enable-logging-for-html-forms}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt het hulpprogramma Logger configureren om logbestanden voor HTML5-formulieren te maken. Het loggerhulpprogramma heeft verschillende niveaus en u kunt een niveau instellen op basis van uw vereisten. HTML5-formulieren hebben server- en clientcomponenten. U kunt logboeken voor beide componenten vormen.

## Logboekregistratie op de server configureren {#configuring-server-side-logging}

Voer de volgende stappen uit om logbestanden aan de serverzijde te configureren:

1. Ga naar `https://[server]:[port]/system/console/configMgr`. Zoek en open de *Configuratie van logboek van Apace Sling-logboekregistratie* optie. Er wordt een dialoogvenster weergegeven:

   ![ Het dialoogvenster voor het instellen van de optie Apace Sling-logboekregistratie](assets/logconfig.png)

   Configuratieoptie Apace Sling-logboekregistratie

1. Wijzig de **Logboekniveau** tot **Foutopsporing**.

1. Geef een naam en pad op voor de **Logbestand**.

   >[!NOTE]
   >
   >Als u logbestanden wilt genereren in de logmap met HTML5-formulieren, voegt u ../logs/ toe vóór de bestandsnaam.

1. Wijzigen **Aanmelder** tot **HTMLFormsPerfLogger.** Klikken **Opslaan**.

## Logboekregistratie van clients configureren {#configuring-client-logging}

U kunt de volgende methoden gebruiken om aanmelding op de client in HTML5-formulieren in te schakelen:

* De genoemde parameter request gebruiken `log`
* CQ-configuratiebeheer gebruiken

### Registreren met behulp van aanvraagparameter inschakelen {#enabling-logging-using-request-parameter}

Met deze methode kunt u logboeken voor een bepaalde aanvraag genereren. De naam van de parameter request is **log**. Het logbestand-URL ziet er als volgt uit:

`https://<server>:<port>/content/xfaforms/profiles/test.html?contentRoot=<path of the folder containing form xdp>&template=<name of the xdp>&log=<log configuration>.`

De logboekconfiguratie wordt samengesteld uit het logboekniveau en de logboekcategorie.

#### Logbestemming {#log-destination}

<table> 
 <tbody> 
  <tr> 
   <th><strong>Logbestemming</strong></th> 
   <th><strong>Beschrijving</strong></th> 
  </tr> 
  <tr> 
   <td>1</td> 
   <td>Logbestanden worden naar de browser geleid <strong>Console</strong></td> 
  </tr> 
  <tr> 
   <td>2</td> 
   <td>Logbestanden worden verzameld in een JavaScript-object op de client en kunnen worden geplaatst op <strong>Server</strong> </td> 
  </tr> 
  <tr> 
   <td>3</td> 
   <td>Beide opties<br /> </td> 
  </tr> 
 </tbody> 
</table>

#### Logboekniveaus {#log-levels}

<table> 
 <tbody> 
  <tr> 
   <th>Logboekniveau</th> 
   <th>Beschrijving</th> 
  </tr> 
  <tr> 
   <td>0</td> 
   <td>UIT<br type="_moz" /> </td> 
  </tr> 
  <tr> 
   <td>1</td> 
   <td>FATAAL<br type="_moz" /> </td> 
  </tr> 
  <tr> 
   <td>2</td> 
   <td>FOUT<br type="_moz" /> </td> 
  </tr> 
  <tr> 
   <td>3</td> 
   <td>WAARSCHUWING<br type="_moz" /> </td> 
  </tr> 
  <tr> 
   <td>4</td> 
   <td>INFO<br type="_moz" /> </td> 
  </tr> 
  <tr> 
   <td>5</td> 
   <td>DEBUG<br type="_moz" /> </td> 
  </tr> 
  <tr> 
   <td>6</td> 
   <td>TRACE<br type="_moz" /> </td> 
  </tr> 
  <tr> 
   <td>7</td> 
   <td>ALLES<br type="_moz" /> </td> 
  </tr> 
 </tbody> 
</table>

#### Gebruikerscategorieën {#logger-categories}

<table> 
 <tbody> 
  <tr> 
   <th>Logboekcategorie</th> 
   <th>Beschrijving</th> 
  </tr> 
  <tr> 
   <td>a</td> 
   <td>xfa (logboeken met scriptengine)</td> 
  </tr> 
  <tr> 
   <td>b</td> 
   <td>xfaView (logbestanden met betrekking tot de layout-engine)<br type="_moz" /> </td> 
  </tr> 
  <tr> 
   <td>c</td> 
   <td>xfaPerf (prestatiegerelateerde logs)<br type="_moz" /> </td> 
  </tr> 
 </tbody> 
</table>

#### Logboekconfiguratie {#log-configuration}

In het logboek URL, wordt de parameter van het de vraagkoord van de logboekconfiguratie als volgt bepaald:

`{destination}-{a level}-{b level}-{c level}`

Bijvoorbeeld:

<table> 
 <tbody> 
  <tr> 
   <th>Logboekconfiguratie</th> 
   <th>Beschrijving</th> 
  </tr> 
  <tr> 
   <td>2-a4-b5-c6<br type="_moz" /> </td> 
   <td>Doel: Server<br /> xfa-niveau: INFO<br /> xfaView-niveau: DEBUG<br /> xfaPerf-niveau: TRACE</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Het standaardlogniveau voor elke logcategorie a (xfa), b (xfaView), en c (xfaPerf) is 2 (ERROR). Dienovereenkomstig, voor logboekconfiguratie: 2-b6, de logboekniveaus voor verschillende categorieën zijn:\
>a (xfa): 2 (FOUT OP standaardniveau)\
>b (xfaView): 6 (door gebruiker opgegeven TRACE)\
>a (xfaPerf): 2 (FOUT OP standaardniveau)

### Registreren inschakelen met Configuratiebeheer {#enabling-logging-using-configuration-manager}

Als u de Manager van de Configuratie voor het toelaten van registreren gebruikt, worden de logboeken geproduceerd voor elk teruggeven verzoek tot het registreren opnieuw onbruikbaar wordt gemaakt.

1. Meld u aan bij CQ Configuration Manager op `https://[server]:[port]/system/console/configMgr` en aanmelden met beheerdersreferenties.
1. Zoeken naar en klikken **Mobiele Forms-configuraties**.
1. Voer in het tekstvak Opties voor foutopsporing de logboekconfiguraties in zoals bijvoorbeeld in de vorige sectie wordt beschreven. **2-a4-b5-c6**

   ![Forms-configuratie](assets/forms_configuration.png)

   Forms-configuratie

## Logbestanden uploaden {#uploading-logs}

Als de bestemming als 1 wordt geplaatst, worden alle berichten van het cliëntmanuscript logboek geleid aan de console. Als een beheerder deze logboeken samen met serverlogboeken vereist, plaats bestemmingsniveau aan 2. Op dit niveau worden alle logbestanden verzameld in een JS-object op de client en als het formulier wordt weergegeven met het standaardprofiel, wordt een **Logbestanden verzenden** wordt links van **Bestaande velden markeren** op de werkbalk. Wanneer de gebruiker op de koppeling klikt, worden alle verzamelde logbestanden naar de server gepost en aangemeld bij het geconfigureerde foutenlogbestand op de server.

Standaard wordt alle informatie toegevoegd aan het bestand error.log in de map /crx-repository/logs/.

De locatie en naam van het logbestand wijzigen:

1. Meld u aan bij Configuratiebeheer als beheerder. De standaard-URL van Configuration Manager is `https://[*Server*]:[*Port*]/system/console/configMgr`.
1. Klikken **Logboekconfiguratie Apache Sling Logging**. Er wordt een dialoogvenster weergegeven.

   ![logconfig-1](assets/logconfig-1.png)

1. Wijzig de **Logboekniveau** op Foutopsporing.

1. Pad en naam van de **Logbestand**.

   >[!NOTE]
   >
   >Als u logbestanden wilt maken in dezelfde map waarin andere logbestanden worden opgeslagen, geeft u ../logs/&lt;filename> in het bezit van de Dossiers van het Logboek.

1. Wijzig de **Aanmelder** tot **HTMLFormsPerfLogger** en klik op **Opslaan**.
