---
title: Regels gebruiken om URL's te transformeren
description: U kunt regelsets in Dynamic Media gebruiken om URL's te transformeren. Regelsets zijn instructiesets die in een scripttaal (zoals JavaScript) zijn geschreven en die XML-gegevens evalueren en bepaalde handelingen uitvoeren als die gegevens aan bepaalde voorwaarden voldoen.
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
exl-id: f0cd3a75-03ed-40a9-b336-8a782f3cfe69
feature: Rulesets
role: Admin,User,Developer
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 3%

---

# Regelsets gebruiken om URL&#39;s te transformeren {#using-rulesets-to-transform-urls}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt regelsets in Dynamic Media gebruiken om URL&#39;s te transformeren. Regelsets zijn instructiesets die in een scripttaal (zoals JavaScript) zijn geschreven en die XML-gegevens evalueren en bepaalde handelingen uitvoeren als die gegevens aan bepaalde voorwaarden voldoen. Elke regel bestaat uit ten minste één voorwaarde en ten minste één actie. Een regel evalueert de gegevens van XML tegen de voorwaarden, en als een voorwaarde wordt voldaan, dan neemt het de aangewezen actie. Voorbeelden van regelsets zijn:

* Een MIME-achtervoegsel toevoegen. Voor veel services en websites zijn afbeeldingsachtervoegsels vereist, zoals toevoegen `.jpg` naar een URL.
* Een mappad naar de URL maken voor SEO-doeleinden (Search Engine Optimization, optimalisatie van zoekprogramma&#39;s).

   Zie [Hoe Adobe Dynamic Media Classic SEO ondersteunt](/help/assets/assets/s7_seo.pdf).

* Metagegevens toevoegen aan de URL voor SEO-doeleinden (Search Engine Optimization).

   Zie [Hoe Adobe Dynamic Media Classic SEO ondersteunt](/help/assets/assets/s7_seo.pdf).

* De positie van de inhoud instellen om een download te activeren.
* Vereenvoudig URL&#39;s met sjablonen voor beeldweergave voor personalisatie. Bijvoorbeeld draaien `rgb{XX,YY,ZZ}` in RTF-gereed `\redXX\greenYY\blueZZ`

* Vraag om bepaalde tekens die moeten worden gecodeerd, zoals `$`, `{`, en `}`en bepaalde tekens die naar ImageServer moeten worden gedecodeerd. Facebook werkt bijvoorbeeld niet goed met URL&#39;s die speciale tekens bevatten.

   Zie [Speciale tekens uit URL&#39;s verwijderen](https://helpx.adobe.com/experience-manager/scene7/kb/base/scene7-rulesets/remove-special-characters-urls.html).

In de context van Dynamic Media kunnen websites die een op XML gebaseerd systeem gebruiken voor het beheer van elementgegevens, XML-bestanden uploaden naar Dynamic Media. U kunt een van deze bestanden aanwijzen als het bestand met de voorverwerkingsregel voor het bedienen van Dynamic Media-elementen. Dit bestand herstructureert de standaard URL-protocolindeling om te voldoen aan de bedrijfslogica van systemen die worden geïntegreerd met Dynamic Media. U geeft een XML-bestand op dat moet dienen als pad naar het definitiebestand voor de regel.

>[!CAUTION]
>
>Wees voorzichtig bij het gebruik van linialen; kunnen voorkomen dat Dynamic Media-inhoud op uw website wordt weergegeven.

Er zijn voorbeeldregels beschikbaar die u kunnen helpen uw eigen regels te maken.\
Zie [Referentie voor regelset](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-serving-api/image-serving-api/rule-set-reference/c-rule-set-reference.html).

Net als bij het maken van alle regelsets moet u ervoor zorgen dat uw XML-bestand geldig is voordat u het uploadt met een XML-validatieprogramma zoals xmlvalid.\
Zie ook [Regelsets voor probleemoplossing](https://helpx.adobe.com/experience-manager/scene7/kb/base/scene7-rulesets/scene7-ruleset-troubleshooting.html).

Zorg er ook voor dat u eerst de regel test die is ingesteld in een testomgeving die geen invloed heeft op uw live productieomgeving.\
Productieomgevingen en staging-omgevingen vereisen doorgaans verschillende logins.

Zie de [Adobe Dynamic Media Classic-bureaubladtoepassing voor aanmelden](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/getting-started/signing-out.html#sign-in-dmc-app).

<!-- * **NA staging environment** login page: [https://s7sps1-staging.scene7.com/IpsWeb/](https://s7sps1-staging.scene7.com/IpsWeb/)
* **EMEA staging environment** login page: [https://s7sps3-staging.scene7.com/IpsWeb/](https://s7sps3-staging.scene7.com/IpsWeb/)
* **JAPAC staging environment** login page: [https://s7sps5-staging.scene7.com/IpsWeb/](https://s7sps5-staging.scene7.com/IpsWeb/) -->

Zie ook [De afbeelding &#39;asset&#39; gebruiken in plaats van &#39;is&#39; in een regelset](https://helpx.adobe.com/experience-manager/scene7/kb/base/scene7-rulesets/ruleset-asset-instead-image.html).

**XML-regelsets implementeren:**

1. Aanmelden bij uw [Dynamic Media Classic-bureaubladtoepassing](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/getting-started/signing-out.html#sign-in-dmc-app).

   Adobe heeft uw aanmeldingsgegevens en aanmeldingsgegevens op het moment van de provisioning opgegeven. Neem contact op met Technische ondersteuning als u deze informatie niet hebt.

1. Upload het bestand met de regelset als volgt:

   * Klik op de algemene navigatiebalk op **[!UICONTROL Upload]**.
   * Op de **[!UICONTROL Upload]** pagina, bij de linkerbovenhoek, klikt u op **[!UICONTROL Browse]**.
   * In de **[!UICONTROL Open]** bladert u naar het bestand met de regelset (XML).
   * Selecteer het bestand en klik op **[!UICONTROL Open]**.
   * Aan de rechterkant van het **[!UICONTROL Upload]** pagina, selecteert u een doelmap voor het regelsetbestand.
   * Onder aan de pagina controleren, controleren **[!UICONTROL Publish After Uploading]** is ingeschakeld.
   * Klik in de rechterbenedenhoek van de pagina op **[!UICONTROL Submit Upload]**.
   * Klik op de algemene navigatiebalk op **[!UICONTROL Jobs]** om de status van de uploadtaak te controleren. Wanneer de **[!UICONTROL Status]** kolom op de **[!UICONTROL Job]** De pagina zegt Geüpload Klaar, ga aan de volgende stappen verder.

1. Klik op de navigatiebalk boven aan de pagina op **[!UICONTROL Setup > Application Setup > Publish Setup > Image Server]**.
1. Zoek op de pagina **[!UICONTROL Image Server Publish]** onder de groep **[!UICONTROL Catalog Management]** naar **[!UICONTROL Rule Set Definition File Path]** en klik vervolgens op **[!UICONTROL Select]**.
1. Blader op de pagina **[!UICONTROL Select Rule Set Definition File (XML)]** naar het bestand met de regelset en klik vervolgens in de rechterbenedenhoek van de pagina op **[!UICONTROL Select]**.
1. Klik in de rechterbenedenhoek van de pagina Setup op **[!UICONTROL Close]**.
1. Voer een publicatietaak voor afbeeldingsservers uit.

   De regelingestelde voorwaarden worden toegepast op de aanvragen voor live Dynamic Media Image Servers.

   Als u wijzigingen aanbrengt in het bestand met de regelset, worden de wijzigingen direct toegepast wanneer u het bijgewerkte bestand met de regelset opnieuw uploadt en publiceert.
