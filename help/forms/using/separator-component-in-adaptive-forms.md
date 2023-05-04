---
title: Scheidingscomponent in adaptieve vormen
seo-title: Separator component in adaptive forms
description: U kunt de scheidingscomponent gebruiken om delen van een formulier visueel te scheiden.
seo-description: You can use the separator component to visually segregate sections of a form.
uuid: d51c3797-8227-41ed-88cd-c56cc129eb86
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: ba674a2d-7c78-430e-8e17-1a18619e71cb
feature: Adaptive Forms
exl-id: 7e37401a-8c63-4711-8a33-61e6bd4b419f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 0%

---

# Scheidingscomponent in adaptieve vormen {#separator-component-in-adaptive-forms}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Met de scheidingscomponent kunt u deelvensters van een formulier visueel van elkaar scheiden. U kunt de algemene vormgeving en stijl van een scheidingscomponent definiëren door de volgende eigenschappen van de scheidingscomponent op te geven:

* **Elementnaam:** Specifies the name of the component. De SOM-expressies richten zich op de component met de waarde die is opgegeven in het veld Elementnaam.
* **Dikte:** Hiermee wordt de dikte van de scheidingscomponent in pixels opgegeven.
* **Colspan:** Hiermee geeft u het aantal kolommen op waaraan een scheidingscomponent zich uitstrekt.
* **CSS-klasse:** Hiermee wordt de aangepaste CSS-klasse voor de scheidingscomponent opgegeven
* **Inline stijlen:** Met AEM Forms kunt u nu inline CSS-stijlen toepassen op afzonderlijke adaptieve formuliercomponenten en een voorvertoning van de wijzigingen in real-time bekijken.

Eigenschappen van een scheidingscomponent opgeven:

1. Selecteer een scheidingscomponent en tik op ![cmppr](assets/cmppr.png). De eigenschappen worden in het zijpaneel geopend.
1. Klik op een tabblad in de sectie Inline CSS-eigenschappen om CSS-eigenschappen op te geven. Bijvoorbeeld: a. Klik op het tabblad Veld op **Item toevoegen**. Er wordt een rij met twee velden toegevoegd.
1. Geef in het eerste veld links een CSS3-eigenschap op die u wilt toepassen. Bijvoorbeeld: **border**. U kunt een eigenschap ook selecteren door op de knop pijl-omlaag te klikken. De vervolgkeuzelijst is niet uitputtend en u kunt elke ondersteunde CSS3-eigenschapnaam opgeven in dit veld.
1. Geef in het aangrenzende veld een geldige waarde op voor de opgegeven CSS3-eigenschap. Bijvoorbeeld: **3px effen zwart**.
1. Klikken **Item toevoegen** om een andere eigenschap en de bijbehorende waarde op te geven.
1. Klikken **Voorvertoning** om een voorbeeld van de wijzigingen in het formulier te bekijken.
1. Klikken **OK** om de wijzigingen te bevestigen of **Annuleren ** om het dialoogvenster zonder wijzigingen af te sluiten.
