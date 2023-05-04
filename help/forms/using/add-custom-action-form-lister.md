---
title: Aangepaste actie toevoegen aan formulierbibliotheekitems
seo-title: Adding custom action on form lister items
description: Formulierontwikkelaars kunnen meer acties toevoegen aan de lijst met formulieren op de pagina Formulierportal. Standaard kunt u het formulier openen, invullen en verzenden.
seo-description: Form developers can add more actions to the listing of forms on the forms portal page. By default, the form listing allows you to access the form, fill it, and submit it.
uuid: 02c64f7d-f726-4a5b-a303-ec96934e9c01
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: customization
discoiquuid: 0e0a9b6b-fd2f-4cec-b233-500c940ee4d5
exl-id: d8f60be3-474a-4dd1-aaa5-7b6a97e1a9bd
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---

# Aangepaste actie toevoegen aan formulierbibliotheekitems {#adding-custom-action-on-form-lister-items}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

In AEM Forms kunt u een poortpagina maken met de beschikbare formulieren. Standaard kunt u formulieren zoeken en weergeven op een portalpagina. U kunt formulieren openen om uw gegevens in te vullen en te verzenden. Alleen renderacties worden in het vak weergegeven voor formulieren die op een portalpagina worden vermeld. Voor meer informatie over de beschikbare acties op een portalpagina raadpleegt u [Een pagina met een portal voor formulieren maken](/help/forms/using/creating-form-portal-page.md).

U kunt andere opties aan de portalpagina toevoegen. Deze opties of acties kunnen worden aangepast door de sjabloon van het formulierportaal aan te passen.

In dit artikel wordt uitgelegd hoe u een knop kunt maken om de koppeling van een formulier rechtstreeks vanaf een pagina op een formulierportal te verzenden. Voor deze aanpassing moet de sjabloon voor de component Search &amp; Lister worden bijgewerkt.

De vereiste code om de actie aan het malplaatje toe te voegen is beschikbaar hieronder. De `onclick` in het codefragment bevat een script waarmee een koppeling van een formulier via e-mail wordt verzonden.

```mxml
<div class="__FP_boxes-container __FP_single-color">
    <div class="boxes __FP_boxes __FP_single-color" data-repeatable="true">
  <div class="__FP_boxes-thumbnail">
            <img src ="${contextPath}${path}/jcr:content/renditions/cq5dam.thumbnail.319.319.png">
        </div>
        <h3 class="__FP_single-color" title="${name}" tabindex="0">${name}</h3>
        <p>${description}</p>
        <div class="boxes-icon-cont __FP_boxes-icon-cont">
            <div class="op-dow">
                <a href="${formUrl}" target="_blank" class="__FP_button ${htmlStyle}" title="${config-htmlLinkText}">Apply</a>
                <a class="__FP_button" title="Email a friend" href="#" onclick="javascript:window.location=&apos;mailto:?subject=Interesting information&body=I thought you might find {name} form helpful :  &apos;+window.location.protocol+window.location.host+&apos;${formUrl}&apos; ;">Email</a>
                <a href="${pdfUrl}" class="__FP_button ${pdfStyle}" title="${config-pdfLinkText}">Download</a>
            </div>
        </div>
    </div>
</div>
```

U kunt vergelijkbare acties toevoegen aan uw aangepaste sjabloon. Als u een JavaScript-functie wilt definiëren, voegt u de functie toe aan een script op paginaniveau en koppelt u deze aan het vereiste HTML-element. In het bovenstaande voorbeeld wordt `onclick` expression is the linked function.

Nadat u de wijzigingen in de sjabloon hebt aangebracht, bevat de pagina met de voorbeeldportal een knop waarmee u de koppeling van het formulier via e-mail kunt verzenden, zoals hieronder wordt weergegeven.

![email](assets/email.png)
