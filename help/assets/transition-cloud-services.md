---
title: Vertaalwolkenservices toepassen op mappen
description: Vertaalwolkenservices toepassen op mappen
contentOwner: AG
feature: Vertaling
role: Administrator
exl-id: 87883a3f-db95-41f4-b0aa-cdaeb7e6f555
translation-type: tm+mt
source-git-commit: bd94d3949f0117aa3e1c9f0e84f7293a5d6b03b4
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 53%

---

# Bezig met toepassen van vertaalcloud-services op mappen {#applying-translation-cloud-services-to-folders}

Met Adobe Experience Manager (AEM) kunt u vertaalservices in de cloud gebruiken van het vertaalbureau van uw keuze om ervoor te zorgen dat uw middelen op basis van uw vereisten worden vertaald.

U kunt de vertaalcloudservice rechtstreeks toepassen op de map met middelen, zodat u deze kunt gebruiken tijdens vertaalworkflows.

## Vertaalservices {#applying-the-translation-services} toepassen

Als u de vertaalcloud-services rechtstreeks toepast op uw map met middelen, hoeft u geen vertaalservices te configureren wanneer u vertaalworkflows maakt of bijwerkt.

1. Selecteer in de interface Elementen de map waarop u vertaalservices wilt toepassen.
1. Klik of tik op het pictogram **[!UICONTROL Properties]** op de werkbalk om de pagina **[!UICONTROL Folder Properties]** weer te geven.

   ![chlimage_1-215](assets/chlimage_1-215.png)

1. Ga naar het tabblad **[!UICONTROL Cloud Services]**.
1. Kies in de lijst Configuraties van Cloud Servicen de gewenste vertaalprovider. Als u bijvoorbeeld vertaalservices wilt gebruiken vanuit Microsoft, kiest u **[!UICONTROL Microsoft Translator]**.

   ![chlimage_1-216](assets/chlimage_1-216.png)

1. Kies de connector voor de vertaalprovider.

   ![chlimage_1-217](assets/chlimage_1-217.png)

1. Klik of tik op de werkbalk op **[!UICONTROL Save]** en klik vervolgens op **[!UICONTROL OK]** om het dialoogvenster te sluiten. De vertaalservice wordt toegepast op de map.

## Aangepaste vertaalconnector {#applying-custom-translation-connector} toepassen

Als u een aangepaste connector wilt toepassen voor de vertaalservices die u wilt gebruiken in vertaalworkflows. Om een aangepaste connector toe te passen installeert u eerst de connector vanaf Package Manager. Vervolgens configureert u de connector vanaf de Cloud Services-console. Nadat u de connector hebt geconfigureerd, is deze beschikbaar in de lijst met connectors op het tabblad Cloud Services die wordt beschreven in [De vertaalservices toepassen](transition-cloud-services.md#applying-the-translation-services). Nadat u de aangepaste connector hebt toegepast en vertaalworkflows hebt uitgevoerd, geeft de tegel **[!UICONTROL Translation Summary]** van het vertaalproject de connectordetails weer onder de koppen **[!UICONTROL Provider]** en **[!UICONTROL Method]**.

1. Installeer de connector via Package Manager.
1. Klik/tik het AEM embleem, en navigeer aan **[!UICONTROL Tools > Deployment > Cloud Services]**.
1. Zoek de connector die u onder de pagina **[!UICONTROL Third Party Services]** in de **[!UICONTROL Cloud Services]** hebt geïnstalleerd.

   ![chlimage_1-218](assets/chlimage_1-218.png)

1. Klik op de koppeling **[!UICONTROL Configure now]** of tik op deze koppeling om het dialoogvenster **[!UICONTROL Create Configuration]** te openen.

   ![chlimage_1-219](assets/chlimage_1-219.png)

1. Geef een titel en een naam op voor de connector en klik of tik vervolgens op **[!UICONTROL Create]**. De aangepaste connector is beschikbaar in de lijst met connectors op het tabblad **[!UICONTROL Cloud Services]** zoals beschreven in stap 5 van [De vertaalservices toepassen](#applying-the-translation-services).
1. Voer een vertaalworkflow uit die in [Vertaalprojecten maken](translation-projects.md) wordt beschreven nadat u de aangepaste connector hebt toegepast. Verifieer de details van de connector in de tegel **[!UICONTROL Translation Summary]** van het vertaalproject in de **[!UICONTROL Projects]**-console.

   ![chlimage_1-220](assets/chlimage_1-220.png)
