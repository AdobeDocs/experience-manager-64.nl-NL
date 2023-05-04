---
title: Elektronische handtekeningen toepassen op een formulier met scripthandtekeningen
seo-title: Apply electronic signatures to a form using scribble signatures
description: Formulieren ondertekenen met behulp van krabbelen
seo-description: Signing forms using scribble
uuid: e807d0de-6d5f-458e-be3e-273ed7a521c0
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: 6a806727-28c5-430e-9a83-b43e0e9d9e1c
feature: Adaptive Forms
exl-id: a870c4b7-4040-4bd8-b477-286ebe6a4b01
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 0%

---

# Elektronische handtekeningen toepassen op een formulier met scripthandtekeningen {#apply-electronic-signatures-to-a-form-using-scribble-signatures}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

U kunt de **Krabbelhandtekening** en **Handtekeningstap** component om een handtekening (krabbelen) te tekenen op een adaptief formulier. De component Handtekeningstap geeft een PDF-versie van het adaptieve formulier weer. U hebt een optie Document of Record ingeschakeld of op een formuliersjabloon gebaseerde adaptieve formulieren nodig om de component Handtekeningstap te kunnen gebruiken.

Beide componenten bieden een venster, zoals hieronder wordt weergegeven, om een formulier te ondertekenen. U kunt ook op het geolocatiepictogram klikken ![aem_6_3_geolocation](assets/aem_6_3_geolocation.png) om geolocatie toe te voegen aan de handtekening.

![Dialoogvenster Krabbelen](assets/scribble-signature.png)

## Een adaptief formulier configureren voor het gebruik van de Krabbelhandtekening {#configure-an-adaptive-form-to-use-scribble-signature}

1. Maak een Document of Record-optie ingeschakeld of een adaptief formulier op basis van een formuliersjabloon. Voor geleidelijke informatie, zie [Een adaptief formulier maken](/help/forms/using/creating-adaptive-form.md).
1. Sleep de **Krabbelhandtekening** van componentbrowser naar het adaptieve formulier.
1. Tik op de knop **Configureren** ![vormen](assets/configure.png) pictogram. De eigenschappenbrowser wordt geopend en de eigenschappen van de component Krabbelen handtekening worden weergegeven. Configureer eigenschappen van de component Krabbelhandtekening.
1. Sleep de component Signature Step van de componentbrowser naar het aangepaste formulier.

   >[!NOTE]
   >
   >De component voor de stap Handtekening gebruikt de volledige breedte die beschikbaar is voor het formulier. Het wordt aanbevolen geen andere component op te nemen in de sectie die de component voor de stap Handtekening bevat.

1. Tik in de Inhoudsbrowser op **Formuliercontainer** en tik op de knop **Configureren** ![vormen](assets/configure.png) pictogram. De eigenschappenbrowser wordt geopend en de eigenschappen van de container Adaptief formulier worden weergegeven. Navigeren naar **Aangepaste formuliercontainer** > **Elektronische handtekening** en deselecteer de **Acrobat Sign inschakelen** optie. Tik op Gereed ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png) om de wijzigingen op te slaan.

   >[!NOTE]
   >
   >Wanneer u een component Handtekeningstap toevoegt aan een adaptief formulier, wordt de optie Acrobat Sign inschakelen automatisch geselecteerd.

1. Tik op de knop **Configureren** ![vormen](assets/configure.png) pictogram. De eigenschappenbrowser wordt geopend en de eigenschappen voor stap Handtekening worden weergegeven. Configureer de volgende eigenschappen:

   * **Elementnaam**: Geef de naam van de component op.
   * **Titel:** Geef een unieke titel van de component op.
   * **Sjabloonbericht:** Geef het bericht op dat moet worden weergegeven wanneer de PDF van de handtekening wordt geladen. Acrobat Sign-services hebben enige tijd nodig om de PDF van de handtekening voor te bereiden en te laden.
   * **Ondertekeningsservice:** Selecteer **Krabbelhandtekening** optie.
   * **CSS-klasse**: Geef eventueel de CSS-klasse van de clientbibliotheek op. Het wordt aanbevolen [thema&#39;s](/help/forms/using/themes.md) en [inline stijlen](/help/forms/using/inline-style-adaptive-forms.md) in plaats van CSS-klasse.

   Tik op Gereed ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png) om de wijzigingen op te slaan. De handtekening is geconfigureerd.

   Wanneer u nu een formulier invult, wordt een PDF-versie van het aangepaste formulier weergegeven en worden opties voor de ondertekening van het PDF-document weergegeven. Zie voor meer informatie [Een adaptief formulier ondertekenen met de Krabbelhandtekening](/help/forms/using/signing-forms-using-scribble.md#p-sign-an-adaptive-form-using-scribble-signature-p).

## Een adaptief formulier ondertekenen met de Krabbelhandtekening {#sign-an-adaptive-form-using-scribble-signature}

1. Nadat u een adaptief formulier hebt ingevuld en de pagina Stap handtekening hebt bereikt, wordt het handtekeningscherm weergegeven.

   ![Handtekeningscherm voor EchoSign-pagina](assets/esignscribblesign.jpg)

1. Klik op **[!UICONTROL Sign]**. Het dialoogvenster Scriptteken wordt weergegeven. Onderteken het formulier en klik op Gereed ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png) pictogram om de handtekening op te slaan.

   ![Dialoogvenster Krabbelen](assets/scribblewidget.jpg)

1. Klik op Voltooien om het ondertekeningsproces te voltooien.

   ![Voltooi het ondertekeningsproces](assets/scribblecomplete.jpg)

De handtekeningen worden toegevoegd aan het formulier en het formulierbesturingselement gaat naar het volgende venster.
