---
title: Integratie van AEM-middelen met Experience Cloud en Creative Cloud configureren
description: Leer hoe u de integratie van AEM Assets kunt configureren met Experience Cloud en Creative Cloud
uuid: 73f90846-71d0-4f72-8784-dc877e0e9c41
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.4/SITES
discoiquuid: c2f190af-656e-4435-9f44-2698d41c4ad1
translation-type: tm+mt
source-git-commit: fb2567cdf5a0ae210270366899b49db256374f25

---


# Integratie van AEM-middelen met Experience Cloud en Creative Cloud configureren {#configure-aem-assets-integration-with-experience-cloud-and-creative-cloud}

Als u een Adobe Experience Cloud-klant bent, kunt u uw middelen in Adobe Experience Manager (AEM)-middelen synchroniseren met Adobe Creative Cloud en andersom. U kunt uw middelen met de Wolk van de Ervaring ook synchroniseren en vice versa. U kunt deze synchronisatie instellen via Adobe I/O.

De workflow voor het instellen van deze integratie is:

1. Maak een verificatie in Adobe I/O met een openbare gateway en ontvang een toepassings-id.
1. Maak een profiel op uw AEM Assets-instantie met de toepassings-id.
1. Gebruik deze configuratie om uw middelen binnen AEM-middelen te synchroniseren met Creative Cloud.

Op de achtergrond wordt uw profiel door de AEM-server geverifieerd met de gateway en worden de gegevens vervolgens gesynchroniseerd tussen AEM Assets en Experience Cloud.

>[!NOTE]
>
>De functie AEM naar Adobe Creative Cloud voor het delen van mappen is verouderd. Leer meer en zoek naar een betere methode in de best practices [voor](../assets/aem-cc-integration-best-practices.md)AEM- en Creative Cloud-integratie. De configuratie van AEM voor replicatie van de Marketing Cloud en het uitwisselen van middelen tussen AEM Assets en Marketing Cloud is niet verouderd.

![Gegevensstroom wanneer AEM Assets en Creative Cloud zijn geïntegreerd](assets/chlimage_1-287.png)

Gegevensstroom wanneer AEM Assets en Creative Cloud zijn geïntegreerd

>[!NOTE]
>
>Voor het delen van elementen tussen Adobe Experience Cloud en Adobe Creative Cloud zijn beheerdersrechten voor de AEM-instantie vereist.

>[!CAUTION]
>
>Adobe Maketing Cloud is omgedoopt tot Adobe Experience Cloud. In de onderstaande procedures wordt nog steeds de Marketing Cloud vermeld om de huidige interface te weerspiegelen.

## Een toepassing maken {#create-an-application}

1. U kunt de Adobe Developer Gateway-interface openen door u aan te melden op [https://legacy-oauth.cloud.adobe.io](https://legacy-oauth.cloud.adobe.io/).

   >[!NOTE]
   >
   >U hebt beheerdersrechten nodig om een toepassings-id te maken.

1. Navigeer in het linkerdeelvenster naar **[!UICONTROL Gereedschappen]** voor ontwikkelaars > **[!UICONTROL Toepassingen]** om een lijst met toepassingen weer te geven.
1. Klik op **[!UICONTROL Add]** ![name_assets_addcircle_icon](assets/aem_assets_addcircle_icon.png) om een toepassing te maken.
1. Selecteer in de lijst **[!UICONTROL Client Credentials]** de optie **[!UICONTROL Service Account (JWT Assertion)]**. Dit is een server-naar-server communicatieservice voor serververificatie.

   ![chlimage_1-288](assets/chlimage_1-288.png)

1. Geef een naam voor de toepassing en een optionele beschrijving op.
1. Selecteer in de lijst **[!UICONTROL Organisatie]** de organisatie waarvoor u elementen wilt synchroniseren.
1. Selecteer in de lijst **[!UICONTROL Bereik]** de optie **[!UICONTROL dam-read]**, **[!UICONTROL dam-sync]**, **[!UICONTROL dam-write]** en **[!UICONTROL cc-share]**.
1. Klik op **[!UICONTROL Maken]**. Een bericht meldt dat de toepassing is gemaakt.

   ![Melding van het feit dat de toepassing is gemaakt om AEM Assets te integreren met Adobe CC](assets/chlimage_1-289.png)

1. Kopieer de **[!UICONTROL toepassings-id]** die voor de nieuwe toepassing wordt gegenereerd.

   >[!CAUTION]
   >
   >Zorg ervoor dat u het **[!UICONTROL toepassingsgeheim]** niet per ongeluk kopieert in plaats van de **[!UICONTROL toepassings-id]**.

## Nieuwe configuratie toevoegen aan Marketing Cloud {#add-a-new-configuration-to-marketing-cloud}

1. Klik op het AEM-logo in de gebruikersinterface van uw lokale AEM Assets-instantie en navigeer naar **[!UICONTROL Extra]** > **[!UICONTROL Cloud Services]** > **[!UICONTROL Oudere Cloud Services]**.

1. Zoek de **[!UICONTROL Adobe Marketing Cloud]** -service. Als er geen configuraties bestaan, klikt u op **[!UICONTROL Nu]** configureren. Als configuraties bestaan, klik **[!UICONTROL tonen Configuraties]** en klik **[!UICONTROL [+]]** om een nieuwe configuratie toe te voegen.

   >[!NOTE]
   >
   >Gebruik een Adobe-id-account met beheerdersrechten voor de organisatie.

1. Geef in het dialoogvenster Configuratie **** maken een titel en naam voor de nieuwe configuratie op en klik op **[!UICONTROL Maken]**.

   ![Geef een nieuwe configuratie de naam om AEM Assets en CC te integreren](assets/cloudservices_configure_mc.png)

1. Geef in het veld URL **** huurder de URL voor AEM-elementen op.

   >[!CAUTION]
   >
   >Als u de URL voor de huurder hebt ingevoerd als **https://&lt;huurder_id>.marketing.adobe.com** , moet u deze wijzigen in **https://&lt;huurder_id>.ExperienceCloud.adobe.com.** Hiervoor voert u de volgende stappen uit:
   1. Ga naar **Gereedschappen > Cloud Services > Legacy Cloud Services**.
   1. Klik onder Adobe Marketing Cloud op **Configuraties** tonen.
   1. Selecteer de configuratie die tijdens vestiging AEM-MAC-CC synchronisatie werd gecreeerd.
   1. Bewerk de configuratie van cloudservice en vervang **marketing.adobe.com** in het veld Tenant URL naar **experienceCloudservice.adobe.com**.
   1. Sla de configuratie op.
   1. Test de MAC-sync replicatieagenten.


1. Plak in het veld **[!UICONTROL Client-id]** de toepassings-id die u hebt gekopieerd aan het einde van de procedure [Een toepassing](/help/sites-administering/configure-assets-cc-integration.md#create-an-application)maken.

   ![Geef de waarden voor de toepassings-id op die vereist zijn voor de integratie van AEM-middelen en Creative Cloud](assets/cloudservices_tenant_info.png)

1. Selecteer onder **[!UICONTROL Synchronisatie]** de optie **[!UICONTROL Ingeschakeld]** om synchronisatie in te schakelen en klik op **[!UICONTROL OK]**.

   >[!NOTE]
   Als u **uitgeschakeld** selecteert, werkt de synchronisatie in één richting.

1. Van de configuratiepagina, klik de Openbare Sleutel **[!UICONTROL van de]** Vertoning om de openbare sleutel te tonen die voor uw instantie wordt geproduceerd. U kunt ook op Openbare sleutel **[!UICONTROL downloaden voor OAuth Gateway]** om het bestand met de openbare sleutel te downloaden. Open vervolgens het bestand om de openbare sleutel weer te geven.

## Synchronisatie inschakelen {#enable-synchronization}

1. Toon de openbare sleutel gebruikend één van de volgende methodes die in de laatste stap van de procedure worden vermeld [voeg een nieuwe configuratie aan de Wolk](/help/sites-administering/configure-assets-cc-integration.md#add-a-new-configuration-to-marketing-cloud)van de Marketing toe. Klik op **[!UICONTROL Openbare sleutel]** weergeven.

   ![chlimage_1-292](assets/chlimage_1-292.png)

1. Kopieer de openbare sleutel en plak het in het **[!UICONTROL Openbare Zeer belangrijke]** gebied van configuratieinterface van de toepassing u in [Create een toepassing](/help/sites-administering/configure-assets-cc-integration.md#create-an-application)creeerde.

   ![chlimage_1-293](assets/chlimage_1-293.png)

1. Klik op **[!UICONTROL Bijwerken]**. Synchroniseer uw elementen nu met de AEM Assets-instantie.

## Synchronisatie testen {#test-the-synchronization}

1. Klik op het AEM-logo in de gebruikersinterface van uw lokale AEM Assets-instantie en navigeer naar **[!UICONTROL Tools]**> **[!UICONTROL Deployment]**> **[!UICONTROL Replication]**om de replicatieprofielen te zoeken die voor synchronisatie zijn gemaakt.
1. Voor de pagina van de **[!UICONTROL Replicatie]** , klik **[!UICONTROL Agenten op auteur]**.
1. Klik in de lijst met profielen op het standaard replicatieprofiel voor uw organisatie om dit te openen.
1. Klik in het dialoogvenster op Verbinding **[!UICONTROL testen]**.

   ![Verbinding testen en standaardreplicatieprofiel voor uw organisatie instellen](assets/chlimage_1-294.png)

1. Wanneer de replicatierest voltooit, controleer een succesbericht aan het eind van de testresultaten.

## Gebruikers toevoegen aan de Marketing Cloud {#add-users-to-marketing-cloud}

1. Meld u met beheerdersgegevens aan bij Marketing Cloud.
1. Ga vanaf de rails naar **[!UICONTROL Beheer]**en klik/tik op **[!UICONTROL Enterprise-dashboard]** starten.
1. Klik in de track op **[!UICONTROL Gebruikers]** om de pagina **[!UICONTROL Gebruikersbeheer]** te openen.
1. Klik op de werkbalk op **Toevoegen** /Tikken ![naam_elementen_add_icon](assets/aem_assets_add_icon.png).
1. Voeg een of meer gebruikers toe die u de mogelijkheid wilt bieden middelen te delen met Creative Cloud.

   >[!NOTE]
   Alleen de gebruikers die u toevoegt aan de Marketing Cloud kunnen middelen van AEM Assets delen naar Creative Cloud.

## Middelen uitwisselen tussen AEM Assets en Marketing Cloud {#exchange-assets-between-aem-assets-and-marketing-cloud}

1. Meld u aan bij AEM Assets.
1. Maak een map in de middelenconsole en upload enkele bestanden naar deze map. Maak bijvoorbeeld een map **mc-demo** en upload er middelen aan.
1. Selecteer de map en klik op **Share** ![assets_share](assets/assets_share.png).
1. Selecteer **[!UICONTROL Adobe Marketing Cloud]** in het menu en klik op **[!UICONTROL Delen]**. Een bericht meldt dat de map wordt gedeeld met Marketing Cloud.

   ![chlimage_1-295](assets/chlimage_1-295.png)

   >[!NOTE]
   Het delen van een map met middelen van het type `sling:OrderedFolder`, wordt niet ondersteund in de context van delen in Adobe Marketing Cloud. Als u een map wilt delen, selecteert u bij het maken ervan in AEM Assets niet de optie **[!UICONTROL Geordend]** .

1. Vernieuw de gebruikersinterface van AEM Assets. De map die u hebt gemaakt in de middelenconsole van uw lokale AEM Assets-instantie, wordt gekopieerd naar de gebruikersinterface van de marketingcloud. Het element dat u uploadt naar de map in AEM Assets wordt weergegeven in de kopie van de map in Marketing Cloud nadat deze is verwerkt door de AEM-server.
1. U kunt ook middelen uploaden in de gedupliceerde kopie van de map in de Marketing Cloud. Nadat het element is verwerkt, wordt het in de gedeelde map in AEM Assets weergegeven.

## Middelen uitwisselen tussen AEM Assets en Creative Cloud {#exchange-assets-between-aem-assets-and-creative-cloud}

Met AEM Assets kunt u mappen met elementen delen met gebruikers van Adobe Creative Cloud.

1. Selecteer in de middelenconsole de map die u wilt delen met Creative Cloud.
1. Klik in de werkbalk op **[!UICONTROL Delen]** ![assets_share](assets/assets_share.png).
1. Selecteer in de lijst de optie **[!UICONTROL Adobe Creative Cloud]** .

   >[!NOTE]
   De opties zijn beschikbaar voor gebruikers met leesmachtigingen in de hoofdmap. Gebruikers moeten de vereiste machtigingen hebben om toegang te krijgen tot de informatie van de replicatieagent van de Marketing Cloud.

1. Voeg op de pagina **[!UICONTROL Creative Cloud Sharing]** de gebruiker toe om de map te delen met en kies een rol voor de gebruiker. Klik op **[!UICONTROL Opslaan]** en **[!UICONTROL OK]**.

1. Meld u aan bij Creative Cloud met de referenties van de gebruiker met wie u de map hebt gedeeld. De gedeelde map is beschikbaar in Creative Cloud.

De synchronisatie van de AEM Assets-Marketing Cloud is zodanig ontworpen dat de instantie van de gebruikerscomputer van waaruit het element is geüpload het recht behoudt om het element te wijzigen. Alleen deze wijzigingen worden doorgegeven aan de andere instantie.

Als een element bijvoorbeeld wordt geüpload vanaf een instantie van AEM Assets (op locatie), worden de wijzigingen in het element van deze instantie doorgegeven aan de instantie Marketing Cloud. De wijzigingen die zijn doorgevoerd van de instantie Marketing Cloud naar hetzelfde element, worden echter niet doorgevoerd in de AEM-instantie en andersom voor middelen die zijn geüpload vanuit de marketingcloud.

>[!MORELIKETHIS]
* [Aanbevolen werkwijzen voor AEM- en Creative Cloud-integratie](../assets/aem-cc-integration-best-practices.md)
* [Aanbevolen werkwijzen delen via AEM naar Creative Cloud-map](../assets/aem-cc-folder-sharing-best-practices.md)

