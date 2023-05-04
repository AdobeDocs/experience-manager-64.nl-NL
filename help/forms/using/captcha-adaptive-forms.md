---
title: CAPTCHA gebruiken in aangepaste vormen
seo-title: Using CAPTCHA in adaptive forms
description: Leer hoe u AEM CAPTCHA- of Google reCAPTCHA-service configureert in adaptieve formulieren.
seo-description: Learn how to configure AEM CAPTCHA or Google reCAPTCHA service in adaptive forms.
uuid: 8bcb0dd7-b43c-4a36-8f6b-7875b68f9ba1
contentOwner: vishgupt
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author, adaptive_forms
discoiquuid: 32369b0b-5abf-487d-ae6b-972c254eb7e2
feature: Adaptive Forms
exl-id: 1129004b-5e8b-42fd-98ed-f203edde93b9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 0%

---

# CAPTCHA gebruiken in aangepaste vormen {#using-captcha-in-adaptive-forms}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

CAPTCHA (Complete Automated Public Turing test to tell Computers and Humans Apart) is een programma dat vaak wordt gebruikt bij online transacties om onderscheid te maken tussen mensen en geautomatiseerde programma&#39;s of bots. Het stelt een uitdaging en evalueert de reactie van de gebruiker om te bepalen of het een mens of bot is die met de site communiceert. Het verhindert de gebruiker om te werk te gaan als de test ontbreekt en de hulp maakt online transacties veilig door bots te houden spam of kwaadwillige doeleinden posten.

AEM Forms ondersteunt CAPTCHA in adaptieve vormen. U kunt de reCAPTCHA-service van Google gebruiken om CAPTCHA te implementeren.

>[!NOTE]
>
>AEM Forms biedt alleen ondersteuning voor reCaptcha v2. Andere versies worden niet ondersteund.
>
>CAPTCHA in adaptieve formulieren wordt niet ondersteund in de offlinemodus van de AEM Forms-app.

## De ReCAPTCHA-service door Google configureren {#google-recaptcha}

Auteurs van formulieren kunnen de reCAPTCHA-service van Google gebruiken om CAPTCHA in adaptieve formulieren te implementeren. Het biedt geavanceerde CAPTCHA-mogelijkheden om uw site te beschermen. Voor meer informatie over hoe reCAPTCHA werkt, zie [Google reCAPTCHA](https://developers.google.com/recaptcha/).

![recaptcha](assets/recaptcha.png)

De reCAPTCHA-service implementeren in AEM Forms:

1. Verkrijgen [reCAPTCHA API-sleutelpaar](https://www.google.com/recaptcha/admin) uit Google. De site bevat een sleutel en een geheim.
1. Configuratiecontainer maken voor cloudservices.

   1. Ga naar **[!UICONTROL Tools > General > Configuration Browser]**.
      * Zie de [Documentatie van de configuratievenster](/help/sites-administering/configurations.md) voor meer informatie .
   1. Ga als volgt te werk om de algemene map voor cloudconfiguraties in te schakelen of sla deze stap over om een andere map voor cloudserviceconfiguraties te maken en te configureren.

      1. In Browser van de Configuratie, selecteer **[!UICONTROL global]** map en tik **[!UICONTROL Properties]**.
      1. Schakel in het dialoogvenster Configuratieeigenschappen de optie **[!UICONTROL Cloud Configurations]**.
      1. Tikken **[!UICONTROL Save & Close]** om de configuratie op te slaan en het dialoogvenster af te sluiten.
   1. Tik in de configuratiebrowser op **[!UICONTROL Create]**.
   1. Geef in het dialoogvenster Configuratie maken een titel op voor de map en schakel **[!UICONTROL Cloud Configurations]**.
   1. Tikken **[!UICONTROL Create]** om de map te maken die is ingeschakeld voor configuraties van de cloudservice.


1. Configureer de cloudservice voor reCAPTCHA.

   1. Ga naar de AEM ![gereedschappen](assets/tools.png) >  **Cloud Services**.
   1. Tik op **[!UICONTROL reCAPTCHA]**. De pagina Configurations wordt geopend. Selecteer de configuratiecontainer die u in de vorige stap hebt gemaakt en tik op **[!UICONTROL Create]**.
   1. Geef Naam, Sitecode en Geheime sleutel voor de service reCAPTCHA op en tik op **[!UICONTROL Create]** om de configuratie van de cloudservice te maken.
   1. Geef in het dialoogvenster Component bewerken de site en de geheime sleutels op die in stap 1 zijn verkregen. Tikken **[!UICONTROL Save Settings]** en tik vervolgens op **[!UICONTROL OK]** om de configuratie te voltooien.

   Zodra de reCAPTCHA-service is geconfigureerd, is deze beschikbaar voor gebruik in adaptieve formulieren. Zie voor meer informatie [CAPTCHA gebruiken in aangepaste vormen](#using-captcha).

## CAPTCHA gebruiken in aangepaste vormen {#using-captcha}

CAPTCHA in adaptieve vorm gebruiken:

1. Open een adaptief formulier in de bewerkingsmodus.

   >[!NOTE]
   >
   >Zorg ervoor dat de configuratiecontainer die is geselecteerd bij het maken van het adaptieve formulier, de reCAPTCHA-cloudservice bevat. U kunt ook adaptieve formuliereigenschappen bewerken om de configuratiecontainer te wijzigen die aan het formulier is gekoppeld.

1. Sleep vanuit de componentbrowser de **[!UICONTROL Captcha]** op het adaptieve formulier.

   >[!NOTE]
   >
   >Het gebruik van meer dan één Captcha-component in een adaptieve vorm wordt niet ondersteund. Het wordt ook afgeraden om CAPTCHA te gebruiken in een deelvenster dat is gemarkeerd voor wazig laden of in een fragment.

   >[!NOTE]
   >
   >Captcha is tijdgevoelig en verloopt over ongeveer een minuut. Daarom wordt aangeraden de component Captcha vlak voor de knop Verzenden in het aangepaste formulier te plaatsen.

1. Selecteer de Captcha-component die u hebt toegevoegd en tik op ![cmppr](assets/cmppr.png) om de eigenschappen te bewerken.
1. Geef een titel op voor de CAPTCHA-widget. De standaardwaarde is **Captcha**. Selecteren **[!UICONTROL Hide title]** als u de titel niet wilt weergeven.
1. Van de **[!UICONTROL Captcha service]** vervolgkeuzelijst, selecteert u **[!UICONTROL reCaptcha]** om de dienst reCAPTCHA toe te laten als u het zoals die in vormde [De dienst van ReCAPTCHA door Google](#google-recaptcha). Selecteer een configuratie in het keuzemenu Instellingen. Selecteer ook de grootte als **[!UICONTROL Normal]** of **[!UICONTROL Compact]** voor de reCAPTCHA-widget.

   >[!NOTE]
   >
   >Niet selecteren **[!UICONTROL Default]** van de de dienstdrop-down Captcha aangezien de standaard AEM dienst CAPTCHA wordt afgekeurd.

1. Sla de eigenschappen op.

De reCAPTCHA-service is ingeschakeld op het adaptieve formulier. U kunt een voorbeeld van het formulier bekijken en de CAPTCHA bekijken.
