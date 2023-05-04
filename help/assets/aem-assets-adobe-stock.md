---
title: Beheren [!DNL Adobe Stock] activa in [!DNL Adobe Experience Manager Assets].
description: Zoeken, ophalen, licentie en beheren [!DNL Adobe Stock] activa van binnen [!DNL Adobe Experience Manager]. Gebruik de in licentie gegeven activa als elk ander digitaal actief.
contentOwner: AG
feature: Search,Adobe Stock
role: User,Admin
exl-id: f360abaf-a812-46ed-a160-ff569b6bec1c
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 2%

---

# Gebruiken [!DNL Adobe Stock] activa in [!DNL Adobe Experience Manager Assets] {#use-adobe-stock-assets-in-aem-assets}

>[!CAUTION]
>
>AEM 6.4 heeft het einde van de uitgebreide ondersteuning bereikt en deze documentatie wordt niet meer bijgewerkt. Raadpleeg voor meer informatie onze [technische ondersteuningsperioden](https://helpx.adobe.com/support/programs/eol-matrix.html). Ondersteunde versies zoeken [hier](https://experienceleague.adobe.com/docs/).

Organisaties kunnen hun [!DNL Adobe Stock] ondernemingsplan met [!DNL Experience Manager Assets] om ervoor te zorgen dat gelicentieerde middelen breed beschikbaar zijn voor hun creatieve en marketingprojecten, met de krachtige mogelijkheden voor middelenbeheer van [!DNL Experience Manager].

[!DNL Adobe Stock] biedt ontwerpers en bedrijven toegang tot miljoenen kwalitatief hoogstaande, gekrulde, royaltyvrije foto&#39;s, vectoren, illustraties, video&#39;s, sjablonen en 3D-middelen voor al hun creatieve projecten. [!DNL Experience Manager] gebruikers kunnen snel zoeken, voorvertonen en licentiëren [!DNL Adobe Stock] elementen die zijn opgeslagen in [!DNL Experience Manager], zonder de [!DNL Experience Manager] interface.

## Vereisten {#prerequisites}

De integratie vereist een [Enterprise Adobe Stock-abonnement](https://stockenterprise.adobe.com/) en [!DNL Experience Manager] 6.4 met minstens opgesteld Service Pack 2. Voor [!DNL Experience Manager] 6.4 de details van het de dienstpak, zie deze [releaseopmerkingen](/help/release-notes/sp-release-notes.md).

## Integreren [!DNL Experience Manager] en [!DNL Adobe Stock] {#integrate-aem-and-adobe-stock}

Communicatie tussen [!DNL Experience Manager] en [!DNL Adobe Stock], maakt u een IMS-configuratie en een [!DNL Adobe Stock] configuratie in [!DNL Experience Manager].

>[!NOTE]
>
>Alleen [!DNL Experience Manager] beheerders en [!DNL Admin Console] beheerders voor een organisatie kunnen de integratie uitvoeren omdat hiervoor beheerdersrechten vereist zijn.

### Een IMS-configuratie maken {#create-an-ims-configuration}

1. In de [!DNL Experience Manager] gebruikersinterface, navigeren naar **[!UICONTROL Tools]** > **[!UICONTROL Security]** > **[!UICONTROL Adobe IMS Configurations]**. Klik op **[!UICONTROL Create]** en selecteer **[!UICONTROL Cloud Solution]** > **[!UICONTROL Adobe Stock]**.
1. U kunt een bestaand certificaat opnieuw gebruiken of **[!UICONTROL Create new certificate]**.
1. Klik op **[!UICONTROL Create certificate]**. Download de openbare sleutel wanneer deze is gemaakt. Klik op **[!UICONTROL Next]**. Laat de [!UICONTROL Adobe IMS Technical Account Configuration] het scherm open om de vereiste waarden op korte termijn te verstrekken.
1. Toegang [Adobe Developer Console](https://console.adobe.io). Zorg ervoor dat uw account beheerdersmachtigingen heeft voor de organisatie waarvoor de integratie is vereist.
1. Klikken **[!UICONTROL Create new project]** en klik op **[!UICONTROL Add API]**. Selecteren **[!UICONTROL Adobe Stock]** in de lijst met API&#39;s die voor u beschikbaar zijn. Selecteer [!UICONTROL OAUTH 2.0 Web].
1. Verlenen **[!UICONTROL Default redirect URI]** en **[!UICONTROL Redirect URI pattern]** waarden. Klik op **[!UICONTROL Save configured API]**. Kopieer de gegenereerde id en het geheim.
1. In [!UICONTROL Adobe IMS Technical Account Configuration] scherm, geef de waarden op in de vakken met de naam **[!UICONTROL Title]**, **[!UICONTROL Authorization Server]**, **[!UICONTROL API Key]**, **[!UICONTROL Client Secret]**, en **[!UICONTROL Payload]**. Voor gedetailleerde informatie over deze waarden raadpleegt u [Snelle start voor JWT-verificatie](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md).

<!-- TBD: Update the URL when the new URL is available. Logged issue github.com/AdobeDocs/adobeio-auth/issues/63.
-->

### Maken [!DNL Adobe Stock] configuratie in [!DNL Experience Manager] {#create-adobe-stock-configuration-in-aem}

1. In de [!DNL Experience Manager] gebruikersinterface, navigeren naar **[!UICONTROL Tools]** > **[!UICONTROL Cloud Services]** > **[!UICONTROL Adobe Stock]**.
1. Klikken **[!UICONTROL Create]** om een configuratie tot stand te brengen en het te associëren met uw bestaande Configuratie IMS. Selecteren `PROD` als de omgevingsparameter.
1. In **[!UICONTROL Licensed Assets Path]** veld, laat de locatie ongewijzigd. Wijzig niet de locatie waar u de [!DNL Adobe Stock] activa.
1. Voltooi het maken door alle vereiste eigenschappen toe te voegen. Klik op **[!UICONTROL Save & Close]**.
1. Toevoegen [!DNL Experience Manager] gebruikers of groepen die een licentie voor de elementen kunnen aanschaffen.

>[!NOTE]
>
>Als er meerdere [!DNL Adobe Stock] -configuraties, selecteert u de gewenste configuratie in het deelvenster Gebruikersvoorkeuren (**[!UICONTROL AEM]** > **[!UICONTROL User Icon]** > **[!UICONTROL User Preferences]** > **[!UICONTROL Stock Configuration]**).

## Gebruiken en beheren [!DNL Adobe Stock] activa in [!DNL Experience Manager] {#usemanage}

Met behulp van deze mogelijkheid kunnen organisaties hun gebruikers toestaan te werken met [!DNL Adobe Stock] activa in [!DNL Experience Manager Assets]. Van binnen [!DNL Experience Manager] gebruikersinterface, gebruikers kunnen zoeken [!DNL Adobe Stock] activa en de vereiste activa in licentie geven.

Eenmaal [!DNL Adobe Stock] activum is in licentie gegeven in [!DNL Experience Manager], kan het als typisch activa worden gebruikt en worden beheerd. In [!DNL Experience Manager]kunnen de gebruikers de middelen zoeken en voorvertonen; de elementen kopiëren en publiceren; delen van de activa op [!DNL Brand Portal]; toegang tot en gebruik de middelen via [!DNL Experience Manager] bureaubladtoepassing; enzovoort.

![Zoeken naar Adobe Stock-middelen en filterresultaten vanuit uw Adobe Experience Manager-werkruimte](assets/adobe-stock-search-results-workspace.png)

*Afbeelding: Zoeken naar [!DNL Adobe Stock] elementen en filterresultaten van uw [!DNL Experience Manager] interface.*

**A.** Zoeken naar elementen die vergelijkbaar zijn met de elementen waarvan [!DNL Adobe Stock] ID is opgegeven. **B.** Zoek naar assets die overeenkomen met de vorm of afdrukstand die u hebt geselecteerd. **C.** Een of meer ondersteunde elementtypen zoeken **D.** Het venster Filters openen of samenvouwen **E.** Licentie toewijzen en het geselecteerde element opslaan in [!DNL Experience Manager] **F.** Middel opslaan in [!DNL Experience Manager] met watermerk **G.** Middelen verkennen op [!DNL Adobe Stock] website die vergelijkbaar is met het geselecteerde element **H.** Geselecteerde elementen weergeven op [!DNL Adobe Stock] website **I.** Aantal geselecteerde elementen uit de zoekresultaten **J.** Schakelen tussen de kaartweergave en de lijstweergave

### Elementen zoeken {#find-assets}

Uw [!DNL Experience Manager] gebruikers, naar elementen in beide kunnen zoeken, [!DNL Experience Manager] en [!DNL Adobe Stock]. Wanneer de zoeklocatie niet beperkt is tot [!DNL Adobe Stock], de zoekresultaten van [!DNL Experience Manager] en [!DNL Adobe Stock] worden weergegeven.

* Als u wilt zoeken naar [!DNL Adobe Stock] elementen, klik op **[!UICONTROL Navigation]** > **[!UICONTROL Assets]** > **[!UICONTROL Search Adobe Stock]**.

* Zoeken naar elementen over [!DNL Adobe Stock] en [!DNL Experience Manager Assets], klikt u op Zoeken ![search_icon](assets/search_icon.png).

U kunt ook beginnen met typen `Location: Adobe Stock` in de zoekbalk om [!DNL Adobe Stock] activa. [!DNL Experience Manager] biedt geavanceerde filtermogelijkheden voor de gezochte middelen, die gebruikers toestaan om op de vereiste activa snel nul-binnen op de filters te gebruiken, zoals types van gesteunde activa, beeldrichtlijn, en vergunning gegeven staat.

>[!NOTE]
>
>Middelen die zijn doorzocht van [!DNL Adobe Stock] worden alleen weergegeven in [!DNL Experience Manager]. [!DNL Adobe Stock] elementen worden opgehaald en opgeslagen in [!DNL Experience Manager] alleen na een gebruiker [een element opslaan](/help/assets/aem-assets-adobe-stock.md#saveassets) of [licenties en slaat een middel op](/help/assets/aem-assets-adobe-stock.md#licenseassets). Elementen die al zijn opgeslagen in [!DNL Experience Manager] worden weergegeven en gemarkeerd voor eenvoudige referentie en toegang. Ook de [!DNL Stock] elementen worden met enkele aanvullende metagegevens opgeslagen om de bron aan te geven als [!DNL Stock].

![Zoekfilters in Experience Manager en gemarkeerde Adobe Stock-elementen in zoekresultaten](assets/aem-search-filters2.jpg)

*Afbeelding: Filters zoeken in [!DNL Experience Manager] en gemarkeerd [!DNL Adobe Stock] elementen in zoekresultaten.*

### De vereiste elementen opslaan en weergeven {#saveassets}

Selecteer een middel waarin u wilt opslaan [!DNL Experience Manager]. Klikken [!UICONTROL Save] in de werkbalk bovenaan en geef de naam en locatie van het element op. De elementen zonder licentie worden lokaal met een watermerk opgeslagen.

De volgende keer dat u naar elementen zoekt, worden de opgeslagen elementen gemarkeerd met een badge om aan te geven dat dergelijke elementen beschikbaar zijn in [!DNL Experience Manager Assets].

>[!NOTE]
>
>De onlangs toegevoegde elementen geven een nieuwe badge weer in plaats van een badge met licentie.

### Licentie-elementen {#licenseassets}

Gebruikers kunnen licenties [!DNL Adobe Stock] activa door gebruik te maken van het quotum van hun [!DNL Adobe Stock] ondernemingsplan. Wanneer u een licentie voor een element aanschaft, wordt het zonder watermerk opgeslagen en is het beschikbaar voor zoeken en gebruiken in [!DNL Experience Manager Assets].

![Dialoogvenster voor het in licentie geven en opslaan van Adobe Stock-middelen in Experience Manager Assets](assets/aem-stock_licenseandsave.jpg)

*Afbeelding: Dialoogvenster voor licentie en opslaan [!DNL Adobe Stock] activa in [!DNL Experience Manager Assets].*

### Metagegevens en elementen openen {#access-metadata-and-asset-properties}

Gebruikers kunnen de metagegevens openen en voorvertonen, inclusief de [!DNL Adobe Stock] eigenschappen van metagegevens voor de elementen die zijn opgeslagen in [!DNL Experience Manager]en toevoegen **[!UICONTROL License References]** voor een actief. De updates voor de licentieverwijzing worden echter niet gesynchroniseerd tussen [!DNL Experience Manager] en [!DNL Adobe Stock] website.

Gebruikers kunnen de eigenschappen van zowel gelicentieerde als niet-gelicentieerde activa zien.

![Metagegevens en licentieverwijzingen van opgeslagen elementen weergeven en openen](assets/metadata_properties.jpg)

*Afbeelding: Metagegevens en licentieverwijzingen van opgeslagen elementen weergeven en openen.*

## Bekende beperkingen {#known-limitations}

* **Waarschuwing voor redactionele afbeelding wordt niet weergegeven**: Wanneer gebruikers een licentie voor een afbeelding verlenen, kunnen ze niet controleren of een afbeelding alleen voor gebruik als redactie is. Om mogelijk misbruik te voorkomen, kunnen de beheerders de toegang tot redactionele activa van de Admin Console uitschakelen.

* **Onjuist licentietype wordt weergegeven**: Het is mogelijk dat een onjuist licentietype wordt weergegeven in [!DNL Experience Manager] voor een actief. Gebruikers kunnen zich aanmelden bij de [!DNL Adobe Stock] website om het licentietype te zien.

* **Referentievelden en metagegevens zijn niet gesynchroniseerd**: Wanneer een gebruiker een veld met een licentieverwijzing bijwerkt, wordt de informatie over de licentieverwijzing bijgewerkt in [!DNL Experience Manager] maar niet op de [!DNL Adobe Stock] website. Op dezelfde manier als de gebruiker de verwijzingsgebieden op de [!DNL Adobe Stock] website, worden de updates niet gesynchroniseerd in [!DNL Experience Manager].

>[!MORELIKETHIS]
>
>* [Videozelfstudie bij gebruik [!DNL Adobe Stock] activa met [!DNL Experience Manager Assets]](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/creative-workflows/adobe-stock.html)
>* [[!DNL Adobe Stock] Help bij bedrijfsplan](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/adobe-stock-enterprise.ug.html)
>* [[!DNL Adobe Stock] Veelgestelde vragen](https://helpx.adobe.com/stock/faq.html)

